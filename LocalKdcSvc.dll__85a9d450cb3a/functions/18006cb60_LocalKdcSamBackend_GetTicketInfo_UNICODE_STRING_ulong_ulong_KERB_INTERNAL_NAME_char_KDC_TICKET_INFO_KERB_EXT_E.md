# LocalKdcSamBackend::GetTicketInfo(_UNICODE_STRING *,ulong,ulong,_KERB_INTERNAL_NAME *,char * *,_KDC_TICKET_INFO *,KERB_EXT_ERROR *,void * *,ulong,ulong,_USER_INTERNAL6_INFORMATION * *,_SID_AND_ATTRIBUTES_LIST *,_SAM_MAPPED_ATTRIBUTE_SET *)

- ea: `0x18006cb60`
- end: `0x18006cdd2`
- name: `?GetTicketInfo@LocalKdcSamBackend@@UEAAJPEAU_UNICODE_STRING@@KKPEAU_KERB_INTERNAL_NAME@@PEAPEADPEAU_KDC_TICKET_INFO@@PEAUKERB_EXT_ERROR@@PEAPEAXKKPEAPEAU_USER_INTERNAL6_INFORMATION@@PEAU_SID_AND_ATTRIBUTES_LIST@@PEAU_SAM_MAPPED_ATTRIBUTE_SET@@@Z`
- size: `626`
- prototype: `__int64 __fastcall(LocalKdcSamBackend *this, struct _UNICODE_STRING *, unsigned int, int, struct _KERB_INTERNAL_NAME *, char **, struct _KDC_TICKET_INFO *, struct KERB_EXT_ERROR *, void **, unsigned int, unsigned int, struct _USER_INTERNAL6_INFORMATION **, struct _SID_AND_ATTRIBUTES_LIST *, struct _SAM_MAPPED_ATTRIBUTE_SET *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005cc0`
- `0x1800101c4`
- `0x180060c24`
- `0x18006c8c8`
- `0x18006ca80`
- `0x18006cb60`
- `0x18006cf80`
- `0x180073f50`
- `0x18007bef4`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18006cba5`
- `ntdll!RtlEqualUnicodeString` at `0x18006cba5`

## pseudocode

```c
__int64 __fastcall LocalKdcSamBackend::GetTicketInfo(
        LocalKdcSamBackend *this,
        struct _UNICODE_STRING *a2,
        unsigned int a3,
        int a4,
        struct _KERB_INTERNAL_NAME *a5,
        char **a6,
        struct _KDC_TICKET_INFO *a7,
        struct KERB_EXT_ERROR *a8,
        void **a9,
        unsigned int a10,
        unsigned int a11,
        struct _USER_INTERNAL6_INFORMATION **a12,
        struct _SID_AND_ATTRIBUTES_LIST *a13,
        struct _SAM_MAPPED_ATTRIBUTE_SET *a14)
{
  Ntlmless::IaKerb *v18; // rcx
  struct KERB_EXT_ERROR *v19; // r9
  unsigned int Krbtgt; // eax
  unsigned int v21; // r10d
  struct _UNICODE_STRING *v22; // rdx
  CSecurityData *v23; // rcx
  __int64 v24; // rdx
  unsigned int v26; // [rsp+70h] [rbp-29h] BYREF
  struct _UNICODE_STRING v27; // [rsp+78h] [rbp-21h] BYREF
  int *v28; // [rsp+88h] [rbp-11h]
  struct KERB_EXT_ERROR **v29; // [rsp+90h] [rbp-9h]
  char v30; // [rsp+98h] [rbp-1h]

  v26 = 0;
  v28 = (int *)&v26;
  v29 = &a8;
  v30 = 1;
  if ( RtlEqualUnicodeString(&String2, a2, 1u) )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_77f473c84dd832facaeecb8a8c59142b_Traceguids);
    Krbtgt = LocalKdcSamBackend::GetKrbtgt(this, a7, a9, a12, a13);
    goto LABEL_30;
  }
  if ( !a5 )
  {
    if ( a2 && (a3 & 0x40) != 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_19;
      v24 = 24;
    }
    else
    {
      if ( !Ntlmless::IaKerb::IsEnabled(v18) || !a2 || !LocalKdcSamBackend::IsMachinePrincipal(this, a2) )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_77f473c84dd832facaeecb8a8c59142b_Traceguids);
        }
        Krbtgt = KdcGetTicketInfoFull(a2, a3, a4 | 0x10u, 0, a6, a7, a8, a9, a10, a11, a12, a13, a14);
        goto LABEL_30;
      }
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_19;
      v24 = 25;
    }
    WPP_SF_(*((_QWORD *)v23 + 2), v24, WPP_77f473c84dd832facaeecb8a8c59142b_Traceguids);
