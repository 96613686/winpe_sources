# tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x1800164c4`
- end: `0x18001655f`
- name: `??$read_cotaskmem_string@Ustring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019850`

## callees

- `0x180010a60`
- `0x1800164c4`
- `0x1800167b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016510`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016510`

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
0x1800164c4  mov     rax, rsp
0x1800164c7  mov     [rax+8], rbx
0x1800164cb  push    rdi
0x1800164cc  sub     rsp, 40h
0x1800164d0  mov     qword ptr [rax-28h], 0
0x1800164d8  lea     r8, [rsp+48h+var_28]
0x1800164dd  mov     qword ptr [rax-20h], 0
0x1800164e5  mov     rdi, rdx
0x1800164e8  mov     byte ptr [rax-18h], 0
0x1800164ec  mov     rbx, rcx
0x1800164ef  xor     eax, eax
0x1800164f1  mov     [rsp+48h+var_17], eax
0x1800164f5  mov     [rsp+48h+var_13], ax
0x1800164fa  mov     [rsp+48h+var_11], al
0x1800164fe  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x180016503  mov     rcx, [rsp+48h+var_20]
0x180016508  test    rcx, rcx
0x18001650b  jz      short loc_18001654A
0x18001650d  add     rcx, rcx; cb
0x180016510  call    cs:__imp_CoTaskMemAlloc
0x180016516  mov     rdx, rax
0x180016519  mov     rcx, rdi
0x18001651c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180016521  mov     rax, [rdi]
0x180016524  test    rax, rax
0x180016527  jz      short loc_18001653D
0x180016529  lea     r8, [rsp+48h+var_28]
0x18001652e  mov     [rsp+48h+var_28], rax
0x180016533  mov     rcx, rbx; this
0x180016536  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x18001653b  jmp     short loc_180016554
0x18001653d  cmp     dword ptr [rbx+8], 0
0x180016541  jl      short loc_18001654A
0x180016543  mov     dword ptr [rbx+8], 8007000Eh
0x18001654a  xor     edx, edx
0x18001654c  mov     rcx, rdi
0x18001654f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180016554  mov     rbx, [rsp+48h+arg_0]
0x180016559  add     rsp, 40h
0x18001655d  pop     rdi
0x18001655e  retn
```
