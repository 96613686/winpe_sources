# PimIMService::_EnsureIndexesUpToDate(void)

- ea: `0x18000b674`
- end: `0x18000b824`
- name: `?_EnsureIndexesUpToDate@PimIMService@@AEAAJXZ`
- size: `432`
- prototype: `__int64 __fastcall(HANDLE *this, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800082c4`

## callees

- `0x180002da8`
- `0x18000428c`
- `0x180006f48`
- `0x1800086a0`
- `0x180009778`
- `0x18000b674`
- `0x18000bb20`
- `0x18000c800`
- `0x18001087c`
- `0x18001122c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b79a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b7ea`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b79a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b7ea`

## string_xrefs

- `0x18000b730`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000b76a`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000b7a9`: `Contacts DB Ready`
- `0x18000b7d7`: `Indexing DB Ready`

## pseudocode

```c
__int64 __fastcall PimIMService::_EnsureIndexesUpToDate(HANDLE *this, __int64 a2)
{
  int IndexManager; // eax
  const unsigned __int16 *v4; // rdx
  HKEY v5; // rcx
  int v6; // ebx
  int v7; // ebp
  __int64 v8; // r9
  __int64 v9; // rcx
  int DWORD; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // ebx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  ESEDataSource *v17; // rcx
  unsigned int v19; // [rsp+58h] [rbp+10h] BYREF
  struct IndexedFiltering::IIndexManager *v20; // [rsp+60h] [rbp+18h] BYREF

  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(this, a2, "Ensure Indexing DB");
  v20 = 0;
  IndexManager = PimIMService::GetIndexManager((struct IndexedFiltering::IIndexManager **)this, 0, 1, &v20);
  v6 = 0;
  v7 = IndexManager;
  if ( IndexManager != -2147221203 )
    v6 = IndexManager;
  if ( v6 >= 0 )
  {
    v19 = 0;
    DWORD = RegistryGetDWORD(v5, v4, L"RebuildAllIndexes", &v19);
    if ( DWORD == -2147024894 )
    {
      v13 = 0;
    }
    else if ( DWORD < 0 || (v13 = 0, v19) )
    {
      v13 = 1;
LABEL_10:
      if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x80u) != 0 )
        McTemplateU0s_EventWriteTransfer(v12, v11, "Rebuilding Indexes");
      if ( v20 && !v13 )
        Log_AssertionEvent(
          v12,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
          922);
      ATL::CComPtrBase<IndexedFiltering::IIndexManager>::Release(&v20);
      v14 = PimIMService::GetIndexManager((struct IndexedFiltering::IIndexManager **)this, 1, 1, &v20);
      v6 = v14;
      if ( v14 < 0 )
      {
        v8 = 926;
LABEL_17:
        v9 = (unsigned int)v14;
        goto LABEL_18;
      }
      SetEvent(this[39]);
      if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x80u) != 0 )
        McTemplateU0s_EventWriteTransfer(v16, v15, "Contacts DB Ready");
      v14 = PimIMService::_RebuildContactIndexes((PimIMService *)this, 1);
      v6 = v14;
      if ( v14 < 0 )
      {
        v8 = 936;
        goto LABEL_17;
      }
LABEL_26:
      if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x80u) != 0 )
        McTemplateU0s_EventWriteTransfer(v12, v11, "Indexing DB Ready");
      SetEvent(this[39]);
      v14 = ESEDataSource::SetRebuildAllIndexesKey(v17, 0);
      v6 = v14;
      if ( v14 >= 0 )
      {
        v6 = 0;
        goto LABEL_31;
      }
      v8 = 949;
      goto LABEL_17;
    }
    if ( v7 != -2147221203 )
      goto LABEL_26;
    goto LABEL_10;
  }
  v8 = 910;
  v9 = (unsigned int)v6;
LABEL_18:
  Log_HREvent(
    v9,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
    v8);
