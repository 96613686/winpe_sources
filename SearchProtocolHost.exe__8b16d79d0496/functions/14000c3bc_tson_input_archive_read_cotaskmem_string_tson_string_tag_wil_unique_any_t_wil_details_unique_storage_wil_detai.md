# tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &)

- ea: `0x14000c3bc`
- end: `0x14000c457`
- name: `??$read_cotaskmem_string@Ustring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400365a0`

## callees

- `0x14000c3bc`
- `0x14000c6ac`
- `0x140037ce0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000c408`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000c408`

## pseudocode

```c
void __fastcall tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        void **a2)
{
  tson::input_archive::read_string_two_phase<tson::string_tag>(this);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    a2,
    0);
}

```

## disassembly

```asm
0x14000c3bc  mov     rax, rsp
0x14000c3bf  mov     [rax+8], rbx
0x14000c3c3  push    rdi
0x14000c3c4  sub     rsp, 40h
0x14000c3c8  mov     qword ptr [rax-28h], 0
0x14000c3d0  lea     r8, [rsp+48h+var_28]
0x14000c3d5  mov     qword ptr [rax-20h], 0
0x14000c3dd  mov     rdi, rdx
0x14000c3e0  mov     byte ptr [rax-18h], 0
0x14000c3e4  mov     rbx, rcx
0x14000c3e7  xor     eax, eax
0x14000c3e9  mov     [rsp+48h+var_17], eax
0x14000c3ed  mov     [rsp+48h+var_13], ax
0x14000c3f2  mov     [rsp+48h+var_11], al
0x14000c3f6  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x14000c3fb  mov     rcx, [rsp+48h+var_20]
0x14000c400  test    rcx, rcx
0x14000c403  jz      short loc_14000C442
0x14000c405  add     rcx, rcx; cb
0x14000c408  call    cs:__imp_CoTaskMemAlloc
0x14000c40e  mov     rdx, rax
0x14000c411  mov     rcx, rdi
0x14000c414  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x14000c419  mov     rax, [rdi]
0x14000c41c  test    rax, rax
0x14000c41f  jz      short loc_14000C435
0x14000c421  lea     r8, [rsp+48h+var_28]
0x14000c426  mov     [rsp+48h+var_28], rax
0x14000c42b  mov     rcx, rbx; this
0x14000c42e  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x14000c433  jmp     short loc_14000C44C
0x14000c435  cmp     dword ptr [rbx+8], 0
0x14000c439  jl      short loc_14000C442
0x14000c43b  mov     dword ptr [rbx+8], 8007000Eh
0x14000c442  xor     edx, edx
0x14000c444  mov     rcx, rdi
0x14000c447  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x14000c44c  mov     rbx, [rsp+48h+arg_0]
0x14000c451  add     rsp, 40h
0x14000c455  pop     rdi
0x14000c456  retn
```
