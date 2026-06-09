# KdcGetSidsFromTgt(KERB_ENCRYPTED_TICKET *,_KDC_TICKET_INFO *,uchar,_KDC_AUTHZ_INFO *,_KDC_AUTHZ_GROUP_BUFFERS *,long *,_UNICODE_STRING *,_UNICODE_STRING *,void * *)

- ea: `0x1800485e4`
- end: `0x180049050`
- name: `?KdcGetSidsFromTgt@@YAJPEAUKERB_ENCRYPTED_TICKET@@PEAU_KDC_TICKET_INFO@@EPEAU_KDC_AUTHZ_INFO@@PEAU_KDC_AUTHZ_GROUP_BUFFERS@@PEAJPEAU_UNICODE_STRING@@5PEAPEAX@Z`
- size: `2668`
- prototype: `int(struct KERB_ENCRYPTED_TICKET *, struct _KDC_TICKET_INFO *, unsigned __int8, struct _KDC_AUTHZ_INFO *, struct _KDC_AUTHZ_GROUP_BUFFERS *, int *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, void **)`
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001ce44`
- `0x1800276cc`

## callees

- `0x1800038f0`
- `0x180003908`
- `0x1800101c4`
- `0x1800101ec`
- `0x18001022c`
- `0x1800106c8`
- `0x180010768`
- `0x180020230`
- `0x18004364c`
- `0x1800453c4`
- `0x1800464f4`
- `0x180047850`
- `0x1800485e4`
- `0x18005a060`
- `0x18006fc78`
- `0x180070f30`
- `0x1800710d8`
- `0x180072338`
- `0x18007d4b0`
- `0x18007e71c`
- `0x18007f1e4`
- `0x18007f69c`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x180048b17`
- `ntdll!RtlEqualUnicodeString` at `0x180048b17`
- `ntdll!RtlSubAuthoritySid` at `0x180048ed9`
- `ntdll!RtlSubAuthoritySid` at `0x180048ed9`
- `ntdll!RtlSubAuthorityCountSid` at `0x180048ecb`
- `ntdll!RtlSubAuthorityCountSid` at `0x180048ecb`
- `ntdll!RtlLengthSid` at `0x1800489c4`
- `ntdll!RtlLengthSid` at `0x1800489d2`
- `ntdll!RtlLengthSid` at `0x1800489f6`
- `ntdll!RtlLengthSid` at `0x180048e62`
- `ntdll!RtlLengthSid` at `0x180048ea6`
- `ntdll!RtlLengthSid` at `0x1800489c4`
- `ntdll!RtlLengthSid` at `0x1800489d2`
- `ntdll!RtlLengthSid` at `0x1800489f6`
- `ntdll!RtlLengthSid` at `0x180048e62`
- `ntdll!RtlLengthSid` at `0x180048ea6`
- `ntdll!RtlCopySid` at `0x180048eb4`
- `ntdll!RtlCopySid` at `0x180048eb4`
- `ntdll!RtlEqualSid` at `0x180048c16`
- `ntdll!RtlEqualSid` at `0x180048c7c`
- `ntdll!RtlEqualSid` at `0x180048c16`
- `ntdll!RtlEqualSid` at `0x180048c7c`
- `SAMSRV!SamIGetAliasMembership` at `0x180048d83`
- `SAMSRV!SamIGetAliasMembership` at `0x180048d83`
- `SAMSRV!SamIDecodeClaimsBlobToAuthz` at `0x180048f25`
- `SAMSRV!SamIDecodeClaimsBlobToAuthz` at `0x180048f25`
- `SAMSRV!SamIGetResourceGroupMembershipsTransitive` at `0x180048d2c`
- `SAMSRV!SamIGetResourceGroupMembershipsTransitive` at `0x180048d2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KdcGetSidsFromTgt(
        struct KERB_ENCRYPTED_TICKET *a1,
        struct _KDC_TICKET_INFO *a2,
        char a3,
        struct _KDC_AUTHZ_INFO *a4,
        struct _KDC_AUTHZ_GROUP_BUFFERS *a5,
        int *a6,
        struct _UNICODE_STRING *a7,
        struct _UNICODE_STRING *a8,
        void **a9)
{
  __int64 v11; // rax
  unsigned int PacFromAuthData; // eax
  unsigned int v13; // edi
  struct _PAC_INFO_BUFFER *v14; // rbx
  int v15; // eax
  struct _PACTYPE *v16; // r12
  struct _PAC_INFO_BUFFER *v17; // r8
  struct _PACTYPE *v19; // rcx
  struct _PAC_INFO_BUFFER *v20; // r8
  struct _PAC_INFO_BUFFER *v21; // rax
  __int64 v22; // r9
  struct _PAC_INFO_BUFFER *v23; // r13
  unsigned __int16 *v24; // rbx
  __int64 v25; // rdx
  WCHAR *v26; // rax
  __int64 v27; // rcx
  WCHAR *v28; // rax
  struct _PAC_INFO_BUFFER *v29; // rax
  struct _PAC_INFO_BUFFER *v30; // r13
  ULONG v31; // ebx
  ULONG v32; // eax
  void *v33; // rax
  ULONG v34; // eax
  struct _PAC_INFO_BUFFER *v35; // rax
  __int64 v36; // rcx
  __int64 v37; // r10
  __int64 v38; // rbx
  int v39; // eax
  struct _PAC_INFO_BUFFER *v40; // r8
  struct _PAC_INFO_BUFFER *v41; // rax
  struct _PAC_INFO_BUFFER *v42; // r13
  unsigned int v43; // ebx
  char v44; // r12
  struct _NETLOGON_VALIDATION_SAM_INFO3 *v45; // rcx
  unsigned int i; // ebx
  int v47; // ebx
  CSecurityData *v48; // rcx
  __int64 v49; // rdx
  _QWORD *v50; // rdi
  int v51; // r13d
  bool v52; // zf
  unsigned int v53; // r13d
  _QWORD *v54; // rax
  __int64 j; // r14
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 k; // rax
  __int64 v59; // rdx
  ULONG v60; // ebx
  char *v61; // rax
  char *v62; // r15
  __int64 v63; // r12
  unsigned int v64; // r13d
  HLOCAL v65; // rbx
  ULONG v66; // eax
  PUCHAR v67; // rax
  __int64 v68; // rax
  __int128 v69; // xmm2
  struct _NETLOGON_VALIDATION_SAM_INFO3 *v70; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v71; // [rsp+60h] [rbp-A8h] BYREF
  struct _PAC_INFO_BUFFER *v72; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v73[3]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v74; // [rsp+88h] [rbp-80h] BYREF
  __int64 v75; // [rsp+90h] [rbp-78h]
  __int128 v76; // [rsp+98h] [rbp-70h] BYREF
  struct _UNICODE_STRING v77; // [rsp+A8h] [rbp-60h] BYREF
  struct _UNICODE_STRING v78; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v79; // [rsp+C8h] [rbp-40h] BYREF
  union _LARGE_INTEGER Time; // [rsp+D0h] [rbp-38h] BYREF
  UNICODE_STRING String2; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v82; // [rsp+E8h] [rbp-20h] BYREF
  UNICODE_STRING String1; // [rsp+F8h] [rbp-10h] BYREF
  __m256i v84; // [rsp+108h] [rbp+0h] BYREF
  __int128 v85; // [rsp+128h] [rbp+20h]
  __int128 v86; // [rsp+138h] [rbp+30h]
  __int128 v87; // [rsp+148h] [rbp+40h]
  __int128 v88; // [rsp+160h] [rbp+58h] BYREF
  __m256i v89; // [rsp+170h] [rbp+68h] BYREF
  __int128 v90; // [rsp+190h] [rbp+88h]
  __int128 v91; // [rsp+1A0h] [rbp+98h]
  __int128 v92; // [rsp+1B0h] [rbp+A8h]
  _BYTE v93[80]; // [rsp+1C8h] [rbp+C0h] BYREF
  char v94; // [rsp+218h] [rbp+110h] BYREF
  char v96; // [rsp+2A8h] [rbp+1A0h]

  v79 = 0;
  v72 = 0;
  v70 = 0;
  memset(v73, 0, sizeof(v73));
  v74 = 0;
  v75 = 0;
  v82 = 0;
  v76 = 0;
  v88 = 0;
  LODWORD(v71) = 0;
  String1 = 0;
  memset_0(&v84, 0, 0x50u);
  v77 = 0;
  v78 = 0;
  v11 = lambda_530ddfda5690aa4758d6a6bc63144caf_::_lambda_530ddfda5690aa4758d6a6bc63144caf_(
          (unsigned int)&v94,
          (unsigned int)&v70,
          (unsigned int)&v84,
          (unsigned int)&v79,
          (__int64)&v76,
          (__int64)&v82,
          (__int64)&String1,
          (__int64)&v77,
          (__int64)&v78);
  wil::scope_exit__lambda_530ddfda5690aa4758d6a6bc63144caf___(v93, v11);
  memset_0(&v89, 0, 0x50u);
  *(__m256i *)a5 = v89;
  *((_OWORD *)a5 + 2) = v90;
  *((_OWORD *)a5 + 3) = v91;
  *((_OWORD *)a5 + 4) = v92;
  if ( (*(_BYTE *)a1 & 0x10) == 0 )
    goto LABEL_16;
  PacFromAuthData = KerbGetPacFromAuthData(*((_QWORD *)a1 + 20), &v79, 0, &v72);
  v13 = PacFromAuthData;
  v14 = v72;
  if ( !v72 )
  {
    *a6 = 0;
LABEL_108:
    v13 = 60;
    goto LABEL_109;
  }
  if ( PacFromAuthData )
    goto LABEL_5;
  v13 = KdcVerifyPacSignature(0, 0, a2, 0, 0, *((_DWORD *)v72 + 4), *((unsigned __int8 **)v72 + 3));
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, WPP_3875113a630833a3e73becf979560e87_Traceguids);
    v15 = KerbMapKerbError(v13);
    goto LABEL_11;
  }
  v16 = (struct _PACTYPE *)*((_QWORD *)v14 + 3);
  if ( !PAC_UnMarshal(v16, *((_DWORD *)v14 + 4)) )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, WPP_3875113a630833a3e73becf979560e87_Traceguids);
    goto LABEL_16;
  }
  v72 = PAC_Find(v16, 1u, v17);
  if ( !v72 )
  {
LABEL_16:
    *a6 = -1073741811;
    wil::details::lambda_call__lambda_530ddfda5690aa4758d6a6bc63144caf___::_lambda_call__lambda_530ddfda5690aa4758d6a6bc63144caf___(v93);
    return 60;
  }
  v13 = 12;
  if ( a7 || a8 )
  {
    v21 = PAC_Find(v19, 0xCu, v20);
    v23 = v21;
    if ( v21 )
    {
      v20 = (struct _PAC_INFO_BUFFER *)*((unsigned int *)v21 + 1);
      if ( (unsigned int)v20 >= 0x14 )
      {
        v24 = (unsigned __int16 *)*((_QWORD *)v21 + 1);
        if ( v22 )
        {
          v25 = v24[2];
          if ( (unsigned int)v25 + v24[3] <= (unsigned int)v20 )
          {
            v26 = (WCHAR *)MIDL_user_allocate(v25 + 2);
            v77.Buffer = v26;
            if ( !v26 )
              goto LABEL_57;
            v77.Length = v24[2];
            v77.MaximumLength = v77.Length + 2;
            memcpy_0(v26, (char *)v24 + v24[3], v24[2]);
          }
        }
        if ( a8 )
        {
          v27 = v24[6];
          if ( (unsigned int)v27 + v24[7] <= *((_DWORD *)v23 + 1) )
          {
            v28 = (WCHAR *)MIDL_user_allocate(v27 + 2);
            v78.Buffer = v28;
            if ( !v28 )
              goto LABEL_57;
            v78.Length = v24[6];
            v78.MaximumLength = v78.Length + 2;
            memcpy_0(v28, (char *)v24 + v24[7], v24[6]);
          }
        }
      }
      else if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          122,
          WPP_3875113a630833a3e73becf979560e87_Traceguids,
          (unsigned int)v20,
          20);
      }
    }
  }
  if ( a9 )
  {
    v29 = PAC_Find(v16, 0x12u, v20);
    v30 = v29;
    if ( v29 )
    {
      if ( *((_DWORD *)v29 + 1) >= 0xCu )
      {
        v31 = *((_DWORD *)v29 + 1);
        if ( v31 >= RtlLengthSid(*((PSID *)v29 + 1)) )
        {
          v32 = RtlLengthSid(*((PSID *)v30 + 1));
          v33 = MIDL_user_allocate(v32);
          *a9 = v33;
          if ( !v33 )
            goto LABEL_57;
          v34 = RtlLengthSid(*((PSID *)v30 + 1));
          memcpy_0(*a9, *((const void **)v30 + 1), v34);
        }
      }
    }
  }
  if ( !a3 )
  {
    v35 = PAC_Find(v16, 0xAu, v20);
    if ( !v35 )
    {
      if ( (CSecurityData **)v37 != &WPP_GLOBAL_Control && (*(_BYTE *)(v37 + 28) & 1) != 0 )
        WPP_SF_(*(_QWORD *)(v37 + 16), 126, WPP_3875113a630833a3e73becf979560e87_Traceguids);
      MicrosoftTelemetryAssertTriggeredNoArgs(v36);
      goto LABEL_46;
    }
    Time.QuadPart = 0;
    String2 = 0;
    if ( *((_DWORD *)v35 + 1) < 0xCu )
    {
      if ( (CSecurityData **)v37 != &WPP_GLOBAL_Control && (*(_BYTE *)(v37 + 28) & 1) != 0 )
        WPP_SF_Dd(
          *(_QWORD *)(v37 + 16),
          123,
          WPP_3875113a630833a3e73becf979560e87_Traceguids,
          *((unsigned int *)v35 + 1),
          12);
      goto LABEL_46;
    }
    v38 = *((_QWORD *)v35 + 1);
    if ( (unsigned __int64)*(unsigned __int16 *)(v38 + 8) + 6 > *((unsigned int *)v35 + 1) )
    {
LABEL_46:
      *a6 = -1073741811;
      goto LABEL_108;
    }
    KerbConvertGeneralizedTimeToLargeInt(&Time);
    if ( Time.QuadPart != *(_QWORD *)v38 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, WPP_3875113a630833a3e73becf979560e87_Traceguids);
LABEL_56:
      *a6 = -1073741715;
      v13 = 41;
      goto LABEL_109;
    }
    String2.Buffer = (PWSTR)(v38 + 10);
    String2.MaximumLength = *(_WORD *)(v38 + 8);
    String2.Length = String2.MaximumLength;
    if ( (unsigned int)KerbConvertPrincipalNameToString(&String1, &v71, (char *)a1 + 56) )
      goto LABEL_57;
    if ( !RtlEqualUnicodeString(&String1, &String2, 1u) )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_ZZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          125,
          (unsigned int)WPP_3875113a630833a3e73becf979560e87_Traceguids,
          (unsigned int)&String2,
          (__int64)&String1);
      goto LABEL_56;
    }
  }
  v39 = PAC_UnmarshallValidationInfo(&v70, *((unsigned __int8 **)v72 + 1), *((_DWORD *)v72 + 1));
  if ( v39 < 0 )
  {
LABEL_107:
    *a6 = v39;
    goto LABEL_108;
  }
  v41 = PAC_Find(v16, 0xDu, v40);
  v42 = v41;
  if ( v41 )
  {
    LODWORD(v82) = *((_DWORD *)v41 + 1);
    *((_QWORD *)&v82 + 1) = *((_QWORD *)v41 + 1);
    v43 = 0;
    v44 = 0;
    v96 = 0;
    while ( 1 )
    {
      v45 = v70;
      if ( v43 >= *((_DWORD *)v70 + 68) )
        break;
      if ( RtlEqualSid(GlobalClaimsValidSid, *(PSID *)(*((_QWORD *)v70 + 35) + 16LL * v43)) )
      {
        v44 = 1;
        v96 = 1;
        goto LABEL_77;
      }
      ++v43;
    }
  }
  else if ( (*((_BYTE *)a2 + 112) & 0x10) == 0 || *((_DWORD *)a2 + 12) == 502 || *((_BYTE *)a2 + 104) )
  {
LABEL_76:
    v44 = 0;
    v96 = 0;
LABEL_77:
    v45 = v70;
  }
  else
  {
    v44 = 1;
    v96 = 1;
    for ( i = 0; ; ++i )
    {
      v45 = v70;
      if ( i >= *((_DWORD *)v70 + 68) )
        break;
      if ( RtlEqualSid(GlobalClaimsValidSid, *(PSID *)(*((_QWORD *)v70 + 35) + 16LL * i)) )
        goto LABEL_76;
    }
  }
  if ( *((_QWORD *)a2 + 11) )
  {
    v15 = KdcFilterSids(
            (struct _UNICODE_STRING *)a2,
            0,
            (struct _SAM_CLAIMS_BLOB *)((unsigned __int64)&v82 & -(__int64)(v42 != 0)),
            (struct _SAM_CLAIMS_BLOB *)&v76,
            v45);
    if ( v15 < 0 )
    {
LABEL_11:
      *a6 = v15;
      goto LABEL_109;
    }
    v45 = v70;
  }
  else
  {
    v76 = v82;
  }
  v13 = KdcBuildPacSidList(v45, 1, (*((_DWORD *)a2 + 14) & 0x10) != 0, (struct _SAMPR_PSID_ARRAY *)&v73[1]);
  if ( v13 )
  {
LABEL_5:
    *a6 = -1073741801;
LABEL_109:
    wil::details::lambda_call__lambda_530ddfda5690aa4758d6a6bc63144caf___::_lambda_call__lambda_530ddfda5690aa4758d6a6bc63144caf___(v93);
    return v13;
  }
  *(_OWORD *)&v84.m256i_u64[1] = *(_OWORD *)&v73[1];
  v47 = SamIGetResourceGroupMembershipsTransitive(GlobalAccountDomainHandle, &v73[1], 0, v73);
  if ( v47 < 0 )
  {
    v48 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_88;
    v49 = v13 + 127;
LABEL_87:
    WPP_SF_d(*((_QWORD *)v48 + 2), v49, WPP_3875113a630833a3e73becf979560e87_Traceguids, (unsigned int)v47);
LABEL_88:
    *a6 = v47;
    goto LABEL_108;
  }
  v84.m256i_i64[0] = v73[0];
  v47 = SamIGetAliasMembership(GlobalBuiltInDomainHandle, &v73[1], &v74);
  if ( v47 < 0 )
  {
    v48 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_88;
    v49 = 128;
    goto LABEL_87;
  }
  v50 = 0;
  v84.m256i_i64[3] = v74;
  *(_QWORD *)&v85 = v75;
  v51 = LODWORD(v73[1]) + *(_DWORD *)v73[0];
  v52 = (_DWORD)v74 + v51 == 0;
  v53 = v74 + v51;
  LODWORD(v72) = v53;
  if ( !v52 )
  {
    v54 = MIDL_user_allocate(16LL * v53);
    v50 = v54;
    if ( v54 )
    {
      *(_QWORD *)&v86 = v54;
      for ( j = 0; (unsigned int)j < LODWORD(v73[1]); j = (unsigned int)(j + 1) )
      {
        v56 = 2LL * (unsigned int)j;
        v54[v56] = *(_QWORD *)(v73[2] + 8 * j);
        LODWORD(v54[v56 + 1]) = 7;
      }
      v57 = 0;
      for ( k = v73[0]; (unsigned int)v57 < *(_DWORD *)v73[0]; k = v73[0] )
      {
        v59 = 2LL * (unsigned int)j;
        v50[v59] = *(_QWORD *)(*(_QWORD *)(k + 8) + 8 * v57);
        LODWORD(v50[v59 + 1]) = 536870919;
        LODWORD(j) = j + 1;
        v57 = (unsigned int)(v57 + 1);
      }
      v60 = RtlLengthSid(GlobalBuiltInSid) + 4;
      v61 = (char *)MIDL_user_allocate((unsigned int)v74 * v60);
      v62 = v61;
      if ( v61 )
      {
        *((_QWORD *)&v85 + 1) = v61;
        LODWORD(v71) = 0;
        if ( (_DWORD)v74 )
        {
          v63 = v60;
          v64 = v71;
          do
          {
            v65 = GlobalBuiltInSid;
            v66 = RtlLengthSid(GlobalBuiltInSid);
            RtlCopySid(v66, v62, v65);
            LODWORD(v65) = *(_DWORD *)(v75 + 4LL * v64);
            v67 = RtlSubAuthorityCountSid(GlobalBuiltInSid);
            *RtlSubAuthoritySid(v62, (unsigned int)*v67 - 1) = (unsigned int)v65;
            v68 = 2LL * (unsigned int)j;
            v50[v68] = v62;
            LODWORD(v50[v68 + 1]) = 7;
            LODWORD(j) = j + 1;
            v62 += v63;
            ++v64;
          }
          while ( v64 < (unsigned int)v74 );
          v44 = v96;
          v53 = (unsigned int)v72;
        }
        goto LABEL_104;
      }
    }
LABEL_57:
    *a6 = -1073741801;
    goto LABEL_108;
  }
LABEL_104:
  if ( v44 && *((_QWORD *)&v76 + 1) )
  {
    v39 = SamIDecodeClaimsBlobToAuthz(*v50, &v76, &v88);
    if ( v39 < 0 )
      goto LABEL_107;
    v69 = v88;
  }
  else
  {
    v69 = v87;
  }
  *((_QWORD *)&v86 + 1) = v70;
  v70 = 0;
  *((_DWORD *)a4 + 2) = v53;
  *(_QWORD *)a4 = v50;
  *(__m256i *)a5 = v84;
  *((_OWORD *)a5 + 2) = v85;
  *((_OWORD *)a5 + 3) = v86;
  *((_OWORD *)a5 + 4) = v69;
  if ( v44 && *((_QWORD *)&v76 + 1) )
    *((_QWORD *)a4 + 2) = (char *)a5 + 64;
  memset_0(&v89, 0, 0x50u);
  v84 = v89;
  v85 = v90;
  v86 = v91;
  v87 = v92;
  if ( a7 )
  {
    *a7 = v77;
    v77 = 0;
  }
  if ( a8 )
  {
    *a8 = v78;
    v78 = 0;
  }
  *a6 = 0;
  wil::details::lambda_call__lambda_530ddfda5690aa4758d6a6bc63144caf___::_lambda_call__lambda_530ddfda5690aa4758d6a6bc63144caf___(v93);
  return 0;
}

```

