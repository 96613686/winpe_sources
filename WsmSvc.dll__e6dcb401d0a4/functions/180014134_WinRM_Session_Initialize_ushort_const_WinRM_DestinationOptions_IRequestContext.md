# WinRM_Session::Initialize(ushort const *,WinRM_DestinationOptions &,IRequestContext &)

- ea: `0x180014134`
- end: `0x180014989`
- name: `?Initialize@WinRM_Session@@QEAA?AW4_MI_Result@@PEBGAEAVWinRM_DestinationOptions@@AEAVIRequestContext@@@Z`
- size: `2133`
- prototype: `enum _MI_Result __fastcall(WinRM_Session *__hidden this, const unsigned __int16 *, struct WinRM_DestinationOptions *, struct IRequestContext *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801400b0`

## callees

- `0x180005d10`
- `0x180008920`
- `0x18000f700`
- `0x180010030`
- `0x180013760`
- `0x180014134`
- `0x180014990`
- `0x180014a60`
- `0x1800161f8`
- `0x1800224f0`
- `0x18003a3a0`
- `0x1800621e0`
- `0x18006c31c`
- `0x18006d8b0`
- `0x1800f9360`
- `0x1800fae50`
- `0x1801123a8`
- `0x18014ffa8`
- `0x1801ba152`
- `0x1801ba1b0`
- `0x1801ba270`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18001451a`
- `msvcrt!_itow_s` at `0x18001451a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014287`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014306`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014287`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014306`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141e3`
- `miutils!ClassCache_New` at `0x180014218`
- `miutils!ClassCache_New` at `0x180014218`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800141ad`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800141ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WinRM_Session::Initialize(
        WinRM_Session *this,
        const unsigned __int16 *a2,
        struct WinRM_DestinationOptions *a3,
        struct IRequestContext *a4)
{
  PTP_WORK ThreadpoolWork; // rax
  DWORD LastError; // eax
  unsigned int v10; // ebx
  CClientConfigCache *ConfigCache; // rax
  DWORD v12; // edi
  struct CClientConfigSettings *CurrentSettings; // rbx
  DWORD v14; // edi
  unsigned __int16 *v15; // rax
  CRemoteSession *v16; // r14
  unsigned __int16 *v17; // rax
  int v18; // r12d
  unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // rax
  int v21; // ecx
  int v22; // eax
  int v23; // ecx
  int v24; // eax
  int v25; // ecx
  unsigned int v26; // ebx
  struct _WSMAN_PROXY_INFO *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // r15
  __int64 v30; // rax
  __int64 v31; // rax
  int v32; // eax
  unsigned __int16 *v34; // rdx
  CClientConfigCache *v35; // [rsp+40h] [rbp-C0h] BYREF
  CRemoteSession *v36; // [rsp+48h] [rbp-B8h] BYREF
  struct CClientConfigSettings *v37; // [rsp+50h] [rbp-B0h] BYREF
  int v38; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+68h] [rbp-98h] BYREF
  __int128 v41; // [rsp+70h] [rbp-90h] BYREF
  __int64 v42; // [rsp+80h] [rbp-80h]
  int v43; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v44; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v45; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v46; // [rsp+A0h] [rbp-60h]
  struct _WSMAN_AUTHENTICATION_CREDENTIALS v47; // [rsp+A8h] [rbp-58h] BYREF
  _OWORD v48[2]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t Buffer[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v50; // [rsp+E4h] [rbp-1Ch]
  __int128 v51; // [rsp+F4h] [rbp-Ch]
  int v52; // [rsp+104h] [rbp+4h]
  unsigned __int16 v53; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v54[4094]; // [rsp+112h] [rbp+12h] BYREF

  v46 = (unsigned __int16 *)*((_QWORD *)a3 + 8);
  v40 = 0;
  v39 = 0;
  memset(&v47, 0, sizeof(v47));
  memset(v48, 0, sizeof(v48));
  ThreadpoolWork = CreateThreadpoolWork(WinRM_Session::_CloseSession, this, 0);
  *((_QWORD *)this + 25) = ThreadpoolWork;
  if ( !ThreadpoolWork )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_8f9c2ceeef8834b6e98f3c915a95a755_Traceguids, LastError);
    }
    goto LABEL_11;
  }
  v10 = ClassCache_New(0, 60, (char *)this + 16);
  if ( v10 )
  {
LABEL_83:
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v39);
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v40);
    return v10;
  }
  ConfigCache = CClientConfigCache::GetConfigCache(a4, 0);
  v35 = ConfigCache;
  if ( !ConfigCache )
  {
    v12 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_8f9c2ceeef8834b6e98f3c915a95a755_Traceguids, v12);
    SetLastError(v12);
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v35);
    goto LABEL_11;
  }
  CurrentSettings = CClientConfigCache::GetCurrentSettings(ConfigCache, a4);
  v37 = CurrentSettings;
  if ( !CurrentSettings )
  {
    v14 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_8f9c2ceeef8834b6e98f3c915a95a755_Traceguids, v14);
    SetLastError(v14);
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v37);
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v35);
    goto LABEL_11;
  }
  v43 = 0;
  v45 = (unsigned __int16 *)&v43;
  v15 = (unsigned __int16 *)WSManMemory::Alloc(1136, 0, 0);
  v44 = v15;
  if ( v15 )
    v16 = CRemoteSession::CRemoteSession((CRemoteSession *)v15);
  else
    v16 = 0;
  v36 = v16;
  if ( !v16 )
    goto LABEL_70;
  v17 = L"https://";
  if ( !*((_BYTE *)a3 + 110) )
    v17 = L"http://";
  v45 = v17;
  if ( a2 )
  {
    if ( (unsigned int)StringCchEquals(a2, L".") )
      a2 = L"localhost";
    v18 = *((_BYTE *)a3 + 110) ? *((_DWORD *)CurrentSettings + 24) : *((_DWORD *)CurrentSettings + 23);
  }
  else
  {
    v18 = 47001;
    a2 = L"localhost";
  }
  v38 = 0;
  v19 = CopyString(a2, &v38, a4);
  AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=((char *)this + 24, v19);
  if ( !(*(unsigned int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 144LL))(a4) )
  {
LABEL_70:
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v36);
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v37);
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v35);
LABEL_11:
    v10 = 1;
    goto LABEL_83;
  }
  if ( !WinRM_Session::SetupRetryNotificationMessages(this, (*((_DWORD *)CurrentSettings + 21) + 60000) / 0xEA60u, a4) )
  {
    if ( (*(unsigned int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 144LL))(a4) )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\mi_transport.cpp", 577, L"577", 0x54Fu, 0);
    goto LABEL_70;
  }
  if ( *((_DWORD *)a3 + 24) )
    v18 = *((_DWORD *)a3 + 24);
  wcscpy(Buffer, L":");
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v20 = (unsigned __int16 *)*((_QWORD *)a3 + 10);
  v44 = v20;
  if ( !v20 )
  {
    v20 = (unsigned __int16 *)*((_QWORD *)CurrentSettings + 13);
    v44 = v20;
  }
  LOWORD(v38) = *v20;
  _itow_s(v18, &Buffer[1], 0x13u, 10);
  v53 = 0;
  memset_0(v54, 0, sizeof(v54));
  StringCchCatW(&v53, 0x800u, v45);
  if ( (int)StringCchCatW(&v53, 0x800u, a2) < 0 || (int)StringCchCatW(&v53, 0x800u, Buffer) < 0 )
  {
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v36);
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v37);
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v35);
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v39);
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v40);
    return 1;
  }
  else
  {
    if ( (_WORD)v38 != 47 && (int)StringCchCatW(&v53, 0x800u, L"/") < 0
      || (int)StringCchCatW(&v53, 0x800u, v44) < 0
      || !(unsigned __int8)WinRM_Session::ConvertCredential(a3, &v47, &v40) )
    {
      goto LABEL_70;
    }
    v21 = (*((_BYTE *)a3 + 104) != 0) | 2;
    if ( !*((_BYTE *)a3 + 105) )
      v21 = *((_BYTE *)a3 + 104) != 0;
    v22 = v21 | 0x40;
    if ( !*((_BYTE *)a3 + 106) )
      v22 = v21;
    v23 = v22 | 4;
    if ( !*((_BYTE *)a3 + 108) )
      v23 = v22;
    v24 = v23 | 8;
    if ( *((_BYTE *)a3 + 107) )
      v24 = v23;
    v25 = v24 | 0x20;
    if ( !*((_BYTE *)a3 + 111) )
      v25 = v24;
    v26 = v25 | 0x10;
    if ( !*((_BYTE *)a3 + 109) )
      v26 = v25;
    if ( *(_QWORD *)a3 && (unsigned int)StringCchEquals(*(const unsigned __int16 **)a3, L"NegoNoCreds") )
      v26 |= 0x80u;
    if ( *((_DWORD *)a3 + 22) != 2 || (v27 = 0, *((_QWORD *)a3 + 4)) )
    {
      LODWORD(v48[0]) = *((_DWORD *)a3 + 22);
      if ( !(unsigned __int8)WinRM_Session::ConvertCredential((char *)a3 + 32, (char *)v48 + 8, &v39) )
        goto LABEL_70;
      v27 = (struct _WSMAN_PROXY_INFO *)v48;
    }
    if ( !(unsigned int)CRemoteBaseSession::Initialize(v16, a4, &v53, v26, &v47, v27, v46) )
    {
      if ( (*(unsigned int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 152LL))(a4) == -2144108327 )
        (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, 2150859256LL);
      goto LABEL_70;
    }
    v41 = 0;
    v42 = 0;
    v28 = *((_QWORD *)a3 + 9);
    v10 = 1;
    v29 = -1;
    if ( v28 )
    {
      LODWORD(v41) = 1;
      v42 = v28;
      v30 = -1;
      do
        ++v30;
      while ( *(_WORD *)(v28 + 2 * v30) );
      DWORD2(v41) = v30;
      if ( !(*(unsigned __int8 (__fastcall **)(__int64, struct IRequestContext *, __int64, __int128 *))(*((_QWORD *)v16 + 5) + 8LL))(
              (__int64)v16 + 40,
              a4,
              25,
              &v41) )
        goto LABEL_82;
    }
    v31 = *((_QWORD *)a3 + 8);
    if ( v31 )
    {
      LODWORD(v41) = 1;
      v42 = v31;
      do
        ++v29;
      while ( *(_WORD *)(v31 + 2 * v29) );
      DWORD2(v41) = v29;
      if ( !(*(unsigned __int8 (__fastcall **)(__int64, struct IRequestContext *, __int64, __int128 *))(*((_QWORD *)v16 + 5) + 8LL))(
              (__int64)v16 + 40,
              a4,
              26,
              &v41) )
        goto LABEL_82;
    }
    v32 = *((_DWORD *)a3 + 23);
    if ( v32 )
    {
      LODWORD(v41) = 4;
      DWORD2(v41) = v32;
      if ( !(*(unsigned __int8 (__fastcall **)(__int64, struct IRequestContext *, __int64, __int128 *))(*((_QWORD *)v16 + 5) + 8LL))(
              (__int64)v16 + 40,
              a4,
              28,
              &v41) )
      {
LABEL_82:
        AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v36);
        AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v37);
        AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v35);
        goto LABEL_83;
      }
    }
    v34 = (unsigned __int16 *)*((_QWORD *)a3 + 14);
    if ( v34 )
      CRemoteSession::SetTargetSPN(v16, v34);
    *((_DWORD *)this + 8) = *((_DWORD *)a3 + 25);
    *((_DWORD *)this + 9) = 0;
    v36 = 0;
    *((_QWORD *)this + 1) = v16;
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v36);
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v37);
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v35);
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v39);
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v40);
    return 0;
  }
}

