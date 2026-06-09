# ServiceContext::ReportStatus(ulong,long,ulong)

- ea: `0x180001a44`
- end: `0x180001a98`
- name: `?ReportStatus@ServiceContext@@QEAAJKJK@Z`
- size: `84`
- prototype: `__int64 __fastcall(ServiceContext *__hidden this, unsigned int, int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180001410`

## callees

- `0x180001a44`
- `0x180002d7c`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180001a6d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180001a6d`

## string_xrefs

- `0x180001a7c`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`

## pseudocode

```c
__int64 __fastcall ServiceContext::ReportStatus(ServiceContext *this, int a2, int a3, int a4)
{
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  ++*((_DWORD *)this + 15);
  *((_DWORD *)this + 14) = a3;
  *((_DWORD *)this + 11) = a2;
  *((_DWORD *)this + 16) = a4;
  *((_DWORD *)this + 13) = (a3 >> 31) & 0x42A;
  if ( SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 9), (LPSERVICE_STATUS)((char *)this + 40)) )
    return 0;
  else
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xC7,
             (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
             v4);
}

```

## disassembly

```asm
0x180001a44  sub     rsp, 28h
0x180001a48  inc     dword ptr [rcx+3Ch]
0x180001a4b  mov     [rcx+38h], r8d
0x180001a4f  mov     [rcx+2Ch], edx
0x180001a52  lea     rdx, [rcx+28h]; lpServiceStatus
0x180001a56  sar     r8d, 1Fh
0x180001a5a  and     r8d, 42Ah
0x180001a61  mov     [rcx+40h], r9d
0x180001a65  mov     [rcx+34h], r8d
0x180001a69  mov     rcx, [rcx+48h]; hServiceStatus
0x180001a6d  call    cs:__imp_SetServiceStatus
0x180001a73  test    eax, eax
0x180001a75  jnz     short loc_180001A91
0x180001a77  mov     rcx, [rsp+28h]; this
0x180001a7c  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\services"...
0x180001a83  mov     edx, 0C7h; void *
0x180001a88  add     rsp, 28h
0x180001a8c  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180001a91  xor     eax, eax
0x180001a93  add     rsp, 28h
0x180001a97  retn
```