LABEL_31:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v20);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000b674  mov     [rsp+arg_0], rbx
0x18000b679  push    rbp
0x18000b67a  push    rsi
0x18000b67b  push    r15
0x18000b67d  sub     rsp, 30h
0x18000b681  cmp     byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 0
0x18000b688  mov     rsi, rcx
0x18000b68b  jge     short loc_18000B699
0x18000b68d  lea     r8, aEnsureIndexing; "Ensure Indexing DB"
0x18000b694  call    McTemplateU0s_EventWriteTransfer
0x18000b699  mov     r15d, 1
0x18000b69f  mov     [rsp+48h+arg_10], 0
0x18000b6a8  mov     r8d, r15d; int
0x18000b6ab  lea     r9, [rsp+48h+arg_10]; struct IndexedFiltering::IIndexManager **
0x18000b6b0  xor     edx, edx; int
0x18000b6b2  mov     rcx, rsi; this
0x18000b6b5  call    ?GetIndexManager@PimIMService@@AEAAJHHPEAPEAUIIndexManager@IndexedFiltering@@@Z; PimIMService::GetIndexManager(int,int,IndexedFiltering::IIndexManager * *)
0x18000b6ba  xor     ebx, ebx
0x18000b6bc  mov     ebp, eax
0x18000b6be  cmp     eax, 8004012Dh
0x18000b6c3  cmovnz  ebx, eax
0x18000b6c6  test    ebx, ebx
0x18000b6c8  jns     short loc_18000B6D7
0x18000b6ca  mov     r9d, 38Eh
0x18000b6d0  mov     ecx, ebx
0x18000b6d2  jmp     loc_18000B767
0x18000b6d7  lea     r9, [rsp+48h+arg_8]; unsigned int *
0x18000b6dc  mov     [rsp+48h+arg_8], 0
0x18000b6e4  lea     r8, aRebuildallinde; "RebuildAllIndexes"
0x18000b6eb  call    ?RegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; RegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000b6f0  cmp     eax, 80070002h
0x18000b6f5  jnz     loc_18000B77B
0x18000b6fb  xor     ebx, ebx
0x18000b6fd  cmp     ebp, 8004012Dh
0x18000b703  jnz     loc_18000B7CE
0x18000b709  cmp     byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 0
0x18000b710  jge     short loc_18000B71E
0x18000b712  lea     r8, aRebuildingInde; "Rebuilding Indexes"
0x18000b719  call    McTemplateU0s_EventWriteTransfer
0x18000b71e  cmp     [rsp+48h+arg_10], 0
0x18000b724  jz      short loc_18000B73C
0x18000b726  test    ebx, ebx
0x18000b728  jnz     short loc_18000B73C
0x18000b72a  mov     r8d, 39Ah
0x18000b730  lea     rdx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000b737  call    Log_AssertionEvent
0x18000b73c  lea     rcx, [rsp+48h+arg_10]
0x18000b741  call    ?Release@?$CComPtrBase@UIIndexManager@IndexedFiltering@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IndexedFiltering::IIndexManager>::Release(void)
0x18000b746  lea     r9, [rsp+48h+arg_10]; struct IndexedFiltering::IIndexManager **
0x18000b74b  mov     r8d, r15d; int
0x18000b74e  mov     edx, r15d; int
0x18000b751  mov     rcx, rsi; this
0x18000b754  call    ?GetIndexManager@PimIMService@@AEAAJHHPEAPEAUIIndexManager@IndexedFiltering@@@Z; PimIMService::GetIndexManager(int,int,IndexedFiltering::IIndexManager * *)
0x18000b759  mov     ebx, eax
0x18000b75b  test    eax, eax
0x18000b75d  jns     short loc_18000B793
0x18000b75f  mov     r9d, 39Eh
0x18000b765  mov     ecx, eax
0x18000b767  mov     edx, r15d
0x18000b76a  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000b771  call    Log_HREvent
0x18000b776  jmp     loc_18000B80A
0x18000b77b  test    eax, eax
0x18000b77d  js      short loc_18000B78B
0x18000b77f  xor     ebx, ebx
0x18000b781  cmp     [rsp+48h+arg_8], ebx
0x18000b785  jz      loc_18000B6FD
0x18000b78b  mov     ebx, r15d
0x18000b78e  jmp     loc_18000B709
0x18000b793  mov     rcx, [rsi+138h]; hEvent
0x18000b79a  call    cs:__imp_SetEvent
0x18000b7a0  cmp     byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 0
0x18000b7a7  jge     short loc_18000B7B5
0x18000b7a9  lea     r8, aContactsDbRead; "Contacts DB Ready"
0x18000b7b0  call    McTemplateU0s_EventWriteTransfer
0x18000b7b5  mov     edx, r15d; int
0x18000b7b8  mov     rcx, rsi; this
0x18000b7bb  call    ?_RebuildContactIndexes@PimIMService@@AEAAJH@Z; PimIMService::_RebuildContactIndexes(int)
0x18000b7c0  mov     ebx, eax
0x18000b7c2  test    eax, eax
0x18000b7c4  jns     short loc_18000B7CE
0x18000b7c6  mov     r9d, 3A8h
0x18000b7cc  jmp     short loc_18000B765
0x18000b7ce  cmp     byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 0
0x18000b7d5  jge     short loc_18000B7E3
0x18000b7d7  lea     r8, aIndexingDbRead; "Indexing DB Ready"
0x18000b7de  call    McTemplateU0s_EventWriteTransfer
0x18000b7e3  mov     rcx, [rsi+138h]; hEvent
0x18000b7ea  call    cs:__imp_SetEvent
0x18000b7f0  xor     edx, edx; int
0x18000b7f2  call    ?SetRebuildAllIndexesKey@ESEDataSource@@QEAAJH@Z; ESEDataSource::SetRebuildAllIndexesKey(int)
0x18000b7f7  mov     ebx, eax
0x18000b7f9  test    eax, eax
0x18000b7fb  jns     short loc_18000B808
0x18000b7fd  mov     r9d, 3B5h
0x18000b803  jmp     loc_18000B765
0x18000b808  xor     ebx, ebx
0x18000b80a  lea     rcx, [rsp+48h+arg_10]
0x18000b80f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b814  mov     eax, ebx
0x18000b816  mov     rbx, [rsp+48h+arg_0]
0x18000b81b  add     rsp, 30h
0x18000b81f  pop     r15
0x18000b821  pop     rsi
0x18000b822  pop     rbp
0x18000b823  retn
```
