# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x1800399a4`
- end: `0x1800399f1`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180033290`
- `0x180033330`

## callees

- `0x18000b198`
- `0x18000b85c`
- `0x1800399a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800399ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800399ce`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        void **a1,
        void *a2)
{
  void *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    CoTaskMemFree(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x1800399a4  mov     [rsp+arg_8], rbx
0x1800399a9  mov     [rsp+arg_10], rsi
0x1800399ae  push    rdi
0x1800399af  sub     rsp, 20h
0x1800399b3  mov     rdi, [rcx]
0x1800399b6  mov     rsi, rdx
0x1800399b9  mov     rbx, rcx
0x1800399bc  test    rdi, rdi
0x1800399bf  jz      short loc_1800399DE
0x1800399c1  lea     rcx, [rsp+28h+arg_0]; this
0x1800399c6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800399cb  mov     rcx, rdi; pv
0x1800399ce  call    cs:__imp_CoTaskMemFree
0x1800399d4  lea     rcx, [rsp+28h+arg_0]; this
0x1800399d9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800399de  mov     [rbx], rsi
0x1800399e1  mov     rbx, [rsp+28h+arg_8]
0x1800399e6  mov     rsi, [rsp+28h+arg_10]
0x1800399eb  add     rsp, 20h
0x1800399ef  pop     rdi
0x1800399f0  retn
```
