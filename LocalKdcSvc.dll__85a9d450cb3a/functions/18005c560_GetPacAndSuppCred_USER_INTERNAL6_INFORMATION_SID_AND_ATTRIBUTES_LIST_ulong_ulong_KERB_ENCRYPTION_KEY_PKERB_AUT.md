# GetPacAndSuppCred(_USER_INTERNAL6_INFORMATION *,_SID_AND_ATTRIBUTES_LIST *,ulong,ulong,_KERB_ENCRYPTION_KEY *,PKERB_AUTHORIZATION_DATA_s *,_LARGE_INTEGER *,_UNICODE_STRING *,_LARGE_INTEGER *,_LARGE_INTEGER *,_SAM_CLAIMS_BLOB *,ulong,PacRequestType,void *,_PACTYPE * *,KERB_EXT_ERROR *)

- ea: `0x18005c560`
- end: `0x18005cda3`
- name: `?GetPacAndSuppCred@@YAJPEAU_USER_INTERNAL6_INFORMATION@@PEAU_SID_AND_ATTRIBUTES_LIST@@KKPEAU_KERB_ENCRYPTION_KEY@@PEAUPKERB_AUTHORIZATION_DATA_s@@PEAT_LARGE_INTEGER@@PEAU_UNICODE_STRING@@44PEAU_SAM_CLAIMS_BLOB@@KW4PacRequestType@@PEAXPEAPEAU_PACTYPE@@PEAUKERB_EXT_ERROR@@@Z`
- size: `2115`
- prototype: `__int64 __fastcall(__int64, unsigned int *, unsigned int, unsigned int, struct _KERB_ENCRYPTION_KEY *, struct PKERB_AUTHORIZATION_DATA_s *, union _LARGE_INTEGER *, struct _UNICODE_STRING *, union _LARGE_INTEGER *, union _LARGE_INTEGER *, struct _SAM_CLAIMS_BLOB *, char, unsigned int, void *Src, struct _PACTYPE **, int *)`
- caller_count: `2`
- callee_count: `24`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180047f90`
- `0x18004b680`

## callees

- `0x180002ad0`
- `0x1800101c4`
- `0x1800101ec`
- `0x18002057c`
- `0x1800206c0`
- `0x1800206e8`
- `0x180037b28`
- `0x18005bbbc`
- `0x18005c560`
- `0x18005d16c`
- `0x18005d228`
- `0x18005d344`
- `0x18005d76c`
- `0x18005d8c4`
- `0x18005d98c`
- `0x18005da04`
- `0x18005feb8`
- `0x1800632e8`
- `0x180066ff0`
- `0x1800673a8`
- `0x1800702dc`
- `0x180071868`
- `0x180099be0`
- `0x18009c010`

## import_xrefs

- `LSASRV!LsaIIsLastInteractiveLogonInfoEnabled` at `0x18005cc15`
- `LSASRV!LsaIIsLastInteractiveLogonInfoEnabled` at `0x18005cc15`

## pseudocode

```c
__int64 __fastcall GetPacAndSuppCred(
        __int64 a1,
        unsigned int *a2,
        unsigned int a3,
        unsigned int a4,
        struct _KERB_ENCRYPTION_KEY *a5,
        struct PKERB_AUTHORIZATION_DATA_s *a6,
        union _LARGE_INTEGER *a7,
        struct _UNICODE_STRING *a8,
        union _LARGE_INTEGER *a9,
        union _LARGE_INTEGER *a10,
        struct _SAM_CLAIMS_BLOB *a11,
        char a12,
        unsigned int a13,
        void *Src,
        struct _PACTYPE **a15,
        int *a16)
{
  __int64 v17; // rdi
  __int64 v18; // rax
  struct PKERB_AUTHORIZATION_DATA_s *v19; // r10
  _QWORD *v20; // r11
  unsigned int v21; // ebx
  unsigned int v23; // ecx
  struct _UNICODE_STRING *v24; // rdx
  int v25; // eax
  __int64 v26; // rax
  unsigned __int64 v27; // rsi
  unsigned int *v28; // rbx
  __int64 v29; // rcx
  void *v30; // rsp
  void *v31; // rsp
  unsigned int *v32; // rax
  unsigned __int64 v33; // rsi
  unsigned int *v34; // rbx
  unsigned __int64 v35; // rcx
  void *v36; // rsp
  void *v37; // rsp
  unsigned int *v38; // rax
  unsigned int v39; // ebx
  __int64 v40; // r12
  struct _LSA_LAST_INTER_LOGON_INFO *v41; // rsi
  unsigned int v42; // r14d
  __int64 v43; // r8
  unsigned int v44; // r15d
  HLOCAL v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rdx
  __int64 v49; // rdx
  __int64 v50; // rdx
  LARGE_INTEGER v51; // rax
  int inited; // eax
  int v53; // ebx
  int *v54; // rax
  _BYTE v55[32]; // [rsp+0h] [rbp-70h] BYREF
  size_t Size; // [rsp+20h] [rbp-50h]
  unsigned int v57; // [rsp+70h] [rbp+0h] BYREF
  unsigned int *v58; // [rsp+78h] [rbp+8h] BYREF
  unsigned int v59; // [rsp+80h] [rbp+10h] BYREF
  unsigned int v60; // [rsp+84h] [rbp+14h] BYREF
  unsigned int *v61; // [rsp+88h] [rbp+18h] BYREF
  struct _PACTYPE *v62; // [rsp+90h] [rbp+20h] BYREF
  unsigned int v63; // [rsp+98h] [rbp+28h]
  unsigned int v64; // [rsp+9Ch] [rbp+2Ch]
  struct _LSA_LAST_INTER_LOGON_INFO *v65; // [rsp+A0h] [rbp+30h]
  struct PKERB_AUTHORIZATION_DATA_s *v66; // [rsp+A8h] [rbp+38h]
  _LSA_LAST_INTER_LOGON_INFO v67; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v68; // [rsp+C8h] [rbp+58h]
  union _LARGE_INTEGER *v69; // [rsp+D0h] [rbp+60h]
  union _LARGE_INTEGER *v70; // [rsp+D8h] [rbp+68h]
  int *v71; // [rsp+E0h] [rbp+70h]
  struct _PACTYPE **v72; // [rsp+E8h] [rbp+78h]
  _DWORD v73[2]; // [rsp+F0h] [rbp+80h] BYREF
  unsigned int *v74; // [rsp+F8h] [rbp+88h]
  _DWORD v75[2]; // [rsp+100h] [rbp+90h] BYREF
  unsigned int *v76; // [rsp+108h] [rbp+98h]
  _BYTE v77[48]; // [rsp+110h] [rbp+A0h] BYREF
  char v78; // [rsp+140h] [rbp+D0h] BYREF
  struct _PAC_INFO_BUFFER *v79[2]; // [rsp+168h] [rbp+F8h] BYREF
  __int128 v80; // [rsp+178h] [rbp+108h]
  __int128 v81; // [rsp+188h] [rbp+118h]

  v63 = a4;
  v64 = a3;
  v17 = a1;
  v68 = a1;
  v71 = a16;
  v66 = a6;
  v70 = a9;
  v69 = a10;
  v72 = a15;
  v62 = 0;
  *(_OWORD *)v79 = 0;
  v80 = 0;
  v81 = 0;
  v57 = 0;
  v60 = 0;
  v73[1] = 0;
  v58 = 0;
  v75[1] = 0;
  v61 = 0;
  memset(&v67, 0, sizeof(v67));
  v59 = 0;
  v18 = lambda_bde1109c27f1d473909aeaf58a3f4245_::_lambda_bde1109c27f1d473909aeaf58a3f4245_(
          (unsigned int)&v78,
          (unsigned int)&v57,
          (unsigned int)v79,
          (unsigned int)&v61,
          (__int64)&v58,
          (__int64)&v62);
  wil::scope_exit__lambda_bde1109c27f1d473909aeaf58a3f4245___(v77, v18);
  *v20 = 0;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
  {
    WPP_SF_ZZZDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)WPP_GLOBAL_Control,
      v17 + 64,
      v17 + 48,
      v17 + 64,
      v17 + 336,
      *(_DWORD *)(v17 + 272),
      *(_DWORD *)(v17 + 280),
      *(_DWORD *)(v17 + 328),
      *(_DWORD *)(v17 + 284),
      a12);
    v19 = v66;
  }
  if ( a5 && *((_QWORD *)a5 + 3) )
  {
    v21 = KdcBuildSupplementalCredentials((struct _USER_INTERNAL6_INFORMATION *)v17, a5, &v79[v57]);
    if ( v21 )
    {
LABEL_7:
      wil::details::lambda_call__lambda_bde1109c27f1d473909aeaf58a3f4245___::_lambda_call__lambda_bde1109c27f1d473909aeaf58a3f4245___(v77);
      return v21;
    }
    v23 = v57;
    goto LABEL_9;
  }
  if ( !v19 || (unsigned int)KdcExtractFieldsFromPac(v19, &v79[v57], &v59) )
  {
    v23 = v57;
  }
  else
  {
    v23 = v57;
    if ( v79[v57] )
LABEL_9:
      v57 = ++v23;
  }
  if ( a7 )
  {
    v21 = KdcBuildPacVerifier(a7, a8, &v79[v23]);
    if ( v21 )
      goto LABEL_7;
    v23 = ++v57;
  }
  v24 = (struct _UNICODE_STRING *)(v17 + 336);
  if ( KdcGlobalNoExtraFieldsInUpnDnsInfo )
    v25 = KdcBuildExtraLogonInfoBuffer(*(_BYTE *)(v17 + 332), v24, &DomainName2, &v79[v23]);
  else
    v25 = KdcBuildExtraLogonInfoExBuffer(
            *(_BYTE *)(v17 + 332),
            v24,
            &DomainName2,
            (struct _UNICODE_STRING *)(v17 + 48),
            *(_DWORD *)(v17 + 272),
            &v79[v23]);
  if ( v25 < 0 )
    goto LABEL_102;
  v26 = ++v57;
  if ( a11 )
  {
    v21 = KdcBuildClaimsPacData(a11, &v79[v26]);
    if ( v21 )
      goto LABEL_7;
    v26 = ++v57;
  }
  if ( (a12 & 8) != 0 )
  {
    v21 = KdcBuildPacAttributes(a13, &v79[v26]);
    if ( v21 )
      goto LABEL_7;
    v26 = ++v57;
  }
  if ( (a12 & 0x10) != 0 && Src )
  {
    v21 = KdcBuildPacRequestor(Src, &v79[v26]);
    if ( v21 )
      goto LABEL_7;
    ++v57;
  }
  v27 = 8LL * *a2;
  v28 = 0;
  if ( !v27
    || v27 > g_ulMaxStackAllocSize
    || v27 + g_ulAdditionalProbeSize + 8 < v27
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_106;
  }
  v29 = v27 + 23;
  if ( v27 + 23 <= v27 + 8 )
    v29 = 0xFFFFFFFFFFFFFF0LL;
  v30 = alloca(v29 & 0xFFFFFFFFFFFFFFF0uLL);
  v31 = alloca(v29 & 0xFFFFFFFFFFFFFFF0uLL);
  v28 = &v57;
  if ( v55 == (_BYTE *)-112LL || (v57 = 1801679955, (v28 = (unsigned int *)&v58) == 0) )
  {
LABEL_106:
    if ( v27 + 8 >= v27 )
    {
      v32 = (unsigned int *)((__int64 (*)(void))g_pfnAllocate)();
      v28 = v32;
      if ( v32 )
      {
        *v32 = 1885431112;
        v28 = v32 + 2;
      }
    }
  }
  v61 = v28;
  if ( !v28 )
    goto LABEL_102;
  if ( *a2 + 5 < *a2 )
    goto LABEL_102;
  v33 = 16LL * (*a2 + 5);
  if ( v33 > 0xFFFFFFFF )
    goto LABEL_102;
  v34 = 0;
  if ( !(_DWORD)v33
    || (unsigned int)v33 > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)(unsigned int)v33 + g_ulAdditionalProbeSize + 8 < (unsigned int)v33
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_107;
  }
  v35 = (unsigned int)v33 + 23LL;
  if ( v35 <= (unsigned __int64)(unsigned int)v33 + 8 )
    v35 = 0xFFFFFFFFFFFFFF0LL;
  v36 = alloca(v35 & 0xFFFFFFFFFFFFFFF0uLL);
  v37 = alloca(v35 & 0xFFFFFFFFFFFFFFF0uLL);
  v34 = &v57;
  if ( v55 == (_BYTE *)-112LL || (v57 = 1801679955, (v34 = (unsigned int *)&v58) == 0) )
  {
LABEL_107:
    if ( (unsigned __int64)(unsigned int)v33 + 8 >= (unsigned int)v33 )
    {
      v38 = (unsigned int *)((__int64 (*)(void))g_pfnAllocate)();
      v34 = v38;
      if ( v38 )
      {
        *v38 = 1885431112;
        v34 = v38 + 2;
      }
    }
  }
  v58 = v34;
  if ( !v34 )
    goto LABEL_102;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v65 = 0;
  v42 = 0;
  if ( *a2 )
  {
    do
    {
      if ( KdcIsOurDomain(*(void **)(*((_QWORD *)a2 + 1) + 16LL * v42), &v60) )
      {
        v44 = v60;
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
        {
          Size = *(_QWORD *)(*((_QWORD *)a2 + 1) + 16LL * v42);
          WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), WPP_GLOBAL_Control, v43, v60);
        }
        v61[2 * v40] = v44;
        v61[2 * v40 + 1] = *(_DWORD *)(*((_QWORD *)a2 + 1) + 16LL * v42 + 8);
        v40 = (unsigned int)(v40 + 1);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
        {
          WPP_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            135,
            WPP_b168486f65343579948eb0cc9cf7c178_Traceguids,
            *(_QWORD *)(*((_QWORD *)a2 + 1) + 16LL * v42));
        }
        *(_OWORD *)&v58[4 * v39++] = *(_OWORD *)(*((_QWORD *)a2 + 1) + 16LL * v42);
      }
      ++v42;
    }
    while ( v42 < *a2 );
    v17 = v68;
    v41 = v65;
  }
  if ( v66 )
  {
    if ( (v59 & 2) != 0 )
    {
      v45 = GlobalAuthenticationServiceAssertedSid;
    }
    else
    {
      if ( (v59 & 1) == 0 )
        goto LABEL_79;
      v45 = GlobalAuthenticationAuthorityAssertedSid;
    }
  }
  else
  {
    v45 = GlobalAuthenticationAuthorityAssertedSid;
    if ( (a12 & 2) != 0 )
      v45 = GlobalAuthenticationServiceAssertedSid;
  }
  if ( v45 )
  {
    v46 = 2LL * v39;
    *(_QWORD *)&v58[2 * v46] = v45;
    v58[2 * v46 + 2] = 7;
    ++v39;
  }
