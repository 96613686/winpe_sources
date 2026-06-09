# MetadataPackageSource::SetQueryIds(uint,ushort const * const *,_GUID const *)

- ea: `0x180011fb0`
- end: `0x1800125c9`
- name: `?SetQueryIds@MetadataPackageSource@@UEAAJIPEBQEBGPEBU_GUID@@@Z`
- size: `1561`
- prototype: `int(MetadataPackageSource *__hidden this, unsigned int, const unsigned __int16 *const *, const struct _GUID *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004dc4`
- `0x180004e2c`
- `0x180005018`
- `0x180005758`
- `0x1800061c8`
- `0x180006320`
- `0x18000bdec`
- `0x18000f4c8`
- `0x180011fb0`
- `0x1800135cc`
- `0x180013700`
- `0x180014010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180012252`
- `KERNEL32!EnterCriticalSection` at `0x180012252`
- `KERNEL32!LeaveCriticalSection` at `0x1800122a0`
- `KERNEL32!LeaveCriticalSection` at `0x1800122a0`
- `KERNEL32!CompareFileTime` at `0x1800124aa`
- `KERNEL32!CompareFileTime` at `0x1800124aa`
- `ole32!StringFromIID` at `0x180012054`
- `ole32!StringFromIID` at `0x180012054`
- `ole32!CoTaskMemFree` at `0x1800122f3`
- `ole32!CoTaskMemFree` at `0x18001259a`
- `ole32!CoTaskMemFree` at `0x1800122f3`
- `ole32!CoTaskMemFree` at `0x18001259a`

## pseudocode

