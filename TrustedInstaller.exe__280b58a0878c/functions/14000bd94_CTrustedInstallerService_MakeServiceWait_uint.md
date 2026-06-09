# CTrustedInstallerService::MakeServiceWait(uint)

- ea: `0x14000bd94`
- end: `0x14000bdca`
- name: `?MakeServiceWait@CTrustedInstallerService@@UEAAJI@Z`
- size: `54`
- prototype: `__int64 __fastcall(CTrustedInstallerService *this, DWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x14000bd80`

## callees

- `0x14000bd94`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000bdbd`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000bdbd`

## pseudocode

```c
__int64 __fastcall CTrustedInstallerService::MakeServiceWait(CTrustedInstallerService *this, DWORD a2)
{
  if ( !*((_DWORD *)this - 4) && vhTiService )
  {
    ++vTiStatus.dwCheckPoint;
    vTiStatus.dwWaitHint = a2;
    SetServiceStatus(vhTiService, &vTiStatus);
  }
  return 0;
}

```

## disassembly

```asm
0x14000bd94  sub     rsp, 28h
0x14000bd98  cmp     dword ptr [rcx-10h], 0
0x14000bd9c  jnz     short loc_14000BDC3
0x14000bd9e  mov     rcx, cs:?vhTiService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x14000bda5  test    rcx, rcx
0x14000bda8  jz      short loc_14000BDC3
0x14000bdaa  inc     cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint; _SERVICE_STATUS vTiStatus ...
0x14000bdb0  mov     cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, edx; _SERVICE_STATUS vTiStatus ...
0x14000bdb6  lea     rdx, ?vTiStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x14000bdbd  call    cs:__imp_SetServiceStatus
0x14000bdc3  xor     eax, eax
0x14000bdc5  add     rsp, 28h
0x14000bdc9  retn
```
