# tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x180052dfc`
- end: `0x180052e94`
- name: `??$read_cotaskmem_string@Uansistring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180057de4`
- `0x180072d44`

## callees

- `0x180052dfc`
- `0x180052e9c`
- `0x1800735a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052e45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052e45`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180052dfc  mov     rax, rsp
0x180052dff  mov     [rax+8], rbx
0x180052e03  push    rdi
0x180052e04  sub     rsp, 40h
0x180052e08  mov     qword ptr [rax-28h], 0
0x180052e10  lea     r8, [rsp+48h+var_28]
0x180052e15  mov     qword ptr [rax-20h], 0
0x180052e1d  mov     rdi, rdx
0x180052e20  mov     byte ptr [rax-18h], 0
0x180052e24  mov     rbx, rcx
0x180052e27  xor     eax, eax
0x180052e29  mov     [rsp+48h+var_17], eax
0x180052e2d  mov     [rsp+48h+var_13], ax
0x180052e32  mov     [rsp+48h+var_11], al
0x180052e36  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x180052e3b  mov     rcx, [rsp+48h+cb]; cb
0x180052e40  test    rcx, rcx
0x180052e43  jz      short loc_180052E7F
0x180052e45  call    cs:__imp_CoTaskMemAlloc
0x180052e4b  mov     rdx, rax
0x180052e4e  mov     rcx, rdi
0x180052e51  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x180052e56  mov     rax, [rdi]
0x180052e59  test    rax, rax
0x180052e5c  jz      short loc_180052E72
0x180052e5e  lea     r8, [rsp+48h+var_28]
0x180052e63  mov     [rsp+48h+var_28], rax
0x180052e68  mov     rcx, rbx; this
0x180052e6b  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x180052e70  jmp     short loc_180052E89
0x180052e72  cmp     dword ptr [rbx+8], 0
0x180052e76  jl      short loc_180052E7F
0x180052e78  mov     dword ptr [rbx+8], 8007000Eh
0x180052e7f  xor     edx, edx
0x180052e81  mov     rcx, rdi
0x180052e84  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x180052e89  mov     rbx, [rsp+48h+arg_0]
0x180052e8e  add     rsp, 40h
0x180052e92  pop     rdi
0x180052e93  retn
```
