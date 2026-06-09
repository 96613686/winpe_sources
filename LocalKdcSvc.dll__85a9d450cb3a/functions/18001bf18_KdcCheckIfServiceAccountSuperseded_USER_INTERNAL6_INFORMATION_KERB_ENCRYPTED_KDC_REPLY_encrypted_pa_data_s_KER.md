# KdcCheckIfServiceAccountSuperseded(_USER_INTERNAL6_INFORMATION *,KERB_ENCRYPTED_KDC_REPLY_encrypted_pa_data_s * *,KERB_KDC_REQUEST_preauth_data_s * *,int)

- ea: `0x18001bf18`
- end: `0x18001c37a`
- name: `?KdcCheckIfServiceAccountSuperseded@@YAXPEAU_USER_INTERNAL6_INFORMATION@@PEAPEAUKERB_ENCRYPTED_KDC_REPLY_encrypted_pa_data_s@@PEAPEAUKERB_KDC_REQUEST_preauth_data_s@@H@Z`
- size: `1122`
- prototype: `void __fastcall(struct _USER_INTERNAL6_INFORMATION *, struct KERB_ENCRYPTED_KDC_REPLY_encrypted_pa_data_s **, struct KERB_KDC_REQUEST_preauth_data_s **, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180016148`

## callees

- `0x1800101c4`
- `0x1800101ec`
- `0x18001022c`
- `0x18001bf18`
- `0x18001e8c8`
- `0x18005a060`
- `0x180072288`
- `0x180072338`
- `0x18007d860`
- `0x18007da34`
- `0x18007db8c`
- `0x18007dbe8`
- `0x18007f78c`

## import_xrefs

