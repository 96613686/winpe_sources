# Windows::Detail::CloseWithCloseServiceHandle(SC_HANDLE__ *)

- ea: `0x14000bb20`
- end: `0x14000bb40`
- name: `?CloseWithCloseServiceHandle@Detail@Windows@@YAXPEAUSC_HANDLE__@@@Z`
- size: `32`
- prototype: `void __fastcall(Windows::Detail *__hidden this, struct SC_HANDLE__ *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x14000d5c8`

## callees

- `0x14000bb20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bb2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bb2e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000bb24`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000bb24`

## pseudocode

```c
void __fastcall Windows::Detail::CloseWithCloseServiceHandle(Windows::Detail *this, struct SC_HANDLE__ *a2)
{
  if ( !CloseServiceHandle((SC_HANDLE)this) )
  {
    GetLastError();
    __fastfail(7u);
  }
}

```

## disassembly

```asm
0x14000bb20  sub     rsp, 28h
0x14000bb24  call    cs:__imp_CloseServiceHandle
0x14000bb2a  test    eax, eax
0x14000bb2c  jnz     short loc_14000BB3B
0x14000bb2e  call    cs:__imp_GetLastError
0x14000bb34  mov     ecx, 7
0x14000bb39  int     29h; Win8: RtlFailFast(ecx)
0x14000bb3b  add     rsp, 28h
0x14000bb3f  retn
```