## disassembly

```asm
0x1800485e4  mov     rax, rsp
0x1800485e7  mov     [rax+20h], r9
0x1800485eb  mov     [rax+18h], r8b
0x1800485ef  mov     [rax+10h], rdx
0x1800485f3  mov     [rax+8], rcx
0x1800485f7  push    rbp
0x1800485f8  push    rbx
0x1800485f9  push    rsi
0x1800485fa  push    rdi
0x1800485fb  push    r12
0x1800485fd  push    r13
0x1800485ff  push    r14
0x180048601  push    r15
0x180048603  lea     rbp, [rax-198h]
0x18004860a  sub     rsp, 258h
0x180048611  mov     rsi, rdx
0x180048614  mov     rbx, rcx
0x180048617  xor     r13d, r13d
0x18004861a  mov     [rbp+190h+var_1D0], r13
0x18004861e  mov     [rsp+290h+var_230], r13
0x180048623  mov     [rsp+290h+var_240], r13
0x180048628  xorps   xmm0, xmm0
0x18004862b  movups  xmmword ptr [rsp+290h+var_228+8], xmm0
0x180048630  mov     qword ptr [rsp+290h+var_228], r13
0x180048635  mov     [rbp+190h+var_210], r13
0x180048639  mov     [rbp+190h+var_208], r13
0x18004863d  movups  [rbp+190h+var_1B0], xmm0
0x180048641  xorps   xmm1, xmm1
0x180048644  movups  [rbp+190h+var_200], xmm1
0x180048648  movups  [rbp+190h+var_138], xmm0
0x18004864c  mov     dword ptr [rsp+290h+var_238], r13d
0x180048651  movups  xmmword ptr [rbp+190h+String1.Length], xmm1
0x180048655  lea     edi, [r13+50h]
0x180048659  mov     r8d, edi; Size
0x18004865c  xor     edx, edx; Val
0x18004865e  lea     rcx, [rbp+190h+var_190]; void *
0x180048662  call    memset_0
0x180048667  xorps   xmm0, xmm0
0x18004866a  movups  [rbp+190h+var_1F0], xmm0
0x18004866e  xorps   xmm1, xmm1
0x180048671  movups  [rbp+190h+var_1E0], xmm1
0x180048675  lea     rax, [rbp+190h+var_1E0]
0x180048679  mov     [rsp+40h], rax
0x18004867e  lea     rax, [rbp+190h+var_1F0]
0x180048682  mov     [rsp+290h+var_258], rax
0x180048687  lea     rax, [rbp+190h+String1]
0x18004868b  mov     [rsp+290h+var_260], rax
0x180048690  lea     rax, [rbp+190h+var_1B0]
0x180048694  mov     qword ptr [rsp+290h+var_268], rax
0x180048699  lea     rax, [rbp+190h+var_200]
0x18004869d  mov     [rsp+290h+var_270], rax
0x1800486a2  lea     r9, [rbp+190h+var_1D0]
0x1800486a6  lea     r8, [rbp+190h+var_190]
0x1800486aa  lea     rdx, [rsp+290h+var_240]
0x1800486af  lea     rcx, [rbp+190h+var_80]
0x1800486b6  call    _lambda_530ddfda5690aa4758d6a6bc63144caf____lambda_530ddfda5690aa4758d6a6bc63144caf_
0x1800486bb  mov     rdx, rax
0x1800486be  lea     rcx, [rbp+190h+var_D0]
0x1800486c5  call    wil__scope_exit__lambda_530ddfda5690aa4758d6a6bc63144caf___
0x1800486ca  nop
0x1800486cb  mov     r8d, edi; Size
0x1800486ce  xor     edx, edx; Val
0x1800486d0  lea     rcx, [rbp+190h+var_128]; void *
0x1800486d4  call    memset_0
0x1800486d9  movups  xmm0, [rbp+190h+var_128]
0x1800486dd  mov     rax, [rbp+190h+arg_20]
0x1800486e4  movaps  xmmword ptr [rax], xmm0
0x1800486e7  movups  xmm1, [rbp+190h+var_118]
0x1800486eb  movaps  xmmword ptr [rax+10h], xmm1
0x1800486ef  movups  xmm0, [rbp+190h+var_108]
0x1800486f6  movaps  xmmword ptr [rax+20h], xmm0
0x1800486fa  movups  xmm1, [rbp+190h+var_F8]
0x180048701  movaps  xmmword ptr [rax+30h], xmm1
0x180048705  movups  xmm0, [rbp+190h+var_E8]
0x18004870c  movaps  xmmword ptr [rax+40h], xmm0
0x180048710  test    byte ptr [rbx], 10h
0x180048713  jz      loc_180048814
0x180048719  lea     r9, [rsp+290h+var_230]
0x18004871e  xor     r8d, r8d
0x180048721  lea     rdx, [rbp+190h+var_1D0]
0x180048725  mov     rcx, [rbx+0A0h]
0x18004872c  call    KerbGetPacFromAuthData
0x180048731  mov     edi, eax
0x180048733  mov     rbx, [rsp+290h+var_230]
0x180048738  test    rbx, rbx
0x18004873b  jnz     short loc_18004874C
0x18004873d  mov     rax, [rbp+190h+arg_28]
0x180048744  mov     [rax], r13d
0x180048747  jmp     loc_180048F38
0x18004874c  test    eax, eax
0x18004874e  jz      short loc_180048762
0x180048750  mov     rax, [rbp+190h+arg_28]
0x180048757  mov     dword ptr [rax], 0C0000017h
0x18004875d  jmp     loc_180048F3D
0x180048762  mov     rax, [rbx+18h]
0x180048766  mov     [rsp+290h+var_260], rax; unsigned __int8 *
0x18004876b  mov     eax, [rbx+10h]
0x18004876e  mov     [rsp+290h+var_268], eax; unsigned int
0x180048772  mov     dword ptr [rsp+290h+var_270], r13d; unsigned int
0x180048777  xor     r9d, r9d; unsigned __int8 *
0x18004877a  mov     r8, rsi; struct _KDC_TICKET_INFO *
0x18004877d  xor     edx, edx; struct _KDC_U2U_TICKET_INFO *
0x18004877f  xor     ecx, ecx; struct _KDC_S4U_TICKET_INFO *
0x180048781  call    ?KdcVerifyPacSignature@@YAJPEAU_KDC_S4U_TICKET_INFO@@PEAU_KDC_U2U_TICKET_INFO@@PEAU_KDC_TICKET_INFO@@PEAEKK3@Z; KdcVerifyPacSignature(_KDC_S4U_TICKET_INFO *,_KDC_U2U_TICKET_INFO *,_KDC_TICKET_INFO *,uchar *,ulong,ulong,uchar *)
0x180048786  mov     edi, eax
0x180048788  test    eax, eax
0x18004878a  jz      short loc_1800487D2
0x18004878c  lea     r14, WPP_GLOBAL_Control
0x180048793  mov     rcx, cs:WPP_GLOBAL_Control
0x18004879a  cmp     rcx, r14
0x18004879d  jz      short loc_1800487BD
0x18004879f  mov     esi, 1
0x1800487a4  test    [rcx+1Ch], sil
0x1800487a8  jz      short loc_1800487BD
0x1800487aa  lea     edx, [rsi+77h]
0x1800487ad  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x1800487b4  mov     rcx, [rcx+10h]
0x1800487b8  call    WPP_SF_
0x1800487bd  mov     ecx, edi; int
0x1800487bf  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x1800487c4  mov     rcx, [rbp+190h+arg_28]
0x1800487cb  mov     [rcx], eax
0x1800487cd  jmp     loc_180048F3D
0x1800487d2  mov     r12, [rbx+18h]
0x1800487d6  mov     edx, [rbx+10h]; unsigned int
0x1800487d9  mov     rcx, r12; struct _PACTYPE *
0x1800487dc  call    ?PAC_UnMarshal@@YAKPEAU_PACTYPE@@K@Z; PAC_UnMarshal(_PACTYPE *,ulong)
0x1800487e1  test    eax, eax
0x1800487e3  jnz     short loc_180048846
0x1800487e5  lea     r14, WPP_GLOBAL_Control
0x1800487ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800487f3  cmp     rcx, r14
0x1800487f6  jz      short loc_180048814
0x1800487f8  lea     esi, [rax+1]
0x1800487fb  test    [rcx+1Ch], sil
0x1800487ff  jz      short loc_180048814
0x180048801  lea     edx, [rax+79h]
0x180048804  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x18004880b  mov     rcx, [rcx+10h]
0x18004880f  call    WPP_SF_
0x180048814  mov     rax, [rbp+190h+arg_28]
0x18004881b  mov     dword ptr [rax], 0C000000Dh
0x180048821  lea     rcx, [rbp+190h+var_D0]
0x180048828  call    wil__details__lambda_call__lambda_530ddfda5690aa4758d6a6bc63144caf______lambda_call__lambda_530ddfda5690aa4758d6a6bc63144caf___
0x18004882d  mov     eax, 3Ch ; '<'
0x180048832  add     rsp, 258h
0x180048839  pop     r15
0x18004883b  pop     r14
0x18004883d  pop     r13
0x18004883f  pop     r12
0x180048841  pop     rdi
0x180048842  pop     rsi
0x180048843  pop     rbx
0x180048844  pop     rbp
0x180048845  retn
0x180048846  mov     esi, 1
0x18004884b  mov     edx, esi; unsigned int
0x18004884d  mov     rcx, r12; struct _PACTYPE *
0x180048850  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x180048855  mov     [rsp+290h+var_230], rax
0x18004885a  test    rax, rax
0x18004885d  jz      short loc_180048814
0x18004885f  lea     r14, WPP_GLOBAL_Control
0x180048866  lea     r15, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x18004886d  lea     edi, [rsi+0Bh]
0x180048870  mov     r9, [rbp+190h+arg_30]
0x180048877  test    r9, r9
0x18004887a  jnz     short loc_180048889
0x18004887c  cmp     [rbp+190h+arg_38], r13
0x180048883  jz      loc_180048992
0x180048889  mov     edx, edi; unsigned int
0x18004888b  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x180048890  mov     r13, rax
0x180048893  test    rax, rax
0x180048896  jz      loc_180048992
0x18004889c  mov     r8d, [rax+4]
0x1800488a0  cmp     r8d, 14h
0x1800488a4  jnb     short loc_1800488E1
0x1800488a6  mov     r10, cs:WPP_GLOBAL_Control
0x1800488ad  cmp     r10, r14
0x1800488b0  jz      loc_180048999
0x1800488b6  test    [r10+1Ch], sil
0x1800488ba  jz      loc_180048999
0x1800488c0  mov     edx, 7Ah ; 'z'
0x1800488c5  mov     dword ptr [rsp+290h+var_270], 14h
0x1800488cd  mov     r9d, r8d
0x1800488d0  mov     r8, r15
0x1800488d3  mov     rcx, [r10+10h]
0x1800488d7  call    WPP_SF_Dd
0x1800488dc  jmp     loc_180048992
0x1800488e1  mov     rbx, [rax+8]
0x1800488e5  mov     r10d, 2
0x1800488eb  test    r9, r9
0x1800488ee  jz      short loc_18004893F
0x1800488f0  movzx   edx, word ptr [rbx+4]
0x1800488f4  movzx   ecx, word ptr [rbx+6]
0x1800488f8  add     ecx, edx
0x1800488fa  cmp     ecx, r8d
0x1800488fd  ja      short loc_18004893F
0x1800488ff  lea     rcx, [r10+rdx]; size
0x180048903  call    MIDL_user_allocate
0x180048908  mov     qword ptr [rbp+190h+var_1F0+8], rax
0x18004890c  test    rax, rax
0x18004890f  jz      loc_180048B68
0x180048915  movzx   ecx, word ptr [rbx+4]
0x180048919  mov     word ptr [rbp+190h+var_1F0], cx
0x18004891d  add     cx, 2
0x180048921  mov     word ptr [rbp+190h+var_1F0+2], cx
0x180048925  movzx   r8d, word ptr [rbx+4]; Size
0x18004892a  movzx   edx, word ptr [rbx+6]
0x18004892e  add     rdx, rbx; Src
0x180048931  mov     rcx, rax; void *
0x180048934  call    memcpy_0
0x180048939  mov     r10d, 2
0x18004893f  cmp     [rbp+190h+arg_38], 0
0x180048947  jz      short loc_180048992
0x180048949  movzx   ecx, word ptr [rbx+0Ch]
0x18004894d  movzx   eax, word ptr [rbx+0Eh]
0x180048951  add     eax, ecx
0x180048953  cmp     eax, [r13+4]
0x180048957  ja      short loc_180048992
0x180048959  add     rcx, r10; size
0x18004895c  call    MIDL_user_allocate
0x180048961  mov     qword ptr [rbp+190h+var_1E0+8], rax
0x180048965  test    rax, rax
0x180048968  jz      loc_180048B68
0x18004896e  movzx   ecx, word ptr [rbx+0Ch]
0x180048972  mov     word ptr [rbp+190h+var_1E0], cx
0x180048976  add     cx, 2
0x18004897a  mov     word ptr [rbp+190h+var_1E0+2], cx
0x18004897e  movzx   r8d, word ptr [rbx+0Ch]; Size
0x180048983  movzx   edx, word ptr [rbx+0Eh]
0x180048987  add     rdx, rbx; Src
0x18004898a  mov     rcx, rax; void *
0x18004898d  call    memcpy_0
0x180048992  mov     r10, cs:WPP_GLOBAL_Control
0x180048999  cmp     [rbp+190h+arg_40], 0
0x1800489a1  jz      short loc_180048A12
0x1800489a3  mov     edx, 12h; unsigned int
0x1800489a8  mov     rcx, r12; struct _PACTYPE *
0x1800489ab  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x1800489b0  mov     r13, rax
0x1800489b3  test    rax, rax
0x1800489b6  jz      short loc_180048A12
0x1800489b8  cmp     [rax+4], edi
0x1800489bb  jb      short loc_180048A12
0x1800489bd  mov     ebx, [rax+4]
0x1800489c0  mov     rcx, [rax+8]; Sid
0x1800489c4  call    cs:__imp_RtlLengthSid
0x1800489ca  cmp     ebx, eax
0x1800489cc  jb      short loc_180048A0B
0x1800489ce  mov     rcx, [r13+8]; Sid
0x1800489d2  call    cs:__imp_RtlLengthSid
0x1800489d8  mov     ecx, eax; size
0x1800489da  call    MIDL_user_allocate
0x1800489df  mov     rbx, [rbp+190h+arg_40]
0x1800489e6  mov     [rbx], rax
0x1800489e9  test    rax, rax
0x1800489ec  jz      loc_180048B68
0x1800489f2  mov     rcx, [r13+8]; Sid
0x1800489f6  call    cs:__imp_RtlLengthSid
0x1800489fc  mov     r8d, eax; Size
0x1800489ff  mov     rdx, [r13+8]; Src
0x180048a03  mov     rcx, [rbx]; void *
0x180048a06  call    memcpy_0
0x180048a0b  mov     r10, cs:WPP_GLOBAL_Control
0x180048a12  cmp     [rbp+190h+arg_10], 0
0x180048a19  jnz     loc_180048BA0
0x180048a1f  mov     edx, 0Ah; unsigned int
0x180048a24  mov     rcx, r12; struct _PACTYPE *
0x180048a27  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x180048a2c  test    rax, rax
0x180048a2f  jz      loc_180048B7A
0x180048a35  mov     qword ptr [rbp+190h+Time], 0
0x180048a3d  xorps   xmm0, xmm0
0x180048a40  movups  xmmword ptr [rbp+190h+String2.Length], xmm0
0x180048a44  cmp     [rax+4], edi
0x180048a47  jnb     short loc_180048A6F
0x180048a49  cmp     r10, r14
0x180048a4c  jz      short loc_180048A83
0x180048a4e  test    [r10+1Ch], sil
0x180048a52  jz      short loc_180048A83
0x180048a54  mov     edx, 7Bh ; '{'
0x180048a59  mov     dword ptr [rsp+290h+var_270], edi
0x180048a5d  mov     r9d, [rax+4]
0x180048a61  mov     r8, r15
0x180048a64  mov     rcx, [r10+10h]
0x180048a68  call    WPP_SF_Dd
0x180048a6d  jmp     short loc_180048A83
0x180048a6f  mov     rbx, [rax+8]
0x180048a73  movzx   ecx, word ptr [rbx+8]
0x180048a77  add     rcx, 6
0x180048a7b  mov     eax, [rax+4]
0x180048a7e  cmp     rcx, rax
0x180048a81  jbe     short loc_180048A95
0x180048a83  mov     rax, [rbp+190h+arg_28]
0x180048a8a  mov     dword ptr [rax], 0C000000Dh
0x180048a90  jmp     loc_180048F38
0x180048a95  mov     r13, [rbp+190h+arg_0]
0x180048a9c  lea     rdx, [r13+60h]
  ... truncated ...
```