- `SAMSRV!SamIFree_UserInternal6Information` at `0x18001c2bf`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18001c2bf`
- `SAMSRV!SamrCloseHandle` at `0x18001c2c9`
- `SAMSRV!SamrCloseHandle` at `0x18001c2c9`
- `SAMSRV!SamIGetUserLogonInformation3` at `0x18001c031`
- `SAMSRV!SamIGetUserLogonInformation3` at `0x18001c031`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18001c2d3`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18001c2d3`

## string_xrefs

- `0x18001c06e`: `kdcsvc.dll`
- `0x18001c15c`: `kdcsvc.dll`

## pseudocode

```c
void __fastcall KdcCheckIfServiceAccountSuperseded(
        struct _USER_INTERNAL6_INFORMATION *a1,
        struct KERB_ENCRYPTED_KDC_REPLY_encrypted_pa_data_s **a2,
        struct KERB_KDC_REQUEST_preauth_data_s **a3,
        int a4)
{
  struct KERB_ENCRYPTED_KDC_REPLY_encrypted_pa_data_s **v5; // rsi
  unsigned __int64 v8; // xmm1_8
  int v9; // ebx
  char IsEnabled; // al
  __int64 v11; // rcx
  __int64 v12; // r8
  CSecurityData *v13; // r10
  int v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // eax
  __int64 v17; // r9
  CSecurityData *v18; // rcx
  __int64 v19; // rdx
  unsigned int v20; // eax
  _DWORD *v21; // rax
  __int64 v22; // [rsp+60h] [rbp-69h] BYREF
  __int128 v23; // [rsp+68h] [rbp-61h] BYREF
  __int64 v24; // [rsp+78h] [rbp-51h] BYREF
  __int128 v25; // [rsp+80h] [rbp-49h] BYREF
  _QWORD v26[2]; // [rsp+90h] [rbp-39h] BYREF
  __int128 v27; // [rsp+A0h] [rbp-29h] BYREF
  __int64 *v28; // [rsp+B0h] [rbp-19h]
  __int64 *v29; // [rsp+B8h] [rbp-11h]
  __int128 *v30; // [rsp+C0h] [rbp-9h]
  __int128 *v31; // [rsp+C8h] [rbp-1h]
  char v32; // [rsp+D0h] [rbp+7h]
  __int64 v33; // [rsp+130h] [rbp+67h] BYREF

  v5 = a3;
  v25 = 0;
  v22 = 0;
  v33 = 0;
  v23 = 0;
  v24 = 0;
  v27 = 0;
  if ( a1 && a3 && a2 )
  {
    v8 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( !*(_QWORD *)((char *)a1 + 660) && v8 == *(_QWORD *)((char *)a1 + 668) )
      return;
    if ( a4 && *((_DWORD *)a1 + 169) != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgs(0);
    v28 = &v33;
    v29 = &v22;
    v30 = &v25;
    v31 = &v23;
    v32 = 1;
    v26[0] = 1048592;
    v26[1] = (char *)a1 + 660;
    v9 = ((__int64 (__fastcall *)(void *, __int64, _QWORD *, __int64, int, _QWORD, _QWORD, _QWORD, __int64 *, __int128 *, _QWORD, __int64 *))SamIGetUserLogonInformation3)(
           GlobalAccountDomainHandle,
           256,
           v26,
           1,
           0x20000000,
           0,
           0,
           0,
           &v33,
           &v25,
           0,
           &v22);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink>::GetImpl'::`2'::impl);
    v11 = v33;
    if ( IsEnabled )
    {
      if ( v9 >= 0 && v33
        || (!v33 ? (v12 = 0) : (v12 = *(unsigned __int8 *)(v33 + 680)),
            MicrosoftTelemetryAssertTriggeredArgs("kdcsvc.dll", (unsigned int)v9, v12),
            v11 = v33,
            v9 >= 0) )
      {
        if ( v11 && *(_BYTE *)(v11 + 680) )
        {
          if ( !*(_QWORD *)(v11 + 684) && v8 == *(_QWORD *)(v11 + 692)
            || *((_QWORD *)a1 + 94) != *(_QWORD *)(v11 + 684)
            || *((_QWORD *)a1 + 95) != *(_QWORD *)(v11 + 692) )
          {
            if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids);
LABEL_64:
              v11 = v33;
            }
LABEL_57:
            SamIFree_UserInternal6Information(v11);
            SamrCloseHandle(&v22);
            SamIFreeSidAndAttributesList(&v25);
            if ( *((_QWORD *)&v23 + 1) )
              KerbFreePrincipalName(&v23);
            KerbFreeRealm(&v24);
            return;
          }
LABEL_35:
          if ( *((_DWORD *)a1 + 169) != *(_DWORD *)(v11 + 700) )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs(v11);
            v11 = v33;
          }
          if ( a4 && *(_DWORD *)(v11 + 700) != 2 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs(v11);
            v11 = v33;
          }
          v16 = KerbConvertStringToPrincipalName(&v23, v11 + 48);
          v17 = v16;
          if ( v16 )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            {
              goto LABEL_56;
            }
            v19 = 86;
          }
          else
          {
            v20 = KerbConvertUnicodeStringToRealm(&v24, &DomainName2);
            v17 = v20;
            if ( !v20 )
            {
              KerbPackData(&v23, 46, &v27, (char *)&v27 + 8);
              if ( !a4 )
                v5 = a2;
              v21 = MIDL_user_allocate(0x20u);
              if ( v21 )
              {
                v21[2] = 170;
                v21[4] = v27;
                *((_QWORD *)v21 + 3) = *((_QWORD *)&v27 + 1);
                *(_QWORD *)v21 = *v5;
                *v5 = (struct KERB_ENCRYPTED_KDC_REPLY_encrypted_pa_data_s *)v21;
              }
              else if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids);
              }
              goto LABEL_56;
            }
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            {
LABEL_56:
              v11 = v33;
              goto LABEL_57;
            }
            v19 = 87;
          }
          WPP_SF_d(*((_QWORD *)v18 + 2), v19, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, v17);
          goto LABEL_56;
        }
      }
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_57;
      if ( v11 )
        v14 = *(unsigned __int8 *)(v11 + 680);
      else
        v14 = 0;
      v15 = 83;
    }
    else
    {
      if ( v9 >= 0 && *(_BYTE *)(v33 + 680)
        || (MicrosoftTelemetryAssertTriggeredArgs("kdcsvc.dll", (unsigned int)v9, *(unsigned __int8 *)(v33 + 680)),
            v11 = v33,
            v9 >= 0) )
      {
        if ( *(_BYTE *)(v11 + 680) )
          goto LABEL_35;
      }
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_57;
      v14 = *(unsigned __int8 *)(v11 + 680);
      v15 = 85;
    }
    WPP_SF_Dd(*((_QWORD *)v13 + 2), v15, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, 0, v14);
    goto LABEL_64;
  }
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids);
}

