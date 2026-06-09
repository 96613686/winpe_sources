# tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18004e980`
- end: `0x18004ea1b`
- name: `??$read_cotaskmem_string@Ustring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180076d68`

## callees

- `0x18004e980`
- `0x18004ea24`
- `0x180073644`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e9cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e9cc`

## pseudocode

```c
__int64 __fastcall tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        __int64 a2)
{
  tson::input_archive::read_string_two_phase<tson::string_tag>(this);
  return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
           a2,
           0);
}

```

## disassembly

```asm
0x18004e980  mov     rax, rsp
0x18004e983  mov     [rax+8], rbx
0x18004e987  push    rdi
0x18004e988  sub     rsp, 40h
0x18004e98c  mov     qword ptr [rax-28h], 0
0x18004e994  lea     r8, [rsp+48h+var_28]
0x18004e999  mov     qword ptr [rax-20h], 0
0x18004e9a1  mov     rdi, rdx
0x18004e9a4  mov     byte ptr [rax-18h], 0
0x18004e9a8  mov     rbx, rcx
0x18004e9ab  xor     eax, eax
0x18004e9ad  mov     [rsp+48h+var_17], eax
0x18004e9b1  mov     [rsp+48h+var_13], ax
0x18004e9b6  mov     [rsp+48h+var_11], al
0x18004e9ba  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x18004e9bf  mov     rcx, [rsp+48h+var_20]
0x18004e9c4  test    rcx, rcx
0x18004e9c7  jz      short loc_18004EA06
0x18004e9c9  add     rcx, rcx; cb
0x18004e9cc  call    cs:__imp_CoTaskMemAlloc
0x18004e9d2  mov     rdx, rax
0x18004e9d5  mov     rcx, rdi
0x18004e9d8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004e9dd  mov     rax, [rdi]
0x18004e9e0  test    rax, rax
0x18004e9e3  jz      short loc_18004E9F9
0x18004e9e5  lea     r8, [rsp+48h+var_28]
0x18004e9ea  mov     [rsp+48h+var_28], rax
0x18004e9ef  mov     rcx, rbx; this
0x18004e9f2  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x18004e9f7  jmp     short loc_18004EA10
0x18004e9f9  cmp     dword ptr [rbx+8], 0
0x18004e9fd  jl      short loc_18004EA06
0x18004e9ff  mov     dword ptr [rbx+8], 8007000Eh
0x18004ea06  xor     edx, edx
0x18004ea08  mov     rcx, rdi
0x18004ea0b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004ea10  mov     rbx, [rsp+48h+arg_0]
0x18004ea15  add     rsp, 40h
0x18004ea19  pop     rdi
0x18004ea1a  retn
```
