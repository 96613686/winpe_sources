# PimIMService::AddSyncPartner(IPOSyncServices *,IPOutlookStoreCollection *,int,int &)

- ea: `0x180004c14`
- end: `0x180005024`
- name: `?AddSyncPartner@PimIMService@@AEAAJPEAUIPOSyncServices@@PEAUIPOutlookStoreCollection@@HAEAH@Z`
- size: `1040`
- prototype: `__int64 __fastcall(PimIMService *this, struct IPOSyncServices *, struct IPOutlookStoreCollection *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800058d0`

## callees

- `0x18000191c`
- `0x18000198c`
- `0x180002da8`
- `0x180003674`
- `0x180003ba0`
- `0x180003e00`
- `0x180003f90`
- `0x18000428c`
- `0x180004a54`
- `0x180004c14`
- `0x18000502c`
- `0x180007298`
- `0x18000b33c`
- `0x18000c51c`
- `0x18000c734`
- `0x180021240`
- `0x180022010`

## string_xrefs

- `0x180004cb8`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180004df9`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180004e4b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180004e9d`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180004efc`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180004fc8`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::AddSyncPartner(
        PimIMService *this,
        struct IPOSyncServices *a2,
        struct IPOutlookStoreCollection *a3,
        unsigned int a4,
        int *a5)
{
  __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // edi
  __int64 v10; // r9
  unsigned int v11; // edi
  _DWORD *v12; // rax
  __int64 v13; // rcx
  _QWORD *ThreadLocalStoragePointer; // rax
  int v15; // eax
  int v16; // esi
  __int64 v17; // rcx
  int TrackedStoresFromRegistry; // eax
  __int64 i; // rcx
  __int64 v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // r9
  struct IUnknown *v27; // [rsp+40h] [rbp-81h] BYREF
  unsigned int v28; // [rsp+48h] [rbp-79h] BYREF
  struct IUnknown *v29[2]; // [rsp+50h] [rbp-71h] BYREF
  __int64 v30; // [rsp+60h] [rbp-61h]
  int v31; // [rsp+68h] [rbp-59h]
  int v32; // [rsp+6Ch] [rbp-55h]
  __int64 v33; // [rsp+70h] [rbp-51h] BYREF
  __int64 v34; // [rsp+78h] [rbp-49h] BYREF
  _QWORD v35[3]; // [rsp+80h] [rbp-41h] BYREF
  __int64 v36; // [rsp+98h] [rbp-29h] BYREF
  const wchar_t *v37; // [rsp+A0h] [rbp-21h]
  __int64 v38; // [rsp+A8h] [rbp-19h]
  const wchar_t *v39; // [rsp+B0h] [rbp-11h]
  char v40[16]; // [rsp+B8h] [rbp-9h] BYREF
  __int64 v41; // [rsp+C8h] [rbp+7h] BYREF
  int v42; // [rsp+D0h] [rbp+Fh]

  v41 = 0;
  v42 = 0;
  v37 = 0;
  v39 = 0;
  v33 = 0;
  v7 = *(_QWORD *)a3;
  v34 = 0;
  v36 = 19;
  v38 = 65;
  v8 = (*(__int64 (__fastcall **)(struct IPOutlookStoreCollection *, _QWORD, __int64 *))(v7 + 96))(a3, a4, &v34);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 1396;
LABEL_5:
    Log_HREvent(
      (unsigned int)v8,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      v10);
    goto LABEL_43;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 56LL))(v34, &v41);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 1398;
    goto LABEL_5;
  }
  v11 = v41;
  v28 = v41;
  v12 = *(_DWORD **)utl::_HashTable<unsigned long,utl::pair<unsigned long const,SyncPartnerData>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,SyncPartnerData>>,0>::_FindFirst<utl::_HashTable<unsigned long,utl::pair<unsigned long const,SyncPartnerData>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,SyncPartnerData>>,0>::_FindFirstFind,unsigned long>(
                      (char *)this + 248,
                      &v27,
                      &v28);
  if ( (_DWORD *)((char *)this + 248) != v12 )
  {
    v12[14] = 1;
    v9 = 1;
    goto LABEL_43;
  }
  v13 = (unsigned int)tls_index;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v27 = 0;
  if ( dword_18002E008 > *(_DWORD *)(ThreadLocalStoragePointer[tls_index] + 4LL) )
  {
    Init_thread_header(&dword_18002E008);
    if ( dword_18002E008 == -1 )
    {
      (*(void (__fastcall **)(PimIMService *, __int64 *))(*(_QWORD *)this + 200LL))(this, qword_18002E010);
      Init_thread_footer(&dword_18002E008);
    }
  }
  v30 = 0;
  *(_OWORD *)v29 = 0;
  v31 = 1;
  v32 = -1;
  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x10) != 0 )
    McTemplateU0q_EventWriteTransfer(v13, PIMIndex_AddSyncPartner_AddingPartner, v11);
  if ( (*(int (__fastcall **)(struct IPOSyncServices *, _QWORD, __int64 *, struct IUnknown **))(*(_QWORD *)a2 + 96LL))(
         a2,
         v11,
         qword_18002E010,
         &v27) < 0 )
  {
    v15 = (*(__int64 (__fastcall **)(struct IPOSyncServices *, _QWORD, __int64 *, const wchar_t *, __int64 *, struct IUnknown **))(*(_QWORD *)a2 + 88LL))(
            a2,
            v11,
            qword_18002E010,
            L"PimIndexMaintenancePartner",
            qword_1800269C0,
            &v27);
    v16 = v15;
    if ( v15 < 0 )
    {
      Log_HREvent(
        (unsigned int)v15,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        1429);
LABEL_15:
      SyncPartnerData::~SyncPartnerData((SyncPartnerData *)v29);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v27);
      v9 = v16;
      goto LABEL_43;
    }
  }
  if ( v27 )
  {
    utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(v35);
    TrackedStoresFromRegistry = PimIMService::GetTrackedStoresFromRegistry(v17, v35);
    if ( TrackedStoresFromRegistry < 0 )
      Log_HREvent(
        (unsigned int)TrackedStoresFromRegistry,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        1437);
    for ( i = 0; (unsigned int)i < (unsigned __int64)((__int64)(v35[1] - v35[0]) >> 2); i = (unsigned int)(i + 1) )
    {
      if ( *(_DWORD *)(v35[0] + 4 * i) == v11 )
        goto LABEL_30;
    }
    if ( !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::_PushBackOne<unsigned long const &>(
                             v35,
                             &v28) )
    {
      v21 = 1451;
LABEL_25:
      v9 = -2147024882;
      v22 = 0;
      v23 = 2147942414LL;
LABEL_26:
      Log_HREvent(
        v23,
        v22,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        v21);
      utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit((__int64)v35);
      goto LABEL_41;
    }
    v24 = PimIMService::WriteTrackedStoresToRegistry(v20, v35);
    v9 = v24;
    if ( v24 < 0 )
    {
      v21 = 1452;
      v22 = 1;
      v23 = (unsigned int)v24;
      goto LABEL_26;
    }
    v11 = v28;
    *a5 = 1;
LABEL_30:
    v16 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v27->lpVtbl[7].AddRef)(v27, &v29[1]);
    if ( v16 >= 0 )
    {
      v37 = L"PIMIMAggregateId";
      v39 = L"PIMIMProcessedObjectVersion";
      v16 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64 *, __int64 *))v29[1]->lpVtbl[1].QueryInterface)(
              v29[1],
              2,
              &v36,
              &v33);
      if ( v16 >= 0 )
      {
        v30 = v33;
        v32 = v11;
        if ( v29[0] != v27 )
          ATL::AtlComPtrAssign(v29, v27);
        if ( *(_QWORD *)utl::_HashTable<unsigned long,utl::pair<unsigned long const,SyncPartnerData>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,SyncPartnerData>>,0>::emplace<unsigned long &,SyncPartnerData &,0>(
                          (char *)this + 248,
                          v40,
                          &v28,
                          v29) )
        {
          utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit((__int64)v35);
          SyncPartnerData::~SyncPartnerData((SyncPartnerData *)v29);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v27);
          v9 = 0;
          goto LABEL_43;
        }
        v21 = 1470;
        goto LABEL_25;
      }
      v25 = 1462;
    }
    else
    {
      v25 = 1457;
    }
    Log_HREvent(
      (unsigned int)v16,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      v25);
    utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit((__int64)v35);
    goto LABEL_15;
  }
  v9 = -2147467259;
  Log_HREvent(
    2147500037LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
    1431);
