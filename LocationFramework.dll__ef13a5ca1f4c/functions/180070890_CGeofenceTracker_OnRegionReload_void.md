# CGeofenceTracker::OnRegionReload(void)

- ea: `0x180070890`
- end: `0x180070e84`
- name: `?OnRegionReload@CGeofenceTracker@@AEAAJXZ`
- size: `1524`
- prototype: `__int64 __fastcall(CGeofenceTracker *__hidden this)`
- caller_count: `0`
- callee_count: `27`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000f888`
- `0x180012194`
- `0x1800123c0`
- `0x180019704`
- `0x180021450`
- `0x180022568`
- `0x180041f7c`
- `0x180042f70`
- `0x180070040`
- `0x180070890`
- `0x180070e8c`
- `0x180081ba8`
- `0x180081ef4`
- `0x180082c9c`
- `0x180090840`
- `0x1800909f4`
- `0x1800922ac`
- `0x180094cc0`
- `0x180097ba8`
- `0x180098dc4`
- `0x18009c310`
- `0x1800a98c0`
- `0x1800a9e0c`
- `0x1800a9e30`
- `0x1800aa5ac`
- `0x1800fcc10`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070ab4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070ac2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070d3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070d4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070de4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070df2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070ab4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070ac2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070d3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070d4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070de4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070df2`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CGeofenceTracker::OnRegionReload(CGeofenceTracker *this, __int64 a2, __int64 a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  unsigned int **v7; // rsi
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rax
  __int64 v10; // r8
  _DWORD *v11; // r15
  __int64 v12; // r9
  std::_Ref_count_base *v13; // rcx
  int v14; // eax
  __int64 v15; // r8
  int v16; // eax
  std::_Ref_count_base *v17; // rbx
  int v18; // eax
  double v19; // xmm0_8
  double v20; // xmm1_8
  double v21; // xmm6_8
  std::_Ref_count_base *v22; // rax
  TRACKED_GEOFENCE *v23; // rax
  unsigned int **v24; // rax
  unsigned int *v25; // rdx
  unsigned int *v26; // rdx
  unsigned int *v27; // rax
  int v28; // edx
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  wil::details *v32; // [rsp+28h] [rbp-D8h]
  wil::details *v33; // [rsp+28h] [rbp-D8h]
  int v34; // [rsp+30h] [rbp-D0h]
  std::_Ref_count_base *v35[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v37; // [rsp+78h] [rbp-88h]
  char v38[8]; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base *v39; // [rsp+88h] [rbp-78h]
  _BYTE v40[48]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v41; // [rsp+C0h] [rbp-40h]
  __int64 v42; // [rsp+D0h] [rbp-30h]
  double v43; // [rsp+D8h] [rbp-28h]
  struct GEOFENCE_INFORMATION *v44; // [rsp+F0h] [rbp-10h]
  LPVOID pv; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v46; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v47[2]; // [rsp+108h] [rbp+8h] BYREF
  _OWORD v48[3]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v49[16]; // [rsp+148h] [rbp+48h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+198h] [rbp+98h]

  if ( (byte_1801E39C4 & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(this, BeginRegionLoad, a3, 1, v49);
  v4 = CGeofenceTracker::EnsureKnownCurrentPosition(this);
  v5 = v4;
  if ( v4 < 0 )
  {
    LODWORD(v32) = v4;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x48E,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\geofence\\geofencetracker\\geofencetracker.cpp",
      "CGeofenceTracker::OnRegionReload",
      "hr",
      v32,
      v34);
    return v5;
  }
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v49,
    (char *)this + 96);
  v7 = (unsigned int **)((char *)this + 304);
  if ( *((_QWORD *)this + 38) )
  {
    CGeofenceTracker::RemoveFromInternalTrackers(this, (char *)this + 304);
    *(_OWORD *)v35 = *(_OWORD *)std::_Tree<std::_Tmap_traits<GEOFENCE_ID,std::shared_ptr<TRACKED_GEOFENCE>,CompareGeofenceId,std::allocator<std::pair<GEOFENCE_ID const,std::shared_ptr<TRACKED_GEOFENCE>>>,0>>::_Eqrange<GEOFENCE_ID>(
                                  (__int64 *)this + 47,
                                  v47,
                                  *v7);
    std::_Tree<std::_Tmap_traits<GEOFENCE_ID,std::shared_ptr<TRACKED_GEOFENCE>,CompareGeofenceId,std::allocator<std::pair<GEOFENCE_ID const,std::shared_ptr<TRACKED_GEOFENCE>>>,0>>::_Erase(
      (char *)this + 376,
      v35);
    *(_OWORD *)v35 = 0;
    std::shared_ptr<ILocationSignalManager>::operator=((char *)this + 304, v35);
    if ( v35[1] )
      std::_Ref_count_base::_Decref(v35[1]);
    *((_OWORD *)this + 20) = 0;
    *((_OWORD *)this + 21) = 0;
  }
  if ( *((_QWORD *)this + 37) > 0xFFFFFFFF )
  {
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v49);
    return 2147549183LL;
  }
  else
  {
    v8 = *((unsigned int *)this + 74);
    if ( !(_DWORD)v8 )
    {
      v5 = 0;
LABEL_47:
      ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v49);
      return v5;
    }
    v9 = 4LL * *((unsigned int *)this + 74);
    if ( !is_mul_ok(v8, 4u) )
      v9 = -1;
    v11 = operator new[](v9, (const struct std::nothrow_t *)std::nothrow);
    v47[0] = v11;
    if ( !v11 )
    {
LABEL_46:
      std::unique_ptr<__MIDL___MIDL_itf_wifipe_0000_0000_0006 [0]>::~unique_ptr<__MIDL___MIDL_itf_wifipe_0000_0000_0006 [0]>(v47);
      v5 = -2147024882;
      goto LABEL_47;
    }
    v12 = 0;
    v13 = (std::_Ref_count_base *)**((_QWORD **)this + 36);
    v35[0] = v13;
    while ( v13 != *((std::_Ref_count_base **)this + 36) )
    {
      v11[v12] = *((_DWORD *)v13 + 7);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IWiFiConnectionStateNotificationSink>>>>,std::_Iterator_base0>::operator++(v35);
      v13 = v35[0];
    }
    v44 = 0;
    v46 = 0;
    pv = 0;
    memset(v48, 0, sizeof(v48));
    v14 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, __int64, __int64))(**((_QWORD **)this + 70) + 32LL))(
            *((_QWORD *)this + 70),
            v48,
            v10,
            v12);
    v5 = v14;
    if ( v14 < 0 )
    {
      LODWORD(v32) = v14;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x4BC,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\geofence\\geofencetracker\\geofencetracker.cpp",
        "CGeofenceTracker::OnRegionReload",
        "hr",
        v32,
        v34);
