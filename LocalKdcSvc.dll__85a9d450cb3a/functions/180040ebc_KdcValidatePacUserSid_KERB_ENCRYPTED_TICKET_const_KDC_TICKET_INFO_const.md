# KdcValidatePacUserSid(KERB_ENCRYPTED_TICKET const &,_KDC_TICKET_INFO const &)

- ea: `0x180040ebc`
- end: `0x1800412a2`
- name: `?KdcValidatePacUserSid@@YAJAEBUKERB_ENCRYPTED_TICKET@@AEBU_KDC_TICKET_INFO@@@Z`
- size: `998`
- prototype: `__int64 __fastcall(const struct KERB_ENCRYPTED_TICKET *, const struct _KDC_TICKET_INFO *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800412e0`

## callees

- `0x180002ad0`
- `0x1800038f0`
- `0x180003908`
- `0x18001cdc4`
- `0x18001ff94`
- `0x18002005c`
- `0x180040ebc`
- `0x18005a060`
- `0x18005a090`
- `0x18006fc78`
- `0x1800705a0`
- `0x180070f30`
- `0x1800710d8`
- `0x18007f5c4`
- `0x18007f69c`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18004111f`
- `ntdll!RtlEqualSid` at `0x18004111f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall KdcValidatePacUserSid(const struct KERB_ENCRYPTED_TICKET *a1, ULONG *a2)
{
  __int64 v4; // rdx
  int PacFromAuthData; // eax
  struct _PACTYPE *v6; // rbx
  struct _PAC_INFO_BUFFER *v7; // r8
  struct _PAC_INFO_BUFFER *v8; // rax
  struct _PAC_INFO_BUFFER *v9; // rbx
  unsigned __int8 *v10; // rax
  unsigned __int8 *v11; // rdi
  int v12; // eax
  struct _NETLOGON_VALIDATION_SAM_INFO3 *v13; // rbx
  void *DomainRelativeSid; // r14
  __int64 v16; // [rsp+30h] [rbp-69h] BYREF
  __int64 v17; // [rsp+38h] [rbp-61h] BYREF
  struct _NETLOGON_VALIDATION_SAM_INFO3 *v18; // [rsp+40h] [rbp-59h] BYREF
  unsigned __int8 *v19; // [rsp+48h] [rbp-51h]
  __int64 v20; // [rsp+50h] [rbp-49h]
  __int64 v21; // [rsp+58h] [rbp-41h]
  __int64 *v22; // [rsp+60h] [rbp-39h]
  char v23; // [rsp+68h] [rbp-31h]
  _BYTE Sid2[80]; // [rsp+70h] [rbp-29h] BYREF

  memset_0(Sid2, 0, 0x48u);
  v4 = 0;
  v16 = 0;
  v22 = &v16;
  v23 = 1;
  v20 = 0;
  v19 = 0;
  v21 = 0;
  if ( (*(_BYTE *)a1 & 0x10) == 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_72c574dd392638b0f9c59822794ca294_Traceguids, a2);
      v4 = v16;
    }
    goto LABEL_51;
  }
  v17 = 0;
  PacFromAuthData = KerbGetPacFromAuthData(*((_QWORD *)a1 + 20), &v16, 0, &v17);
  if ( PacFromAuthData || !v17 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_72c574dd392638b0f9c59822794ca294_Traceguids,
        (_DWORD)a2,
        PacFromAuthData);
    goto LABEL_50;
  }
  v6 = *(struct _PACTYPE **)(v17 + 24);
  if ( !PAC_UnMarshal(v6, *(_DWORD *)(v17 + 16)) )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_72c574dd392638b0f9c59822794ca294_Traceguids, a2);
LABEL_50:
    v4 = v16;
