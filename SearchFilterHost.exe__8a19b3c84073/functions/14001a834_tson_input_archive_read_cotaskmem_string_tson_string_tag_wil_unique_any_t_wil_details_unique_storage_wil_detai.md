# tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &)

- ea: `0x14001a834`
- end: `0x14001a8cf`
- name: `??$read_cotaskmem_string@Ustring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14002632c`

## callees

- `0x14001a834`
- `0x14001ab24`
- `0x140026df0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001a880`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001a880`

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
0x14001a834  mov     rax, rsp
0x14001a837  mov     [rax+8], rbx
0x14001a83b  push    rdi
0x14001a83c  sub     rsp, 40h
0x14001a840  mov     qword ptr [rax-28h], 0
0x14001a848  lea     r8, [rsp+48h+var_28]
0x14001a84d  mov     qword ptr [rax-20h], 0
0x14001a855  mov     rdi, rdx
0x14001a858  mov     byte ptr [rax-18h], 0
0x14001a85c  mov     rbx, rcx
0x14001a85f  xor     eax, eax
0x14001a861  mov     [rsp+48h+var_17], eax
0x14001a865  mov     [rsp+48h+var_13], ax
0x14001a86a  mov     [rsp+48h+var_11], al
0x14001a86e  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x14001a873  mov     rcx, [rsp+48h+var_20]
0x14001a878  test    rcx, rcx
0x14001a87b  jz      short loc_14001A8BA
0x14001a87d  add     rcx, rcx; cb
0x14001a880  call    cs:__imp_CoTaskMemAlloc
0x14001a886  mov     rdx, rax
0x14001a889  mov     rcx, rdi
0x14001a88c  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x14001a891  mov     rax, [rdi]
0x14001a894  test    rax, rax
0x14001a897  jz      short loc_14001A8AD
0x14001a899  lea     r8, [rsp+48h+var_28]
0x14001a89e  mov     [rsp+48h+var_28], rax
0x14001a8a3  mov     rcx, rbx; this
0x14001a8a6  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x14001a8ab  jmp     short loc_14001A8C4
0x14001a8ad  cmp     dword ptr [rbx+8], 0
0x14001a8b1  jl      short loc_14001A8BA
0x14001a8b3  mov     dword ptr [rbx+8], 8007000Eh
0x14001a8ba  xor     edx, edx
0x14001a8bc  mov     rcx, rdi
0x14001a8bf  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x14001a8c4  mov     rbx, [rsp+48h+arg_0]
0x14001a8c9  add     rsp, 40h
0x14001a8cd  pop     rdi
0x14001a8ce  retn
```
