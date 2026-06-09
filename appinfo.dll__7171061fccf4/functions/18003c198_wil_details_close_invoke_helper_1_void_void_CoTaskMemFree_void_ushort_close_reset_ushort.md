# wil::details::close_invoke_helper<1,void (*)(void *),&CoTaskMemFree(void *),ushort *>::close_reset(ushort *)

- ea: `0x18003c198`
- end: `0x18003c1cb`
- name: `?close_reset@?$close_invoke_helper@$00P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZPEAG@details@wil@@SAXPEAG@Z`
- size: `51`
- prototype: `void __fastcall(LPVOID pv)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003c5b4`
- `0x18003c6ac`

## callees

- `0x18000debc`
- `0x18003c198`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c1bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c1bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c1ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c1ae`

## pseudocode

```c
void __fastcall wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(
        LPVOID pv)
{
  char v2; // [rsp+38h] [rbp+10h] BYREF
  DWORD dwErrCode; // [rsp+3Ch] [rbp+14h]

  wil::last_error_context::last_error_context((wil::last_error_context *)&v2);
  CoTaskMemFree(pv);
  if ( !v2 )
    SetLastError(dwErrCode);
}

```

## disassembly

```asm
0x18003c198  push    rbx
0x18003c19a  sub     rsp, 20h
0x18003c19e  mov     rbx, rcx
0x18003c1a1  lea     rcx, [rsp+28h+arg_8]; this
0x18003c1a6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003c1ab  mov     rcx, rbx; pv
0x18003c1ae  call    cs:__imp_CoTaskMemFree
0x18003c1b4  cmp     [rsp+28h+arg_8], 0
0x18003c1b9  jnz     short loc_18003C1C5
0x18003c1bb  mov     ecx, [rsp+28h+dwErrCode]; dwErrCode
0x18003c1bf  call    cs:__imp_SetLastError
0x18003c1c5  add     rsp, 20h
0x18003c1c9  pop     rbx
0x18003c1ca  retn
```
