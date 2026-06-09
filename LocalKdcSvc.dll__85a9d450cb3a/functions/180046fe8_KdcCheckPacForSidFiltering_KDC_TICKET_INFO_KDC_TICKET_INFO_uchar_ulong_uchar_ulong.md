# KdcCheckPacForSidFiltering(_KDC_TICKET_INFO *,_KDC_TICKET_INFO *,uchar * *,ulong *,uchar,ulong *)

- ea: `0x180046fe8`
- end: `0x18004774e`
- name: `?KdcCheckPacForSidFiltering@@YAJPEAU_KDC_TICKET_INFO@@0PEAPEAEPEAKE2@Z`
- size: `1894`
- prototype: `__int64 __fastcall(struct _KDC_TICKET_INFO *, struct _KDC_TICKET_INFO *, unsigned __int8 **, unsigned int *, char, unsigned int *)`
- caller_count: `3`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180047f90`
- `0x180049ed4`
- `0x18004ab84`

## callees

- `0x180002ad0`
- `0x1800038f0`
- `0x1800101c4`
- `0x180045280`
- `0x1800452bc`
- `0x1800455c8`
- `0x180046fe8`
- `0x180047850`
- `0x18005a090`
- `0x18006fc78`
- `0x18006fcac`
- `0x180070984`
- `0x180070f30`
- `0x180070fdc`
- `0x1800710d8`
- `0x180071134`
- `0x180071868`
- `0x180099be0`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180047276`
- `ntdll!RtlEqualSid` at `0x180047276`

## pseudocode

