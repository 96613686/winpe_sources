# tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180023a8c`
- end: `0x180023b27`
- name: `??$read_cotaskmem_string@Ustring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180037068`

## callees

- `0x180023a8c`
- `0x180023b30`
- `0x1800359f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023ad8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023ad8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180023a8c  mov     rax, rsp
0x180023a8f  mov     [rax+8], rbx
0x180023a93  push    rdi
0x180023a94  sub     rsp, 40h
0x180023a98  mov     qword ptr [rax-28h], 0
0x180023aa0  lea     r8, [rsp+48h+var_28]
0x180023aa5  mov     qword ptr [rax-20h], 0
0x180023aad  mov     rdi, rdx
0x180023ab0  mov     byte ptr [rax-18h], 0
0x180023ab4  mov     rbx, rcx
0x180023ab7  xor     eax, eax
0x180023ab9  mov     [rsp+48h+var_17], eax
0x180023abd  mov     [rsp+48h+var_13], ax
0x180023ac2  mov     [rsp+48h+var_11], al
0x180023ac6  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x180023acb  mov     rcx, [rsp+48h+var_20]
0x180023ad0  test    rcx, rcx
0x180023ad3  jz      short loc_180023B12
0x180023ad5  add     rcx, rcx; cb
0x180023ad8  call    cs:__imp_CoTaskMemAlloc
0x180023ade  mov     rdx, rax
0x180023ae1  mov     rcx, rdi
0x180023ae4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180023ae9  mov     rax, [rdi]
0x180023aec  test    rax, rax
0x180023aef  jz      short loc_180023B05
0x180023af1  lea     r8, [rsp+48h+var_28]
0x180023af6  mov     [rsp+48h+var_28], rax
0x180023afb  mov     rcx, rbx; this
0x180023afe  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x180023b03  jmp     short loc_180023B1C
0x180023b05  cmp     dword ptr [rbx+8], 0
0x180023b09  jl      short loc_180023B12
0x180023b0b  mov     dword ptr [rbx+8], 8007000Eh
0x180023b12  xor     edx, edx
0x180023b14  mov     rcx, rdi
0x180023b17  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180023b1c  mov     rbx, [rsp+48h+arg_0]
0x180023b21  add     rsp, 40h
0x180023b25  pop     rdi
0x180023b26  retn
```
