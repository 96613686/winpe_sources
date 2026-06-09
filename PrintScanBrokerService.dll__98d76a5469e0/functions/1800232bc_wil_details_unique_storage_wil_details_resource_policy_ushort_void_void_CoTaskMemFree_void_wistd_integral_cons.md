# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x1800232bc`
- end: `0x180023309`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800229ac`
- `0x180022ef0`
- `0x180027f60`
- `0x1800296a0`
- `0x18002b4d0`

## callees

- `0x180007a28`
- `0x18000876c`
- `0x1800232bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800232e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800232e6`

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
0x1800232bc  mov     [rsp+arg_8], rbx
0x1800232c1  mov     [rsp+arg_10], rsi
0x1800232c6  push    rdi
0x1800232c7  sub     rsp, 20h
0x1800232cb  mov     rdi, [rcx]
0x1800232ce  mov     rsi, rdx
0x1800232d1  mov     rbx, rcx
0x1800232d4  test    rdi, rdi
0x1800232d7  jz      short loc_1800232F6
0x1800232d9  lea     rcx, [rsp+28h+arg_0]; this
0x1800232de  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800232e3  mov     rcx, rdi; pv
0x1800232e6  call    cs:__imp_CoTaskMemFree
0x1800232ec  lea     rcx, [rsp+28h+arg_0]; this
0x1800232f1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800232f6  mov     [rbx], rsi
0x1800232f9  mov     rbx, [rsp+28h+arg_8]
0x1800232fe  mov     rsi, [rsp+28h+arg_10]
0x180023303  add     rsp, 20h
0x180023307  pop     rdi
0x180023308  retn
```
