# _dynamic_atexit_destructor_for__g_cache__

- ea: `0x180052d60`
- end: `0x180052ebb`
- name: `_dynamic_atexit_destructor_for__g_cache__`
- size: `347`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800065d0`
- `0x18000ae24`
- `0x180052d60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052e0d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052e1a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052e0d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052e1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052d8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052da9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052d8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052da9`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_cache__()
{
  qword_180070D10 = &CFolderItemCache::`vftable'{for `ISyncClientFolderItemCache'};
  qword_180070D18 = (__int64)&CFolderItemCache::`vftable'{for `ISyncMgrEvents'};
  if ( qword_180070D28 )
  {
    CloseHandle(qword_180070D28);
    qword_180070D28 = 0;
  }
  if ( pHandles )
  {
    CloseHandle(pHandles);
    pHandles = 0;
  }
  if ( hdpa )
  {
    DPA_DestroyCallback(hdpa, (PFNDAENUMCALLBACK)DPA_ReleaseCB<CCachedHandler>, 0);
    hdpa = 0;
  }
  if ( *(&hdpa + 1) )
  {
    DPA_DestroyCallback(*(&hdpa + 1), (PFNDAENUMCALLBACK)DPA_DeleteCB<CLegacyHandlerShim::_KEYEDPROGRESSVALUES>, 0);
    *(&hdpa + 1) = 0;
  }
  DeleteCriticalSection(&stru_180070D50);
  DeleteCriticalSection(&stru_180070D78);
  if ( qword_180070DA8 )
  {
    DPA_DestroyCallback(qword_180070DA8, (PFNDAENUMCALLBACK)DPA_DeleteCB<CUpdateRegistrationEntry>, 0);
    qword_180070DA8 = 0;
  }
  if ( *(&hdpa + 1) )
  {
    DPA_DestroyCallback(
      *(&hdpa + 1),
      CDPA_Base<CLegacyHandlerShim::_KEYEDPROGRESSVALUES,CTContainer_PolicyUnOwned<CLegacyHandlerShim::_KEYEDPROGRESSVALUES>>::_StandardDestroyCB,
      0);
    *(&hdpa + 1) = 0;
    DPA_Destroy(0);
    *(&hdpa + 1) = 0;
  }
  if ( hdpa )
  {
    DPA_DestroyCallback(
      hdpa,
      CDPA_Base<CLegacyHandlerShim::_KEYEDPROGRESSVALUES,CTContainer_PolicyUnOwned<CLegacyHandlerShim::_KEYEDPROGRESSVALUES>>::_StandardDestroyCB,
      0);
    hdpa = 0;
    DPA_Destroy(0);
    hdpa = 0;
  }
}

