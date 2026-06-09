# tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x180023e44`
- end: `0x180023edc`
- name: `??$read_cotaskmem_string@Uansistring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027ee8`
- `0x180035110`

## callees

- `0x180023e44`
- `0x180023ee4`
- `0x180035954`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023e8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023e8d`

## pseudocode

```c
__int64 __fastcall tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        __int64 a2)
{
  tson::input_archive::read_string_two_phase<tson::ansistring_tag>(this);
  return wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
           a2,
           0);
}

```

## disassembly

```asm
0x180023e44  mov     rax, rsp
0x180023e47  mov     [rax+8], rbx
0x180023e4b  push    rdi
0x180023e4c  sub     rsp, 40h
0x180023e50  mov     qword ptr [rax-28h], 0
0x180023e58  lea     r8, [rsp+48h+var_28]
0x180023e5d  mov     qword ptr [rax-20h], 0
0x180023e65  mov     rdi, rdx
0x180023e68  mov     byte ptr [rax-18h], 0
0x180023e6c  mov     rbx, rcx
0x180023e6f  xor     eax, eax
0x180023e71  mov     [rsp+48h+var_17], eax
0x180023e75  mov     [rsp+48h+var_13], ax
0x180023e7a  mov     [rsp+48h+var_11], al
0x180023e7e  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x180023e83  mov     rcx, [rsp+48h+cb]; cb
0x180023e88  test    rcx, rcx
0x180023e8b  jz      short loc_180023EC7
0x180023e8d  call    cs:__imp_CoTaskMemAlloc
0x180023e93  mov     rdx, rax
0x180023e96  mov     rcx, rdi
0x180023e99  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x180023e9e  mov     rax, [rdi]
0x180023ea1  test    rax, rax
0x180023ea4  jz      short loc_180023EBA
0x180023ea6  lea     r8, [rsp+48h+var_28]
0x180023eab  mov     [rsp+48h+var_28], rax
0x180023eb0  mov     rcx, rbx; this
0x180023eb3  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x180023eb8  jmp     short loc_180023ED1
0x180023eba  cmp     dword ptr [rbx+8], 0
0x180023ebe  jl      short loc_180023EC7
0x180023ec0  mov     dword ptr [rbx+8], 8007000Eh
0x180023ec7  xor     edx, edx
0x180023ec9  mov     rcx, rdi
0x180023ecc  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x180023ed1  mov     rbx, [rsp+48h+arg_0]
0x180023ed6  add     rsp, 40h
0x180023eda  pop     rdi
0x180023edb  retn
```
