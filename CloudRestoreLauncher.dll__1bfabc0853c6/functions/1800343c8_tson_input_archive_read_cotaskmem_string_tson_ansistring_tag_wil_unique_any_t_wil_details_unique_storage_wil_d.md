# tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x1800343c8`
- end: `0x180034460`
- name: `??$read_cotaskmem_string@Uansistring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18002f00c`
- `0x180033b6c`

## callees

- `0x18001da4c`
- `0x1800343c8`
- `0x1800346b4`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x180034411`
- `OLE32!CoTaskMemAlloc` at `0x180034411`

## pseudocode

```c
void __fastcall tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        void **a2)
{
  tson::input_archive::read_string_two_phase<tson::ansistring_tag>(this);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    a2,
    0);
}

```

## disassembly

```asm
0x1800343c8  mov     rax, rsp
0x1800343cb  mov     [rax+8], rbx
0x1800343cf  push    rdi
0x1800343d0  sub     rsp, 40h
0x1800343d4  mov     qword ptr [rax-28h], 0
0x1800343dc  lea     r8, [rsp+48h+var_28]
0x1800343e1  mov     qword ptr [rax-20h], 0
0x1800343e9  mov     rdi, rdx
0x1800343ec  mov     byte ptr [rax-18h], 0
0x1800343f0  mov     rbx, rcx
0x1800343f3  xor     eax, eax
0x1800343f5  mov     [rsp+48h+var_17], eax
0x1800343f9  mov     [rsp+48h+var_13], ax
0x1800343fe  mov     [rsp+48h+var_11], al
0x180034402  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x180034407  mov     rcx, [rsp+48h+cb]; cb
0x18003440c  test    rcx, rcx
0x18003440f  jz      short loc_18003444B
0x180034411  call    cs:__imp_CoTaskMemAlloc
0x180034417  mov     rdx, rax
0x18003441a  mov     rcx, rdi
0x18003441d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180034422  mov     rax, [rdi]
0x180034425  test    rax, rax
0x180034428  jz      short loc_18003443E
0x18003442a  lea     r8, [rsp+48h+var_28]
0x18003442f  mov     [rsp+48h+var_28], rax
0x180034434  mov     rcx, rbx; this
0x180034437  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x18003443c  jmp     short loc_180034455
0x18003443e  cmp     dword ptr [rbx+8], 0
0x180034442  jl      short loc_18003444B
0x180034444  mov     dword ptr [rbx+8], 8007000Eh
0x18003444b  xor     edx, edx
0x18003444d  mov     rcx, rdi
0x180034450  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180034455  mov     rbx, [rsp+48h+arg_0]
0x18003445a  add     rsp, 40h
0x18003445e  pop     rdi
0x18003445f  retn
```
