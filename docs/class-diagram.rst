Class Diagram
=============

Class
-----

.. admonition:: 9.2.4.1 Classifiers
  :class: tip

  The default notation for a Classifier is a solid-outline rectangle containing
  the Classifier’s name, and with compartments separated by horizontal lines
  below the name. The name of the Classifier should be centered in boldface.
  For those languages that distinguish between uppercase and lowercase
  characters, Classifier names should begin with an uppercase character.

.. code-block:: cpp

  class Foo { /* ... */ };

.. image:: class-diagram/simple-class.png
  :align: center

.. code-block:: cpp

  class A {
   public:
    int foo;
    bool boo;

    float bar();
    double baz(int val, bool cond);
  };

.. image:: class-diagram/attributes-methods-class.png
  :align: center

.. admonition:: 10.4.4 Notation
  :class: tip

  An Interface may be designated using the default notation for Classifier (see
  9.2.4) with the keyword «interface».

.. admonition:: 9.2.4.1 Classifiers
  :class: tip

  If the default notation is used for a Classifier, a keyword corresponding to
  the metaclass of the Classifier shall be shown in guillemets above the name.

.. code-block:: cpp

  class Foo {
   public:
    virtual bool foo();
  };

.. image:: class-diagram/interface-class.png
  :align: center

.. admonition:: 9.2.4.1 Classifiers
  :class: tip

  The name of an abstract Classifier is shown in italics, where permitted by
  the font in use. Alternatively or in addition, an abstract Classifier may be
  shown using the textual annotation {abstract} after or below its name .

.. code-block:: cpp

  class A {
   public:
    virtual void boo(int x) =0;
  };

.. image:: class-diagram/abstract-class.png
  :align: center

.. admonition:: 9.2.4.1 Classifiers
  :class: tip

  Any compartment which contains notation for Features may show those Features
  grouped under the literals public, private and protected, representing their
  visibility . The visibility literals are left-justified in the compartment
  with the Features’ notation appearing indented beneath them. The groups may
  appear in any order. Visibility grouping is optional: a conforming tool need
  not support it.

.. code-block:: cpp

  class A {
   public:
    int boo;

   private:
    bool foo;

   public:
    void bar();

   private:
    void baz();
  };

.. image:: class-diagram/visibility-literals.png
  :align: center

Generalization
--------------

.. admonition:: 9.2.4.2 Other elements
  :class: tip

  A Generalization is shown as a line with a hollow triangle as an arrowhead
  between the symbols representing the involved Classifiers. The arrowhead
  points to the symbol representing the general Classifier.

.. code-block:: cpp

  class Foo { /* ... */ };
  class Boo { /* ... */ };

  class Bar: public Foo, public Boo { /* ... */ };

.. image:: class-diagram/generalization.png
  :align: center

Usage
-----

.. admonition:: 7.7.4 Notation
  :class: tip

  A Dependency is shown as a dashed arrow between two model Elements. The model
  Element at the tail of the arrow (the client) depends on the model Element
  at the arrowhead (the supplier). The arrow may be labeled with an optional
  keyword or stereotype and an optional name (see Figure 7.18).

.. admonition:: 7.7.4 Notation
  :class: tip

  A Usage is shown as a Dependency with a «use» keyword attached to it.

.. code-block:: cpp

  class Foo {
   public:
    void foo();
  };

  class Boo {
   public:
    void boo(Foo& x) {
      return x.foo();
    }
  };

.. image:: class-diagram/usage.png
  :align: center

Realization
-----------

.. admonition:: 7.7.4 Notation
  :class: tip

  A Realization is shown as a dashed line with a triangular arrowhead at the
  end that corresponds to the realized Element.

.. code-block:: cpp

  class Foo {
   public:
    virtual void foo() =0;
  };

  class Boo: public Foo {
   public:
    virtual void foo() { /* ... */ }
  };

.. image:: class-diagram/realization.png
  :align: center
