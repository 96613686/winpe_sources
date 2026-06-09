# PimIMService::ConfigureSyncPartners(int)

- ea: `0x1800058d0`
- end: `0x180005d26`
- name: `?ConfigureSyncPartners@PimIMService@@UEAAJH@Z`
- size: `1110`
- prototype: `__int64 __fastcall(PimIMService *this, int, __int64)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002da8`
- `0x180003468`
- `0x180003648`
- `0x180003674`
- `0x180003ba0`
- `0x1800041f4`
- `0x18000428c`
- `0x1800042b0`
- `0x1800043d0`
- `0x180004a54`
- `0x180004c14`
- `0x1800058d0`
- `0x180006a1c`
- `0x180007298`
- `0x18000b33c`
- `0x18000bb20`
- `0x18000c51c`
- `0x18000c618`
- `0x180021240`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000599d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000599d`

## string_xrefs

- `0x1800059af`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x1800059ef`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180005a68`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180005bd6`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180005c1e`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180005c77`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::ConfigureSyncPartners(PimIMService *this, int a2, __int64 a3)
{
  __int64 *v5; // rbx
  __int64 *v6; // rax
  int v7; // r12d
  HRESULT Instance; // eax
  unsigned int v9; // edi
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // r9
  int v13; // edi
  int v14; // r15d
  int v15; // eax
  PimIMService *v16; // rcx
  __int64 *i; // rax
  __int64 *v18; // rdx
  __int64 *v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rdx
  int *j; // rdi
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r9
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 *k; // rdi
  int v32; // eax
  PimIMService *v33; // rcx
  struct IPOutlookStoreCollection *v35; // [rsp+30h] [rbp-39h] BYREF
  int v36; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v37[4]; // [rsp+3Ch] [rbp-2Dh] BYREF
  _BYTE v38[4]; // [rsp+40h] [rbp-29h] BYREF
  int v39; // [rsp+44h] [rbp-25h] BYREF
  struct IPOSyncServices *ppv; // [rsp+48h] [rbp-21h] BYREF
  __m128i si128; // [rsp+50h] [rbp-19h] BYREF
  __int64 v42; // [rsp+60h] [rbp-9h]
  __m128i v43; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v44; // [rsp+88h] [rbp+1Fh]

  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context,
      PIMIndex_AddingSyncPartner_START,
      a3,
      1,
      &v43);
  v38[1] = 1;
  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x200) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context,
      CONFIGURE_SYNC_START,
      a3,
      1,
      &v43);
  v5 = (__int64 *)((char *)this + 248);
  v37[1] = 1;
  v6 = (__int64 *)*((_QWORD *)this + 31);
  v7 = 0;
  while ( v6 != v5 )
  {
    *((_DWORD *)v6 + 14) = 0;
    v6 = (__int64 *)*v6;
  }
  ppv = 0;
  Instance = CoCreateInstance(
               &GUID_40b47a8f_c442_4f06_8304_aa1058edeea0,
               0,
               0x17u,
               &GUID_21e1b5a4_0010_437a_bfa7_9d1455238f39,
               (LPVOID *)&ppv);
  v9 = Instance;
  if ( Instance >= 0 )
  {
    v10 = *((_QWORD *)this + 27);
    v35 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, struct IPOutlookStoreCollection **))(*(_QWORD *)v10 + 88LL))(v10, &v35);
    v9 = v11;
    if ( v11 < 0 )
    {
      v12 = 1268;
LABEL_12:
      Log_HREvent(
        (unsigned int)v11,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        v12);
LABEL_13:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
      goto LABEL_64;
    }
    v39 = 0;
    v11 = (*(__int64 (__fastcall **)(struct IPOutlookStoreCollection *, int *))(*(_QWORD *)v35 + 56LL))(v35, &v39);
    v9 = v11;
    if ( v11 < 0 )
    {
      v12 = 1271;
      goto LABEL_12;
    }
    v13 = 1;
    v36 = 0;
    v14 = 0;
    if ( v39 >= 1 )
    {
      do
      {
        v15 = PimIMService::AddSyncPartner(this, ppv, v35, v13, &v36);
        if ( v15 < 0 )
          Log_HREvent(
            (unsigned int)v15,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
            1279);
        ++v13;
      }
      while ( v13 <= v39 );
      v14 = v36;
      if ( v36 )
      {
        v11 = PimIMService::FlushTrackedStoresInRegistry(v16);
        v9 = v11;
        if ( v11 < 0 )
        {
          v12 = 1287;
          goto LABEL_12;
        }
      }
    }
