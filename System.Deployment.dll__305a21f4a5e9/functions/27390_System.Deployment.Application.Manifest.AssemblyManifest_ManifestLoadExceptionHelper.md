# System.Deployment.Application.Manifest.AssemblyManifest::ManifestLoadExceptionHelper

- ea: `0x27390`
- end: `0x273c0`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::ManifestLoadExceptionHelper`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x25670`
- `0x25870`

## callees

- `0x147b0`
- `0x23020`

## string_xrefs

- `0x2739c`: `Ex_ManifestLoadFromFile`

## pseudocode

```c

```

## disassembly

```asm
0x27390  ldarg.1
0x27391  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x27396  stloc.0
0x27397  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x2739c  ldstr    aExManifestload// "Ex_ManifestLoadFromFile"
0x273a1  call     string System.Deployment.Application.Resources::GetString(string s)
0x273a6  ldc.i4.1
0x273a7  newarr   [mscorlib]System.Object
0x273ac  dup
0x273ad  ldc.i4.0
0x273ae  ldloc.0
0x273af  stelem.ref
0x273b0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x273b5  stloc.1
0x273b6  ldc.i4.s 0xE
0x273b8  ldloc.1
0x273b9  ldarg.0
0x273ba  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x273bf  throw
```
