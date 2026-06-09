# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x1800149f8`
- end: `0x180014a79`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ea78`

## callees

- `0x1800149f8`
- `0x1800150c0`
- `0x180025db0`
- `0x1800272f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a56`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
        void **a1,
        __int64 a2,
        __int64 a3)
{
  void **v4; // rax
  void **v5; // rdi
  void *v6; // rbp
  void *v7; // rsi
  char v9; // [rsp+40h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+58h] [rbp+20h] BYREF

  v4 = (void **)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                  &pv,
                  a2,
                  a3);
  v5 = v4;
  if ( a1 != v4 )
  {
    v6 = *v4;
    v7 = *a1;
    if ( *a1 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v9);
      CoTaskMemFree(v7);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v9);
    }
    *a1 = v6;
    *v5 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  return *a1 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x1800149f8  mov     [rsp+arg_8], rbx
0x1800149fd  push    rbp
0x1800149fe  push    rsi
0x1800149ff  push    rdi
0x180014a00  sub     rsp, 20h
0x180014a04  mov     rbx, rcx
0x180014a07  lea     rcx, [rsp+38h+pv]
0x180014a0c  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180014a11  mov     rdi, rax
0x180014a14  cmp     rbx, rax
0x180014a17  jz      short loc_180014A4C
0x180014a19  mov     rbp, [rax]
0x180014a1c  mov     rsi, [rbx]
0x180014a1f  test    rsi, rsi
0x180014a22  jz      short loc_180014A42
0x180014a24  lea     rcx, [rsp+38h+arg_0]; this
0x180014a29  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180014a2e  mov     rcx, rsi; pv
0x180014a31  call    cs:__imp_CoTaskMemFree
0x180014a37  lea     rcx, [rsp+38h+arg_0]; this
0x180014a3c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180014a41  nop
0x180014a42  mov     [rbx], rbp
0x180014a45  mov     qword ptr [rdi], 0
0x180014a4c  mov     rcx, [rsp+38h+pv]; pv
0x180014a51  test    rcx, rcx
0x180014a54  jz      short loc_180014A5D
0x180014a56  call    cs:__imp_CoTaskMemFree
0x180014a5c  nop
0x180014a5d  mov     rax, [rbx]
0x180014a60  neg     rax
0x180014a63  sbb     eax, eax
0x180014a65  not     eax
0x180014a67  and     eax, 8007000Eh
0x180014a6c  mov     rbx, [rsp+38h+arg_8]
0x180014a71  add     rsp, 20h
0x180014a75  pop     rdi
0x180014a76  pop     rsi
0x180014a77  pop     rbp
0x180014a78  retn
```