LABEL_79:
  if ( *(_BYTE *)(v17 + 624) )
  {
    v47 = 2LL * v39;
    *(_QWORD *)&v58[2 * v47] = GlobalAuthenticationKeyTrustSid;
    v58[2 * v47 + 2] = 7;
    ++v39;
    if ( *(_BYTE *)(v17 + 626) )
    {
      v48 = 2LL * v39;
      *(_QWORD *)&v58[2 * v48] = GlobalAuthenticationKeyPropertyMFASid;
      v58[2 * v48 + 2] = 7;
      ++v39;
    }
    if ( *(_BYTE *)(v17 + 625) )
    {
      v49 = 2LL * v39;
      *(_QWORD *)&v58[2 * v49] = GlobalAuthenticationKeyPropertyAttestationSid;
      v58[2 * v49 + 2] = 7;
      ++v39;
    }
  }
  if ( (a12 & 4) != 0 )
  {
    v50 = 2LL * v39;
    *(_QWORD *)&v58[2 * v50] = GlobalFreshnessSid;
    v58[2 * v50 + 2] = 7;
    ++v39;
  }
  v76 = v61;
  v75[0] = v40;
  v74 = v58;
  v73[0] = v39;
  if ( a7
    && (unsigned int)KdcIsLHFunctionalLevel()
    && ((unsigned int)LsaIIsLastInteractiveLogonInfoEnabled() || KdcGlobalEmitLILI) )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
    v51 = *(LARGE_INTEGER *)(v17 + 392);
    v67.LastFailedLogon.QuadPart = *(_QWORD *)(v17 + 400);
    v67.FailedAttemptCountSinceLastSuccessfulLogon = *(_DWORD *)(v17 + 408);
    if ( !v51.QuadPart )
      v51.QuadPart = 0x7FFFFFFFFFFFFFFFLL;
    v67.LastSuccessfulLogon = v51;
    v41 = &v67;
  }
  inited = PAC_InitEx2(
             (struct _SAMPR_USER_ALL_INFORMATION *)v17,
             (struct _SAMPR_GET_GROUPS_BUFFER *)v75,
             (struct _SID_AND_ATTRIBUTES_LIST *)v73,
             GlobalDomainSid,
             Size,
             &DestinationString,
             v64,
             v63,
             v57,
             v79,
             v70,
             v69,
             v41,
             &v62);
  v53 = inited;
  if ( inited < 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        137,
        WPP_b168486f65343579948eb0cc9cf7c178_Traceguids,
        (unsigned int)inited);
    if ( (KDCInfoLevel & 0x10000000) != 0 )
    {
      v54 = v71;
      *v71 = v53;
      v54[1] = 68099534;
      v54[2] = 2;
    }
