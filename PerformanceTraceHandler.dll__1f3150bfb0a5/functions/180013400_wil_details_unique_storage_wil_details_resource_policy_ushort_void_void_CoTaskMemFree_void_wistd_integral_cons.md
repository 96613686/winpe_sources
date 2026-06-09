# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x180013400`
- end: `0x18001344d`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: `void __fastcall(void **, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010c6c`
- `0x180011bd4`

## callees

- `0x1800045b8`
- `0x180004c88`
- `0x180013400`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001342a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001342a`

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
0x180013400  mov     [rsp+arg_8], rbx
0x180013405  mov     [rsp+arg_10], rsi
0x18001340a  push    rdi
0x18001340b  sub     rsp, 20h
0x18001340f  mov     rdi, [rcx]
0x180013412  mov     rsi, rdx
0x180013415  mov     rbx, rcx
0x180013418  test    rdi, rdi
0x18001341b  jz      short loc_18001343A
0x18001341d  lea     rcx, [rsp+28h+arg_0]; this
0x180013422  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180013427  mov     rcx, rdi; pv
0x18001342a  call    cs:__imp_CoTaskMemFree
0x180013430  lea     rcx, [rsp+28h+arg_0]; this
0x180013435  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001343a  mov     [rbx], rsi
0x18001343d  mov     rbx, [rsp+28h+arg_8]
0x180013442  mov     rsi, [rsp+28h+arg_10]
0x180013447  add     rsp, 20h
0x18001344b  pop     rdi
0x18001344c  retn
```