```c
__int64 __fastcall KdcCheckPacForSidFiltering(
        struct _KDC_TICKET_INFO *a1,
        struct _KDC_TICKET_INFO *a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        char a5,
        unsigned int *a6)
{
  unsigned int v7; // edi
  __int64 v8; // rax
  struct _PACTYPE **v9; // r11
  struct _PACTYPE *v10; // r12
  unsigned int *v11; // r10
  unsigned int v12; // ebx
  struct _PAC_INFO_BUFFER *v13; // r8
  CSecurityData *v14; // rcx
  __int64 v15; // rdx
  struct _PAC_INFO_BUFFER *v16; // rax
  struct _PAC_INFO_BUFFER *v17; // r8
  struct _PAC_INFO_BUFFER *v18; // rax
  struct _PAC_INFO_BUFFER *v19; // r8
  char v20; // r15
  struct _PAC_INFO_BUFFER *v21; // rax
  struct _PAC_INFO_BUFFER *v22; // r14
  struct _NETLOGON_VALIDATION_SAM_INFO3 *v23; // rdx
  unsigned int v24; // esi
  BOOLEAN v25; // al
  struct _KDC_TICKET_INFO *v26; // rdi
  struct _PAC_INFO_BUFFER *v27; // r8
  struct _PAC_INFO_BUFFER *v28; // r14
  struct _PAC_INFO_BUFFER *v29; // rax
  int v31; // eax
  unsigned int v32; // edx
  struct _NETLOGON_VALIDATION_SAM_INFO3 *v33; // rcx
  unsigned int v34; // eax
  unsigned __int64 v35; // rsi
  struct _NETLOGON_VALIDATION_SAM_INFO3 **v36; // rdi
  unsigned __int64 v37; // rcx
  unsigned __int64 v38; // rcx
  void *v39; // rsp
  void *v40; // rsp
  _DWORD *v41; // rax
  unsigned __int64 v42; // rax
  struct _PAC_INFO_BUFFER *v43; // r8
  unsigned int Size; // eax
  unsigned int v45; // r11d
  __int64 v46; // [rsp+0h] [rbp-70h] BYREF
  int v47; // [rsp+70h] [rbp+0h] BYREF
  struct _NETLOGON_VALIDATION_SAM_INFO3 *v48; // [rsp+78h] [rbp+8h] BYREF
  struct _PACTYPE *v49; // [rsp+80h] [rbp+10h] BYREF
  unsigned int v50; // [rsp+88h] [rbp+18h] BYREF
  int v51; // [rsp+8Ch] [rbp+1Ch] BYREF
  void *Src; // [rsp+90h] [rbp+20h] BYREF
  struct _NETLOGON_VALIDATION_SAM_INFO3 *v53; // [rsp+98h] [rbp+28h] BYREF
  struct _PACTYPE *v54; // [rsp+A0h] [rbp+30h] BYREF
  struct _KDC_TICKET_INFO *v55; // [rsp+A8h] [rbp+38h]
  __int128 v56; // [rsp+B0h] [rbp+40h] BYREF
  __int128 v57; // [rsp+C0h] [rbp+50h] BYREF
  __int128 v58; // [rsp+D0h] [rbp+60h] BYREF
  __int128 v59; // [rsp+E0h] [rbp+70h] BYREF
  __int128 v60; // [rsp+F0h] [rbp+80h] BYREF
  __int128 v61; // [rsp+100h] [rbp+90h] BYREF
  struct _PAC_INFO_BUFFER *v62; // [rsp+110h] [rbp+A0h]
  unsigned __int8 **v63; // [rsp+118h] [rbp+A8h]
  unsigned int *v64; // [rsp+120h] [rbp+B0h]
  _BYTE v65[112]; // [rsp+130h] [rbp+C0h] BYREF
  char v66; // [rsp+1A0h] [rbp+130h] BYREF

  v64 = a4;
  v63 = a3;
  v55 = a2;
  v7 = 0;
  v49 = 0;
  v48 = 0;
  v53 = 0;
  Src = 0;
  v51 = 0;
  BYTE1(v47) = 0;
  v54 = 0;
  v50 = 0;
  v58 = 0;
  v59 = 0;
  v56 = 0;
  v57 = 0;
  v61 = 0;
  v60 = 0;
  v8 = lambda_cfb68bcf5d67a1ebe74ee9ad44f62bf7_::_lambda_cfb68bcf5d67a1ebe74ee9ad44f62bf7_(
         (unsigned int)&v66,
         (unsigned int)&v54,
         (unsigned int)&v50,
         (unsigned int)&v49,
         (__int64)&v47 + 1,
         (__int64)&v48,
         (__int64)&Src,
         (__int64)&v51,
         (__int64)&v53,
         (__int64)&v59,
         (__int64)&v58,
         (__int64)&v57,
         (__int64)&v56);
  wil::scope_exit__lambda_cfb68bcf5d67a1ebe74ee9ad44f62bf7___(v65, v8);
  v10 = *v9;
  v12 = *v11;
  if ( !PAC_UnMarshal(*v9, *v11) )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_60;
    v15 = 61;
    goto LABEL_87;
  }
  v54 = v10;
  v50 = v12;
  v16 = PAC_Find(v10, 1u, v13);
  if ( !v16 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_60;
    v15 = 62;
    goto LABEL_87;
  }
  if ( (int)PAC_UnmarshallValidationInfo(&v48, *((unsigned __int8 **)v16 + 1), *((_DWORD *)v16 + 1)) < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_60;
    v15 = 63;
    goto LABEL_87;
  }
  v18 = PAC_Find(v10, 0xEu, v17);
  if ( v18 && (int)PAC_UnmarshallAndConvertDeviceInfo(&v53, *((unsigned __int8 **)v18 + 1), *((_DWORD *)v18 + 1)) < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_60;
    v15 = 64;
    goto LABEL_87;
  }
  v20 = 0;
  LOBYTE(v47) = 0;
  v21 = PAC_Find(v10, 0xDu, v19);
  v22 = v21;
  v62 = v21;
  v23 = v48;
  v24 = *((_DWORD *)v48 + 68);
  if ( v21 )
  {
    LODWORD(v58) = *((_DWORD *)v21 + 1);
    *((_QWORD *)&v58 + 1) = *((_QWORD *)v21 + 1);
  }
  else if ( (*((_BYTE *)a1 + 112) & 0x10) != 0 && *((_DWORD *)a1 + 12) != 502 && !*((_BYTE *)a1 + 104) )
  {
    v20 = 1;
    LOBYTE(v47) = 1;
    while ( v7 < *((_DWORD *)v23 + 68) )
    {
      v25 = RtlEqualSid(GlobalClaimsValidSid, *(PSID *)(*((_QWORD *)v23 + 35) + 16LL * v7));
      v23 = v48;
      if ( v25 )
      {
        v20 = 0;
        LOBYTE(v47) = 0;
        break;
      }
      ++v7;
    }
  }
  v26 = v55;
  if ( (int)KdcFilterSids(
              (struct _UNICODE_STRING *)a1,
              v55,
              (struct _SAM_CLAIMS_BLOB *)((unsigned __int64)&v58 & -(__int64)(v22 != 0)),
              (struct _SAM_CLAIMS_BLOB *)&v59,
              v23) < 0 )
  {
LABEL_34:
    wil::details::lambda_call__lambda_cfb68bcf5d67a1ebe74ee9ad44f62bf7___::_lambda_call__lambda_cfb68bcf5d67a1ebe74ee9ad44f62bf7___(v65);
    return 12;
  }
  v28 = 0;
  LODWORD(v61) = 13;
  DWORD1(v61) = v59;
  *((_QWORD *)&v61 + 1) = *((_QWORD *)&v59 + 1);
  if ( v53 )
  {
    v29 = PAC_Find(v10, 0xFu, v27);
    v28 = v29;
    if ( v29 )
    {
      LODWORD(v56) = *((_DWORD *)v29 + 1);
      *((_QWORD *)&v56 + 1) = *((_QWORD *)v29 + 1);
    }
    if ( a5 )
    {
      v57 = v56;
    }
    else if ( (int)KdcFilterSids(
                     (struct _UNICODE_STRING *)a1,
                     v26,
                     (struct _SAM_CLAIMS_BLOB *)((unsigned __int64)&v56 & -(__int64)(v29 != 0)),
                     (struct _SAM_CLAIMS_BLOB *)&v57,
                     v53) < 0 )
    {
      goto LABEL_34;
    }
    LODWORD(v60) = 15;
    DWORD1(v60) = v57;
    *((_QWORD *)&v60 + 1) = *((_QWORD *)&v57 + 1);
  }
  v31 = (*((_DWORD *)a1 + 14) >> 4) & 1;
  if ( a5 )
    ++v31;
  v32 = v31 + 1;
  if ( !v20 )
    v32 = v31;
  v33 = v48;
  if ( v24 < v32 || *((_DWORD *)v48 + 68) > v24 - v32 )
  {
    Src = (void *)*((_QWORD *)v48 + 35);
    v51 = *((_DWORD *)v48 + 68);
    v34 = *((_DWORD *)v48 + 68);
    if ( v34 + v32 < v34 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_60;
      v15 = 65;
      goto LABEL_87;
    }
    v35 = 16LL * (v34 + v32);
    if ( v35 > 0xFFFFFFFF )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_60;
      v15 = 66;
      goto LABEL_87;
    }
    v36 = 0;
    if ( (_DWORD)v35
      && (unsigned int)v35 <= (unsigned __int64)g_ulMaxStackAllocSize
      && (unsigned __int64)(unsigned int)v35 + g_ulAdditionalProbeSize + 8 >= (unsigned int)v35 )
    {
      if ( (unsigned int)VerifyStackAvailable((unsigned int)v35 + g_ulAdditionalProbeSize + 8) )
      {
        v37 = (unsigned int)v35 + 23LL;
        if ( v37 <= (unsigned __int64)(unsigned int)v35 + 8 )
          v37 = 0xFFFFFFFFFFFFFF0LL;
        v38 = v37 & 0xFFFFFFFFFFFFFFF0uLL;
        v39 = alloca(v38);
        v40 = alloca(v38);
        v36 = (struct _NETLOGON_VALIDATION_SAM_INFO3 **)&v47;
        if ( &v46 != (__int64 *)-112LL )
        {
          v47 = 1801679955;
          v36 = &v48;
          if ( &v48 )
            goto LABEL_57;
        }
      }
      v33 = v48;
    }
    if ( (unsigned __int64)(unsigned int)v35 + 8 < (unsigned int)v35 )
    {
LABEL_58:
      *((_QWORD *)v33 + 35) = v36;
      if ( !*((_QWORD *)v48 + 35) )
      {
        *((_QWORD *)v48 + 35) = Src;
        Src = 0;
LABEL_60:
        wil::details::lambda_call__lambda_cfb68bcf5d67a1ebe74ee9ad44f62bf7___::_lambda_call__lambda_cfb68bcf5d67a1ebe74ee9ad44f62bf7___(v65);
        return 60;
      }
      BYTE1(v47) = 1;
      v42 = 16LL * *((unsigned int *)v48 + 68);
      if ( v42 <= 0xFFFFFFFF )
      {
        memcpy_0(*((void **)v48 + 35), Src, (unsigned int)v42);
        v33 = v48;
        v20 = v47;
        goto LABEL_63;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_60;
      v15 = 67;
LABEL_87:
      WPP_SF_(*((_QWORD *)v14 + 2), v15, WPP_3875113a630833a3e73becf979560e87_Traceguids);
      goto LABEL_60;
    }
    v41 = (_DWORD *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)((unsigned int)v35 + 8LL);
    v36 = (struct _NETLOGON_VALIDATION_SAM_INFO3 **)v41;
    if ( v41 )
    {
      *v41 = 1885431112;
      v36 = (struct _NETLOGON_VALIDATION_SAM_INFO3 **)(v41 + 2);
    }
LABEL_57:
    v33 = v48;
    goto LABEL_58;
  }
LABEL_63:
  if ( (*((_BYTE *)a1 + 56) & 0x10) != 0 )
  {
    *(_QWORD *)(*((_QWORD *)v33 + 35) + 16LL * *((unsigned int *)v33 + 68)) = GlobalOtherOrganizationSid;
    *(_DWORD *)(*((_QWORD *)v48 + 35) + 16LL * (unsigned int)(*((_DWORD *)v48 + 68))++ + 8) = 7;
    v33 = v48;
  }
  if ( a5 )
  {
    *(_QWORD *)(*((_QWORD *)v33 + 35) + 16LL * *((unsigned int *)v33 + 68)) = GlobalCompoundedIdentitySid;
    *(_DWORD *)(*((_QWORD *)v48 + 35) + 16LL * (unsigned int)(*((_DWORD *)v48 + 68))++ + 8) = 7;
    v33 = v48;
  }
  if ( v20 )
  {
    *(_QWORD *)(*((_QWORD *)v33 + 35) + 16LL * *((unsigned int *)v33 + 68)) = GlobalClaimsValidSid;
    *(_DWORD *)(*((_QWORD *)v48 + 35) + 16LL * (unsigned int)(*((_DWORD *)v48 + 68))++ + 8) = 7;
    v33 = v48;
  }
  if ( v62 || v20 )
    v43 = (struct _PAC_INFO_BUFFER *)&v61;
  else
    v43 = 0;
  if ( PAC_UpdateGroupsAndClaims(
         v33,
         v53,
         v43,
         (struct _PAC_INFO_BUFFER *)((unsigned __int64)&v60 & -(__int64)(v28 != 0)),
         v10,
         &v49) < 0 )
    goto LABEL_60;
  Size = PAC_GetSize(v49);
  if ( !PAC_ReMarshal(v49, Size) )
    goto LABEL_60;
  *v63 = (unsigned __int8 *)v49;
  v49 = 0;
  v54 = 0;
  *v64 = v45;
  MIDL_user_free(v10);
  if ( a6 )
    *a6 = *((_DWORD *)v48 + 60);
  wil::details::lambda_call__lambda_cfb68bcf5d67a1ebe74ee9ad44f62bf7___::_lambda_call__lambda_cfb68bcf5d67a1ebe74ee9ad44f62bf7___(v65);
  return 0;
}

```

