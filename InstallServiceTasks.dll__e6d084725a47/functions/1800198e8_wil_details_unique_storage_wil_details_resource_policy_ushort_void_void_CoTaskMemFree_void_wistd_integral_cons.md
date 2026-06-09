# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x1800198e8`
- end: `0x180019935`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016e44`

## callees

- `0x180005894`
- `0x180005f24`
- `0x1800198e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019912`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019912`

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
0x1800198e8  mov     [rsp+arg_8], rbx
0x1800198ed  mov     [rsp+arg_10], rsi
0x1800198f2  push    rdi
0x1800198f3  sub     rsp, 20h
0x1800198f7  mov     rdi, [rcx]
0x1800198fa  mov     rsi, rdx
0x1800198fd  mov     rbx, rcx
0x180019900  test    rdi, rdi
0x180019903  jz      short loc_180019922
0x180019905  lea     rcx, [rsp+28h+arg_0]; this
0x18001990a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001990f  mov     rcx, rdi; pv
0x180019912  call    cs:__imp_CoTaskMemFree
0x180019918  lea     rcx, [rsp+28h+arg_0]; this
0x18001991d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180019922  mov     [rbx], rsi
0x180019925  mov     rbx, [rsp+28h+arg_8]
0x18001992a  mov     rsi, [rsp+28h+arg_10]
0x18001992f  add     rsp, 20h
0x180019933  pop     rdi
0x180019934  retn
```
