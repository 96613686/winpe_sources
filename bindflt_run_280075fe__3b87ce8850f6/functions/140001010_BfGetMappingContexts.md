# BfGetMappingContexts

- ea: `0x140001010`
- end: `0x140001340`
- name: `BfGetMappingContexts`
- size: `816`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140012c60`
- `0x140013864`
- `0x140014324`
- `0x1400157a0`
- `0x140017f00`

## callees

- `0x140001010`
- `0x140001348`
- `0x14001fcf0`

## import_xrefs

- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x1400010ee`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x1400010ee`
- `ntoskrnl!SeQueryInformationToken` at `0x1400010d4`
- `ntoskrnl!SeQueryInformationToken` at `0x1400010d4`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000115f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000115f`
- `ntoskrnl!RtlEqualSid` at `0x140001259`
- `ntoskrnl!RtlEqualSid` at `0x140001259`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140001210`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140001210`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400011f3`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400011f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001177`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001177`
- `ntoskrnl!IoGetSilo` at `0x14000103c`
- `ntoskrnl!IoGetSilo` at `0x14000103c`
- `FLTMGR!FltAcquireResourceShared` at `0x14000110f`
- `FLTMGR!FltAcquireResourceShared` at `0x14000110f`
- `FLTMGR!FltReleaseResource` at `0x140001141`
- `FLTMGR!FltReleaseResource` at `0x140001141`

## pseudocode

```c
__int64 __fastcall BfGetMappingContexts(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4, _QWORD *a5, _QWORD *a6)
{
  NTSTATUS v6; // ebx
  __int64 v7; // rbp
  __int64 Silo; // rax
  __int64 v12; // rdx
  __int64 v13; // rsi
  __int64 v14; // rax
  __int64 v15; // r13
  char v16; // r12
  PACCESS_TOKEN ClientToken; // rdi
  int v18; // edx
  void *v19; // r13
  __int64 i; // rdi
  __int64 v21; // rcx
  NTSTATUS v22; // eax
  int v24; // eax
  int v25; // edx
  PVOID TokenInformation; // [rsp+40h] [rbp-68h] BYREF
  __int64 v27; // [rsp+48h] [rbp-60h] BYREF
  _LUID AuthenticationId; // [rsp+50h] [rbp-58h] BYREF
  _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+60h] [rbp-48h] BYREF

  v6 = 0;
  v7 = 0;
  v27 = 0;
  Silo = IoGetSilo(a1);
  if ( Silo )
  {
    LOBYTE(v12) = 1;
    v24 = BfGetOrCreateSiloContext(Silo, v12, &v27);
    v6 = v24;
    if ( v24 != -1073741275 )
    {
      if ( v24 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v25) = 2;
          WPP_RECORDER_SF_sDd(
            WPP_GLOBAL_Control->DeviceExtension,
            v25,
            7,
            11,
            (__int64)WPP_ab4056511ca038337f1519c30a6fffbb_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\context.c",
            237,
            v24);
        }
        goto LABEL_21;
      }
      v7 = *(_QWORD *)(v27 + 8);
    }
  }
  v13 = 0;
  if ( !a3 )
    goto LABEL_18;
  v14 = *(_QWORD *)(a3 + 16);
  v15 = 0;
  TokenInformation = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  AuthenticationId = 0;
  if ( *(_BYTE *)(v14 + 4) )
  {
    SeCaptureSubjectContext(&SubjectContext);
    v16 = 1;
  }
  else
  {
    v16 = 0;
    SubjectContext = *(_SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(*(_QWORD *)(v14 + 24) + 8LL) + 32LL);
  }
  ClientToken = SubjectContext.ClientToken;
  if ( !SubjectContext.ClientToken )
    ClientToken = SubjectContext.PrimaryToken;
  v6 = SeQueryInformationToken(ClientToken, TokenUser, &TokenInformation);
  if ( v6 >= 0 )
  {
    v6 = SeQueryAuthenticationIdToken(ClientToken, &AuthenticationId);
    if ( v6 >= 0 )
    {
      v19 = *(void **)TokenInformation;
      FltAcquireResourceShared(&Resource);
      for ( i = qword_14000B1D8; ; i = *(_QWORD *)i )
      {
        if ( (__int64 *)i == &qword_14000B1D8 )
        {
          v6 = -1073741275;
          v15 = 0;
          goto LABEL_12;
        }
        if ( RtlEqualSid(*(PSID *)(i + 16), v19) )
          break;
      }
      v15 = i;
LABEL_12:
      FltReleaseResource(&Resource);
    }
  }
  if ( v16 )
    SeReleaseSubjectContext(&SubjectContext);
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( v6 == -1073741275 )
    goto LABEL_18;
  if ( v6 >= 0 )
  {
    v13 = *(_QWORD *)(v15 + 24);
LABEL_18:
    v21 = *(_QWORD *)(a2 + 48);
    *a4 = v7;
    *a5 = v13;
    *a6 = v21;
    v22 = 0;
    if ( v6 != -1073741275 )
      v22 = v6;
    v6 = v22;
    goto LABEL_21;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v18) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v18,
      7,
      12,
      (__int64)WPP_ab4056511ca038337f1519c30a6fffbb_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\context.c",
      252,
      v6);
  }
