# tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &)

- ea: `0x180016f00`
- end: `0x180016f9b`
- name: `??$read_cotaskmem_string@Ustring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180024144`

## callees

- `0x180016f00`
- `0x1800171f0`
- `0x180025158`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016f4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016f4c`

## pseudocode

```c
__int64 __fastcall tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        __int64 a2)
{
  tson::input_archive::read_string_two_phase<tson::string_tag>(this);
  return wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
           a2,
           0);
}

```

## disassembly

```asm
0x180016f00  mov     rax, rsp
0x180016f03  mov     [rax+8], rbx
0x180016f07  push    rdi
0x180016f08  sub     rsp, 40h
0x180016f0c  mov     qword ptr [rax-28h], 0
0x180016f14  lea     r8, [rsp+48h+var_28]
0x180016f19  mov     qword ptr [rax-20h], 0
0x180016f21  mov     rdi, rdx
0x180016f24  mov     byte ptr [rax-18h], 0
0x180016f28  mov     rbx, rcx
0x180016f2b  xor     eax, eax
0x180016f2d  mov     [rsp+48h+var_17], eax
0x180016f31  mov     [rsp+48h+var_13], ax
0x180016f36  mov     [rsp+48h+var_11], al
0x180016f3a  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x180016f3f  mov     rcx, [rsp+48h+var_20]
0x180016f44  test    rcx, rcx
0x180016f47  jz      short loc_180016F86
0x180016f49  add     rcx, rcx; cb
0x180016f4c  call    cs:__imp_CoTaskMemAlloc
0x180016f52  mov     rdx, rax
0x180016f55  mov     rcx, rdi
0x180016f58  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x180016f5d  mov     rax, [rdi]
0x180016f60  test    rax, rax
0x180016f63  jz      short loc_180016F79
0x180016f65  lea     r8, [rsp+48h+var_28]
0x180016f6a  mov     [rsp+48h+var_28], rax
0x180016f6f  mov     rcx, rbx; this
0x180016f72  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x180016f77  jmp     short loc_180016F90
0x180016f79  cmp     dword ptr [rbx+8], 0
0x180016f7d  jl      short loc_180016F86
0x180016f7f  mov     dword ptr [rbx+8], 8007000Eh
0x180016f86  xor     edx, edx
0x180016f88  mov     rcx, rdi
0x180016f8b  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x180016f90  mov     rbx, [rsp+48h+arg_0]
0x180016f95  add     rsp, 40h
0x180016f99  pop     rdi
0x180016f9a  retn
```
