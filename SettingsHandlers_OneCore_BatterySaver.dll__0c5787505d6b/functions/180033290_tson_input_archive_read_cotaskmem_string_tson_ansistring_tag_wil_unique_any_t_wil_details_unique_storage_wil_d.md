# tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x180033290`
- end: `0x180033328`
- name: `??$read_cotaskmem_string@Uansistring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180031e9c`
- `0x180032c34`

## callees

- `0x180033290`
- `0x18003357c`
- `0x1800399a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800332d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800332d9`

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
0x180033290  mov     rax, rsp
0x180033293  mov     [rax+8], rbx
0x180033297  push    rdi
0x180033298  sub     rsp, 40h
0x18003329c  mov     qword ptr [rax-28h], 0
0x1800332a4  lea     r8, [rsp+48h+var_28]
0x1800332a9  mov     qword ptr [rax-20h], 0
0x1800332b1  mov     rdi, rdx
0x1800332b4  mov     byte ptr [rax-18h], 0
0x1800332b8  mov     rbx, rcx
0x1800332bb  xor     eax, eax
0x1800332bd  mov     [rsp+48h+var_17], eax
0x1800332c1  mov     [rsp+48h+var_13], ax
0x1800332c6  mov     [rsp+48h+var_11], al
0x1800332ca  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x1800332cf  mov     rcx, [rsp+48h+cb]; cb
0x1800332d4  test    rcx, rcx
0x1800332d7  jz      short loc_180033313
0x1800332d9  call    cs:__imp_CoTaskMemAlloc
0x1800332df  mov     rdx, rax
0x1800332e2  mov     rcx, rdi
0x1800332e5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800332ea  mov     rax, [rdi]
0x1800332ed  test    rax, rax
0x1800332f0  jz      short loc_180033306
0x1800332f2  lea     r8, [rsp+48h+var_28]
0x1800332f7  mov     [rsp+48h+var_28], rax
0x1800332fc  mov     rcx, rbx; this
0x1800332ff  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x180033304  jmp     short loc_18003331D
0x180033306  cmp     dword ptr [rbx+8], 0
0x18003330a  jl      short loc_180033313
0x18003330c  mov     dword ptr [rbx+8], 8007000Eh
0x180033313  xor     edx, edx
0x180033315  mov     rcx, rdi
0x180033318  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003331d  mov     rbx, [rsp+48h+arg_0]
0x180033322  add     rsp, 40h
0x180033326  pop     rdi
0x180033327  retn
```
