# tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18001135c`
- end: `0x1800113f7`
- name: `??$read_cotaskmem_string@Ustring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019cd8`

## callees

- `0x18001135c`
- `0x18001164c`
- `0x18001a980`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800113a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800113a8`

## pseudocode

```c
__int64 __fastcall tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        __int64 a2)
{
  tson::input_archive::read_string_two_phase<tson::string_tag>(this);
  return wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
           a2,
           0);
}

```

## disassembly

```asm
0x18001135c  mov     rax, rsp
0x18001135f  mov     [rax+8], rbx
0x180011363  push    rdi
0x180011364  sub     rsp, 40h
0x180011368  mov     qword ptr [rax-28h], 0
0x180011370  lea     r8, [rsp+48h+var_28]
0x180011375  mov     qword ptr [rax-20h], 0
0x18001137d  mov     rdi, rdx
0x180011380  mov     byte ptr [rax-18h], 0
0x180011384  mov     rbx, rcx
0x180011387  xor     eax, eax
0x180011389  mov     [rsp+48h+var_17], eax
0x18001138d  mov     [rsp+48h+var_13], ax
0x180011392  mov     [rsp+48h+var_11], al
0x180011396  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x18001139b  mov     rcx, [rsp+48h+var_20]
0x1800113a0  test    rcx, rcx
0x1800113a3  jz      short loc_1800113E2
0x1800113a5  add     rcx, rcx; cb
0x1800113a8  call    cs:__imp_CoTaskMemAlloc
0x1800113ae  mov     rdx, rax
0x1800113b1  mov     rcx, rdi
0x1800113b4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800113b9  mov     rax, [rdi]
0x1800113bc  test    rax, rax
0x1800113bf  jz      short loc_1800113D5
0x1800113c1  lea     r8, [rsp+48h+var_28]
0x1800113c6  mov     [rsp+48h+var_28], rax
0x1800113cb  mov     rcx, rbx; this
0x1800113ce  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x1800113d3  jmp     short loc_1800113EC
0x1800113d5  cmp     dword ptr [rbx+8], 0
0x1800113d9  jl      short loc_1800113E2
0x1800113db  mov     dword ptr [rbx+8], 8007000Eh
0x1800113e2  xor     edx, edx
0x1800113e4  mov     rcx, rdi
0x1800113e7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800113ec  mov     rbx, [rsp+48h+arg_0]
0x1800113f1  add     rsp, 40h
0x1800113f5  pop     rdi
0x1800113f6  retn
```
