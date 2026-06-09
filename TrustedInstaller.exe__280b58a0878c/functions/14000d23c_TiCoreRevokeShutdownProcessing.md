# TiCoreRevokeShutdownProcessing

- ea: `0x14000d23c`
- end: `0x14000d417`
- name: `TiCoreRevokeShutdownProcessing`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14000c304`

## callees

- `0x1400023e0`
- `0x140006e98`
- `0x140007630`
- `0x14000d23c`
- `0x14000d420`
- `0x140017658`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d2d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d3c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d2d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d3c6`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000d3bc`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000d3bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000d2ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000d2ba`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14000d334`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14000d334`

## string_xrefs

- `0x14000d2aa`: `Software\Microsoft\Windows\CurrentVersion\Component Based Servicing\ReservesRebootPending`
- `0x14000d32a`: `Software\Microsoft\Windows\CurrentVersion\Component Based Servicing\RebootPending`
- `0x14000d34b`: `Failed to delete RebootPending key.`
- `0x14000d3dc`: `Failed to set Trusted Installer status to accept preshutdown controls.`
- `0x14000d317`: `Unable to change Trusted Installer to demand-start service.`
- `0x14000d2f9`: `Not setting Trusted Installer to demand start because reserves are waiting on a reboot`

## pseudocode

```c
void __fastcall TiCoreRevokeShutdownProcessing(__int64 a1, HKEY a2)
{
  HKEY *phkResult; // rax
  LSTATUS v3; // eax
  signed int LastError; // eax
  const char *v5; // r9
  int v6; // eax
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  bool v9; // sf
  Windows::Detail *v10; // [rsp+30h] [rbp-18h] BYREF

  v10 = 0;
  if ( _InterlockedExchangeAdd(&vcRequireShutdownProcessing, 0xFFFFFFFF) == 1 && !vbRequireReboot )
  {
    vbRequireShutdownProcessing = 0;
    phkResult = (HKEY *)Windows::AutoComPtr<IClassFactory>::GetInitPointer(&v10);
    v3 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\ReservesRebootPending",
           0,
           1u,
           phkResult);
    if ( (unsigned int)(v3 - 2) <= 1 )
    {
      v6 = TiCoreSetTiDemandStart();
      if ( v6 < 0 )
        CBSWdsLogLight(
          0x4000000u,
          (unsigned int)v6,
          (size_t *)1,
          "Unable to change Trusted Installer to demand-start service.");
    }
    else
    {
      if ( v3 )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v5 = "Failed to check if reserves are waiting on a reboot";
        if ( LastError >= 0 )
          LastError = -2147467259;
        goto LABEL_26;
      }
      CBSWdsLogLight(
        0x4000000u,
        0,
        0,
        "Not setting Trusted Installer to demand start because reserves are waiting on a reboot");
    }
    v7 = RegDeleteKeyW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\RebootPending");
    v8 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      CBSWdsLogLight(0x4000000u, v8, (size_t *)1, "Failed to delete RebootPending key.");
      if ( (v8 & 0x80000000) != 0 )
        CBSWdsLogLight(0x4000000u, v8, (size_t *)1, "Unable to to unmark the pending reboot.");
    }
    else
    {
      CBSWdsLogLight(0x4000000u, 0, 0, "Reboot mark cleared");
    }
    if ( !vbAnticipateShutdownProcessingNeeded )
    {
      if ( vhTiService )
      {
        *(_QWORD *)&vTiStatus.dwControlsAccepted = 321;
        *(_QWORD *)&vTiStatus.dwCheckPoint = 0;
        if ( !SetServiceStatus(vhTiService, &vTiStatus) )
        {
          LastError = GetLastError();
          v9 = LastError < 0;
          if ( LastError > 0 )
          {
            LastError = (unsigned __int16)LastError | 0x80070000;
            v9 = LastError < 0;
          }
          if ( v9 )
          {
            v5 = "Failed to set Trusted Installer status to accept preshutdown controls.";
LABEL_26:
            CBSWdsLogLight(0x4000000u, (unsigned int)LastError, (size_t *)1, v5);
          }
        }
      }
    }
  }
  Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(
    &v10,
    a2);
}

```

## disassembly

