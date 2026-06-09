# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)

- ea: `0x140003970`
- end: `0x140003987`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(OLECHAR **)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000e1eb`
- `0x14000e217`
- `0x14000e9e9`
- `0x14000ea1e`
- `0x14000ea53`

## callees

- `0x140003970`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000397c`
- `OLEAUT32!__imp_SysFreeString` at `0x14000397c`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(
        OLECHAR **a1)
{
  OLECHAR *v1; // rcx

  v1 = *a1;
  if ( v1 )
    SysFreeString(v1);
}

```

## disassembly

```asm
0x140003970  sub     rsp, 28h
0x140003974  mov     rcx, [rcx]; bstrString
0x140003977  test    rcx, rcx
0x14000397a  jz      short loc_140003982
0x14000397c  call    cs:__imp_SysFreeString
0x140003982  add     rsp, 28h
0x140003986  retn
```
