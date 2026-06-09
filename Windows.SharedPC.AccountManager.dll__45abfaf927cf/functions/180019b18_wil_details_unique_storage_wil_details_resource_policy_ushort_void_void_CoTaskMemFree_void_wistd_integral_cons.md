# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x180019b18`
- end: `0x180019b65`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015ee0`
- `0x18001d110`
- `0x18001d480`
- `0x18001fcf4`
- `0x180020e10`

## callees

- `0x180006e2c`
- `0x180007328`
- `0x180019b18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019b42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019b42`

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
0x180019b18  mov     [rsp+arg_8], rbx
0x180019b1d  mov     [rsp+arg_10], rsi
0x180019b22  push    rdi
0x180019b23  sub     rsp, 20h
0x180019b27  mov     rdi, [rcx]
0x180019b2a  mov     rsi, rdx
0x180019b2d  mov     rbx, rcx
0x180019b30  test    rdi, rdi
0x180019b33  jz      short loc_180019B52
0x180019b35  lea     rcx, [rsp+28h+arg_0]; this
0x180019b3a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180019b3f  mov     rcx, rdi; pv
0x180019b42  call    cs:__imp_CoTaskMemFree
0x180019b48  lea     rcx, [rsp+28h+arg_0]; this
0x180019b4d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180019b52  mov     [rbx], rsi
0x180019b55  mov     rbx, [rsp+28h+arg_8]
0x180019b5a  mov     rsi, [rsp+28h+arg_10]
0x180019b5f  add     rsp, 20h
0x180019b63  pop     rdi
0x180019b64  retn
```
