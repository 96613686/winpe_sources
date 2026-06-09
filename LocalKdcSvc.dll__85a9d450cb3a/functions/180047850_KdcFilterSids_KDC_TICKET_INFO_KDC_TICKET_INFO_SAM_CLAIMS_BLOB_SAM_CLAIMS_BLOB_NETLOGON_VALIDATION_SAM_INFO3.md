# KdcFilterSids(_KDC_TICKET_INFO *,_KDC_TICKET_INFO *,_SAM_CLAIMS_BLOB *,_SAM_CLAIMS_BLOB *,_NETLOGON_VALIDATION_SAM_INFO3 *)

- ea: `0x180047850`
- end: `0x180047d22`
- name: `?KdcFilterSids@@YAJPEAU_KDC_TICKET_INFO@@0PEAU_SAM_CLAIMS_BLOB@@1PEAU_NETLOGON_VALIDATION_SAM_INFO3@@@Z`
- size: `1234`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _KDC_TICKET_INFO *, struct _SAM_CLAIMS_BLOB *, struct _SAM_CLAIMS_BLOB *, struct _NETLOGON_VALIDATION_SAM_INFO3 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180046fe8`
- `0x1800485e4`

## callees

- `0x18000d42c`
- `0x1800101ec`
- `0x18001e888`
- `0x18001ff94`
- `0x180047850`

## import_xrefs

- `SAMSRV!SamIFreeClaimsBlob` at `0x180047b84`
- `SAMSRV!SamIFreeClaimsBlob` at `0x180047c25`
- `SAMSRV!SamIFreeClaimsBlob` at `0x180047b84`
- `SAMSRV!SamIFreeClaimsBlob` at `0x180047c25`
- `LSASRV!LsaIAuditKdcEvent` at `0x180047a7f`
- `LSASRV!LsaIAuditKdcEvent` at `0x180047a7f`
- `LSASRV!LsaITransformAuthorizationData` at `0x180047991`
- `LSASRV!LsaITransformAuthorizationData` at `0x180047cac`
- `LSASRV!LsaITransformAuthorizationData` at `0x180047991`
- `LSASRV!LsaITransformAuthorizationData` at `0x180047cac`

## pseudocode

```c
__int64 __fastcall KdcFilterSids(
        struct _UNICODE_STRING *a1,
        struct _KDC_TICKET_INFO *a2,
        struct _SAM_CLAIMS_BLOB *a3,
        struct _SAM_CLAIMS_BLOB *a4,
        struct _NETLOGON_VALIDATION_SAM_INFO3 *a5)
{
  struct _UNICODE_STRING *v7; // r14
  CSecurityData *v8; // rcx
  PWSTR Buffer; // rdx
  struct _NETLOGON_VALIDATION_SAM_INFO3 *v10; // rsi
  char *v11; // rcx
  int v12; // eax
  unsigned int v13; // ebx
  bool v14; // zf
  char *v16; // rbx
  __int64 v17; // r8
  int v18; // eax
  int v19; // [rsp+E0h] [rbp-80h] BYREF
  __int128 v20; // [rsp+E8h] [rbp-78h] BYREF
  __int128 *v21; // [rsp+F8h] [rbp-68h]
  struct _SAM_CLAIMS_BLOB **v22; // [rsp+100h] [rbp-60h]
  struct _SAM_CLAIMS_BLOB **v23; // [rsp+108h] [rbp-58h]
  char v24; // [rsp+110h] [rbp-50h]
  int v25; // [rsp+160h] [rbp+0h] BYREF
  struct _SAM_CLAIMS_BLOB *v26; // [rsp+170h] [rbp+10h] BYREF
  struct _SAM_CLAIMS_BLOB *v27; // [rsp+178h] [rbp+18h] BYREF

  v27 = a4;
  v26 = a3;
  v25 = 0;
  v7 = 0;
  v20 = 0;
  v21 = &v20;
  v22 = &v26;
  v23 = &v27;
  v24 = 1;
  if ( ((__int64)a1[3].Buffer & 8) == 0 )
    goto LABEL_5;
  v7 = a1 + 1;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_3875113a630833a3e73becf979560e87_Traceguids, v7);
    a4 = v27;
