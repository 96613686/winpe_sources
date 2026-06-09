# Smb2ValidateWindowsHelloForBusinessAuthentication

- ea: `0x14006a1c4`
- end: `0x14006a56a`
- name: `Smb2ValidateWindowsHelloForBusinessAuthentication`
- size: `934`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400921f0`

## callees

- `0x140015960`
- `0x14002019c`
- `0x1400224b8`
- `0x140069b14`
- `0x14006a1c4`
- `0x140077600`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006a506`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a525`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a506`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a525`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006a3e1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006a404`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006a3e1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006a404`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a317`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a362`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a435`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a480`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a317`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a362`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a435`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a480`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14006a541`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14006a541`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14006a272`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14006a272`
- `ntoskrnl!SeQueryInformationToken` at `0x14006a2c1`
- `ntoskrnl!SeQueryInformationToken` at `0x14006a37a`
- `ntoskrnl!SeQueryInformationToken` at `0x14006a2c1`
- `ntoskrnl!SeQueryInformationToken` at `0x14006a37a`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14006a2f1`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14006a3c0`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14006a2f1`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14006a3c0`
- `srvnet!SrvLibIsNetwork` at `0x14006a1fc`
- `srvnet!SrvLibIsNetwork` at `0x14006a1fc`

## pseudocode

```c
__int64 __fastcall Smb2ValidateWindowsHelloForBusinessAuthentication(__int64 a1)
{
  void *v1; // r14
  int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  char v7; // r15
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  PACCESS_TOKEN v10; // rax
  NTSTATUS v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // ebx
  unsigned int v15; // eax
  char v16; // r13
  char v17; // r12
  unsigned int v18; // r15d
  NTSTATUS v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+20h] [rbp-30h] BYREF
  PVOID TokenInformation; // [rsp+28h] [rbp-28h] BYREF
  PVOID P; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int8 EffectiveOnly; // [rsp+A0h] [rbp+50h] BYREF
  unsigned __int8 CopyOnOpen; // [rsp+A8h] [rbp+58h] BYREF

  v1 = 0;
  TokenInformation = 0;
  P = 0;
  v2 = Smb2ImpersonateSecurityContext(a1);
  v6 = (unsigned int)v2;
  if ( v2 < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    v7 = 0;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_52;
    }
    v24 = 45;
LABEL_51:
    WPP_SF_d(v23->AttachedDevice, v24, &WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids, v6);
    goto LABEL_52;
  }
  v7 = 1;
  if ( !(unsigned __int8)SrvLibIsNetwork(v4, v3, v5, (unsigned int)v2) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_52;
    }
    v9 = 40;
    goto LABEL_7;
  }
  CopyOnOpen = 0;
  EffectiveOnly = 0;
  ImpersonationLevel = SecurityAnonymous;
  v10 = PsReferenceImpersonationToken(KeGetCurrentThread(), &CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
  v1 = v10;
  if ( !v10 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_52;
    }
    v9 = 41;
LABEL_7:
    WPP_SF_(v8->AttachedDevice, v9, &WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids);
LABEL_52:
    v14 = -1073741628;
    goto LABEL_53;
  }
  if ( !SeQueryInformationToken(v10, TokenUser, &TokenInformation) )
  {
    UnicodeString = 0;
    v11 = RtlConvertSidToUnicodeString(&UnicodeString, *(PSID *)TokenInformation, 1u);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          42,
          &WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids,
          (unsigned int)v11);
      }
    }
    else if ( (unsigned __int8)Smb2IsUserOrGroupInExceptionList(UnicodeString.Buffer, v12, v13, (unsigned int)v11) )
    {
      v14 = 0;
      RtlFreeUnicodeString(&UnicodeString);
      goto LABEL_53;
    }
    if ( UnicodeString.Buffer )
      RtlFreeUnicodeString(&UnicodeString);
  }
  v15 = SeQueryInformationToken(v1, TokenGroups, &P);
  v6 = v15;
  if ( v15 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_52;
    }
    v24 = 44;
    goto LABEL_51;
  }
  v16 = 0;
  v17 = 0;
  v18 = 0;
  UnicodeString = 0;
  while ( v18 < *(_DWORD *)P )
  {
    v19 = RtlConvertSidToUnicodeString(&UnicodeString, *((PSID *)P + 2 * v18 + 1), 1u);
    if ( v19 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          43,
          &WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids,
          (unsigned int)v19);
      }
      goto LABEL_39;
    }
    if ( RtlEqualUnicodeString(&UnicodeString, &String2, 1u) )
    {
      v16 = 1;
LABEL_32:
      if ( v17 )
        goto LABEL_40;
      goto LABEL_33;
    }
    if ( RtlEqualUnicodeString(&UnicodeString, &stru_14003F230, 1u) )
      v17 = 1;
    if ( v16 )
      goto LABEL_32;
