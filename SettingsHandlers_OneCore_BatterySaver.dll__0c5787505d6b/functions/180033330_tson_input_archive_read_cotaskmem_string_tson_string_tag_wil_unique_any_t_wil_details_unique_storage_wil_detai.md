# tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180033330`
- end: `0x1800333cb`
- name: `??$read_cotaskmem_string@Ustring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180038b64`

## callees

- `0x180033330`
- `0x180033620`
- `0x1800399a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003337c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003337c`

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
0x180033330  mov     rax, rsp
0x180033333  mov     [rax+8], rbx
0x180033337  push    rdi
0x180033338  sub     rsp, 40h
0x18003333c  mov     qword ptr [rax-28h], 0
0x180033344  lea     r8, [rsp+48h+var_28]
0x180033349  mov     qword ptr [rax-20h], 0
0x180033351  mov     rdi, rdx
0x180033354  mov     byte ptr [rax-18h], 0
0x180033358  mov     rbx, rcx
0x18003335b  xor     eax, eax
0x18003335d  mov     [rsp+48h+var_17], eax
0x180033361  mov     [rsp+48h+var_13], ax
0x180033366  mov     [rsp+48h+var_11], al
0x18003336a  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x18003336f  mov     rcx, [rsp+48h+var_20]
0x180033374  test    rcx, rcx
0x180033377  jz      short loc_1800333B6
0x180033379  add     rcx, rcx; cb
0x18003337c  call    cs:__imp_CoTaskMemAlloc
0x180033382  mov     rdx, rax
0x180033385  mov     rcx, rdi
0x180033388  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003338d  mov     rax, [rdi]
0x180033390  test    rax, rax
0x180033393  jz      short loc_1800333A9
0x180033395  lea     r8, [rsp+48h+var_28]
0x18003339a  mov     [rsp+48h+var_28], rax
0x18003339f  mov     rcx, rbx; this
0x1800333a2  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x1800333a7  jmp     short loc_1800333C0
0x1800333a9  cmp     dword ptr [rbx+8], 0
0x1800333ad  jl      short loc_1800333B6
0x1800333af  mov     dword ptr [rbx+8], 8007000Eh
0x1800333b6  xor     edx, edx
0x1800333b8  mov     rcx, rdi
0x1800333bb  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800333c0  mov     rbx, [rsp+48h+arg_0]
0x1800333c5  add     rsp, 40h
0x1800333c9  pop     rdi
0x1800333ca  retn
```