LABEL_5:
    v8 = WPP_GLOBAL_Control;
  }
  Buffer = a1[5].Buffer;
  v10 = a5;
  if ( Buffer || *(_DWORD *)(&a1[3].MaximumLength + 1) == 3 || ((__int64)a1[3].Buffer & 0x10) != 0 )
  {
    v11 = (char *)a5 + 296;
    LOBYTE(v11) = 1;
    v12 = LsaITransformAuthorizationData(
            v11,
            v7,
            a1,
            2,
            *(_DWORD *)(&a1[3].MaximumLength + 1),
            a1[3].Buffer,
            Buffer,
            3,
            a5,
            *((_QWORD *)a5 + 36),
            (char *)a5 + 296,
            *((_QWORD *)a5 + 38),
            v26,
            (unsigned __int64)&v20 & -(__int64)(a4 != 0));
    v25 = v12;
    if ( v12 < 0 )
    {
      if ( v12 == -1073741413 )
      {
        if ( (qword_1800B2E50 & 0x800000000LL) != 0 )
        {
          v19 = 0;
          LsaIAuditKdcEvent(
            673,
            (char *)v10 + 48,
            (char *)v10 + 208,
            0,
            a1,
            0,
            &v19,
            &v25,
            0,
            0,
            &GlobalLocalhostAddress,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtendedAuditingForKerberos>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExtendedAuditingForKerberos>::GetImpl'::`2'::impl) )
          LogGetTgsExtendedAudit(
            (struct _UNICODE_STRING *)v10 + 3,
            (struct _UNICODE_STRING *)v10 + 13,
            a1,
            0,
            0,
            &v25,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0);
      }
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          58,
          WPP_3875113a630833a3e73becf979560e87_Traceguids,
          (unsigned int)v25);
      v13 = v25;
      if ( !*((_QWORD *)&v20 + 1) || v26 && *((_QWORD *)v26 + 1) == *((_QWORD *)&v20 + 1) )
        return v13;
      if ( !v27 )
        goto LABEL_27;
      v14 = *((_QWORD *)v27 + 1) == *((_QWORD *)&v20 + 1);
      goto LABEL_26;
    }
    a4 = v27;
    v8 = WPP_GLOBAL_Control;
  }
  else if ( a4 && v26 )
  {
    v20 = *(_OWORD *)v26;
  }
  if ( a2 )
  {
    if ( (*((_BYTE *)a2 + 56) & 8) != 0 )
    {
      v16 = (char *)a2 + 16;
      if ( v8 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
      {
        WPP_SF_Z(*((_QWORD *)v8 + 2), 59, WPP_3875113a630833a3e73becf979560e87_Traceguids, (char *)a2 + 16);
        a4 = v27;
      }
    }
    else
    {
      v16 = 0;
    }
    v17 = *((_QWORD *)a2 + 11);
    if ( v17 || *((_DWORD *)a2 + 13) == 3 || (*((_BYTE *)a2 + 56) & 0x10) != 0 )
    {
      v18 = LsaITransformAuthorizationData(
              0,
              v16,
              a2,
              1,
              *((_DWORD *)a2 + 13),
              *((_DWORD *)a2 + 14),
              v17,
              3,
              v10,
              *((_QWORD *)v10 + 36),
              (char *)v10 + 296,
              *((_QWORD *)v10 + 38),
              (unsigned __int64)&v20 & ((unsigned __int128)-(__int128)*((unsigned __int64 *)&v20 + 1) >> 64),
              a4);
      v13 = v18;
      v25 = v18;
      if ( v18 >= 0 )
        goto LABEL_41;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          WPP_3875113a630833a3e73becf979560e87_Traceguids,
          (unsigned int)v18);
        v13 = v25;
      }
      if ( !*((_QWORD *)&v20 + 1) || v26 && *((_QWORD *)v26 + 1) == *((_QWORD *)&v20 + 1) )
        return v13;
      if ( !v27 )
        goto LABEL_27;
      v14 = *((_QWORD *)v27 + 1) == *((_QWORD *)&v20 + 1);
LABEL_26:
      if ( !v14 )
LABEL_27:
        SamIFreeClaimsBlob(&v20);
      return v13;
    }
  }
  if ( !a4 )
    goto LABEL_42;
  *(_OWORD *)a4 = v20;
