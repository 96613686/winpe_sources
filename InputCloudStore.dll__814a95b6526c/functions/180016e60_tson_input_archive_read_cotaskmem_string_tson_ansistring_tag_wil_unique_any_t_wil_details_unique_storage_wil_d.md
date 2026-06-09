# tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x180016e60`
- end: `0x180016ef8`
- name: `??$read_cotaskmem_string@Uansistring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009ad8`
- `0x180015e84`

## callees

- `0x180016e60`
- `0x18001714c`
- `0x180025158`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016ea9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016ea9`

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
0x180016e60  mov     rax, rsp
0x180016e63  mov     [rax+8], rbx
0x180016e67  push    rdi
0x180016e68  sub     rsp, 40h
0x180016e6c  mov     qword ptr [rax-28h], 0
0x180016e74  lea     r8, [rsp+48h+var_28]
0x180016e79  mov     qword ptr [rax-20h], 0
0x180016e81  mov     rdi, rdx
0x180016e84  mov     byte ptr [rax-18h], 0
0x180016e88  mov     rbx, rcx
0x180016e8b  xor     eax, eax
0x180016e8d  mov     [rsp+48h+var_17], eax
0x180016e91  mov     [rsp+48h+var_13], ax
0x180016e96  mov     [rsp+48h+var_11], al
0x180016e9a  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x180016e9f  mov     rcx, [rsp+48h+cb]; cb
0x180016ea4  test    rcx, rcx
0x180016ea7  jz      short loc_180016EE3
0x180016ea9  call    cs:__imp_CoTaskMemAlloc
0x180016eaf  mov     rdx, rax
0x180016eb2  mov     rcx, rdi
0x180016eb5  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x180016eba  mov     rax, [rdi]
0x180016ebd  test    rax, rax
0x180016ec0  jz      short loc_180016ED6
0x180016ec2  lea     r8, [rsp+48h+var_28]
0x180016ec7  mov     [rsp+48h+var_28], rax
0x180016ecc  mov     rcx, rbx; this
0x180016ecf  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x180016ed4  jmp     short loc_180016EED
0x180016ed6  cmp     dword ptr [rbx+8], 0
0x180016eda  jl      short loc_180016EE3
0x180016edc  mov     dword ptr [rbx+8], 8007000Eh
0x180016ee3  xor     edx, edx
0x180016ee5  mov     rcx, rdi
0x180016ee8  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x180016eed  mov     rbx, [rsp+48h+arg_0]
0x180016ef2  add     rsp, 40h
0x180016ef6  pop     rdi
0x180016ef7  retn
```