LABEL_51:
    if ( v4 )
      KerbFreeData(1, v4);
    return 60;
  }
  v8 = PAC_Find(v6, 1u, v7);
  v9 = v8;
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_72c574dd392638b0f9c59822794ca294_Traceguids, a2);
    goto LABEL_50;
  }
  v10 = (unsigned __int8 *)MIDL_user_allocate(*((unsigned int *)v8 + 1));
  v11 = v10;
  v19 = v10;
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_72c574dd392638b0f9c59822794ca294_Traceguids, a2);
    goto LABEL_50;
  }
  memcpy_0(v10, *((const void **)v9 + 1), *((unsigned int *)v9 + 1));
  v18 = 0;
  v12 = PAC_UnmarshallValidationInfo(&v18, v11, *((_DWORD *)v9 + 1));
  v13 = v18;
  if ( v12 < 0 || !v18 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)WPP_72c574dd392638b0f9c59822794ca294_Traceguids,
        (_DWORD)a2,
        v12);
    MIDL_user_free(v11);
    if ( v13 )
      MIDL_user_free(v13);
    goto LABEL_50;
  }
  DomainRelativeSid = PAC_MakeDomainRelativeSid(*((PSID *)v18 + 28), *((_DWORD *)v18 + 37));
  if ( !DomainRelativeSid )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_72c574dd392638b0f9c59822794ca294_Traceguids, a2);
    MIDL_user_free(v11);
    MIDL_user_free(v13);
    goto LABEL_50;
  }
  KdcMakeAccountSid(Sid2, a2[12]);
  if ( !RtlEqualSid(DomainRelativeSid, Sid2) )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_72c574dd392638b0f9c59822794ca294_Traceguids, a2);
    MIDL_user_free(DomainRelativeSid);
    MIDL_user_free(v11);
    MIDL_user_free(v13);
    goto LABEL_50;
  }
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_72c574dd392638b0f9c59822794ca294_Traceguids, a2);
  MIDL_user_free(DomainRelativeSid);
  MIDL_user_free(v11);
  MIDL_user_free(v13);
  if ( v16 )
    KerbFreeData(1, v16);
  return 0;
}

