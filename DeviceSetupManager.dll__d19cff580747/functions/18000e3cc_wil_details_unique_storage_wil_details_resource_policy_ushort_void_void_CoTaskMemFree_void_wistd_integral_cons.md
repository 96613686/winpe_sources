# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x18000e3cc`
- end: `0x18000e419`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009928`
- `0x180010f48`
- `0x1800143e0`
- `0x1800157a8`
- `0x180016d60`
- `0x1800173ac`
- `0x180033d80`
- `0x180036cd8`

## callees

- `0x18000e3cc`
- `0x180015404`
- `0x180015494`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e3f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e3f6`

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
0x18000e3cc  mov     [rsp+arg_8], rbx
0x18000e3d1  mov     [rsp+arg_10], rsi
0x18000e3d6  push    rdi
0x18000e3d7  sub     rsp, 20h
0x18000e3db  mov     rdi, [rcx]
0x18000e3de  mov     rsi, rdx
0x18000e3e1  mov     rbx, rcx
0x18000e3e4  test    rdi, rdi
0x18000e3e7  jz      short loc_18000E406
0x18000e3e9  lea     rcx, [rsp+28h+arg_0]; this
0x18000e3ee  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000e3f3  mov     rcx, rdi; pv
0x18000e3f6  call    cs:__imp_CoTaskMemFree
0x18000e3fc  lea     rcx, [rsp+28h+arg_0]; this
0x18000e401  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000e406  mov     [rbx], rsi
0x18000e409  mov     rbx, [rsp+28h+arg_8]
0x18000e40e  mov     rsi, [rsp+28h+arg_10]
0x18000e413  add     rsp, 20h
0x18000e417  pop     rdi
0x18000e418  retn
```
