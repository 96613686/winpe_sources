# CONFIG_HISTORY::SnapshotConfigFilesWorkItem(void)

- ea: `0x180004014`
- end: `0x180004104`
- name: `?SnapshotConfigFilesWorkItem@CONFIG_HISTORY@@AEAAJXZ`
- size: `240`
- prototype: `__int64 __fastcall(CONFIG_HISTORY *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002da0`

## callees

- `0x180004014`
- `0x18000410c`
- `0x1800041e8`
- `0x1800048fc`
- `0x180004b0c`

## import_xrefs

- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180004038`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180004038`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800040f3`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800040f3`
- `iisutil!PuDbgPrintError` at `0x1800040e9`
- `iisutil!PuDbgPrintError` at `0x1800040e9`

## string_xrefs

- `0x1800040de`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\config_history.cxx`
- `0x18000405e`: `ValidateApphostConfig() failed. Snapshot avoided.\n`
- `0x1800040d2`: `CONFIG_HISTORY::SnapshotConfigFilesWorkItem`
- `0x18000408a`: `ValidateAdminConfig() failed. Snapshot avoided.\n`
- `0x1800040be`: `m_pConfigHistory->ScanHistoryDirectory () failed.\n`

## pseudocode

```c
__int64 __fastcall CONFIG_HISTORY::SnapshotConfigFilesWorkItem(CONFIG_HISTORY *this)
{
  __int32 v2; // esi
  int v4; // ebx
  CONFIG_HISTORY *v5; // rcx

  v2 = _InterlockedExchange((volatile __int32 *)this + 30, 0);
  if ( *((_DWORD *)this + 31) )
    return 0;
  v4 = 0;
  CReaderWriterLock3::WriteLock((CONFIG_HISTORY *)((char *)this + 24));
  if ( v2 )
  {
    v4 = CONFIG_HISTORY::ValidateApphostConfig(v5);
    if ( v4 >= 0 )
    {
      if ( *((_DWORD *)this + 12) && (v4 = CONFIG_HISTORY::ValidateAdminConfig(this), v4 < 0) )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\config_history.cxx",
            1625,
            "CONFIG_HISTORY::SnapshotConfigFilesWorkItem",
            v4,
            "ValidateAdminConfig() failed. Snapshot avoided.\n");
      }
      else
      {
        v4 = CONFIG_HISTORY_ENTITY::ScanHistoryDirectory(*((const unsigned __int16 ***)this + 5));
        if ( v4 < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\config_history.cxx",
              1651,
              "CONFIG_HISTORY::SnapshotConfigFilesWorkItem",
              v4,
              "m_pConfigHistory->ScanHistoryDirectory () failed.\n");
        }
        else
        {
          v4 = CONFIG_HISTORY_ENTITY::SnapshotConfig(*((const unsigned __int16 ***)this + 5));
        }
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\config_history.cxx",
        1611,
        "CONFIG_HISTORY::SnapshotConfigFilesWorkItem",
        v4,
        "ValidateApphostConfig() failed. Snapshot avoided.\n");
    }
  }
  CReaderWriterLock3::WriteUnlock((CONFIG_HISTORY *)((char *)this + 24));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180004014  push    rbx
0x180004016  push    rbp
0x180004017  push    rsi
0x180004018  push    rdi
0x180004019  sub     rsp, 38h
0x18000401d  xor     esi, esi
0x18000401f  mov     rdi, rcx
0x180004022  xchg    esi, [rcx+78h]
0x180004025  cmp     dword ptr [rcx+7Ch], 0
0x180004029  jz      short loc_180004032
0x18000402b  xor     eax, eax
0x18000402d  jmp     loc_1800040FB
0x180004032  add     rcx, 18h
0x180004036  xor     ebx, ebx
0x180004038  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000403e  test    esi, esi
0x180004040  jz      loc_1800040EF
0x180004046  call    ?ValidateApphostConfig@CONFIG_HISTORY@@AEAAJXZ; CONFIG_HISTORY::ValidateApphostConfig(void)
0x18000404b  mov     ebx, eax
0x18000404d  test    eax, eax
0x18000404f  jns     short loc_18000406D
0x180004051  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004058  jz      loc_1800040EF
0x18000405e  lea     rax, aValidateapphos; "ValidateApphostConfig() failed. Snapsho"...
0x180004065  mov     r8d, 64Bh
0x18000406b  jmp     short loc_1800040CB
0x18000406d  cmp     dword ptr [rdi+30h], 0
0x180004071  jz      short loc_180004099
0x180004073  mov     rcx, rdi; this
0x180004076  call    ?ValidateAdminConfig@CONFIG_HISTORY@@AEAAJXZ; CONFIG_HISTORY::ValidateAdminConfig(void)
0x18000407b  mov     ebx, eax
0x18000407d  test    eax, eax
0x18000407f  jns     short loc_180004099
0x180004081  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004088  jz      short loc_1800040EF
0x18000408a  lea     rax, aValidateadminc; "ValidateAdminConfig() failed. Snapshot "...
0x180004091  mov     r8d, 659h
0x180004097  jmp     short loc_1800040CB
0x180004099  mov     rcx, [rdi+28h]; this
0x18000409d  call    ?ScanHistoryDirectory@CONFIG_HISTORY_ENTITY@@QEAAJXZ; CONFIG_HISTORY_ENTITY::ScanHistoryDirectory(void)
0x1800040a2  mov     ebx, eax
0x1800040a4  test    eax, eax
0x1800040a6  js      short loc_1800040B5
0x1800040a8  mov     rcx, [rdi+28h]; this
0x1800040ac  call    ?SnapshotConfig@CONFIG_HISTORY_ENTITY@@QEAAJXZ; CONFIG_HISTORY_ENTITY::SnapshotConfig(void)
0x1800040b1  mov     ebx, eax
0x1800040b3  jmp     short loc_1800040EF
0x1800040b5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800040bc  jz      short loc_1800040EF
0x1800040be  lea     rax, aMPconfighistor; "m_pConfigHistory->ScanHistoryDirectory "...
0x1800040c5  mov     r8d, 673h
0x1800040cb  mov     rcx, cs:g_pDebug
0x1800040d2  lea     r9, aConfigHistoryS_1; "CONFIG_HISTORY::SnapshotConfigFilesWork"...
0x1800040d9  mov     [rsp+58h+var_30], rax
0x1800040de  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800040e5  mov     [rsp+58h+var_38], ebx
0x1800040e9  call    cs:__imp_PuDbgPrintError
0x1800040ef  lea     rcx, [rdi+18h]
0x1800040f3  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800040f9  mov     eax, ebx
0x1800040fb  add     rsp, 38h
0x1800040ff  pop     rdi
0x180004100  pop     rsi
0x180004101  pop     rbp
0x180004102  pop     rbx
0x180004103  retn
```
