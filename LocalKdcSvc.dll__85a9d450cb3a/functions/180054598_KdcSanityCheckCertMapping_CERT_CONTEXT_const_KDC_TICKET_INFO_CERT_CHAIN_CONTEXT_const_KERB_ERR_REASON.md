# KdcSanityCheckCertMapping(_CERT_CONTEXT const &,_KDC_TICKET_INFO &,_CERT_CHAIN_CONTEXT const *,KERB_ERR_REASON &)

- ea: `0x180054598`
- end: `0x180054905`
- name: `?KdcSanityCheckCertMapping@@YAJAEBU_CERT_CONTEXT@@AEAU_KDC_TICKET_INFO@@PEBU_CERT_CHAIN_CONTEXT@@AEAUKERB_ERR_REASON@@@Z`
- size: `877`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, struct _KDC_TICKET_INFO *, const struct _CERT_CHAIN_CONTEXT *, struct KERB_ERR_REASON *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016148`
- `0x180029844`

## callees

- `0x180003908`
- `0x1800101c4`
- `0x1800101ec`
- `0x18002005c`
- `0x18003a570`
- `0x180040420`
- `0x18004dd60`
- `0x18004e0b4`
- `0x18004e314`
- `0x18004f2bc`
- `0x180054598`
- `0x1800632e8`
- `0x1800761d4`

## import_xrefs

- `ntdll!RtlValidSid` at `0x1800546c4`
- `ntdll!RtlValidSid` at `0x1800546c4`

## pseudocode

```c
__int64 __fastcall KdcSanityCheckCertMapping(
        PCCERT_CONTEXT pCertContext,
        struct _KDC_TICKET_INFO *a2,
        const struct _CERT_CHAIN_CONTEXT *a3,
        struct KERB_ERR_REASON *a4)
{
  struct _KDC_TICKET_INFO *v6; // rdi
  __int64 v8; // r9
  __int64 result; // rax
  CSecurityData *v10; // r10
  LONGLONG v11; // rax
  LONGLONG v12; // r9
  struct _CERT_CHAIN_CONTEXT Sid; // [rsp+30h] [rbp-79h] BYREF
  _BYTE v14[128]; // [rsp+80h] [rbp-29h] BYREF
  union _LARGE_INTEGER NotBefore; // [rsp+118h] [rbp+6Fh] BYREF

  v6 = a2;
  if ( (*((_DWORD *)a2 + 28) & 0x800) != 0 )
  {
    if ( !*(_DWORD *)a4 )
      *(_QWORD *)a4 = 4;
    return 0;
  }
  if ( *((char *)a2 + 112) >= 0 || (*((_DWORD *)a2 + 28) & 0x200) != 0 )
  {
    LOBYTE(a2) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_StrongNameMatchPolicy>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_StrongNameMatchPolicy>::GetImpl'::`2'::impl,
      a2);
    if ( KdcUseStrongNameMatches
      && (*((_DWORD *)v6 + 11) & 0x180) == 0
      && (int)KdcCheckCertMappingViaPolicy(pCertContext, v6, a3) >= 0 )
    {
      *((_DWORD *)v6 + 28) |= 0x800u;
      *(_QWORD *)a4 = 6;
      return 0;
    }
    if ( KdcGlobalUseSubjectAltName
      || *((_QWORD *)v6 + 19) == *((_QWORD *)v6 + 20)
      || (*((_DWORD *)v6 + 11) & 0x180) != 0 )
    {
      Sid = *(struct _CERT_CHAIN_CONTEXT *)KerbGetExtendedSanFromCert((__int64)v14, (__int64)pCertContext);
      v8 = (unsigned int)_mm_cvtsi128_si32(*(__m128i *)&Sid.cbSize);
      if ( (int)v8 < 0 )
      {
        if ( (_DWORD)v8 != -1073741275 )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 176, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids, v8);
          }
          *(_DWORD *)a4 = 11;
          result = 60;
          goto LABEL_23;
        }
      }
      else if ( RtlValidSid(&Sid.TrustStatus) )
      {
        NotBefore.LowPart = 0;
        if ( KdcIsOurDomain(&Sid.TrustStatus, (unsigned int *)&NotBefore) )
        {
          if ( *((_DWORD *)v6 + 12) != NotBefore.LowPart )
          {
            if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids);
            }
            KdcAuditCertificateSidMismatch(pCertContext, &Sid.TrustStatus, v6, a3);
            *(_DWORD *)a4 = 10;
            goto LABEL_22;
          }
        }
        else if ( (*((_BYTE *)v6 + 44) & 0x40) == 0 )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids);
          }
          KdcAuditCertificateSidMismatch(pCertContext, &Sid.TrustStatus, v6, a3);
          *(_DWORD *)a4 = 9;