```asm
0x14000d23c  mov     r11, rsp
0x14000d23f  mov     [r11+8], rbx
0x14000d243  mov     [r11+10h], rbp
0x14000d247  push    r14
0x14000d249  sub     rsp, 40h
0x14000d24d  mov     rax, cs:__security_cookie
0x14000d254  xor     rax, rsp
0x14000d257  mov     [rsp+48h+var_10], rax
0x14000d25c  mov     qword ptr [r11-18h], 0
0x14000d264  or      eax, 0FFFFFFFFh
0x14000d267  lock xadd cs:?vcRequireShutdownProcessing@@3JA, eax; long vcRequireShutdownProcessing
0x14000d26f  cmp     eax, 1
0x14000d272  jnz     loc_14000D3EF
0x14000d278  cmp     cs:?vbRequireReboot@@3HA, 0; int vbRequireReboot
0x14000d27f  jnz     loc_14000D3EF
0x14000d285  lea     rcx, [r11-18h]
0x14000d289  mov     cs:?vbRequireShutdownProcessing@@3HA, 0; int vbRequireShutdownProcessing
0x14000d293  call    ?GetInitPointer@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAPEAPEAUIClassFactory@@XZ; Windows::AutoComPtr<IClassFactory>::GetInitPointer(void)
0x14000d298  mov     r14d, 1
0x14000d29e  mov     [rsp+48h+phkResult], rax; phkResult
0x14000d2a3  mov     rbx, 0FFFFFFFF80000002h
0x14000d2aa  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14000d2b1  mov     r9d, r14d; samDesired
0x14000d2b4  mov     rcx, rbx; hKey
0x14000d2b7  xor     r8d, r8d; ulOptions
0x14000d2ba  call    cs:__imp_RegOpenKeyExW
0x14000d2c0  mov     ebp, 4000000h
0x14000d2c5  lea     ecx, [rax-2]
0x14000d2c8  cmp     ecx, r14d
0x14000d2cb  jbe     short loc_14000D30E
0x14000d2cd  test    eax, eax
0x14000d2cf  jz      short loc_14000D2F9
0x14000d2d1  call    cs:__imp_GetLastError
0x14000d2d7  test    eax, eax
0x14000d2d9  jle     short loc_14000D2E3
0x14000d2db  movzx   eax, ax
0x14000d2de  or      eax, 80070000h
0x14000d2e3  test    eax, eax
0x14000d2e5  lea     r9, aFailedToCheckI; "Failed to check if reserves are waiting"...
0x14000d2ec  mov     ecx, 80004005h
0x14000d2f1  cmovns  eax, ecx
0x14000d2f4  jmp     loc_14000D3E3
0x14000d2f9  lea     r9, aNotSettingTrus; "Not setting Trusted Installer to demand"...
0x14000d300  xor     r8d, r8d
0x14000d303  xor     edx, edx
0x14000d305  mov     ecx, ebp
0x14000d307  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d30c  jmp     short loc_14000D32A
0x14000d30e  call    TiCoreSetTiDemandStart
0x14000d313  test    eax, eax
0x14000d315  jns     short loc_14000D32A
0x14000d317  lea     r9, aUnableToChange; "Unable to change Trusted Installer to d"...
0x14000d31e  mov     r8d, r14d
0x14000d321  mov     edx, eax
0x14000d323  mov     ecx, ebp
0x14000d325  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d32a  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14000d331  mov     rcx, rbx; hKey
0x14000d334  call    cs:__imp_RegDeleteKeyW
0x14000d33a  mov     ebx, eax
0x14000d33c  test    eax, eax
0x14000d33e  jz      short loc_14000D377
0x14000d340  jle     short loc_14000D34B
0x14000d342  movzx   ebx, ax
0x14000d345  or      ebx, 80070000h
0x14000d34b  lea     r9, aFailedToDelete; "Failed to delete RebootPending key."
0x14000d352  mov     r8d, r14d
0x14000d355  mov     edx, ebx
0x14000d357  mov     ecx, ebp
0x14000d359  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d35e  test    ebx, ebx
0x14000d360  jns     short loc_14000D38A
0x14000d362  lea     r9, aUnableToToUnma; "Unable to to unmark the pending reboot."
0x14000d369  mov     r8d, r14d
0x14000d36c  mov     edx, ebx
0x14000d36e  mov     ecx, ebp
0x14000d370  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d375  jmp     short loc_14000D38A
0x14000d377  lea     r9, aRebootMarkClea; "Reboot mark cleared"
0x14000d37e  xor     r8d, r8d
0x14000d381  xor     edx, edx
0x14000d383  mov     ecx, ebp
0x14000d385  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d38a  cmp     cs:?vbAnticipateShutdownProcessingNeeded@@3HA, 0; int vbAnticipateShutdownProcessingNeeded
0x14000d391  jnz     short loc_14000D3EF
0x14000d393  mov     rcx, cs:?vhTiService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x14000d39a  test    rcx, rcx
0x14000d39d  jz      short loc_14000D3EF
0x14000d39f  lea     rdx, ?vTiStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x14000d3a6  mov     qword ptr cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 141h; _SERVICE_STATUS vTiStatus ...
0x14000d3b1  mov     qword ptr cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS vTiStatus ...
0x14000d3bc  call    cs:__imp_SetServiceStatus
0x14000d3c2  test    eax, eax
0x14000d3c4  jnz     short loc_14000D3EF
0x14000d3c6  call    cs:__imp_GetLastError
0x14000d3cc  test    eax, eax
0x14000d3ce  jle     short loc_14000D3DA
0x14000d3d0  movzx   eax, ax
0x14000d3d3  or      eax, 80070000h
0x14000d3d8  test    eax, eax
0x14000d3da  jns     short loc_14000D3EF
0x14000d3dc  lea     r9, aFailedToSetTru_0; "Failed to set Trusted Installer status "...
0x14000d3e3  mov     r8d, r14d
0x14000d3e6  mov     edx, eax
0x14000d3e8  mov     ecx, ebp
0x14000d3ea  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d3ef  lea     rcx, [rsp+48h+var_18]
0x14000d3f4  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
0x14000d3f9  mov     rcx, [rsp+48h+var_10]
0x14000d3fe  xor     rcx, rsp; StackCookie
0x14000d401  call    __security_check_cookie
0x14000d406  mov     rbx, [rsp+48h+arg_0]
0x14000d40b  mov     rbp, [rsp+48h+arg_8]
0x14000d410  add     rsp, 40h
0x14000d414  pop     r14
0x14000d416  retn
```
