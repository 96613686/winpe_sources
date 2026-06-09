# System.Deployment.Application.UserInterface::get_DefaultBrowserExePath

- ea: `0x21fc0`
- end: `0x2203d`
- name: `System.Deployment.Application.UserInterface::get_DefaultBrowserExePath`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x21fa0`

## callees

- `0x21fc0`

## string_xrefs

- `0x21fc7`: `http\shell\open\command`

## pseudocode

```c

```

## disassembly

```asm
0x21fc0  ldnull
0x21fc1  stloc.0
0x21fc2  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::ClassesRoot
0x21fc7  ldstr    aHttpShellOpenC// "http\\shell\\open\\command"
0x21fcc  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x21fd1  stloc.1
0x21fd2  ldloc.1
0x21fd3  brfalse.s loc_2203B
0x21fd5  ldloc.1
0x21fd6  ldsfld   string [mscorlib]System.String::Empty
0x21fdb  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x21fe0  castclass [mscorlib]System.String
0x21fe5  stloc.2
0x21fe6  ldloc.2
0x21fe7  brfalse.s loc_2203B
0x21fe9  ldloc.2
0x21fea  callvirt instance string [mscorlib]System.String::Trim()
0x21fef  stloc.2
0x21ff0  ldloc.2
0x21ff1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x21ff6  brfalse.s loc_2203B
0x21ff8  ldloc.2
0x21ff9  ldc.i4.0
0x21ffa  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x21fff  ldc.i4.s 0x22
0x22001  bne.un.s loc_2201E
0x22003  ldloc.2
0x22004  ldc.i4.s 0x22
0x22006  ldc.i4.1
0x22007  callvirt instance int32 [mscorlib]System.String::IndexOf(char, int32)
0x2200c  stloc.3
0x2200d  ldloc.3
0x2200e  ldc.i4.m1
0x2200f  beq.s    loc_2203B
0x22011  ldloc.2
0x22012  ldc.i4.1
0x22013  ldloc.3
0x22014  ldc.i4.1
0x22015  sub
0x22016  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x2201b  stloc.0
0x2201c  br.s     loc_2203B
0x2201e  ldloc.2
0x2201f  ldc.i4.s 0x20
0x22021  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x22026  stloc.s  4
0x22028  ldloc.s  4
0x2202a  ldc.i4.m1
0x2202b  beq.s    loc_22039
0x2202d  ldloc.2
0x2202e  ldc.i4.0
0x2202f  ldloc.s  4
0x22031  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x22036  stloc.0
0x22037  br.s     loc_2203B
0x22039  ldloc.2
0x2203a  stloc.0
0x2203b  ldloc.0
0x2203c  ret
```