LABEL_21:
      CoTaskMemFree(pv);
      pv = 0;
      CoTaskMemFree(v44);
      v44 = 0;
      std::unique_ptr<__MIDL___MIDL_itf_wifipe_0000_0000_0006 [0]>::~unique_ptr<__MIDL___MIDL_itf_wifipe_0000_0000_0006 [0]>(v47);
      goto LABEL_47;
    }
    v16 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *, __int64, _QWORD, _DWORD, _DWORD *))(**((_QWORD **)this + 18) + 80LL))(
            *((_QWORD *)this + 18),
            &v46,
            v15,
            *((unsigned int *)this + 89),
            v8,
            v11);
    v5 = v16;
    if ( v16 < 0 )
    {
      LODWORD(v33) = v16;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x4CA,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\geofence\\geofencetracker\\geofencetracker.cpp",
        "CGeofenceTracker::OnRegionReload",
        "hr",
        v33,
        (int)&v46);
      goto LABEL_21;
    }
    if ( !(_DWORD)v46 && HIDWORD(v46) )
    {
      v5 = -2147023537;
      LODWORD(v33) = -2147023537;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x4CF,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\geofence\\geofencetracker\\geofencetracker.cpp",
        "CGeofenceTracker::OnRegionReload",
        "HRESULT_FROM_WIN32(ERROR_INTERNAL_ERROR)",
        v33,
        (int)&v46);
      goto LABEL_21;
    }
    v17 = (std::_Ref_count_base *)**((_QWORD **)this + 47);
    v35[0] = v17;
    while ( v17 != *((std::_Ref_count_base **)this + 47) )
    {
      if ( *(_BYTE *)(*((_QWORD *)v17 + 6) + 120LL) )
      {
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IWiFiConnectionStateNotificationSink>>>>,std::_Iterator_base0>::operator++(v35);
      }
      else
      {
        CGeofenceTracker::RemoveFromInternalTrackers(this, (char *)v17 + 48);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IWiFiConnectionStateNotificationSink>>>>,std::_Iterator_base0>::operator++(v35);
        std::_Tree<std::_Tmap_traits<GEOFENCE_ID,std::shared_ptr<TRACKED_GEOFENCE>,CompareGeofenceId,std::allocator<std::pair<GEOFENCE_ID const,std::shared_ptr<TRACKED_GEOFENCE>>>,0>>::_Erase_unchecked(
          (char *)this + 376,
          v17);
      }
      v17 = v35[0];
    }
    CGeofenceTracker::StartTrackingGeofences(this, (const struct GEOFENCE_INFORMATION *)pv, HIDWORD(v46));
    v18 = v46;
    if ( (_DWORD)v46 )
    {
      *((_DWORD *)this + 80) = 1;
      v19 = *(double *)v48;
      *((_QWORD *)this + 41) = *(_QWORD *)&v48[0];
      v20 = *((double *)v48 + 1);
      *((_QWORD *)this + 42) = *((_QWORD *)&v48[0] + 1);
      v35[0] = 0;
      CalculateDistancesToRegion(
        v19,
        v20,
        (struct GEOFENCE_INFORMATION *)((char *)v44 + 88 * (unsigned int)(v18 - 1) + 48),
        0,
        (double *)v35);
      v21 = DOUBLE_40000_0;
      if ( (unsigned int)v46 >= *((_DWORD *)this + 89) || *(double *)v35 >= 40000.0 )
      {
        if ( *(double *)v35 >= 50.0 )
          v21 = fmin(*(double *)v35, 40000.0);
        else
          v21 = DOUBLE_50_0;
      }
      *((double *)this + 43) = v21;
      memset_0(v40, 0, 0x58u);
      v41 = *((_OWORD *)this + 20);
      v42 = *((_QWORD *)this + 42);
      v43 = (double)(100 - *((_DWORD *)this + 88)) * v21 / 100.0;
      v22 = (std::_Ref_count_base *)operator new(0xC8u, (const struct std::nothrow_t *)std::nothrow);
      v35[0] = v22;
      if ( v22 )
        v23 = TRACKED_GEOFENCE::TRACKED_GEOFENCE(v22, (const struct GEOFENCE_INFORMATION *)v40);
      else
        v23 = 0;
      v24 = (unsigned int **)std::shared_ptr<TRACKED_GEOFENCE>::shared_ptr<TRACKED_GEOFENCE>(v35, v23);
      v25 = *v24;
      *v24 = *v7;
      *v7 = v25;
      v26 = v24[1];
      v24[1] = (unsigned int *)*((_QWORD *)this + 39);
      *((_QWORD *)this + 39) = v26;
      if ( v35[1] )
        std::_Ref_count_base::_Decref(v35[1]);
      if ( !*v7 )
      {
        CoTaskMemFree(pv);
        pv = 0;
        CoTaskMemFree(v44);
        v44 = 0;
        goto LABEL_46;
      }
      (*v7)[20] = 1;
      (*v7)[22] = 1;
      v27 = *v7;
      v36 = *(_QWORD *)*v7;
      v37 = v27[2];
      std::shared_ptr<GEOFENCE_DISTANCE>::shared_ptr<GEOFENCE_DISTANCE>(v38, (char *)this + 304);
      std::_Tree<std::_Tmap_traits<GEOFENCE_ID,std::shared_ptr<TRACKED_GEOFENCE>,CompareGeofenceId,std::allocator<std::pair<GEOFENCE_ID const,std::shared_ptr<TRACKED_GEOFENCE>>>,0>>::_Emplace<std::pair<GEOFENCE_ID,std::shared_ptr<TRACKED_GEOFENCE>>>(
        (__int64 *)this + 47,
        (__int64)v35,
        (__int64)&v36);
      if ( v39 )
        std::_Ref_count_base::_Decref(v39);
      CGeofenceTracker::AddToInternalTrackers(this, (char *)this + 304);
      CGeofenceTracker::StartTrackingGeofences(this, v44, (unsigned int)v46);
    }
    CoTaskMemFree(pv);
    pv = 0;
    CoTaskMemFree(v44);
    v44 = 0;
    std::unique_ptr<__MIDL___MIDL_itf_wifipe_0000_0000_0006 [0]>::~unique_ptr<__MIDL___MIDL_itf_wifipe_0000_0000_0006 [0]>(v47);
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v49);
    if ( (byte_1801E39C4 & 4) != 0 )
      McTemplateU0gggq_EventWriteTransfer(v29, v28, v30, v31, *((_QWORD *)this + 43), *((_DWORD *)this + 96));
    return 0;
  }
}