LABEL_23:
    for ( i = (__int64 *)*v5; i != v5; i = (__int64 *)*i )
    {
      if ( !*((_DWORD *)i + 14) )
      {
        v7 = 1;
        v18 = (__int64 *)i[1];
        v19 = (__int64 *)*i;
        v20 = (8LL << *((_BYTE *)this + 280)) - 1;
        *v18 = *i;
        v19[1] = (__int64)v18;
        v21 = v20 & i[2];
        v22 = *((_QWORD *)this + 33);
        v23 = 2 * v21;
        if ( *(__int64 **)(v22 + 8 * v23) == i )
        {
          if ( *(__int64 **)(v22 + 8 * v23 + 8) == i )
          {
            *(_QWORD *)(v22 + 8 * v23 + 8) = 0;
            v19 = 0;
          }
          else
          {
            v19 = (__int64 *)*i;
          }
          *(_QWORD *)(v22 + 8 * v23) = v19;
        }
        else if ( *(__int64 **)(v22 + 8 * v23 + 8) == i )
        {
          v19 = (__int64 *)i[1];
          *(_QWORD *)(v22 + 8 * v23 + 8) = v19;
        }
        --*((_QWORD *)this + 34);
        utl::_ContainerBase<utl::pair<unsigned long const,SyncPartnerData>,utl::allocator<utl::pair<unsigned long const,SyncPartnerData>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned long const,SyncPartnerData>>>(
          v19,
          i);
        goto LABEL_23;
      }
    }
    if ( v7 || v14 )
      goto LABEL_45;
    if ( a2 )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      v42 = -1;
      if ( (int)PimIMService::GetTrackedStoresFromRegistry((char *)this + 248, &si128) >= 0 )
      {
        for ( j = (int *)si128.m128i_i64[0]; j != (int *)si128.m128i_i64[1]; ++j )
        {
          v36 = *j;
          if ( *(__int64 **)utl::_HashTable<unsigned long,utl::pair<unsigned long const,SyncPartnerData>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,SyncPartnerData>>,0>::_FindFirst<utl::_HashTable<unsigned long,utl::pair<unsigned long const,SyncPartnerData>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,SyncPartnerData>>,0>::_FindFirstFind,unsigned long>(
                              (char *)this + 248,
                              &v43,
                              &v36) == v5 )
          {
            v7 = 1;
            break;
          }
        }
      }
      utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(&si128);
      if ( v7 )
      {
LABEL_45:
        v25 = PimIMService::_RebuildContactIndexes(this, 0);
        v9 = -2147023781;
        if ( v25 == -2147023781 )
          goto LABEL_13;
        if ( v25 < 0 )
          Log_HREvent(
            (unsigned int)v25,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
            1349);
        v26 = *((_QWORD *)this + 34);
        v43 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
        v44 = -1;
        if ( !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::reserve(&v43, v26) )
        {
          v9 = -2147024882;
          v28 = 1352;
          v29 = 2147942414LL;
          v30 = 0;
          goto LABEL_50;
        }
        for ( k = (__int64 *)*v5; k != v5; k = (__int64 *)*k )
        {
          si128.m128i_i32[0] = *((_DWORD *)k + 6);
          SyncPartnerData::SyncPartnerData(
            (SyncPartnerData *)&si128.m128i_u64[1],
            (const struct SyncPartnerData *)(k + 4));
          if ( !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::_PushBackOne<unsigned long const &>(
                                   &v43,
                                   &si128) )
          {
            v9 = -2147024882;
            Log_HREvent(
              2147942414LL,
              0,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
              1356);
            SyncPartnerData::~SyncPartnerData((SyncPartnerData *)&si128.m128i_u64[1]);
            goto LABEL_51;
          }
          SyncPartnerData::~SyncPartnerData((SyncPartnerData *)&si128.m128i_u64[1]);
        }
        v32 = PimIMService::WriteTrackedStoresToRegistry(v27, &v43);
        v9 = v32;
        if ( v32 < 0 )
        {
          v28 = 1359;
LABEL_59:
          v30 = 1;
          v29 = (unsigned int)v32;
LABEL_50:
          Log_HREvent(
            v29,
            v30,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
            v28);
LABEL_51:
          utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(&v43);
          goto LABEL_13;
        }
        v32 = PimIMService::FlushTrackedStoresInRegistry(v33);
        v9 = v32;
        if ( v32 < 0 )
        {
          v28 = 1360;
          goto LABEL_59;
        }
        utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(&v43);
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
    v9 = 0;
    goto LABEL_64;
  }
  Log_HREvent(
    (unsigned int)Instance,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
    1265);
