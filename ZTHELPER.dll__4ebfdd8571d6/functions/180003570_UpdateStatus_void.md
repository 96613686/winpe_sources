# UpdateStatus(void)

- ea: `0x180003570`
- end: `0x18000366c`
- name: `?UpdateStatus@@YAKXZ`
- size: `252`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x180002b90`
- `0x180003150`
- `0x180003450`

## callees

- `0x180003570`
- `0x180015008`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000360e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000360e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003618`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003618`

## pseudocode

```c
__int64 UpdateStatus(void)
{
  SERVICE_STATUS_HANDLE v0; // rcx
  DWORD dwWin32ExitCode; // ebx
  DWORD LastError; // eax

  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 10, WPP_fd30cb189484364f2633d135959507bb_Traceguids, ServiceStatus.dwCurrentState);
  if ( ServiceStatus.dwCurrentState == 4 || ServiceStatus.dwCurrentState <= 1 || ServiceStatus.dwCurrentState >= 7 )
    ServiceStatus.dwCheckPoint = 0;
  else
    ++ServiceStatus.dwCheckPoint;
  v0 = ServiceStatusHandle;
  if ( ServiceStatusHandle )
  {
    dwWin32ExitCode = ServiceStatus.dwWin32ExitCode;
    if ( ServiceStatus.dwWin32ExitCode && (xmmword_18001F260 & 4) != 0 )
    {
      WPP_SF_d(1026, 11, WPP_fd30cb189484364f2633d135959507bb_Traceguids, ServiceStatus.dwWin32ExitCode);
      v0 = ServiceStatusHandle;
    }
    if ( !SetServiceStatus(v0, &ServiceStatus) )
    {
      LastError = GetLastError();
      dwWin32ExitCode = LastError;
      if ( (xmmword_18001F260 & 4) == 0 )
        return dwWin32ExitCode;
      WPP_SF_d(1026, 12, WPP_fd30cb189484364f2633d135959507bb_Traceguids, LastError);
    }
  }
  else
  {
    dwWin32ExitCode = 6;
  }
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 13, WPP_fd30cb189484364f2633d135959507bb_Traceguids, dwWin32ExitCode);
  return dwWin32ExitCode;
}

```

## disassembly

```asm
0x180003570  push    rbx
0x180003572  sub     rsp, 20h
0x180003576  test    byte ptr cs:xmmword_18001F260, 4
0x18000357d  jz      short loc_18000359C
0x18000357f  mov     r9d, cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState; _SERVICE_STATUS ServiceStatus ...
0x180003586  lea     r8, WPP_fd30cb189484364f2633d135959507bb_Traceguids
0x18000358d  mov     edx, 0Ah
0x180003592  mov     ecx, 402h
0x180003597  call    WPP_SF_d
0x18000359c  mov     eax, cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState; _SERVICE_STATUS ServiceStatus ...
0x1800035a2  cmp     eax, 4
0x1800035a5  jz      short loc_1800035B9
0x1800035a7  cmp     eax, 1
0x1800035aa  jbe     short loc_1800035B9
0x1800035ac  cmp     eax, 7
0x1800035af  jnb     short loc_1800035B9
0x1800035b1  inc     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint; _SERVICE_STATUS ServiceStatus ...
0x1800035b7  jmp     short loc_1800035C3
0x1800035b9  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS ServiceStatus ...
0x1800035c3  mov     rcx, cs:?ServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * ServiceStatusHandle
0x1800035ca  test    rcx, rcx
0x1800035cd  jnz     short loc_1800035D4
0x1800035cf  lea     ebx, [rcx+6]
0x1800035d2  jmp     short loc_180003642
0x1800035d4  mov     ebx, cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode; _SERVICE_STATUS ServiceStatus ...
0x1800035da  test    ebx, ebx
0x1800035dc  jz      short loc_180003607
0x1800035de  test    byte ptr cs:xmmword_18001F260, 4
0x1800035e5  jz      short loc_180003607
0x1800035e7  mov     edx, 0Bh
0x1800035ec  lea     r8, WPP_fd30cb189484364f2633d135959507bb_Traceguids
0x1800035f3  mov     ecx, 402h
0x1800035f8  mov     r9d, ebx
0x1800035fb  call    WPP_SF_d
0x180003600  mov     rcx, cs:?ServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180003607  lea     rdx, ?ServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x18000360e  call    cs:__imp_SetServiceStatus
0x180003614  test    eax, eax
0x180003616  jnz     short loc_180003642
0x180003618  call    cs:__imp_GetLastError
0x18000361e  mov     ebx, eax
0x180003620  test    byte ptr cs:xmmword_18001F260, 4
0x180003627  jz      short loc_180003664
0x180003629  mov     edx, 0Ch
0x18000362e  lea     r8, WPP_fd30cb189484364f2633d135959507bb_Traceguids
0x180003635  mov     ecx, 402h
0x18000363a  mov     r9d, eax
0x18000363d  call    WPP_SF_d
0x180003642  test    byte ptr cs:xmmword_18001F260, 4
0x180003649  jz      short loc_180003664
0x18000364b  mov     edx, 0Dh
0x180003650  lea     r8, WPP_fd30cb189484364f2633d135959507bb_Traceguids
0x180003657  mov     ecx, 402h
0x18000365c  mov     r9d, ebx
0x18000365f  call    WPP_SF_d
0x180003664  mov     eax, ebx
0x180003666  add     rsp, 20h
0x18000366a  pop     rbx
0x18000366b  retn
```
