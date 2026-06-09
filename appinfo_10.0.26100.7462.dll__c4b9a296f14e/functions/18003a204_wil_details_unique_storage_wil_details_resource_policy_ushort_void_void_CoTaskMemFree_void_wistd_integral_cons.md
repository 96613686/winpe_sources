# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x18003a204`
- end: `0x18003a258`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `84`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002a2a8`
- `0x18003d608`
- `0x18003df24`

## callees

- `0x180010f70`
- `0x1800121a4`
- `0x18003a204`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a22e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a22e`

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
0x18003a204  mov     [rsp+arg_8], rbx
0x18003a209  mov     [rsp+arg_10], rsi
0x18003a20e  push    rdi
0x18003a20f  sub     rsp, 20h
0x18003a213  mov     rdi, [rcx]
0x18003a216  mov     rsi, rdx
0x18003a219  mov     rbx, rcx
0x18003a21c  test    rdi, rdi
0x18003a21f  jz      short loc_18003A244
0x18003a221  lea     rcx, [rsp+28h+arg_0]; this
0x18003a226  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003a22b  mov     rcx, rdi; pv
0x18003a22e  call    cs:__imp_CoTaskMemFree
0x18003a235  nop     dword ptr [rax+rax+00h]
0x18003a23a  lea     rcx, [rsp+28h+arg_0]; this
0x18003a23f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003a244  mov     [rbx], rsi
0x18003a247  mov     rbx, [rsp+28h+arg_8]
0x18003a24c  mov     rsi, [rsp+28h+arg_10]
0x18003a251  add     rsp, 20h
0x18003a255  pop     rdi
0x18003a256  retn
```
