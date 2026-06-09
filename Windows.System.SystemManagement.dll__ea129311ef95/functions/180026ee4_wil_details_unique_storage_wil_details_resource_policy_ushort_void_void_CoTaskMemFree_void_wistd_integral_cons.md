# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x180026ee4`
- end: `0x180026f31`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001f51c`

## callees

- `0x1800059e0`
- `0x180005e48`
- `0x180026ee4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f0e`

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
0x180026ee4  mov     [rsp+arg_8], rbx
0x180026ee9  mov     [rsp+arg_10], rsi
0x180026eee  push    rdi
0x180026eef  sub     rsp, 20h
0x180026ef3  mov     rdi, [rcx]
0x180026ef6  mov     rsi, rdx
0x180026ef9  mov     rbx, rcx
0x180026efc  test    rdi, rdi
0x180026eff  jz      short loc_180026F1E
0x180026f01  lea     rcx, [rsp+28h+arg_0]; this
0x180026f06  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180026f0b  mov     rcx, rdi; pv
0x180026f0e  call    cs:__imp_CoTaskMemFree
0x180026f14  lea     rcx, [rsp+28h+arg_0]; this
0x180026f19  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180026f1e  mov     [rbx], rsi
0x180026f21  mov     rbx, [rsp+28h+arg_8]
0x180026f26  mov     rsi, [rsp+28h+arg_10]
0x180026f2b  add     rsp, 20h
0x180026f2f  pop     rdi
0x180026f30  retn
```