```

## disassembly

```asm
0x180052d60  sub     rsp, 28h
0x180052d64  mov     rcx, cs:qword_180070D28; hObject
0x180052d6b  lea     rax, ??_7CFolderItemCache@@6BISyncClientFolderItemCache@@@; const CFolderItemCache::`vftable'{for `ISyncClientFolderItemCache'}
0x180052d72  mov     cs:qword_180070D10, rax
0x180052d79  lea     rax, ??_7CFolderItemCache@@6BISyncMgrEvents@@@; const CFolderItemCache::`vftable'{for `ISyncMgrEvents'}
0x180052d80  mov     cs:qword_180070D18, rax
0x180052d87  test    rcx, rcx
0x180052d8a  jz      short loc_180052D9D
0x180052d8c  call    cs:__imp_CloseHandle
0x180052d92  mov     cs:qword_180070D28, 0
0x180052d9d  mov     rcx, cs:pHandles; hObject
0x180052da4  test    rcx, rcx
0x180052da7  jz      short loc_180052DBA
0x180052da9  call    cs:__imp_CloseHandle
0x180052daf  mov     cs:pHandles, 0
0x180052dba  mov     rcx, qword ptr cs:hdpa; hdpa
0x180052dc1  test    rcx, rcx
0x180052dc4  jz      short loc_180052DE0
0x180052dc6  xor     r8d, r8d; pData
0x180052dc9  lea     rdx, ??$DPA_ReleaseCB@VCCachedHandler@@@@YAHPEAVCCachedHandler@@PEAX@Z; pfnCB
0x180052dd0  call    DPA_DestroyCallback
0x180052dd5  mov     qword ptr cs:hdpa, 0
0x180052de0  mov     rcx, qword ptr cs:hdpa+8; hdpa
0x180052de7  test    rcx, rcx
0x180052dea  jz      short loc_180052E06
0x180052dec  xor     r8d, r8d; pData
0x180052def  lea     rdx, ??$DPA_DeleteCB@U_KEYEDPROGRESSVALUES@CLegacyHandlerShim@@@@YAHPEAU_KEYEDPROGRESSVALUES@CLegacyHandlerShim@@PEAX@Z; pfnCB
0x180052df6  call    DPA_DestroyCallback
0x180052dfb  mov     qword ptr cs:hdpa+8, 0
0x180052e06  lea     rcx, stru_180070D50; lpCriticalSection
0x180052e0d  call    cs:__imp_DeleteCriticalSection
0x180052e13  lea     rcx, stru_180070D78; lpCriticalSection
0x180052e1a  call    cs:__imp_DeleteCriticalSection
0x180052e20  mov     rcx, cs:qword_180070DA8; hdpa
0x180052e27  test    rcx, rcx
0x180052e2a  jz      short loc_180052E46
0x180052e2c  xor     r8d, r8d; pData
0x180052e2f  lea     rdx, ??$DPA_DeleteCB@VCUpdateRegistrationEntry@@@@YAHPEAVCUpdateRegistrationEntry@@PEAX@Z; pfnCB
0x180052e36  call    DPA_DestroyCallback
0x180052e3b  mov     cs:qword_180070DA8, 0
0x180052e46  mov     rcx, qword ptr cs:hdpa+8; hdpa
0x180052e4d  test    rcx, rcx
0x180052e50  jz      short loc_180052E7E
0x180052e52  xor     r8d, r8d; pData
0x180052e55  lea     rdx, ?_StandardDestroyCB@?$CDPA_Base@U_KEYEDPROGRESSVALUES@CLegacyHandlerShim@@V?$CTContainer_PolicyUnOwned@U_KEYEDPROGRESSVALUES@CLegacyHandlerShim@@@@@@CAHPEAU_KEYEDPROGRESSVALUES@CLegacyHandlerShim@@PEAX@Z; pfnCB
0x180052e5c  call    DPA_DestroyCallback
0x180052e61  xor     ecx, ecx; hdpa
0x180052e63  mov     qword ptr cs:hdpa+8, 0
0x180052e6e  call    DPA_Destroy
0x180052e73  mov     qword ptr cs:hdpa+8, 0
0x180052e7e  mov     rcx, qword ptr cs:hdpa; hdpa
0x180052e85  test    rcx, rcx
0x180052e88  jz      short loc_180052EB6
0x180052e8a  xor     r8d, r8d; pData
0x180052e8d  lea     rdx, ?_StandardDestroyCB@?$CDPA_Base@U_KEYEDPROGRESSVALUES@CLegacyHandlerShim@@V?$CTContainer_PolicyUnOwned@U_KEYEDPROGRESSVALUES@CLegacyHandlerShim@@@@@@CAHPEAU_KEYEDPROGRESSVALUES@CLegacyHandlerShim@@PEAX@Z; pfnCB
0x180052e94  call    DPA_DestroyCallback
0x180052e99  xor     ecx, ecx; hdpa
0x180052e9b  mov     qword ptr cs:hdpa, 0
0x180052ea6  call    DPA_Destroy
0x180052eab  mov     qword ptr cs:hdpa, 0
0x180052eb6  add     rsp, 28h
0x180052eba  retn
```
