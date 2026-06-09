# tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x1800264b4`
- end: `0x18002654c`
- name: `??$read_cotaskmem_string@Uansistring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022e88`
- `0x1800259e4`

## callees

- `0x180022498`
- `0x1800264b4`
- `0x1800267a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800264fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800264fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800264b4  mov     rax, rsp
0x1800264b7  mov     [rax+8], rbx
0x1800264bb  push    rdi
0x1800264bc  sub     rsp, 40h
0x1800264c0  mov     qword ptr [rax-28h], 0
0x1800264c8  lea     r8, [rsp+48h+var_28]
0x1800264cd  mov     qword ptr [rax-20h], 0
0x1800264d5  mov     rdi, rdx
0x1800264d8  mov     byte ptr [rax-18h], 0
0x1800264dc  mov     rbx, rcx
0x1800264df  xor     eax, eax
0x1800264e1  mov     [rsp+48h+var_17], eax
0x1800264e5  mov     [rsp+48h+var_13], ax
0x1800264ea  mov     [rsp+48h+var_11], al
0x1800264ee  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x1800264f3  mov     rcx, [rsp+48h+cb]; cb
0x1800264f8  test    rcx, rcx
0x1800264fb  jz      short loc_180026537
0x1800264fd  call    cs:__imp_CoTaskMemAlloc
0x180026503  mov     rdx, rax
0x180026506  mov     rcx, rdi
0x180026509  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002650e  mov     rax, [rdi]
0x180026511  test    rax, rax
0x180026514  jz      short loc_18002652A
0x180026516  lea     r8, [rsp+48h+var_28]
0x18002651b  mov     [rsp+48h+var_28], rax
0x180026520  mov     rcx, rbx; this
0x180026523  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x180026528  jmp     short loc_180026541
0x18002652a  cmp     dword ptr [rbx+8], 0
0x18002652e  jl      short loc_180026537
0x180026530  mov     dword ptr [rbx+8], 8007000Eh
0x180026537  xor     edx, edx
0x180026539  mov     rcx, rdi
0x18002653c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180026541  mov     rbx, [rsp+48h+arg_0]
0x180026546  add     rsp, 40h
0x18002654a  pop     rdi
0x18002654b  retn
```
