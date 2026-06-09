# TiCoreAnticipateShutdownProcessingNeeded

- ea: `0x14000c320`
- end: `0x14000c395`
- name: `TiCoreAnticipateShutdownProcessingNeeded`
- size: `117`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x14000bb04`
- `0x14000c830`

## callees

- `0x14000c320`
- `0x14000c92c`
- `0x140017658`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c361`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c361`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000c357`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000c357`

## string_xrefs

- `0x14000c377`: `Failed to set Trusted Installer status to accept preshutdown controls.`

## pseudocode

```c
void TiCoreAnticipateShutdownProcessingNeeded()
{
  signed int LastError; // eax
  bool v1; // sf

  if ( vhTiService )
  {
    SetAnticipateShutdownProcessingNeeded();
    *(_QWORD *)&vTiStatus.dwControlsAccepted = 320;
    *(_QWORD *)&vTiStatus.dwCheckPoint = 0;
    if ( !SetServiceStatus(vhTiService, &vTiStatus) )
    {
      LastError = GetLastError();
      v1 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v1 = LastError < 0;
      }
      if ( v1 )
        CBSWdsLogLight(
          0x4000000u,
          (unsigned int)LastError,
          (size_t *)1,
          "Failed to set Trusted Installer status to accept preshutdown controls.");
    }
  }
}

```

## disassembly

```asm
0x14000c320  sub     rsp, 28h
0x14000c324  cmp     cs:?vhTiService@@3PEAUSERVICE_STATUS_HANDLE__@@EA, 0; SERVICE_STATUS_HANDLE__ * vhTiService
0x14000c32c  jz      short loc_14000C390
0x14000c32e  call    SetAnticipateShutdownProcessingNeeded
0x14000c333  mov     rcx, cs:?vhTiService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x14000c33a  lea     rdx, ?vTiStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x14000c341  mov     qword ptr cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 140h; _SERVICE_STATUS vTiStatus ...
0x14000c34c  mov     qword ptr cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS vTiStatus ...
0x14000c357  call    cs:__imp_SetServiceStatus
0x14000c35d  test    eax, eax
0x14000c35f  jnz     short loc_14000C390
0x14000c361  call    cs:__imp_GetLastError
0x14000c367  test    eax, eax
0x14000c369  jle     short loc_14000C375
0x14000c36b  movzx   eax, ax
0x14000c36e  or      eax, 80070000h
0x14000c373  test    eax, eax
0x14000c375  jns     short loc_14000C390
0x14000c377  lea     r9, aFailedToSetTru_0; "Failed to set Trusted Installer status "...
0x14000c37e  mov     r8d, 1
0x14000c384  mov     edx, eax
0x14000c386  mov     ecx, 4000000h
0x14000c38b  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000c390  add     rsp, 28h
0x14000c394  retn
```
