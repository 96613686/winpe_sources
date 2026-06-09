# tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x180010bc8`
- end: `0x180010c60`
- name: `??$read_cotaskmem_string@Uansistring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c940`
- `0x18000fff8`

## callees

- `0x180010bc8`
- `0x180010eb4`
- `0x18002005c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010c11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010c11`

## pseudocode

```c
__int64 __fastcall tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        __int64 a2)
{
  tson::input_archive::read_string_two_phase<tson::ansistring_tag>(this);
  return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
           a2,
           0);
}

```

## disassembly

```asm
0x180010bc8  mov     rax, rsp
0x180010bcb  mov     [rax+8], rbx
0x180010bcf  push    rdi
0x180010bd0  sub     rsp, 40h
0x180010bd4  mov     qword ptr [rax-28h], 0
0x180010bdc  lea     r8, [rsp+48h+var_28]
0x180010be1  mov     qword ptr [rax-20h], 0
0x180010be9  mov     rdi, rdx
0x180010bec  mov     byte ptr [rax-18h], 0
0x180010bf0  mov     rbx, rcx
0x180010bf3  xor     eax, eax
0x180010bf5  mov     [rsp+48h+var_17], eax
0x180010bf9  mov     [rsp+48h+var_13], ax
0x180010bfe  mov     [rsp+48h+var_11], al
0x180010c02  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x180010c07  mov     rcx, [rsp+48h+cb]; cb
0x180010c0c  test    rcx, rcx
0x180010c0f  jz      short loc_180010C4B
0x180010c11  call    cs:__imp_CoTaskMemAlloc
0x180010c17  mov     rdx, rax
0x180010c1a  mov     rcx, rdi
0x180010c1d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180010c22  mov     rax, [rdi]
0x180010c25  test    rax, rax
0x180010c28  jz      short loc_180010C3E
0x180010c2a  lea     r8, [rsp+48h+var_28]
0x180010c2f  mov     [rsp+48h+var_28], rax
0x180010c34  mov     rcx, rbx; this
0x180010c37  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x180010c3c  jmp     short loc_180010C55
0x180010c3e  cmp     dword ptr [rbx+8], 0
0x180010c42  jl      short loc_180010C4B
0x180010c44  mov     dword ptr [rbx+8], 8007000Eh
0x180010c4b  xor     edx, edx
0x180010c4d  mov     rcx, rdi
0x180010c50  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180010c55  mov     rbx, [rsp+48h+arg_0]
0x180010c5a  add     rsp, 40h
0x180010c5e  pop     rdi
0x180010c5f  retn
```
