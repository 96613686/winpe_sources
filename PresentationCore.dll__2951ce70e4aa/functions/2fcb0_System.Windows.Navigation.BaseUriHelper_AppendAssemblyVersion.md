# System.Windows.Navigation.BaseUriHelper::AppendAssemblyVersion

- ea: `0x2fcb0`
- end: `0x2fe0e`
- name: `System.Windows.Navigation.BaseUriHelper::AppendAssemblyVersion`
- size: `350`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x2f8c0`
- `0x2f9a0`
- `0x2fcb0`
- `0x2fec0`

## string_xrefs

- `0x2fdca`: `;component`

## pseudocode

```c

```

## disassembly

```asm
0x2fcb0  ldnull
0x2fcb1  stloc.1
0x2fcb2  ldnull
0x2fcb3  stloc.s  5
0x2fcb5  ldarg.1
0x2fcb6  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x2fcbb  newobj   instance void [mscorlib]System.Reflection.AssemblyName::.ctor(string)
0x2fcc0  stloc.s  4
0x2fcc2  ldloc.s  4
0x2fcc4  callvirt instance class [mscorlib]System.Version [mscorlib]System.Reflection.AssemblyName::get_Version()
0x2fcc9  dup
0x2fcca  brtrue.s loc_2FCD0
0x2fccc  pop
0x2fccd  ldnull
0x2fcce  br.s     loc_2FCD5
0x2fcd0  callvirt instance string [mscorlib]System.Object::ToString()
0x2fcd5  stloc.s  8
0x2fcd7  ldarg.0
0x2fcd8  ldnull
0x2fcd9  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x2fcde  brfalse  loc_2FE0C
0x2fce3  ldloc.s  8
0x2fce5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2fcea  brtrue   loc_2FE0C
0x2fcef  ldarg.0
0x2fcf0  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x2fcf5  brfalse.s loc_2FD1D
0x2fcf7  ldarg.0
0x2fcf8  call     bool System.Windows.Navigation.BaseUriHelper::IsPackApplicationUri(class [System]System.Uri uri)
0x2fcfd  brfalse.s loc_2FD1F
0x2fcff  ldarg.0
0x2fd00  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x2fd05  ldc.i4.2
0x2fd06  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x2fd0b  stloc.1
0x2fd0c  ldarg.0
0x2fd0d  ldc.i4.1
0x2fd0e  callvirt instance string [System]System.Uri::GetLeftPart(valuetype [System]System.UriPartial)
0x2fd13  ldc.i4.1
0x2fd14  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x2fd19  stloc.s  5
0x2fd1b  br.s     loc_2FD1F
0x2fd1d  ldarg.0
0x2fd1e  stloc.1
0x2fd1f  ldloc.1
0x2fd20  ldnull
0x2fd21  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x2fd26  brfalse  loc_2FE0C
0x2fd2b  ldloc.1
0x2fd2c  ldloca.s 0xA
0x2fd2e  ldloca.s 3
0x2fd30  ldloca.s 9
0x2fd32  ldloca.s 2
0x2fd34  call     void System.Windows.Navigation.BaseUriHelper::GetAssemblyNameAndPart(class [System]System.Uri uri, [out] string& partName, [out] string& assemblyName, [out] string& assemblyVersion, [out] string& assemblyKey)
0x2fd39  ldloc.2
0x2fd3a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2fd3f  ldc.i4.0
0x2fd40  ceq
0x2fd42  stloc.s  7
0x2fd44  ldloc.3
0x2fd45  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2fd4a  brtrue   loc_2FE0C
0x2fd4f  ldloc.s  9
0x2fd51  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2fd56  brfalse  loc_2FE0C
0x2fd5b  ldloc.3
0x2fd5c  ldloc.s  4
0x2fd5e  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0x2fd63  ldc.i4.4
0x2fd64  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2fd69  brfalse  loc_2FE0C
0x2fd6e  ldloc.s  7
0x2fd70  brfalse.s loc_2FD7F
0x2fd72  ldloc.s  4
0x2fd74  ldloc.2
0x2fd75  call     bool System.Windows.Navigation.BaseUriHelper::AssemblyMatchesKeyString(class [mscorlib]System.Reflection.AssemblyName asmName, string assemblyKey)
0x2fd7a  brfalse  loc_2FE0C
0x2fd7f  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2fd84  stloc.0
0x2fd85  ldloc.0
0x2fd86  ldc.i4.s 0x2F
0x2fd88  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x2fd8d  pop
0x2fd8e  ldloc.0
0x2fd8f  ldloc.3
0x2fd90  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2fd95  pop
0x2fd96  ldloc.0
0x2fd97  ldc.i4.s 0x3B
0x2fd99  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x2fd9e  pop
0x2fd9f  ldloc.0
0x2fda0  ldstr    aV// "v"
0x2fda5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2fdaa  pop
0x2fdab  ldloc.0
0x2fdac  ldloc.s  8
0x2fdae  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2fdb3  pop
0x2fdb4  ldloc.s  7
0x2fdb6  brfalse.s loc_2FDC9
0x2fdb8  ldloc.0
0x2fdb9  ldc.i4.s 0x3B
0x2fdbb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x2fdc0  pop
0x2fdc1  ldloc.0
0x2fdc2  ldloc.2
0x2fdc3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2fdc8  pop
0x2fdc9  ldloc.0
0x2fdca  ldstr    aComponent// ";component"
0x2fdcf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2fdd4  pop
0x2fdd5  ldloc.0
0x2fdd6  ldc.i4.s 0x2F
0x2fdd8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x2fddd  pop
0x2fdde  ldloc.0
0x2fddf  ldloc.s  0xA
0x2fde1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2fde6  pop
0x2fde7  ldloc.0
0x2fde8  callvirt instance string [mscorlib]System.Object::ToString()
0x2fded  stloc.s  6
0x2fdef  ldloc.s  5
0x2fdf1  ldnull
0x2fdf2  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x2fdf7  brfalse.s loc_2FE03
0x2fdf9  ldloc.s  5
0x2fdfb  ldloc.s  6
0x2fdfd  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, string)
0x2fe02  ret
0x2fe03  ldloc.s  6
0x2fe05  ldc.i4.2
0x2fe06  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x2fe0b  ret
0x2fe0c  ldnull
0x2fe0d  ret
```