```c
__int64 __fastcall MetadataPackageSource::SetQueryIds(
        MetadataPackageSource *this,
        unsigned int a2,
        const unsigned __int16 *const *a3,
        const struct _GUID *a4)
{
  int v6; // r14d
  unsigned __int16 *v8; // r15
  __int64 v9; // rdi
  __int64 v10; // rbx
  HRESULT v11; // eax
  signed int v12; // r14d
  void (*v13)(void); // rax
  unsigned __int64 v14; // rcx
  _QWORD *v15; // rdx
  bool v16; // cc
  __int64 v17; // rax
  unsigned __int16 *v18; // rdx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rax
  unsigned __int16 *v22; // rdx
  int WorkItem; // eax
  __int16 v24; // dx
  bool Hwid; // al
  char BestPackage; // r13
  bool v28; // r12
  struct _MRC_STRUCT *v29; // rcx
  unsigned __int16 **v30; // r13
  struct _INDEX_STRUCT *v31; // r14
  char v32; // cl
  const wchar_t *v33; // r9
  bool v34; // cc
  char v35; // al
  LONG v36; // eax
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  _QWORD *v40; // rcx
  __int64 v41; // rdx
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  unsigned int v46; // [rsp+44h] [rbp-BCh]
  LPOLESTR lpsz; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v48; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v49; // [rsp+58h] [rbp-A8h] BYREF
  int v50[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE FileTime1[64]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE FileTime2[64]; // [rsp+B0h] [rbp-50h] BYREF

  v6 = a2;
  if ( !*((_BYTE *)this + 88) || *((_BYTE *)this + 89) )
    return 2147549183LL;
  lpsz = 0;
  v8 = 0;
  v9 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *(_QWORD *)v50 = v9;
  v10 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v49 = v10;
  if ( a4 )
  {
    v11 = StringFromIID(a4, &lpsz);
    LODWORD(a4) = 0;
    v12 = v11;
    if ( v11 < 0 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v10 - 24 + 16), 0xFFFFFFFF) > 1 )
        goto LABEL_41;
      v13 = *(void (**)(void))(**(_QWORD **)(v10 - 24) + 8LL);
      goto LABEL_40;
    }
    v14 = -1;
    do
      ++v14;
    while ( lpsz[v14] );
    if ( v14 < 0x26 )
    {
      if ( _InterlockedDecrement((volatile signed __int32 *)(v10 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 - 24) + 8LL))(*(_QWORD *)(v10 - 24));
      v15 = (_QWORD *)(v9 - 24);
      v16 = _InterlockedDecrement((volatile signed __int32 *)(v9 - 24 + 16)) <= 0;
LABEL_13:
      if ( v16 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 8LL))(*v15);
      v12 = -2147024882;
      goto LABEL_43;
    }
    lpsz[37] = 0;
    v8 = lpsz + 1;
    v17 = IndexCreateQueryTableKey(&v48, lpsz + 1, *((unsigned int *)this + 18), *((_QWORD *)this + 10));
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      &v49,
      v17);
    v18 = v48 - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)v48 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v18 + 8LL))(*(_QWORD *)v18);
    v10 = v49;
    if ( !*(_DWORD *)(v49 - 16) )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_23;
      v20 = 11;
LABEL_22:
      WPP_SF_(v19[2], v20, &WPP_81786cd8cf3b310d22fd5a7ce0f9edab_Traceguids);
LABEL_23:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v10 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 - 24) + 8LL))(*(_QWORD *)(v10 - 24));
      v15 = (_QWORD *)(v9 - 24);
      v16 = _InterlockedExchangeAdd((volatile signed __int32 *)(v9 - 24 + 16), 0xFFFFFFFF) <= 1;
      goto LABEL_13;
    }
    v6 = a2;
  }
  if ( a3 && v6 )
  {
    v21 = IndexCreateQueryTableKey(&v48, *a3, *((unsigned int *)this + 18), *((_QWORD *)this + 10));
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(v50, v21);
    v22 = v48 - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v48 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v22 + 8LL))(*(_QWORD *)v22);
    v9 = *(_QWORD *)v50;
    if ( *(_DWORD *)(*(_QWORD *)v50 - 16LL) == (_DWORD)a4 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_23;
      v20 = 12;
      goto LABEL_22;
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  WorkItem = WorkerCreateWorkItem(*((_QWORD *)g_pmrc + 8), v6, (int)a3, (int)v50, v8, (__int64)&v49, (__int64)this + 96);
  v12 = WorkItem;
  if ( WorkItem > 0 )
    v12 = (unsigned __int16)WorkItem | 0x80070000;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  if ( v12 < 0 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v10 - 24 + 16), 0xFFFFFFFF) > 1 )
      goto LABEL_41;
    v13 = *(void (**)(void))(**(_QWORD **)(v10 - 24) + 8LL);
LABEL_40:
    v13();
LABEL_41:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v9 - 24) + 8LL))(*(_QWORD *)(v9 - 24));
LABEL_43:
    CoTaskMemFree(lpsz);
    return (unsigned int)v12;
  }
  FileTime1[4] = 0;
  Hwid = 0;
  *(_DWORD *)FileTime1 = -1;
  *(_DWORD *)&FileTime1[8] = -1;
  *(_QWORD *)&FileTime1[12] = 0;
  BestPackage = 0;
  *(_DWORD *)FileTime2 = -1;
  FileTime2[4] = 0;
  *(_DWORD *)&FileTime2[8] = -1;
  *(_QWORD *)&FileTime2[12] = 0;
  memset(&FileTime1[24], 0, 40);
  memset(&FileTime2[24], 0, 40);
  if ( a3 && a2 )
    Hwid = IndexFindHwid(
             *((struct _INDEX **)g_pmrc + 5),
             v24,
             a2,
             a3,
             *((_DWORD *)this + 18),
             *((const unsigned __int16 *const **)this + 10),
             (struct PackageMatch *)FileTime1);
  v28 = Hwid;
  if ( v8 )
  {
    v29 = g_pmrc;
    v30 = (unsigned __int16 **)*((_QWORD *)this + 10);
    v46 = *((_DWORD *)this + 18);
    v31 = (struct _INDEX_STRUCT *)*((_QWORD *)g_pmrc + 5);
    v48 = v8;
    if ( !v31 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( *(_DWORD *)v31 != 1229866053 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (Microsoft_Windows_UserPnpEnableBits & 0x40) != 0 )
      McTemplateU0zz_EventWriteTransfer(v29, &DMRC_QUERY, L"Model Id", v8);
    BestPackage = FindBestPackage(v31, 1u, &v48, v46, v30, (struct PackageMatch *)FileTime2);
  }
  if ( v28 || (v32 = 0, BestPackage) )
    v32 = 1;
  *((_BYTE *)this + 104) = v32;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    if ( v28 && BestPackage )
    {
      v33 = L"two";
    }
    else
    {
      v33 = L"a";
      if ( !v32 )
        v33 = L"no";
    }
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_81786cd8cf3b310d22fd5a7ce0f9edab_Traceguids, v33);
  }
  if ( *((_BYTE *)this + 104) )
  {
    v34 = *(_DWORD *)FileTime1 <= *(_DWORD *)FileTime2;
    if ( *(_DWORD *)FileTime1 != *(_DWORD *)FileTime2 )
      goto LABEL_68;
    v35 = FileTime2[4];
    if ( FileTime1[4] != FileTime2[4] )
      goto LABEL_74;
    v34 = *(_DWORD *)&FileTime1[8] <= *(_DWORD *)&FileTime2[8];
    if ( *(_DWORD *)&FileTime1[8] == *(_DWORD *)&FileTime2[8] )
    {
      v36 = CompareFileTime((const FILETIME *)&FileTime1[12], (const FILETIME *)&FileTime2[12]);
      if ( !v36 )
        goto LABEL_78;
      v35 = v36 == -1;
    }
    else
    {
LABEL_68:
      if ( !v34 )
        goto LABEL_75;
      v35 = 0;
    }
LABEL_74:
    if ( v35 )
    {
LABEL_75:
      v37 = *(_OWORD *)&FileTime2[16];
      *((_OWORD *)this + 7) = *(_OWORD *)FileTime2;
      v38 = *(_OWORD *)&FileTime2[32];
      *((_OWORD *)this + 8) = v37;
      v39 = *(_OWORD *)&FileTime2[48];
      *((_OWORD *)this + 9) = v38;
      *((_OWORD *)this + 10) = v39;
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_82;
      v41 = 14;
      goto LABEL_81;
    }
LABEL_78:
    v42 = *(_OWORD *)&FileTime1[16];
    *((_OWORD *)this + 7) = *(_OWORD *)FileTime1;
    v43 = *(_OWORD *)&FileTime1[32];
    *((_OWORD *)this + 8) = v42;
    v44 = *(_OWORD *)&FileTime1[48];
    *((_OWORD *)this + 9) = v43;
    *((_OWORD *)this + 10) = v44;
    v40 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_82;
    v41 = 15;
LABEL_81:
    WPP_SF_(v40[2], v41, &WPP_81786cd8cf3b310d22fd5a7ce0f9edab_Traceguids);
  }
LABEL_82:
  *((_BYTE *)this + 89) = 1;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v10 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 - 24) + 8LL))(*(_QWORD *)(v10 - 24));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v9 - 24) + 8LL))(*(_QWORD *)(v9 - 24));
  CoTaskMemFree(lpsz);
  return 0;
}

```

