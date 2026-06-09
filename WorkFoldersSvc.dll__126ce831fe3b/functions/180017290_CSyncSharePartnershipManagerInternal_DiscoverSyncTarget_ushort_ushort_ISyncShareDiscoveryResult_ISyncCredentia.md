# CSyncSharePartnershipManagerInternal::DiscoverSyncTarget(ushort *,ushort *,ISyncShareDiscoveryResult * *,ISyncCredentialsInfo * *)

- ea: `0x180017290`
- end: `0x180017acc`
- name: `?DiscoverSyncTarget@CSyncSharePartnershipManagerInternal@@UEAAJPEAG0PEAPEAUISyncShareDiscoveryResult@@PEAPEAUISyncCredentialsInfo@@@Z`
- size: `2108`
- prototype: `int(CSyncSharePartnershipManagerInternal *__hidden this, unsigned __int16 *, unsigned __int16 *, struct ISyncShareDiscoveryResult **, struct ISyncCredentialsInfo **)`
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180003604`
- `0x180007e10`
- `0x180007f1c`
- `0x180008b60`
- `0x180009158`
- `0x180010f40`
- `0x180011314`
- `0x18001511c`
- `0x1800151d8`
- `0x1800155e0`
- `0x1800162b8`
- `0x1800163b8`
- `0x1800164c4`
- `0x180017290`
- `0x180019db8`
- `0x180019f8c`
- `0x18001a0d0`
- `0x18001daf8`
- `0x1800215e0`
- `0x1800216e0`
- `0x180023e64`
- `0x1800251b0`
- `0x18013e010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180017393`
- `OLEAUT32!__imp_SysStringLen` at `0x1800173b6`
- `OLEAUT32!__imp_SysStringLen` at `0x180017393`
- `OLEAUT32!__imp_SysStringLen` at `0x1800173b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800177b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800177b7`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800173ed`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800173ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall CSyncSharePartnershipManagerInternal::DiscoverSyncTarget(
        CSyncSharePartnershipManagerInternal *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct ISyncShareDiscoveryResult **a4,
        struct ISyncCredentialsInfo **a5)
{
  OLECHAR *v6; // r14
  OLECHAR *v7; // rsi
  _BYTE *v9; // rax
  char v10; // di
  char v11; // al
  HRESULT v12; // eax
  __int16 v13; // r12
  __int16 v14; // r15
  _WORD *i; // rcx
  unsigned __int16 v16; // ax
  signed int v17; // eax
  CSyncShareDiscoveryResult *v18; // r13
  signed int v19; // eax
  __int16 v20; // r9
  __int16 v21; // ax
  const unsigned __int16 *v22; // r8
  const unsigned __int16 *v23; // rdx
  const unsigned __int16 *v24; // r8
  int v25; // ecx
  unsigned __int16 **v26; // rax
  CSyncShareDiscoveryResult *v27; // rax
  unsigned __int64 v28; // rdx
  int v29; // ecx
  signed int v30; // eax
  _QWORD *v31; // r8
  _QWORD *v32; // rdx
  signed int v33; // ecx
  DWORD v34; // ebx
  struct ISyncCredentialsInfo *v36; // rdx
  DWORD dwMessageId; // [rsp+50h] [rbp-A08h] BYREF
  int v38; // [rsp+54h] [rbp-A04h]
  char v39; // [rsp+58h] [rbp-A00h]
  const char *v40; // [rsp+60h] [rbp-9F8h]
  __int64 v41; // [rsp+68h] [rbp-9F0h]
  char v42; // [rsp+70h] [rbp-9E8h]
  char v43; // [rsp+71h] [rbp-9E7h]
  CSyncShareExtendedInfo *v44; // [rsp+78h] [rbp-9E0h] BYREF
  unsigned __int16 *v45; // [rsp+80h] [rbp-9D8h]
  unsigned __int16 *v46; // [rsp+88h] [rbp-9D0h]
  unsigned __int16 v47; // [rsp+90h] [rbp-9C8h]
  HRESULT pExceptionObject; // [rsp+94h] [rbp-9C4h] BYREF
  signed int v49; // [rsp+98h] [rbp-9C0h] BYREF
  signed int v50; // [rsp+9Ch] [rbp-9BCh] BYREF
  int v51; // [rsp+A0h] [rbp-9B8h] BYREF
  int v52; // [rsp+A4h] [rbp-9B4h] BYREF
  int v53; // [rsp+A8h] [rbp-9B0h] BYREF
  signed int v54; // [rsp+ACh] [rbp-9ACh] BYREF
  signed int v55; // [rsp+B0h] [rbp-9A8h] BYREF
  int v56; // [rsp+B4h] [rbp-9A4h] BYREF
  CSyncShareDiscoveryResult *v57; // [rsp+B8h] [rbp-9A0h] BYREF
  struct ISyncCredentialsInfo **v58; // [rsp+C0h] [rbp-998h]
  CSyncShareDiscoveryResult *v59; // [rsp+C8h] [rbp-990h] BYREF
  unsigned __int64 v60; // [rsp+D0h] [rbp-988h] BYREF
  struct ISyncShareExtendedInfo *v61; // [rsp+D8h] [rbp-980h] BYREF
  struct ISyncCredentialsInfo *v62; // [rsp+E0h] [rbp-978h] BYREF
  DWORD v63; // [rsp+E8h] [rbp-970h] BYREF
  _WORD *v64; // [rsp+F0h] [rbp-968h]
  struct ISyncShareDiscoveryResult **v65; // [rsp+F8h] [rbp-960h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+100h] [rbp-958h] BYREF
  char v67; // [rsp+108h] [rbp-950h]
  __int128 v68; // [rsp+110h] [rbp-948h] BYREF
  __int64 v69; // [rsp+120h] [rbp-938h]
  DWORD *v70; // [rsp+130h] [rbp-928h] BYREF
  _QWORD v71[4]; // [rsp+140h] [rbp-918h] BYREF
  _QWORD v72[4]; // [rsp+160h] [rbp-8F8h] BYREF
  int v73; // [rsp+180h] [rbp-8D8h]
  unsigned int v74; // [rsp+184h] [rbp-8D4h]
  unsigned __int16 *v75[2]; // [rsp+190h] [rbp-8C8h] BYREF
  __int64 v76; // [rsp+1A0h] [rbp-8B8h]
  unsigned __int64 v77; // [rsp+1A8h] [rbp-8B0h]
  unsigned __int16 *v78[2]; // [rsp+1B0h] [rbp-8A8h] BYREF
  __int64 v79; // [rsp+1C0h] [rbp-898h]
  unsigned __int64 v80; // [rsp+1C8h] [rbp-890h]
  unsigned __int16 *v81[2]; // [rsp+1D0h] [rbp-888h] BYREF
  __int64 v82; // [rsp+1E0h] [rbp-878h]
  unsigned __int64 v83; // [rsp+1E8h] [rbp-870h]
  unsigned __int64 v84[4]; // [rsp+1F0h] [rbp-868h] BYREF
  unsigned __int16 v85; // [rsp+210h] [rbp-848h] BYREF
  char v86[2046]; // [rsp+212h] [rbp-846h] BYREF

