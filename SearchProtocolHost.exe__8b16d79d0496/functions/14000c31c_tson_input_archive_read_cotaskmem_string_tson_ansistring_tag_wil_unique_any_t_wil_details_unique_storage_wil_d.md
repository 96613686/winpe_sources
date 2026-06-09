# tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x14000c31c`
- end: `0x14000c3b4`
- name: `??$read_cotaskmem_string@Uansistring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140007a18`
- `0x14000b7ac`

## callees

- `0x14000c31c`
- `0x14000c608`
- `0x140037ce0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000c365`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000c365`

## pseudocode

```c
void __fastcall tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        void **a2)
{
  tson::input_archive::read_string_two_phase<tson::ansistring_tag>(this);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    a2,
    0);
}

```

## disassembly

```asm
0x14000c31c  mov     rax, rsp
0x14000c31f  mov     [rax+8], rbx
0x14000c323  push    rdi
0x14000c324  sub     rsp, 40h
0x14000c328  mov     qword ptr [rax-28h], 0
0x14000c330  lea     r8, [rsp+48h+var_28]
0x14000c335  mov     qword ptr [rax-20h], 0
0x14000c33d  mov     rdi, rdx
0x14000c340  mov     byte ptr [rax-18h], 0
0x14000c344  mov     rbx, rcx
0x14000c347  xor     eax, eax
0x14000c349  mov     [rsp+48h+var_17], eax
0x14000c34d  mov     [rsp+48h+var_13], ax
0x14000c352  mov     [rsp+48h+var_11], al
0x14000c356  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x14000c35b  mov     rcx, [rsp+48h+cb]; cb
0x14000c360  test    rcx, rcx
0x14000c363  jz      short loc_14000C39F
0x14000c365  call    cs:__imp_CoTaskMemAlloc
0x14000c36b  mov     rdx, rax
0x14000c36e  mov     rcx, rdi
0x14000c371  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x14000c376  mov     rax, [rdi]
0x14000c379  test    rax, rax
0x14000c37c  jz      short loc_14000C392
0x14000c37e  lea     r8, [rsp+48h+var_28]
0x14000c383  mov     [rsp+48h+var_28], rax
0x14000c388  mov     rcx, rbx; this
0x14000c38b  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x14000c390  jmp     short loc_14000C3A9
0x14000c392  cmp     dword ptr [rbx+8], 0
0x14000c396  jl      short loc_14000C39F
0x14000c398  mov     dword ptr [rbx+8], 8007000Eh
0x14000c39f  xor     edx, edx
0x14000c3a1  mov     rcx, rdi
0x14000c3a4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x14000c3a9  mov     rbx, [rsp+48h+arg_0]
0x14000c3ae  add     rsp, 40h
0x14000c3b2  pop     rdi
0x14000c3b3  retn
```