LABEL_41:
  a4 = v27;
LABEL_42:
  if ( *((_QWORD *)&v20 + 1)
    && (!v26 || *((_QWORD *)v26 + 1) != *((_QWORD *)&v20 + 1))
    && (!a4 || *((_QWORD *)a4 + 1) != *((_QWORD *)&v20 + 1)) )
  {
    SamIFreeClaimsBlob(&v20);
  }
  return 0;
}

```

## disassembly

```asm
0x180047850  mov     [rsp-8+arg_18], r9
0x180047855  mov     [rsp-8+arg_10], r8
0x18004785a  push    rbp
0x18004785b  push    rbx
0x18004785c  push    rsi
0x18004785d  push    rdi
0x18004785e  push    r12
0x180047860  push    r14
0x180047862  push    r15
0x180047864  lea     rbp, [rsp+40h]
0x180047869  sub     rsp, 120h
0x180047870  mov     rdi, rdx
0x180047873  mov     rbx, rcx
0x180047876  xor     r15d, r15d
0x180047879  mov     [rbp-10h+arg_0], r15d
0x18004787d  mov     r14d, r15d
0x180047880  xorps   xmm0, xmm0
0x180047883  movups  [rbp-10h+var_68], xmm0
0x180047887  lea     rax, [rbp-10h+var_68]
0x18004788b  mov     [rbp-10h+var_58], rax
0x18004788f  lea     rax, [rbp-10h+arg_10]
0x180047893  mov     [rbp-10h+var_50], rax
0x180047897  lea     rax, [rbp-10h+arg_18]
0x18004789b  mov     [rbp-10h+var_48], rax
0x18004789f  mov     [rbp-10h+var_40], 1
0x1800478a3  lea     r12, WPP_GLOBAL_Control
0x1800478aa  test    byte ptr [rcx+38h], 8
0x1800478ae  jz      short loc_1800478E1
0x1800478b0  lea     r14, [rcx+10h]
0x1800478b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800478bb  cmp     rcx, r12
0x1800478be  jz      short loc_1800478E8
0x1800478c0  test    byte ptr [rcx+1Ch], 4
0x1800478c4  jz      short loc_1800478E8
0x1800478c6  lea     edx, [r15+39h]
0x1800478ca  mov     r9, r14
0x1800478cd  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x1800478d4  mov     rcx, [rcx+10h]
0x1800478d8  call    WPP_SF_Z
0x1800478dd  mov     r9, [rbp-10h+arg_18]
0x1800478e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800478e8  mov     rdx, [rbx+58h]
0x1800478ec  mov     rsi, [rbp-10h+arg_20]
0x1800478f0  test    rdx, rdx
0x1800478f3  jnz     short loc_180047924
0x1800478f5  cmp     dword ptr [rbx+34h], 3
0x1800478f9  jz      short loc_180047924
0x1800478fb  test    byte ptr [rbx+38h], 10h
0x1800478ff  jnz     short loc_180047924
0x180047901  test    r9, r9
0x180047904  jz      loc_180047B9C
0x18004790a  mov     rax, [rbp-10h+arg_10]
0x18004790e  test    rax, rax
0x180047911  jz      loc_180047B9C
0x180047917  movups  xmm0, xmmword ptr [rax]
0x18004791a  movdqu  [rbp-10h+var_68], xmm0
0x18004791f  jmp     loc_180047B9C
0x180047924  neg     r9
0x180047927  sbb     rax, rax
0x18004792a  lea     rcx, [rbp-10h+var_68]
0x18004792e  and     rax, rcx
0x180047931  lea     rcx, [rsi+128h]
0x180047938  mov     [rsp+150h+var_E8], rax
0x18004793d  mov     rax, [rbp-10h+arg_10]
0x180047941  mov     [rsp+150h+var_F0], rax
0x180047946  mov     rax, [rsi+130h]
0x18004794d  mov     [rsp+150h+var_F8], rax
0x180047952  mov     [rsp+150h+var_100], rcx
0x180047957  mov     rax, [rsi+120h]
0x18004795e  mov     [rsp+150h+var_108], rax
0x180047963  mov     [rsp+150h+var_110], rsi
0x180047968  mov     dword ptr [rsp+150h+var_118], 3
0x180047970  mov     [rsp+150h+var_120], rdx
0x180047975  mov     eax, [rbx+38h]
0x180047978  mov     dword ptr [rsp+150h+var_128], eax
0x18004797c  mov     eax, [rbx+34h]
0x18004797f  mov     dword ptr [rsp+150h+var_130], eax
0x180047983  mov     r9d, 2
0x180047989  mov     r8, rbx
0x18004798c  mov     rdx, r14
0x18004798f  mov     cl, 1
0x180047991  call    cs:__imp_LsaITransformAuthorizationData
0x180047997  mov     [rbp-10h+arg_0], eax
0x18004799a  test    eax, eax
0x18004799c  jns     loc_180047B91
0x1800479a2  cmp     eax, 0C000019Bh
0x1800479a7  jnz     loc_180047B2B
0x1800479ad  lea     rdi, [rsi+0D0h]
0x1800479b4  test    byte ptr cs:qword_1800B2E50+4, 8
0x1800479bb  jz      loc_180047A85
0x1800479c1  mov     [rbp-10h+var_70], r15d
0x1800479c5  mov     [rsp+150h+var_78], r15
0x1800479cd  mov     [rsp+150h+var_80], r15
0x1800479d5  mov     [rsp+150h+var_88], r15
0x1800479dd  mov     [rsp+150h+var_90], r15
0x1800479e5  mov     [rsp+150h+var_98], r15
0x1800479ed  mov     [rsp+150h+var_A0], r15
0x1800479f5  mov     [rsp+150h+var_A8], r15
0x1800479fd  mov     [rsp+150h+var_B0], r15
0x180047a05  mov     [rsp+150h+var_B8], r15
0x180047a0d  mov     [rsp+150h+var_C0], r15
0x180047a15  mov     [rsp+150h+var_C8], r15
0x180047a1d  mov     [rsp+150h+var_D0], r15
0x180047a25  mov     [rsp+150h+var_D8], r15
0x180047a2a  mov     [rsp+150h+var_E0], r15
0x180047a2f  mov     [rsp+150h+var_E8], r15
0x180047a34  mov     [rsp+150h+var_F0], r15
0x180047a39  mov     [rsp+150h+var_F8], r15
0x180047a3e  lea     rax, ?GlobalLocalhostAddress@@3Usockaddr_storage@@A; sockaddr_storage GlobalLocalhostAddress
0x180047a45  mov     [rsp+150h+var_100], rax
0x180047a4a  mov     [rsp+150h+var_108], r15
0x180047a4f  mov     [rsp+150h+var_110], r15
0x180047a54  lea     rax, [rbp-10h+arg_0]
0x180047a58  mov     [rsp+150h+var_118], rax
0x180047a5d  lea     rax, [rbp-10h+var_70]
0x180047a61  mov     [rsp+150h+var_120], rax
0x180047a66  mov     [rsp+150h+var_128], r15
0x180047a6b  mov     [rsp+150h+var_130], rbx
0x180047a70  xor     r9d, r9d
0x180047a73  mov     r8, rdi
0x180047a76  lea     rdx, [rsi+30h]
0x180047a7a  mov     ecx, 2A1h
0x180047a7f  call    cs:__imp_LsaIAuditKdcEvent
0x180047a85  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ExtendedAuditingForKerberos@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ExtendedAuditingForKerberos@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtendedAuditingForKerberos> `wil::Feature<__WilFeatureTraits_Feature_ExtendedAuditingForKerberos>::GetImpl(void)'::`2'::impl
0x180047a8c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ExtendedAuditingForKerberos@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtendedAuditingForKerberos>::__private_IsEnabled(void)
0x180047a91  test    al, al
0x180047a93  jz      loc_180047B2B
0x180047a99  mov     [rsp+150h+var_98], r15; struct _USER_INTERNAL6_INFORMATION *
0x180047aa1  mov     [rsp+150h+var_A0], r15; struct _KDC_S4U_TICKET_AUDIT_INFO *
0x180047aa9  mov     [rsp+150h+var_A8], r15; struct _KDC_U2U_TICKET_AUDIT_INFO *
0x180047ab1  mov     [rsp+150h+var_B0], r15; struct _KDC_S4U_TICKET_INFO *
0x180047ab9  mov     [rsp+150h+var_B8], r15; struct _KDC_U2U_TICKET_INFO *
0x180047ac1  mov     [rsp+150h+var_C0], r15; struct _KERB_ENCRYPTION_KEY *
0x180047ac9  mov     [rsp+150h+var_C8], r15; unsigned int *
0x180047ad1  mov     [rsp+150h+var_D0], r15; unsigned int *
0x180047ad9  mov     [rsp+150h+var_D8], r15; struct KERB_EXT_ERROR *
0x180047ade  mov     [rsp+150h+var_E0], r15; struct _UNICODE_STRING *
0x180047ae3  mov     [rsp+150h+var_E8], r15; struct KERB_ENCRYPTED_KDC_REPLY *
0x180047ae8  mov     [rsp+150h+var_F0], r15; struct KERB_TICKET *
0x180047aed  mov     [rsp+150h+var_F8], r15; struct KERB_KDC_REQUEST_BODY *
0x180047af2  mov     [rsp+150h+var_100], r15; struct KERB_AP_REQUEST *
0x180047af7  mov     [rsp+150h+var_108], r15; struct _LSA_ADT_STRING_LIST *
0x180047afc  mov     [rsp+150h+var_110], r15; struct _GUID *
0x180047b01  mov     [rsp+150h+var_118], r15; struct sockaddr *
0x180047b06  mov     [rsp+150h+var_120], r15; unsigned int *
0x180047b0b  lea     rax, [rbp-10h+arg_0]
0x180047b0f  mov     [rsp+150h+var_128], rax; int *
0x180047b14  mov     [rsp+150h+var_130], r15; unsigned int *
0x180047b19  xor     r9d, r9d; void *
0x180047b1c  mov     r8, rbx; struct _UNICODE_STRING *
0x180047b1f  mov     rdx, rdi; struct _UNICODE_STRING *
0x180047b22  lea     rcx, [rsi+30h]; struct _UNICODE_STRING *
0x180047b26  call    ?LogGetTgsExtendedAudit@@YAXPEAU_UNICODE_STRING@@00PEAXPEAKPEAJ2PEAUsockaddr@@PEAU_GUID@@PEAU_LSA_ADT_STRING_LIST@@PEAUKERB_AP_REQUEST@@PEAUKERB_KDC_REQUEST_BODY@@PEAUKERB_TICKET@@PEAUKERB_ENCRYPTED_KDC_REPLY@@0PEAUKERB_EXT_ERROR@@22PEAU_KERB_ENCRYPTION_KEY@@PEAU_KDC_U2U_TICKET_INFO@@PEAU_KDC_S4U_TICKET_INFO@@PEAU_KDC_U2U_TICKET_AUDIT_INFO@@PEAU_KDC_S4U_TICKET_AUDIT_INFO@@PEAU_USER_INTERNAL6_INFORMATION@@@Z; LogGetTgsExtendedAudit(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,void *,ulong *,long *,ulong *,sockaddr *,_GUID *,_LSA_ADT_STRING_LIST *,KERB_AP_REQUEST *,KERB_KDC_REQUEST_BODY *,KERB_TICKET *,KERB_ENCRYPTED_KDC_REPLY *,_UNICODE_STRING *,KERB_EXT_ERROR *,ulong *,ulong *,_KERB_ENCRYPTION_KEY *,_KDC_U2U_TICKET_INFO *,_KDC_S4U_TICKET_INFO *,_KDC_U2U_TICKET_AUDIT_INFO *,_KDC_S4U_TICKET_AUDIT_INFO *,_USER_INTERNAL6_INFORMATION *)
0x180047b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180047b32  cmp     rcx, r12
0x180047b35  jz      short loc_180047B56
0x180047b37  test    byte ptr [rcx+1Ch], 1
0x180047b3b  jz      short loc_180047B56
0x180047b3d  mov     edx, 3Ah ; ':'
0x180047b42  mov     r9d, [rbp-10h+arg_0]
0x180047b46  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x180047b4d  mov     rcx, [rcx+10h]
0x180047b51  call    WPP_SF_d
0x180047b56  mov     ebx, [rbp-10h+arg_0]
0x180047b59  mov     rcx, qword ptr [rbp-10h+var_68+8]
0x180047b5d  test    rcx, rcx
0x180047b60  jz      short loc_180047B8A
0x180047b62  mov     rax, [rbp-10h+arg_10]
0x180047b66  test    rax, rax
0x180047b69  jz      short loc_180047B71
0x180047b6b  cmp     [rax+8], rcx
0x180047b6f  jz      short loc_180047B8A
0x180047b71  mov     rdx, [rbp-10h+arg_18]
0x180047b75  test    rdx, rdx
0x180047b78  jz      short loc_180047B80
0x180047b7a  cmp     [rdx+8], rcx
0x180047b7e  jz      short loc_180047B8A
0x180047b80  lea     rcx, [rbp-10h+var_68]
0x180047b84  call    cs:__imp_SamIFreeClaimsBlob
0x180047b8a  mov     eax, ebx
0x180047b8c  jmp     loc_180047C2D
0x180047b91  mov     r9, [rbp-10h+arg_18]
0x180047b95  mov     rcx, cs:WPP_GLOBAL_Control
0x180047b9c  test    rdi, rdi
0x180047b9f  jz      short loc_180047BEC
0x180047ba1  test    byte ptr [rdi+38h], 8
0x180047ba5  jz      short loc_180047BD4
0x180047ba7  lea     rbx, [rdi+10h]
0x180047bab  cmp     rcx, r12
0x180047bae  jz      short loc_180047BD7
0x180047bb0  test    byte ptr [rcx+1Ch], 4
0x180047bb4  jz      short loc_180047BD7
0x180047bb6  mov     edx, 3Bh ; ';'
0x180047bbb  mov     r9, rbx
0x180047bbe  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x180047bc5  mov     rcx, [rcx+10h]
0x180047bc9  call    WPP_SF_Z
0x180047bce  mov     r9, [rbp-10h+arg_18]
0x180047bd2  jmp     short loc_180047BD7
0x180047bd4  mov     rbx, r15
0x180047bd7  mov     r8, [rdi+58h]
0x180047bdb  test    r8, r8
0x180047bde  jnz     short loc_180047C3F
0x180047be0  cmp     dword ptr [rdi+34h], 3
0x180047be4  jz      short loc_180047C3F
0x180047be6  test    byte ptr [rdi+38h], 10h
0x180047bea  jnz     short loc_180047C3F
0x180047bec  test    r9, r9
0x180047bef  jz      short loc_180047BFE
0x180047bf1  movups  xmm0, [rbp-10h+var_68]
0x180047bf5  movdqu  xmmword ptr [r9], xmm0
0x180047bfa  mov     r9, [rbp-10h+arg_18]
0x180047bfe  mov     rax, qword ptr [rbp-10h+var_68+8]
0x180047c02  test    rax, rax
0x180047c05  jz      short loc_180047C2B
0x180047c07  mov     rcx, [rbp-10h+arg_10]
0x180047c0b  test    rcx, rcx
0x180047c0e  jz      short loc_180047C16
0x180047c10  cmp     [rcx+8], rax
0x180047c14  jz      short loc_180047C2B
0x180047c16  test    r9, r9
0x180047c19  jz      short loc_180047C21
0x180047c1b  cmp     [r9+8], rax
0x180047c1f  jz      short loc_180047C2B
0x180047c21  lea     rcx, [rbp-10h+var_68]
0x180047c25  call    cs:__imp_SamIFreeClaimsBlob
0x180047c2b  xor     eax, eax
0x180047c2d  add     rsp, 120h
0x180047c34  pop     r15
0x180047c36  pop     r14
0x180047c38  pop     r12
0x180047c3a  pop     rdi
0x180047c3b  pop     rsi
0x180047c3c  pop     rbx
0x180047c3d  pop     rbp
0x180047c3e  retn
0x180047c3f  mov     rax, qword ptr [rbp-10h+var_68+8]
0x180047c43  neg     rax
0x180047c46  sbb     rdx, rdx
0x180047c49  lea     rax, [rbp-10h+var_68]
0x180047c4d  and     rdx, rax
0x180047c50  lea     rcx, [rsi+128h]
0x180047c57  mov     [rsp+150h+var_E8], r9
0x180047c5c  mov     [rsp+150h+var_F0], rdx
0x180047c61  mov     rax, [rsi+130h]
0x180047c68  mov     [rsp+150h+var_F8], rax
0x180047c6d  mov     [rsp+150h+var_100], rcx
0x180047c72  mov     rax, [rsi+120h]
0x180047c79  mov     [rsp+150h+var_108], rax
0x180047c7e  mov     [rsp+150h+var_110], rsi
0x180047c83  mov     dword ptr [rsp+150h+var_118], 3
0x180047c8b  mov     [rsp+150h+var_120], r8
0x180047c90  mov     eax, [rdi+38h]
0x180047c93  mov     dword ptr [rsp+150h+var_128], eax
0x180047c97  mov     eax, [rdi+34h]
0x180047c9a  mov     dword ptr [rsp+150h+var_130], eax
0x180047c9e  mov     r9d, 1
0x180047ca4  mov     r8, rdi
0x180047ca7  mov     rdx, rbx
0x180047caa  xor     ecx, ecx
0x180047cac  call    cs:__imp_LsaITransformAuthorizationData
0x180047cb2  mov     ebx, eax
0x180047cb4  mov     [rbp-10h+arg_0], eax
0x180047cb7  test    eax, eax
0x180047cb9  jns     loc_180047BFA
0x180047cbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180047cc6  cmp     rcx, r12
0x180047cc9  jz      short loc_180047CEC
0x180047ccb  test    byte ptr [rcx+1Ch], 1
0x180047ccf  jz      short loc_180047CEC
0x180047cd1  mov     edx, 3Ch ; '<'
0x180047cd6  mov     r9d, eax
0x180047cd9  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x180047ce0  mov     rcx, [rcx+10h]
0x180047ce4  call    WPP_SF_d
0x180047ce9  mov     ebx, [rbp-10h+arg_0]
0x180047cec  mov     rcx, qword ptr [rbp-10h+var_68+8]
0x180047cf0  test    rcx, rcx
0x180047cf3  jz      loc_180047B8A
0x180047cf9  mov     rax, [rbp-10h+arg_10]
0x180047cfd  test    rax, rax
0x180047d00  jz      short loc_180047D0C
0x180047d02  cmp     [rax+8], rcx
0x180047d06  jz      loc_180047B8A
0x180047d0c  mov     rax, [rbp-10h+arg_18]
0x180047d10  test    rax, rax
0x180047d13  jz      loc_180047B80
0x180047d19  cmp     [rax+8], rcx
0x180047d1d  jmp     loc_180047B7E
```