## disassembly

```asm
0x180046fe8  push    rbp
0x180046fea  push    rbx
0x180046feb  push    rsi
0x180046fec  push    rdi
0x180046fed  push    r12
0x180046fef  push    r13
0x180046ff1  push    r14
0x180046ff3  push    r15
0x180046ff5  sub     rsp, 218h
0x180046ffc  lea     rbp, [rsp+70h]
0x180047001  mov     rax, cs:__security_cookie
0x180047008  xor     rax, rbp
0x18004700b  mov     [rbp+1E0h+var_50], rax
0x180047012  mov     r10, r9
0x180047015  mov     [rbp+1E0h+var_130], r9
0x18004701c  mov     r11, r8
0x18004701f  mov     [rbp+1E0h+var_138], r8
0x180047026  mov     [rbp+1E0h+var_1A8], rdx
0x18004702a  mov     r13, rcx
0x18004702d  xor     edi, edi
0x18004702f  mov     [rbp+1E0h+var_1D0], rdi
0x180047033  mov     [rbp+1E0h+var_1D8], rdi
0x180047037  mov     [rbp+1E0h+var_1B8], rdi
0x18004703b  mov     [rbp+1E0h+Src], rdi
0x18004703f  mov     [rbp+1E0h+var_1C4], edi
0x180047042  mov     [rbp+1E0h+var_1DF], dil
0x180047046  mov     [rbp+1E0h+var_1B0], rdi
0x18004704a  mov     [rbp+1E0h+var_1C8], edi
0x18004704d  xorps   xmm0, xmm0
0x180047050  movups  [rbp+1E0h+var_180], xmm0
0x180047054  xorps   xmm1, xmm1
0x180047057  movups  [rbp+1E0h+var_170], xmm1
0x18004705b  movups  [rbp+1E0h+var_1A0], xmm0
0x18004705f  movups  [rbp+1E0h+var_190], xmm1
0x180047063  movups  [rbp+1E0h+var_150], xmm0
0x18004706a  movups  [rbp+1E0h+var_160], xmm1
0x180047071  lea     rax, [rbp+1E0h+var_1A0]
0x180047075  mov     [rsp+250h+var_1F0], rax
0x18004707a  lea     rax, [rbp+1E0h+var_190]
0x18004707e  mov     [rsp+250h+var_1F8], rax
0x180047083  lea     rax, [rbp+1E0h+var_180]
0x180047087  mov     [rsp+250h+var_200], rax
0x18004708c  lea     rax, [rbp+1E0h+var_170]
0x180047090  mov     [rsp+250h+var_208], rax
0x180047095  lea     rax, [rbp+1E0h+var_1B8]
0x180047099  mov     [rsp+250h+var_210], rax
0x18004709e  lea     rax, [rbp+1E0h+var_1C4]
0x1800470a2  mov     [rsp+250h+var_218], rax
0x1800470a7  lea     rax, [rbp+1E0h+Src]
0x1800470ab  mov     [rsp+250h+var_220], rax
0x1800470b0  lea     rax, [rbp+1E0h+var_1D8]
0x1800470b4  mov     [rsp+250h+var_228], rax
0x1800470b9  lea     rax, [rbp+1E0h+var_1DF]
0x1800470bd  mov     [rsp+250h+var_230], rax
0x1800470c2  lea     r9, [rbp+1E0h+var_1D0]
0x1800470c6  lea     r8, [rbp+1E0h+var_1C8]
0x1800470ca  lea     rdx, [rbp+1E0h+var_1B0]
0x1800470ce  lea     rcx, [rbp+1E0h+var_B0]
0x1800470d5  call    _lambda_cfb68bcf5d67a1ebe74ee9ad44f62bf7____lambda_cfb68bcf5d67a1ebe74ee9ad44f62bf7_
0x1800470da  mov     rdx, rax
0x1800470dd  lea     rcx, [rbp+1E0h+var_120]
0x1800470e4  call    wil__scope_exit__lambda_cfb68bcf5d67a1ebe74ee9ad44f62bf7___
0x1800470e9  nop
0x1800470ea  mov     r12, [r11]
0x1800470ed  mov     ebx, [r10]
0x1800470f0  mov     edx, ebx; unsigned int
0x1800470f2  mov     rcx, r12; struct _PACTYPE *
0x1800470f5  call    ?PAC_UnMarshal@@YAKPEAU_PACTYPE@@K@Z; PAC_UnMarshal(_PACTYPE *,ulong)
0x1800470fa  test    eax, eax
0x1800470fc  jnz     short loc_180047129
0x1800470fe  lea     rax, WPP_GLOBAL_Control
0x180047105  mov     rcx, cs:WPP_GLOBAL_Control
0x18004710c  cmp     rcx, rax
0x18004710f  jz      loc_1800474D4
0x180047115  lea     ebx, [rdi+1]
0x180047118  test    [rcx+1Ch], bl
0x18004711b  jz      loc_1800474D4
0x180047121  lea     edx, [rdi+3Dh]
0x180047124  jmp     loc_180047738
0x180047129  mov     [rbp+1E0h+var_1B0], r12
0x18004712d  mov     [rbp+1E0h+var_1C8], ebx
0x180047130  mov     ebx, 1
0x180047135  mov     edx, ebx; unsigned int
0x180047137  mov     rcx, r12; struct _PACTYPE *
0x18004713a  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x18004713f  test    rax, rax
0x180047142  jnz     short loc_18004716D
0x180047144  lea     rax, WPP_GLOBAL_Control
0x18004714b  mov     rcx, cs:WPP_GLOBAL_Control
0x180047152  cmp     rcx, rax
0x180047155  jz      loc_1800474D4
0x18004715b  test    byte ptr [rcx+1Ch], 2
0x18004715f  jz      loc_1800474D4
0x180047165  lea     edx, [rbx+3Dh]
0x180047168  jmp     loc_180047738
0x18004716d  mov     r8d, [rax+4]; unsigned int
0x180047171  mov     rdx, [rax+8]; unsigned __int8 *
0x180047175  lea     rcx, [rbp+1E0h+var_1D8]; struct _NETLOGON_VALIDATION_SAM_INFO3 **
0x180047179  call    ?PAC_UnmarshallValidationInfo@@YAJPEAPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAEK@Z; PAC_UnmarshallValidationInfo(_NETLOGON_VALIDATION_SAM_INFO3 * *,uchar *,ulong)
0x18004717e  test    eax, eax
0x180047180  jns     short loc_1800471AC
0x180047182  lea     rax, WPP_GLOBAL_Control
0x180047189  mov     rcx, cs:WPP_GLOBAL_Control
0x180047190  cmp     rcx, rax
0x180047193  jz      loc_1800474D4
0x180047199  test    [rcx+1Ch], bl
0x18004719c  jz      loc_1800474D4
0x1800471a2  mov     edx, 3Fh ; '?'
0x1800471a7  jmp     loc_180047738
0x1800471ac  mov     edx, 0Eh; unsigned int
0x1800471b1  mov     rcx, r12; struct _PACTYPE *
0x1800471b4  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x1800471b9  test    rax, rax
0x1800471bc  jz      short loc_1800471FD
0x1800471be  mov     r8d, [rax+4]; unsigned int
0x1800471c2  mov     rdx, [rax+8]; unsigned __int8 *
0x1800471c6  lea     rcx, [rbp+1E0h+var_1B8]; struct _NETLOGON_VALIDATION_SAM_INFO4 **
0x1800471ca  call    ?PAC_UnmarshallAndConvertDeviceInfo@@YAJPEAPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAEK@Z; PAC_UnmarshallAndConvertDeviceInfo(_NETLOGON_VALIDATION_SAM_INFO4 * *,uchar *,ulong)
0x1800471cf  test    eax, eax
0x1800471d1  jns     short loc_1800471FD
0x1800471d3  lea     rax, WPP_GLOBAL_Control
0x1800471da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800471e1  cmp     rcx, rax
0x1800471e4  jz      loc_1800474D4
0x1800471ea  test    [rcx+1Ch], bl
0x1800471ed  jz      loc_1800474D4
0x1800471f3  mov     edx, 40h ; '@'
0x1800471f8  jmp     loc_180047738
0x1800471fd  mov     r15b, dil
0x180047200  mov     [rbp+1E0h+var_1E0], dil
0x180047204  mov     edx, 0Dh; unsigned int
0x180047209  mov     rcx, r12; struct _PACTYPE *
0x18004720c  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x180047211  mov     r14, rax
0x180047214  mov     [rbp+1E0h+var_140], rax
0x18004721b  mov     rdx, [rbp+1E0h+var_1D8]
0x18004721f  mov     esi, [rdx+110h]
0x180047225  test    rax, rax
0x180047228  jz      short loc_18004723A
0x18004722a  mov     ecx, [rax+4]
0x18004722d  mov     dword ptr [rbp+1E0h+var_180], ecx
0x180047230  mov     rcx, [rax+8]
0x180047234  mov     qword ptr [rbp+1E0h+var_180+8], rcx
0x180047238  jmp     short loc_18004728F
0x18004723a  test    byte ptr [r13+70h], 10h
0x18004723f  jz      short loc_18004728F
0x180047241  cmp     dword ptr [r13+30h], 1F6h
0x180047249  jz      short loc_18004728F
0x18004724b  cmp     [r13+68h], dil
0x18004724f  jnz     short loc_18004728F
0x180047251  mov     r15b, bl
0x180047254  mov     [rbp+1E0h+var_1E0], bl
0x180047257  cmp     edi, [rdx+110h]
0x18004725d  jnb     short loc_18004728F
0x18004725f  mov     eax, edi
0x180047261  add     rax, rax
0x180047264  mov     rdx, [rdx+118h]
0x18004726b  mov     rdx, [rdx+rax*8]; Sid2
0x18004726f  mov     rcx, cs:?GlobalClaimsValidSid@@3PEAXEA; Sid1
0x180047276  call    cs:__imp_RtlEqualSid
0x18004727c  mov     rdx, [rbp+1E0h+var_1D8]
0x180047280  test    al, al
0x180047282  jnz     short loc_180047288
0x180047284  add     edi, ebx
0x180047286  jmp     short loc_180047257
0x180047288  xor     r15b, r15b
0x18004728b  mov     [rbp+1E0h+var_1E0], r15b
0x18004728f  mov     rax, r14
0x180047292  neg     rax
0x180047295  sbb     r8, r8
0x180047298  lea     rax, [rbp+1E0h+var_180]
0x18004729c  and     r8, rax; struct _SAM_CLAIMS_BLOB *
0x18004729f  mov     [rsp+250h+var_230], rdx; struct _NETLOGON_VALIDATION_SAM_INFO3 *
0x1800472a4  lea     r9, [rbp+1E0h+var_170]; struct _SAM_CLAIMS_BLOB *
0x1800472a8  mov     rdi, [rbp+1E0h+var_1A8]
0x1800472ac  mov     rdx, rdi; struct _KDC_TICKET_INFO *
0x1800472af  mov     rcx, r13; struct _UNICODE_STRING *
0x1800472b2  call    ?KdcFilterSids@@YAJPEAU_KDC_TICKET_INFO@@0PEAU_SAM_CLAIMS_BLOB@@1PEAU_NETLOGON_VALIDATION_SAM_INFO3@@@Z; KdcFilterSids(_KDC_TICKET_INFO *,_KDC_TICKET_INFO *,_SAM_CLAIMS_BLOB *,_SAM_CLAIMS_BLOB *,_NETLOGON_VALIDATION_SAM_INFO3 *)
0x1800472b7  test    eax, eax
0x1800472b9  js      loc_180047341
0x1800472bf  xor     r14d, r14d
0x1800472c2  mov     dword ptr [rbp+1E0h+var_150], 0Dh
0x1800472cc  mov     eax, dword ptr [rbp+1E0h+var_170]
0x1800472cf  mov     dword ptr [rbp+1E0h+var_150+4], eax
0x1800472d5  mov     rax, qword ptr [rbp+1E0h+var_170+8]
0x1800472d9  mov     qword ptr [rbp+1E0h+var_150+8], rax
0x1800472e0  cmp     [rbp+1E0h+var_1B8], r14
0x1800472e4  jz      loc_18004739C
0x1800472ea  lea     edx, [r14+0Fh]; unsigned int
0x1800472ee  mov     rcx, r12; struct _PACTYPE *
0x1800472f1  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x1800472f6  mov     r14, rax
0x1800472f9  test    rax, rax
0x1800472fc  jz      short loc_18004730C
0x1800472fe  mov     ecx, [rax+4]
0x180047301  mov     dword ptr [rbp+1E0h+var_1A0], ecx
0x180047304  mov     rcx, [rax+8]
0x180047308  mov     qword ptr [rbp+1E0h+var_1A0+8], rcx
0x18004730c  cmp     [rbp+1E0h+arg_20], 0
0x180047313  jnz     short loc_180047375
0x180047315  mov     rcx, rax
0x180047318  neg     rcx
0x18004731b  sbb     r8, r8
0x18004731e  lea     rax, [rbp+1E0h+var_1A0]
0x180047322  and     r8, rax; struct _SAM_CLAIMS_BLOB *
0x180047325  mov     rax, [rbp+1E0h+var_1B8]
0x180047329  mov     [rsp+250h+var_230], rax; struct _NETLOGON_VALIDATION_SAM_INFO3 *
0x18004732e  lea     r9, [rbp+1E0h+var_190]; struct _SAM_CLAIMS_BLOB *
0x180047332  mov     rdx, rdi; struct _KDC_TICKET_INFO *
0x180047335  mov     rcx, r13; struct _UNICODE_STRING *
0x180047338  call    ?KdcFilterSids@@YAJPEAU_KDC_TICKET_INFO@@0PEAU_SAM_CLAIMS_BLOB@@1PEAU_NETLOGON_VALIDATION_SAM_INFO3@@@Z; KdcFilterSids(_KDC_TICKET_INFO *,_KDC_TICKET_INFO *,_SAM_CLAIMS_BLOB *,_SAM_CLAIMS_BLOB *,_NETLOGON_VALIDATION_SAM_INFO3 *)
0x18004733d  test    eax, eax
0x18004733f  jns     short loc_18004737E
0x180047341  lea     rcx, [rbp+1E0h+var_120]
0x180047348  call    wil__details__lambda_call__lambda_cfb68bcf5d67a1ebe74ee9ad44f62bf7______lambda_call__lambda_cfb68bcf5d67a1ebe74ee9ad44f62bf7___
0x18004734d  mov     eax, 0Ch
0x180047352  mov     rcx, [rbp+1E0h+var_50]
0x180047359  xor     rcx, rbp; StackCookie
0x18004735c  call    __security_check_cookie
0x180047361  lea     rsp, [rbp+1A8h]
0x180047368  pop     r15
0x18004736a  pop     r14
0x18004736c  pop     r13
0x18004736e  pop     r12
0x180047370  pop     rdi
0x180047371  pop     rsi
0x180047372  pop     rbx
0x180047373  pop     rbp
0x180047374  retn
0x180047375  movaps  xmm0, [rbp+1E0h+var_1A0]
0x180047379  movdqa  [rbp+1E0h+var_190], xmm0
0x18004737e  mov     dword ptr [rbp+1E0h+var_160], 0Fh
0x180047388  mov     eax, dword ptr [rbp+1E0h+var_190]
0x18004738b  mov     dword ptr [rbp+1E0h+var_160+4], eax
0x180047391  mov     rax, qword ptr [rbp+1E0h+var_190+8]
0x180047395  mov     qword ptr [rbp+1E0h+var_160+8], rax
0x18004739c  mov     eax, [r13+38h]
0x1800473a0  shr     eax, 4
0x1800473a3  and     eax, ebx
0x1800473a5  cmp     [rbp+1E0h+arg_20], 0
0x1800473ac  jz      short loc_1800473B0
0x1800473ae  inc     eax
0x1800473b0  lea     edx, [rax+1]
0x1800473b3  test    r15b, r15b
0x1800473b6  cmovz   edx, eax
0x1800473b9  mov     rcx, [rbp+1E0h+var_1D8]
0x1800473bd  cmp     esi, edx
0x1800473bf  jb      short loc_1800473CF
0x1800473c1  sub     esi, edx
0x1800473c3  cmp     [rcx+110h], esi
0x1800473c9  jbe     loc_180047520
0x1800473cf  mov     rax, [rcx+118h]
0x1800473d6  mov     [rbp+1E0h+Src], rax
0x1800473da  mov     eax, [rcx+110h]
0x1800473e0  mov     [rbp+1E0h+var_1C4], eax
0x1800473e3  mov     eax, [rcx+110h]
0x1800473e9  lea     r8d, [rax+rdx]
0x1800473ed  cmp     r8d, eax
0x1800473f0  jb      loc_180047713
0x1800473f6  mov     esi, r8d
0x1800473f9  shl     rsi, 4
0x1800473fd  mov     eax, 0FFFFFFFFh
0x180047402  cmp     rsi, rax
0x180047405  ja      loc_1800476EC
0x18004740b  xor     edi, edi
0x18004740d  test    esi, esi
0x18004740f  jz      short loc_18004747C
0x180047411  mov     r15d, esi
0x180047414  cmp     r15, cs:g_ulMaxStackAllocSize
0x18004741b  ja      short loc_18004747C
0x18004741d  mov     rdx, cs:g_ulAdditionalProbeSize
0x180047424  add     rdx, 8
0x180047428  add     rdx, r15
0x18004742b  cmp     rdx, r15
0x18004742e  jb      short loc_18004747C
0x180047430  mov     rcx, rdx
0x180047433  call    VerifyStackAvailable
0x180047438  test    eax, eax
0x18004743a  jz      short loc_180047478
0x18004743c  lea     rax, [r15+8]
0x180047440  lea     rcx, [rax+0Fh]
0x180047444  cmp     rcx, rax
0x180047447  ja      short loc_180047453
0x180047449  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180047453  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180047457  mov     rax, rcx
0x18004745a  call    _alloca_probe
0x18004745f  sub     rsp, rcx
0x180047462  lea     rdi, [rsp+250h+var_1E0]
0x180047467  test    rdi, rdi
0x18004746a  jz      short loc_180047478
0x18004746c  mov     dword ptr [rdi], 6B637453h
0x180047472  add     rdi, 8
0x180047476  jnz     short loc_1800474A8
0x180047478  mov     rcx, [rbp+1E0h+var_1D8]
0x18004747c  mov     eax, esi
0x18004747e  lea     rdx, [rax+8]
0x180047482  cmp     rdx, rax
0x180047485  jb      short loc_1800474AC
0x180047487  mov     rcx, rdx
  ... truncated ...
```
