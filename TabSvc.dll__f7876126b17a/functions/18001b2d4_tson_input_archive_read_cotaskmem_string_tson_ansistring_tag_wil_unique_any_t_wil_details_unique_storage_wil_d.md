# tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x18001b2d4`
- end: `0x18001b36c`
- name: `??$read_cotaskmem_string@Uansistring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b2a4`
- `0x18001dfe4`

## callees

- `0x18001a978`
- `0x18001b2d4`
- `0x18001e828`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b31d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b31d`

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
0x18001b2d4  mov     rax, rsp
0x18001b2d7  mov     [rax+8], rbx
0x18001b2db  push    rdi
0x18001b2dc  sub     rsp, 40h
0x18001b2e0  mov     qword ptr [rax-28h], 0
0x18001b2e8  lea     r8, [rsp+48h+var_28]
0x18001b2ed  mov     qword ptr [rax-20h], 0
0x18001b2f5  mov     rdi, rdx
0x18001b2f8  mov     byte ptr [rax-18h], 0
0x18001b2fc  mov     rbx, rcx
0x18001b2ff  xor     eax, eax
0x18001b301  mov     [rsp+48h+var_17], eax
0x18001b305  mov     [rsp+48h+var_13], ax
0x18001b30a  mov     [rsp+48h+var_11], al
0x18001b30e  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x18001b313  mov     rcx, [rsp+48h+cb]; cb
0x18001b318  test    rcx, rcx
0x18001b31b  jz      short loc_18001B357
0x18001b31d  call    cs:__imp_CoTaskMemAlloc
0x18001b323  mov     rdx, rax
0x18001b326  mov     rcx, rdi
0x18001b329  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001b32e  mov     rax, [rdi]
0x18001b331  test    rax, rax
0x18001b334  jz      short loc_18001B34A
0x18001b336  lea     r8, [rsp+48h+var_28]
0x18001b33b  mov     [rsp+48h+var_28], rax
0x18001b340  mov     rcx, rbx; this
0x18001b343  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x18001b348  jmp     short loc_18001B361
0x18001b34a  cmp     dword ptr [rbx+8], 0
0x18001b34e  jl      short loc_18001B357
0x18001b350  mov     dword ptr [rbx+8], 8007000Eh
0x18001b357  xor     edx, edx
0x18001b359  mov     rcx, rdi
0x18001b35c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001b361  mov     rbx, [rsp+48h+arg_0]
0x18001b366  add     rsp, 40h
0x18001b36a  pop     rdi
0x18001b36b  retn
```
