# Smb2ValidateSecurityBuffer

- ea: `0x140095748`
- end: `0x140095f80`
- name: `Smb2ValidateSecurityBuffer`
- size: `2104`
- prototype: `__int64 __usercall@<rax>(PCtxtHandle phContext@<rcx>, __int64, __int64, __int64, __int64, void *, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400921f0`

## callees

- `0x140005070`
- `0x140018c60`
- `0x14001c768`
- `0x140022958`
- `0x140024260`
- `0x14002d4dc`
- `0x140031ac0`
- `0x140038490`
- `0x140095748`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400958c3`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400958c3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140095960`
- `ntoskrnl!ExReleaseResourceLite` at `0x140095960`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400959ca`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400959ca`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400959e9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140095a0e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400959e9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140095a0e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140095c39`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140095c39`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140095c8d`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140095c8d`
- `ntoskrnl!ExLocalTimeToSystemTime` at `0x140095a23`
- `ntoskrnl!ExLocalTimeToSystemTime` at `0x140095a23`
- `ntoskrnl!SeLockSubjectContext` at `0x140095c49`
- `ntoskrnl!SeLockSubjectContext` at `0x140095c49`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140095c5d`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140095c5d`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140095c7d`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140095c7d`
- `srvnet!SrvLibQueryCredentialHandle` at `0x1400958f5`
- `srvnet!SrvLibQueryCredentialHandle` at `0x1400958f5`
- `ksecdd!FreeContextBuffer` at `0x140095de9`
- `ksecdd!FreeContextBuffer` at `0x140095de9`
- `ksecdd!MapSecurityError` at `0x14009598e`
- `ksecdd!MapSecurityError` at `0x140095a4a`
- `ksecdd!MapSecurityError` at `0x140095ad3`
- `ksecdd!MapSecurityError` at `0x140095c6b`
- `ksecdd!MapSecurityError` at `0x140095d25`
- `ksecdd!MapSecurityError` at `0x140095dc6`
- `ksecdd!MapSecurityError` at `0x14009598e`
- `ksecdd!MapSecurityError` at `0x140095a4a`
- `ksecdd!MapSecurityError` at `0x140095ad3`
- `ksecdd!MapSecurityError` at `0x140095c6b`
- `ksecdd!MapSecurityError` at `0x140095d25`
- `ksecdd!MapSecurityError` at `0x140095dc6`
- `ksecdd!QueryContextAttributesW` at `0x140095a3c`
- `ksecdd!QueryContextAttributesW` at `0x140095aa3`
- `ksecdd!QueryContextAttributesW` at `0x140095ce1`
- `ksecdd!QueryContextAttributesW` at `0x140095d15`
- `ksecdd!QueryContextAttributesW` at `0x140095db8`
- `ksecdd!QueryContextAttributesW` at `0x140095a3c`
- `ksecdd!QueryContextAttributesW` at `0x140095aa3`
- `ksecdd!QueryContextAttributesW` at `0x140095ce1`
- `ksecdd!QueryContextAttributesW` at `0x140095d15`
- `ksecdd!QueryContextAttributesW` at `0x140095db8`
- `ksecdd!ImpersonateSecurityContext` at `0x140095bf5`
- `ksecdd!ImpersonateSecurityContext` at `0x140095bf5`
- `ksecdd!RevertSecurityContext` at `0x140095cb8`
- `ksecdd!RevertSecurityContext` at `0x140095cb8`
- `ksecdd!AcceptSecurityContext` at `0x14009593a`
- `ksecdd!AcceptSecurityContext` at `0x14009593a`

## string_xrefs

- `0x140095882`: `Smb2ValidateSecurityBuffer`
- `0x14009596c`: `Smb2ValidateSecurityBuffer`
- `0x140095a78`: `Smb2ValidateSecurityBuffer`
- `0x140095aaf`: `Smb2ValidateSecurityBuffer`
- `0x140095c1f`: `Smb2ValidateSecurityBuffer`
- `0x140095c99`: `Smb2ValidateSecurityBuffer`

## pseudocode

