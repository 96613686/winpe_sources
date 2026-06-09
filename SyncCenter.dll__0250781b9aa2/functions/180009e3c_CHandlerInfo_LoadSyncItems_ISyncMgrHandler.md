# CHandlerInfo::_LoadSyncItems(ISyncMgrHandler *)

- ea: `0x180009e3c`
- end: `0x18000a05b`
- name: `?_LoadSyncItems@CHandlerInfo@@AEAAJPEAUISyncMgrHandler@@@Z`
- size: `543`
- prototype: `__int64 __fastcall(CHandlerInfo *__hidden this, struct ISyncMgrHandler *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007964`

## callees

- `0x180004de0`
- `0x180007f44`
- `0x180008abc`
- `0x18000926c`
- `0x180009bb8`
- `0x180009e3c`
- `0x18000b5f0`
- `0x180010310`
- `0x180013ab0`
- `0x180016014`
- `0x1800196ec`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a030`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a030`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009fef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009fef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f58`

## pseudocode

```c
__int64 __fastcall CHandlerInfo::_LoadSyncItems(CHandlerInfo *this, struct ISyncMgrHandler *a2)
{
  struct ISyncMgrHandlerVtbl *lpVtbl; // rax
  int appended; // edi
  HDPA v5; // rbx
  int i; // r14d
  int v7; // eax
  struct ISyncMgrSyncItem *Ptr; // rax
  int *v9; // rax
  int v10; // edi
  int j; // ebx
  char *v12; // rax
  HDPA hdpa; // [rsp+30h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-18h] BYREF
  __int64 v16; // [rsp+40h] [rbp-10h] BYREF
  __int64 v17; // [rsp+48h] [rbp-8h] BYREF
  int v18; // [rsp+88h] [rbp+38h] BYREF
  __int64 v19; // [rsp+90h] [rbp+40h] BYREF
  __int64 v20; // [rsp+98h] [rbp+48h] BYREF

  lpVtbl = a2->lpVtbl;
  v17 = 0;
  appended = ((__int64 (__fastcall *)(struct ISyncMgrHandler *, GUID *, __int64 *))lpVtbl->QueryInterface)(
               a2,
               &GUID_90701133_be32_4129_a65c_99e616cafff4,
               &v17);
  if ( appended < 0 )
  {
    if ( appended == -2147467262 )
      return 0;
  }
  else
  {
    if ( v17 )
    {
      v16 = 0;
      appended = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 32LL))(v17, &v16);
      if ( appended >= 0 )
      {
        hdpa = 0;
        v20 = 0;
        if ( (unsigned int)CDPA_Base<ISyncClientFolderItem,CTContainer_PolicyUnOwned<ISyncClientFolderItem>>::Create(&hdpa) )
        {
          if ( (unsigned int)CDPA_Base<ISyncClientFolderItem,CTContainer_PolicyUnOwned<ISyncClientFolderItem>>::Create(&v20) )
          {
            v19 = 0;
            v18 = 0;
            while ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v16 + 24LL))(
                       v16,
                       1,
                       &v19,
                       &v18) )
            {
              appended = CDPA_Base<CHandlerCollectionInfo,CTContainer_PolicyUnOwned<CHandlerCollectionInfo>>::AppendPtr(
                           &hdpa,
                           v19);
              if ( appended >= 0 )
              {
                pv = 0;
                appended = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v19 + 24LL))(v19, &pv);
                if ( appended >= 0 )
                {
                  appended = CDPA_Base<CHandlerCollectionInfo,CTContainer_PolicyUnOwned<CHandlerCollectionInfo>>::AppendPtr(
                               &v20,
                               pv);
                  if ( appended < 0 )
                    CoTaskMemFree(pv);
                }
                v19 = 0;
              }
              SafeRelease<ISyncMgrSyncItemContainer>(&v19);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
            CHandlerInfo::_MarkItemsToBePurged(this);
            v5 = hdpa;
            for ( i = 0; ; ++i )
            {
              v7 = v5 ? *(_DWORD *)v5 : 0;
              if ( i >= v7 )
                break;
              Ptr = (struct ISyncMgrSyncItem *)DPA_GetPtr(v5, i);
              CHandlerInfo::_InitSyncItem(this, Ptr, 0);
            }
            CDPA<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>::DestroyCallback(&v20);
          }
          CDPA<ISyncMgrSyncItem,CTContainer_PolicyUnOwned<ISyncMgrSyncItem>>::DestroyCallback(&hdpa);
        }
        CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>::~CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>(&v20);
        CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>::~CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>((__int64 *)&hdpa);
      }
    }
    else
    {
      EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 1));
      v9 = (int *)*((_QWORD *)this + 254);
      if ( v9 )
      {
        v10 = *v9;
        for ( j = 0; j < v10; ++j )
        {
          v12 = (char *)DPA_GetPtr(*((HDPA *)this + 254), j);
          CItemState::MarkChangeState(v12 + 8, 5);
        }
      }
      LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 1));
      appended = 0;
    }
    SafeRelease<ISyncMgrSyncItemContainer>(&v17);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180009e3c  push    rbp
