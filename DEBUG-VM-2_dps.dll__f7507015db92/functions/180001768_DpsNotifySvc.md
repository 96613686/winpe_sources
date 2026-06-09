# DpsNotifySvc

- ea: `0x180001768`
- end: `0x180001828`
- name: `DpsNotifySvc`
- size: `192`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180001e88`
- `0x18000aff0`
- `0x18000b0a0`
- `0x18000f2f4`

## callees

- `0x180001768`
- `0x180009090`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800017e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800017e0`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800017d2`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800017d2`

## pseudocode

```c
__int64 __fastcall DpsNotifySvc(char a1, DWORD a2, DWORD a3, DWORD a4, DWORD a5)
{
  signed int v5; // ebx
  signed int LastError; // eax
  char Args[4]; // [rsp+20h] [rbp-18h]

  if ( (a1 & 0x10) == 0 )
  {
    g_sSvcStatus.dwCurrentState = 0;
    *(_QWORD *)&g_sSvcStatus.dwCheckPoint = 0;
    g_sSvcStatus.dwWin32ExitCode = 0;
    if ( (a1 & 1) != 0 )
      g_sSvcStatus.dwCurrentState = a2;
    if ( (a1 & 2) != 0 )
      g_sSvcStatus.dwCheckPoint = a3;
    if ( (a1 & 4) != 0 )
      g_sSvcStatus.dwWaitHint = a4;
    if ( (a1 & 8) != 0 )
      g_sSvcStatus.dwWin32ExitCode = a5;
  }
  if ( SetServiceStatus(hServiceStatus, &g_sSvcStatus) )
  {
    return 0;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0 )
    {
      *(_DWORD *)Args = (unsigned __int16)v5;
      WdipTraceError(
        (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dps.cpp",
        (__int64)L"DpsNotifySvc",
        182,
        (const wchar_t *)L"Error = %d",
        *(_DWORD *)Args);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180001768  push    rbx
0x18000176a  sub     rsp, 30h
0x18000176e  test    cl, 10h
0x180001771  jnz     short loc_1800017C4
0x180001773  mov     cs:g_sSvcStatus.dwCurrentState, 0
0x18000177d  mov     qword ptr cs:g_sSvcStatus.dwCheckPoint, 0
0x180001788  mov     cs:g_sSvcStatus.dwWin32ExitCode, 0
0x180001792  test    cl, 1
0x180001795  jz      short loc_18000179D
0x180001797  mov     cs:g_sSvcStatus.dwCurrentState, edx
0x18000179d  test    cl, 2
0x1800017a0  jz      short loc_1800017A9
0x1800017a2  mov     cs:g_sSvcStatus.dwCheckPoint, r8d
0x1800017a9  test    cl, 4
0x1800017ac  jz      short loc_1800017B5
0x1800017ae  mov     cs:g_sSvcStatus.dwWaitHint, r9d
0x1800017b5  test    cl, 8
0x1800017b8  jz      short loc_1800017C4
0x1800017ba  mov     eax, [rsp+38h+arg_20]
0x1800017be  mov     cs:g_sSvcStatus.dwWin32ExitCode, eax
0x1800017c4  mov     rcx, cs:hServiceStatus; hServiceStatus
0x1800017cb  lea     rdx, g_sSvcStatus; lpServiceStatus
0x1800017d2  call    cs:__imp_SetServiceStatus
0x1800017d8  test    eax, eax
0x1800017da  jz      short loc_1800017E0
0x1800017dc  xor     ebx, ebx
0x1800017de  jmp     short loc_180001820
0x1800017e0  call    cs:__imp_GetLastError
0x1800017e6  mov     ebx, eax
0x1800017e8  test    eax, eax
0x1800017ea  jle     short loc_1800017F5
0x1800017ec  movzx   ebx, ax
0x1800017ef  or      ebx, 80070000h
0x1800017f5  test    ebx, ebx
0x1800017f7  jns     short loc_180001820
0x1800017f9  movzx   ecx, bx
0x1800017fc  lea     r9, aErrorD; "Error = %d"
0x180001803  mov     dword ptr [rsp+38h+Args], ecx; Args
0x180001807  lea     rdx, aDpsnotifysvc; "DpsNotifySvc"
0x18000180e  lea     rcx, aClientcoreBase_3; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180001815  mov     r8d, 0B6h; int
0x18000181b  call    WdipTraceError
0x180001820  mov     eax, ebx
0x180001822  add     rsp, 30h
0x180001826  pop     rbx
0x180001827  retn
```
