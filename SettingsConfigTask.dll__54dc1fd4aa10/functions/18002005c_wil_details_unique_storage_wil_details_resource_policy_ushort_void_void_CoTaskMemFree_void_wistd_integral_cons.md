# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x18002005c`
- end: `0x1800200a9`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010bc8`
- `0x180010c68`
- `0x180012d98`

## callees

- `0x180004264`
- `0x180004a88`
- `0x18002005c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020086`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020086`

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
0x18002005c  mov     [rsp+arg_8], rbx
0x180020061  mov     [rsp+arg_10], rsi
0x180020066  push    rdi
0x180020067  sub     rsp, 20h
0x18002006b  mov     rdi, [rcx]
0x18002006e  mov     rsi, rdx
0x180020071  mov     rbx, rcx
0x180020074  test    rdi, rdi
0x180020077  jz      short loc_180020096
0x180020079  lea     rcx, [rsp+28h+arg_0]; this
0x18002007e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180020083  mov     rcx, rdi; pv
0x180020086  call    cs:__imp_CoTaskMemFree
0x18002008c  lea     rcx, [rsp+28h+arg_0]; this
0x180020091  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180020096  mov     [rbx], rsi
0x180020099  mov     rbx, [rsp+28h+arg_8]
0x18002009e  mov     rsi, [rsp+28h+arg_10]
0x1800200a3  add     rsp, 20h
0x1800200a7  pop     rdi
0x1800200a8  retn
```