0x180009e3e  push    rbx
0x180009e3f  push    rsi
0x180009e40  push    rdi
0x180009e41  push    r14
0x180009e43  mov     rbp, rsp
0x180009e46  sub     rsp, 50h
0x180009e4a  mov     rax, [rdx]
0x180009e4d  lea     r8, [rbp+var_8]
0x180009e51  mov     r9, rdx
0x180009e54  mov     [rbp+var_8], 0
0x180009e5c  mov     rsi, rcx
0x180009e5f  lea     rdx, _GUID_90701133_be32_4129_a65c_99e616cafff4
0x180009e66  mov     rcx, r9
0x180009e69  mov     rax, [rax]
0x180009e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e71  mov     edi, eax
0x180009e73  test    eax, eax
0x180009e75  js      loc_18000A043
0x180009e7b  mov     rcx, [rbp+var_8]
0x180009e7f  test    rcx, rcx
0x180009e82  jz      loc_180009FEB
0x180009e88  mov     [rbp+var_10], 0
0x180009e90  lea     rdx, [rbp+var_10]
0x180009e94  mov     rax, [rcx]
0x180009e97  mov     rax, [rax+20h]
0x180009e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ea0  mov     edi, eax
0x180009ea2  test    eax, eax
0x180009ea4  js      loc_18000A038
0x180009eaa  lea     rcx, [rbp+hdpa]
0x180009eae  mov     [rbp+hdpa], 0
0x180009eb6  mov     [rbp+arg_18], 0
0x180009ebe  call    ?Create@?$CDPA_Base@UISyncClientFolderItem@@V?$CTContainer_PolicyUnOwned@UISyncClientFolderItem@@@@@@QEAAHH@Z; CDPA_Base<ISyncClientFolderItem,CTContainer_PolicyUnOwned<ISyncClientFolderItem>>::Create(int)
0x180009ec3  test    eax, eax
0x180009ec5  jz      loc_180009FD7
0x180009ecb  lea     rcx, [rbp+arg_18]
0x180009ecf  call    ?Create@?$CDPA_Base@UISyncClientFolderItem@@V?$CTContainer_PolicyUnOwned@UISyncClientFolderItem@@@@@@QEAAHH@Z; CDPA_Base<ISyncClientFolderItem,CTContainer_PolicyUnOwned<ISyncClientFolderItem>>::Create(int)
0x180009ed4  test    eax, eax
0x180009ed6  jz      loc_180009FCE
0x180009edc  mov     [rbp+arg_10], 0
0x180009ee4  mov     [rbp+arg_8], 0
0x180009eeb  mov     rcx, [rbp+var_10]
0x180009eef  lea     r9, [rbp+arg_8]
0x180009ef3  lea     r8, [rbp+arg_10]
0x180009ef7  mov     edx, 1
0x180009efc  mov     rax, [rcx]
0x180009eff  mov     rax, [rax+18h]
0x180009f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f08  test    eax, eax
0x180009f0a  jnz     short loc_180009F74
0x180009f0c  mov     rdx, [rbp+arg_10]
0x180009f10  lea     rcx, [rbp+hdpa]
0x180009f14  call    ?AppendPtr@?$CDPA_Base@VCHandlerCollectionInfo@@V?$CTContainer_PolicyUnOwned@VCHandlerCollectionInfo@@@@@@QEAAJPEAVCHandlerCollectionInfo@@PEAH@Z; CDPA_Base<CHandlerCollectionInfo,CTContainer_PolicyUnOwned<CHandlerCollectionInfo>>::AppendPtr(CHandlerCollectionInfo *,int *)
0x180009f19  mov     edi, eax
0x180009f1b  test    eax, eax
0x180009f1d  js      short loc_180009F66
0x180009f1f  mov     rcx, [rbp+arg_10]
0x180009f23  lea     rdx, [rbp+pv]
0x180009f27  mov     [rbp+pv], 0
0x180009f2f  mov     rax, [rcx]
0x180009f32  mov     rax, [rax+18h]
0x180009f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f3b  mov     edi, eax
0x180009f3d  test    eax, eax
0x180009f3f  js      short loc_180009F5E
0x180009f41  mov     rdx, [rbp+pv]
0x180009f45  lea     rcx, [rbp+arg_18]
0x180009f49  call    ?AppendPtr@?$CDPA_Base@VCHandlerCollectionInfo@@V?$CTContainer_PolicyUnOwned@VCHandlerCollectionInfo@@@@@@QEAAJPEAVCHandlerCollectionInfo@@PEAH@Z; CDPA_Base<CHandlerCollectionInfo,CTContainer_PolicyUnOwned<CHandlerCollectionInfo>>::AppendPtr(CHandlerCollectionInfo *,int *)
0x180009f4e  mov     edi, eax
0x180009f50  test    eax, eax
0x180009f52  jns     short loc_180009F5E
0x180009f54  mov     rcx, [rbp+pv]; pv
0x180009f58  call    cs:__imp_CoTaskMemFree
0x180009f5e  mov     [rbp+arg_10], 0
0x180009f66  lea     rcx, [rbp+arg_10]
0x180009f6a  call    ??$SafeRelease@UISyncMgrSyncItemContainer@@@@YAXPEAPEAUISyncMgrSyncItemContainer@@@Z; SafeRelease<ISyncMgrSyncItemContainer>(ISyncMgrSyncItemContainer * *)
0x180009f6f  jmp     loc_180009EEB
0x180009f74  mov     rcx, [rbp+var_10]
0x180009f78  mov     rax, [rcx]
0x180009f7b  mov     rax, [rax+10h]
0x180009f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f84  lea     rdx, [rbp+arg_18]
0x180009f88  mov     rcx, rsi; this
0x180009f8b  call    ?_MarkItemsToBePurged@CHandlerInfo@@AEAAXAEBV?$CDPA@GV?$CTContainer_PolicyUnOwned@G@@@@@Z; CHandlerInfo::_MarkItemsToBePurged(CDPA<ushort,CTContainer_PolicyUnOwned<ushort>> const &)
0x180009f90  mov     rbx, [rbp+hdpa]
0x180009f94  xor     r14d, r14d
0x180009f97  test    rbx, rbx
0x180009f9a  jz      short loc_180009FA0
0x180009f9c  mov     eax, [rbx]
0x180009f9e  jmp     short loc_180009FA2
0x180009fa0  xor     eax, eax
0x180009fa2  cmp     r14d, eax
0x180009fa5  jge     short loc_180009FC5
0x180009fa7  movsxd  rdx, r14d; i
0x180009faa  mov     rcx, rbx; hdpa
0x180009fad  call    DPA_GetPtr
0x180009fb2  xor     r8d, r8d; bool
0x180009fb5  mov     rdx, rax; struct ISyncMgrSyncItem *
0x180009fb8  mov     rcx, rsi; this
0x180009fbb  call    ?_InitSyncItem@CHandlerInfo@@AEAAJPEAUISyncMgrSyncItem@@_N@Z; CHandlerInfo::_InitSyncItem(ISyncMgrSyncItem *,bool)
0x180009fc0  inc     r14d
0x180009fc3  jmp     short loc_180009F97
0x180009fc5  lea     rcx, [rbp+arg_18]
0x180009fc9  call    ?DestroyCallback@?$CDPA@GV?$CTContainer_PolicyUnOwned@G@@@@QEAAXP6AHPEAGPEAX@Z1@Z; CDPA<ushort,CTContainer_PolicyUnOwned<ushort>>::DestroyCallback(int (*)(ushort *,void *),void *)
0x180009fce  lea     rcx, [rbp+hdpa]
0x180009fd2  call    ?DestroyCallback@?$CDPA@UISyncMgrSyncItem@@V?$CTContainer_PolicyUnOwned@UISyncMgrSyncItem@@@@@@QEAAXP6AHPEAUISyncMgrSyncItem@@PEAX@Z1@Z; CDPA<ISyncMgrSyncItem,CTContainer_PolicyUnOwned<ISyncMgrSyncItem>>::DestroyCallback(int (*)(ISyncMgrSyncItem *,void *),void *)
0x180009fd7  lea     rcx, [rbp+arg_18]
0x180009fdb  call    ??1?$CDPA_Base@VCSyncItemRequestState@@V?$CTContainer_PolicyUnOwned@VCSyncItemRequestState@@@@@@QEAA@XZ; CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>::~CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>(void)
0x180009fe0  lea     rcx, [rbp+hdpa]
0x180009fe4  call    ??1?$CDPA_Base@VCSyncItemRequestState@@V?$CTContainer_PolicyUnOwned@VCSyncItemRequestState@@@@@@QEAA@XZ; CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>::~CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>(void)
0x180009fe9  jmp     short loc_18000A038
0x180009feb  mov     rcx, [rsi+8]; lpCriticalSection
0x180009fef  call    cs:__imp_EnterCriticalSection
0x180009ff5  mov     rax, [rsi+7F0h]
0x180009ffc  test    rax, rax
0x180009fff  jz      short loc_18000A02C
0x18000a001  mov     edi, [rax]
0x18000a003  xor     ebx, ebx
0x18000a005  test    edi, edi
0x18000a007  jle     short loc_18000A02C
0x18000a009  mov     rcx, [rsi+7F0h]; hdpa
0x18000a010  movsxd  rdx, ebx; i
0x18000a013  call    DPA_GetPtr
0x18000a018  mov     edx, 5
0x18000a01d  lea     rcx, [rax+8]
0x18000a021  call    ?MarkChangeState@CItemState@@QEAAJW4SYNCMGR_INVALIDATE_REASON@@@Z; CItemState::MarkChangeState(SYNCMGR_INVALIDATE_REASON)
0x18000a026  inc     ebx
0x18000a028  cmp     ebx, edi
0x18000a02a  jl      short loc_18000A009
0x18000a02c  mov     rcx, [rsi+8]; lpCriticalSection
0x18000a030  call    cs:__imp_LeaveCriticalSection
0x18000a036  xor     edi, edi
0x18000a038  lea     rcx, [rbp+var_8]
0x18000a03c  call    ??$SafeRelease@UISyncMgrSyncItemContainer@@@@YAXPEAPEAUISyncMgrSyncItemContainer@@@Z; SafeRelease<ISyncMgrSyncItemContainer>(ISyncMgrSyncItemContainer * *)
0x18000a041  jmp     short loc_18000A04E
0x18000a043  xor     eax, eax
0x18000a045  cmp     edi, 80004002h
0x18000a04b  cmovz   edi, eax
0x18000a04e  mov     eax, edi
0x18000a050  add     rsp, 50h
0x18000a054  pop     r14
0x18000a056  pop     rdi
0x18000a057  pop     rsi
0x18000a058  pop     rbx
0x18000a059  pop     rbp
0x18000a05a  retn
```
