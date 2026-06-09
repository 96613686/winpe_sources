# tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18001a8d4`
- end: `0x18001a96f`
- name: `??$read_cotaskmem_string@Ustring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800297b0`

## callees

- `0x18001a8d4`
- `0x18001a978`
- `0x18001e8cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a920`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a920`

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
0x18001a8d4  mov     rax, rsp
0x18001a8d7  mov     [rax+8], rbx
0x18001a8db  push    rdi
0x18001a8dc  sub     rsp, 40h
0x18001a8e0  mov     qword ptr [rax-28h], 0
0x18001a8e8  lea     r8, [rsp+48h+var_28]
0x18001a8ed  mov     qword ptr [rax-20h], 0
0x18001a8f5  mov     rdi, rdx
0x18001a8f8  mov     byte ptr [rax-18h], 0
0x18001a8fc  mov     rbx, rcx
0x18001a8ff  xor     eax, eax
0x18001a901  mov     [rsp+48h+var_17], eax
0x18001a905  mov     [rsp+48h+var_13], ax
0x18001a90a  mov     [rsp+48h+var_11], al
0x18001a90e  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x18001a913  mov     rcx, [rsp+48h+var_20]
0x18001a918  test    rcx, rcx
0x18001a91b  jz      short loc_18001A95A
0x18001a91d  add     rcx, rcx; cb
0x18001a920  call    cs:__imp_CoTaskMemAlloc
0x18001a926  mov     rdx, rax
0x18001a929  mov     rcx, rdi
0x18001a92c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001a931  mov     rax, [rdi]
0x18001a934  test    rax, rax
0x18001a937  jz      short loc_18001A94D
0x18001a939  lea     r8, [rsp+48h+var_28]
0x18001a93e  mov     [rsp+48h+var_28], rax
0x18001a943  mov     rcx, rbx; this
0x18001a946  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x18001a94b  jmp     short loc_18001A964
0x18001a94d  cmp     dword ptr [rbx+8], 0
0x18001a951  jl      short loc_18001A95A
0x18001a953  mov     dword ptr [rbx+8], 8007000Eh
0x18001a95a  xor     edx, edx
0x18001a95c  mov     rcx, rdi
0x18001a95f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001a964  mov     rbx, [rsp+48h+arg_0]
0x18001a969  add     rsp, 40h
0x18001a96d  pop     rdi
0x18001a96e  retn
```
