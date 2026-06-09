# tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180026554`
- end: `0x1800265ef`
- name: `??$read_cotaskmem_string@Ustring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180035878`

## callees

- `0x180022498`
- `0x180026554`
- `0x180026844`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800265a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800265a0`

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
0x180026554  mov     rax, rsp
0x180026557  mov     [rax+8], rbx
0x18002655b  push    rdi
0x18002655c  sub     rsp, 40h
0x180026560  mov     qword ptr [rax-28h], 0
0x180026568  lea     r8, [rsp+48h+var_28]
0x18002656d  mov     qword ptr [rax-20h], 0
0x180026575  mov     rdi, rdx
0x180026578  mov     byte ptr [rax-18h], 0
0x18002657c  mov     rbx, rcx
0x18002657f  xor     eax, eax
0x180026581  mov     [rsp+48h+var_17], eax
0x180026585  mov     [rsp+48h+var_13], ax
0x18002658a  mov     [rsp+48h+var_11], al
0x18002658e  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x180026593  mov     rcx, [rsp+48h+var_20]
0x180026598  test    rcx, rcx
0x18002659b  jz      short loc_1800265DA
0x18002659d  add     rcx, rcx; cb
0x1800265a0  call    cs:__imp_CoTaskMemAlloc
0x1800265a6  mov     rdx, rax
0x1800265a9  mov     rcx, rdi
0x1800265ac  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800265b1  mov     rax, [rdi]
0x1800265b4  test    rax, rax
0x1800265b7  jz      short loc_1800265CD
0x1800265b9  lea     r8, [rsp+48h+var_28]
0x1800265be  mov     [rsp+48h+var_28], rax
0x1800265c3  mov     rcx, rbx; this
0x1800265c6  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x1800265cb  jmp     short loc_1800265E4
0x1800265cd  cmp     dword ptr [rbx+8], 0
0x1800265d1  jl      short loc_1800265DA
0x1800265d3  mov     dword ptr [rbx+8], 8007000Eh
0x1800265da  xor     edx, edx
0x1800265dc  mov     rcx, rdi
0x1800265df  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800265e4  mov     rbx, [rsp+48h+arg_0]
0x1800265e9  add     rsp, 40h
0x1800265ed  pop     rdi
0x1800265ee  retn
```
