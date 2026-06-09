# TiCoreRequireShutdownProcessing

- ea: `0x14000d12c`
- end: `0x14000d233`
- name: `TiCoreRequireShutdownProcessing`
- size: `263`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140009b2c`
- `0x14000c284`
- `0x14000c2b4`
- `0x14000d5c8`

## callees

- `0x14000bdd0`
- `0x14000d12c`
- `0x140017658`
- `0x14001e19c`
- `0x14001e32c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d1ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d1ee`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000d1e4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000d1e4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000d227`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000d227`

## string_xrefs

- `0x14000d17d`: `Failed to change the Trusted Installer to an auto start service, hopefully the auto-start registry key is already set.`
- `0x14000d186`: `Failed to open TrustedInstaller service to change config, hopefully the auto-start registry key is already set.`
- `0x14000d204`: `Failed to set Trusted Installer status to accept preshutdown controls.`

## pseudocode

```c
void __fastcall TiCoreRequireShutdownProcessing(__int64 a1)
{
  int v1; // eax
  __int64 v2; // rdx
  int v3; // eax
  int v4; // eax
  signed int LastError; // eax
  bool v6; // sf
  SC_HANDLE hSCObject; // [rsp+70h] [rbp+8h] BYREF

  hSCObject = 0;
  if ( _InterlockedIncrement(&vcRequireShutdownProcessing) <= 1 )
  {
    vbRequireShutdownProcessing = 1;
    v1 = SvcOpen(a1, 2u, &hSCObject);
    if ( v1 < 0 )
    {
      CBSWdsLogLight(
        0x4000000u,
        (unsigned int)v1,
        (size_t *)1,
        "Failed to open TrustedInstaller service to change config, hopefully the auto-start registry key is already set.");
    }
    else
    {
      v3 = SvcChangeConfig(hSCObject, v2, 2);
      if ( v3 < 0 )
        CBSWdsLogLight(
          0x4000000u,
          (unsigned int)v3,
          (size_t *)1,
          "Failed to change the Trusted Installer to an auto start service, hopefully the auto-start registry key is already set.");
    }
    v4 = RebootMark::Mark();
    if ( v4 < 0 )
      CBSWdsLogLight(0x4000000u, (unsigned int)v4, (size_t *)1, "Unable to to mark the pending reboot.");
    if ( vhTiService )
    {
      *(_QWORD *)&vTiStatus.dwControlsAccepted = 256;
      *(_QWORD *)&vTiStatus.dwCheckPoint = 0;
      if ( !SetServiceStatus(vhTiService, &vTiStatus) )
      {
        LastError = GetLastError();
        v6 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v6 = LastError < 0;
        }
        if ( v6 )
          CBSWdsLogLight(
            0x4000000u,
            (unsigned int)LastError,
            (size_t *)1,
            "Failed to set Trusted Installer status to accept preshutdown controls.");
      }
    }
    if ( hSCObject )
      CloseServiceHandle(hSCObject);
  }
}

```

## disassembly

```asm
0x14000d12c  push    rsi
0x14000d12e  sub     rsp, 60h
0x14000d132  mov     esi, 1
0x14000d137  mov     [rsp+68h+hSCObject], 0
0x14000d140  mov     eax, esi
0x14000d142  lock xadd cs:?vcRequireShutdownProcessing@@3JA, eax; long vcRequireShutdownProcessing
0x14000d14a  add     eax, esi
0x14000d14c  cmp     eax, esi
0x14000d14e  jg      loc_14000D22D
0x14000d154  lea     r8, [rsp+68h+hSCObject]
0x14000d159  mov     cs:?vbRequireShutdownProcessing@@3HA, esi; int vbRequireShutdownProcessing
0x14000d15f  lea     edx, [rsi+1]
0x14000d162  call    SvcOpen
0x14000d167  test    eax, eax
0x14000d169  js      short loc_14000D186
0x14000d16b  mov     rcx, [rsp+68h+hSCObject]
0x14000d170  lea     r8d, [rsi+1]
0x14000d174  call    SvcChangeConfig
0x14000d179  test    eax, eax
0x14000d17b  jns     short loc_14000D19C
0x14000d17d  lea     r9, aFailedToChange; "Failed to change the Trusted Installer "...
0x14000d184  jmp     short loc_14000D18D
0x14000d186  lea     r9, aFailedToOpenTr; "Failed to open TrustedInstaller service"...
0x14000d18d  mov     r8d, esi
0x14000d190  mov     edx, eax
0x14000d192  mov     ecx, 4000000h
0x14000d197  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d19c  call    ?Mark@RebootMark@@SAJXZ; RebootMark::Mark(void)
0x14000d1a1  test    eax, eax
0x14000d1a3  jns     short loc_14000D1BB
0x14000d1a5  lea     r9, aUnableToToMark; "Unable to to mark the pending reboot."
0x14000d1ac  mov     r8d, esi
0x14000d1af  mov     edx, eax
0x14000d1b1  mov     ecx, 4000000h
0x14000d1b6  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d1bb  mov     rcx, cs:?vhTiService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x14000d1c2  test    rcx, rcx
0x14000d1c5  jz      short loc_14000D21A
0x14000d1c7  lea     rdx, ?vTiStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x14000d1ce  mov     qword ptr cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 100h; _SERVICE_STATUS vTiStatus ...
0x14000d1d9  mov     qword ptr cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS vTiStatus ...
0x14000d1e4  call    cs:__imp_SetServiceStatus
0x14000d1ea  test    eax, eax
0x14000d1ec  jnz     short loc_14000D21A
0x14000d1ee  call    cs:__imp_GetLastError
0x14000d1f4  test    eax, eax
0x14000d1f6  jle     short loc_14000D202
0x14000d1f8  movzx   eax, ax
0x14000d1fb  or      eax, 80070000h
0x14000d200  test    eax, eax
0x14000d202  jns     short loc_14000D21A
0x14000d204  lea     r9, aFailedToSetTru_0; "Failed to set Trusted Installer status "...
0x14000d20b  mov     r8d, esi
0x14000d20e  mov     edx, eax
0x14000d210  mov     ecx, 4000000h
0x14000d215  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d21a  cmp     [rsp+68h+hSCObject], 0
0x14000d220  jz      short loc_14000D22D
0x14000d222  mov     rcx, [rsp+68h+hSCObject]; hSCObject
0x14000d227  call    cs:__imp_CloseServiceHandle
0x14000d22d  add     rsp, 60h
0x14000d231  pop     rsi
0x14000d232  retn
```
