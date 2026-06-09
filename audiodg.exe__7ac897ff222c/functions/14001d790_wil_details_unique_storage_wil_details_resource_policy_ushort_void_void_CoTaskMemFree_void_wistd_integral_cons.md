# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x14001d790`
- end: `0x14001d7e6`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `86`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `19`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000664c`
- `0x1400171a4`
- `0x14001d540`
- `0x14001d76c`
- `0x140038230`
- `0x140045b80`
- `0x140047448`
- `0x1400476e8`
- `0x140047894`
- `0x140052090`
- `0x140054bcc`
- `0x140054f24`
- `0x140058e58`
- `0x140065774`
- `0x140067680`
- `0x14007e090`
- `0x140081a60`
- `0x140081d08`
- `0x140095494`

## callees

- `0x14001d790`
- `0x1400215f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001d7de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001d7de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d7cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d7cd`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        void **a1,
        void *a2)
{
  void *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF
  DWORD dwErrCode; // [rsp+34h] [rbp+Ch]

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    CoTaskMemFree(v2);
    if ( !v5 )
      SetLastError(dwErrCode);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x14001d790  mov     [rsp+arg_8], rbx
0x14001d795  mov     [rsp+arg_10], rsi
0x14001d79a  push    rdi
0x14001d79b  sub     rsp, 20h
0x14001d79f  mov     rdi, [rcx]
0x14001d7a2  mov     rsi, rdx
0x14001d7a5  mov     rbx, rcx
0x14001d7a8  test    rdi, rdi
0x14001d7ab  jnz     short loc_14001D7C0
0x14001d7ad  mov     [rbx], rsi
0x14001d7b0  mov     rbx, [rsp+28h+arg_8]
0x14001d7b5  mov     rsi, [rsp+28h+arg_10]
0x14001d7ba  add     rsp, 20h
0x14001d7be  pop     rdi
0x14001d7bf  retn
0x14001d7c0  lea     rcx, [rsp+28h+arg_0]; this
0x14001d7c5  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001d7ca  mov     rcx, rdi; pv
0x14001d7cd  call    cs:__imp_CoTaskMemFree
0x14001d7d3  cmp     [rsp+28h+arg_0], 0
0x14001d7d8  jnz     short loc_14001D7AD
0x14001d7da  mov     ecx, [rsp+28h+dwErrCode]; dwErrCode
0x14001d7de  call    cs:__imp_SetLastError
0x14001d7e4  jmp     short loc_14001D7AD
```
