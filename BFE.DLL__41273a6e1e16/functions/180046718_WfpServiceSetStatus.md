# WfpServiceSetStatus

- ea: `0x180046718`
- end: `0x1800467c7`
- name: `WfpServiceSetStatus`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18004668c`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x180046718`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004677e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004677e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18004676e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18004676e`

## string_xrefs

- `0x18004678d`: `SetServiceStatus`
- `0x1800467a1`: `WfpServiceSetStatus`

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
0x180046718  push    rbx
0x18004671a  sub     rsp, 50h
0x18004671e  mov     rax, cs:__security_cookie
0x180046725  xor     rax, rsp
0x180046728  mov     [rsp+58h+var_18], rax
0x18004672d  xor     ebx, ebx
0x18004672f  cmp     [rcx+18h], rbx
0x180046733  jz      short loc_1800467B0
0x180046735  mov     edx, [rcx+24h]
0x180046738  movups  xmm0, xmmword ptr [rcx+20h]
0x18004673c  movups  xmm1, xmmword ptr [rcx+2Ch]
0x180046740  lea     eax, [rdx-2]
0x180046743  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x180046748  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm1
0x18004674d  cmp     eax, 1
0x180046750  jbe     short loc_180046761
0x180046752  lea     eax, [rdx-5]
0x180046755  cmp     eax, 1
0x180046758  jbe     short loc_180046761
0x18004675a  mov     qword ptr [rsp+58h+ServiceStatus.dwCheckPoint], rbx
0x18004675f  jmp     short loc_180046765
0x180046761  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], ebx
0x180046765  mov     rcx, [rcx+18h]; hServiceStatus
0x180046769  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18004676e  call    cs:__imp_SetServiceStatus
0x180046775  nop     dword ptr [rax+rax+00h]
0x18004677a  test    eax, eax
0x18004677c  jnz     short loc_1800467B0
0x18004677e  call    cs:__imp_GetLastError
0x180046785  nop     dword ptr [rax+rax+00h]
0x18004678a  mov     r8d, eax
0x18004678d  lea     rdx, aSetservicestat_0; "SetServiceStatus"
0x180046794  call    WfpReportSysErrorAsWinError
0x180046799  mov     rbx, rax
0x18004679c  test    rax, rax
0x18004679f  jz      short loc_1800467B0
0x1800467a1  lea     rdx, aWfpservicesets; "WfpServiceSetStatus"
0x1800467a8  mov     rcx, rax
0x1800467ab  call    WfpReportError
0x1800467b0  mov     rax, rbx
0x1800467b3  mov     rcx, [rsp+58h+var_18]
0x1800467b8  xor     rcx, rsp; StackCookie
0x1800467bb  call    __security_check_cookie
0x1800467c0  add     rsp, 50h
0x1800467c4  pop     rbx
0x1800467c5  retn
```