LABEL_33:
    if ( (unsigned __int8)Smb2IsUserOrGroupInExceptionList(UnicodeString.Buffer, v20, v21, v22) )
    {
LABEL_40:
      v14 = 0;
      RtlFreeUnicodeString(&UnicodeString);
      goto LABEL_41;
    }
    RtlFreeUnicodeString(&UnicodeString);
LABEL_39:
    ++v18;
  }
  v14 = -1067646966;
LABEL_41:
  v7 = 1;
LABEL_53:
  if ( TokenInformation )
  {
    ExFreePoolWithTag(TokenInformation, 0);
    TokenInformation = 0;
  }
  if ( P )
  {
    ExFreePoolWithTag(P, 0);
    P = 0;
  }
  if ( v1 )
    PsDereferenceImpersonationToken(v1);
  if ( v7 )
    Smb2Revert();
  return v14;
}

```

## disassembly

```asm
0x14006a1c4  push    rbp
0x14006a1c6  push    rbx
0x14006a1c7  push    rdi
0x14006a1c8  push    r12
0x14006a1ca  push    r13
0x14006a1cc  push    r14
0x14006a1ce  push    r15
0x14006a1d0  mov     rbp, rsp
0x14006a1d3  sub     rsp, 50h
0x14006a1d7  xor     r14d, r14d
0x14006a1da  mov     [rbp+TokenInformation], r14
0x14006a1de  mov     [rbp+P], r14
0x14006a1e2  call    Smb2ImpersonateSecurityContext
0x14006a1e7  mov     r9d, eax
0x14006a1ea  test    eax, eax
0x14006a1ec  js      loc_14006A4BA
0x14006a1f2  lea     ebx, [r14+1]
0x14006a1f6  mov     r15b, bl
0x14006a1f9  mov     [rbp+arg_8], bl
0x14006a1fc  call    cs:__imp_SrvLibIsNetwork
0x14006a203  nop     dword ptr [rax+rax+00h]
0x14006a208  test    al, al
0x14006a20a  jnz     short loc_14006A251
0x14006a20c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a213  lea     rdi, WPP_GLOBAL_Control
0x14006a21a  cmp     rcx, rdi
0x14006a21d  jz      loc_14006A4F6
0x14006a223  test    dword ptr [rcx+2Ch], 20000h
0x14006a22a  jz      loc_14006A4F6
0x14006a230  cmp     [rcx+29h], bl
0x14006a233  jb      loc_14006A4F6
0x14006a239  lea     edx, [rbx+27h]
0x14006a23c  mov     rcx, [rcx+18h]
0x14006a240  lea     r8, WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids
0x14006a247  call    WPP_SF_
0x14006a24c  jmp     loc_14006A4F6
0x14006a251  mov     [rbp+CopyOnOpen], r14b
0x14006a255  lea     r9, [rbp+ImpersonationLevel]; ImpersonationLevel
0x14006a259  mov     [rbp+EffectiveOnly], r14b
0x14006a25d  lea     r8, [rbp+EffectiveOnly]; EffectiveOnly
0x14006a261  mov     [rbp+ImpersonationLevel], r14d
0x14006a265  lea     rdx, [rbp+CopyOnOpen]; CopyOnOpen
0x14006a269  mov     rcx, gs:188h; Thread
0x14006a272  call    cs:__imp_PsReferenceImpersonationToken
0x14006a279  nop     dword ptr [rax+rax+00h]
0x14006a27e  mov     r14, rax
0x14006a281  test    rax, rax
0x14006a284  jnz     short loc_14006A2B8
0x14006a286  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a28d  lea     rdi, WPP_GLOBAL_Control
0x14006a294  cmp     rcx, rdi
0x14006a297  jz      loc_14006A4F6
0x14006a29d  test    dword ptr [rcx+2Ch], 20000h
0x14006a2a4  jz      loc_14006A4F6
0x14006a2aa  cmp     [rcx+29h], bl
0x14006a2ad  jb      loc_14006A4F6
0x14006a2b3  lea     edx, [rax+29h]
0x14006a2b6  jmp     short loc_14006A23C
0x14006a2b8  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14006a2bc  mov     edx, ebx; TokenInformationClass
0x14006a2be  mov     rcx, r14; Token
0x14006a2c1  call    cs:__imp_SeQueryInformationToken
0x14006a2c8  nop     dword ptr [rax+rax+00h]
0x14006a2cd  lea     rdi, WPP_GLOBAL_Control
0x14006a2d4  test    eax, eax
0x14006a2d6  jnz     loc_14006A36E
0x14006a2dc  mov     rdx, [rbp+TokenInformation]
0x14006a2e0  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14006a2e4  xorps   xmm0, xmm0
0x14006a2e7  mov     r8b, bl; AllocateDestinationString
0x14006a2ea  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x14006a2ee  mov     rdx, [rdx]; Sid
0x14006a2f1  call    cs:__imp_RtlConvertSidToUnicodeString
0x14006a2f8  nop     dword ptr [rax+rax+00h]
0x14006a2fd  mov     r9d, eax
0x14006a300  test    eax, eax
0x14006a302  js      short loc_14006A328
0x14006a304  mov     rcx, [rbp+UnicodeString.Buffer]
0x14006a308  call    Smb2IsUserOrGroupInExceptionList
0x14006a30d  test    al, al
0x14006a30f  jz      short loc_14006A357
0x14006a311  xor     ebx, ebx
0x14006a313  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14006a317  call    cs:__imp_RtlFreeUnicodeString
0x14006a31e  nop     dword ptr [rax+rax+00h]
0x14006a323  jmp     loc_14006A4FB
0x14006a328  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a32f  cmp     rcx, rdi
0x14006a332  jz      short loc_14006A357
0x14006a334  test    dword ptr [rcx+2Ch], 20000h
0x14006a33b  jz      short loc_14006A357
0x14006a33d  cmp     [rcx+29h], bl
0x14006a340  jb      short loc_14006A357
0x14006a342  mov     rcx, [rcx+18h]
0x14006a346  lea     r8, WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids
0x14006a34d  mov     edx, 2Ah ; '*'
0x14006a352  call    WPP_SF_d
0x14006a357  cmp     [rbp+UnicodeString.Buffer], 0
0x14006a35c  jz      short loc_14006A36E
0x14006a35e  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14006a362  call    cs:__imp_RtlFreeUnicodeString
0x14006a369  nop     dword ptr [rax+rax+00h]
0x14006a36e  lea     r8, [rbp+P]; TokenInformation
0x14006a372  mov     edx, 2; TokenInformationClass
0x14006a377  mov     rcx, r14; Token
0x14006a37a  call    cs:__imp_SeQueryInformationToken
0x14006a381  nop     dword ptr [rax+rax+00h]
0x14006a386  mov     r9d, eax
0x14006a389  test    eax, eax
0x14006a38b  jnz     loc_14006A499
0x14006a391  xor     r13b, r13b
0x14006a394  xor     r12b, r12b
0x14006a397  xorps   xmm0, xmm0
0x14006a39a  xor     r15d, r15d
0x14006a39d  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x14006a3a1  mov     rcx, [rbp+P]
0x14006a3a5  cmp     r15d, [rcx]
0x14006a3a8  jnb     loc_14006A492
0x14006a3ae  mov     edx, r15d
0x14006a3b1  mov     r8b, bl; AllocateDestinationString
0x14006a3b4  add     rdx, rdx
0x14006a3b7  mov     rdx, [rcx+rdx*8+8]; Sid
0x14006a3bc  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14006a3c0  call    cs:__imp_RtlConvertSidToUnicodeString
0x14006a3c7  nop     dword ptr [rax+rax+00h]
0x14006a3cc  mov     r9d, eax
0x14006a3cf  test    eax, eax
0x14006a3d1  js      short loc_14006A443
0x14006a3d3  mov     r8b, bl; CaseInSensitive
0x14006a3d6  lea     rdx, String2; String2
0x14006a3dd  lea     rcx, [rbp+UnicodeString]; String1
0x14006a3e1  call    cs:__imp_RtlEqualUnicodeString
0x14006a3e8  nop     dword ptr [rax+rax+00h]
0x14006a3ed  test    al, al
0x14006a3ef  jz      short loc_14006A3F6
0x14006a3f1  mov     r13b, bl
0x14006a3f4  jmp     short loc_14006A41F
0x14006a3f6  mov     r8b, bl; CaseInSensitive
0x14006a3f9  lea     rdx, stru_14003F230; String2
0x14006a400  lea     rcx, [rbp+UnicodeString]; String1
0x14006a404  call    cs:__imp_RtlEqualUnicodeString
0x14006a40b  nop     dword ptr [rax+rax+00h]
0x14006a410  test    al, al
0x14006a412  movzx   r12d, r12b
0x14006a416  cmovnz  r12d, ebx
0x14006a41a  test    r13b, r13b
0x14006a41d  jz      short loc_14006A424
0x14006a41f  test    r12b, r12b
0x14006a422  jnz     short loc_14006A47A
0x14006a424  mov     rcx, [rbp+UnicodeString.Buffer]
0x14006a428  call    Smb2IsUserOrGroupInExceptionList
0x14006a42d  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14006a431  test    al, al
0x14006a433  jnz     short loc_14006A47E
0x14006a435  call    cs:__imp_RtlFreeUnicodeString
0x14006a43c  nop     dword ptr [rax+rax+00h]
0x14006a441  jmp     short loc_14006A472
0x14006a443  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a44a  cmp     rcx, rdi
0x14006a44d  jz      short loc_14006A472
0x14006a44f  test    dword ptr [rcx+2Ch], 20000h
0x14006a456  jz      short loc_14006A472
0x14006a458  cmp     [rcx+29h], bl
0x14006a45b  jb      short loc_14006A472
0x14006a45d  mov     rcx, [rcx+18h]
0x14006a461  lea     r8, WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids
0x14006a468  mov     edx, 2Bh ; '+'
0x14006a46d  call    WPP_SF_d
0x14006a472  add     r15d, ebx
0x14006a475  jmp     loc_14006A3A1
0x14006a47a  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14006a47e  xor     ebx, ebx
0x14006a480  call    cs:__imp_RtlFreeUnicodeString
0x14006a487  nop     dword ptr [rax+rax+00h]
0x14006a48c  mov     r15b, [rbp+arg_8]
0x14006a490  jmp     short loc_14006A4FB
0x14006a492  mov     ebx, 0C05D000Ah
0x14006a497  jmp     short loc_14006A48C
0x14006a499  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a4a0  cmp     rcx, rdi
0x14006a4a3  jz      short loc_14006A4F6
0x14006a4a5  test    dword ptr [rcx+2Ch], 20000h
0x14006a4ac  jz      short loc_14006A4F6
0x14006a4ae  cmp     [rcx+29h], bl
0x14006a4b1  jb      short loc_14006A4F6
0x14006a4b3  mov     edx, 2Ch ; ','
0x14006a4b8  jmp     short loc_14006A4E6
0x14006a4ba  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a4c1  lea     rdi, WPP_GLOBAL_Control
0x14006a4c8  xor     r15b, r15b
0x14006a4cb  cmp     rcx, rdi
0x14006a4ce  jz      short loc_14006A4F6
0x14006a4d0  test    dword ptr [rcx+2Ch], 20000h
0x14006a4d7  jz      short loc_14006A4F6
0x14006a4d9  mov     ebx, 1
0x14006a4de  cmp     [rcx+29h], bl
0x14006a4e1  jb      short loc_14006A4F6
0x14006a4e3  lea     edx, [rbx+2Ch]
0x14006a4e6  mov     rcx, [rcx+18h]
0x14006a4ea  lea     r8, WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids
0x14006a4f1  call    WPP_SF_d
0x14006a4f6  mov     ebx, 0C00000C4h
0x14006a4fb  mov     rcx, [rbp+TokenInformation]; P
0x14006a4ff  test    rcx, rcx
0x14006a502  jz      short loc_14006A51A
0x14006a504  xor     edx, edx; Tag
0x14006a506  call    cs:__imp_ExFreePoolWithTag
0x14006a50d  nop     dword ptr [rax+rax+00h]
0x14006a512  mov     [rbp+TokenInformation], 0
0x14006a51a  mov     rcx, [rbp+P]; P
0x14006a51e  test    rcx, rcx
0x14006a521  jz      short loc_14006A539
0x14006a523  xor     edx, edx; Tag
0x14006a525  call    cs:__imp_ExFreePoolWithTag
0x14006a52c  nop     dword ptr [rax+rax+00h]
0x14006a531  mov     [rbp+P], 0
0x14006a539  test    r14, r14
0x14006a53c  jz      short loc_14006A54D
0x14006a53e  mov     rcx, r14; ImpersonationToken
0x14006a541  call    cs:__imp_PsDereferenceImpersonationToken
0x14006a548  nop     dword ptr [rax+rax+00h]
0x14006a54d  test    r15b, r15b
0x14006a550  jz      short loc_14006A557
0x14006a552  call    Smb2Revert
0x14006a557  mov     eax, ebx
0x14006a559  add     rsp, 50h
0x14006a55d  pop     r15
0x14006a55f  pop     r14
0x14006a561  pop     r13
0x14006a563  pop     r12
0x14006a565  pop     rdi
0x14006a566  pop     rbx
0x14006a567  pop     rbp
0x14006a568  retn
```