LABEL_22:
          result = 66;
LABEL_23:
          *((_DWORD *)a4 + 1) = result;
          return result;
        }
        *((_DWORD *)v6 + 28) |= 0x800u;
        *(_QWORD *)a4 = 7;
        return 0;
      }
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        177,
        (unsigned int)WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids,
        (_DWORD)v6,
        KdcGlobalEnforceStrongCertificateMapping);
      v10 = WPP_GLOBAL_Control;
    }
    if ( KdcGlobalEnforceStrongCertificateMapping == 2 )
    {
      KdcAuditWeakCertificateBinding(pCertContext, v6, a3);
      *(_DWORD *)a4 = 12;
    }
    else
    {
      NotBefore = (union _LARGE_INTEGER)pCertContext->pCertInfo->NotBefore;
      v11 = *((_QWORD *)v6 + 18);
      v12 = NotBefore.QuadPart + 10000000LL * KdcGlobalCertBackdatingCompensationSeconds;
      if ( v12 >= v11 )
      {
        KdcAuditWeakCertificateBinding(pCertContext, v6, a3);
        *(_QWORD *)a4 = 14;
        return 0;
      }
      if ( v10 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
        WPP_SF_ii(*((_QWORD *)v10 + 2), 178, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids, v12, v11);
      KdcAuditWeakCertificateThatPredatesUser(
        pCertContext,
        v6,
        (union _LARGE_INTEGER)pCertContext->pCertInfo->NotBefore,
        a3);
      *(_DWORD *)a4 = 13;
    }
    goto LABEL_22;
  }
  memset_0(&Sid, 0, sizeof(Sid));
  KdcAuditWeakCertificateBinding(pCertContext, v6, &Sid);
  *(_QWORD *)a4 = 5;
  return 0;
}

