# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x1800112f0`
- end: `0x18001133d`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d904`
- `0x180013284`

## callees

- `0x1800047c4`
- `0x180004e40`
- `0x1800112f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001131a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001131a`

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
0x1800112f0  mov     [rsp+arg_8], rbx
0x1800112f5  mov     [rsp+arg_10], rsi
0x1800112fa  push    rdi
0x1800112fb  sub     rsp, 20h
0x1800112ff  mov     rdi, [rcx]
0x180011302  mov     rsi, rdx
0x180011305  mov     rbx, rcx
0x180011308  test    rdi, rdi
0x18001130b  jz      short loc_18001132A
0x18001130d  lea     rcx, [rsp+28h+arg_0]; this
0x180011312  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180011317  mov     rcx, rdi; pv
0x18001131a  call    cs:__imp_CoTaskMemFree
0x180011320  lea     rcx, [rsp+28h+arg_0]; this
0x180011325  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001132a  mov     [rbx], rsi
0x18001132d  mov     rbx, [rsp+28h+arg_8]
0x180011332  mov     rsi, [rsp+28h+arg_10]
0x180011337  add     rsp, 20h
0x18001133b  pop     rdi
0x18001133c  retn
```