```

## disassembly

```asm
0x180040ebc  mov     [rsp-8+arg_10], rbx
0x180040ec1  push    rbp
0x180040ec2  push    rsi
0x180040ec3  push    rdi
0x180040ec4  push    r12
0x180040ec6  push    r14
0x180040ec8  lea     rbp, [rsp-37h]
0x180040ecd  sub     rsp, 0D0h
0x180040ed4  mov     rax, cs:__security_cookie
0x180040edb  xor     rax, rsp
0x180040ede  mov     [rbp+57h+var_30], rax
0x180040ee2  mov     rsi, rdx
0x180040ee5  mov     rbx, rcx
0x180040ee8  xor     edx, edx; Val
0x180040eea  lea     r8d, [rdx+48h]; Size
0x180040eee  lea     rcx, [rbp+57h+Sid2]; void *
0x180040ef2  call    memset_0
0x180040ef7  xor     edx, edx
0x180040ef9  mov     [rbp+57h+var_C0], rdx
0x180040efd  lea     rax, [rbp+57h+var_C0]
0x180040f01  mov     [rbp+57h+var_90], rax
0x180040f05  lea     r12d, [rdx+1]
0x180040f09  mov     [rbp+57h+var_88], r12b
0x180040f0d  mov     [rbp+57h+var_A0], rdx
0x180040f11  mov     [rbp+57h+var_A8], rdx
0x180040f15  mov     [rbp+57h+var_98], rdx
0x180040f19  test    byte ptr [rbx], 10h
0x180040f1c  jnz     short loc_180040F58
0x180040f1e  lea     rax, WPP_GLOBAL_Control
0x180040f25  mov     rcx, cs:WPP_GLOBAL_Control
0x180040f2c  cmp     rcx, rax
0x180040f2f  jz      short loc_180040F53
0x180040f31  test    [rcx+1Ch], r12b
0x180040f35  jz      short loc_180040F53
0x180040f37  lea     edx, [r12+0Ch]
0x180040f3c  mov     r9, rsi
0x180040f3f  lea     r8, WPP_72c574dd392638b0f9c59822794ca294_Traceguids
0x180040f46  mov     rcx, [rcx+10h]
0x180040f4a  call    WPP_SF_Z
0x180040f4f  mov     rdx, [rbp+57h+var_C0]
0x180040f53  jmp     loc_18004126C
0x180040f58  mov     [rbp+57h+var_B8], 0
0x180040f60  lea     r9, [rbp+57h+var_B8]
0x180040f64  xor     r8d, r8d
0x180040f67  lea     rdx, [rbp+57h+var_C0]
0x180040f6b  mov     rcx, [rbx+0A0h]
0x180040f72  call    KerbGetPacFromAuthData
0x180040f77  mov     r8d, eax
0x180040f7a  test    eax, eax
0x180040f7c  jnz     loc_180041231
0x180040f82  mov     rdx, [rbp+57h+var_B8]
0x180040f86  test    rdx, rdx
0x180040f89  jz      loc_180041231
0x180040f8f  mov     rbx, [rdx+18h]
0x180040f93  mov     edx, [rdx+10h]; unsigned int
0x180040f96  mov     rcx, rbx; struct _PACTYPE *
0x180040f99  call    ?PAC_UnMarshal@@YAKPEAU_PACTYPE@@K@Z; PAC_UnMarshal(_PACTYPE *,ulong)
0x180040f9e  test    eax, eax
0x180040fa0  jnz     short loc_180040FD9
0x180040fa2  lea     rax, WPP_GLOBAL_Control
0x180040fa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180040fb0  cmp     rcx, rax
0x180040fb3  jz      short loc_180040FD4
0x180040fb5  test    [rcx+1Ch], r12b
0x180040fb9  jz      short loc_180040FD4
0x180040fbb  mov     edx, 0Fh
0x180040fc0  mov     r9, rsi
0x180040fc3  lea     r8, WPP_72c574dd392638b0f9c59822794ca294_Traceguids
0x180040fca  mov     rcx, [rcx+10h]
0x180040fce  call    WPP_SF_Z
0x180040fd3  nop
0x180040fd4  jmp     loc_180041268
0x180040fd9  mov     edx, r12d; unsigned int
0x180040fdc  mov     rcx, rbx; struct _PACTYPE *
0x180040fdf  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x180040fe4  mov     rbx, rax
0x180040fe7  test    rax, rax
0x180040fea  jnz     short loc_180041021
0x180040fec  lea     rax, WPP_GLOBAL_Control
0x180040ff3  mov     rcx, cs:WPP_GLOBAL_Control
0x180040ffa  cmp     rcx, rax
0x180040ffd  jz      short loc_18004101C
0x180040fff  test    [rcx+1Ch], r12b
0x180041003  jz      short loc_18004101C
0x180041005  lea     edx, [rbx+10h]
0x180041008  mov     r9, rsi
0x18004100b  lea     r8, WPP_72c574dd392638b0f9c59822794ca294_Traceguids
0x180041012  mov     rcx, [rcx+10h]
0x180041016  call    WPP_SF_Z
0x18004101b  nop
0x18004101c  jmp     loc_180041268
0x180041021  mov     ecx, [rax+4]; size
0x180041024  call    MIDL_user_allocate
0x180041029  mov     rdi, rax
0x18004102c  mov     [rbp+57h+var_A8], rax
0x180041030  test    rax, rax
0x180041033  jnz     short loc_18004106A
0x180041035  lea     rax, WPP_GLOBAL_Control
0x18004103c  mov     rcx, cs:WPP_GLOBAL_Control
0x180041043  cmp     rcx, rax
0x180041046  jz      short loc_180041065
0x180041048  test    [rcx+1Ch], r12b
0x18004104c  jz      short loc_180041065
0x18004104e  lea     edx, [rdi+11h]
0x180041051  mov     r9, rsi
0x180041054  lea     r8, WPP_72c574dd392638b0f9c59822794ca294_Traceguids
0x18004105b  mov     rcx, [rcx+10h]
0x18004105f  call    WPP_SF_Z
0x180041064  nop
0x180041065  jmp     loc_180041268
0x18004106a  mov     r8d, [rbx+4]; Size
0x18004106e  mov     rdx, [rbx+8]; Src
0x180041072  mov     rcx, rdi; void *
0x180041075  call    memcpy_0
0x18004107a  mov     [rbp+57h+var_B0], 0
0x180041082  mov     r8d, [rbx+4]; unsigned int
0x180041086  mov     rdx, rdi; unsigned __int8 *
0x180041089  lea     rcx, [rbp+57h+var_B0]; struct _NETLOGON_VALIDATION_SAM_INFO3 **
0x18004108d  call    ?PAC_UnmarshallValidationInfo@@YAJPEAPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAEK@Z; PAC_UnmarshallValidationInfo(_NETLOGON_VALIDATION_SAM_INFO3 * *,uchar *,ulong)
0x180041092  mov     r8d, eax
0x180041095  mov     rbx, [rbp+57h+var_B0]
0x180041099  test    eax, eax
0x18004109b  js      loc_1800411E1
0x1800410a1  test    rbx, rbx
0x1800410a4  jz      loc_1800411E1
0x1800410aa  mov     edx, [rbx+94h]; unsigned int
0x1800410b0  mov     rcx, [rbx+0E0h]; SourceSid
0x1800410b7  call    ?PAC_MakeDomainRelativeSid@@YAPEAXPEAXK@Z; PAC_MakeDomainRelativeSid(void *,ulong)
0x1800410bc  mov     r14, rax
0x1800410bf  test    rax, rax
0x1800410c2  jnz     short loc_18004110C
0x1800410c4  lea     rax, WPP_GLOBAL_Control
0x1800410cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800410d2  cmp     rcx, rax
0x1800410d5  jz      short loc_1800410F5
0x1800410d7  test    [rcx+1Ch], r12b
0x1800410db  jz      short loc_1800410F5
0x1800410dd  lea     edx, [r14+13h]
0x1800410e1  mov     r9, rsi
0x1800410e4  lea     r8, WPP_72c574dd392638b0f9c59822794ca294_Traceguids
0x1800410eb  mov     rcx, [rcx+10h]
0x1800410ef  call    WPP_SF_Z
0x1800410f4  nop
0x1800410f5  mov     rcx, rdi; void *
0x1800410f8  call    MIDL_user_free
0x1800410fd  nop
0x1800410fe  mov     rcx, rbx; void *
0x180041101  call    MIDL_user_free
0x180041106  nop
0x180041107  jmp     loc_180041268
0x18004110c  mov     edx, [rsi+30h]; unsigned int
0x18004110f  lea     rcx, [rbp+57h+Sid2]; Sid
0x180041113  call    ?KdcMakeAccountSid@@YAXPEAXK@Z; KdcMakeAccountSid(void *,ulong)
0x180041118  lea     rdx, [rbp+57h+Sid2]; Sid2
0x18004111c  mov     rcx, r14; Sid1
0x18004111f  call    cs:__imp_RtlEqualSid
0x180041125  test    al, al
0x180041127  jnz     short loc_18004117B
0x180041129  lea     rax, WPP_GLOBAL_Control
0x180041130  mov     rcx, cs:WPP_GLOBAL_Control
0x180041137  cmp     rcx, rax
0x18004113a  jz      short loc_18004115B
0x18004113c  test    [rcx+1Ch], r12b
0x180041140  jz      short loc_18004115B
0x180041142  mov     edx, 14h
0x180041147  mov     r9, rsi
0x18004114a  lea     r8, WPP_72c574dd392638b0f9c59822794ca294_Traceguids
0x180041151  mov     rcx, [rcx+10h]
0x180041155  call    WPP_SF_Z
0x18004115a  nop
0x18004115b  mov     rcx, r14; void *
0x18004115e  call    MIDL_user_free
0x180041163  nop
0x180041164  mov     rcx, rdi; void *
0x180041167  call    MIDL_user_free
0x18004116c  nop
0x18004116d  mov     rcx, rbx; void *
0x180041170  call    MIDL_user_free
0x180041175  nop
0x180041176  jmp     loc_180041268
0x18004117b  lea     rax, WPP_GLOBAL_Control
0x180041182  mov     rcx, cs:WPP_GLOBAL_Control
0x180041189  cmp     rcx, rax
0x18004118c  jz      short loc_1800411AD
0x18004118e  test    byte ptr [rcx+1Ch], 4
0x180041192  jz      short loc_1800411AD
0x180041194  mov     edx, 15h
0x180041199  mov     r9, rsi
0x18004119c  lea     r8, WPP_72c574dd392638b0f9c59822794ca294_Traceguids
0x1800411a3  mov     rcx, [rcx+10h]
0x1800411a7  call    WPP_SF_Z
0x1800411ac  nop
0x1800411ad  mov     rcx, r14; void *
0x1800411b0  call    MIDL_user_free
0x1800411b5  nop
0x1800411b6  mov     rcx, rdi; void *
0x1800411b9  call    MIDL_user_free
0x1800411be  nop
0x1800411bf  mov     rcx, rbx; void *
0x1800411c2  call    MIDL_user_free
0x1800411c7  nop
0x1800411c8  mov     rdx, [rbp+57h+var_C0]
0x1800411cc  test    rdx, rdx
0x1800411cf  jz      short loc_1800411DA
0x1800411d1  mov     ecx, r12d
0x1800411d4  call    KerbFreeData
0x1800411d9  nop
0x1800411da  xor     eax, eax
0x1800411dc  jmp     loc_18004127F
0x1800411e1  lea     rax, WPP_GLOBAL_Control
0x1800411e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800411ef  cmp     rcx, rax
0x1800411f2  jz      short loc_180041218
0x1800411f4  test    [rcx+1Ch], r12b
0x1800411f8  jz      short loc_180041218
0x1800411fa  mov     edx, 12h
0x1800411ff  mov     [rsp+0F0h+var_D0], r8d
0x180041204  mov     r9, rsi
0x180041207  lea     r8, WPP_72c574dd392638b0f9c59822794ca294_Traceguids
0x18004120e  mov     rcx, [rcx+10h]
0x180041212  call    WPP_SF_Zd
0x180041217  nop
0x180041218  mov     rcx, rdi; void *
0x18004121b  call    MIDL_user_free
0x180041220  nop
0x180041221  test    rbx, rbx
0x180041224  jz      short loc_18004122F
0x180041226  mov     rcx, rbx; void *
0x180041229  call    MIDL_user_free
0x18004122e  nop
0x18004122f  jmp     short loc_180041268
0x180041231  lea     rax, WPP_GLOBAL_Control
0x180041238  mov     rcx, cs:WPP_GLOBAL_Control
0x18004123f  cmp     rcx, rax
0x180041242  jz      short loc_180041268
0x180041244  test    [rcx+1Ch], r12b
0x180041248  jz      short loc_180041268
0x18004124a  mov     edx, 0Eh
0x18004124f  mov     [rsp+0F0h+var_D0], r8d
0x180041254  mov     r9, rsi
0x180041257  lea     r8, WPP_72c574dd392638b0f9c59822794ca294_Traceguids
0x18004125e  mov     rcx, [rcx+10h]
0x180041262  call    WPP_SF_Zd
0x180041267  nop
0x180041268  mov     rdx, [rbp+57h+var_C0]
0x18004126c  test    rdx, rdx
0x18004126f  jz      short loc_18004127A
0x180041271  mov     ecx, r12d
0x180041274  call    KerbFreeData
0x180041279  nop
0x18004127a  mov     eax, 3Ch ; '<'
0x18004127f  mov     rcx, [rbp+57h+var_30]
0x180041283  xor     rcx, rsp; StackCookie
0x180041286  call    __security_check_cookie
0x18004128b  mov     rbx, [rsp+0F0h+arg_10]
0x180041293  add     rsp, 0D0h
0x18004129a  pop     r14
0x18004129c  pop     r12
0x18004129e  pop     rdi
0x18004129f  pop     rsi
0x1800412a0  pop     rbp
0x1800412a1  retn
```
