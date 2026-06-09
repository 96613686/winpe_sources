# WfpServiceSetStatus

- ea: `0x1800447b8`
- end: `0x18004485a`
- name: `WfpServiceSetStatus`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18004472c`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x1800447b8`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044818`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044818`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18004480e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18004480e`

## string_xrefs

- `0x180044821`: `SetServiceStatus`
- `0x180044835`: `WfpServiceSetStatus`

## pseudocode

```c
__int64 __fastcall WfpServiceSetStatus(__int64 a1)
{
  __int64 v1; // rbx
  int v2; // edx
  __int128 v3; // xmm1
  DWORD LastError; // eax
  __int64 v5; // rcx
  __int64 v6; // rax
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  v1 = 0;
  if ( *(_QWORD *)(a1 + 24) )
  {
    v2 = *(_DWORD *)(a1 + 36);
    v3 = *(_OWORD *)(a1 + 44);
    *(_OWORD *)&ServiceStatus.dwServiceType = *(_OWORD *)(a1 + 32);
    *(_OWORD *)&ServiceStatus.dwWin32ExitCode = v3;
    if ( (unsigned int)(v2 - 2) <= 1 || (unsigned int)(v2 - 5) <= 1 )
      ServiceStatus.dwControlsAccepted = 0;
    else
      *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
    if ( !SetServiceStatus(*(SERVICE_STATUS_HANDLE *)(a1 + 24), &ServiceStatus) )
    {
      LastError = GetLastError();
      v6 = WfpReportSysErrorAsWinError(v5, "SetServiceStatus", LastError);
      v1 = v6;
      if ( v6 )
        WfpReportError(v6, "WfpServiceSetStatus");
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800447b8  push    rbx
0x1800447ba  sub     rsp, 50h
0x1800447be  mov     rax, cs:__security_cookie
0x1800447c5  xor     rax, rsp
0x1800447c8  mov     [rsp+58h+var_18], rax
0x1800447cd  xor     ebx, ebx
0x1800447cf  cmp     [rcx+18h], rbx
0x1800447d3  jz      short loc_180044844
0x1800447d5  mov     edx, [rcx+24h]
0x1800447d8  movups  xmm0, xmmword ptr [rcx+20h]
0x1800447dc  movups  xmm1, xmmword ptr [rcx+2Ch]
0x1800447e0  lea     eax, [rdx-2]
0x1800447e3  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x1800447e8  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm1
0x1800447ed  cmp     eax, 1
0x1800447f0  jbe     short loc_180044801
0x1800447f2  lea     eax, [rdx-5]
0x1800447f5  cmp     eax, 1
0x1800447f8  jbe     short loc_180044801
0x1800447fa  mov     qword ptr [rsp+58h+ServiceStatus.dwCheckPoint], rbx
0x1800447ff  jmp     short loc_180044805
0x180044801  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], ebx
0x180044805  mov     rcx, [rcx+18h]; hServiceStatus
0x180044809  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18004480e  call    cs:__imp_SetServiceStatus
0x180044814  test    eax, eax
0x180044816  jnz     short loc_180044844
0x180044818  call    cs:__imp_GetLastError
0x18004481e  mov     r8d, eax
0x180044821  lea     rdx, aSetservicestat_0; "SetServiceStatus"
0x180044828  call    WfpReportSysErrorAsWinError
0x18004482d  mov     rbx, rax
0x180044830  test    rax, rax
0x180044833  jz      short loc_180044844
0x180044835  lea     rdx, aWfpservicesets; "WfpServiceSetStatus"
0x18004483c  mov     rcx, rax
0x18004483f  call    WfpReportError
0x180044844  mov     rax, rbx
0x180044847  mov     rcx, [rsp+58h+var_18]
0x18004484c  xor     rcx, rsp; StackCookie
0x18004484f  call    __security_check_cookie
0x180044854  add     rsp, 50h
0x180044858  pop     rbx
0x180044859  retn
```
