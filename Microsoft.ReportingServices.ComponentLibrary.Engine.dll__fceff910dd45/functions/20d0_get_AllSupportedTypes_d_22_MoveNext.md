# <get_AllSupportedTypes>d__22::MoveNext

- ea: `0x20d0`
- end: `0x21c5`
- name: `<get_AllSupportedTypes>d__22::MoveNext`
- size: `245`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x9f0`
- `0xa00`
- `0xa10`
- `0xa20`
- `0xa30`
- `0xa40`
- `0xa50`
- `0x20d0`

## pseudocode

```c

```

## disassembly

```asm
0x20d0  ldarg.0
0x20d1  ldfld    int32 <get_AllSupportedTypes>d__22::<>1__state
0x20d6  stloc.0
0x20d7  ldloc.0
0x20d8  switch   loc_20FF, loc_211A, loc_2135, loc_2150, loc_216B, loc_2186, loc_21A1, loc_21BC
0x20fd  ldc.i4.0
0x20fe  ret
0x20ff  ldarg.0
0x2100  ldc.i4.m1
0x2101  stfld    int32 <get_AllSupportedTypes>d__22::<>1__state
0x2106  ldarg.0
0x2107  call     class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::get_Chart()
0x210c  stfld    class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType <get_AllSupportedTypes>d__22::<>2__current
0x2111  ldarg.0
0x2112  ldc.i4.1
0x2113  stfld    int32 <get_AllSupportedTypes>d__22::<>1__state
0x2118  ldc.i4.1
0x2119  ret
0x211a  ldarg.0
0x211b  ldc.i4.m1
0x211c  stfld    int32 <get_AllSupportedTypes>d__22::<>1__state
0x2121  ldarg.0
0x2122  call     class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::get_GaugePanel()
0x2127  stfld    class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType <get_AllSupportedTypes>d__22::<>2__current
0x212c  ldarg.0
0x212d  ldc.i4.2
0x212e  stfld    int32 <get_AllSupportedTypes>d__22::<>1__state
0x2133  ldc.i4.1
0x2134  ret
0x2135  ldarg.0
0x2136  ldc.i4.m1
0x2137  stfld    int32 <get_AllSupportedTypes>d__22::<>1__state
0x213c  ldarg.0
0x213d  call     class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::get_Image()
0x2142  stfld    class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType <get_AllSupportedTypes>d__22::<>2__current
0x2147  ldarg.0
0x2148  ldc.i4.3
0x2149  stfld    int32 <get_AllSupportedTypes>d__22::<>1__state
0x214e  ldc.i4.1
0x214f  ret
0x2150  ldarg.0
0x2151  ldc.i4.m1
0x2152  stfld    int32 <get_AllSupportedTypes>d__22::<>1__state
0x2157  ldarg.0
0x2158  call     class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::get_Rectangle()
0x215d  stfld    class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType <get_AllSupportedTypes>d__22::<>2__current
0x2162  ldarg.0
0x2163  ldc.i4.4
0x2164  stfld    int32 <get_AllSupportedTypes>d__22::<>1__state
0x2169  ldc.i4.1
0x216a  ret
0x216b  ldarg.0
0x216c  ldc.i4.m1
0x216d  stfld    int32 <get_AllSupportedTypes>d__22::<>1__state
0x2172  ldarg.0
0x2173  call     class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::get_Tablix()
0x2178  stfld    class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType <get_AllSupportedTypes>d__22::<>2__current
0x217d  ldarg.0
0x217e  ldc.i4.5
0x217f  stfld    int32 <get_AllSupportedTypes>d__22::<>1__state
0x2184  ldc.i4.1
0x2185  ret
0x2186  ldarg.0
0x2187  ldc.i4.m1
0x2188  stfld    int32 <get_AllSupportedTypes>d__22::<>1__state
0x218d  ldarg.0
0x218e  call     class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::get_Map()
0x2193  stfld    class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType <get_AllSupportedTypes>d__22::<>2__current
0x2198  ldarg.0
0x2199  ldc.i4.6
0x219a  stfld    int32 <get_AllSupportedTypes>d__22::<>1__state
0x219f  ldc.i4.1
0x21a0  ret
0x21a1  ldarg.0
0x21a2  ldc.i4.m1
0x21a3  stfld    int32 <get_AllSupportedTypes>d__22::<>1__state
0x21a8  ldarg.0
0x21a9  call     class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::get_ReportParameter()
0x21ae  stfld    class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType <get_AllSupportedTypes>d__22::<>2__current
0x21b3  ldarg.0
0x21b4  ldc.i4.7
0x21b5  stfld    int32 <get_AllSupportedTypes>d__22::<>1__state
0x21ba  ldc.i4.1
0x21bb  ret
0x21bc  ldarg.0
0x21bd  ldc.i4.m1
0x21be  stfld    int32 <get_AllSupportedTypes>d__22::<>1__state
0x21c3  ldc.i4.0
0x21c4  ret
```
