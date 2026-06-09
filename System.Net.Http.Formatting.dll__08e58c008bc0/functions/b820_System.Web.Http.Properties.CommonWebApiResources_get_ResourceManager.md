# System.Web.Http.Properties.CommonWebApiResources::get_ResourceManager

- ea: `0xb820`
- end: `0xb88a`
- name: `System.Web.Http.Properties.CommonWebApiResources::get_ResourceManager`
- size: `106`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb8b0`
- `0xb8d0`
- `0xb8f0`
- `0xb910`
- `0xb930`
- `0xb950`
- `0xb970`

## callees

- `0xb820`

## pseudocode

```c

```

## disassembly

```asm
0xb820  ldsfld   class [mscorlib]System.Resources.ResourceManager System.Web.Http.Properties.CommonWebApiResources::resourceMan
0xb825  brtrue.s loc_B884
0xb827  ldtoken  System.Web.Http.Properties.CommonWebApiResources
0xb82c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb831  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0xb836  stloc.0
0xb837  ldloc.0
0xb838  callvirt instance string[] [mscorlib]System.Reflection.Assembly::GetManifestResourceNames()
0xb83d  ldsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__4_0
0xb842  dup
0xb843  brtrue.s loc_B85C
0xb845  pop
0xb846  ldsfld   class <>c <>c::<>9
0xb84b  ldftn    instance bool <>c::<get_ResourceManager>b__4_0(string s)
0xb851  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0xb856  dup
0xb857  stsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__4_0
0xb85c  call     T0x2B00005F
0xb861  call     T0x2B000060
0xb866  stloc.1
0xb867  ldloc.1
0xb868  ldc.i4.0
0xb869  ldloc.1
0xb86a  callvirt instance int32 [mscorlib]System.String::get_Length()
0xb86f  ldc.i4.s 0xA
0xb871  sub
0xb872  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xb877  stloc.1
0xb878  ldloc.1
0xb879  ldloc.0
0xb87a  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0xb87f  stsfld   class [mscorlib]System.Resources.ResourceManager System.Web.Http.Properties.CommonWebApiResources::resourceMan
0xb884  ldsfld   class [mscorlib]System.Resources.ResourceManager System.Web.Http.Properties.CommonWebApiResources::resourceMan
0xb889  ret
```