LABEL_41:
  SyncPartnerData::~SyncPartnerData((SyncPartnerData *)v29);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v27);
LABEL_43:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
  return v9;
}

```

## disassembly

```asm
0x180004c14  push    rbp
0x180004c16  push    rbx
0x180004c17  push    rsi
0x180004c18  push    rdi
0x180004c19  push    r14
0x180004c1b  push    r15
0x180004c1d  lea     rbp, [rsp-27h]
0x180004c22  sub     rsp, 0E8h
0x180004c29  mov     rax, cs:__security_cookie
0x180004c30  xor     rax, rsp
0x180004c33  mov     [rbp+4Fh+var_38], rax
0x180004c37  mov     r15, [rbp+4Fh+arg_20]
0x180004c3b  xor     eax, eax
0x180004c3d  mov     [rbp+4Fh+var_48], rax
0x180004c41  mov     r10d, r9d
0x180004c44  mov     [rbp+4Fh+var_40], eax
0x180004c47  mov     r9, r8
0x180004c4a  mov     [rbp+4Fh+var_70], rax
0x180004c4e  mov     rsi, rdx
0x180004c51  mov     [rbp+4Fh+var_60], rax
0x180004c55  mov     rbx, rcx
0x180004c58  mov     [rbp+4Fh+var_A0], rax
0x180004c5c  mov     edx, r10d
0x180004c5f  mov     rax, [r8]
0x180004c62  mov     rcx, r9
0x180004c65  lea     r8, [rbp+4Fh+var_98]
0x180004c69  mov     [rbp+4Fh+var_98], 0
0x180004c71  mov     [rbp+4Fh+var_78], 13h
0x180004c79  mov     [rbp+4Fh+var_68], 41h ; 'A'
0x180004c81  mov     rax, [rax+60h]
0x180004c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c8a  mov     edi, eax
0x180004c8c  test    eax, eax
0x180004c8e  jns     short loc_180004C98
0x180004c90  mov     r9d, 574h
0x180004c96  jmp     short loc_180004CB8
0x180004c98  mov     rcx, [rbp+4Fh+var_98]
0x180004c9c  lea     rdx, [rbp+4Fh+var_48]
0x180004ca0  mov     rax, [rcx]
0x180004ca3  mov     rax, [rax+38h]
0x180004ca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cac  mov     edi, eax
0x180004cae  test    eax, eax
0x180004cb0  jns     short loc_180004CD0
0x180004cb2  mov     r9d, 576h
0x180004cb8  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180004cbf  mov     edx, 1
0x180004cc4  mov     ecx, eax
0x180004cc6  call    Log_HREvent
0x180004ccb  jmp     loc_180004FFD
0x180004cd0  mov     edi, dword ptr [rbp+4Fh+var_48]
0x180004cd3  lea     r14, [rbx+0F8h]
0x180004cda  mov     rcx, r14
0x180004cdd  mov     [rbp+4Fh+var_C8], edi
0x180004ce0  lea     r8, [rbp+4Fh+var_C8]
0x180004ce4  lea     rdx, [rsp+110h+var_D0]
0x180004ce9  call    ??$_FindFirst@U_FindFirstFind@?$_HashTable@KU?$pair@$$CBKUSyncPartnerData@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKUSyncPartnerData@@@utl@@@2@$0A@@utl@@K@?$_HashTable@KU?$pair@$$CBKUSyncPartnerData@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKUSyncPartnerData@@@utl@@@2@$0A@@utl@@AEBA?AU_FindFirstFind@01@AEBK@Z; utl::_HashTable<ulong,utl::pair<ulong const,SyncPartnerData>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,SyncPartnerData>>,0>::_FindFirst<utl::_HashTable<ulong,utl::pair<ulong const,SyncPartnerData>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,SyncPartnerData>>,0>::_FindFirstFind,ulong>(ulong const &)
0x180004cee  mov     rax, [rax]
0x180004cf1  cmp     r14, rax
0x180004cf4  jnz     loc_180004FF3
0x180004cfa  mov     ecx, cs:_tls_index
0x180004d00  mov     rax, gs:58h
0x180004d09  mov     edx, 4
0x180004d0e  mov     [rsp+110h+var_D0], 0
0x180004d17  mov     rax, [rax+rcx*8]
0x180004d1b  mov     eax, [rdx+rax]
0x180004d1e  cmp     cs:dword_18002E008, eax
0x180004d24  jle     short loc_180004D60
0x180004d26  lea     rcx, dword_18002E008
0x180004d2d  call    _Init_thread_header
0x180004d32  cmp     cs:dword_18002E008, 0FFFFFFFFh
0x180004d39  jnz     short loc_180004D60
0x180004d3b  mov     rax, [rbx]
0x180004d3e  lea     rdx, qword_18002E010
0x180004d45  mov     rcx, rbx
0x180004d48  mov     rax, [rax+0C8h]
0x180004d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d54  lea     rcx, dword_18002E008
0x180004d5b  call    _Init_thread_footer
0x180004d60  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 10h
0x180004d67  xorps   xmm0, xmm0
0x180004d6a  mov     ebx, 1
0x180004d6f  mov     [rbp+4Fh+var_B0], 0
0x180004d77  movdqu  xmmword ptr [rbp+4Fh+var_C0], xmm0
0x180004d7c  mov     [rbp+4Fh+var_A8], ebx
0x180004d7f  mov     [rbp+4Fh+var_A4], 0FFFFFFFFh
0x180004d86  jz      short loc_180004D97
0x180004d88  mov     r8d, edi
0x180004d8b  lea     rdx, PIMIndex_AddSyncPartner_AddingPartner
0x180004d92  call    McTemplateU0q_EventWriteTransfer
0x180004d97  mov     rax, [rsi]
0x180004d9a  lea     r9, [rsp+110h+var_D0]
0x180004d9f  lea     r8, qword_18002E010
0x180004da6  mov     edx, edi
0x180004da8  mov     rcx, rsi
0x180004dab  mov     rax, [rax+60h]
0x180004daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004db4  test    eax, eax
0x180004db6  jns     short loc_180004E23
0x180004db8  mov     rax, [rsi]
0x180004dbb  lea     rcx, [rsp+110h+var_D0]
0x180004dc0  mov     [rsp+110h+var_E8], rcx
0x180004dc5  lea     r9, aPimindexmainte_0; "PimIndexMaintenancePartner"
0x180004dcc  lea     rcx, qword_1800269C0
0x180004dd3  mov     edx, edi
0x180004dd5  mov     [rsp+110h+var_F0], rcx
0x180004dda  lea     r8, qword_18002E010
0x180004de1  mov     rax, [rax+58h]
0x180004de5  mov     rcx, rsi
0x180004de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ded  mov     esi, eax
0x180004def  test    eax, eax
0x180004df1  jns     short loc_180004E23
0x180004df3  mov     r9d, 595h
0x180004df9  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180004e00  mov     edx, ebx
0x180004e02  mov     ecx, eax
0x180004e04  call    Log_HREvent
0x180004e09  lea     rcx, [rbp+4Fh+var_C0]; this
0x180004e0d  call    ??1SyncPartnerData@@QEAA@XZ; SyncPartnerData::~SyncPartnerData(void)
0x180004e12  lea     rcx, [rsp+110h+var_D0]
0x180004e17  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004e1c  mov     edi, esi
0x180004e1e  jmp     loc_180004FFD
0x180004e23  cmp     [rsp+110h+var_D0], 0
0x180004e29  jz      loc_180004FC3
0x180004e2f  lea     rcx, [rbp+4Fh+var_90]
0x180004e33  call    ??0?$vector@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(void)
0x180004e38  lea     rdx, [rbp+4Fh+var_90]
0x180004e3c  call    ?GetTrackedStoresFromRegistry@PimIMService@@QEAAJAEAV?$vector@KV?$allocator@K@utl@@@utl@@@Z; PimIMService::GetTrackedStoresFromRegistry(utl::vector<ulong,utl::allocator<ulong>> &)
0x180004e41  test    eax, eax
0x180004e43  jns     short loc_180004E5B
0x180004e45  mov     r9d, 59Dh
0x180004e4b  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180004e52  xor     edx, edx
0x180004e54  mov     ecx, eax
0x180004e56  call    Log_HREvent
0x180004e5b  mov     rdx, [rbp+4Fh+var_90]
0x180004e5f  xor     ecx, ecx
0x180004e61  mov     rax, [rbp+4Fh+var_88]
0x180004e65  sub     rax, rdx
0x180004e68  mov     r8d, ecx
0x180004e6b  sar     rax, 2
0x180004e6f  cmp     r8, rax
0x180004e72  jnb     short loc_180004E7D
0x180004e74  cmp     [rdx+rcx*4], edi
0x180004e77  jz      short loc_180004ED8
0x180004e79  add     ecx, ebx
0x180004e7b  jmp     short loc_180004E61
0x180004e7d  lea     rdx, [rbp+4Fh+var_C8]
0x180004e81  lea     rcx, [rbp+4Fh+var_90]
0x180004e85  call    ??$_PushBackOne@AEBK@?$vector@KV?$allocator@K@utl@@@utl@@AEAA_NAEBK@Z; utl::vector<ulong,utl::allocator<ulong>>::_PushBackOne<ulong const &>(ulong const &)
0x180004e8a  test    al, al
0x180004e8c  jnz     short loc_180004EB7
0x180004e8e  mov     r9d, 5ABh
0x180004e94  mov     edi, 8007000Eh
0x180004e99  xor     edx, edx
0x180004e9b  mov     ecx, edi
0x180004e9d  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180004ea4  call    Log_HREvent
0x180004ea9  lea     rcx, [rbp+4Fh+var_90]
0x180004ead  call    ?_Uninit@?$vector@URunOnToken@IndexedFiltering@@V?$allocator@URunOnToken@IndexedFiltering@@@utl@@@utl@@AEAAXXZ; utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(void)
0x180004eb2  jmp     loc_180004FDE
0x180004eb7  lea     rdx, [rbp+4Fh+var_90]
0x180004ebb  call    ?WriteTrackedStoresToRegistry@PimIMService@@QEAAJAEBV?$vector@KV?$allocator@K@utl@@@utl@@@Z; PimIMService::WriteTrackedStoresToRegistry(utl::vector<ulong,utl::allocator<ulong>> const &)
0x180004ec0  mov     edi, eax
0x180004ec2  test    eax, eax
0x180004ec4  jns     short loc_180004ED2
0x180004ec6  mov     r9d, 5ACh
0x180004ecc  mov     edx, ebx
0x180004ece  mov     ecx, eax
0x180004ed0  jmp     short loc_180004E9D
0x180004ed2  mov     edi, [rbp+4Fh+var_C8]
0x180004ed5  mov     [r15], ebx
0x180004ed8  mov     rcx, [rsp+110h+var_D0]
0x180004edd  lea     rdx, [rbp+4Fh+var_C0+8]
0x180004ee1  mov     rax, [rcx]
0x180004ee4  mov     rax, [rax+0B0h]
0x180004eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ef0  mov     esi, eax
0x180004ef2  test    eax, eax
0x180004ef4  jns     short loc_180004F1A
0x180004ef6  mov     r9d, 5B1h
0x180004efc  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180004f03  mov     edx, ebx
0x180004f05  mov     ecx, esi
0x180004f07  call    Log_HREvent
0x180004f0c  lea     rcx, [rbp+4Fh+var_90]
0x180004f10  call    ?_Uninit@?$vector@URunOnToken@IndexedFiltering@@V?$allocator@URunOnToken@IndexedFiltering@@@utl@@@utl@@AEAAXXZ; utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(void)
0x180004f15  jmp     loc_180004E09
0x180004f1a  mov     rcx, [rbp+4Fh+var_C0+8]
0x180004f1e  lea     rax, aPimimaggregate; "PIMIMAggregateId"
0x180004f25  mov     [rbp+4Fh+var_70], rax
0x180004f29  lea     r9, [rbp+4Fh+var_A0]
0x180004f2d  lea     rax, aPimimprocessed; "PIMIMProcessedObjectVersion"
0x180004f34  mov     edx, 2
0x180004f39  mov     [rbp+4Fh+var_60], rax
0x180004f3d  lea     r8, [rbp+4Fh+var_78]
0x180004f41  mov     rax, [rcx]
0x180004f44  mov     rax, [rax+18h]
0x180004f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f4d  mov     esi, eax
0x180004f4f  test    eax, eax
0x180004f51  jns     short loc_180004F5B
0x180004f53  mov     r9d, 5B6h
0x180004f59  jmp     short loc_180004EFC
0x180004f5b  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x180004f5e  mov     rdx, [rsp+110h+var_D0]; struct IUnknown *
0x180004f63  mov     dword ptr [rbp+4Fh+var_B0], eax
0x180004f66  mov     eax, dword ptr [rbp+4Fh+var_A0+4]
0x180004f69  mov     dword ptr [rbp+4Fh+var_B0+4], eax
0x180004f6c  mov     [rbp+4Fh+var_A4], edi
0x180004f6f  cmp     [rbp+4Fh+var_C0], rdx
0x180004f73  jz      short loc_180004F7E
0x180004f75  lea     rcx, [rbp+4Fh+var_C0]; struct IUnknown **
0x180004f79  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180004f7e  lea     r9, [rbp+4Fh+var_C0]
0x180004f82  mov     rcx, r14
0x180004f85  lea     r8, [rbp+4Fh+var_C8]
0x180004f89  lea     rdx, [rbp+4Fh+var_58]
0x180004f8d  call    ??$emplace@AEAKAEAUSyncPartnerData@@$0A@@?$_HashTable@KU?$pair@$$CBKUSyncPartnerData@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKUSyncPartnerData@@@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_DlistIt@U?$_HashNode@U?$pair@$$CBKUSyncPartnerData@@@utl@@@utl@@U?$pair@$$CBKUSyncPartnerData@@@2@@utl@@_N@1@AEAKAEAUSyncPartnerData@@@Z; utl::_HashTable<ulong,utl::pair<ulong const,SyncPartnerData>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,SyncPartnerData>>,0>::emplace<ulong &,SyncPartnerData &,0>(ulong &,SyncPartnerData &)
0x180004f92  cmp     qword ptr [rax], 0
0x180004f96  jz      short loc_180004FB8
0x180004f98  lea     rcx, [rbp+4Fh+var_90]
0x180004f9c  call    ?_Uninit@?$vector@URunOnToken@IndexedFiltering@@V?$allocator@URunOnToken@IndexedFiltering@@@utl@@@utl@@AEAAXXZ; utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(void)
0x180004fa1  lea     rcx, [rbp+4Fh+var_C0]; this
0x180004fa5  call    ??1SyncPartnerData@@QEAA@XZ; SyncPartnerData::~SyncPartnerData(void)
0x180004faa  lea     rcx, [rsp+110h+var_D0]
0x180004faf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004fb4  xor     edi, edi
0x180004fb6  jmp     short loc_180004FFD
0x180004fb8  mov     r9d, 5BEh
0x180004fbe  jmp     loc_180004E94
0x180004fc3  mov     edi, 80004005h
0x180004fc8  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180004fcf  mov     ecx, edi
0x180004fd1  mov     r9d, 597h
0x180004fd7  xor     edx, edx
0x180004fd9  call    Log_HREvent
0x180004fde  lea     rcx, [rbp+4Fh+var_C0]; this
0x180004fe2  call    ??1SyncPartnerData@@QEAA@XZ; SyncPartnerData::~SyncPartnerData(void)
0x180004fe7  lea     rcx, [rsp+110h+var_D0]
0x180004fec  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004ff1  jmp     short loc_180004FFD
0x180004ff3  mov     ebx, 1
0x180004ff8  mov     [rax+38h], ebx
0x180004ffb  mov     edi, ebx
0x180004ffd  lea     rcx, [rbp+4Fh+var_98]
0x180005001  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005006  mov     eax, edi
0x180005008  mov     rcx, [rbp+4Fh+var_38]
0x18000500c  xor     rcx, rsp; StackCookie
0x18000500f  call    __security_check_cookie
0x180005014  add     rsp, 0E8h
0x18000501b  pop     r15
0x18000501d  pop     r14
0x18000501f  pop     rdi
0x180005020  pop     rsi
0x180005021  pop     rbx
0x180005022  pop     rbp
0x180005023  retn
```