```c
__int64 __fastcall Smb2ValidateSecurityBuffer(
        PCtxtHandle phContext,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        _DWORD *a6,
        union _LARGE_INTEGER *a7,
        void *a8,
        int *a9,
        struct _LUID *a10,
        _BYTE *a11,
        _BYTE *a12,
        _WORD *a13,
        __int64 a14,
        __int64 a15)
{
  struct _SecHandle *v15; // rbx
  _DWORD *v17; // rdx
  unsigned int v19; // r10d
  __int64 v20; // rax
  struct _SecHandle *CredentialHandle; // rax
  SECURITY_STATUS v22; // ebx
  NTSTATUS v23; // eax
  SECURITY_STATUS v24; // ebx
  __int64 v25; // rax
  SECURITY_STATUS v27; // eax
  NTSTATUS v28; // eax
  __int64 v29; // rdx
  SECURITY_STATUS ContextAttributesW; // ebx
  NTSTATUS v31; // eax
  int v32; // r8d
  int v33; // ecx
  int v34; // eax
  __int64 v35; // rdx
  SECURITY_STATUS AuthenticationIdToken; // eax
  SECURITY_STATUS v37; // ebx
  NTSTATUS v38; // eax
  __int64 v39; // rax
  SECURITY_STATUS v40; // eax
  PVOID v41; // rcx
  int TargetDataRepb; // [rsp+20h] [rbp-E0h]
  int TargetDataRep; // [rsp+20h] [rbp-E0h]
  int TargetDataRepc; // [rsp+20h] [rbp-E0h]
  int TargetDataRepa; // [rsp+20h] [rbp-E0h]
  int TargetDataRepd; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int pfContextAttr; // [rsp+54h] [rbp-ACh] BYREF
  PLARGE_INTEGER SystemTime; // [rsp+58h] [rbp-A8h] BYREF
  int pBuffer; // [rsp+60h] [rbp-A0h] BYREF
  PVOID pvContextBuffer; // [rsp+68h] [rbp-98h] BYREF
  int v52; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v53; // [rsp+74h] [rbp-8Ch]
  __int128 v54; // [rsp+78h] [rbp-88h] BYREF
  SECURITY_INTEGER LocalTime; // [rsp+88h] [rbp-78h] BYREF
  struct _SecBufferDesc pInput; // [rsp+90h] [rbp-70h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v58; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v59; // [rsp+B8h] [rbp-48h] BYREF
  PLUID AuthenticationId; // [rsp+C0h] [rbp-40h]
  _BYTE *v61; // [rsp+C8h] [rbp-38h]
  _DWORD *v62; // [rsp+D0h] [rbp-30h]
  __int64 v63; // [rsp+D8h] [rbp-28h]
  __int64 v64; // [rsp+E0h] [rbp-20h]
  __int64 v65; // [rsp+E8h] [rbp-18h]
  _DWORD v66[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v67; // [rsp+F8h] [rbp-8h]
  int v68; // [rsp+100h] [rbp+0h]
  int v69; // [rsp+104h] [rbp+4h]
  __int64 v70; // [rsp+108h] [rbp+8h]
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+110h] [rbp+10h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v72; // [rsp+130h] [rbp+30h] BYREF
  __int64 *v73; // [rsp+150h] [rbp+50h]
  __int64 v74; // [rsp+158h] [rbp+58h]
  __int64 *v75; // [rsp+160h] [rbp+60h]
  __int64 v76; // [rsp+168h] [rbp+68h]
  int *v77; // [rsp+170h] [rbp+70h]
  __int64 v78; // [rsp+178h] [rbp+78h]
  int *v79; // [rsp+180h] [rbp+80h]
  __int64 v80; // [rsp+188h] [rbp+88h]
  PLARGE_INTEGER *p_SystemTime; // [rsp+190h] [rbp+90h]
  __int64 v82; // [rsp+198h] [rbp+98h]

  v15 = 0;
  v17 = a6;
  v19 = *a6;
  pvContextBuffer = a8;
  SystemTime = a7;
  AuthenticationId = a10;
  pBuffer = 0;
  pfContextAttr = 0;
  LocalTime.QuadPart = 0;
  v62 = a6;
  v61 = a11;
  v53 = v19;
  pInput = 0;
  pOutput = 0;
  v54 = 0;
  v20 = MEMORY[0xFFFFF78000000014];
  *a11 = 0;
  *a12 = 0;
  *a6 = 0;
  v64 = v20;
  if ( a13 )
    *a13 = -1;
  pInput.pBuffers = (PSecBuffer)v66;
  if ( a14 )
  {
    pInput.cBuffers = 2;
    v70 = a14;
    v68 = 32;
    v69 = 129;
  }
  else
  {
    pInput.cBuffers = 1;
  }
  v67 = a3;
  pOutput.pBuffers = (PSecBuffer)&v54;
  LOBYTE(v17) = 7;
  *((_QWORD *)&v54 + 1) = a5;
  v66[0] = a4;
  v66[1] = 2;
  pInput.ulVersion = 0;
  pOutput.cBuffers = 1;
  pOutput.ulVersion = 0;
  *(_QWORD *)&v54 = v19 | 0x200000000LL;
  pfContextAttr = 0;
  ++*(_DWORD *)(Srv2Statistics + 24);
  SRV2_PERF_ENTER_EX(a15 + 584, v17, 1090, "Smb2ValidateSecurityBuffer", 1);
  ExAcquireResourceSharedLite(&Smb2ExtensibleCredHandleLock, 1u);
  v63 = MEMORY[0xFFFFF78000000014];
  if ( *(_OWORD *)phContext != 0 )
    v15 = phContext;
  CredentialHandle = (struct _SecHandle *)SrvLibQueryCredentialHandle(Smb2ExtensibleCredentialHandle);
  v22 = AcceptSecurityContext(
          CredentialHandle,
          v15,
          &pInput,
          0x908001u,
          0x10u,
          phContext,
          &pOutput,
          &pfContextAttr,
          &LocalTime);
  v65 = MEMORY[0xFFFFF78000000014];
  ExReleaseResourceLite(&Smb2ExtensibleCredHandleLock);
  LOBYTE(TargetDataRepb) = 1;
  SRV2_PERF_ENTER_EX(a15 + 584, 0, 1112, "Smb2ValidateSecurityBuffer", TargetDataRepb);
  v23 = MapSecurityError(v22);
  v24 = v23;
  if ( v23 == -1073741816 || v23 == -1073741570 )
  {
    v24 = -1073741623;
LABEL_47:
    if ( (pfContextAttr & 0x8000) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qqD(
          WPP_GLOBAL_Control->AttachedDevice,
          37,
          &WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids,
          a15,
          a2,
          v24);
      }
      goto LABEL_58;
    }
    goto LABEL_52;
  }
  if ( v23 < 0 )
    goto LABEL_47;
  if ( v23 )
  {
LABEL_52:
    v24 = -1073741802;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        36,
        &WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids,
        a15,
        a2,
        -1073741802);
    }
    goto LABEL_56;
  }
  ExAcquirePushLockExclusiveEx(*(_QWORD *)(a2 + 24) + 80LL, 0);
  v25 = *(_QWORD *)(a2 + 24);
  if ( *(_DWORD *)(v25 + 12) == 221 )
  {
    ExReleasePushLockExclusiveEx(v25 + 80, 0);
    return 3221226332LL;
  }
  *(_DWORD *)(v25 + 12) = 220;
  ExReleasePushLockExclusiveEx(*(_QWORD *)(a2 + 24) + 80LL, 0);
  ExLocalTimeToSystemTime(&LocalTime, SystemTime);
  v27 = QueryContextAttributesW(phContext, 0x25u, &pBuffer);
  v28 = MapSecurityError(v27);
  v24 = v28;
  if ( v28 == -1073741637 )
  {
    *a12 = 0;
  }
  else if ( v28 < 0 )
  {
LABEL_26:
    v34 = 0;
    LODWORD(v54) = 0;
LABEL_57:
    *v62 = v34;
    goto LABEL_58;
  }
  if ( pBuffer )
    *a12 = 1;
  LOBYTE(TargetDataRep) = 1;
  LOBYTE(v29) = 7;
  SRV2_PERF_ENTER_EX(a15 + 584, v29, 1167, "Smb2ValidateSecurityBuffer", TargetDataRep);
  LOBYTE(TargetDataRepc) = 1;
  ContextAttributesW = QueryContextAttributesW(phContext, 9u, a9);
  SRV2_PERF_ENTER_EX(a15 + 584, 0, 1173, "Smb2ValidateSecurityBuffer", TargetDataRepc);
  v31 = MapSecurityError(ContextAttributesW);
  LOBYTE(v32) = 0;
  v24 = v31;
  if ( v31 < 0 )
    goto LABEL_26;
  if ( (unsigned int)dword_1400583B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400583B0, 0x400000000000LL, 0) )
  {
    v58 = 0x2000000;
    v73 = &v58;
    v74 = 8;
    v75 = &v59;
    v47 = *a9;
    v77 = &v47;
    v52 = *(_DWORD *)(a2 + 292);
    v79 = &v52;
    LODWORD(SystemTime) = Smb2MinSessionKeyCbLength;
    p_SystemTime = &SystemTime;
    v59 = 1;
    v76 = 8;
    v78 = 4;
    v80 = 4;
    v82 = 4;
    tlgWriteAgg(v33, (int)&dword_140043447, v32, v32 + 7, &v72);
    LOBYTE(v32) = 0;
  }
  if ( *a12 == (_BYTE)v32 && *a9 < (unsigned int)Smb2MinSessionKeyCbLength )
  {
    Smb2LogTooShortKeyError(a15, a2, phContext, a9);
    v24 = -1073740521;
    goto LABEL_26;
  }
  v24 = ImpersonateSecurityContext(phContext);
  if ( v24 < 0 )
    goto LABEL_26;
  LOBYTE(TargetDataRepa) = 1;
  LOBYTE(v35) = 7;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SRV2_PERF_ENTER_EX(a15 + 584, v35, 1211, "Smb2ValidateSecurityBuffer", TargetDataRepa);
  SeCaptureSubjectContext(&SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  AuthenticationIdToken = SeQueryAuthenticationIdToken(SubjectContext.ClientToken, AuthenticationId);
  v24 = MapSecurityError(AuthenticationIdToken);
  SeUnlockSubjectContext(&SubjectContext);
  SeReleaseSubjectContext(&SubjectContext);
  LOBYTE(TargetDataRepd) = 1;
  SRV2_PERF_ENTER_EX(a15 + 584, 0, 1227, "Smb2ValidateSecurityBuffer", TargetDataRepd);
  RevertSecurityContext(phContext);
  if ( v24 < 0 )
    goto LABEL_26;
  v47 = 0;
  if ( !QueryContextAttributesW(phContext, 0xBu, &v47) && (v47 & 1) != 0 )
    *v61 = 1;
  SystemTime = 0;
  v37 = QueryContextAttributesW(phContext, 0x15u, &SystemTime);
  v38 = MapSecurityError(v37);
  if ( v38 < 0 )
  {
    if ( v38 != -1073741637 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 35, &WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids, a15, v37);
      }
      v24 = -1073741616;
      goto LABEL_26;
    }
    v39 = 0x7FFFFFFFFFFFFFFFLL;
  }
  else
  {
    v39 = (__int64)SystemTime;
  }
  *(_QWORD *)pvContextBuffer = v39;
  if ( a13 )
  {
    pvContextBuffer = 0;
    v40 = QueryContextAttributesW(phContext, 0xAu, &pvContextBuffer);
    if ( MapSecurityError(v40) >= 0 )
    {
      v41 = pvContextBuffer;
      if ( pvContextBuffer )
      {
        *a13 = *((_WORD *)pvContextBuffer + 3);
        FreeContextBuffer(v41);
      }
    }
  }
  v24 = 0;
LABEL_56:
  v34 = v54;
  if ( (unsigned int)v54 <= v53 )
    goto LABEL_57;
LABEL_58:
  if ( MEMORY[0xFFFFF78000000014] - v64 > 50000000 && (byte_14004C339 & 0x10) != 0 )
    McTemplateK0hxxxx_EtwWriteTransfer(
      (unsigned __int64)(v65 - v64 + ((unsigned __int128)((v65 - v64) * (__int128)(__int64)0xD6BF94D5E57A42BDuLL) >> 64)) >> 63,
      (v63 - v64) / 10000000,
      (v65 - v64) / 10000000,
      1,
      (v63 - v64) / 10000000,
      (v65 - v64) / 10000000,
      (MEMORY[0xFFFFF78000000014] - v64) / 10000000);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x140095748  mov     [rsp-8+arg_10], rbx
0x14009574d  push    rbp
0x14009574e  push    rsi
0x14009574f  push    rdi
0x140095750  push    r12
0x140095752  push    r13
0x140095754  push    r14
0x140095756  push    r15
0x140095758  lea     rbp, [rsp-0B0h]
0x140095760  sub     rsp, 1B0h
0x140095767  mov     rax, cs:__security_cookie
0x14009576e  xor     rax, rsp
0x140095771  mov     [rbp+0E0h+var_40], rax
0x140095778  mov     rax, [rbp+0E0h+arg_38]
0x14009577f  xor     ebx, ebx
0x140095781  mov     r15, [rbp+0E0h+arg_58]
0x140095788  xorps   xmm0, xmm0
0x14009578b  mov     r12, [rbp+0E0h+arg_60]
0x140095792  mov     rsi, rdx
0x140095795  mov     rdx, [rbp+0E0h+arg_28]
0x14009579c  mov     rdi, rcx
0x14009579f  mov     rcx, [rbp+0E0h+arg_50]
0x1400957a6  xorps   xmm1, xmm1
0x1400957a9  mov     r13, [rbp+0E0h+arg_40]
0x1400957b0  mov     r14, [rbp+0E0h+arg_70]
0x1400957b7  mov     r10d, [rdx]
0x1400957ba  mov     [rsp+1E0h+pvContextBuffer], rax
0x1400957bf  mov     rax, [rbp+0E0h+arg_30]
0x1400957c6  mov     [rsp+1E0h+SystemTime], rax
0x1400957cb  mov     rax, [rbp+0E0h+arg_48]
0x1400957d2  mov     [rbp+0E0h+AuthenticationId], rax
0x1400957d6  mov     rax, 0FFFFF78000000014h
0x1400957e0  mov     [rsp+1E0h+pBuffer], ebx
0x1400957e4  mov     [rsp+1E0h+var_18C], ebx
0x1400957e8  mov     qword ptr [rbp+0E0h+LocalTime], rbx
0x1400957ec  mov     [rbp+0E0h+var_110], rdx
0x1400957f0  mov     [rbp+0E0h+var_118], rcx
0x1400957f4  mov     [rsp+1E0h+var_16C], r10d
0x1400957f9  movups  xmmword ptr [rbp+0E0h+pInput.ulVersion], xmm0
0x1400957fd  movups  xmmword ptr [rbp+0E0h+var_140.ulVersion], xmm1
0x140095801  movups  [rsp+1E0h+var_168], xmm0
0x140095806  mov     rax, [rax]
0x140095809  mov     [rcx], bl
0x14009580b  mov     [r15], bl
0x14009580e  mov     [rdx], ebx
0x140095810  mov     [rbp+0E0h+var_100], rax
0x140095814  test    r12, r12
0x140095817  jz      short loc_140095820
0x140095819  mov     word ptr [r12], 0FFFFh
0x140095820  lea     rax, [rbp+0E0h+var_F0]
0x140095824  mov     ecx, 2
0x140095829  mov     [rbp+0E0h+pInput.pBuffers], rax
0x14009582d  mov     rax, [rbp+0E0h+arg_68]
0x140095834  test    rax, rax
0x140095837  jz      short loc_140095850
0x140095839  mov     [rbp+0E0h+pInput.cBuffers], ecx
0x14009583c  mov     [rbp+0E0h+var_D8], rax
0x140095840  mov     [rbp+0E0h+var_E0], 20h ; ' '
0x140095847  mov     [rbp+0E0h+var_DC], 81h
0x14009584e  jmp     short loc_140095857
0x140095850  mov     [rbp+0E0h+pInput.cBuffers], 1
0x140095857  mov     [rbp+0E0h+var_E8], r8
0x14009585b  lea     rax, [rsp+1E0h+var_168]
0x140095860  mov     [rbp+0E0h+var_140.pBuffers], rax
0x140095864  mov     r8d, 442h
0x14009586a  mov     rax, [rbp+0E0h+arg_20]
0x140095871  mov     dl, 7
0x140095873  mov     qword ptr [rbp+0E0h+var_168+8], rax
0x140095877  mov     rax, cs:Srv2Statistics
0x14009587e  mov     [rbp+0E0h+var_F0], r9d
0x140095882  lea     r9, aSmb2validatese; "Smb2ValidateSecurityBuffer"
0x140095889  mov     [rbp+0E0h+var_EC], ecx
0x14009588c  mov     dword ptr [rsp+1E0h+var_168+4], ecx
0x140095890  lea     rcx, [r14+248h]
0x140095897  mov     [rbp+0E0h+pInput.ulVersion], ebx
0x14009589a  mov     [rbp+0E0h+var_140.cBuffers], 1
0x1400958a1  mov     [rbp+0E0h+var_140.ulVersion], ebx
0x1400958a4  mov     dword ptr [rsp+1E0h+var_168], r10d
0x1400958a9  mov     [rsp+1E0h+var_18C], ebx
0x1400958ad  inc     dword ptr [rax+18h]
0x1400958b0  mov     byte ptr [rsp+1E0h+TargetDataRep], 1
0x1400958b5  call    SRV2_PERF_ENTER_EX
0x1400958ba  mov     dl, 1; Wait
0x1400958bc  lea     rcx, Smb2ExtensibleCredHandleLock; Resource
0x1400958c3  call    cs:__imp_ExAcquireResourceSharedLite
0x1400958ca  nop     dword ptr [rax+rax+00h]
0x1400958cf  mov     rcx, 0FFFFF78000000014h
0x1400958d9  mov     rax, [rcx]
0x1400958dc  mov     [rbp+0E0h+var_108], rax
0x1400958e0  cmp     [rdi], rbx
0x1400958e3  jnz     short loc_1400958EB
0x1400958e5  cmp     [rdi+8], rbx
0x1400958e9  jz      short loc_1400958EE
0x1400958eb  mov     rbx, rdi
0x1400958ee  mov     rcx, cs:Smb2ExtensibleCredentialHandle
0x1400958f5  call    cs:__imp_SrvLibQueryCredentialHandle
0x1400958fc  nop     dword ptr [rax+rax+00h]
0x140095901  mov     r9d, 908001h; fContextReq
0x140095907  lea     r8, [rbp+0E0h+pInput]; pInput
0x14009590b  mov     rcx, rax; phCredential
0x14009590e  mov     rdx, rbx; phContext
0x140095911  lea     rax, [rbp+0E0h+LocalTime]
0x140095915  mov     [rsp+1E0h+ptsExpiry], rax; ptsExpiry
0x14009591a  lea     rax, [rsp+1E0h+var_18C]
0x14009591f  mov     [rsp+1E0h+pfContextAttr], rax; pfContextAttr
0x140095924  lea     rax, [rbp+0E0h+var_140]
0x140095928  mov     [rsp+1E0h+pOutput], rax; pOutput
0x14009592d  mov     [rsp+1E0h+phNewContext], rdi; phNewContext
0x140095932  mov     [rsp+1E0h+TargetDataRep], 10h; TargetDataRep
0x14009593a  call    cs:__imp_AcceptSecurityContext
0x140095941  nop     dword ptr [rax+rax+00h]
0x140095946  mov     ebx, eax
0x140095948  lea     rcx, Smb2ExtensibleCredHandleLock; Resource
0x14009594f  mov     rax, 0FFFFF78000000014h
0x140095959  mov     rax, [rax]
0x14009595c  mov     [rbp+0E0h+var_F8], rax
0x140095960  call    cs:__imp_ExReleaseResourceLite
0x140095967  nop     dword ptr [rax+rax+00h]
0x14009596c  lea     r9, aSmb2validatese; "Smb2ValidateSecurityBuffer"
0x140095973  mov     byte ptr [rsp+1E0h+TargetDataRep], 1
0x140095978  xor     edx, edx
0x14009597a  lea     rcx, [r14+248h]
0x140095981  mov     r8d, 458h
0x140095987  call    SRV2_PERF_ENTER_EX
0x14009598c  mov     ecx, ebx; SecStatus
0x14009598e  call    cs:__imp_MapSecurityError
0x140095995  nop     dword ptr [rax+rax+00h]
0x14009599a  mov     ebx, eax
0x14009599c  cmp     eax, 0C0000008h
0x1400959a1  jz      loc_140095DFC
0x1400959a7  cmp     eax, 0C00000FEh
0x1400959ac  jz      loc_140095DFC
0x1400959b2  test    eax, eax
0x1400959b4  js      loc_140095E01
0x1400959ba  jnz     loc_140095E58
0x1400959c0  mov     rcx, [rsi+18h]
0x1400959c4  xor     edx, edx
0x1400959c6  add     rcx, 50h ; 'P'
0x1400959ca  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400959d1  nop     dword ptr [rax+rax+00h]
0x1400959d6  mov     rax, [rsi+18h]
0x1400959da  xor     edx, edx
0x1400959dc  cmp     dword ptr [rax+0Ch], 0DDh
0x1400959e3  jnz     short loc_1400959FF
0x1400959e5  lea     rcx, [rax+50h]
0x1400959e9  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400959f0  nop     dword ptr [rax+rax+00h]
0x1400959f5  mov     eax, 0C000035Ch
0x1400959fa  jmp     loc_140095F55
0x1400959ff  mov     dword ptr [rax+0Ch], 0DCh
0x140095a06  mov     rcx, [rsi+18h]
0x140095a0a  add     rcx, 50h ; 'P'
0x140095a0e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140095a15  nop     dword ptr [rax+rax+00h]
0x140095a1a  mov     rdx, [rsp+1E0h+SystemTime]; SystemTime
0x140095a1f  lea     rcx, [rbp+0E0h+LocalTime]; LocalTime
0x140095a23  call    cs:__imp_ExLocalTimeToSystemTime
0x140095a2a  nop     dword ptr [rax+rax+00h]
0x140095a2f  lea     r8, [rsp+1E0h+pBuffer]; pBuffer
0x140095a34  mov     edx, 25h ; '%'; ulAttribute
0x140095a39  mov     rcx, rdi; phContext
0x140095a3c  call    cs:__imp_QueryContextAttributesW
0x140095a43  nop     dword ptr [rax+rax+00h]
0x140095a48  mov     ecx, eax; SecStatus
0x140095a4a  call    cs:__imp_MapSecurityError
0x140095a51  nop     dword ptr [rax+rax+00h]
0x140095a56  mov     ebx, eax
0x140095a58  cmp     eax, 0C00000BBh
0x140095a5d  jnz     short loc_140095A65
0x140095a5f  mov     byte ptr [r15], 0
0x140095a63  jmp     short loc_140095A6D
0x140095a65  test    eax, eax
0x140095a67  js      loc_140095BE7
0x140095a6d  cmp     [rsp+1E0h+pBuffer], 0
0x140095a72  jz      short loc_140095A78
0x140095a74  mov     byte ptr [r15], 1
0x140095a78  lea     r9, aSmb2validatese; "Smb2ValidateSecurityBuffer"
0x140095a7f  mov     byte ptr [rsp+1E0h+TargetDataRep], 1
0x140095a84  mov     r8d, 48Fh
0x140095a8a  lea     rcx, [r14+248h]
0x140095a91  mov     dl, 7
0x140095a93  call    SRV2_PERF_ENTER_EX
0x140095a98  mov     r8, r13; pBuffer
0x140095a9b  mov     edx, 9; ulAttribute
0x140095aa0  mov     rcx, rdi; phContext
0x140095aa3  call    cs:__imp_QueryContextAttributesW
0x140095aaa  nop     dword ptr [rax+rax+00h]
0x140095aaf  lea     r9, aSmb2validatese; "Smb2ValidateSecurityBuffer"
0x140095ab6  mov     byte ptr [rsp+1E0h+TargetDataRep], 1
0x140095abb  xor     edx, edx
0x140095abd  lea     rcx, [r14+248h]
0x140095ac4  mov     r8d, 495h
0x140095aca  mov     ebx, eax
0x140095acc  call    SRV2_PERF_ENTER_EX
0x140095ad1  mov     ecx, ebx; SecStatus
0x140095ad3  call    cs:__imp_MapSecurityError
0x140095ada  nop     dword ptr [rax+rax+00h]
0x140095adf  xor     r8d, r8d
0x140095ae2  mov     ebx, eax
0x140095ae4  test    eax, eax
0x140095ae6  js      loc_140095BE7
0x140095aec  mov     eax, cs:dword_1400583B0
0x140095af2  cmp     eax, 5
0x140095af5  jbe     loc_140095BC0
0x140095afb  mov     rdx, 400000000000h
0x140095b05  lea     rcx, dword_1400583B0
0x140095b0c  call    _tlgKeywordOn
0x140095b11  test    al, al
0x140095b13  jz      loc_140095BC0
0x140095b19  lea     rax, [rbp+0E0h+var_130]
0x140095b1d  mov     [rbp+0E0h+var_130], 2000000h
0x140095b25  mov     [rbp+0E0h+var_90], rax
0x140095b29  lea     r9d, [r8+7]; int
0x140095b2d  lea     rax, [rbp+0E0h+var_128]
0x140095b31  mov     [rbp+0E0h+var_88], 8
0x140095b39  mov     [rbp+0E0h+var_80], rax
0x140095b3d  lea     rdx, dword_140043447; int
0x140095b44  mov     eax, [r13+0]
0x140095b48  mov     [rsp+1E0h+var_190], eax
0x140095b4c  lea     rax, [rsp+1E0h+var_190]
0x140095b51  mov     [rbp+0E0h+var_70], rax
0x140095b55  mov     eax, [rsi+124h]
0x140095b5b  mov     [rsp+1E0h+var_170], eax
0x140095b5f  lea     rax, [rsp+1E0h+var_170]
0x140095b64  mov     [rbp+0E0h+var_60], rax
0x140095b6b  mov     eax, cs:Smb2MinSessionKeyCbLength
0x140095b71  mov     dword ptr [rsp+1E0h+SystemTime], eax
0x140095b75  lea     rax, [rsp+1E0h+SystemTime]
0x140095b7a  mov     [rbp+0E0h+var_50], rax
0x140095b81  lea     rax, [rbp+0E0h+var_B0]
0x140095b85  mov     qword ptr [rsp+1E0h+TargetDataRep], rax; PEVENT_DATA_DESCRIPTOR
0x140095b8a  mov     [rbp+0E0h+var_128], 1
0x140095b92  mov     [rbp+0E0h+var_78], 8
0x140095b9a  mov     [rbp+0E0h+var_68], 4
0x140095ba2  mov     [rbp+0E0h+var_58], 4
0x140095bad  mov     [rbp+0E0h+var_48], 4
0x140095bb8  call    _tlgWriteAgg
0x140095bbd  xor     r8d, r8d
0x140095bc0  cmp     [r15], r8b
0x140095bc3  jnz     short loc_140095BF2
0x140095bc5  mov     eax, cs:Smb2MinSessionKeyCbLength
0x140095bcb  cmp     [r13+0], eax
0x140095bcf  jnb     short loc_140095BF2
0x140095bd1  mov     r9, r13
0x140095bd4  mov     r8, rdi
0x140095bd7  mov     rdx, rsi
0x140095bda  mov     rcx, r14
0x140095bdd  call    Smb2LogTooShortKeyError
0x140095be2  mov     ebx, 0C0000517h
0x140095be7  xor     eax, eax
0x140095be9  mov     dword ptr [rsp+1E0h+var_168], eax
0x140095bed  jmp     loc_140095EAE
0x140095bf2  mov     rcx, rdi; phContext
0x140095bf5  call    cs:__imp_ImpersonateSecurityContext
0x140095bfc  nop     dword ptr [rax+rax+00h]
0x140095c01  mov     ebx, eax
0x140095c03  test    eax, eax
0x140095c05  js      short loc_140095BE7
0x140095c07  xorps   xmm0, xmm0
0x140095c0a  mov     byte ptr [rsp+1E0h+TargetDataRep], 1
0x140095c0f  lea     rsi, [r14+248h]
0x140095c16  mov     r8d, 4BBh
0x140095c1c  mov     rcx, rsi
0x140095c1f  lea     r9, aSmb2validatese; "Smb2ValidateSecurityBuffer"
0x140095c26  mov     dl, 7
0x140095c28  movups  xmmword ptr [rbp+0E0h+SubjectContext.ClientToken], xmm0
0x140095c2c  movups  xmmword ptr [rbp+0E0h+SubjectContext.PrimaryToken], xmm0
0x140095c30  call    SRV2_PERF_ENTER_EX
0x140095c35  lea     rcx, [rbp+0E0h+SubjectContext]; SubjectContext
0x140095c39  call    cs:__imp_SeCaptureSubjectContext
0x140095c40  nop     dword ptr [rax+rax+00h]
0x140095c45  lea     rcx, [rbp+0E0h+SubjectContext]; SubjectContext
0x140095c49  call    cs:__imp_SeLockSubjectContext
0x140095c50  nop     dword ptr [rax+rax+00h]
0x140095c55  mov     rdx, [rbp+0E0h+AuthenticationId]; AuthenticationId
0x140095c59  mov     rcx, [rbp+0E0h+SubjectContext.ClientToken]; Token
0x140095c5d  call    cs:__imp_SeQueryAuthenticationIdToken
0x140095c64  nop     dword ptr [rax+rax+00h]
0x140095c69  mov     ecx, eax; SecStatus
0x140095c6b  call    cs:__imp_MapSecurityError
0x140095c72  nop     dword ptr [rax+rax+00h]
0x140095c77  lea     rcx, [rbp+0E0h+SubjectContext]; SubjectContext
0x140095c7b  mov     ebx, eax
0x140095c7d  call    cs:__imp_SeUnlockSubjectContext
0x140095c84  nop     dword ptr [rax+rax+00h]
0x140095c89  lea     rcx, [rbp+0E0h+SubjectContext]; SubjectContext
0x140095c8d  call    cs:__imp_SeReleaseSubjectContext
0x140095c94  nop     dword ptr [rax+rax+00h]
0x140095c99  lea     r9, aSmb2validatese; "Smb2ValidateSecurityBuffer"
0x140095ca0  mov     byte ptr [rsp+1E0h+TargetDataRep], 1
0x140095ca5  xor     edx, edx
0x140095ca7  mov     r8d, 4CBh
0x140095cad  mov     rcx, rsi
0x140095cb0  call    SRV2_PERF_ENTER_EX
0x140095cb5  mov     rcx, rdi; phContext
0x140095cb8  call    cs:__imp_RevertSecurityContext
0x140095cbf  nop     dword ptr [rax+rax+00h]
0x140095cc4  test    ebx, ebx
0x140095cc6  js      loc_140095BE7
0x140095ccc  lea     r8, [rsp+1E0h+var_190]; pBuffer
  ... truncated ...
```
