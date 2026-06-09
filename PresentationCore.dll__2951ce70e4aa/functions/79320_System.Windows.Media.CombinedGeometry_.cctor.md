# System.Windows.Media.CombinedGeometry::.cctor

- ea: `0x79320`
- end: `0x793d6`
- name: `System.Windows.Media.CombinedGeometry::.cctor`
- size: `182`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x84760`
- `0xbfb60`

## string_xrefs

- `0x7933f`: `GeometryCombineMode`

## pseudocode

```c

```

## disassembly

```asm
0x79320  call     class System.Windows.Media.Geometry System.Windows.Media.Geometry::get_Empty()
0x79325  stsfld   class System.Windows.Media.Geometry System.Windows.Media.CombinedGeometry::s_Geometry1
0x7932a  call     class System.Windows.Media.Geometry System.Windows.Media.Geometry::get_Empty()
0x7932f  stsfld   class System.Windows.Media.Geometry System.Windows.Media.CombinedGeometry::s_Geometry2
0x79334  ldtoken  System.Windows.Media.CombinedGeometry
0x79339  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7933e  stloc.0
0x7933f  ldstr    aGeometrycombin// "GeometryCombineMode"
0x79344  ldtoken  System.Windows.Media.GeometryCombineMode
0x79349  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7934e  ldloc.0
0x7934f  ldc.i4.0
0x79350  box      System.Windows.Media.GeometryCombineMode
0x79355  ldnull
0x79356  ldftn    void System.Windows.Media.CombinedGeometry::GeometryCombineModePropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x7935c  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x79361  ldnull
0x79362  ldftn    bool System.Windows.Media.ValidateEnums::IsGeometryCombineModeValid(object valueObject)
0x79368  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x7936d  ldc.i4.0
0x7936e  ldnull
0x7936f  call     class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Animation.Animatable::RegisterProperty(string name, class [mscorlib]System.Type propertyType, class [mscorlib]System.Type ownerType, object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback changed, class [WindowsBase]System.Windows.ValidateValueCallback validate, bool isIndependentlyAnimated, class [WindowsBase]System.Windows.CoerceValueCallback coerced)
0x79374  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.CombinedGeometry::GeometryCombineModeProperty
0x79379  ldstr    aGeometry1// "Geometry1"
0x7937e  ldtoken  System.Windows.Media.Geometry
0x79383  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x79388  ldloc.0
0x79389  call     class System.Windows.Media.Geometry System.Windows.Media.Geometry::get_Empty()
0x7938e  ldnull
0x7938f  ldftn    void System.Windows.Media.CombinedGeometry::Geometry1PropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x79395  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x7939a  ldnull
0x7939b  ldc.i4.0
0x7939c  ldnull
0x7939d  call     class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Animation.Animatable::RegisterProperty(string name, class [mscorlib]System.Type propertyType, class [mscorlib]System.Type ownerType, object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback changed, class [WindowsBase]System.Windows.ValidateValueCallback validate, bool isIndependentlyAnimated, class [WindowsBase]System.Windows.CoerceValueCallback coerced)
0x793a2  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.CombinedGeometry::Geometry1Property
0x793a7  ldstr    aGeometry2// "Geometry2"
0x793ac  ldtoken  System.Windows.Media.Geometry
0x793b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x793b6  ldloc.0
0x793b7  call     class System.Windows.Media.Geometry System.Windows.Media.Geometry::get_Empty()
0x793bc  ldnull
0x793bd  ldftn    void System.Windows.Media.CombinedGeometry::Geometry2PropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x793c3  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x793c8  ldnull
0x793c9  ldc.i4.0
0x793ca  ldnull
0x793cb  call     class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Animation.Animatable::RegisterProperty(string name, class [mscorlib]System.Type propertyType, class [mscorlib]System.Type ownerType, object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback changed, class [WindowsBase]System.Windows.ValidateValueCallback validate, bool isIndependentlyAnimated, class [WindowsBase]System.Windows.CoerceValueCallback coerced)
0x793d0  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.CombinedGeometry::Geometry2Property
0x793d5  ret
```
