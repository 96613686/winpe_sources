# MemberMarkupInfo::MemberRequiresNamespaceHoisting

- ea: `0x29400`
- end: `0x2942b`
- name: `MemberMarkupInfo::MemberRequiresNamespaceHoisting`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x293a0`

## callees

- `0xa500`
- `0xa6c0`
- `0xa6e0`
- `0xf950`
- `0x29400`

## string_xrefs

- `0x2941e`: `http://www.w3.org/XML/1998/namespace`

## pseudocode

```c

```

## disassembly

```asm
0x29400  ldarg.1
0x29401  callvirt instance bool System.Xaml.XamlMember::get_IsAttachable()
0x29406  brtrue.s loc_29418
0x29408  ldarg.1
0x29409  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x2940e  brfalse.s loc_29429
0x29410  ldarg.1
0x29411  call     bool System.Xaml.XamlXmlWriter::IsImplicit(class System.Xaml.XamlMember xamlMember)
0x29416  brtrue.s loc_29429
0x29418  ldarg.1
0x29419  callvirt instance string System.Xaml.XamlMember::get_PreferredXamlNamespace()
0x2941e  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x29423  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x29428  ret
0x29429  ldc.i4.0
0x2942a  ret
```