```

## disassembly

```asm
0x18001bf18  push    rbp
0x18001bf1a  push    rbx
0x18001bf1b  push    rsi
0x18001bf1c  push    rdi
0x18001bf1d  push    r12
0x18001bf1f  push    r13
0x18001bf21  push    r14
0x18001bf23  push    r15
0x18001bf25  lea     rbp, [rsp-1Fh]
0x18001bf2a  sub     rsp, 0E8h
0x18001bf31  mov     r14d, r9d
0x18001bf34  mov     rsi, r8
0x18001bf37  mov     r13, rdx
0x18001bf3a  mov     rdi, rcx
0x18001bf3d  xorps   xmm0, xmm0
0x18001bf40  movups  [rbp+57h+var_A0], xmm0
0x18001bf44  xor     ecx, ecx
0x18001bf46  mov     [rbp+57h+var_C0], rcx
0x18001bf4a  mov     [rbp+57h+arg_0], rcx
0x18001bf4e  xorps   xmm1, xmm1
0x18001bf51  xor     eax, eax
0x18001bf53  movups  [rbp+57h+var_B8], xmm0
0x18001bf57  mov     [rbp+57h+var_A8], rax
0x18001bf5b  movups  [rbp+57h+var_80], xmm0
0x18001bf5f  test    rdi, rdi
0x18001bf62  jz      loc_18001C338
0x18001bf68  test    r8, r8
0x18001bf6b  jz      loc_18001C338
0x18001bf71  test    rdx, rdx
0x18001bf74  jz      loc_18001C338
0x18001bf7a  lea     rbx, [rdi+294h]
0x18001bf81  movq    r12, xmm1
0x18001bf86  psrldq  xmm1, 8
0x18001bf8b  movq    r15, xmm1
0x18001bf90  cmp     r12, [rbx]
0x18001bf93  jnz     short loc_18001BF9F
0x18001bf95  cmp     r15, [rbx+8]
0x18001bf99  jz      loc_18001C366
0x18001bf9f  test    r14d, r14d
0x18001bfa2  jz      short loc_18001BFB4
0x18001bfa4  cmp     dword ptr [rdi+2A4h], 2
0x18001bfab  jz      short loc_18001BFB4
0x18001bfad  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001bfb2  xor     ecx, ecx
0x18001bfb4  lea     rax, [rbp+57h+arg_0]
0x18001bfb8  mov     [rbp+57h+var_70], rax
0x18001bfbc  lea     rax, [rbp+57h+var_C0]
0x18001bfc0  mov     [rbp+57h+var_68], rax
0x18001bfc4  lea     rax, [rbp+57h+var_A0]
0x18001bfc8  mov     [rbp+57h+var_60], rax
0x18001bfcc  lea     rax, [rbp+57h+var_B8]
0x18001bfd0  mov     [rbp+57h+var_58], rax
0x18001bfd4  mov     [rbp+57h+var_50], 1
0x18001bfd8  mov     [rbp+57h+var_90], 100010h
0x18001bfe0  mov     [rbp+57h+var_88], rbx
0x18001bfe4  lea     rax, [rbp+57h+var_C0]
0x18001bfe8  mov     [rsp+120h+var_C8], rax
0x18001bfed  mov     [rsp+120h+var_D0], rcx
0x18001bff2  lea     rax, [rbp+57h+var_A0]
0x18001bff6  mov     [rsp+120h+var_D8], rax
0x18001bffb  lea     rax, [rbp+57h+arg_0]
0x18001bfff  mov     [rsp+120h+var_E0], rax
0x18001c004  mov     [rsp+120h+var_E8], rcx
0x18001c009  mov     [rsp+120h+var_F0], rcx
0x18001c00e  mov     [rsp+120h+var_F8], rcx
0x18001c013  mov     [rsp+120h+var_100], 20000000h
0x18001c01b  mov     r9d, 1
0x18001c021  lea     r8, [rbp+57h+var_90]
0x18001c025  mov     edx, 100h
0x18001c02a  mov     rcx, cs:?GlobalAccountDomainHandle@@3PEAXEA; void * GlobalAccountDomainHandle
0x18001c031  call    cs:__imp_SamIGetUserLogonInformation3
0x18001c037  mov     ebx, eax
0x18001c039  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink> `wil::Feature<__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink>::GetImpl(void)'::`2'::impl
0x18001c040  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink>::__private_IsEnabled(void)
0x18001c045  mov     rcx, [rbp+57h+arg_0]
0x18001c049  test    al, al
0x18001c04b  jz      loc_18001C145
0x18001c051  test    ebx, ebx
0x18001c053  js      short loc_18001C05A
0x18001c055  test    rcx, rcx
0x18001c058  jnz     short loc_18001C086
0x18001c05a  test    rcx, rcx
0x18001c05d  jz      short loc_18001C069
0x18001c05f  movzx   r8d, byte ptr [rcx+2A8h]
0x18001c067  jmp     short loc_18001C06C
0x18001c069  xor     r8d, r8d
0x18001c06c  mov     edx, ebx
0x18001c06e  lea     rcx, aKdcsvcDll; "kdcsvc.dll"
0x18001c075  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001c07a  mov     rcx, [rbp+57h+arg_0]
0x18001c07e  test    ebx, ebx
0x18001c080  js      loc_18001C107
0x18001c086  xor     ebx, ebx
0x18001c088  test    rcx, rcx
0x18001c08b  jz      short loc_18001C109
0x18001c08d  cmp     [rcx+2A8h], bl
0x18001c093  jz      short loc_18001C109
0x18001c095  cmp     r12, [rcx+2ACh]
0x18001c09c  jnz     short loc_18001C0A7
0x18001c09e  cmp     r15, [rcx+2B4h]
0x18001c0a5  jz      short loc_18001C0CB
0x18001c0a7  mov     rax, [rdi+2F0h]
0x18001c0ae  cmp     rax, [rcx+2ACh]
0x18001c0b5  jnz     short loc_18001C0CB
0x18001c0b7  mov     rax, [rdi+2F8h]
0x18001c0be  cmp     rax, [rcx+2B4h]
0x18001c0c5  jz      loc_18001C182
0x18001c0cb  lea     rax, WPP_GLOBAL_Control
0x18001c0d2  mov     r9, cs:WPP_GLOBAL_Control
0x18001c0d9  cmp     r9, rax
0x18001c0dc  jz      loc_18001C336
0x18001c0e2  test    byte ptr [r9+1Ch], 2
0x18001c0e7  jz      loc_18001C336
0x18001c0ed  mov     edx, 54h ; 'T'
0x18001c0f2  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x18001c0f9  mov     rcx, [r9+10h]
0x18001c0fd  call    WPP_SF_
0x18001c102  jmp     loc_18001C332
0x18001c107  xor     ebx, ebx
0x18001c109  lea     rax, WPP_GLOBAL_Control
0x18001c110  mov     r10, cs:WPP_GLOBAL_Control
0x18001c117  cmp     r10, rax
0x18001c11a  jz      loc_18001C336
0x18001c120  test    byte ptr [r10+1Ch], 2
0x18001c125  jz      loc_18001C336
0x18001c12b  test    rcx, rcx
0x18001c12e  jz      short loc_18001C139
0x18001c130  movzx   eax, byte ptr [rcx+2A8h]
0x18001c137  jmp     short loc_18001C13B
0x18001c139  mov     eax, ebx
0x18001c13b  mov     edx, 53h ; 'S'
0x18001c140  jmp     loc_18001C31B
0x18001c145  test    ebx, ebx
0x18001c147  js      short loc_18001C152
0x18001c149  cmp     byte ptr [rcx+2A8h], 0
0x18001c150  jnz     short loc_18001C174
0x18001c152  movzx   r8d, byte ptr [rcx+2A8h]
0x18001c15a  mov     edx, ebx
0x18001c15c  lea     rcx, aKdcsvcDll; "kdcsvc.dll"
0x18001c163  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001c168  mov     rcx, [rbp+57h+arg_0]
0x18001c16c  test    ebx, ebx
0x18001c16e  js      loc_18001C2F3
0x18001c174  xor     ebx, ebx
0x18001c176  cmp     [rcx+2A8h], bl
0x18001c17c  jz      loc_18001C2F5
0x18001c182  mov     eax, [rcx+2BCh]
0x18001c188  cmp     [rdi+2A4h], eax
0x18001c18e  jz      short loc_18001C199
0x18001c190  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001c195  mov     rcx, [rbp+57h+arg_0]
0x18001c199  test    r14d, r14d
0x18001c19c  jz      short loc_18001C1B0
0x18001c19e  cmp     dword ptr [rcx+2BCh], 2
0x18001c1a5  jz      short loc_18001C1B0
0x18001c1a7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001c1ac  mov     rcx, [rbp+57h+arg_0]
0x18001c1b0  lea     rdx, [rcx+30h]
0x18001c1b4  lea     rcx, [rbp+57h+var_B8]
0x18001c1b8  call    KerbConvertStringToPrincipalName
0x18001c1bd  mov     r9d, eax
0x18001c1c0  test    eax, eax
0x18001c1c2  jz      short loc_18001C1FF
0x18001c1c4  lea     rax, WPP_GLOBAL_Control
0x18001c1cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1d2  cmp     rcx, rax
0x18001c1d5  jz      loc_18001C2BB
0x18001c1db  test    byte ptr [rcx+1Ch], 2
0x18001c1df  jz      loc_18001C2BB
0x18001c1e5  mov     edx, 56h ; 'V'
0x18001c1ea  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x18001c1f1  mov     rcx, [rcx+10h]
0x18001c1f5  call    WPP_SF_d
0x18001c1fa  jmp     loc_18001C2BB
0x18001c1ff  lea     rdx, DomainName2
0x18001c206  lea     rcx, [rbp+57h+var_A8]
0x18001c20a  call    KerbConvertUnicodeStringToRealm
0x18001c20f  mov     r9d, eax
0x18001c212  test    eax, eax
0x18001c214  jz      short loc_18001C23E
0x18001c216  lea     rax, WPP_GLOBAL_Control
0x18001c21d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c224  cmp     rcx, rax
0x18001c227  jz      loc_18001C2BB
0x18001c22d  test    byte ptr [rcx+1Ch], 2
0x18001c231  jz      loc_18001C2BB
0x18001c237  mov     edx, 57h ; 'W'
0x18001c23c  jmp     short loc_18001C1EA
0x18001c23e  lea     r9, [rbp+57h+var_80+8]
0x18001c242  lea     r8, [rbp+57h+var_80]
0x18001c246  mov     edx, 2Eh ; '.'
0x18001c24b  lea     rcx, [rbp+57h+var_B8]
0x18001c24f  call    KerbPackData
0x18001c254  test    r14d, r14d
0x18001c257  cmovz   rsi, r13
0x18001c25b  mov     ecx, 20h ; ' '; size
0x18001c260  call    MIDL_user_allocate
0x18001c265  mov     rcx, rax
0x18001c268  test    rax, rax
0x18001c26b  jnz     short loc_18001C29D
0x18001c26d  lea     rax, WPP_GLOBAL_Control
0x18001c274  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c27b  cmp     rcx, rax
0x18001c27e  jz      short loc_18001C2BB
0x18001c280  test    byte ptr [rcx+1Ch], 2
0x18001c284  jz      short loc_18001C2BB
0x18001c286  mov     edx, 58h ; 'X'
0x18001c28b  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x18001c292  mov     rcx, [rcx+10h]
0x18001c296  call    WPP_SF_
0x18001c29b  jmp     short loc_18001C2BB
0x18001c29d  mov     dword ptr [rax+8], 0AAh
0x18001c2a4  mov     eax, dword ptr [rbp+57h+var_80]
0x18001c2a7  mov     [rcx+10h], eax
0x18001c2aa  mov     rax, qword ptr [rbp+57h+var_80+8]
0x18001c2ae  mov     [rcx+18h], rax
0x18001c2b2  mov     rax, [rsi]
0x18001c2b5  mov     [rcx], rax
0x18001c2b8  mov     [rsi], rcx
0x18001c2bb  mov     rcx, [rbp+57h+arg_0]
0x18001c2bf  call    cs:__imp_SamIFree_UserInternal6Information
0x18001c2c5  lea     rcx, [rbp+57h+var_C0]
0x18001c2c9  call    cs:__imp_SamrCloseHandle
0x18001c2cf  lea     rcx, [rbp+57h+var_A0]
0x18001c2d3  call    cs:__imp_SamIFreeSidAndAttributesList
0x18001c2d9  cmp     qword ptr [rbp+57h+var_B8+8], rbx
0x18001c2dd  jz      short loc_18001C2E8
0x18001c2df  lea     rcx, [rbp+57h+var_B8]
0x18001c2e3  call    KerbFreePrincipalName
0x18001c2e8  lea     rcx, [rbp+57h+var_A8]
0x18001c2ec  call    KerbFreeRealm
0x18001c2f1  jmp     short loc_18001C366
0x18001c2f3  xor     ebx, ebx
0x18001c2f5  lea     rax, WPP_GLOBAL_Control
0x18001c2fc  mov     r10, cs:WPP_GLOBAL_Control
0x18001c303  cmp     r10, rax
0x18001c306  jz      short loc_18001C336
0x18001c308  test    byte ptr [r10+1Ch], 2
0x18001c30d  jz      short loc_18001C336
0x18001c30f  movzx   eax, byte ptr [rcx+2A8h]
0x18001c316  mov     edx, 55h ; 'U'
0x18001c31b  mov     [rsp+120h+var_100], eax
0x18001c31f  xor     r9d, r9d
0x18001c322  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x18001c329  mov     rcx, [r10+10h]
0x18001c32d  call    WPP_SF_Dd
0x18001c332  mov     rcx, [rbp+57h+arg_0]
0x18001c336  jmp     short loc_18001C2BF
0x18001c338  lea     rax, WPP_GLOBAL_Control
0x18001c33f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c346  cmp     rcx, rax
0x18001c349  jz      short loc_18001C366
0x18001c34b  test    byte ptr [rcx+1Ch], 2
0x18001c34f  jz      short loc_18001C366
0x18001c351  mov     edx, 52h ; 'R'
0x18001c356  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x18001c35d  mov     rcx, [rcx+10h]
0x18001c361  call    WPP_SF_
0x18001c366  add     rsp, 0E8h
0x18001c36d  pop     r15
0x18001c36f  pop     r14
0x18001c371  pop     r13
0x18001c373  pop     r12
0x18001c375  pop     rdi
0x18001c376  pop     rsi
0x18001c377  pop     rbx
0x18001c378  pop     rbp
0x18001c379  retn
```
