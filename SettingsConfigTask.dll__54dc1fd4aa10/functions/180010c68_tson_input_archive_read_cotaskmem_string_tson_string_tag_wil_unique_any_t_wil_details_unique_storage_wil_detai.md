# tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180010c68`
- end: `0x180010d03`
- name: `??$read_cotaskmem_string@Ustring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001efd4`

## callees

- `0x180010c68`
- `0x180010f58`
- `0x18002005c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010cb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010cb4`

## pseudocode

```c
void __fastcall tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        void **a2)
{
  tson::input_archive::read_string_two_phase<tson::string_tag>(this);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    a2,
    0);
}

```

## disassembly

```asm
0x180010c68  mov     rax, rsp
0x180010c6b  mov     [rax+8], rbx
0x180010c6f  push    rdi
0x180010c70  sub     rsp, 40h
0x180010c74  mov     qword ptr [rax-28h], 0
0x180010c7c  lea     r8, [rsp+48h+var_28]
0x180010c81  mov     qword ptr [rax-20h], 0
0x180010c89  mov     rdi, rdx
0x180010c8c  mov     byte ptr [rax-18h], 0
0x180010c90  mov     rbx, rcx
0x180010c93  xor     eax, eax
0x180010c95  mov     [rsp+48h+var_17], eax
0x180010c99  mov     [rsp+48h+var_13], ax
0x180010c9e  mov     [rsp+48h+var_11], al
0x180010ca2  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x180010ca7  mov     rcx, [rsp+48h+var_20]
0x180010cac  test    rcx, rcx
0x180010caf  jz      short loc_180010CEE
0x180010cb1  add     rcx, rcx; cb
0x180010cb4  call    cs:__imp_CoTaskMemAlloc
0x180010cba  mov     rdx, rax
0x180010cbd  mov     rcx, rdi
0x180010cc0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180010cc5  mov     rax, [rdi]
0x180010cc8  test    rax, rax
0x180010ccb  jz      short loc_180010CE1
0x180010ccd  lea     r8, [rsp+48h+var_28]
0x180010cd2  mov     [rsp+48h+var_28], rax
0x180010cd7  mov     rcx, rbx; this
0x180010cda  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x180010cdf  jmp     short loc_180010CF8
0x180010ce1  cmp     dword ptr [rbx+8], 0
0x180010ce5  jl      short loc_180010CEE
0x180010ce7  mov     dword ptr [rbx+8], 8007000Eh
0x180010cee  xor     edx, edx
0x180010cf0  mov     rcx, rdi
0x180010cf3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180010cf8  mov     rbx, [rsp+48h+arg_0]
0x180010cfd  add     rsp, 40h
0x180010d01  pop     rdi
0x180010d02  retn
```