  v65 = a4;
  v6 = a3;
  v7 = a2;
  v45 = a2;
  v46 = a3;
  v58 = a5;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 75, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
  }
  if ( (v9[68] & 8) != 0 && v9[65] >= 6u )
  {
    v10 = 1;
    v11 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v11 = 0;
  v10 = 1;
LABEL_9:
  dwMessageId = 0;
  v38 = 1140;
  v39 = v11;
  v40 = "CSyncSharePartnershipManagerInternal::DiscoverSyncTarget";
  v41 = 0;
  if ( a4 )
    *a4 = 0;
  if ( v58 )
    *v58 = 0;
  AuthenticationInfo::AuthenticationInfo((AuthenticationInfo *)v71);
  try
  {
    if ( !SysStringLen(v7) )
    {
      dwMessageId = -2147024809;
      HIWORD(v38) = 1148;
      v53 = -2147024809;
      throw (long *)&v53;
    }
    LOWORD(v38) = 1148;
    dwMessageId = 0;
    if ( !SysStringLen(v6) )
    {
      dwMessageId = -2147024809;
      HIWORD(v38) = 1149;
      v52 = -2147024809;
      throw (long *)&v52;
    }
    LOWORD(v38) = 1149;
    dwMessageId = 0;
    if ( !a4 )
    {
      dwMessageId = -2147024809;
      HIWORD(v38) = 1150;
      v51 = -2147024809;
      throw (long *)&v51;
    }
    LOWORD(v38) = 1150;
    v12 = CoImpersonateClient();
    dwMessageId = v12;
    if ( v12 < 0 )
    {
      HIWORD(v38) = 1152;
      pExceptionObject = v12;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v38) = 1152;
    CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(
      (__int64)&lpCriticalSection,
      (struct _RTL_CRITICAL_SECTION *)((char *)this + 216));
    CSyncStateManager::AddImpersonatingUser(*((CSyncStateManager **)this + 18), (__int64)v84);
    std::wstring::_Tidy_deallocate(v84);
    *(_OWORD *)v75 = 0;
    v76 = 0;
    v77 = 7;
    LOWORD(v75[0]) = 0;
    *(_OWORD *)v81 = 0;
    v82 = 0;
    v83 = 7;
    LOWORD(v81[0]) = 0;
    v60 = 0;
    *(_OWORD *)v84 = 0;
    v68 = 0;
    v69 = 0;
    *(_OWORD *)v78 = 0;
    v79 = 0;
    v80 = 7;
    LOWORD(v78[0]) = 0;
    LOBYTE(v13) = 0;
    v42 = 0;
    LOBYTE(v14) = 0;
    v43 = 0;
    CSyncStateManager::DiscoverSyncShare(
      *((_QWORD *)this + 18),
      (_DWORD)v7,
      (_DWORD)v6,
      (unsigned int)v75,
      (__int64)v81,
      (__int64)&v60,
      (__int64)v71,
      (__int64)v84,
      (__int64)&v68,
      (__int64)v78);
    for ( i = (_WORD *)v68; ; ++i )
    {
      v64 = i;
      if ( i == *((_WORD **)&v68 + 1) )
        break;
      v16 = *i;
      v47 = v16;
      if ( (_BYTE)v16 == 2 )
      {
        v13 = HIBYTE(v16);
        v42 = HIBYTE(v16);
      }
      if ( (_BYTE)v16 == 1 )
      {
        v14 = HIBYTE(v16);
        v43 = HIBYTE(v16);
      }
    }
    v59 = 0;
    v17 = ATL::CComObject<CSyncShareDiscoveryResult>::CreateInstance(&v59);
    dwMessageId = v17;
    if ( v17 < 0 )
    {
      HIWORD(v38) = 1183;
      v49 = v17;
      throw (long *)&v49;
    }
    LOWORD(v38) = 1183;
    v18 = v59;
    v57 = v59;
    if ( v59 )
      (*(void (__fastcall **)(CSyncShareDiscoveryResult *))(*(_QWORD *)v59 + 8LL))(v59);
    v44 = 0;
    v19 = ATL::CComObject<CSyncShareExtendedInfo>::CreateInstance(&v44);
    dwMessageId = v19;
    if ( v19 < 0 )
    {
      HIWORD(v38) = 1187;
      v50 = v19;
      throw (long *)&v50;
    }
    LOWORD(v38) = 1187;
    v20 = -1;
    v21 = -1;
    if ( !(_BYTE)v14 )
      v21 = 0;
    if ( !(_BYTE)v13 )
      v20 = 0;
    v22 = (const unsigned __int16 *)v78;
    if ( v80 > 7 )
      v22 = v78[0];
    v23 = (const unsigned __int16 *)v81;
    if ( v83 > 7 )
      v23 = v81[0];
    CSyncShareExtendedInfo::Initialize(v44, v23, v22, v20, v21, v84[0], v60);
    ATL::CComPtr<ISyncShareExtendedInfo>::CComPtr<ISyncShareExtendedInfo>(&v61, (__int64)v44);
    v24 = (const unsigned __int16 *)v75;
    if ( v77 > 7 )
      v24 = v75[0];
    CSyncShareDiscoveryResult::Initialize(v18, v7, v24, v61);
    if ( (Microsoft_Windows_WorkFoldersEnableBits & 1) != 0 )
    {
      v26 = v75;
      if ( v77 > 7 )
        v26 = (unsigned __int16 **)v75[0];
      McTemplateU0zzz_EventWriteTransfer(
        v25,
        (unsigned int)ECSHOST_EVENT_DISCOVER_SYNC_TARGET,
        (_DWORD)v7,
        (_DWORD)v6,
        (__int64)v26);
    }
    v27 = v57;
    v57 = 0;
    *v65 = v27;
    ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v61);
    ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v57);
    std::wstring::_Tidy_deallocate(v78);
    std::vector<PolicyEntry>::_Tidy(&v68);
    std::wstring::_Tidy_deallocate(v81);
    std::wstring::_Tidy_deallocate(v75);
    if ( v67 )
    {
      LeaveCriticalSection(lpCriticalSection);
      v67 = 0;
    }
  }
  catch ( long v63 )
  {
    dwMessageId = v63;
    LODWORD(v6) = (_DWORD)v46;
    LODWORD(v7) = (_DWORD)v45;
    v10 = 1;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v38) = 1206;
    dwMessageId = -2147024882;
    LODWORD(v6) = (_DWORD)v46;
    LODWORD(v7) = (_DWORD)v45;
    v10 = 1;
  }
  catch ( std::exception )
  {
    HIWORD(v38) = 1206;
    dwMessageId = -2147418113;
    LODWORD(v6) = (_DWORD)v46;
    LODWORD(v7) = (_DWORD)v45;
    v10 = 1;
  }
  catch ( const ATL::CAtlException *v70 )
  {
    HIWORD(v38) = 1206;
    dwMessageId = *v70;
    LODWORD(v6) = (_DWORD)v46;
    LODWORD(v7) = (_DWORD)v45;
    v10 = 1;
  }
  if ( (dwMessageId & 0x80000000) != 0 && (Microsoft_Windows_WorkFoldersEnableBits & 2) != 0 )
  {
    v85 = 0;
    memset_0(v86, 0, sizeof(v86));
    CEcsFunctionTracer::GetErrorText(dwMessageId, v28, &v85);
    McTemplateU0zzzd_EventWriteTransfer(
      v29,
      (unsigned int)ECSHOST_EVENT_DISCOVER_SYNC_TARGET_FAILED,
      (_DWORD)v7,
      (_DWORD)v6,
      (__int64)&v85,
      dwMessageId);
  }
  if ( dwMessageId == -2134375680 )
  {
    v44 = 0;
    v30 = ATL::CComObject<CSyncCredentialsInfo>::CreateInstance(&v44);
    dwMessageId = v30;
    if ( v30 >= 0 )
    {
      LOWORD(v38) = 1218;
      ATL::CComPtr<ISyncShareExtendedInfo>::CComPtr<ISyncShareExtendedInfo>(&v62, (__int64)v44);
      v31 = v72;
      if ( v72[3] > 7u )
        v31 = (_QWORD *)v72[0];
      if ( v71[3] <= 7u )
        v10 = 0;
      v32 = v71;
      if ( v10 )
        v32 = (_QWORD *)v71[0];
      v33 = CSyncCredentialsInfo::Initialize(v44, v32, v31, v74, v73);
      dwMessageId = v33;
      if ( v33 < 0 )
      {
        HIWORD(v38) = 1223;
        v55 = v33;
        throw (long *)&v55;
      }
      LOWORD(v38) = 1223;
      v36 = v62;
      v62 = 0;
      *v58 = v36;
      dwMessageId = -2134375680;
      HIWORD(v38) = 1226;
      v56 = -2134375680;
      throw (long *)&v56;
    }
    HIWORD(v38) = 1218;
    v54 = v30;
    throw (long *)&v54;
  }
  v34 = dwMessageId;
  DiscoverSyncShareResponseType::~DiscoverSyncShareResponseType((DiscoverSyncShareResponseType *)v71);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&dwMessageId);
  return v34;
}

