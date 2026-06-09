# UpdateServiceStatus(ulong,long)

- ea: `0x180012c9c`
- end: `0x180012dd2`
- name: `?UpdateServiceStatus@@YAJKJ@Z`
- size: `310`
- prototype: `__int64 __fastcall(DWORD, __int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x1800124dc`
- `0x1800127bc`
- `0x180012974`
- `0x180012de0`

## callees

- `0x18000a644`
- `0x18000a778`
- `0x180012c9c`
- `0x180013064`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d50`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180012d46`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180012d46`

## pseudocode

```c
__int64 __fastcall UpdateServiceStatus(DWORD a1, __int64 a2, __int64 a3)
{
  _QWORD *v4; // rcx
  unsigned int v5; // ebx
  DWORD v6; // edi
  DWORD v7; // edi
  signed int LastError; // eax
  _QWORD *v9; // rcx

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = 0;
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
    WPP_SF_dd(v4[2], a2, a3, g_ServiceStatus.dwCurrentState, a1);
  g_ServiceStatus.dwCurrentState = a1;
  *(_QWORD *)&g_ServiceStatus.dwCheckPoint = 0;
  v6 = a1 - 2;
  if ( v6 && (v7 = v6 - 1) != 0 )
  {
    if ( v7 == 1 )
      g_ServiceStatus.dwControlsAccepted |= 0x401u;
  }
  else
  {
    g_ServiceStatus.dwControlsAccepted = 0;
  }
  *(_QWORD *)&g_ServiceStatus.dwWin32ExitCode = 0;
  if ( SetServiceStatus(g_hService, &g_ServiceStatus) )
    goto LABEL_20;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( (v5 & 0x80000000) == 0 )
    v5 = -2147467259;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_21:
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x20) != 0 )
        WPP_SF_(v9[2], 13, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
      return v5;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
LABEL_20:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_21;
  }
  return v5;
}

```

## disassembly

```asm
0x180012c9c  mov     [rsp+arg_0], rbx
0x180012ca1  mov     [rsp+arg_8], rbp
0x180012ca6  push    rdi
0x180012ca7  sub     rsp, 30h
0x180012cab  mov     edi, ecx
0x180012cad  mov     rcx, cs:WPP_GLOBAL_Control
0x180012cb4  lea     rbp, WPP_GLOBAL_Control
0x180012cbb  cmp     rcx, rbp
0x180012cbe  jz      short loc_180012CE2
0x180012cc0  test    byte ptr [rcx+1Ch], 20h
0x180012cc4  jz      short loc_180012CE2
0x180012cc6  mov     rcx, [rcx+10h]
0x180012cca  lea     r8, WPP_3f50365df99735211a88e8fb382b12e7_Traceguids
0x180012cd1  mov     edx, 0Ah
0x180012cd6  call    WPP_SF_
0x180012cdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ce2  xor     ebx, ebx
0x180012ce4  cmp     rcx, rbp
0x180012ce7  jz      short loc_180012D03
0x180012ce9  test    byte ptr [rcx+1Ch], 8
0x180012ced  jz      short loc_180012D03
0x180012cef  mov     r9d, cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState; _SERVICE_STATUS g_ServiceStatus ...
0x180012cf6  mov     rcx, [rcx+10h]
0x180012cfa  mov     [rsp+38h+var_18], edi
0x180012cfe  call    WPP_SF_dd
0x180012d03  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, edi; _SERVICE_STATUS g_ServiceStatus ...
0x180012d09  mov     qword ptr cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, rbx; _SERVICE_STATUS g_ServiceStatus ...
0x180012d10  sub     edi, 2
0x180012d13  jz      short loc_180012D2B
0x180012d15  sub     edi, 1
0x180012d18  jz      short loc_180012D2B
0x180012d1a  cmp     edi, 1
0x180012d1d  jnz     short loc_180012D31
0x180012d1f  or      cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 401h; _SERVICE_STATUS g_ServiceStatus ...
0x180012d29  jmp     short loc_180012D31
0x180012d2b  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, ebx; _SERVICE_STATUS g_ServiceStatus ...
0x180012d31  mov     rcx, cs:?g_hService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180012d38  lea     rdx, ?g_ServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180012d3f  mov     qword ptr cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, rbx; _SERVICE_STATUS g_ServiceStatus ...
0x180012d46  call    cs:__imp_SetServiceStatus
0x180012d4c  test    eax, eax
0x180012d4e  jnz     short loc_180012D99
0x180012d50  call    cs:__imp_GetLastError
0x180012d56  mov     ebx, eax
0x180012d58  test    eax, eax
0x180012d5a  jle     short loc_180012D65
0x180012d5c  movzx   ebx, ax
0x180012d5f  or      ebx, 80070000h
0x180012d65  test    ebx, ebx
0x180012d67  mov     eax, 80004005h
0x180012d6c  cmovns  ebx, eax
0x180012d6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d76  cmp     rcx, rbp
0x180012d79  jz      short loc_180012DC0
0x180012d7b  test    byte ptr [rcx+1Ch], 2
0x180012d7f  jz      short loc_180012DA0
0x180012d81  mov     rcx, [rcx+10h]
0x180012d85  lea     r8, WPP_3f50365df99735211a88e8fb382b12e7_Traceguids
0x180012d8c  mov     edx, 0Ch
0x180012d91  mov     r9d, ebx
0x180012d94  call    WPP_SF_d
0x180012d99  mov     rcx, cs:WPP_GLOBAL_Control
0x180012da0  cmp     rcx, rbp
0x180012da3  jz      short loc_180012DC0
0x180012da5  test    byte ptr [rcx+1Ch], 20h
0x180012da9  jz      short loc_180012DC0
0x180012dab  mov     rcx, [rcx+10h]
0x180012daf  lea     r8, WPP_3f50365df99735211a88e8fb382b12e7_Traceguids
0x180012db6  mov     edx, 0Dh
0x180012dbb  call    WPP_SF_
0x180012dc0  mov     rbp, [rsp+38h+arg_8]
0x180012dc5  mov     eax, ebx
0x180012dc7  mov     rbx, [rsp+38h+arg_0]
0x180012dcc  add     rsp, 30h
0x180012dd0  pop     rdi
0x180012dd1  retn
```
