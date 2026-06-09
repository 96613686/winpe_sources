# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x18001a3fc`
- end: `0x18001a44b`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `79`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006990`
- `0x1800153c0`
- `0x180015910`
- `0x180019428`
- `0x180024594`
- `0x180046f20`
- `0x1800473b0`

## callees

- `0x18001a3fc`
- `0x180025db0`
- `0x1800272f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a439`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a439`

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
0x18001a3fc  mov     [rsp+arg_8], rbx
0x18001a401  mov     [rsp+arg_10], rsi
0x18001a406  push    rdi
0x18001a407  sub     rsp, 20h
0x18001a40b  mov     rdi, [rcx]
0x18001a40e  mov     rsi, rdx
0x18001a411  mov     rbx, rcx
0x18001a414  test    rdi, rdi
0x18001a417  jnz     short loc_18001A42C
0x18001a419  mov     [rbx], rsi
0x18001a41c  mov     rbx, [rsp+28h+arg_8]
0x18001a421  mov     rsi, [rsp+28h+arg_10]
0x18001a426  add     rsp, 20h
0x18001a42a  pop     rdi
0x18001a42b  retn
0x18001a42c  lea     rcx, [rsp+28h+arg_0]; this
0x18001a431  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001a436  mov     rcx, rdi; pv
0x18001a439  call    cs:__imp_CoTaskMemFree
0x18001a43f  lea     rcx, [rsp+28h+arg_0]; this
0x18001a444  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001a449  jmp     short loc_18001A419
```