```

## disassembly

```asm
0x180017290  push    rbx
0x180017292  push    rsi
0x180017293  push    rdi
0x180017294  push    r12
0x180017296  push    r13
0x180017298  push    r14
0x18001729a  push    r15
0x18001729c  sub     rsp, 0A20h
0x1800172a3  mov     rax, cs:__security_cookie
0x1800172aa  xor     rax, rsp
0x1800172ad  mov     [rsp+0A58h+var_48], rax
0x1800172b5  mov     r15, r9
0x1800172b8  mov     [rsp+0A58h+var_960], r9
0x1800172c0  mov     r14, r8
0x1800172c3  mov     rsi, rdx
0x1800172c6  mov     r13, rcx
0x1800172c9  mov     [rsp+0A58h+var_9D8], rdx
0x1800172d1  mov     [rsp+0A58h+var_9D0], r8
0x1800172d9  mov     rax, [rsp+0A58h+arg_20]
0x1800172e1  mov     [rsp+0A58h+var_998], rax
0x1800172e9  lea     rcx, WPP_GLOBAL_Control
0x1800172f0  mov     rax, cs:WPP_GLOBAL_Control
0x1800172f7  cmp     rax, rcx
0x1800172fa  jz      short loc_180017324
0x1800172fc  test    byte ptr [rax+44h], 8
0x180017300  jz      short loc_18001733A
0x180017302  cmp     byte ptr [rax+41h], 6
0x180017306  jb      short loc_180017324
0x180017308  mov     edx, 4Bh ; 'K'
0x18001730d  lea     r8, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids
0x180017314  mov     rcx, [rax+38h]
0x180017318  call    WPP_SF_
0x18001731d  mov     rax, cs:WPP_GLOBAL_Control
0x180017324  test    byte ptr [rax+44h], 8
0x180017328  jz      short loc_18001733A
0x18001732a  cmp     byte ptr [rax+41h], 6
0x18001732e  jb      short loc_18001733A
0x180017330  mov     dil, 1
0x180017333  mov     al, dil
0x180017336  xor     ebx, ebx
0x180017338  jmp     short loc_180017341
0x18001733a  xor     ebx, ebx
0x18001733c  mov     al, bl
0x18001733e  mov     dil, 1
0x180017341  mov     [rsp+0A58h+dwMessageId], ebx
0x180017345  mov     [rsp+0A58h+var_A04], 474h
0x18001734d  mov     [rsp+0A58h+var_A00], al
0x180017351  lea     rax, aCsyncsharepart_26; "CSyncSharePartnershipManagerInternal::D"...
0x180017358  mov     [rsp+0A58h+var_9F8], rax
0x18001735d  mov     [rsp+0A58h+var_9F0], rbx
0x180017362  test    r15, r15
0x180017365  jz      short loc_18001736A
0x180017367  mov     [r15], rbx
0x18001736a  mov     rax, [rsp+0A58h+var_998]
0x180017372  test    rax, rax
0x180017375  jz      short loc_18001737A
0x180017377  mov     [rax], rbx
0x18001737a  lea     rcx, [rsp+0A58h+var_918]; this
0x180017382  call    ??0AuthenticationInfo@@QEAA@XZ; AuthenticationInfo::AuthenticationInfo(void)
0x180017387  nop
0x180017388  mov     eax, [rsp+0A58h+dwMessageId]
0x18001738c  mov     [rsp+0A58h+dwMessageId], eax
0x180017390  mov     rcx, rsi; pbstr
0x180017393  call    cs:__imp_SysStringLen
0x180017399  mov     ecx, 47Ch
0x18001739e  test    eax, eax
0x1800173a0  jz      loc_180017A12
0x1800173a6  mov     [rsp+0A58h+dwMessageId], ebx
0x1800173aa  mov     word ptr [rsp+0A58h+var_A04], cx
0x1800173af  mov     [rsp+0A58h+dwMessageId], ebx
0x1800173b3  mov     rcx, r14; pbstr
0x1800173b6  call    cs:__imp_SysStringLen
0x1800173bc  mov     ecx, 47Dh
0x1800173c1  test    eax, eax
0x1800173c3  jz      loc_1800179E9
0x1800173c9  mov     [rsp+0A58h+dwMessageId], ebx
0x1800173cd  mov     word ptr [rsp+0A58h+var_A04], cx
0x1800173d2  mov     [rsp+0A58h+dwMessageId], ebx
0x1800173d6  mov     ecx, 47Eh
0x1800173db  test    r15, r15
0x1800173de  jz      loc_1800179C0
0x1800173e4  mov     [rsp+0A58h+dwMessageId], ebx
0x1800173e8  mov     word ptr [rsp+0A58h+var_A04], cx
0x1800173ed  call    cs:__imp_CoImpersonateClient
0x1800173f3  mov     [rsp+0A58h+dwMessageId], eax
0x1800173f7  mov     [rsp+0A58h+dwMessageId], eax
0x1800173fb  mov     ecx, 480h
0x180017400  test    eax, eax
0x180017402  js      loc_18001795D
0x180017408  mov     word ptr [rsp+0A58h+var_A04], cx
0x18001740d  lea     rdx, [r13+0D8h]
0x180017414  lea     rcx, [rsp+0A58h+lpCriticalSection]
0x18001741c  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x180017421  nop
0x180017422  lea     rdx, [rsp+0A58h+var_868]
0x18001742a  mov     rcx, [r13+90h]; this
0x180017431  call    ?AddImpersonatingUser@CSyncStateManager@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CSyncStateManager::AddImpersonatingUser(void)
0x180017436  lea     rcx, [rsp+0A58h+var_868]
0x18001743e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017443  xorps   xmm0, xmm0
0x180017446  movups  xmmword ptr [rsp+0A58h+var_8C8], xmm0
0x18001744e  mov     [rsp+0A58h+var_8B8], rbx
0x180017456  mov     [rsp+0A58h+var_8B0], rbx
0x18001745e  mov     [rsp+0A58h+var_8B8], rbx
0x180017466  mov     [rsp+0A58h+var_8B0], 7
0x180017472  mov     word ptr [rsp+0A58h+var_8C8], bx
0x18001747a  movups  xmmword ptr [rsp+0A58h+var_888], xmm0
0x180017482  mov     [rsp+0A58h+var_878], rbx
0x18001748a  mov     [rsp+0A58h+var_870], rbx
0x180017492  mov     [rsp+0A58h+var_878], rbx
0x18001749a  mov     [rsp+0A58h+var_870], 7
0x1800174a6  mov     word ptr [rsp+0A58h+var_888], bx
0x1800174ae  mov     [rsp+0A58h+var_988], rbx
0x1800174b6  movups  xmmword ptr [rsp+0A58h+var_868], xmm0
0x1800174be  xorps   xmm1, xmm1
0x1800174c1  movdqu  [rsp+0A58h+var_948], xmm1
0x1800174ca  mov     [rsp+0A58h+var_938], rbx
0x1800174d2  movups  xmmword ptr [rsp+0A58h+var_8A8], xmm0
0x1800174da  mov     [rsp+0A58h+var_898], rbx
0x1800174e2  mov     [rsp+0A58h+var_890], rbx
0x1800174ea  mov     [rsp+0A58h+var_898], rbx
0x1800174f2  mov     [rsp+0A58h+var_890], 7
0x1800174fe  mov     word ptr [rsp+0A58h+var_8A8], bx
0x180017506  mov     r12b, bl
0x180017509  mov     [rsp+0A58h+var_9E8], bl
0x18001750d  mov     r15b, bl
0x180017510  mov     [rsp+0A58h+var_9E7], bl
0x180017514  lea     rax, [rsp+0A58h+var_8A8]
0x18001751c  mov     [rsp+0A58h+var_A10], rax
0x180017521  lea     rax, [rsp+0A58h+var_948]
0x180017529  mov     [rsp+0A58h+var_A18], rax
0x18001752e  lea     rax, [rsp+0A58h+var_868]
0x180017536  mov     [rsp+0A58h+var_A20], rax
0x18001753b  lea     rax, [rsp+0A58h+var_918]
0x180017543  mov     [rsp+0A58h+var_A28], rax
0x180017548  lea     rax, [rsp+0A58h+var_988]
0x180017550  mov     [rsp+0A58h+var_A30], rax
0x180017555  lea     rax, [rsp+0A58h+var_888]
0x18001755d  mov     qword ptr [rsp+0A58h+var_A38], rax
0x180017562  lea     r9, [rsp+0A58h+var_8C8]
0x18001756a  mov     r8, r14
0x18001756d  mov     rdx, rsi
0x180017570  mov     rcx, [r13+90h]
0x180017577  call    ?DiscoverSyncShare@CSyncStateManager@@QEAAXPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1AEA_KAEAUAuthenticationInfo@@AEAUQuotaUsageEntry@@AEAV?$vector@UPolicyEntry@@V?$allocator@UPolicyEntry@@@std@@@3@1@Z; CSyncStateManager::DiscoverSyncShare(ushort const *,ushort const *,std::wstring &,std::wstring &,unsigned __int64 &,AuthenticationInfo &,QuotaUsageEntry &,std::vector<PolicyEntry> &,std::wstring &)
0x18001757c  mov     rcx, qword ptr [rsp+0A58h+var_948]
0x180017584  mov     [rsp+0A58h+var_968], rcx
0x18001758c  cmp     rcx, qword ptr [rsp+0A58h+var_948+8]
0x180017594  jz      short loc_1800175CC
0x180017596  movzx   eax, word ptr [rcx]
0x180017599  mov     [rsp+0A58h+var_9C8], ax
0x1800175a1  cmp     al, 2
0x1800175a3  jnz     short loc_1800175B3
0x1800175a5  movzx   r12d, ax
0x1800175a9  shr     r12w, 8
0x1800175ae  mov     [rsp+0A58h+var_9E8], r12b
0x1800175b3  cmp     al, dil
0x1800175b6  jnz     short loc_1800175C6
0x1800175b8  movzx   r15d, ax
0x1800175bc  shr     r15w, 8
0x1800175c1  mov     [rsp+0A58h+var_9E7], r15b
0x1800175c6  add     rcx, 2
0x1800175ca  jmp     short loc_180017584
0x1800175cc  mov     [rsp+0A58h+var_990], rbx
0x1800175d4  lea     rcx, [rsp+0A58h+var_990]
0x1800175dc  call    ?CreateInstance@?$CComObject@VCSyncShareDiscoveryResult@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CSyncShareDiscoveryResult>::CreateInstance(ATL::CComObject<CSyncShareDiscoveryResult> * *)
0x1800175e1  mov     [rsp+0A58h+dwMessageId], eax
0x1800175e5  mov     [rsp+0A58h+dwMessageId], eax
0x1800175e9  mov     ecx, 49Fh
0x1800175ee  test    eax, eax
0x1800175f0  js      loc_18001797E
0x1800175f6  mov     word ptr [rsp+0A58h+var_A04], cx
0x1800175fb  mov     r13, [rsp+0A58h+var_990]
0x180017603  mov     [rsp+0A58h+var_9A0], r13
0x18001760b  test    r13, r13
0x18001760e  jz      short loc_180017621
0x180017610  mov     rax, [r13+0]
0x180017614  mov     rcx, r13
0x180017617  mov     rax, [rax+8]
0x18001761b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017620  nop
0x180017621  mov     [rsp+0A58h+var_9E0], rbx
0x180017626  lea     rcx, [rsp+0A58h+var_9E0]
0x18001762b  call    ?CreateInstance@?$CComObject@VCSyncShareExtendedInfo@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CSyncShareExtendedInfo>::CreateInstance(ATL::CComObject<CSyncShareExtendedInfo> * *)
0x180017630  mov     [rsp+0A58h+dwMessageId], eax
0x180017634  mov     [rsp+0A58h+dwMessageId], eax
0x180017638  mov     ecx, 4A3h
0x18001763d  test    eax, eax
0x18001763f  js      loc_18001799F
0x180017645  mov     word ptr [rsp+0A58h+var_A04], cx
0x18001764a  mov     rcx, [rsp+0A58h+var_988]
0x180017652  mov     r10, [rsp+0A58h+var_868]
0x18001765a  or      r9d, 0FFFFFFFFh
0x18001765e  test    r15b, r15b
0x180017661  mov     eax, r9d
0x180017664  jnz     short loc_180017668
0x180017666  mov     eax, ebx
0x180017668  test    r12b, r12b
0x18001766b  jnz     short loc_180017670
0x18001766d  mov     r9d, ebx; __int16
0x180017670  lea     r8, [rsp+0A58h+var_8A8]
0x180017678  cmp     [rsp+0A58h+var_890], 7
0x180017681  cmova   r8, [rsp+0A58h+var_8A8]; unsigned __int16 *
0x18001768a  lea     rdx, [rsp+0A58h+var_888]
0x180017692  cmp     [rsp+0A58h+var_870], 7
0x18001769b  cmova   rdx, [rsp+0A58h+var_888]; unsigned __int16 *
0x1800176a4  mov     [rsp+0A58h+var_A28], rcx; unsigned __int64
0x1800176a9  mov     [rsp+0A58h+var_A30], r10; unsigned __int64
0x1800176ae  mov     [rsp+0A58h+var_A38], ax; __int16
0x1800176b3  mov     rcx, [rsp+0A58h+var_9E0]; this
0x1800176b8  call    ?Initialize@CSyncShareExtendedInfo@@QEAAXPEBG0FF_K1@Z; CSyncShareExtendedInfo::Initialize(ushort const *,ushort const *,short,short,unsigned __int64,unsigned __int64)
0x1800176bd  mov     rdx, [rsp+0A58h+var_9E0]
0x1800176c2  lea     rcx, [rsp+0A58h+var_980]
0x1800176ca  call    ??0?$CComPtr@UISyncShareExtendedInfo@@@ATL@@QEAA@PEAUISyncShareExtendedInfo@@@Z; ATL::CComPtr<ISyncShareExtendedInfo>::CComPtr<ISyncShareExtendedInfo>(ISyncShareExtendedInfo *)
0x1800176cf  nop
0x1800176d0  lea     r8, [rsp+0A58h+var_8C8]
0x1800176d8  cmp     [rsp+0A58h+var_8B0], 7
0x1800176e1  cmova   r8, [rsp+0A58h+var_8C8]; unsigned __int16 *
0x1800176ea  mov     r9, [rsp+0A58h+var_980]; struct ISyncShareExtendedInfo *
0x1800176f2  mov     rdx, rsi; unsigned __int16 *
0x1800176f5  mov     rcx, r13; this
0x1800176f8  call    ?Initialize@CSyncShareDiscoveryResult@@QEAAXPEBG0PEAUISyncShareExtendedInfo@@@Z; CSyncShareDiscoveryResult::Initialize(ushort const *,ushort const *,ISyncShareExtendedInfo *)
0x1800176fd  test    byte ptr cs:Microsoft_Windows_WorkFoldersEnableBits, dil
0x180017704  jz      short loc_180017737
0x180017706  lea     rax, [rsp+0A58h+var_8C8]
0x18001770e  cmp     [rsp+0A58h+var_8B0], 7
0x180017717  cmova   rax, [rsp+0A58h+var_8C8]
0x180017720  mov     qword ptr [rsp+0A58h+var_A38], rax
0x180017725  mov     r9, r14
0x180017728  mov     r8, rsi
0x18001772b  lea     rdx, ECSHOST_EVENT_DISCOVER_SYNC_TARGET
0x180017732  call    McTemplateU0zzz_EventWriteTransfer
0x180017737  mov     rax, [rsp+0A58h+var_9A0]
0x18001773f  mov     [rsp+0A58h+var_9A0], rbx
0x180017747  mov     rcx, [rsp+0A58h+var_960]
0x18001774f  mov     [rcx], rax
0x180017752  lea     rcx, [rsp+0A58h+var_980]
0x18001775a  call    ??1?$CComPtr@UICloudFileInfoFromDisk@@@ATL@@QEAA@XZ; ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(void)
0x18001775f  nop
0x180017760  lea     rcx, [rsp+0A58h+var_9A0]
0x180017768  call    ??1?$CComPtr@UICloudFileInfoFromDisk@@@ATL@@QEAA@XZ; ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(void)
0x18001776d  nop
0x18001776e  lea     rcx, [rsp+0A58h+var_8A8]
0x180017776  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001777b  nop
0x18001777c  lea     rcx, [rsp+0A58h+var_948]
0x180017784  call    ?_Tidy@?$vector@UPolicyEntry@@V?$allocator@UPolicyEntry@@@std@@@std@@AEAAXXZ; std::vector<PolicyEntry>::_Tidy(void)
0x180017789  nop
0x18001778a  lea     rcx, [rsp+0A58h+var_888]
0x180017792  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017797  nop
0x180017798  lea     rcx, [rsp+0A58h+var_8C8]
0x1800177a0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800177a5  nop
0x1800177a6  cmp     [rsp+0A58h+var_950], bl
0x1800177ad  jz      short loc_1800177C4
0x1800177af  mov     rcx, [rsp+0A58h+lpCriticalSection]; lpCriticalSection
0x1800177b7  call    cs:__imp_LeaveCriticalSection
0x1800177bd  mov     [rsp+0A58h+var_950], bl
0x1800177c4  jmp     short loc_1800177DB
0x1800177c6  mov     r14, [rsp+0A58h+var_9D0]
0x1800177ce  mov     rsi, [rsp+0A58h+var_9D8]
0x1800177d6  xor     ebx, ebx
0x1800177d8  mov     dil, 1
0x1800177db  mov     r15d, [rsp+0A58h+dwMessageId]
0x1800177e0  test    r15d, r15d
0x1800177e3  jns     short loc_18001783F
0x1800177e5  test    byte ptr cs:Microsoft_Windows_WorkFoldersEnableBits, 2
0x1800177ec  jz      short loc_18001783F
0x1800177ee  mov     [rsp+0A58h+var_848], bx
0x1800177f6  xor     edx, edx; Val
0x1800177f8  mov     r8d, 7FEh; Size
0x1800177fe  lea     rcx, [rsp+0A58h+var_846]; void *
0x180017806  call    memset_0
0x18001780b  lea     r8, [rsp+0A58h+var_848]; unsigned __int16 *
0x180017813  mov     ecx, r15d; dwMessageId
0x180017816  call    ?GetErrorText@CEcsFunctionTracer@@SAXJ_KPEAG@Z; CEcsFunctionTracer::GetErrorText(long,unsigned __int64,ushort *)
0x18001781b  mov     dword ptr [rsp+0A58h+var_A30], r15d
0x180017820  lea     rax, [rsp+0A58h+var_848]
0x180017828  mov     qword ptr [rsp+0A58h+var_A38], rax
0x18001782d  mov     r9, r14
0x180017830  mov     r8, rsi
0x180017833  lea     rdx, ECSHOST_EVENT_DISCOVER_SYNC_TARGET_FAILED
0x18001783a  call    McTemplateU0zzzd_EventWriteTransfer
0x18001783f  mov     esi, 80C80300h
0x180017844  cmp     [rsp+0A58h+dwMessageId], esi
0x180017848  jnz     loc_180017918
0x18001784e  mov     [rsp+0A58h+var_9E0], rbx
0x180017853  lea     rcx, [rsp+0A58h+var_9E0]
0x180017858  call    ?CreateInstance@?$CComObject@VCSyncCredentialsInfo@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CSyncCredentialsInfo>::CreateInstance(ATL::CComObject<CSyncCredentialsInfo> * *)
0x18001785d  mov     [rsp+0A58h+dwMessageId], eax
0x180017861  mov     [rsp+0A58h+dwMessageId], eax
0x180017865  mov     ecx, 4C2h
0x18001786a  test    eax, eax
0x18001786c  js      loc_180017A3C
0x180017872  jmp     short loc_18001787E
0x180017874  jmp     loc_1800177C6
0x180017879  jmp     loc_1800177C6
0x18001787e  mov     word ptr [rsp+0A58h+var_A04], cx
0x180017883  mov     rdx, [rsp+0A58h+var_9E0]
0x180017888  lea     rcx, [rsp+0A58h+var_978]
  ... truncated ...
```
