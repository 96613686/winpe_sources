# System.Web.Script.Services.ClientProxyGenerator::GeneratePrototype

- ea: `0x2fdb0`
- end: `0x2fe51`
- name: `System.Web.Script.Services.ClientProxyGenerator::GeneratePrototype`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x2fcc0`

## callees

- `0x2e820`
- `0x2fdb0`
- `0x2fe60`
- `0x30820`
- `0x30ca0`

## string_xrefs

- `0x2fdcf`: `_get_path:function() {\n var p = this.get_path();\n if (p) return p;\n else return `
- `0x2fdec`: `._staticInstance.get_path();},\n`

## pseudocode

```c

```

## disassembly

```asm
0x2fdb0  ldarg.0
0x2fdb1  ldarg.1
0x2fdb2  ldc.i4.1
0x2fdb3  callvirt instance void System.Web.Script.Services.ClientProxyGenerator::GenerateTypeDeclaration(class System.Web.Script.Services.WebServiceData webServiceData, bool genClass)
0x2fdb8  ldarg.0
0x2fdb9  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x2fdbe  ldstr    asc_4AD80// "{\r\n"
0x2fdc3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2fdc8  pop
0x2fdc9  ldarg.0
0x2fdca  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x2fdcf  ldstr    aGetPathFunctio// "_get_path:function() {\r\n var p = this"...
0x2fdd4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2fdd9  pop
0x2fdda  ldarg.0
0x2fddb  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x2fde0  ldarg.0
0x2fde1  ldarg.1
0x2fde2  callvirt instance string System.Web.Script.Services.ClientProxyGenerator::GetProxyTypeName(class System.Web.Script.Services.WebServiceData data)
0x2fde7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2fdec  ldstr    aStaticinstance// "._staticInstance.get_path();},\r\n"
0x2fdf1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2fdf6  pop
0x2fdf7  ldc.i4.1
0x2fdf8  stloc.0
0x2fdf9  ldarg.1
0x2fdfa  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class System.Web.Script.Services.WebServiceMethodData> System.Web.Script.Services.WebServiceData::get_MethodDatas()
0x2fdff  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Web.Script.Services.WebServiceMethodData>::GetEnumerator()
0x2fe04  stloc.1
0x2fe05  br.s     loc_2FE2B
0x2fe07  ldloc.1
0x2fe08  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Web.Script.Services.WebServiceMethodData>::get_Current()
0x2fe0d  stloc.2
0x2fe0e  ldloc.0
0x2fe0f  brtrue.s loc_2FE22
0x2fe11  ldarg.0
0x2fe12  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x2fe17  ldstr    asc_4AE72// ",\r\n"
0x2fe1c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2fe21  pop
0x2fe22  ldc.i4.0
0x2fe23  stloc.0
0x2fe24  ldarg.0
0x2fe25  ldloc.2
0x2fe26  call     instance void System.Web.Script.Services.ClientProxyGenerator::GenerateWebMethodProxy(class System.Web.Script.Services.WebServiceMethodData methodData)
0x2fe2b  ldloc.1
0x2fe2c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2fe31  brtrue.s loc_2FE07
0x2fe33  leave.s  loc_2FE3F
0x2fe35  ldloc.1
0x2fe36  brfalse.s loc_2FE3E
0x2fe38  ldloc.1
0x2fe39  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2fe3e  endfinally
0x2fe3f  ldarg.0
0x2fe40  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x2fe45  ldstr    asc_4AD78// "}\r\n"
0x2fe4a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2fe4f  pop
0x2fe50  ret
```