LABEL_64:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  tlx::_UndoSolo__lambda_598552b5da512f01ef64876b6fc9ea1b___::__UndoSolo__lambda_598552b5da512f01ef64876b6fc9ea1b___(v37);
  tlx::_UndoSolo__lambda_3594964cbf5d30c4734180cf6210409f___::__UndoSolo__lambda_3594964cbf5d30c4734180cf6210409f___(v38);
  return v9;
}

```

## disassembly

```asm
0x1800058d0  mov     [rsp-8+arg_8], rbx
0x1800058d5  mov     [rsp-8+arg_10], rdi
0x1800058da  push    rbp
0x1800058db  push    r12
0x1800058dd  push    r13
0x1800058df  push    r14
0x1800058e1  push    r15
0x1800058e3  lea     rbp, [rsp-37h]
0x1800058e8  sub     rsp, 0A0h
0x1800058ef  mov     rax, cs:__security_cookie
0x1800058f6  xor     rax, rsp
0x1800058f9  mov     [rbp+57h+var_30], rax
0x1800058fd  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 10h
0x180005904  mov     r13d, edx
0x180005907  mov     r14, rcx
0x18000590a  mov     r15d, 1
0x180005910  jz      short loc_180005931
0x180005912  lea     rax, [rbp+57h+var_48]
0x180005916  mov     r9d, r15d
0x180005919  lea     rdx, PIMIndex_AddingSyncPartner_START
0x180005920  mov     [rsp+0C0h+ppv], rax
0x180005925  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x18000592c  call    McGenEventWrite_EventWriteTransfer
0x180005931  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits+1, 2
0x180005938  mov     [rbp+57h+var_7F], r15b
0x18000593c  jz      short loc_18000595D
0x18000593e  lea     rax, [rbp+57h+var_48]
0x180005942  mov     r9d, r15d
0x180005945  lea     rdx, CONFIGURE_SYNC_START
0x18000594c  mov     [rsp+0C0h+ppv], rax
0x180005951  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x180005958  call    McGenEventWrite_EventWriteTransfer
0x18000595d  lea     rbx, [r14+0F8h]
0x180005964  mov     [rbp+57h+var_83], r15b
0x180005968  mov     rax, [rbx]
0x18000596b  xor     r12d, r12d
0x18000596e  cmp     rax, rbx
0x180005971  jz      short loc_18000597C
0x180005973  mov     [rax+38h], r12d
0x180005977  mov     rax, [rax]
0x18000597a  jmp     short loc_18000596E
0x18000597c  xor     edx, edx; pUnkOuter
0x18000597e  mov     [rbp+57h+var_78], r12
0x180005982  lea     rax, [rbp+57h+var_78]
0x180005986  lea     r9, _GUID_21e1b5a4_0010_437a_bfa7_9d1455238f39; riid
0x18000598d  mov     [rsp+0C0h+ppv], rax; ppv
0x180005992  lea     rcx, _GUID_40b47a8f_c442_4f06_8304_aa1058edeea0; rclsid
0x180005999  lea     r8d, [rdx+17h]; dwClsContext
0x18000599d  call    cs:__imp_CoCreateInstance
0x1800059a3  mov     edi, eax
0x1800059a5  test    eax, eax
0x1800059a7  jns     short loc_1800059C5
0x1800059a9  mov     r9d, 4F1h
0x1800059af  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800059b6  mov     edx, r15d
0x1800059b9  mov     ecx, eax
0x1800059bb  call    Log_HREvent
0x1800059c0  jmp     loc_180005CE0
0x1800059c5  mov     rcx, [r14+0D8h]
0x1800059cc  lea     rdx, [rbp+57h+var_90]
0x1800059d0  mov     [rbp+57h+var_90], r12
0x1800059d4  mov     rax, [rcx]
0x1800059d7  mov     rax, [rax+58h]
0x1800059db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059e0  mov     edi, eax
0x1800059e2  test    eax, eax
0x1800059e4  jns     short loc_180005A0B
0x1800059e6  mov     r9d, 4F4h
0x1800059ec  mov     edx, r15d
0x1800059ef  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800059f6  mov     ecx, eax
0x1800059f8  call    Log_HREvent
0x1800059fd  lea     rcx, [rbp+57h+var_90]
0x180005a01  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005a06  jmp     loc_180005CE0
0x180005a0b  mov     rcx, [rbp+57h+var_90]
0x180005a0f  lea     rdx, [rbp+57h+var_7C]
0x180005a13  mov     [rbp+57h+var_7C], r12d
0x180005a17  mov     rax, [rcx]
0x180005a1a  mov     rax, [rax+38h]
0x180005a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a23  mov     edi, eax
0x180005a25  test    eax, eax
0x180005a27  jns     short loc_180005A31
0x180005a29  mov     r9d, 4F7h
0x180005a2f  jmp     short loc_1800059EC
0x180005a31  mov     edi, 1
0x180005a36  mov     [rbp+57h+var_88], r12d
0x180005a3a  mov     r15d, r12d
0x180005a3d  cmp     [rbp+57h+var_7C], edi
0x180005a40  jl      short loc_180005AA3
0x180005a42  mov     r8, [rbp+57h+var_90]; struct IPOutlookStoreCollection *
0x180005a46  lea     rax, [rbp+57h+var_88]
0x180005a4a  mov     rdx, [rbp+57h+var_78]; struct IPOSyncServices *
0x180005a4e  mov     r9d, edi; int
0x180005a51  mov     rcx, r14; this
0x180005a54  mov     [rsp+0C0h+ppv], rax; int *
0x180005a59  call    ?AddSyncPartner@PimIMService@@AEAAJPEAUIPOSyncServices@@PEAUIPOutlookStoreCollection@@HAEAH@Z; PimIMService::AddSyncPartner(IPOSyncServices *,IPOutlookStoreCollection *,int,int &)
0x180005a5e  test    eax, eax
0x180005a60  jns     short loc_180005A78
0x180005a62  mov     r9d, 4FFh
0x180005a68  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180005a6f  xor     edx, edx
0x180005a71  mov     ecx, eax
0x180005a73  call    Log_HREvent
0x180005a78  inc     edi
0x180005a7a  cmp     edi, [rbp+57h+var_7C]
0x180005a7d  jle     short loc_180005A42
0x180005a7f  mov     r15d, [rbp+57h+var_88]
0x180005a83  test    r15d, r15d
0x180005a86  jz      short loc_180005AA3
0x180005a88  call    ?FlushTrackedStoresInRegistry@PimIMService@@QEAAJXZ; PimIMService::FlushTrackedStoresInRegistry(void)
0x180005a8d  mov     edi, eax
0x180005a8f  test    eax, eax
0x180005a91  jns     short loc_180005AA3
0x180005a93  mov     r9d, 507h
0x180005a99  mov     edx, 1
0x180005a9e  jmp     loc_1800059EF
0x180005aa3  mov     rax, [rbx]
0x180005aa6  mov     rcx, rbx
0x180005aa9  cmp     rax, rcx
0x180005aac  jz      loc_180005B3E
0x180005ab2  cmp     dword ptr [rax+38h], 0
0x180005ab6  jnz     short loc_180005B36
0x180005ab8  mov     cl, [r14+118h]
0x180005abf  mov     r12d, 1
0x180005ac5  mov     rdx, [rax+8]
0x180005ac9  lea     r8d, [r12+7]
0x180005ace  shl     r8, cl
0x180005ad1  mov     rcx, [rax]
0x180005ad4  dec     r8
0x180005ad7  mov     [rdx], rcx
0x180005ada  mov     [rcx+8], rdx
0x180005ade  mov     rdx, [rax+10h]
0x180005ae2  and     rdx, r8
0x180005ae5  mov     r8, [r14+108h]
0x180005aec  add     rdx, rdx
0x180005aef  cmp     [r8+rdx*8], rax
0x180005af3  jnz     short loc_180005B12
0x180005af5  cmp     [r8+rdx*8+8], rax
0x180005afa  jnz     short loc_180005B09
0x180005afc  mov     qword ptr [r8+rdx*8+8], 0
0x180005b05  xor     ecx, ecx
0x180005b07  jmp     short loc_180005B0C
0x180005b09  mov     rcx, [rax]
0x180005b0c  mov     [r8+rdx*8], rcx
0x180005b10  jmp     short loc_180005B22
0x180005b12  cmp     [r8+rdx*8+8], rax
0x180005b17  jnz     short loc_180005B22
0x180005b19  mov     rcx, [rax+8]
0x180005b1d  mov     [r8+rdx*8+8], rcx
0x180005b22  dec     qword ptr [r14+110h]
0x180005b29  mov     rdx, rax
0x180005b2c  call    ??$_DeleteNode@U?$_HashNode@U?$pair@$$CBKUSyncPartnerData@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CBKUSyncPartnerData@@@utl@@V?$allocator@U?$pair@$$CBKUSyncPartnerData@@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@U?$pair@$$CBKUSyncPartnerData@@@utl@@@1@@Z; utl::_ContainerBase<utl::pair<ulong const,SyncPartnerData>,utl::allocator<utl::pair<ulong const,SyncPartnerData>>>::_DeleteNode<utl::_HashNode<utl::pair<ulong const,SyncPartnerData>>>(utl::_HashNode<utl::pair<ulong const,SyncPartnerData>> *)
0x180005b31  jmp     loc_180005AA3
0x180005b36  mov     rax, [rax]
0x180005b39  jmp     loc_180005AA9
0x180005b3e  test    r12d, r12d
0x180005b41  jnz     short loc_180005BB5
0x180005b43  test    r15d, r15d
0x180005b46  jnz     short loc_180005BB5
0x180005b48  test    r13d, r13d
0x180005b4b  jz      loc_180005CD5
0x180005b51  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180005b59  lea     rdx, [rbp+57h+var_70]
0x180005b5d  movdqu  [rbp+57h+var_70], xmm0
0x180005b62  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFFh
0x180005b6a  call    ?GetTrackedStoresFromRegistry@PimIMService@@QEAAJAEAV?$vector@KV?$allocator@K@utl@@@utl@@@Z; PimIMService::GetTrackedStoresFromRegistry(utl::vector<ulong,utl::allocator<ulong>> &)
0x180005b6f  test    eax, eax
0x180005b71  js      short loc_180005BA3
0x180005b73  mov     rdi, qword ptr [rbp+57h+var_70]
0x180005b77  cmp     rdi, qword ptr [rbp+57h+var_70+8]
0x180005b7b  jz      short loc_180005BA3
0x180005b7d  mov     eax, [rdi]
0x180005b7f  lea     r8, [rbp+57h+var_88]
0x180005b83  lea     rdx, [rbp+57h+var_48]
0x180005b87  mov     [rbp+57h+var_88], eax
0x180005b8a  mov     rcx, rbx
0x180005b8d  call    ??$_FindFirst@U_FindFirstFind@?$_HashTable@KU?$pair@$$CBKUSyncPartnerData@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKUSyncPartnerData@@@utl@@@2@$0A@@utl@@K@?$_HashTable@KU?$pair@$$CBKUSyncPartnerData@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKUSyncPartnerData@@@utl@@@2@$0A@@utl@@AEBA?AU_FindFirstFind@01@AEBK@Z; utl::_HashTable<ulong,utl::pair<ulong const,SyncPartnerData>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,SyncPartnerData>>,0>::_FindFirst<utl::_HashTable<ulong,utl::pair<ulong const,SyncPartnerData>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,SyncPartnerData>>,0>::_FindFirstFind,ulong>(ulong const &)
0x180005b92  cmp     [rax], rbx
0x180005b95  jz      short loc_180005B9D
0x180005b97  add     rdi, 4
0x180005b9b  jmp     short loc_180005B77
0x180005b9d  mov     r12d, 1
0x180005ba3  lea     rcx, [rbp+57h+var_70]
0x180005ba7  call    ?_Uninit@?$vector@URunOnToken@IndexedFiltering@@V?$allocator@URunOnToken@IndexedFiltering@@@utl@@@utl@@AEAAXXZ; utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(void)
0x180005bac  test    r12d, r12d
0x180005baf  jz      loc_180005CD5
0x180005bb5  xor     edx, edx; int
0x180005bb7  mov     rcx, r14; this
0x180005bba  call    ?_RebuildContactIndexes@PimIMService@@AEAAJH@Z; PimIMService::_RebuildContactIndexes(int)
0x180005bbf  mov     edi, 8007045Bh
0x180005bc4  cmp     eax, edi
0x180005bc6  jz      loc_1800059FD
0x180005bcc  test    eax, eax
0x180005bce  jns     short loc_180005BE6
0x180005bd0  mov     r9d, 545h
0x180005bd6  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180005bdd  xor     edx, edx
0x180005bdf  mov     ecx, eax
0x180005be1  call    Log_HREvent
0x180005be6  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180005bee  lea     rcx, [rbp+57h+var_48]
0x180005bf2  mov     rdx, [r14+110h]
0x180005bf9  movdqu  [rbp+57h+var_48], xmm0
0x180005bfe  mov     [rbp+57h+var_38], 0FFFFFFFFFFFFFFFFh
0x180005c06  call    ?reserve@?$vector@KV?$allocator@K@utl@@@utl@@QEAA_N_K@Z; utl::vector<ulong,utl::allocator<ulong>>::reserve(unsigned __int64)
0x180005c0b  test    al, al
0x180005c0d  jnz     short loc_180005C38
0x180005c0f  mov     edi, 8007000Eh
0x180005c14  mov     r9d, 548h
0x180005c1a  mov     ecx, edi
0x180005c1c  xor     edx, edx
0x180005c1e  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180005c25  call    Log_HREvent
0x180005c2a  lea     rcx, [rbp+57h+var_48]
0x180005c2e  call    ?_Uninit@?$vector@URunOnToken@IndexedFiltering@@V?$allocator@URunOnToken@IndexedFiltering@@@utl@@@utl@@AEAAXXZ; utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(void)
0x180005c33  jmp     loc_1800059FD
0x180005c38  mov     rdi, [rbx]
0x180005c3b  cmp     rdi, rbx
0x180005c3e  jz      short loc_180005C98
0x180005c40  mov     eax, [rdi+18h]
0x180005c43  lea     rdx, [rdi+20h]; struct SyncPartnerData *
0x180005c47  lea     rcx, [rbp+57h+var_70+8]; this
0x180005c4b  mov     dword ptr [rbp+57h+var_70], eax
0x180005c4e  call    ??0SyncPartnerData@@QEAA@AEBU0@@Z; SyncPartnerData::SyncPartnerData(SyncPartnerData const &)
0x180005c53  lea     rdx, [rbp+57h+var_70]
0x180005c57  lea     rcx, [rbp+57h+var_48]
0x180005c5b  call    ??$_PushBackOne@AEBK@?$vector@KV?$allocator@K@utl@@@utl@@AEAA_NAEBK@Z; utl::vector<ulong,utl::allocator<ulong>>::_PushBackOne<ulong const &>(ulong const &)
0x180005c60  test    al, al
0x180005c62  jz      short loc_180005C72
0x180005c64  lea     rcx, [rbp+57h+var_70+8]; this
0x180005c68  call    ??1SyncPartnerData@@QEAA@XZ; SyncPartnerData::~SyncPartnerData(void)
0x180005c6d  mov     rdi, [rdi]
0x180005c70  jmp     short loc_180005C3B
0x180005c72  mov     edi, 8007000Eh
0x180005c77  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180005c7e  mov     ecx, edi
0x180005c80  mov     r9d, 54Ch
0x180005c86  xor     edx, edx
0x180005c88  call    Log_HREvent
0x180005c8d  lea     rcx, [rbp+57h+var_70+8]; this
0x180005c91  call    ??1SyncPartnerData@@QEAA@XZ; SyncPartnerData::~SyncPartnerData(void)
0x180005c96  jmp     short loc_180005C2A
0x180005c98  lea     rdx, [rbp+57h+var_48]
0x180005c9c  call    ?WriteTrackedStoresToRegistry@PimIMService@@QEAAJAEBV?$vector@KV?$allocator@K@utl@@@utl@@@Z; PimIMService::WriteTrackedStoresToRegistry(utl::vector<ulong,utl::allocator<ulong>> const &)
0x180005ca1  mov     edi, eax
0x180005ca3  test    eax, eax
0x180005ca5  jns     short loc_180005CB9
0x180005ca7  mov     r9d, 54Fh
0x180005cad  mov     edx, 1
0x180005cb2  mov     ecx, eax
0x180005cb4  jmp     loc_180005C1E
0x180005cb9  call    ?FlushTrackedStoresInRegistry@PimIMService@@QEAAJXZ; PimIMService::FlushTrackedStoresInRegistry(void)
0x180005cbe  mov     edi, eax
0x180005cc0  test    eax, eax
0x180005cc2  jns     short loc_180005CCC
0x180005cc4  mov     r9d, 550h
0x180005cca  jmp     short loc_180005CAD
0x180005ccc  lea     rcx, [rbp+57h+var_48]
0x180005cd0  call    ?_Uninit@?$vector@URunOnToken@IndexedFiltering@@V?$allocator@URunOnToken@IndexedFiltering@@@utl@@@utl@@AEAAXXZ; utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(void)
0x180005cd5  lea     rcx, [rbp+57h+var_90]
0x180005cd9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005cde  xor     edi, edi
0x180005ce0  lea     rcx, [rbp+57h+var_78]
0x180005ce4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005ce9  lea     rcx, [rbp+57h+var_84]
0x180005ced  call    tlx___UndoSolo__lambda_598552b5da512f01ef64876b6fc9ea1b_______UndoSolo__lambda_598552b5da512f01ef64876b6fc9ea1b___
0x180005cf2  lea     rcx, [rbp+57h+var_80]
0x180005cf6  call    tlx___UndoSolo__lambda_3594964cbf5d30c4734180cf6210409f_______UndoSolo__lambda_3594964cbf5d30c4734180cf6210409f___
0x180005cfb  mov     eax, edi
0x180005cfd  mov     rcx, [rbp+57h+var_30]
0x180005d01  xor     rcx, rsp; StackCookie
0x180005d04  call    __security_check_cookie
0x180005d09  lea     r11, [rsp+0C0h+var_20]
0x180005d11  mov     rbx, [r11+38h]
0x180005d15  mov     rdi, [r11+40h]
0x180005d19  mov     rsp, r11
0x180005d1c  pop     r15
0x180005d1e  pop     r14
0x180005d20  pop     r13
0x180005d22  pop     r12
0x180005d24  pop     rbp
0x180005d25  retn
```