LABEL_21:
  if ( v27 )
    PsDereferenceSiloContext();
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140001010  mov     rax, rsp
0x140001013  push    rbx
0x140001014  sub     rsp, 0A0h
0x14000101b  mov     [rax+8], rbp
0x14000101f  xor     ebx, ebx
0x140001021  mov     [rax+18h], rdi
0x140001025  xor     ebp, ebp
0x140001027  mov     [rax-20h], r14
0x14000102b  mov     rdi, r8
0x14000102e  mov     [rax-28h], r15
0x140001032  mov     r14, r9
0x140001035  mov     r15, rdx
0x140001038  mov     [rax-60h], rbx
0x14000103c  call    cs:__imp_IoGetSilo
0x140001043  nop     dword ptr [rax+rax+00h]
0x140001048  test    rax, rax
0x14000104b  jnz     loc_140001224
0x140001051  mov     [rsp+0A8h+arg_8], rsi
0x140001059  xor     esi, esi
0x14000105b  mov     [rsp+0A8h+var_18], r13
0x140001063  test    rdi, rdi
0x140001066  jz      loc_14000118F
0x14000106c  mov     rax, [rdi+10h]
0x140001070  xorps   xmm0, xmm0
0x140001073  xor     r13d, r13d
0x140001076  mov     [rsp+0A8h+TokenInformation], rsi
0x14000107b  movups  xmmword ptr [rsp+0A8h+SubjectContext.ClientToken], xmm0
0x140001080  mov     qword ptr [rsp+0A8h+AuthenticationId.LowPart], rsi
0x140001085  movups  xmmword ptr [rsp+0A8h+SubjectContext.PrimaryToken], xmm0
0x14000108a  mov     [rsp+0A8h+var_10], r12
0x140001092  cmp     [rax+4], sil
0x140001096  jnz     loc_14000120B
0x14000109c  mov     rax, [rax+18h]
0x1400010a0  xor     r12b, r12b
0x1400010a3  mov     rcx, [rax+8]
0x1400010a7  movups  xmm0, xmmword ptr [rcx+20h]
0x1400010ab  movups  xmmword ptr [rsp+0A8h+SubjectContext.ClientToken], xmm0
0x1400010b0  movups  xmm1, xmmword ptr [rcx+30h]
0x1400010b4  movups  xmmword ptr [rsp+0A8h+SubjectContext.PrimaryToken], xmm1
0x1400010b9  mov     rdi, [rsp+0A8h+SubjectContext.ClientToken]
0x1400010be  lea     r8, [rsp+0A8h+TokenInformation]; TokenInformation
0x1400010c3  test    rdi, rdi
0x1400010c6  mov     edx, 1; TokenInformationClass
0x1400010cb  cmovz   rdi, [rsp+0A8h+SubjectContext.PrimaryToken]
0x1400010d1  mov     rcx, rdi; Token
0x1400010d4  call    cs:__imp_SeQueryInformationToken
0x1400010db  nop     dword ptr [rax+rax+00h]
0x1400010e0  mov     ebx, eax
0x1400010e2  test    eax, eax
0x1400010e4  js      short loc_14000114D
0x1400010e6  lea     rdx, [rsp+0A8h+AuthenticationId]; AuthenticationId
0x1400010eb  mov     rcx, rdi; Token
0x1400010ee  call    cs:__imp_SeQueryAuthenticationIdToken
0x1400010f5  nop     dword ptr [rax+rax+00h]
0x1400010fa  mov     ebx, eax
0x1400010fc  test    eax, eax
0x1400010fe  js      short loc_14000114D
0x140001100  mov     rax, [rsp+0A8h+TokenInformation]
0x140001105  lea     rcx, Resource; Resource
0x14000110c  mov     r13, [rax]
0x14000110f  call    cs:__imp_FltAcquireResourceShared
0x140001116  nop     dword ptr [rax+rax+00h]
0x14000111b  mov     rdi, cs:qword_14000B1D8
0x140001122  lea     rax, qword_14000B1D8
0x140001129  cmp     rdi, rax
0x14000112c  jnz     loc_140001252
0x140001132  mov     ebx, 0C0000225h
0x140001137  mov     r13, rsi
0x14000113a  lea     rcx, Resource; Resource
0x140001141  call    cs:__imp_FltReleaseResource
0x140001148  nop     dword ptr [rax+rax+00h]
0x14000114d  test    r12b, r12b
0x140001150  mov     r12, [rsp+0A8h+var_10]
0x140001158  jz      short loc_14000116B
0x14000115a  lea     rcx, [rsp+0A8h+SubjectContext]; SubjectContext
0x14000115f  call    cs:__imp_SeReleaseSubjectContext
0x140001166  nop     dword ptr [rax+rax+00h]
0x14000116b  mov     rcx, [rsp+0A8h+TokenInformation]; P
0x140001170  test    rcx, rcx
0x140001173  jz      short loc_140001183
0x140001175  xor     edx, edx; Tag
0x140001177  call    cs:__imp_ExFreePoolWithTag
0x14000117e  nop     dword ptr [rax+rax+00h]
0x140001183  cmp     ebx, 0C0000225h
0x140001189  jnz     loc_1400012D0
0x14000118f  mov     rax, [rsp+0A8h+arg_20]
0x140001197  mov     rcx, [r15+30h]
0x14000119b  mov     [r14], rbp
0x14000119e  mov     [rax], rsi
0x1400011a1  mov     rax, [rsp+0A8h+arg_28]
0x1400011a9  mov     [rax], rcx
0x1400011ac  xor     eax, eax
0x1400011ae  cmp     ebx, 0C0000225h
0x1400011b4  cmovnz  eax, ebx
0x1400011b7  mov     ebx, eax
0x1400011b9  mov     rsi, [rsp+0A8h+arg_8]
0x1400011c1  mov     r13, [rsp+0A8h+var_18]
0x1400011c9  mov     rcx, [rsp+0A8h+var_60]
0x1400011ce  mov     r15, [rsp+0A8h+var_28]
0x1400011d6  mov     r14, [rsp+0A8h+var_20]
0x1400011de  mov     rdi, [rsp+0A8h+arg_10]
0x1400011e6  mov     rbp, [rsp+0A8h+arg_0]
0x1400011ee  test    rcx, rcx
0x1400011f1  jz      short loc_1400011FF
0x1400011f3  call    cs:__imp_PsDereferenceSiloContext
0x1400011fa  nop     dword ptr [rax+rax+00h]
0x1400011ff  mov     eax, ebx
0x140001201  add     rsp, 0A0h
0x140001208  pop     rbx
0x140001209  retn
0x14000120b  lea     rcx, [rsp+0A8h+SubjectContext]; SubjectContext
0x140001210  call    cs:__imp_SeCaptureSubjectContext
0x140001217  nop     dword ptr [rax+rax+00h]
0x14000121c  mov     r12b, 1
0x14000121f  jmp     loc_1400010B9
0x140001224  lea     r8, [rsp+0A8h+var_60]
0x140001229  mov     dl, 1
0x14000122b  mov     rcx, rax
0x14000122e  call    BfGetOrCreateSiloContext
0x140001233  mov     ebx, eax
0x140001235  cmp     eax, 0C0000225h
0x14000123a  jz      loc_140001051
0x140001240  test    eax, eax
0x140001242  js      short loc_140001275
0x140001244  mov     rax, [rsp+0A8h+var_60]
0x140001249  mov     rbp, [rax+8]
0x14000124d  jmp     loc_140001051
0x140001252  mov     rcx, [rdi+10h]; Sid1
0x140001256  mov     rdx, r13; Sid2
0x140001259  call    cs:__imp_RtlEqualSid
0x140001260  nop     dword ptr [rax+rax+00h]
0x140001265  test    al, al
0x140001267  jnz     loc_14000132F
0x14000126d  mov     rdi, [rdi]
0x140001270  jmp     loc_140001122
0x140001275  lea     rax, WPP_RECORDER_INITIALIZED
0x14000127c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140001283  jz      loc_1400011C9
0x140001289  mov     rcx, cs:WPP_GLOBAL_Control
0x140001290  lea     rax, aOnecoreBaseFsW; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140001297  mov     [rsp+0A8h+var_70], ebx
0x14000129b  mov     r9d, 0Bh
0x1400012a1  mov     [rsp+0A8h+var_78], 0EDh
0x1400012a9  mov     r8d, 7
0x1400012af  mov     [rsp+0A8h+var_80], rax
0x1400012b4  mov     dl, 2
0x1400012b6  mov     rcx, [rcx+40h]
0x1400012ba  lea     rax, WPP_ab4056511ca038337f1519c30a6fffbb_Traceguids
0x1400012c1  mov     [rsp+0A8h+var_88], rax
0x1400012c6  call    WPP_RECORDER_SF_sDd
0x1400012cb  jmp     loc_1400011C9
0x1400012d0  test    ebx, ebx
0x1400012d2  jns     short loc_140001337
0x1400012d4  lea     rax, WPP_RECORDER_INITIALIZED
0x1400012db  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400012e2  jz      loc_1400011B9
0x1400012e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400012ef  lea     rax, aOnecoreBaseFsW; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x1400012f6  mov     [rsp+0A8h+var_70], ebx
0x1400012fa  mov     r9d, 0Ch
0x140001300  mov     [rsp+0A8h+var_78], 0FCh
0x140001308  mov     r8d, 7
0x14000130e  mov     [rsp+0A8h+var_80], rax
0x140001313  mov     dl, 2
0x140001315  mov     rcx, [rcx+40h]
0x140001319  lea     rax, WPP_ab4056511ca038337f1519c30a6fffbb_Traceguids
0x140001320  mov     [rsp+0A8h+var_88], rax
0x140001325  call    WPP_RECORDER_SF_sDd
0x14000132a  jmp     loc_1400011B9
0x14000132f  mov     r13, rdi
0x140001332  jmp     loc_14000113A
0x140001337  mov     rsi, [r13+18h]
0x14000133b  jmp     loc_14000118F
```
