# System.Web.ApplicationServices.ApplicationServiceHelper::EnsureProfileServiceEnabled

- ea: `0x392f0`
- end: `0x3931b`
- name: `System.Web.ApplicationServices.ApplicationServiceHelper::EnsureProfileServiceEnabled`
- size: `43`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x750`
- `0x770`
- `0x790`
- `0x7a0`
- `0x38a00`
- `0x38ad0`
- `0x38b80`
- `0x38d10`

## callees

- `0x280f0`
- `0x39140`
- `0x392f0`

## string_xrefs

- `0x39309`: `ProfileService`

## pseudocode

```c

```

## disassembly

```asm
0x392f0  call     bool System.Web.ApplicationServices.ApplicationServiceHelper::get_ProfileServiceEnabled()
0x392f5  brtrue.s loc_3931A
0x392f7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x392fc  call     string System.Web.Resources.AtlasWeb::get_AppService_Disabled()
0x39301  ldc.i4.1
0x39302  newarr   [mscorlib]System.Object
0x39307  dup
0x39308  ldc.i4.0
0x39309  ldstr    aProfileservice_2// "ProfileService"
0x3930e  stelem.ref
0x3930f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x39314  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x39319  throw
0x3931a  ret
```