## disassembly

```asm
0x180011fb0  push    rbp
0x180011fb2  push    rbx
0x180011fb3  push    rsi
0x180011fb4  push    rdi
0x180011fb5  push    r12
0x180011fb7  push    r13
0x180011fb9  push    r14
0x180011fbb  push    r15
0x180011fbd  lea     rbp, [rsp-8]
0x180011fc2  sub     rsp, 108h
0x180011fc9  mov     rax, cs:__security_cookie
0x180011fd0  xor     rax, rsp
0x180011fd3  mov     [rbp+40h+var_50], rax
0x180011fd7  xor     ebx, ebx
0x180011fd9  mov     [rsp+140h+var_FC], edx
0x180011fdd  mov     r13, r9
0x180011fe0  mov     r12, r8
0x180011fe3  mov     r14d, edx
0x180011fe6  mov     rsi, rcx
0x180011fe9  cmp     [rcx+58h], bl
0x180011fec  jz      loc_1800125A4
0x180011ff2  cmp     [rcx+59h], bl
0x180011ff5  jnz     loc_1800125A4
0x180011ffb  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180012002  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180012009  mov     [rsp+140h+lpsz], rbx
0x18001200e  mov     rax, [rax+18h]
0x180012012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012017  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001201e  mov     r15d, ebx
0x180012021  lea     rdi, [rax+18h]
0x180012025  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001202c  mov     qword ptr [rsp+140h+var_E0], rdi
0x180012031  mov     rax, [rax+18h]
0x180012035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001203a  lea     rbx, [rax+18h]
0x18001203e  mov     [rsp+140h+var_E8], rbx
0x180012043  test    r13, r13
0x180012046  jz      loc_1800121BC
0x18001204c  lea     rdx, [rsp+140h+lpsz]; lplpsz
0x180012051  mov     rcx, r13; rclsid
0x180012054  call    cs:__imp_StringFromIID
0x18001205a  xor     r13d, r13d
0x18001205d  mov     r14d, eax
0x180012060  test    eax, eax
0x180012062  jns     short loc_180012088
0x180012064  lea     rdx, [rbx-18h]
0x180012068  or      ecx, 0FFFFFFFFh
0x18001206b  lock xadd [rdx+10h], ecx
0x180012070  sub     ecx, 1
0x180012073  jg      loc_1800122CE
0x180012079  mov     rcx, [rdx]
0x18001207c  mov     r8, [rcx]
0x18001207f  mov     rax, [r8+8]
0x180012083  jmp     loc_1800122C9
0x180012088  mov     rax, [rsp+140h+lpsz]
0x18001208d  or      r14, 0FFFFFFFFFFFFFFFFh
0x180012091  mov     rcx, r14
0x180012094  inc     rcx
0x180012097  cmp     [rax+rcx*2], r13w
0x18001209c  jnz     short loc_180012094
0x18001209e  cmp     rcx, 26h ; '&'
0x1800120a2  jnb     short loc_1800120F3
0x1800120a4  lea     rdx, [rbx-18h]
0x1800120a8  mov     eax, r14d
0x1800120ab  lock xadd [rdx+10h], eax
0x1800120b0  add     eax, r14d
0x1800120b3  test    eax, eax
0x1800120b5  jg      short loc_1800120C6
0x1800120b7  mov     rcx, [rdx]
0x1800120ba  mov     rax, [rcx]
0x1800120bd  mov     rax, [rax+8]
0x1800120c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120c6  lea     rdx, [rdi-18h]
0x1800120ca  mov     eax, r14d
0x1800120cd  lock xadd [rdx+10h], eax
0x1800120d2  add     eax, r14d
0x1800120d5  test    eax, eax
0x1800120d7  jg      short loc_1800120E8
0x1800120d9  mov     rcx, [rdx]
0x1800120dc  mov     rax, [rcx]
0x1800120df  mov     rax, [rax+8]
0x1800120e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120e8  mov     r14d, 8007000Eh
0x1800120ee  jmp     loc_1800122EE
0x1800120f3  mov     [rax+4Ah], r13w
0x1800120f8  lea     rcx, [rsp+140h+var_F0]
0x1800120fd  mov     r15, [rsp+140h+lpsz]
0x180012102  mov     r9, [rsi+50h]
0x180012106  add     r15, 2
0x18001210a  mov     r8d, [rsi+48h]
0x18001210e  mov     rdx, r15
0x180012111  call    ?IndexCreateQueryTableKey@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGKPEBQEBG@Z; IndexCreateQueryTableKey(ushort const *,ulong,ushort const * const *)
0x180012116  mov     rdx, rax
0x180012119  lea     rcx, [rsp+140h+var_E8]
0x18001211e  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180012123  mov     rdx, [rsp+140h+var_F0]
0x180012128  mov     eax, r14d
0x18001212b  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18001212f  lock xadd [rdx+10h], eax
0x180012134  add     eax, r14d
0x180012137  test    eax, eax
0x180012139  jg      short loc_18001214A
0x18001213b  mov     rcx, [rdx]
0x18001213e  mov     rax, [rcx]
0x180012141  mov     rax, [rax+8]
0x180012145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001214a  mov     rbx, [rsp+140h+var_E8]
0x18001214f  cmp     [rbx-10h], r13d
0x180012153  jnz     short loc_1800121B7
0x180012155  mov     rcx, cs:WPP_GLOBAL_Control
0x18001215c  lea     r14, WPP_GLOBAL_Control
0x180012163  cmp     rcx, r14
0x180012166  jz      short loc_180012183
0x180012168  test    byte ptr [rcx+1Ch], 1
0x18001216c  jz      short loc_180012183
0x18001216e  mov     edx, 0Bh
0x180012173  mov     rcx, [rcx+10h]
0x180012177  lea     r8, WPP_81786cd8cf3b310d22fd5a7ce0f9edab_Traceguids
0x18001217e  call    WPP_SF_
0x180012183  lea     rdx, [rbx-18h]
0x180012187  or      eax, 0FFFFFFFFh
0x18001218a  lock xadd [rdx+10h], eax
0x18001218f  sub     eax, 1
0x180012192  jg      short loc_1800121A3
0x180012194  mov     rcx, [rdx]
0x180012197  mov     rax, [rcx]
0x18001219a  mov     rax, [rax+8]
0x18001219e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121a3  lea     rdx, [rdi-18h]
0x1800121a7  or      eax, 0FFFFFFFFh
0x1800121aa  lock xadd [rdx+10h], eax
0x1800121af  sub     eax, 1
0x1800121b2  jmp     loc_1800120D7
0x1800121b7  mov     r14d, [rsp+140h+var_FC]
0x1800121bc  test    r12, r12
0x1800121bf  jz      loc_180012248
0x1800121c5  test    r14d, r14d
0x1800121c8  jz      short loc_180012248
0x1800121ca  mov     r9, [rsi+50h]
0x1800121ce  lea     rcx, [rsp+140h+var_F0]
0x1800121d3  mov     r8d, [rsi+48h]
0x1800121d7  mov     rdx, [r12]
0x1800121db  call    ?IndexCreateQueryTableKey@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGKPEBQEBG@Z; IndexCreateQueryTableKey(ushort const *,ulong,ushort const * const *)
0x1800121e0  mov     rdx, rax
0x1800121e3  lea     rcx, [rsp+140h+var_E0]
0x1800121e8  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800121ed  mov     rdx, [rsp+140h+var_F0]
0x1800121f2  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800121f6  or      eax, 0FFFFFFFFh
0x1800121f9  lock xadd [rdx+10h], eax
0x1800121fe  sub     eax, 1
0x180012201  jg      short loc_180012212
0x180012203  mov     rcx, [rdx]
0x180012206  mov     rax, [rcx]
0x180012209  mov     rax, [rax+8]
0x18001220d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012212  mov     rdi, qword ptr [rsp+140h+var_E0]
0x180012217  cmp     [rdi-10h], r13d
0x18001221b  jnz     short loc_180012248
0x18001221d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012224  lea     r14, WPP_GLOBAL_Control
0x18001222b  cmp     rcx, r14
0x18001222e  jz      loc_180012183
0x180012234  test    byte ptr [rcx+1Ch], 1
0x180012238  jz      loc_180012183
0x18001223e  mov     edx, 0Ch
0x180012243  jmp     loc_180012173
0x180012248  lea     r13, [rsi+0B0h]
0x18001224f  mov     rcx, r13; lpCriticalSection
0x180012252  call    cs:__imp_EnterCriticalSection
0x180012258  mov     rcx, cs:?g_pmrc@@3PEAU_MRC_STRUCT@@EA; _MRC_STRUCT * g_pmrc
0x18001225f  lea     rax, [rsi+60h]
0x180012263  mov     [rsp+140h+var_110], rax; __int64
0x180012268  lea     r9, [rsp+140h+var_E0]; int
0x18001226d  lea     rax, [rsp+140h+var_E8]
0x180012272  mov     r8, r12; int
0x180012275  mov     [rsp+140h+var_118], rax; __int64
0x18001227a  mov     edx, r14d; int
0x18001227d  mov     rcx, [rcx+40h]; int
0x180012281  mov     [rsp+140h+var_120], r15; unsigned __int16 *
0x180012286  call    ?WorkerCreateWorkItem@@YAKPEAUUNNAMED_STRUCT_WORKER@@KPEBQEBGAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG2AEAPEAU_WORKITEM@@@Z; WorkerCreateWorkItem(UNNAMED_STRUCT_WORKER *,ulong,ushort const * const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_WORKITEM * &)
0x18001228b  mov     r14d, eax
0x18001228e  test    eax, eax
0x180012290  jle     short loc_18001229D
0x180012292  movzx   r14d, ax
0x180012296  or      r14d, 80070000h
0x18001229d  mov     rcx, r13; lpCriticalSection
0x1800122a0  call    cs:__imp_LeaveCriticalSection
0x1800122a6  xor     r10d, r10d
0x1800122a9  test    r14d, r14d
0x1800122ac  jns     short loc_180012301
0x1800122ae  lea     rdx, [rbx-18h]
0x1800122b2  or      eax, 0FFFFFFFFh
0x1800122b5  lock xadd [rdx+10h], eax
0x1800122ba  sub     eax, 1
0x1800122bd  jg      short loc_1800122CE
0x1800122bf  mov     rcx, [rdx]
0x1800122c2  mov     rax, [rcx]
0x1800122c5  mov     rax, [rax+8]
0x1800122c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122ce  lea     rdx, [rdi-18h]
0x1800122d2  or      eax, 0FFFFFFFFh
0x1800122d5  lock xadd [rdx+10h], eax
0x1800122da  sub     eax, 1
0x1800122dd  jg      short loc_1800122EE
0x1800122df  mov     rcx, [rdx]
0x1800122e2  mov     rax, [rcx]
0x1800122e5  mov     rax, [rax+8]
0x1800122e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122ee  mov     rcx, [rsp+140h+lpsz]; pv
0x1800122f3  call    cs:__imp_CoTaskMemFree
0x1800122f9  mov     eax, r14d
0x1800122fc  jmp     loc_1800125A9
0x180012301  or      ecx, 0FFFFFFFFh
0x180012304  mov     byte ptr [rsp+140h+FileTime1.dwHighDateTime], r10b
0x180012309  xor     eax, eax
0x18001230b  mov     [rsp+140h+FileTime1.dwLowDateTime], ecx
0x18001230f  mov     [rsp+140h+FileTime1.dwLowDateTime+8], ecx
0x180012313  xorps   xmm0, xmm0
0x180012316  mov     qword ptr [rsp+140h+FileTime1.dwHighDateTime+8], rax
0x18001231b  mov     r13b, r10b
0x18001231e  mov     [rbp+40h+var_98], rax
0x180012322  mov     [rbp+40h+FileTime2.dwLowDateTime], ecx
0x180012325  mov     byte ptr [rbp+40h+FileTime2.dwHighDateTime], r10b
0x180012329  mov     [rbp+40h+FileTime2.dwLowDateTime+8], ecx
0x18001232c  mov     qword ptr [rbp+40h+FileTime2.dwHighDateTime+8], rax
0x180012330  mov     [rbp+40h+var_58], rax
0x180012334  movups  [rbp+40h+var_B8], xmm0
0x180012338  movups  [rbp+40h+var_A8], xmm0
0x18001233c  movups  [rbp+40h+var_78], xmm0
0x180012340  movups  [rbp+40h+var_68], xmm0
0x180012344  test    r12, r12
0x180012347  jz      short loc_180012383
0x180012349  mov     r8d, [rsp+140h+var_FC]; unsigned int
0x18001234e  test    r8d, r8d
0x180012351  jz      short loc_180012383
0x180012353  mov     rcx, cs:?g_pmrc@@3PEAU_MRC_STRUCT@@EA; _MRC_STRUCT * g_pmrc
0x18001235a  lea     rax, [rsp+140h+FileTime1]
0x18001235f  mov     [rsp+140h+var_110], rax; struct PackageMatch *
0x180012364  mov     r9, r12; unsigned __int16 **
0x180012367  mov     rax, [rsi+50h]
0x18001236b  mov     [rsp+140h+var_118], rax; unsigned __int16 **
0x180012370  mov     eax, [rsi+48h]
0x180012373  mov     rcx, [rcx+28h]; struct _INDEX *
0x180012377  mov     dword ptr [rsp+140h+var_120], eax; unsigned int
0x18001237b  call    ?IndexFindHwid@@YA_NPEAU_INDEX@@FKQEBQEBGKPEBQEBGPEAUPackageMatch@@@Z; IndexFindHwid(_INDEX *,short,ulong,ushort const * const * const,ulong,ushort const * const *,PackageMatch *)
0x180012380  xor     r10d, r10d
0x180012383  mov     r12b, al
0x180012386  test    r15, r15
0x180012389  jz      short loc_180012408
0x18001238b  mov     rcx, cs:?g_pmrc@@3PEAU_MRC_STRUCT@@EA; _MRC_STRUCT * g_pmrc
0x180012392  mov     eax, [rsi+48h]
0x180012395  mov     r13, [rsi+50h]
0x180012399  mov     [rsp+140h+var_FC], eax
0x18001239d  mov     r14, [rcx+28h]
0x1800123a1  mov     [rsp+140h+var_F0], r15
0x1800123a6  test    r14, r14
0x1800123a9  jnz     short loc_1800123B0
0x1800123ab  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800123b0  cmp     dword ptr [r14], 494E4445h
0x1800123b7  jz      short loc_1800123BE
0x1800123b9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800123be  test    cs:Microsoft_Windows_UserPnpEnableBits, 40h
0x1800123c5  jz      short loc_1800123DD
0x1800123c7  mov     r9, r15
0x1800123ca  lea     r8, aModelId; "Model Id"
0x1800123d1  lea     rdx, DMRC_QUERY
0x1800123d8  call    McTemplateU0zz_EventWriteTransfer
0x1800123dd  mov     r9d, [rsp+140h+var_FC]; unsigned int
0x1800123e2  lea     rax, [rbp+40h+FileTime2]
0x1800123e6  mov     [rsp+140h+var_118], rax; struct PackageMatch *
0x1800123eb  lea     r8, [rsp+140h+var_F0]; unsigned __int16 **
0x1800123f0  mov     edx, 1; unsigned int
0x1800123f5  mov     [rsp+140h+var_120], r13; unsigned __int16 **
0x1800123fa  mov     rcx, r14; struct _INDEX_STRUCT *
0x1800123fd  call    FindBestPackage
0x180012402  mov     r13b, al
0x180012405  xor     r10d, r10d
0x180012408  test    r12b, r12b
0x18001240b  jnz     short loc_180012415
0x18001240d  mov     cl, r10b
0x180012410  test    r13b, r13b
0x180012413  jz      short loc_180012417
0x180012415  mov     cl, 1
0x180012417  mov     [rsi+68h], cl
0x18001241a  mov     rax, cs:WPP_GLOBAL_Control
0x180012421  lea     r14, WPP_GLOBAL_Control
0x180012428  mov     r15b, 8
0x18001242b  cmp     rax, r14
0x18001242e  jz      short loc_180012475
0x180012430  test    [rax+1Ch], r15b
0x180012434  jz      short loc_180012475
0x180012436  test    r12b, r12b
0x180012439  jz      short loc_180012449
0x18001243b  test    r13b, r13b
0x18001243e  jz      short loc_180012449
0x180012440  lea     r9, aTwo; "two"
0x180012447  jmp     short loc_18001245D
0x180012449  test    cl, cl
  ... truncated ...
```