```

## disassembly

```asm
0x180070890  mov     rax, rsp
0x180070893  mov     [rax+10h], rbx
0x180070897  mov     [rax+18h], rsi
0x18007089b  push    rbp
0x18007089c  push    rdi
0x18007089d  push    r12
0x18007089f  push    r14
0x1800708a1  push    r15
0x1800708a3  lea     rbp, [rsp-70h]
0x1800708a8  sub     rsp, 170h
0x1800708af  movaps  xmmword ptr [rax-38h], xmm6
0x1800708b3  mov     rax, cs:__security_cookie
0x1800708ba  xor     rax, rsp
0x1800708bd  mov     [rbp+90h+var_38], rax
0x1800708c1  mov     rdi, rcx
0x1800708c4  test    cs:byte_1801E39C4, 4
0x1800708cb  jz      short loc_1800708E8
0x1800708cd  lea     rax, [rbp+90h+var_48]
0x1800708d1  mov     [rsp+190h+var_170], rax
0x1800708d6  mov     r9d, 1
0x1800708dc  lea     rdx, BeginRegionLoad
0x1800708e3  call    McGenEventWrite_EventWriteTransfer
0x1800708e8  mov     rcx, rdi; this
0x1800708eb  call    ?EnsureKnownCurrentPosition@CGeofenceTracker@@AEAAJXZ; CGeofenceTracker::EnsureKnownCurrentPosition(void)
0x1800708f0  mov     ebx, eax
0x1800708f2  xor     r12d, r12d
0x1800708f5  test    eax, eax
0x1800708f7  jns     short loc_18007092F
0x1800708f9  mov     rcx, [rbp+98h]; this
0x180070900  mov     dword ptr [rsp+190h+var_168], eax; wil::details *
0x180070904  lea     rdx, aHr; "hr"
0x18007090b  mov     [rsp+190h+var_170], rdx; char *
0x180070910  lea     r9, aCgeofencetrack_11; "CGeofenceTracker::OnRegionReload"
0x180070917  lea     r8, aOnecoreuapDriv_10; "onecoreuap\\drivers\\mobilepc\\location"...
0x18007091e  mov     edx, 48Eh; void *
0x180070923  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180070928  mov     eax, ebx
0x18007092a  jmp     loc_180070E57
0x18007092f  lea     rdx, [rdi+60h]
0x180070933  lea     rcx, [rbp+90h+var_48]
0x180070937  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18007093c  nop
0x18007093d  lea     rsi, [rdi+130h]
0x180070944  cmp     [rsi], r12
0x180070947  jz      short loc_1800709B6
0x180070949  mov     rdx, rsi
0x18007094c  mov     rcx, rdi
0x18007094f  call    ?RemoveFromInternalTrackers@CGeofenceTracker@@AEAAJAEBV?$shared_ptr@UTRACKED_GEOFENCE@@@std@@@Z; CGeofenceTracker::RemoveFromInternalTrackers(std::shared_ptr<TRACKED_GEOFENCE> const &)
0x180070954  lea     rbx, [rdi+178h]
0x18007095b  mov     r8, [rsi]
0x18007095e  lea     rdx, [rbp+8]
0x180070962  mov     rcx, rbx
0x180070965  call    ??$_Eqrange@UGEOFENCE_ID@@@?$_Tree@V?$_Tmap_traits@UGEOFENCE_ID@@V?$shared_ptr@UTRACKED_GEOFENCE@@@std@@UCompareGeofenceId@@V?$allocator@U?$pair@$$CBUGEOFENCE_ID@@V?$shared_ptr@UTRACKED_GEOFENCE@@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBUGEOFENCE_ID@@V?$shared_ptr@UTRACKED_GEOFENCE@@@std@@@std@@PEAX@std@@PEAU12@@1@AEBUGEOFENCE_ID@@@Z; std::_Tree<std::_Tmap_traits<GEOFENCE_ID,std::shared_ptr<TRACKED_GEOFENCE>,CompareGeofenceId,std::allocator<std::pair<GEOFENCE_ID const,std::shared_ptr<TRACKED_GEOFENCE>>>,0>>::_Eqrange<GEOFENCE_ID>(GEOFENCE_ID const &)
0x18007096a  movups  xmm0, xmmword ptr [rax]
0x18007096d  movdqu  xmmword ptr [rsp+190h+var_130], xmm0
0x180070973  lea     rdx, [rsp+190h+var_130]
0x180070978  mov     rcx, rbx
0x18007097b  call    ?_Erase@?$_Tree@V?$_Tmap_traits@UGEOFENCE_ID@@V?$shared_ptr@UTRACKED_GEOFENCE@@@std@@UCompareGeofenceId@@V?$allocator@U?$pair@$$CBUGEOFENCE_ID@@V?$shared_ptr@UTRACKED_GEOFENCE@@@std@@@std@@@3@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBUGEOFENCE_ID@@V?$shared_ptr@UTRACKED_GEOFENCE@@@std@@@std@@PEAX@std@@PEAU12@@2@@Z; std::_Tree<std::_Tmap_traits<GEOFENCE_ID,std::shared_ptr<TRACKED_GEOFENCE>,CompareGeofenceId,std::allocator<std::pair<GEOFENCE_ID const,std::shared_ptr<TRACKED_GEOFENCE>>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<GEOFENCE_ID const,std::shared_ptr<TRACKED_GEOFENCE>>,void *> *,std::_Tree_node<std::pair<GEOFENCE_ID const,std::shared_ptr<TRACKED_GEOFENCE>>,void *> *>)
0x180070980  xorps   xmm0, xmm0
0x180070983  movdqu  xmmword ptr [rsp+190h+var_130], xmm0
0x180070989  lea     rdx, [rsp+190h+var_130]
0x18007098e  mov     rcx, rsi
0x180070991  call    ??4?$shared_ptr@VILocationSignalManager@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ILocationSignalManager>::operator=(std::shared_ptr<ILocationSignalManager> &&)
0x180070996  mov     rcx, [rsp+190h+var_130+8]; this
0x18007099b  test    rcx, rcx
0x18007099e  jz      short loc_1800709A5
0x1800709a0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800709a5  xorps   xmm0, xmm0
0x1800709a8  movups  xmmword ptr [rdi+140h], xmm0
0x1800709af  movups  xmmword ptr [rdi+150h], xmm0
0x1800709b6  mov     eax, 0FFFFFFFFh
0x1800709bb  cmp     [rdi+128h], rax
0x1800709c2  ja      loc_180070E49
0x1800709c8  mov     r14d, [rdi+128h]
0x1800709cf  test    r14d, r14d
0x1800709d2  jnz     short loc_1800709DC
0x1800709d4  mov     ebx, r12d
0x1800709d7  jmp     loc_180070D63
0x1800709dc  mov     eax, 4
0x1800709e1  mul     r14
0x1800709e4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800709eb  cmovb   rax, rcx
0x1800709ef  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800709f6  mov     rcx, rax; unsigned __int64
0x1800709f9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800709fe  mov     r15, rax
0x180070a01  mov     [rbp+8], rax
0x180070a05  test    rax, rax
0x180070a08  jz      loc_180070D55
0x180070a0e  mov     r9, r12
0x180070a11  mov     rcx, [rdi+120h]
0x180070a18  mov     rcx, [rcx]
0x180070a1b  mov     [rsp+190h+var_130], rcx
0x180070a20  cmp     rcx, [rdi+120h]
0x180070a27  jz      short loc_180070A44
0x180070a29  mov     eax, [rcx+1Ch]
0x180070a2c  mov     [r15+r9*4], eax
0x180070a30  inc     r9
0x180070a33  lea     rcx, [rsp+190h+var_130]
0x180070a38  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$CAdapt@V?$CComPtr@UIWiFiConnectionStateNotificationSink@@@ATL@@@ATL@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IWiFiConnectionStateNotificationSink>>>>,std::_Iterator_base0>::operator++(void)
0x180070a3d  mov     rcx, [rsp+190h+var_130]
0x180070a42  jmp     short loc_180070A20
0x180070a44  mov     [rbp+90h+var_A0], r12
0x180070a48  mov     dword ptr [rbp+90h+var_90], r12d
0x180070a4c  mov     [rbp+90h+pv], r12
0x180070a50  mov     dword ptr [rbp+90h+var_90+4], r12d
0x180070a54  xorps   xmm0, xmm0
0x180070a57  movups  xmmword ptr [rbp+90h+var_78], xmm0
0x180070a5b  movups  [rbp+90h+var_68], xmm0
0x180070a5f  movups  [rbp+90h+var_58], xmm0
0x180070a63  mov     rcx, [rdi+230h]
0x180070a6a  mov     rax, [rcx]
0x180070a6d  lea     rdx, [rbp+90h+var_78]
0x180070a71  mov     rax, [rax+20h]
0x180070a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070a7a  mov     ebx, eax
0x180070a7c  test    eax, eax
0x180070a7e  jns     short loc_180070ADA
0x180070a80  mov     dword ptr [rsp+190h+var_168], eax; wil::details *
0x180070a84  lea     rdx, aHr; "hr"
0x180070a8b  mov     [rsp+190h+var_170], rdx; char *
0x180070a90  mov     edx, 4BCh; void *
0x180070a95  mov     rcx, [rbp+98h]; this
0x180070a9c  lea     r9, aCgeofencetrack_11; "CGeofenceTracker::OnRegionReload"
0x180070aa3  lea     r8, aOnecoreuapDriv_10; "onecoreuap\\drivers\\mobilepc\\location"...
0x180070aaa  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180070aaf  nop
0x180070ab0  mov     rcx, [rbp+90h+pv]; pv
0x180070ab4  call    cs:__imp_CoTaskMemFree
0x180070aba  mov     [rbp+90h+pv], r12
0x180070abe  mov     rcx, [rbp+90h+var_A0]; pv
0x180070ac2  call    cs:__imp_CoTaskMemFree
0x180070ac8  mov     [rbp+90h+var_A0], r12
0x180070acc  lea     rcx, [rbp+8]
0x180070ad0  call    ??1?$unique_ptr@$$BY0A@U__MIDL___MIDL_itf_wifipe_0000_0000_0006@@U?$default_delete@$$BY0A@U__MIDL___MIDL_itf_wifipe_0000_0000_0006@@@std@@@std@@QEAA@XZ; std::unique_ptr<__MIDL___MIDL_itf_wifipe_0000_0000_0006 [0]>::~unique_ptr<__MIDL___MIDL_itf_wifipe_0000_0000_0006 [0]>(void)
0x180070ad5  jmp     loc_180070D63
0x180070ada  mov     rcx, [rdi+90h]
0x180070ae1  mov     rax, [rcx]
0x180070ae4  lea     rdx, [rbp+90h+pv]
0x180070ae8  mov     [rsp+190h+var_140], rdx
0x180070aed  lea     rdx, [rbp+90h+var_90+4]
0x180070af1  mov     [rsp+190h+var_148], rdx
0x180070af6  mov     edx, [rdi+168h]
0x180070afc  mov     [rsp+190h+var_150], edx
0x180070b00  lea     rdx, [rbp+90h+var_A0]
0x180070b04  mov     [rsp+190h+var_158], rdx
0x180070b09  lea     rdx, [rbp+90h+var_90]
0x180070b0d  mov     [rsp+190h+var_160], rdx
0x180070b12  mov     [rsp+190h+var_168], r15
0x180070b17  mov     dword ptr [rsp+190h+var_170], r14d
0x180070b1c  mov     r9d, [rdi+164h]
0x180070b23  movsd   xmm2, [rbp+90h+var_78+8]
0x180070b28  movsd   xmm1, [rbp+90h+var_78]
0x180070b2d  mov     rax, [rax+50h]
0x180070b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070b36  mov     ebx, eax
0x180070b38  test    eax, eax
0x180070b3a  jns     short loc_180070B56
0x180070b3c  mov     dword ptr [rsp+190h+var_168], eax
0x180070b40  lea     rdx, aHr; "hr"
0x180070b47  mov     [rsp+190h+var_170], rdx
0x180070b4c  mov     edx, 4CAh
0x180070b51  jmp     loc_180070A95
0x180070b56  cmp     dword ptr [rbp+90h+var_90], r12d
0x180070b5a  jnz     short loc_180070B81
0x180070b5c  cmp     dword ptr [rbp+90h+var_90+4], r12d
0x180070b60  jbe     short loc_180070B81
0x180070b62  mov     ebx, 8007054Fh
0x180070b67  mov     dword ptr [rsp+190h+var_168], ebx
0x180070b6b  lea     rax, aHresultFromWin_3; "HRESULT_FROM_WIN32(ERROR_INTERNAL_ERROR"...
0x180070b72  mov     [rsp+190h+var_170], rax
0x180070b77  mov     edx, 4CFh
0x180070b7c  jmp     loc_180070A95
0x180070b81  lea     r14, [rdi+178h]
0x180070b88  mov     rbx, [r14]
0x180070b8b  mov     rbx, [rbx]
0x180070b8e  mov     [rsp+190h+var_130], rbx
0x180070b93  cmp     rbx, [r14]
0x180070b96  jz      short loc_180070BD5
0x180070b98  lea     rdx, [rbx+30h]
0x180070b9c  mov     rax, [rdx]
0x180070b9f  cmp     [rax+78h], r12b
0x180070ba3  jnz     short loc_180070BC4
0x180070ba5  mov     rcx, rdi
0x180070ba8  call    ?RemoveFromInternalTrackers@CGeofenceTracker@@AEAAJAEBV?$shared_ptr@UTRACKED_GEOFENCE@@@std@@@Z; CGeofenceTracker::RemoveFromInternalTrackers(std::shared_ptr<TRACKED_GEOFENCE> const &)
0x180070bad  lea     rcx, [rsp+190h+var_130]
0x180070bb2  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$CAdapt@V?$CComPtr@UIWiFiConnectionStateNotificationSink@@@ATL@@@ATL@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IWiFiConnectionStateNotificationSink>>>>,std::_Iterator_base0>::operator++(void)
0x180070bb7  mov     rdx, rbx
0x180070bba  mov     rcx, r14
0x180070bbd  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@UGEOFENCE_ID@@V?$shared_ptr@UTRACKED_GEOFENCE@@@std@@UCompareGeofenceId@@V?$allocator@U?$pair@$$CBUGEOFENCE_ID@@V?$shared_ptr@UTRACKED_GEOFENCE@@@std@@@std@@@3@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBUGEOFENCE_ID@@V?$shared_ptr@UTRACKED_GEOFENCE@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUGEOFENCE_ID@@V?$shared_ptr@UTRACKED_GEOFENCE@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree<std::_Tmap_traits<GEOFENCE_ID,std::shared_ptr<TRACKED_GEOFENCE>,CompareGeofenceId,std::allocator<std::pair<GEOFENCE_ID const,std::shared_ptr<TRACKED_GEOFENCE>>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<GEOFENCE_ID const,std::shared_ptr<TRACKED_GEOFENCE>>>>,std::_Iterator_base0>)
0x180070bc2  jmp     short loc_180070BCE
0x180070bc4  lea     rcx, [rsp+190h+var_130]
0x180070bc9  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$CAdapt@V?$CComPtr@UIWiFiConnectionStateNotificationSink@@@ATL@@@ATL@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IWiFiConnectionStateNotificationSink>>>>,std::_Iterator_base0>::operator++(void)
0x180070bce  mov     rbx, [rsp+190h+var_130]
0x180070bd3  jmp     short loc_180070B93
0x180070bd5  mov     r8d, dword ptr [rbp+90h+var_90+4]; unsigned __int64
0x180070bd9  mov     rdx, [rbp+90h+pv]; struct GEOFENCE_INFORMATION *
0x180070bdd  mov     rcx, rdi; this
0x180070be0  call    ?StartTrackingGeofences@CGeofenceTracker@@AEAAJPEBUGEOFENCE_INFORMATION@@_K@Z; CGeofenceTracker::StartTrackingGeofences(GEOFENCE_INFORMATION const *,unsigned __int64)
0x180070be5  mov     eax, dword ptr [rbp+90h+var_90]
0x180070be8  test    eax, eax
0x180070bea  jz      loc_180070DE0
0x180070bf0  mov     dword ptr [rdi+140h], 1
0x180070bfa  movsd   xmm0, [rbp+90h+var_78]; double
0x180070bff  movsd   qword ptr [rdi+148h], xmm0
0x180070c07  movsd   xmm1, [rbp+90h+var_78+8]; double
0x180070c0c  movsd   qword ptr [rdi+150h], xmm1
0x180070c14  xorps   xmm2, xmm2
0x180070c17  movsd   [rsp+190h+var_130], xmm2
0x180070c1d  lea     ecx, [rax-1]
0x180070c20  imul    rdx, rcx, 58h ; 'X'
0x180070c24  mov     r8, [rbp+90h+var_A0]
0x180070c28  add     r8, 30h ; '0'
0x180070c2c  add     r8, rdx; struct GEOREGION *
0x180070c2f  lea     rax, [rsp+190h+var_130]
0x180070c34  mov     [rsp+190h+var_170], rax; double *
0x180070c39  xor     r9d, r9d; double *
0x180070c3c  call    ?CalculateDistancesToRegion@@YAXNNAEBUGEOREGION@@PEAN1@Z; CalculateDistancesToRegion(double,double,GEOREGION const &,double *,double *)
0x180070c41  movsd   xmm6, cs:__real@40e3880000000000
0x180070c49  movsd   xmm0, [rsp+190h+var_130]
0x180070c4f  mov     eax, [rdi+164h]
0x180070c55  cmp     dword ptr [rbp+90h+var_90], eax
0x180070c58  jnb     short loc_180070C60
0x180070c5a  comisd  xmm6, xmm0
0x180070c5e  ja      short loc_180070C7A
0x180070c60  movsd   xmm1, cs:__real@4049000000000000
0x180070c68  comisd  xmm1, xmm0
0x180070c6c  jbe     short loc_180070C73
0x180070c6e  movaps  xmm6, xmm1
0x180070c71  jmp     short loc_180070C7A
0x180070c73  minsd   xmm0, xmm6
0x180070c77  movaps  xmm6, xmm0
0x180070c7a  movsd   qword ptr [rdi+158h], xmm6
0x180070c82  xor     edx, edx; Val
0x180070c84  lea     r8d, [rdx+58h]; Size
0x180070c88  lea     rcx, [rbp+90h+var_100]; void *
0x180070c8c  call    memset_0
0x180070c91  movups  xmm0, xmmword ptr [rdi+140h]
0x180070c98  movaps  [rbp+90h+var_D0], xmm0
0x180070c9c  movsd   xmm1, qword ptr [rdi+150h]
0x180070ca4  movsd   [rbp+90h+var_C0], xmm1
0x180070ca9  mov     eax, 64h ; 'd'
0x180070cae  sub     eax, [rdi+160h]
0x180070cb4  xorps   xmm0, xmm0
0x180070cb7  cvtsi2sd xmm0, rax
0x180070cbc  mulsd   xmm0, xmm6
0x180070cc0  divsd   xmm0, cs:__real@4059000000000000
0x180070cc8  movsd   [rbp+90h+var_B8], xmm0
0x180070ccd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180070cd4  mov     ecx, 0C8h; unsigned __int64
0x180070cd9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180070cde  mov     [rsp+190h+var_130], rax
0x180070ce3  test    rax, rax
0x180070ce6  jz      short loc_180070CF6
0x180070ce8  lea     rdx, [rbp+90h+var_100]; struct GEOFENCE_INFORMATION *
0x180070cec  mov     rcx, rax; this
0x180070cef  call    ??0TRACKED_GEOFENCE@@QEAA@AEBUGEOFENCE_INFORMATION@@@Z; TRACKED_GEOFENCE::TRACKED_GEOFENCE(GEOFENCE_INFORMATION const &)
0x180070cf4  jmp     short loc_180070CF9
0x180070cf6  mov     rax, r12
0x180070cf9  mov     rdx, rax
0x180070cfc  lea     rcx, [rsp+190h+var_130]
0x180070d01  call    ??$?0UTRACKED_GEOFENCE@@$0A@@?$shared_ptr@UTRACKED_GEOFENCE@@@std@@QEAA@PEAUTRACKED_GEOFENCE@@@Z; std::shared_ptr<TRACKED_GEOFENCE>::shared_ptr<TRACKED_GEOFENCE>(TRACKED_GEOFENCE *)
0x180070d06  mov     rdx, [rax]
0x180070d09  mov     rcx, [rsi]
0x180070d0c  mov     [rax], rcx
0x180070d0f  mov     [rsi], rdx
0x180070d12  mov     rdx, [rax+8]
0x180070d16  mov     rcx, [rsi+8]
0x180070d1a  mov     [rax+8], rcx
0x180070d1e  mov     [rsi+8], rdx
0x180070d22  mov     rcx, [rsp+190h+var_130+8]; this
0x180070d27  test    rcx, rcx
0x180070d2a  jz      short loc_180070D31
0x180070d2c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180070d31  mov     rax, [rsi]
0x180070d34  test    rax, rax
0x180070d37  jnz     short loc_180070D71
0x180070d39  mov     rcx, [rbp+90h+pv]; pv
0x180070d3d  call    cs:__imp_CoTaskMemFree
0x180070d43  mov     [rbp+90h+pv], r12
0x180070d47  mov     rcx, [rbp+90h+var_A0]; pv
0x180070d4b  call    cs:__imp_CoTaskMemFree
0x180070d51  mov     [rbp+90h+var_A0], r12
0x180070d55  lea     rcx, [rbp+8]
0x180070d59  call    ??1?$unique_ptr@$$BY0A@U__MIDL___MIDL_itf_wifipe_0000_0000_0006@@U?$default_delete@$$BY0A@U__MIDL___MIDL_itf_wifipe_0000_0000_0006@@@std@@@std@@QEAA@XZ; std::unique_ptr<__MIDL___MIDL_itf_wifipe_0000_0000_0006 [0]>::~unique_ptr<__MIDL___MIDL_itf_wifipe_0000_0000_0006 [0]>(void)
0x180070d5e  mov     ebx, 8007000Eh
0x180070d63  lea     rcx, [rbp+90h+var_48]
0x180070d67  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180070d6c  jmp     loc_180070928
0x180070d71  mov     dword ptr [rax+50h], 1
0x180070d78  mov     rax, [rsi]
0x180070d7b  mov     dword ptr [rax+58h], 1
0x180070d82  mov     rax, [rsi]
0x180070d85  movsd   xmm0, qword ptr [rax]
0x180070d89  movsd   [rsp+190h+var_120], xmm0
0x180070d8f  mov     eax, [rax+8]
0x180070d92  mov     [rsp+190h+var_118], eax
0x180070d96  mov     rdx, rsi
0x180070d99  lea     rcx, [rbp+90h+var_110]
0x180070d9d  call    ??0?$shared_ptr@UGEOFENCE_DISTANCE@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<GEOFENCE_DISTANCE>::shared_ptr<GEOFENCE_DISTANCE>(std::shared_ptr<GEOFENCE_DISTANCE> const &)
  ... truncated ...
```
