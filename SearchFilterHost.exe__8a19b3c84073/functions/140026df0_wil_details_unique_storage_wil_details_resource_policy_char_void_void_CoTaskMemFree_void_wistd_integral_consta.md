# wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)

- ea: `0x140026df0`
- end: `0x140026e3d`
- name: `?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14001a794`
- `0x14001a834`

## callees

- `0x140006418`
- `0x140006b80`
- `0x140026df0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026e1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026e1a`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
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
0x140026df0  mov     [rsp+arg_8], rbx
0x140026df5  mov     [rsp+arg_10], rsi
0x140026dfa  push    rdi
0x140026dfb  sub     rsp, 20h
0x140026dff  mov     rdi, [rcx]
0x140026e02  mov     rsi, rdx
0x140026e05  mov     rbx, rcx
0x140026e08  test    rdi, rdi
0x140026e0b  jz      short loc_140026E2A
0x140026e0d  lea     rcx, [rsp+28h+arg_0]; this
0x140026e12  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140026e17  mov     rcx, rdi; pv
0x140026e1a  call    cs:__imp_CoTaskMemFree
0x140026e20  lea     rcx, [rsp+28h+arg_0]; this
0x140026e25  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140026e2a  mov     [rbx], rsi
0x140026e2d  mov     rbx, [rsp+28h+arg_8]
0x140026e32  mov     rsi, [rsp+28h+arg_10]
0x140026e37  add     rsp, 20h
0x140026e3b  pop     rdi
0x140026e3c  retn
```
