# ReportSvcStatus(ulong,ulong,ulong)

- ea: `0x180005ac0`
- end: `0x180005b76`
- name: `?ReportSvcStatus@@YAXKKK@Z`
- size: `182`
- prototype: `void __fastcall(unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180005b80`
- `0x180005bc4`
- `0x180006040`

## callees

- `0x180005ac0`
- `0x180006168`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b53`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005b2a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005b2a`

## pseudocode

```c
void __fastcall ReportSvcStatus(DWORD a1, DWORD a2, DWORD a3)
{
  DWORD LastError; // eax
  __int64 v4; // r8

  g_SvcStatus.dwCurrentState = a1;
  g_SvcStatus.dwWin32ExitCode = a2;
  g_SvcStatus.dwWaitHint = a3;
  if ( a1 == 2 )
  {
    g_SvcStatus.dwControlsAccepted = 0;
  }
  else
  {
    g_SvcStatus.dwControlsAccepted = 1;
    if ( a1 == 4 || a1 == 1 )
    {
      g_SvcStatus.dwCheckPoint = 0;
      goto LABEL_7;
    }
  }
  g_SvcStatus.dwCheckPoint = dword_18000E1F8++;
LABEL_7:
  if ( !SetServiceStatus(g_SvcStatusHandle, &g_SvcStatus)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xAu, v4, LastError);
  }
}

```

## disassembly

```asm
0x180005ac0  sub     rsp, 28h
0x180005ac4  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, ecx; _SERVICE_STATUS g_SvcStatus ...
0x180005aca  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, edx; _SERVICE_STATUS g_SvcStatus ...
0x180005ad0  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, r8d; _SERVICE_STATUS g_SvcStatus ...
0x180005ad7  cmp     ecx, 2
0x180005ada  jnz     short loc_180005AE8
0x180005adc  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 0; _SERVICE_STATUS g_SvcStatus ...
0x180005ae6  jmp     short loc_180005AFC
0x180005ae8  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 1; _SERVICE_STATUS g_SvcStatus ...
0x180005af2  cmp     ecx, 4
0x180005af5  jz      short loc_180005B12
0x180005af7  cmp     ecx, 1
0x180005afa  jz      short loc_180005B12
0x180005afc  mov     eax, cs:dword_18000E1F8
0x180005b02  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, eax; _SERVICE_STATUS g_SvcStatus ...
0x180005b08  inc     eax
0x180005b0a  mov     cs:dword_18000E1F8, eax
0x180005b10  jmp     short loc_180005B1C
0x180005b12  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_SvcStatus ...
0x180005b1c  mov     rcx, cs:?g_SvcStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180005b23  lea     rdx, ?g_SvcStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180005b2a  call    cs:__imp_SetServiceStatus
0x180005b30  test    eax, eax
0x180005b32  jnz     short loc_180005B71
0x180005b34  mov     rax, cs:WPP_GLOBAL_Control
0x180005b3b  lea     rcx, WPP_GLOBAL_Control
0x180005b42  cmp     rax, rcx
0x180005b45  jz      short loc_180005B71
0x180005b47  test    byte ptr [rax+1Ch], 80h
0x180005b4b  jz      short loc_180005B71
0x180005b4d  cmp     byte ptr [rax+19h], 2
0x180005b51  jb      short loc_180005B71
0x180005b53  call    cs:__imp_GetLastError
0x180005b59  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b60  mov     edx, 0Ah
0x180005b65  mov     r9d, eax
0x180005b68  mov     rcx, [rcx+10h]
0x180005b6c  call    WPP_SF_D
0x180005b71  add     rsp, 28h
0x180005b75  retn
```