```

## disassembly

```asm
0x180014134  push    rbp
0x180014136  push    rbx
0x180014137  push    rsi
0x180014138  push    rdi
0x180014139  push    r12
0x18001413b  push    r13
0x18001413d  push    r14
0x18001413f  push    r15
0x180014141  lea     rbp, [rsp-1028h]
0x180014149  mov     eax, 1128h
0x18001414e  call    _alloca_probe
0x180014153  sub     rsp, rax
0x180014156  mov     rax, cs:__security_cookie
0x18001415d  xor     rax, rsp
0x180014160  mov     [rbp+1060h+var_50], rax
0x180014167  mov     rdi, r9
0x18001416a  mov     rsi, r8
0x18001416d  mov     r15, rdx
0x180014170  mov     r13, rcx
0x180014173  mov     rax, [r8+40h]
0x180014177  mov     [rbp+1060h+var_10C0], rax
0x18001417b  xor     r12d, r12d
0x18001417e  mov     [rsp+1160h+var_10F8], r12
0x180014183  mov     [rsp+1160h+var_1100], r12
0x180014188  xorps   xmm0, xmm0
0x18001418b  xor     eax, eax
0x18001418d  movups  xmmword ptr [rbp+1060h+var_10B8.authenticationMechanism], xmm0
0x180014191  mov     qword ptr [rbp+1060h+var_10B8.8+8], rax
0x180014195  xorps   xmm1, xmm1
0x180014198  movups  [rbp+1060h+var_10A0], xmm1
0x18001419c  movups  [rbp+1060h+var_1090], xmm1
0x1800141a0  xor     r8d, r8d; pcbe
0x1800141a3  mov     rdx, rcx; pv
0x1800141a6  lea     rcx, ?_CloseSession@WinRM_Session@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800141ad  call    cs:__imp_CreateThreadpoolWork
0x1800141b3  mov     [r13+0C8h], rax
0x1800141ba  test    rax, rax
0x1800141bd  jnz     short loc_18001420D
0x1800141bf  lea     rax, WPP_GLOBAL_Control
0x1800141c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800141cd  cmp     rcx, rax
0x1800141d0  jz      loc_180014299
0x1800141d6  test    dword ptr [rcx+1Ch], 200h
0x1800141dd  jz      loc_180014299
0x1800141e3  call    cs:__imp_GetLastError
0x1800141e9  lea     edx, [r12+0Fh]
0x1800141ee  mov     r9d, eax
0x1800141f1  lea     r8, WPP_8f9c2ceeef8834b6e98f3c915a95a755_Traceguids
0x1800141f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800141ff  mov     rcx, [rcx+10h]
0x180014203  call    WPP_SF_d
0x180014208  jmp     loc_180014299
0x18001420d  lea     r8, [r13+10h]
0x180014211  mov     edx, 3Ch ; '<'
0x180014216  xor     ecx, ecx
0x180014218  call    cs:__imp_ClassCache_New
0x18001421e  mov     ebx, eax
0x180014220  test    eax, eax
0x180014222  jnz     loc_1800148B0
0x180014228  xor     edx, edx; int
0x18001422a  mov     rcx, rdi; struct IRequestContext *
0x18001422d  call    ?GetConfigCache@CClientConfigCache@@SAPEAV1@PEAVIRequestContext@@H@Z; CClientConfigCache::GetConfigCache(IRequestContext *,int)
0x180014232  mov     [rsp+1160h+var_1120], rax
0x180014237  test    rax, rax
0x18001423a  jnz     short loc_1800142A3
0x18001423c  mov     rax, [rdi]
0x18001423f  mov     rcx, rdi
0x180014242  mov     rax, [rax+98h]
0x180014249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001424e  mov     edi, eax
0x180014250  lea     rax, WPP_GLOBAL_Control
0x180014257  mov     rcx, cs:WPP_GLOBAL_Control
0x18001425e  cmp     rcx, rax
0x180014261  jz      short loc_180014285
0x180014263  mov     ebx, 800h
0x180014268  test    [rcx+1Ch], ebx
0x18001426b  jz      short loc_180014285
0x18001426d  mov     edx, 10h
0x180014272  mov     r9d, edi
0x180014275  lea     r8, WPP_8f9c2ceeef8834b6e98f3c915a95a755_Traceguids
0x18001427c  mov     rcx, [rcx+10h]
0x180014280  call    WPP_SF_d
0x180014285  mov     ecx, edi; dwErrCode
0x180014287  call    cs:__imp_SetLastError
0x18001428d  nop
0x18001428e  lea     rcx, [rsp+1160h+var_1120]
0x180014293  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x180014298  nop
0x180014299  mov     ebx, 1
0x18001429e  jmp     loc_1800148B0
0x1800142a3  mov     rdx, rdi; struct IRequestContext *
0x1800142a6  mov     rcx, rax; this
0x1800142a9  call    ?GetCurrentSettings@CClientConfigCache@@QEAAPEAVCClientConfigSettings@@PEAVIRequestContext@@@Z; CClientConfigCache::GetCurrentSettings(IRequestContext *)
0x1800142ae  mov     rbx, rax
0x1800142b1  mov     [rsp+1160h+var_1110], rax
0x1800142b6  test    rax, rax
0x1800142b9  jnz     short loc_180014328
0x1800142bb  mov     rax, [rdi]
0x1800142be  mov     rcx, rdi
0x1800142c1  mov     rax, [rax+98h]
0x1800142c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142cd  mov     edi, eax
0x1800142cf  lea     rax, WPP_GLOBAL_Control
0x1800142d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142dd  cmp     rcx, rax
0x1800142e0  jz      short loc_180014304
0x1800142e2  mov     ebx, 800h
0x1800142e7  test    [rcx+1Ch], ebx
0x1800142ea  jz      short loc_180014304
0x1800142ec  mov     edx, 11h
0x1800142f1  mov     r9d, edi
0x1800142f4  lea     r8, WPP_8f9c2ceeef8834b6e98f3c915a95a755_Traceguids
0x1800142fb  mov     rcx, [rcx+10h]
0x1800142ff  call    WPP_SF_d
0x180014304  mov     ecx, edi; dwErrCode
0x180014306  call    cs:__imp_SetLastError
0x18001430c  nop
0x18001430d  lea     rcx, [rsp+1160h+var_1110]
0x180014312  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x180014317  nop
0x180014318  lea     rcx, [rsp+1160h+var_1120]
0x18001431d  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x180014322  nop
0x180014323  jmp     loc_180014299
0x180014328  mov     [rbp+1060h+var_10D8], r12d
0x18001432c  lea     rax, [rbp+1060h+var_10D8]
0x180014330  mov     [rbp+1060h+var_10C8], rax
0x180014334  xor     r8d, r8d
0x180014337  xor     edx, edx
0x180014339  mov     ecx, 470h
0x18001433e  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x180014343  mov     [rbp+1060h+var_10D0], rax
0x180014347  test    rax, rax
0x18001434a  jz      short loc_180014359
0x18001434c  mov     rcx, rax; this
0x18001434f  call    ??0CRemoteSession@@QEAA@XZ; CRemoteSession::CRemoteSession(void)
0x180014354  mov     r14, rax
0x180014357  jmp     short loc_18001435C
0x180014359  mov     r14, r12
0x18001435c  mov     [rsp+1160h+var_1118], r14
0x180014361  test    r14, r14
0x180014364  jnz     short loc_18001438C
0x180014366  lea     rcx, [rsp+1160h+var_1118]
0x18001436b  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x180014370  nop
0x180014371  lea     rcx, [rsp+1160h+var_1110]
0x180014376  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x18001437b  nop
0x18001437c  lea     rcx, [rsp+1160h+var_1120]
0x180014381  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x180014386  nop
0x180014387  jmp     loc_180014299
0x18001438c  lea     rcx, aHttp_0; "http://"
0x180014393  lea     rax, aHttps_0; "https://"
0x18001439a  cmp     [rsi+6Eh], r12b
0x18001439e  cmovz   rax, rcx
0x1800143a2  mov     [rbp+1060h+var_10C8], rax
0x1800143a6  test    r15, r15
0x1800143a9  jz      short loc_1800143D9
0x1800143ab  lea     rdx, asc_1801D9F5C; "."
0x1800143b2  mov     rcx, r15; unsigned __int16 *
0x1800143b5  call    ?StringCchEquals@@YAHPEBG0@Z; StringCchEquals(ushort const *,ushort const *)
0x1800143ba  lea     rcx, aLocalhost; "localhost"
0x1800143c1  test    eax, eax
0x1800143c3  cmovnz  r15, rcx
0x1800143c7  cmp     [rsi+6Eh], r12b
0x1800143cb  jz      short loc_1800143D3
0x1800143cd  mov     r12d, [rbx+60h]
0x1800143d1  jmp     short loc_1800143E6
0x1800143d3  mov     r12d, [rbx+5Ch]
0x1800143d7  jmp     short loc_1800143E6
0x1800143d9  mov     r12d, 0B799h
0x1800143df  lea     r15, aLocalhost; "localhost"
0x1800143e6  mov     [rsp+1160h+var_1108], 0
0x1800143ee  mov     r8, rdi; struct IRequestContext *
0x1800143f1  lea     rdx, [rsp+1160h+var_1108]; int *
0x1800143f6  mov     rcx, r15; unsigned __int16 *
0x1800143f9  call    ?CopyString@@YAPEAGPEBGAEBHAEAVIRequestContext@@@Z; CopyString(ushort const *,int const &,IRequestContext &)
0x1800143fe  lea     rcx, [r13+18h]
0x180014402  mov     rdx, rax
0x180014405  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x18001440a  mov     rax, [rdi]
0x18001440d  mov     rcx, rdi
0x180014410  mov     rax, [rax+90h]
0x180014417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001441c  test    eax, eax
0x18001441e  jnz     short loc_180014446
0x180014420  lea     rcx, [rsp+1160h+var_1118]
0x180014425  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x18001442a  nop
0x18001442b  lea     rcx, [rsp+1160h+var_1110]
0x180014430  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x180014435  nop
0x180014436  lea     rcx, [rsp+1160h+var_1120]
0x18001443b  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x180014440  nop
0x180014441  jmp     loc_180014299
0x180014446  mov     ecx, [rbx+54h]
0x180014449  add     ecx, 0EA60h
0x18001444f  mov     eax, 45E7B273h
0x180014454  mul     ecx
0x180014456  shr     edx, 0Eh; unsigned int
0x180014459  mov     r8, rdi; struct IRequestContext *
0x18001445c  mov     rcx, r13; this
0x18001445f  call    ?SetupRetryNotificationMessages@WinRM_Session@@AEAA_NKAEAVIRequestContext@@@Z; WinRM_Session::SetupRetryNotificationMessages(ulong,IRequestContext &)
0x180014464  test    al, al
0x180014466  jnz     short loc_1800144CC
0x180014468  mov     rax, [rdi]
0x18001446b  mov     rcx, rdi
0x18001446e  mov     rax, [rax+90h]
0x180014475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001447a  test    eax, eax
0x18001447c  jz      short loc_1800144A6
0x18001447e  mov     [rsp+1160h+var_1140], 0; struct IRequestContext *
0x180014487  mov     r9d, 54Fh; unsigned int
0x18001448d  lea     r8, a577; "577"
0x180014494  mov     edx, 241h; unsigned int
0x180014499  lea     rcx, aOnecoreAdminWm_34; "onecore\\admin\\wmi\\wmx\\client\\remot"...
0x1800144a0  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800144a5  nop
0x1800144a6  lea     rcx, [rsp+1160h+var_1118]
0x1800144ab  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x1800144b0  nop
0x1800144b1  lea     rcx, [rsp+1160h+var_1110]
0x1800144b6  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x1800144bb  nop
0x1800144bc  lea     rcx, [rsp+1160h+var_1120]
0x1800144c1  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x1800144c6  nop
0x1800144c7  jmp     loc_180014299
0x1800144cc  cmp     dword ptr [rsi+60h], 0
0x1800144d0  cmovnz  r12d, [rsi+60h]
0x1800144d5  mov     dword ptr [rbp+1060h+Buffer], 3Ah ; ':'
0x1800144dc  xorps   xmm0, xmm0
0x1800144df  xor     eax, eax
0x1800144e1  movups  [rbp+1060h+var_107C], xmm0
0x1800144e5  movups  [rbp+1060h+var_106C], xmm0
0x1800144e9  mov     [rbp+1060h+var_105C], eax
0x1800144ec  mov     rax, [rsi+50h]
0x1800144f0  mov     [rbp+1060h+var_10D0], rax
0x1800144f4  test    rax, rax
0x1800144f7  jnz     short loc_180014501
0x1800144f9  mov     rax, [rbx+68h]
0x1800144fd  mov     [rbp+1060h+var_10D0], rax
0x180014501  movzx   eax, word ptr [rax]
0x180014504  mov     word ptr [rsp+1160h+var_1108], ax
0x180014509  mov     r9d, 0Ah; Radix
0x18001450f  lea     r8d, [r9+9]; BufferCount
0x180014513  lea     rdx, [rbp+1060h+Buffer+2]; Buffer
0x180014517  mov     ecx, r12d; Value
0x18001451a  call    cs:__imp__itow_s
0x180014520  xor     r12d, r12d
0x180014523  mov     [rbp+1060h+var_1050], r12w
0x180014528  xor     edx, edx; Val
0x18001452a  mov     r8d, 0FFEh; Size
0x180014530  lea     rcx, [rbp+1060h+var_104E]; void *
0x180014534  call    memset_0
0x180014539  mov     r8, [rbp+1060h+var_10C8]; unsigned __int16 *
0x18001453d  mov     ebx, 800h
0x180014542  mov     edx, ebx; unsigned __int64
0x180014544  lea     rcx, [rbp+1060h+var_1050]; unsigned __int16 *
0x180014548  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001454d  mov     r8, r15; unsigned __int16 *
0x180014550  mov     edx, ebx; unsigned __int64
0x180014552  lea     rcx, [rbp+1060h+var_1050]; unsigned __int16 *
0x180014556  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001455b  test    eax, eax
0x18001455d  js      loc_18001492B
0x180014563  lea     r8, [rbp+1060h+Buffer]; unsigned __int16 *
0x180014567  mov     edx, ebx; unsigned __int64
0x180014569  lea     rcx, [rbp+1060h+var_1050]; unsigned __int16 *
0x18001456d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180014572  test    eax, eax
0x180014574  js      loc_18001492B
0x18001457a  cmp     word ptr [rsp+1160h+var_1108], 2Fh ; '/'
0x180014580  jz      short loc_1800145BE
0x180014582  lea     r8, asc_1801DB75C; "/"
0x180014589  mov     edx, ebx; unsigned __int64
0x18001458b  lea     rcx, [rbp+1060h+var_1050]; unsigned __int16 *
0x18001458f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180014594  test    eax, eax
0x180014596  jns     short loc_1800145BE
0x180014598  lea     rcx, [rsp+1160h+var_1118]
0x18001459d  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x1800145a2  nop
0x1800145a3  lea     rcx, [rsp+1160h+var_1110]
0x1800145a8  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x1800145ad  nop
0x1800145ae  lea     rcx, [rsp+1160h+var_1120]
0x1800145b3  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x1800145b8  nop
0x1800145b9  jmp     loc_180014299
0x1800145be  mov     r8, [rbp+1060h+var_10D0]; unsigned __int16 *
0x1800145c2  mov     rdx, rbx; unsigned __int64
0x1800145c5  lea     rcx, [rbp+1060h+var_1050]; unsigned __int16 *
0x1800145c9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800145ce  test    eax, eax
0x1800145d0  jns     short loc_1800145F8
0x1800145d2  lea     rcx, [rsp+1160h+var_1118]
0x1800145d7  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
  ... truncated ...
```
