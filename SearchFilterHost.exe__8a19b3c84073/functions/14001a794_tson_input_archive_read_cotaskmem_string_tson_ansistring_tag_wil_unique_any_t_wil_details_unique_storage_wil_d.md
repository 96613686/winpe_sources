# tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x14001a794`
- end: `0x14001a82c`
- name: `??$read_cotaskmem_string@Uansistring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140019c98`
- `0x14001a2e8`

## callees

- `0x14001a794`
- `0x14001aa80`
- `0x140026df0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001a7dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001a7dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x14001a794  mov     rax, rsp
0x14001a797  mov     [rax+8], rbx
0x14001a79b  push    rdi
0x14001a79c  sub     rsp, 40h
0x14001a7a0  mov     qword ptr [rax-28h], 0
0x14001a7a8  lea     r8, [rsp+48h+var_28]
0x14001a7ad  mov     qword ptr [rax-20h], 0
0x14001a7b5  mov     rdi, rdx
0x14001a7b8  mov     byte ptr [rax-18h], 0
0x14001a7bc  mov     rbx, rcx
0x14001a7bf  xor     eax, eax
0x14001a7c1  mov     [rsp+48h+var_17], eax
0x14001a7c5  mov     [rsp+48h+var_13], ax
0x14001a7ca  mov     [rsp+48h+var_11], al
0x14001a7ce  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x14001a7d3  mov     rcx, [rsp+48h+cb]; cb
0x14001a7d8  test    rcx, rcx
0x14001a7db  jz      short loc_14001A817
0x14001a7dd  call    cs:__imp_CoTaskMemAlloc
0x14001a7e3  mov     rdx, rax
0x14001a7e6  mov     rcx, rdi
0x14001a7e9  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x14001a7ee  mov     rax, [rdi]
0x14001a7f1  test    rax, rax
0x14001a7f4  jz      short loc_14001A80A
0x14001a7f6  lea     r8, [rsp+48h+var_28]
0x14001a7fb  mov     [rsp+48h+var_28], rax
0x14001a800  mov     rcx, rbx; this
0x14001a803  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x14001a808  jmp     short loc_14001A821
0x14001a80a  cmp     dword ptr [rbx+8], 0
0x14001a80e  jl      short loc_14001A817
0x14001a810  mov     dword ptr [rbx+8], 8007000Eh
0x14001a817  xor     edx, edx
0x14001a819  mov     rcx, rdi
0x14001a81c  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x14001a821  mov     rbx, [rsp+48h+arg_0]
0x14001a826  add     rsp, 40h
0x14001a82a  pop     rdi
0x14001a82b  retn
```
