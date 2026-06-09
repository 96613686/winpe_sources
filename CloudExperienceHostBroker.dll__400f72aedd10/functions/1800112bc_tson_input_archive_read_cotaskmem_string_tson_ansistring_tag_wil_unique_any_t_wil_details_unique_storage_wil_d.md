# tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x1800112bc`
- end: `0x180011354`
- name: `??$read_cotaskmem_string@Uansistring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000fffc`
- `0x180010bec`

## callees

- `0x1800112bc`
- `0x1800115a8`
- `0x18001a980`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011305`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011305`

## pseudocode

```c
__int64 __fastcall tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        __int64 a2)
{
  tson::input_archive::read_string_two_phase<tson::ansistring_tag>(this);
  return wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
           a2,
           0);
}

```

## disassembly

```asm
0x1800112bc  mov     rax, rsp
0x1800112bf  mov     [rax+8], rbx
0x1800112c3  push    rdi
0x1800112c4  sub     rsp, 40h
0x1800112c8  mov     qword ptr [rax-28h], 0
0x1800112d0  lea     r8, [rsp+48h+var_28]
0x1800112d5  mov     qword ptr [rax-20h], 0
0x1800112dd  mov     rdi, rdx
0x1800112e0  mov     byte ptr [rax-18h], 0
0x1800112e4  mov     rbx, rcx
0x1800112e7  xor     eax, eax
0x1800112e9  mov     [rsp+48h+var_17], eax
0x1800112ed  mov     [rsp+48h+var_13], ax
0x1800112f2  mov     [rsp+48h+var_11], al
0x1800112f6  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x1800112fb  mov     rcx, [rsp+48h+cb]; cb
0x180011300  test    rcx, rcx
0x180011303  jz      short loc_18001133F
0x180011305  call    cs:__imp_CoTaskMemAlloc
0x18001130b  mov     rdx, rax
0x18001130e  mov     rcx, rdi
0x180011311  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180011316  mov     rax, [rdi]
0x180011319  test    rax, rax
0x18001131c  jz      short loc_180011332
0x18001131e  lea     r8, [rsp+48h+var_28]
0x180011323  mov     [rsp+48h+var_28], rax
0x180011328  mov     rcx, rbx; this
0x18001132b  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x180011330  jmp     short loc_180011349
0x180011332  cmp     dword ptr [rbx+8], 0
0x180011336  jl      short loc_18001133F
0x180011338  mov     dword ptr [rbx+8], 8007000Eh
0x18001133f  xor     edx, edx
0x180011341  mov     rcx, rdi
0x180011344  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180011349  mov     rbx, [rsp+48h+arg_0]
0x18001134e  add     rsp, 40h
0x180011352  pop     rdi
0x180011353  retn
```