```

## disassembly

```asm
0x180054598  push    rbp
0x18005459a  push    rbx
0x18005459b  push    rdi
0x18005459c  push    r12
0x18005459e  push    r14
0x1800545a0  push    r15
0x1800545a2  lea     rbp, [rsp-2Fh]
0x1800545a7  sub     rsp, 0D8h
0x1800545ae  mov     r14d, 800h
0x1800545b4  mov     rbx, r9
0x1800545b7  mov     r12, r8
0x1800545ba  mov     rdi, rdx
0x1800545bd  mov     r15, rcx
0x1800545c0  test    [rdx+70h], r14d
0x1800545c4  jz      short loc_1800545DC
0x1800545c6  cmp     dword ptr [r9], 0
0x1800545ca  jnz     loc_1800548F2
0x1800545d0  mov     qword ptr [r9], 4
0x1800545d7  jmp     loc_1800548F2
0x1800545dc  test    byte ptr [rdx+70h], 80h
0x1800545e0  jz      short loc_180054615
0x1800545e2  test    dword ptr [rdx+70h], 200h
0x1800545e9  jnz     short loc_180054615
0x1800545eb  xor     edx, edx; Val
0x1800545ed  lea     rcx, [rbp+57h+Sid]; void *
0x1800545f1  lea     r8d, [rdx+48h]; Size
0x1800545f5  call    memset_0
0x1800545fa  lea     r8, [rbp+57h+Sid]; struct _CERT_CHAIN_CONTEXT *
0x1800545fe  mov     rdx, rdi; struct _KDC_TICKET_INFO *
0x180054601  mov     rcx, r15; pCertContext
0x180054604  call    ?KdcAuditWeakCertificateBinding@@YAXAEBU_CERT_CONTEXT@@AEBU_KDC_TICKET_INFO@@AEBU_CERT_CHAIN_CONTEXT@@@Z; KdcAuditWeakCertificateBinding(_CERT_CONTEXT const &,_KDC_TICKET_INFO const &,_CERT_CHAIN_CONTEXT const &)
0x180054609  mov     qword ptr [rbx], 5
0x180054610  jmp     loc_1800548F2
0x180054615  mov     dl, 1
0x180054617  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_StrongNameMatchPolicy@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_StrongNameMatchPolicy@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StrongNameMatchPolicy> `wil::Feature<__WilFeatureTraits_Feature_StrongNameMatchPolicy>::GetImpl(void)'::`2'::impl
0x18005461e  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_StrongNameMatchPolicy@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StrongNameMatchPolicy>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180054623  cmp     cs:?KdcUseStrongNameMatches@@3KA, 0; ulong KdcUseStrongNameMatches
0x18005462a  jz      short loc_180054657
0x18005462c  test    dword ptr [rdi+2Ch], 180h
0x180054633  jnz     short loc_180054657
0x180054635  mov     r8, r12; struct _CERT_CHAIN_CONTEXT *
0x180054638  mov     rdx, rdi; struct _KDC_TICKET_INFO *
0x18005463b  mov     rcx, r15; struct _CERT_CONTEXT *
0x18005463e  call    ?KdcCheckCertMappingViaPolicy@@YAJAEBU_CERT_CONTEXT@@AEAU_KDC_TICKET_INFO@@PEBU_CERT_CHAIN_CONTEXT@@@Z; KdcCheckCertMappingViaPolicy(_CERT_CONTEXT const &,_KDC_TICKET_INFO &,_CERT_CHAIN_CONTEXT const *)
0x180054643  test    eax, eax
0x180054645  js      short loc_180054657
0x180054647  or      [rdi+70h], r14d
0x18005464b  mov     qword ptr [rbx], 6
0x180054652  jmp     loc_1800548F2
0x180054657  cmp     cs:?KdcGlobalUseSubjectAltName@@3KA, 0; ulong KdcGlobalUseSubjectAltName
0x18005465e  jnz     short loc_18005467D
0x180054660  mov     rax, [rdi+0A0h]
0x180054667  cmp     [rdi+98h], rax
0x18005466e  jz      short loc_18005467D
0x180054670  test    dword ptr [rdi+2Ch], 180h
0x180054677  jz      loc_1800547EE
0x18005467d  mov     rdx, r15
0x180054680  lea     rcx, [rbp+57h+var_80]
0x180054684  call    ?KerbGetExtendedSanFromCert@@YA?AUKerbExtendedSanLookupResult@@PEBU_CERT_CONTEXT@@@Z; KerbGetExtendedSanFromCert(_CERT_CONTEXT const *)
0x180054689  movups  xmm2, xmmword ptr [rax]
0x18005468c  movaps  [rbp+57h+Sid], xmm2
0x180054690  movups  xmm0, xmmword ptr [rax+10h]
0x180054694  movd    r9d, xmm2
0x180054699  movaps  [rbp+57h+var_C0], xmm0
0x18005469d  movups  xmm1, xmmword ptr [rax+20h]
0x1800546a1  movaps  [rbp+57h+var_B0], xmm1
0x1800546a5  movups  xmm0, xmmword ptr [rax+30h]
0x1800546a9  movaps  [rbp+57h+var_A0], xmm0
0x1800546ad  movsd   xmm1, qword ptr [rax+40h]
0x1800546b2  movsd   [rbp+57h+var_90], xmm1
0x1800546b7  test    r9d, r9d
0x1800546ba  js      loc_1800547A7
0x1800546c0  lea     rcx, [rbp+57h+Sid+4]; Sid
0x1800546c4  call    cs:__imp_RtlValidSid
0x1800546ca  test    al, al
0x1800546cc  jz      loc_1800547EE
0x1800546d2  lea     rdx, [rbp+57h+arg_8]; unsigned int *
0x1800546d6  mov     dword ptr [rbp+57h+arg_8], 0
0x1800546dd  lea     rcx, [rbp+57h+Sid+4]; void *
0x1800546e1  call    ?KdcIsOurDomain@@YAEPEAXPEAK@Z; KdcIsOurDomain(void *,ulong *)
0x1800546e6  test    al, al
0x1800546e8  jnz     short loc_180054747
0x1800546ea  test    byte ptr [rdi+2Ch], 40h
0x1800546ee  jnz     loc_180054797
0x1800546f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800546fb  lea     r14, WPP_GLOBAL_Control
0x180054702  cmp     rcx, r14
0x180054705  jz      short loc_180054722
0x180054707  test    byte ptr [rcx+1Ch], 1
0x18005470b  jz      short loc_180054722
0x18005470d  mov     rcx, [rcx+10h]
0x180054711  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x180054718  mov     edx, 0AEh
0x18005471d  call    WPP_SF_
0x180054722  mov     r9, r12; struct _CERT_CHAIN_CONTEXT *
0x180054725  lea     rdx, [rbp+57h+Sid+4]; Sid
0x180054729  mov     r8, rdi; struct _KDC_TICKET_INFO *
0x18005472c  mov     rcx, r15; pCertContext
0x18005472f  call    ?KdcAuditCertificateSidMismatch@@YAXAEBU_CERT_CONTEXT@@AEBU_SID@@AEBU_KDC_TICKET_INFO@@AEBU_CERT_CHAIN_CONTEXT@@@Z; KdcAuditCertificateSidMismatch(_CERT_CONTEXT const &,_SID const &,_KDC_TICKET_INFO const &,_CERT_CHAIN_CONTEXT const &)
0x180054734  mov     dword ptr [rbx], 9
0x18005473a  mov     eax, 42h ; 'B'
0x18005473f  mov     [rbx+4], eax
0x180054742  jmp     loc_1800548F4
0x180054747  mov     eax, dword ptr [rbp+57h+arg_8]
0x18005474a  cmp     [rdi+30h], eax
0x18005474d  jz      short loc_180054797
0x18005474f  mov     rcx, cs:WPP_GLOBAL_Control
0x180054756  lea     r14, WPP_GLOBAL_Control
0x18005475d  cmp     rcx, r14
0x180054760  jz      short loc_18005477D
0x180054762  test    byte ptr [rcx+1Ch], 1
0x180054766  jz      short loc_18005477D
0x180054768  mov     rcx, [rcx+10h]
0x18005476c  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x180054773  mov     edx, 0AFh
0x180054778  call    WPP_SF_
0x18005477d  mov     r9, r12; struct _CERT_CHAIN_CONTEXT *
0x180054780  lea     rdx, [rbp+57h+Sid+4]; Sid
0x180054784  mov     r8, rdi; struct _KDC_TICKET_INFO *
0x180054787  mov     rcx, r15; pCertContext
0x18005478a  call    ?KdcAuditCertificateSidMismatch@@YAXAEBU_CERT_CONTEXT@@AEBU_SID@@AEBU_KDC_TICKET_INFO@@AEBU_CERT_CHAIN_CONTEXT@@@Z; KdcAuditCertificateSidMismatch(_CERT_CONTEXT const &,_SID const &,_KDC_TICKET_INFO const &,_CERT_CHAIN_CONTEXT const &)
0x18005478f  mov     dword ptr [rbx], 0Ah
0x180054795  jmp     short loc_18005473A
0x180054797  or      [rdi+70h], r14d
0x18005479b  mov     qword ptr [rbx], 7
0x1800547a2  jmp     loc_1800548F2
0x1800547a7  cmp     r9d, 0C0000225h
0x1800547ae  jz      short loc_1800547EE
0x1800547b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800547b7  lea     r14, WPP_GLOBAL_Control
0x1800547be  cmp     rcx, r14
0x1800547c1  jz      short loc_1800547DE
0x1800547c3  test    byte ptr [rcx+1Ch], 1
0x1800547c7  jz      short loc_1800547DE
0x1800547c9  mov     rcx, [rcx+10h]
0x1800547cd  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x1800547d4  mov     edx, 0B0h
0x1800547d9  call    WPP_SF_d
0x1800547de  mov     dword ptr [rbx], 0Bh
0x1800547e4  mov     eax, 3Ch ; '<'
0x1800547e9  jmp     loc_18005473F
0x1800547ee  mov     r10, cs:WPP_GLOBAL_Control
0x1800547f5  lea     r14, WPP_GLOBAL_Control
0x1800547fc  cmp     r10, r14
0x1800547ff  jz      short loc_180054831
0x180054801  test    byte ptr [r10+1Ch], 2
0x180054806  jz      short loc_180054831
0x180054808  mov     eax, cs:?KdcGlobalEnforceStrongCertificateMapping@@3W4KerbStrongCertificateMappingEnforcement@@A; KerbStrongCertificateMappingEnforcement KdcGlobalEnforceStrongCertificateMapping
0x18005480e  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x180054815  mov     rcx, [r10+10h]
0x180054819  mov     edx, 0B1h
0x18005481e  mov     r9, rdi
0x180054821  mov     dword ptr [rsp+100h+var_E0], eax
0x180054825  call    WPP_SF_Zd
0x18005482a  mov     r10, cs:WPP_GLOBAL_Control
0x180054831  cmp     cs:?KdcGlobalEnforceStrongCertificateMapping@@3W4KerbStrongCertificateMappingEnforcement@@A, 2; KerbStrongCertificateMappingEnforcement KdcGlobalEnforceStrongCertificateMapping
0x180054838  jnz     short loc_180054853
0x18005483a  mov     r8, r12; struct _CERT_CHAIN_CONTEXT *
0x18005483d  mov     rdx, rdi; struct _KDC_TICKET_INFO *
0x180054840  mov     rcx, r15; pCertContext
0x180054843  call    ?KdcAuditWeakCertificateBinding@@YAXAEBU_CERT_CONTEXT@@AEBU_KDC_TICKET_INFO@@AEBU_CERT_CHAIN_CONTEXT@@@Z; KdcAuditWeakCertificateBinding(_CERT_CONTEXT const &,_KDC_TICKET_INFO const &,_CERT_CHAIN_CONTEXT const &)
0x180054848  mov     dword ptr [rbx], 0Ch
0x18005484e  jmp     loc_18005473A
0x180054853  mov     rax, [r15+18h]
0x180054857  mov     rax, [rax+40h]
0x18005485b  mov     rcx, rax
0x18005485e  mov     dword ptr [rbp+57h+arg_8], eax
0x180054861  mov     eax, cs:?KdcGlobalCertBackdatingCompensationSeconds@@3KA; ulong KdcGlobalCertBackdatingCompensationSeconds
0x180054867  imul    r9, rax, 989680h
0x18005486e  mov     rax, [rdi+90h]
0x180054875  shr     rcx, 20h
0x180054879  mov     dword ptr [rbp+57h+arg_8+4], ecx
0x18005487c  add     r9, qword ptr [rbp+57h+arg_8]
0x180054880  cmp     r9, rax
0x180054883  jge     short loc_1800548DD
0x180054885  cmp     r10, r14
0x180054888  jz      short loc_1800548AB
0x18005488a  test    byte ptr [r10+1Ch], 1
0x18005488f  jz      short loc_1800548AB
0x180054891  mov     rcx, [r10+10h]
0x180054895  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x18005489c  mov     edx, 0B2h
0x1800548a1  mov     [rsp+100h+var_E0], rax
0x1800548a6  call    WPP_SF_ii
0x1800548ab  mov     rax, [r15+18h]
0x1800548af  mov     r9, r12; struct _CERT_CHAIN_CONTEXT *
0x1800548b2  mov     rdx, rdi; struct _KDC_TICKET_INFO *
0x1800548b5  mov     rax, [rax+40h]
0x1800548b9  mov     rcx, rax
0x1800548bc  mov     dword ptr [rbp+57h+arg_8], eax
0x1800548bf  shr     rcx, 20h
0x1800548c3  mov     dword ptr [rbp+57h+arg_8+4], ecx
0x1800548c6  mov     rcx, r15; pCertContext
0x1800548c9  mov     r8, qword ptr [rbp+57h+arg_8]; union _LARGE_INTEGER
0x1800548cd  call    ?KdcAuditWeakCertificateThatPredatesUser@@YAXAEBU_CERT_CONTEXT@@AEBU_KDC_TICKET_INFO@@T_LARGE_INTEGER@@AEBU_CERT_CHAIN_CONTEXT@@@Z; KdcAuditWeakCertificateThatPredatesUser(_CERT_CONTEXT const &,_KDC_TICKET_INFO const &,_LARGE_INTEGER,_CERT_CHAIN_CONTEXT const &)
0x1800548d2  mov     dword ptr [rbx], 0Dh
0x1800548d8  jmp     loc_18005473A
0x1800548dd  mov     r8, r12; struct _CERT_CHAIN_CONTEXT *
0x1800548e0  mov     rdx, rdi; struct _KDC_TICKET_INFO *
0x1800548e3  mov     rcx, r15; pCertContext
0x1800548e6  call    ?KdcAuditWeakCertificateBinding@@YAXAEBU_CERT_CONTEXT@@AEBU_KDC_TICKET_INFO@@AEBU_CERT_CHAIN_CONTEXT@@@Z; KdcAuditWeakCertificateBinding(_CERT_CONTEXT const &,_KDC_TICKET_INFO const &,_CERT_CHAIN_CONTEXT const &)
0x1800548eb  mov     qword ptr [rbx], 0Eh
0x1800548f2  xor     eax, eax
0x1800548f4  add     rsp, 0D8h
0x1800548fb  pop     r15
0x1800548fd  pop     r14
0x1800548ff  pop     r12
0x180054901  pop     rdi
0x180054902  pop     rbx
0x180054903  pop     rbp
0x180054904  retn
```