LABEL_19:
    v22 = a2;
    goto LABEL_12;
  }
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_77f473c84dd832facaeecb8a8c59142b_Traceguids);
  v27 = 0;
  v21 = KerbConvertKdcNameToString(&v27, a5, &stru_1800B2D60);
  v26 = v21;
  if ( !v21 )
  {
    v22 = &v27;
LABEL_12:
    Krbtgt = LocalKdcSamBackend::GetMachineTicketInfo(this, v22, a7, v19, a12);
LABEL_30:
    v21 = Krbtgt;
  }
  if ( a8 )
    FillExtendedError(-2147483640, 1, 0, 0, a8);
  return v21;
}

```

## disassembly

```asm
0x18006cb60  push    rbp
0x18006cb62  push    rbx
0x18006cb63  push    rdi
0x18006cb64  push    r14
0x18006cb66  push    r15
0x18006cb68  lea     rbp, [rsp-7]
0x18006cb6d  sub     rsp, 0A0h
0x18006cb74  mov     r15d, r9d
0x18006cb77  mov     r14d, r8d
0x18006cb7a  mov     rbx, rdx
0x18006cb7d  mov     rdi, rcx
0x18006cb80  mov     [rbp+27h+var_50], 0
0x18006cb87  lea     rax, [rbp+27h+var_50]
0x18006cb8b  mov     [rbp+27h+var_38], rax
0x18006cb8f  lea     rax, [rbp+27h+arg_38]
0x18006cb93  mov     [rbp+27h+var_30], rax
0x18006cb97  mov     [rbp+27h+var_28], 1
0x18006cb9b  mov     r8b, 1; CaseInsensitive
0x18006cb9e  lea     rcx, String2; String1
0x18006cba5  call    cs:__imp_RtlEqualUnicodeString
0x18006cbab  test    al, al
0x18006cbad  jz      short loc_18006CC05
0x18006cbaf  lea     rax, WPP_GLOBAL_Control
0x18006cbb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cbbd  cmp     rcx, rax
0x18006cbc0  jz      short loc_18006CBDD
0x18006cbc2  test    byte ptr [rcx+1Ch], 4
0x18006cbc6  jz      short loc_18006CBDD
0x18006cbc8  mov     edx, 16h
0x18006cbcd  lea     r8, WPP_77f473c84dd832facaeecb8a8c59142b_Traceguids
0x18006cbd4  mov     rcx, [rcx+10h]
0x18006cbd8  call    WPP_SF_
0x18006cbdd  mov     rax, [rbp+27h+arg_60]
0x18006cbe4  mov     [rsp+0C0h+var_A0], rax; struct _SID_AND_ATTRIBUTES_LIST *
0x18006cbe9  mov     r9, [rbp+27h+arg_58]; struct _USER_INTERNAL6_INFORMATION **
0x18006cbf0  mov     r8, [rbp+27h+arg_40]; void **
0x18006cbf4  mov     rdx, [rbp+27h+arg_30]; struct _KDC_TICKET_INFO *
0x18006cbf8  mov     rcx, rdi; this
0x18006cbfb  call    ?GetKrbtgt@LocalKdcSamBackend@@AEAAJPEAU_KDC_TICKET_INFO@@PEAPEAXPEAPEAU_USER_INTERNAL6_INFORMATION@@PEAU_SID_AND_ATTRIBUTES_LIST@@@Z; LocalKdcSamBackend::GetKrbtgt(_KDC_TICKET_INFO *,void * *,_USER_INTERNAL6_INFORMATION * *,_SID_AND_ATTRIBUTES_LIST *)
0x18006cc00  jmp     loc_18006CD9B
0x18006cc05  cmp     [rbp+27h+arg_20], 0
0x18006cc0a  jz      short loc_18006CC84
0x18006cc0c  lea     rax, WPP_GLOBAL_Control
0x18006cc13  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cc1a  cmp     rcx, rax
0x18006cc1d  jz      short loc_18006CC3A
0x18006cc1f  test    byte ptr [rcx+1Ch], 4
0x18006cc23  jz      short loc_18006CC3A
0x18006cc25  mov     edx, 17h
0x18006cc2a  lea     r8, WPP_77f473c84dd832facaeecb8a8c59142b_Traceguids
0x18006cc31  mov     rcx, [rcx+10h]
0x18006cc35  call    WPP_SF_
0x18006cc3a  xorps   xmm0, xmm0
0x18006cc3d  movups  xmmword ptr [rbp+27h+var_48.Length], xmm0
0x18006cc41  lea     r8, stru_1800B2D60; struct _UNICODE_STRING *
0x18006cc48  mov     rdx, [rbp+27h+arg_20]; struct _KERB_INTERNAL_NAME *
0x18006cc4c  lea     rcx, [rbp+27h+var_48]; struct _UNICODE_STRING *
0x18006cc50  call    ?KerbConvertKdcNameToString@@YAJPEAU_UNICODE_STRING@@PEAU_KERB_INTERNAL_NAME@@0@Z; KerbConvertKdcNameToString(_UNICODE_STRING *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *)
0x18006cc55  mov     r10d, eax
0x18006cc58  mov     [rbp+27h+var_50], eax
0x18006cc5b  test    eax, eax
0x18006cc5d  jnz     loc_18006CD9E
0x18006cc63  lea     rdx, [rbp+27h+var_48]; struct _UNICODE_STRING *
0x18006cc67  mov     rax, [rbp+27h+arg_58]
0x18006cc6e  mov     r8, [rbp+27h+arg_30]; struct _KDC_TICKET_INFO *
0x18006cc72  mov     [rsp+0C0h+var_A0], rax; struct _USER_INTERNAL6_INFORMATION **
0x18006cc77  mov     rcx, rdi; this
0x18006cc7a  call    ?GetMachineTicketInfo@LocalKdcSamBackend@@AEAAJPEAU_UNICODE_STRING@@PEAU_KDC_TICKET_INFO@@PEAUKERB_EXT_ERROR@@PEAPEAU_USER_INTERNAL6_INFORMATION@@@Z; LocalKdcSamBackend::GetMachineTicketInfo(_UNICODE_STRING *,_KDC_TICKET_INFO *,KERB_EXT_ERROR *,_USER_INTERNAL6_INFORMATION * *)
0x18006cc7f  jmp     loc_18006CD9B
0x18006cc84  test    rbx, rbx
0x18006cc87  jz      short loc_18006CCC2
0x18006cc89  test    r14b, 40h
0x18006cc8d  jz      short loc_18006CCC2
0x18006cc8f  lea     rax, WPP_GLOBAL_Control
0x18006cc96  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cc9d  cmp     rcx, rax
0x18006cca0  jz      short loc_18006CCBD
0x18006cca2  test    byte ptr [rcx+1Ch], 4
0x18006cca6  jz      short loc_18006CCBD
0x18006cca8  mov     edx, 18h
0x18006ccad  lea     r8, WPP_77f473c84dd832facaeecb8a8c59142b_Traceguids
0x18006ccb4  mov     rcx, [rcx+10h]
0x18006ccb8  call    WPP_SF_
0x18006ccbd  mov     rdx, rbx
0x18006ccc0  jmp     short loc_18006CC67
0x18006ccc2  call    ?IsEnabled@IaKerb@Ntlmless@@YA_NXZ; Ntlmless::IaKerb::IsEnabled(void)
0x18006ccc7  test    al, al
0x18006ccc9  jz      short loc_18006CCFF
0x18006cccb  test    rbx, rbx
0x18006ccce  jz      short loc_18006CCFF
0x18006ccd0  mov     rdx, rbx; struct _UNICODE_STRING *
0x18006ccd3  mov     rcx, rdi; this
0x18006ccd6  call    ?IsMachinePrincipal@LocalKdcSamBackend@@AEAA_NPEAU_UNICODE_STRING@@@Z; LocalKdcSamBackend::IsMachinePrincipal(_UNICODE_STRING *)
0x18006ccdb  test    al, al
0x18006ccdd  jz      short loc_18006CCFF
0x18006ccdf  lea     rax, WPP_GLOBAL_Control
0x18006cce6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cced  cmp     rcx, rax
0x18006ccf0  jz      short loc_18006CCBD
0x18006ccf2  test    byte ptr [rcx+1Ch], 4
0x18006ccf6  jz      short loc_18006CCBD
0x18006ccf8  mov     edx, 19h
0x18006ccfd  jmp     short loc_18006CCAD
0x18006ccff  lea     rax, WPP_GLOBAL_Control
0x18006cd06  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cd0d  cmp     rcx, rax
0x18006cd10  jz      short loc_18006CD2D
0x18006cd12  test    byte ptr [rcx+1Ch], 4
0x18006cd16  jz      short loc_18006CD2D
0x18006cd18  mov     edx, 1Ah
0x18006cd1d  lea     r8, WPP_77f473c84dd832facaeecb8a8c59142b_Traceguids
0x18006cd24  mov     rcx, [rcx+10h]
0x18006cd28  call    WPP_SF_
0x18006cd2d  or      r15d, 10h
0x18006cd31  mov     rax, [rbp+27h+arg_68]
0x18006cd38  mov     [rsp+0C0h+var_60], rax; struct _SAM_MAPPED_ATTRIBUTE_SET *
0x18006cd3d  mov     rax, [rbp+27h+arg_60]
0x18006cd44  mov     [rsp+0C0h+var_68], rax; struct _SID_AND_ATTRIBUTES_LIST *
0x18006cd49  mov     rax, [rbp+27h+arg_58]
0x18006cd50  mov     [rsp+0C0h+var_70], rax; struct _USER_INTERNAL6_INFORMATION **
0x18006cd55  mov     eax, [rbp+27h+arg_50]
0x18006cd5b  mov     [rsp+0C0h+var_78], eax; unsigned int
0x18006cd5f  mov     eax, [rbp+27h+arg_48]
0x18006cd62  mov     [rsp+0C0h+var_80], eax; unsigned int
0x18006cd66  mov     rax, [rbp+27h+arg_40]
0x18006cd6a  mov     [rsp+0C0h+var_88], rax; void **
0x18006cd6f  mov     rax, [rbp+27h+arg_38]
0x18006cd73  mov     [rsp+0C0h+var_90], rax; struct KERB_EXT_ERROR *
0x18006cd78  mov     rax, [rbp+27h+arg_30]
0x18006cd7c  mov     [rsp+0C0h+var_98], rax; struct _KDC_TICKET_INFO *
0x18006cd81  mov     rax, [rbp+27h+arg_28]
0x18006cd85  mov     [rsp+0C0h+var_A0], rax; char **
0x18006cd8a  xor     r9d, r9d; struct _KERB_INTERNAL_NAME *
0x18006cd8d  mov     r8d, r15d; unsigned int
0x18006cd90  mov     edx, r14d; unsigned int
0x18006cd93  mov     rcx, rbx; struct _UNICODE_STRING *
0x18006cd96  call    ?KdcGetTicketInfoFull@@YAJPEAU_UNICODE_STRING@@KKPEAU_KERB_INTERNAL_NAME@@PEAPEADPEAU_KDC_TICKET_INFO@@PEAUKERB_EXT_ERROR@@PEAPEAXKKPEAPEAU_USER_INTERNAL6_INFORMATION@@PEAU_SID_AND_ATTRIBUTES_LIST@@PEAU_SAM_MAPPED_ATTRIBUTE_SET@@@Z; KdcGetTicketInfoFull(_UNICODE_STRING *,ulong,ulong,_KERB_INTERNAL_NAME *,char * *,_KDC_TICKET_INFO *,KERB_EXT_ERROR *,void * *,ulong,ulong,_USER_INTERNAL6_INFORMATION * *,_SID_AND_ATTRIBUTES_LIST *,_SAM_MAPPED_ATTRIBUTE_SET *)
0x18006cd9b  mov     r10d, eax
0x18006cd9e  mov     rax, [rbp+27h+arg_38]
0x18006cda2  test    rax, rax
0x18006cda5  jz      short loc_18006CDC0
0x18006cda7  mov     [rsp+0C0h+var_A0], rax; struct KERB_EXT_ERROR *
0x18006cdac  xor     r9d, r9d; unsigned int
0x18006cdaf  xor     r8d, r8d; unsigned int
0x18006cdb2  lea     edx, [r9+1]; unsigned int
0x18006cdb6  mov     ecx, 80000008h; int
0x18006cdbb  call    ?FillExtendedError@@YAXJKKKPEAUKERB_EXT_ERROR@@@Z; FillExtendedError(long,ulong,ulong,ulong,KERB_EXT_ERROR *)
0x18006cdc0  mov     eax, r10d
0x18006cdc3  add     rsp, 0A0h
0x18006cdca  pop     r15
0x18006cdcc  pop     r14
0x18006cdce  pop     rdi
0x18006cdcf  pop     rbx
0x18006cdd0  pop     rbp
0x18006cdd1  retn
```