LABEL_102:
    wil::details::lambda_call__lambda_bde1109c27f1d473909aeaf58a3f4245___::_lambda_call__lambda_bde1109c27f1d473909aeaf58a3f4245___(v77);
    return 60;
  }
  *v72 = v62;
  v62 = 0;
  wil::details::lambda_call__lambda_bde1109c27f1d473909aeaf58a3f4245___::_lambda_call__lambda_bde1109c27f1d473909aeaf58a3f4245___(v77);
  return 0;
}

```

## disassembly

```asm
0x18005c560  push    rbp
0x18005c562  push    rbx
0x18005c563  push    rsi
0x18005c564  push    rdi
0x18005c565  push    r12
0x18005c567  push    r13
0x18005c569  push    r14
0x18005c56b  push    r15
0x18005c56d  sub     rsp, 1A8h
0x18005c574  lea     rbp, [rsp+70h]
0x18005c579  mov     rax, cs:__security_cookie
0x18005c580  xor     rax, rbp
0x18005c583  mov     [rbp+170h+var_48], rax
0x18005c58a  mov     [rbp+170h+var_148], r9d
0x18005c58e  mov     [rbp+170h+var_144], r8d
0x18005c592  mov     r13, rdx
0x18005c595  mov     rdi, rcx
0x18005c598  mov     [rbp+170h+var_118], rcx
0x18005c59c  mov     rax, [rbp+170h+arg_78]
0x18005c5a3  mov     [rbp+170h+var_100], rax
0x18005c5a7  mov     rbx, [rbp+170h+arg_20]
0x18005c5ae  mov     r10, [rbp+170h+arg_28]
0x18005c5b5  mov     [rbp+170h+var_138], r10
0x18005c5b9  mov     r14, [rbp+170h+arg_38]
0x18005c5c0  mov     rax, [rbp+170h+arg_40]
0x18005c5c7  mov     [rbp+170h+var_108], rax
0x18005c5cb  mov     rax, [rbp+170h+arg_48]
0x18005c5d2  mov     [rbp+170h+var_110], rax
0x18005c5d6  mov     rsi, [rbp+170h+arg_50]
0x18005c5dd  mov     r15, [rbp+170h+Src]
0x18005c5e4  mov     r11, [rbp+170h+arg_70]
0x18005c5eb  mov     [rbp+170h+var_F8], r11
0x18005c5ef  xor     r12d, r12d
0x18005c5f2  mov     [rbp+170h+var_150], r12
0x18005c5f6  xorps   xmm0, xmm0
0x18005c5f9  movups  xmmword ptr [rbp+170h+var_78], xmm0
0x18005c600  movups  [rbp+170h+var_68], xmm0
0x18005c607  movups  [rbp+170h+var_58], xmm0
0x18005c60e  mov     [rbp+170h+var_170], r12d
0x18005c612  mov     [rbp+170h+var_15C], r12d
0x18005c616  mov     [rbp+170h+var_EC], r12d
0x18005c61d  mov     [rbp+170h+var_168], r12
0x18005c621  mov     [rbp+170h+var_DC], r12d
0x18005c628  mov     [rbp+170h+var_158], r12
0x18005c62c  mov     dword ptr [rbp+170h+var_130.LastSuccessfulLogon], r12d
0x18005c630  xor     eax, eax
0x18005c632  movups  xmmword ptr [rbp+170h+var_130.LastSuccessfulLogon+4], xmm0
0x18005c636  mov     dword ptr [rbp+170h+var_130+14h], eax
0x18005c639  mov     [rbp+170h+var_160], r12d
0x18005c63d  lea     rax, [rbp+170h+var_150]
0x18005c641  mov     [rsp+1E0h+var_1B8], rax
0x18005c646  lea     rax, [rbp+170h+var_168]
0x18005c64a  mov     [rsp+1E0h+Size], rax
0x18005c64f  lea     r9, [rbp+170h+var_158]
0x18005c653  lea     r8, [rbp+170h+var_78]
0x18005c65a  lea     rdx, [rbp+170h+var_170]
0x18005c65e  lea     rcx, [rbp+170h+var_A0]
0x18005c665  call    _lambda_bde1109c27f1d473909aeaf58a3f4245____lambda_bde1109c27f1d473909aeaf58a3f4245_
0x18005c66a  mov     rdx, rax
0x18005c66d  lea     rcx, [rbp+170h+var_D0]
0x18005c674  call    wil__scope_exit__lambda_bde1109c27f1d473909aeaf58a3f4245___
0x18005c679  nop
0x18005c67a  mov     [r11], r12
0x18005c67d  lea     rax, WPP_GLOBAL_Control
0x18005c684  mov     rdx, cs:WPP_GLOBAL_Control
0x18005c68b  mov     r12d, dword ptr [rbp+170h+arg_58]
0x18005c692  cmp     rdx, rax
0x18005c695  jz      short loc_18005C6F3
0x18005c697  test    dword ptr [rdx+1Ch], 8000h
0x18005c69e  jz      short loc_18005C6F3
0x18005c6a0  lea     rcx, [rdi+150h]
0x18005c6a7  lea     r8, [rdi+40h]
0x18005c6ab  lea     r9, [rdi+30h]
0x18005c6af  mov     dword ptr [rsp+1E0h+var_190], r12d
0x18005c6b4  mov     eax, [rdi+11Ch]
0x18005c6ba  mov     dword ptr [rsp+1E0h+var_198], eax
0x18005c6be  mov     eax, [rdi+148h]
0x18005c6c4  mov     [rsp+1E0h+var_1A0], eax
0x18005c6c8  mov     eax, [rdi+118h]
0x18005c6ce  mov     [rsp+1E0h+var_1A8], eax
0x18005c6d2  mov     eax, [rdi+110h]
0x18005c6d8  mov     [rsp+1E0h+var_1B0], eax
0x18005c6dc  mov     [rsp+1E0h+var_1B8], rcx
0x18005c6e1  mov     [rsp+1E0h+Size], r8; Size
0x18005c6e6  mov     rcx, [rdx+10h]
0x18005c6ea  call    WPP_SF_ZZZDDDDD
0x18005c6ef  mov     r10, [rbp+170h+var_138]
0x18005c6f3  test    rbx, rbx
0x18005c6f6  jz      short loc_18005C73B
0x18005c6f8  cmp     qword ptr [rbx+18h], 0
0x18005c6fd  jz      short loc_18005C73B
0x18005c6ff  mov     eax, [rbp+170h+var_170]
0x18005c702  lea     r8, [rbp+170h+var_78]
0x18005c709  lea     r8, [r8+rax*8]; struct _PAC_INFO_BUFFER **
0x18005c70d  mov     rdx, rbx; struct _KERB_ENCRYPTION_KEY *
0x18005c710  mov     rcx, rdi; struct _USER_INTERNAL6_INFORMATION *
0x18005c713  call    ?KdcBuildSupplementalCredentials@@YAJPEAU_USER_INTERNAL6_INFORMATION@@PEAU_KERB_ENCRYPTION_KEY@@PEAPEAU_PAC_INFO_BUFFER@@@Z; KdcBuildSupplementalCredentials(_USER_INTERNAL6_INFORMATION *,_KERB_ENCRYPTION_KEY *,_PAC_INFO_BUFFER * *)
0x18005c718  mov     ebx, eax
0x18005c71a  test    eax, eax
0x18005c71c  jz      short loc_18005C731
0x18005c71e  lea     rcx, [rbp+170h+var_D0]
0x18005c725  call    wil__details__lambda_call__lambda_bde1109c27f1d473909aeaf58a3f4245______lambda_call__lambda_bde1109c27f1d473909aeaf58a3f4245___
0x18005c72a  mov     eax, ebx
0x18005c72c  jmp     loc_18005CD5D
0x18005c731  mov     ecx, [rbp+170h+var_170]
0x18005c734  inc     ecx
0x18005c736  mov     [rbp+170h+var_170], ecx
0x18005c739  jmp     short loc_18005C771
0x18005c73b  test    r10, r10
0x18005c73e  jz      short loc_18005C76E
0x18005c740  mov     eax, [rbp+170h+var_170]
0x18005c743  lea     rdx, [rbp+170h+var_78]
0x18005c74a  lea     rdx, [rdx+rax*8]; struct _PAC_INFO_BUFFER **
0x18005c74e  lea     r8, [rbp+170h+var_160]; unsigned int *
0x18005c752  mov     rcx, r10; struct PKERB_AUTHORIZATION_DATA_s *
0x18005c755  call    ?KdcExtractFieldsFromPac@@YAJPEAUPKERB_AUTHORIZATION_DATA_s@@PEAPEAU_PAC_INFO_BUFFER@@PEAK@Z; KdcExtractFieldsFromPac(PKERB_AUTHORIZATION_DATA_s *,_PAC_INFO_BUFFER * *,ulong *)
0x18005c75a  test    eax, eax
0x18005c75c  jnz     short loc_18005C76E
0x18005c75e  mov     ecx, [rbp+170h+var_170]
0x18005c761  cmp     [rbp+rcx*8+170h+var_78], 0
0x18005c76a  jz      short loc_18005C771
0x18005c76c  jmp     short loc_18005C734
0x18005c76e  mov     ecx, [rbp+170h+var_170]
0x18005c771  mov     r9, [rbp+170h+arg_30]
0x18005c778  test    r9, r9
0x18005c77b  jz      short loc_18005C7A3
0x18005c77d  mov     eax, ecx
0x18005c77f  lea     r8, [rbp+170h+var_78]
0x18005c786  lea     r8, [r8+rax*8]; struct _PAC_INFO_BUFFER **
0x18005c78a  mov     rdx, r14; struct _UNICODE_STRING *
0x18005c78d  mov     rcx, r9; union _LARGE_INTEGER *
0x18005c790  call    ?KdcBuildPacVerifier@@YAJPEAT_LARGE_INTEGER@@PEAU_UNICODE_STRING@@PEAPEAU_PAC_INFO_BUFFER@@@Z; KdcBuildPacVerifier(_LARGE_INTEGER *,_UNICODE_STRING *,_PAC_INFO_BUFFER * *)
0x18005c795  mov     ebx, eax
0x18005c797  test    eax, eax
0x18005c799  jnz     short loc_18005C71E
0x18005c79b  mov     ecx, [rbp+170h+var_170]
0x18005c79e  inc     ecx
0x18005c7a0  mov     [rbp+170h+var_170], ecx
0x18005c7a3  lea     rdx, [rdi+150h]; struct _UNICODE_STRING *
0x18005c7aa  mov     eax, ecx
0x18005c7ac  lea     r8, DomainName2; struct _UNICODE_STRING *
0x18005c7b3  cmp     cs:?KdcGlobalNoExtraFieldsInUpnDnsInfo@@3KA, 0; ulong KdcGlobalNoExtraFieldsInUpnDnsInfo
0x18005c7ba  jnz     short loc_18005C7E7
0x18005c7bc  lea     rcx, [rbp+170h+var_78]
0x18005c7c3  lea     rcx, [rcx+rax*8]
0x18005c7c7  lea     r9, [rdi+30h]; struct _UNICODE_STRING *
0x18005c7cb  mov     [rsp+1E0h+var_1B8], rcx; struct _PAC_INFO_BUFFER **
0x18005c7d0  mov     eax, [rdi+110h]
0x18005c7d6  mov     dword ptr [rsp+1E0h+Size], eax; unsigned int
0x18005c7da  mov     cl, [rdi+14Ch]; unsigned __int8
0x18005c7e0  call    ?KdcBuildExtraLogonInfoExBuffer@@YAJEPEAU_UNICODE_STRING@@00KPEAPEAU_PAC_INFO_BUFFER@@@Z; KdcBuildExtraLogonInfoExBuffer(uchar,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,_PAC_INFO_BUFFER * *)
0x18005c7e5  jmp     short loc_18005C7FD
0x18005c7e7  lea     r9, [rbp+170h+var_78]
0x18005c7ee  lea     r9, [r9+rax*8]; struct _PAC_INFO_BUFFER **
0x18005c7f2  mov     cl, [rdi+14Ch]; unsigned __int8
0x18005c7f8  call    ?KdcBuildExtraLogonInfoBuffer@@YAJEPEAU_UNICODE_STRING@@0PEAPEAU_PAC_INFO_BUFFER@@@Z; KdcBuildExtraLogonInfoBuffer(uchar,_UNICODE_STRING *,_UNICODE_STRING *,_PAC_INFO_BUFFER * *)
0x18005c7fd  test    eax, eax
0x18005c7ff  js      loc_18005CD4C
0x18005c805  mov     eax, [rbp+170h+var_170]
0x18005c808  inc     eax
0x18005c80a  mov     [rbp+170h+var_170], eax
0x18005c80d  test    rsi, rsi
0x18005c810  jz      short loc_18005C837
0x18005c812  lea     rdx, [rbp+170h+var_78]
0x18005c819  lea     rdx, [rdx+rax*8]; struct _PAC_INFO_BUFFER **
0x18005c81d  mov     rcx, rsi; struct _SAM_CLAIMS_BLOB *
0x18005c820  call    ?KdcBuildClaimsPacData@@YAJPEAU_SAM_CLAIMS_BLOB@@PEAPEAU_PAC_INFO_BUFFER@@@Z; KdcBuildClaimsPacData(_SAM_CLAIMS_BLOB *,_PAC_INFO_BUFFER * *)
0x18005c825  mov     ebx, eax
0x18005c827  test    eax, eax
0x18005c829  jnz     loc_18005C71E
0x18005c82f  mov     eax, [rbp+170h+var_170]
0x18005c832  inc     eax
0x18005c834  mov     [rbp+170h+var_170], eax
0x18005c837  test    r12b, 8
0x18005c83b  jz      short loc_18005C865
0x18005c83d  lea     rdx, [rbp+170h+var_78]
0x18005c844  lea     rdx, [rdx+rax*8]
0x18005c848  mov     ecx, [rbp+170h+arg_60]
0x18005c84e  call    ?KdcBuildPacAttributes@@YAJW4PacRequestType@@PEAPEAU_PAC_INFO_BUFFER@@@Z; KdcBuildPacAttributes(PacRequestType,_PAC_INFO_BUFFER * *)
0x18005c853  mov     ebx, eax
0x18005c855  test    eax, eax
0x18005c857  jnz     loc_18005C71E
0x18005c85d  mov     eax, [rbp+170h+var_170]
0x18005c860  inc     eax
0x18005c862  mov     [rbp+170h+var_170], eax
0x18005c865  test    r12b, 10h
0x18005c869  jz      short loc_18005C890
0x18005c86b  test    r15, r15
0x18005c86e  jz      short loc_18005C890
0x18005c870  lea     rdx, [rbp+170h+var_78]
0x18005c877  lea     rdx, [rdx+rax*8]; struct _PAC_INFO_BUFFER **
0x18005c87b  mov     rcx, r15; Src
0x18005c87e  call    ?KdcBuildPacRequestor@@YAJPEAXPEAPEAU_PAC_INFO_BUFFER@@@Z; KdcBuildPacRequestor(void *,_PAC_INFO_BUFFER * *)
0x18005c883  mov     ebx, eax
0x18005c885  test    eax, eax
0x18005c887  jnz     loc_18005C71E
0x18005c88d  inc     [rbp+170h+var_170]
0x18005c890  mov     eax, [r13+0]
0x18005c894  lea     rsi, ds:0[rax*8]
0x18005c89c  xor     ebx, ebx
0x18005c89e  mov     r12d, 6B637453h
0x18005c8a4  mov     r15, 0FFFFFFFFFFFFFF0h
0x18005c8ae  test    rsi, rsi
0x18005c8b1  jz      short loc_18005C90A
0x18005c8b3  cmp     rsi, cs:g_ulMaxStackAllocSize
0x18005c8ba  ja      short loc_18005C90A
0x18005c8bc  mov     rcx, cs:g_ulAdditionalProbeSize
0x18005c8c3  add     rcx, 8
0x18005c8c7  add     rcx, rsi
0x18005c8ca  cmp     rcx, rsi
0x18005c8cd  jb      short loc_18005C90A
0x18005c8cf  call    VerifyStackAvailable
0x18005c8d4  test    eax, eax
0x18005c8d6  jz      short loc_18005C90A
0x18005c8d8  lea     rax, [rsi+8]
0x18005c8dc  lea     rcx, [rax+0Fh]
0x18005c8e0  cmp     rcx, rax
0x18005c8e3  ja      short loc_18005C8E8
0x18005c8e5  mov     rcx, r15
0x18005c8e8  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18005c8ec  mov     rax, rcx
0x18005c8ef  call    _alloca_probe
0x18005c8f4  sub     rsp, rcx
0x18005c8f7  lea     rbx, [rsp+1E0h+var_170]
0x18005c8fc  test    rbx, rbx
0x18005c8ff  jz      short loc_18005C90A
0x18005c901  mov     [rbx], r12d
0x18005c904  add     rbx, 8
0x18005c908  jnz     short loc_18005C931
0x18005c90a  lea     rcx, [rsi+8]
0x18005c90e  cmp     rcx, rsi
0x18005c911  jb      short loc_18005C931
0x18005c913  mov     rax, cs:g_pfnAllocate
0x18005c91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c91f  mov     rbx, rax
0x18005c922  test    rax, rax
0x18005c925  jz      short loc_18005C931
0x18005c927  mov     dword ptr [rax], 70616548h
0x18005c92d  add     rbx, 8
0x18005c931  mov     [rbp+170h+var_158], rbx
0x18005c935  test    rbx, rbx
0x18005c938  jz      loc_18005CD4C
0x18005c93e  mov     eax, [r13+0]
0x18005c942  lea     ecx, [rax+5]
0x18005c945  cmp     ecx, eax
0x18005c947  jb      loc_18005CD4C
0x18005c94d  mov     esi, ecx
0x18005c94f  shl     rsi, 4
0x18005c953  mov     eax, 0FFFFFFFFh
0x18005c958  cmp     rsi, rax
0x18005c95b  ja      loc_18005CD4C
0x18005c961  xor     ebx, ebx
0x18005c963  test    esi, esi
0x18005c965  jz      short loc_18005C9C1
0x18005c967  mov     r14d, esi
0x18005c96a  cmp     r14, cs:g_ulMaxStackAllocSize
0x18005c971  ja      short loc_18005C9C1
0x18005c973  mov     rcx, cs:g_ulAdditionalProbeSize
0x18005c97a  add     rcx, 8
0x18005c97e  add     rcx, r14
0x18005c981  cmp     rcx, r14
0x18005c984  jb      short loc_18005C9C1
0x18005c986  call    VerifyStackAvailable
0x18005c98b  test    eax, eax
0x18005c98d  jz      short loc_18005C9C1
0x18005c98f  lea     rax, [r14+8]
0x18005c993  lea     rcx, [rax+0Fh]
0x18005c997  cmp     rcx, rax
0x18005c99a  ja      short loc_18005C99F
0x18005c99c  mov     rcx, r15
0x18005c99f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18005c9a3  mov     rax, rcx
0x18005c9a6  call    _alloca_probe
0x18005c9ab  sub     rsp, rcx
0x18005c9ae  lea     rbx, [rsp+1E0h+var_170]
0x18005c9b3  test    rbx, rbx
0x18005c9b6  jz      short loc_18005C9C1
0x18005c9b8  mov     [rbx], r12d
0x18005c9bb  add     rbx, 8
0x18005c9bf  jnz     short loc_18005C9EA
0x18005c9c1  mov     eax, esi
0x18005c9c3  lea     rcx, [rax+8]
0x18005c9c7  cmp     rcx, rax
0x18005c9ca  jb      short loc_18005C9EA
0x18005c9cc  mov     rax, cs:g_pfnAllocate
0x18005c9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c9d8  mov     rbx, rax
0x18005c9db  test    rax, rax
0x18005c9de  jz      short loc_18005C9EA
0x18005c9e0  mov     dword ptr [rax], 70616548h
0x18005c9e6  add     rbx, 8
0x18005c9ea  mov     [rbp+170h+var_168], rbx
0x18005c9ee  test    rbx, rbx
0x18005c9f1  jz      loc_18005CD4C
0x18005c9f7  xor     ebx, ebx
0x18005c9f9  xor     r12d, r12d
0x18005c9fc  xor     esi, esi
0x18005c9fe  mov     [rbp+170h+var_140], rsi
0x18005ca02  xor     r14d, r14d
0x18005ca05  cmp     [r13+0], ebx
  ... truncated ...
```
