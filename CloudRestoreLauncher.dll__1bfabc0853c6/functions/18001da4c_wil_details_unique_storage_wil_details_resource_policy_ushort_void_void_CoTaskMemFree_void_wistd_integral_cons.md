# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x18001da4c`
- end: `0x18001da99`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180016d30`
- `0x180020f48`
- `0x180027f50`
- `0x1800343c8`
- `0x180034468`
- `0x18003dbe8`
- `0x180059f08`
- `0x18009ac3c`
- `0x1800a5f44`
- `0x1800aa010`
- `0x1800ad43c`
- `0x1800ad564`
- `0x1800adf58`
- `0x1800ae108`
- `0x1800bc5ac`
- `0x1800bd330`

## callees

- `0x18001003c`
- `0x18001031c`
- `0x18001da4c`

## import_xrefs

- `OLE32!CoTaskMemFree` at `0x18001da76`
- `OLE32!CoTaskMemFree` at `0x18001da76`

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
0x18001da4c  mov     [rsp+arg_8], rbx
0x18001da51  mov     [rsp+arg_10], rsi
0x18001da56  push    rdi
0x18001da57  sub     rsp, 20h
0x18001da5b  mov     rdi, [rcx]
0x18001da5e  mov     rsi, rdx
0x18001da61  mov     rbx, rcx
0x18001da64  test    rdi, rdi
0x18001da67  jz      short loc_18001DA86
0x18001da69  lea     rcx, [rsp+28h+arg_0]; this
0x18001da6e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001da73  mov     rcx, rdi; pv
0x18001da76  call    cs:__imp_CoTaskMemFree
0x18001da7c  lea     rcx, [rsp+28h+arg_0]; this
0x18001da81  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001da86  mov     [rbx], rsi
0x18001da89  mov     rbx, [rsp+28h+arg_8]
0x18001da8e  mov     rsi, [rsp+28h+arg_10]
0x18001da93  add     rsp, 20h
0x18001da97  pop     rdi
0x18001da98  retn
```
