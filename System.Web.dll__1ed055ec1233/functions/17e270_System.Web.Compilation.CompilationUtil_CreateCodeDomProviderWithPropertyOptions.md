# System.Web.Compilation.CompilationUtil::CreateCodeDomProviderWithPropertyOptions

- ea: `0x17e270`
- end: `0x17e36d`
- name: `System.Web.Compilation.CompilationUtil::CreateCodeDomProviderWithPropertyOptions`
- size: `253`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x17e230`
- `0x17e250`

## callees

- `0x17e0a0`
- `0x17e270`
- `0x17e370`
- `0x17e3d0`
- `0x17e470`
- `0x17ff90`
- `0x17ffa0`

## string_xrefs

- `0x17e35d`: `CompilerDirectoryPath`
- `0x17e29b`: `CompilerVersion`
- `0x17e2b4`: `CompilerVersion`
- `0x17e2ed`: `CompilerVersion`

## pseudocode

```c

```

## disassembly

```asm
0x17e270  ldarg.0
0x17e271  call     class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> System.Web.Compilation.CompilationUtil::GetProviderOptions(class [mscorlib]System.Type codeDomProviderType)
0x17e276  stloc.0
0x17e277  ldnull
0x17e278  stloc.1
0x17e279  ldloc.0
0x17e27a  brfalse.s loc_17E285
0x17e27c  ldloc.0
0x17e27d  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<var<u1>, !!T0>)
0x17e282  stloc.1
0x17e283  br.s     loc_17E28B
0x17e285  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x17e28a  stloc.1
0x17e28b  ldloc.1
0x17e28c  call     void System.Web.Compilation.CompilationUtil::CheckCompilerDirectoryPathAllowed(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> providerOptions)
0x17e291  ldc.i4.0
0x17e292  stloc.2
0x17e293  call     bool System.Web.Compilation.MultiTargetingUtil::get_IsTargetFramework20()
0x17e298  brfalse.s loc_17E2AC
0x17e29a  ldloc.1
0x17e29b  ldstr    aCompilerversio// "CompilerVersion"
0x17e2a0  ldstr    aV20// "v2.0"
0x17e2a5  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x17e2aa  br.s     loc_17E2FC
0x17e2ac  call     bool System.Web.Compilation.MultiTargetingUtil::get_IsTargetFramework35()
0x17e2b1  brfalse.s loc_17E2C5
0x17e2b3  ldloc.1
0x17e2b4  ldstr    aCompilerversio// "CompilerVersion"
0x17e2b9  ldstr    aV35// "v3.5"
0x17e2be  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x17e2c3  br.s     loc_17E2FC
0x17e2c5  ldarg.0
0x17e2c6  call     string System.Web.Compilation.CompilationUtil::GetCompilerVersion(class [mscorlib]System.Type codeDomProviderType)
0x17e2cb  stloc.3
0x17e2cc  ldloc.3
0x17e2cd  call     class [mscorlib]System.Version System.Web.Compilation.CompilationUtil::GetVersionFromVString(string version)
0x17e2d2  stloc.s  4
0x17e2d4  ldloc.s  4
0x17e2d6  ldnull
0x17e2d7  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x17e2dc  brfalse.s loc_17E2FC
0x17e2de  ldloc.s  4
0x17e2e0  ldsfld   class [mscorlib]System.Version System.Web.Compilation.MultiTargetingUtil::Version40
0x17e2e5  call     bool [mscorlib]System.Version::op_LessThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x17e2ea  brfalse.s loc_17E2FC
0x17e2ec  ldloc.1
0x17e2ed  ldstr    aCompilerversio// "CompilerVersion"
0x17e2f2  ldstr    aV40// "v4.0"
0x17e2f7  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x17e2fc  ldloc.1
0x17e2fd  brfalse.s loc_17E36B
0x17e2ff  ldloc.1
0x17e300  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Count()
0x17e305  ldc.i4.0
0x17e306  ble.s    loc_17E36B
0x17e308  ldarg.0
0x17e309  ldc.i4.1
0x17e30a  newarr   [mscorlib]System.Type
0x17e30f  dup
0x17e310  ldc.i4.0
0x17e311  ldtoken  class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>
0x17e316  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e31b  stelem.ref
0x17e31c  callvirt instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(class [mscorlib]System.Type[])
0x17e321  stloc.s  5
0x17e323  ldnull
0x17e324  stloc.s  6
0x17e326  ldloc.s  5
0x17e328  ldnull
0x17e329  call     bool [mscorlib]System.Reflection.ConstructorInfo::op_Inequality(class [mscorlib]System.Reflection.ConstructorInfo, class [mscorlib]System.Reflection.ConstructorInfo)
0x17e32e  brfalse.s loc_17E359
0x17e330  ldarg.0
0x17e331  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x17e336  castclass [System]System.CodeDom.Compiler.CodeDomProvider
0x17e33b  stloc.s  7
0x17e33d  ldloc.s  7
0x17e33f  callvirt instance string [System]System.CodeDom.Compiler.CodeDomProvider::get_FileExtension()
0x17e344  stloc.s  8
0x17e346  ldloc.s  8
0x17e348  call     string [System]System.CodeDom.Compiler.CodeDomProvider::GetLanguageFromExtension(string)
0x17e34d  stloc.s  9
0x17e34f  ldloc.s  9
0x17e351  ldloc.1
0x17e352  call     class [System]System.CodeDom.Compiler.CodeDomProvider [System]System.CodeDom.Compiler.CodeDomProvider::CreateProvider(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>)
0x17e357  stloc.s  6
0x17e359  ldloc.2
0x17e35a  brfalse.s loc_17E368
0x17e35c  ldloc.1
0x17e35d  ldstr    aCompilerdirect// "CompilerDirectoryPath"
0x17e362  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Remove(var<u1>)
0x17e367  pop
0x17e368  ldloc.s  6
0x17e36a  ret
0x17e36b  ldnull
0x17e36c  ret
```
