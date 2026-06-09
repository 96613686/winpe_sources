# AipCreateProcessNotifyRoutine

- ea: `0x1400373b0`
- end: `0x140037ab6`
- name: `AipCreateProcessNotifyRoutine`
- size: `1798`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x140036f60`

## callees

- `0x140001550`
- `0x140001590`
- `0x140001970`
- `0x140002070`
- `0x140006a20`
- `0x14001f9f0`
- `0x140027560`
- `0x140029678`
- `0x140030ff0`
- `0x140032dc0`
- `0x140032e40`
- `0x1400331f0`
- `0x140033dc0`
- `0x140035250`
- `0x140035580`
- `0x140036af0`
- `0x1400373b0`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x14003744c`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x14003744c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003766f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037685`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400377d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037a38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037a4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003766f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037685`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400377d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037a38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037a4f`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x140037426`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x140037426`
- `ntoskrnl!ExAllocatePool2` at `0x14003770a`
- `ntoskrnl!ExAllocatePool2` at `0x14003770a`
- `ntoskrnl!EtwWrite` at `0x1400379e4`
- `ntoskrnl!EtwWrite` at `0x1400379e4`
- `ntoskrnl!ZwQueryInformationToken` at `0x14003756e`
- `ntoskrnl!ZwQueryInformationToken` at `0x14003756e`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140037479`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140037479`
- `ntoskrnl!ZwClose` at `0x1400377eb`
- `ntoskrnl!ZwClose` at `0x140037804`
- `ntoskrnl!ZwClose` at `0x140037819`
- `ntoskrnl!ZwClose` at `0x1400377eb`
- `ntoskrnl!ZwClose` at `0x140037804`
- `ntoskrnl!ZwClose` at `0x140037819`
- `ntoskrnl!EtwWriteTransfer` at `0x140037967`
- `ntoskrnl!EtwWriteTransfer` at `0x140037967`

## pseudocode

```c
NTSTATUS __fastcall AipCreateProcessNotifyRoutine(__int64 a1, PVOID *a2, __int64 a3, __int64 a4, __int64 a5)
{
  HANDLE v5; // r15
  HANDLE v7; // rsi
  NTSTATUS result; // eax
  __int64 v9; // r14
  __int64 PerformanceCounter; // rbx
  NTSTATUS IsTokenService; // edi
  int v12; // r12d
  int Tokens; // eax
  __int64 v14; // rbx
  __int64 v15; // rcx
  int AppxAttributes; // eax
  __int64 v17; // r9
  _QWORD *v18; // rbx
  void *v19; // rcx
  char *v20; // rbx
  char v21; // bl
  int v22; // ecx
  _QWORD *Pool2; // rax
  void *v24; // r13
  __int64 v25; // rbx
  PVOID *v26; // rdx
  int v27; // r8d
  PVOID *v28; // rsi
  PVOID *v29; // rbx
  unsigned __int16 v30; // ax
  NTSTATUS v31; // eax
  int v32; // r8d
  __int64 v33; // rcx
  char v34[4]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v35[2]; // [rsp+64h] [rbp-9Ch] BYREF
  char v36[8]; // [rsp+68h] [rbp-98h] BYREF
  NTSTATUS TokenInformation; // [rsp+70h] [rbp-90h] BYREF
  ULONG ReturnLength; // [rsp+78h] [rbp-88h] BYREF
  HANDLE TokenHandle; // [rsp+80h] [rbp-80h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp-78h] BYREF
  PVOID *v41; // [rsp+90h] [rbp-70h]
  char v42[8]; // [rsp+98h] [rbp-68h]
  __int64 v43; // [rsp+A0h] [rbp-60h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+A8h] [rbp-58h] BYREF
  PVOID P[2]; // [rsp+B8h] [rbp-48h] BYREF
  PVOID v46[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE UserData[24]; // [rsp+E0h] [rbp-20h] BYREF
  int v48; // [rsp+F8h] [rbp-8h]
  int v49; // [rsp+FCh] [rbp-4h]
  NTSTATUS *p_TokenInformation; // [rsp+100h] [rbp+0h]
  __int64 v51; // [rsp+108h] [rbp+8h]
  _WORD *v52; // [rsp+110h] [rbp+10h]
  __int64 v53; // [rsp+118h] [rbp+18h]

  v5 = 0;
  v43 = a4;
  *(_QWORD *)&EventDescriptor.Id = a3;
  v41 = a2;
  *(_QWORD *)v42 = a1;
  TokenHandle = 0;
  v7 = 0;
  Handle = 0;
  v36[0] = 0;
  LOBYTE(v35[0]) = 0;
  *(_QWORD *)UserData = 0;
  *(_OWORD *)P = 0;
  v34[0] = 0;
  *(_OWORD *)v46 = 0;
  result = RtlRunOnceExecuteOnce(&AipInitRunOnceState, AipInitRunOnce, 0, 0);
  if ( result < 0 )
    return result;
  v9 = 0;
  ExEnterCriticalRegionAndAcquireResourceShared(&stru_140019300);
  if ( qword_1400193F8 )
  {
    _InterlockedIncrement((volatile signed __int32 *)qword_1400193F8);
    v9 = qword_1400193F8 + 8;
  }
  ExReleaseResourceAndLeaveCriticalRegion(&stru_140019300);
  if ( !v9 )
    return -1073740956;
  PerformanceCounter = AiQueryPerformanceCounter(0, 0);
  IsTokenService = AiCapturePackageMoniker(a4, v36, v35, P);
  AiUpdatePerfTime(qword_1400196D0, PerformanceCounter, 0);
  v12 = (unsigned __int8)v36[0];
  if ( IsTokenService >= 0 )
  {
    if ( v36[0]
      && !*(_BYTE *)(v9 + 308)
      && (*(int *)(v9 + 128) < 0 || !*(_DWORD *)(*(_QWORD *)(v9 + 136) + 12LL))
      && (unsigned __int8)SrpIsOnlySmartLockerEnabledForPolicyType(v9, 0) )
    {
      IsTokenService = 0;
      goto LABEL_42;
    }
    Tokens = AiGetTokens(*(void **)v42, &TokenHandle, UserData);
    v5 = TokenHandle;
    IsTokenService = Tokens;
    if ( Tokens < 0
      || (ReturnLength = 0,
          TokenInformation = 0,
          IsTokenService = ZwQueryInformationToken(TokenHandle, TokenSandBoxInert, &TokenInformation, 4u, &ReturnLength),
          IsTokenService < 0)
      || TokenInformation
      || (IsTokenService = SrpIsTokenService(v5, v34), IsTokenService < 0)
      || (v14 = AiQueryPerformanceCounter(0, 0),
          IsTokenService = AiOpenImageFile(v41, *(_QWORD *)&EventDescriptor.Id, &Handle),
          AiUpdatePerfTime(qword_140019640, v14, 0),
          IsTokenService < 0) )
    {
      v7 = *(HANDLE *)UserData;
      goto LABEL_42;
    }
    v7 = *(HANDLE *)UserData;
    if ( (_BYTE)v12 )
    {
      LOBYTE(v15) = 1;
      TokenHandle = 0;
      *(_OWORD *)UserData = 0;
      AiEnsureServiceRunning(v15);
      AppxAttributes = AipkGetAppxAttributes((int)P, (__int64)&TokenHandle);
      v18 = TokenHandle;
      if ( AppxAttributes >= 0 )
      {
        *(_OWORD *)v46 = *(_OWORD *)UserData;
        if ( (int)AiSetTokenAttributes(v5, TokenHandle) >= 0 && v7 != v5 )
          AiSetTokenAttributes(v7, v18);
      }
      if ( v18 )
      {
        v19 = (void *)*(v18 - 6);
        v20 = (char *)(v18 - 8);
        if ( v19 )
          ExFreePoolWithTag(v19, 0);
        if ( v20 )
          ExFreePoolWithTag(v20, 0);
      }
LABEL_35:
      *(_QWORD *)UserData = a4;
      *(_QWORD *)&UserData[12] = 0;
      *(_DWORD *)&UserData[20] = 0;
      *(_DWORD *)&UserData[8] = -1073741823;
      Pool2 = (_QWORD *)ExAllocatePool2(258, 80, 1145663553, v17);
      v24 = Pool2;
      if ( Pool2 )
      {
        Pool2[7] = a5;
        Pool2[4] = v43;
        Pool2[5] = *(_QWORD *)v42;
        Pool2[8] = UserData;
        Pool2[6] = v7;
        v25 = AiQueryPerformanceCounter(0, 0);
        if ( (_BYTE)v12 )
        {
          v26 = v46;
          v27 = 0;
        }
        else
        {
          v27 = (int)v41;
          v26 = 0;
        }
        IsTokenService = SrpVerifyProcess(
                           (int)v7,
                           (int)v5,
                           v9,
                           v27,
                           v42[0],
                           v12,
                           (__int64)v26,
                           (__int64)v24,
                           v34[0],
                           *(PFILE_OBJECT *)&EventDescriptor.Id,
                           Handle);
        AiUpdatePerfTime(qword_1400196C0, v25, 0);
        ExFreePoolWithTag(v24, 0);
      }
      else
      {
        IsTokenService = -1073741801;
      }
      goto LABEL_42;
    }
    v21 = v34[0];
    v22 = *(_DWORD *)(*(_QWORD *)(v9 + 40) + 24LL) & 0xC;
    if ( v34[0] )
    {
      if ( v22 )
      {
LABEL_33:
        if ( !(unsigned __int8)SrpIsOnlySmartLockerEnabledForPolicyType(v9, 0) )
          AiSetAttributesExe(v9, (_DWORD)Handle, (_DWORD)v5, (_DWORD)v7, v21);
        goto LABEL_35;
      }
    }
    else if ( v22 != 8 )
    {
      goto LABEL_33;
    }
    if ( !*(_BYTE *)(v9 + 260) )
      goto LABEL_42;
    goto LABEL_33;
  }
LABEL_42:
  if ( v5 )
    ZwClose(v5);
  if ( v7 && v7 != v5 )
    ZwClose(v7);
  if ( Handle )
    ZwClose(Handle);
  if ( (int)(IsTokenService + 0x80000000) >= 0 && IsTokenService != -1073740956 )
  {
    v28 = v41;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_ZD(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        (unsigned int)WPP_c7f28e522d5a3d44ab43fad3c67cb075_Traceguids,
        (_DWORD)v41,
        IsTokenService);
    if ( (unsigned int)dword_140019000 > 4
      && (qword_140019010 & 0x200000000000LL) != 0
      && (qword_140019018 & 0x200000000000LL) == qword_140019018 )
    {
      EventDescriptor.Keyword = 0x200000000000LL;
      v51 = 8;
      LOBYTE(v35[0]) = v12;
      v53 = 1;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      v43 = IsTokenService;
      p_TokenInformation = (NTSTATUS *)&v43;
      v52 = v35;
      *(_DWORD *)&EventDescriptor.Level = 4;
      *(_QWORD *)UserData = EventInformation;
      *(_DWORD *)&UserData[8] = *(unsigned __int16 *)EventInformation;
      *(_QWORD *)&UserData[16] = byte_140015E49;
      *(_DWORD *)&UserData[12] = 2;
      v48 = 45;
      v49 = 1;
      ReturnLength = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, (PEVENT_DATA_DESCRIPTOR)UserData);
    }
    v29 = P;
    TokenInformation = IsTokenService;
    *(_QWORD *)&UserData[8] = 2;
    if ( !(_BYTE)v12 )
      v29 = v28;
    v49 = 0;
    v51 = 4;
    v30 = *(_WORD *)v29;
    v48 = *(unsigned __int16 *)v29;
    v35[0] = v30 >> 1;
    *(_QWORD *)UserData = v35;
    *(_QWORD *)&UserData[16] = v29[1];
    p_TokenInformation = &TokenInformation;
    v31 = EtwWrite(
            (REGHANDLE)WPP_MAIN_CB.Queue.ListEntry.Blink,
            &AppIdNewProcessFailed,
            0,
            3u,
            (PEVENT_DATA_DESCRIPTOR)UserData);
    if ( v31 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      WPP_SF_ZDD(WPP_GLOBAL_Control->AttachedDevice, 13, v32, (_DWORD)v29, TokenInformation, v31);
    }
  }
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0);
  if ( v46[1] )
    ExFreePoolWithTag(v46[1], 0);
  if ( IsTokenService < 0 )
  {
    v33 = 261;
    if ( (_BYTE)v12 )
      v33 = 309;
    if ( !*(_BYTE *)(v33 + v9) )
      IsTokenService = 0;
  }
  ReleasePolicyRef((PVOID)(v9 - 8));
  return IsTokenService;
}

```

## disassembly

```asm
0x1400373b0  push    rbp
0x1400373b2  push    rsi
0x1400373b3  push    r13
0x1400373b5  push    r15
0x1400373b7  lea     rbp, [rsp-58h]
0x1400373bc  sub     rsp, 158h
0x1400373c3  mov     rax, cs:__security_cookie
0x1400373ca  xor     rax, rsp
0x1400373cd  mov     [rbp+70h+var_50], rax
0x1400373d1  xor     r15d, r15d
0x1400373d4  mov     [rbp+70h+var_D0], r9
0x1400373d8  mov     r13, r9
0x1400373db  mov     qword ptr [rbp+70h+EventDescriptor.Id], r8
0x1400373df  mov     [rbp+70h+var_E0], rdx
0x1400373e3  xorps   xmm0, xmm0
0x1400373e6  mov     qword ptr [rbp+70h+var_D8], rcx
0x1400373ea  lea     rdx, AipInitRunOnce; InitFn
0x1400373f1  xorps   xmm1, xmm1
0x1400373f4  mov     [rbp+70h+TokenHandle], r15
0x1400373f8  xor     esi, esi
0x1400373fa  mov     [rbp+70h+Handle], r15
0x1400373fe  xor     r9d, r9d; Context
0x140037401  mov     [rsp+170h+var_108], r15b
0x140037406  xor     r8d, r8d; Parameter
0x140037409  mov     byte ptr [rsp+170h+var_10C], r15b
0x14003740e  lea     rcx, AipInitRunOnceState; RunOnce
0x140037415  mov     [rbp+70h+var_90.Ptr], rsi
0x140037419  movups  xmmword ptr [rbp+70h+P], xmm0
0x14003741d  mov     [rsp+170h+var_110], sil
0x140037422  movups  xmmword ptr [rbp+70h+var_A0], xmm1
0x140037426  call    cs:__imp_RtlRunOnceExecuteOnce
0x14003742d  nop     dword ptr [rax+rax+00h]
0x140037432  test    eax, eax
0x140037434  js      loc_140037A9B
0x14003743a  mov     [rsp+170h+var_38], r14
0x140037442  lea     rcx, stru_140019300; Resource
0x140037449  xor     r14d, r14d
0x14003744c  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceShared
0x140037453  nop     dword ptr [rax+rax+00h]
0x140037458  mov     rax, cs:qword_1400193F8
0x14003745f  test    rax, rax
0x140037462  jz      short loc_140037472
0x140037464  lock inc dword ptr [rax]
0x140037467  mov     r14, cs:qword_1400193F8
0x14003746e  add     r14, 8
0x140037472  lea     rcx, stru_140019300; Resource
0x140037479  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140037480  nop     dword ptr [rax+rax+00h]
0x140037485  test    r14, r14
0x140037488  jnz     short loc_140037494
0x14003748a  mov     eax, 0C0000364h
0x14003748f  jmp     loc_140037A93
0x140037494  mov     [rsp+170h+var_20], rbx
0x14003749c  xor     edx, edx
0x14003749e  mov     [rsp+170h+var_28], rdi
0x1400374a6  xor     ecx, ecx
0x1400374a8  mov     [rsp+170h+var_30], r12
0x1400374b0  call    AiQueryPerformanceCounter
0x1400374b5  lea     r9, [rbp+70h+P]
0x1400374b9  mov     rcx, r13
0x1400374bc  lea     r8, [rsp+170h+var_10C]
0x1400374c1  mov     rbx, rax
0x1400374c4  lea     rdx, [rsp+170h+var_108]
0x1400374c9  call    AiCapturePackageMoniker
0x1400374ce  xor     r8d, r8d
0x1400374d1  lea     rcx, qword_1400196D0
0x1400374d8  mov     rdx, rbx
0x1400374db  mov     edi, eax
0x1400374dd  call    AiUpdatePerfTime
0x1400374e2  movzx   r12d, [rsp+170h+var_108]
0x1400374e8  test    edi, edi
0x1400374ea  js      loc_1400377E3
0x1400374f0  test    r12b, r12b
0x1400374f3  jz      short loc_140037528
0x1400374f5  cmp     [r14+134h], sil
0x1400374fc  jnz     short loc_140037528
0x1400374fe  cmp     [r14+80h], esi
0x140037505  jl      short loc_140037513
0x140037507  mov     rax, [r14+88h]
0x14003750e  cmp     [rax+0Ch], esi
0x140037511  jnz     short loc_140037528
0x140037513  xor     edx, edx
0x140037515  mov     rcx, r14
0x140037518  call    SrpIsOnlySmartLockerEnabledForPolicyType
0x14003751d  test    al, al
0x14003751f  jz      short loc_140037528
0x140037521  xor     edi, edi
0x140037523  jmp     loc_1400377E3
0x140037528  mov     rcx, qword ptr [rbp+70h+var_D8]
0x14003752c  lea     r8, [rbp+70h+var_90]
0x140037530  lea     rdx, [rbp+70h+TokenHandle]
0x140037534  call    AiGetTokens
0x140037539  mov     r15, [rbp+70h+TokenHandle]
0x14003753d  mov     edi, eax
0x14003753f  test    eax, eax
0x140037541  js      loc_1400377DF
0x140037547  xor     eax, eax
0x140037549  lea     r8, [rsp+170h+TokenInformation]; TokenInformation
0x14003754e  mov     [rsp+170h+var_F8], eax
0x140037552  mov     r9d, 4; TokenInformationLength
0x140037558  mov     [rsp+170h+TokenInformation], eax
0x14003755c  mov     edx, 0Fh; TokenInformationClass
0x140037561  lea     rax, [rsp+170h+var_F8]
0x140037566  mov     rcx, r15; TokenHandle
0x140037569  mov     [rsp+170h+ReturnLength], rax; ReturnLength
0x14003756e  call    cs:__imp_ZwQueryInformationToken
0x140037575  nop     dword ptr [rax+rax+00h]
0x14003757a  mov     edi, eax
0x14003757c  test    eax, eax
0x14003757e  js      loc_1400377DF
0x140037584  cmp     [rsp+170h+TokenInformation], esi
0x140037588  jnz     loc_1400377DF
0x14003758e  lea     rdx, [rsp+170h+var_110]
0x140037593  mov     rcx, r15
0x140037596  call    SrpIsTokenService
0x14003759b  mov     edi, eax
0x14003759d  test    eax, eax
0x14003759f  js      loc_1400377DF
0x1400375a5  xor     edx, edx
0x1400375a7  xor     ecx, ecx
0x1400375a9  call    AiQueryPerformanceCounter
0x1400375ae  mov     rdx, qword ptr [rbp+70h+EventDescriptor.Id]
0x1400375b2  lea     r8, [rbp+70h+Handle]
0x1400375b6  mov     rcx, [rbp+70h+var_E0]
0x1400375ba  mov     rbx, rax
0x1400375bd  call    AiOpenImageFile
0x1400375c2  xor     r8d, r8d
0x1400375c5  lea     rcx, qword_140019640
0x1400375cc  mov     rdx, rbx
0x1400375cf  mov     edi, eax
0x1400375d1  call    AiUpdatePerfTime
0x1400375d6  test    edi, edi
0x1400375d8  js      loc_1400377DF
0x1400375de  mov     rsi, [rbp+70h+var_90.Ptr]
0x1400375e2  test    r12b, r12b
0x1400375e5  jz      loc_140037693
0x1400375eb  mov     rbx, [rbp+70h+Handle]
0x1400375ef  xorps   xmm0, xmm0
0x1400375f2  mov     cl, 1
0x1400375f4  mov     [rbp+70h+TokenHandle], 0
0x1400375fc  movups  xmmword ptr [rbp+70h+var_90.Ptr], xmm0
0x140037600  xor     dil, dil
0x140037603  call    AiEnsureServiceRunning
0x140037608  movzx   r8d, byte ptr [rsp+170h+var_10C]
0x14003760e  lea     rax, [rbp+70h+TokenHandle]
0x140037612  lea     r9, [rbp+70h+var_90]
0x140037616  mov     [rsp+170h+ReturnLength], rax; __int64
0x14003761b  mov     rdx, rbx
0x14003761e  lea     rcx, [rbp+70h+P]; int
0x140037622  call    AipkGetAppxAttributes
0x140037627  mov     rbx, [rbp+70h+TokenHandle]
0x14003762b  test    eax, eax
0x14003762d  js      short loc_140037657
0x14003762f  movaps  xmm0, xmmword ptr [rbp+70h+var_90.Ptr]
0x140037633  mov     rdx, rbx
0x140037636  mov     rcx, r15
0x140037639  movdqa  xmmword ptr [rbp+70h+var_A0], xmm0
0x14003763e  call    AiSetTokenAttributes
0x140037643  test    eax, eax
0x140037645  js      short loc_140037657
0x140037647  cmp     rsi, r15
0x14003764a  jz      short loc_140037657
0x14003764c  mov     rdx, rbx
0x14003764f  mov     rcx, rsi
0x140037652  call    AiSetTokenAttributes
0x140037657  test    rbx, rbx
0x14003765a  jz      loc_1400376E6
0x140037660  mov     rcx, [rbx-30h]; P
0x140037664  add     rbx, 0FFFFFFFFFFFFFFC0h
0x140037668  test    rcx, rcx
0x14003766b  jz      short loc_14003767B
0x14003766d  xor     edx, edx; Tag
0x14003766f  call    cs:__imp_ExFreePoolWithTag
0x140037676  nop     dword ptr [rax+rax+00h]
0x14003767b  test    rbx, rbx
0x14003767e  jz      short loc_1400376E6
0x140037680  xor     edx, edx; Tag
0x140037682  mov     rcx, rbx; P
0x140037685  call    cs:__imp_ExFreePoolWithTag
0x14003768c  nop     dword ptr [rax+rax+00h]
0x140037691  jmp     short loc_1400376E6
0x140037693  mov     rax, [r14+28h]
0x140037697  movzx   ebx, [rsp+170h+var_110]
0x14003769c  mov     ecx, [rax+18h]
0x14003769f  and     ecx, 0Ch
0x1400376a2  test    bl, bl
0x1400376a4  jz      short loc_1400376AC
0x1400376a6  test    ecx, ecx
0x1400376a8  jz      short loc_1400376B1
0x1400376aa  jmp     short loc_1400376BF
0x1400376ac  cmp     ecx, 8
0x1400376af  jnz     short loc_1400376BF
0x1400376b1  cmp     byte ptr [r14+104h], 0
0x1400376b9  jz      loc_1400377E3
0x1400376bf  xor     edx, edx
0x1400376c1  mov     rcx, r14
0x1400376c4  call    SrpIsOnlySmartLockerEnabledForPolicyType
0x1400376c9  movzx   edi, al
0x1400376cc  test    al, al
0x1400376ce  jnz     short loc_1400376E6
0x1400376d0  mov     rdx, [rbp+70h+Handle]
0x1400376d4  mov     r9, rsi
0x1400376d7  mov     r8, r15
0x1400376da  mov     byte ptr [rsp+170h+ReturnLength], bl
0x1400376de  mov     rcx, r14
0x1400376e1  call    AiSetAttributesExe
0x1400376e6  xor     eax, eax
0x1400376e8  mov     [rbp+70h+var_90.Ptr], r13
0x1400376ec  mov     edx, 50h ; 'P'
0x1400376f1  mov     qword ptr [rbp+70h+var_90.0Ch], rax
0x1400376f5  mov     ecx, 102h
0x1400376fa  mov     [rbp+70h+var_7C], eax
0x1400376fd  mov     r8d, 44497041h
0x140037703  mov     [rbp+70h+var_90.Size], 0C0000001h
0x14003770a  call    cs:__imp_ExAllocatePool2
0x140037711  nop     dword ptr [rax+rax+00h]
0x140037716  mov     r13, rax
0x140037719  test    rax, rax
0x14003771c  jnz     short loc_140037728
0x14003771e  mov     edi, 0C0000017h
0x140037723  jmp     loc_1400377E3
0x140037728  mov     rax, [rbp+70h+arg_20]
0x14003772f  xor     edx, edx
0x140037731  mov     [r13+38h], rax
0x140037735  xor     ecx, ecx
0x140037737  mov     rax, [rbp+70h+var_D0]
0x14003773b  mov     [r13+20h], rax
0x14003773f  mov     rax, qword ptr [rbp+70h+var_D8]
0x140037743  mov     [r13+28h], rax
0x140037747  lea     rax, [rbp+70h+var_90]
0x14003774b  mov     [r13+40h], rax
0x14003774f  mov     [r13+30h], rsi
0x140037753  call    AiQueryPerformanceCounter
0x140037758  mov     rbx, rax
0x14003775b  test    r12b, r12b
0x14003775e  jz      short loc_140037769
0x140037760  lea     rdx, [rbp+70h+var_A0]
0x140037764  xor     r8d, r8d
0x140037767  jmp     short loc_14003776F
0x140037769  mov     r8, [rbp+70h+var_E0]
0x14003776d  xor     edx, edx
0x14003776f  mov     rax, [rbp+70h+Handle]
0x140037773  movzx   r9d, dil
0x140037777  mov     [rsp+170h+var_118], rax; HANDLE
0x14003777c  mov     rcx, rsi; int
0x14003777f  mov     rax, qword ptr [rbp+70h+EventDescriptor.Id]
0x140037783  mov     [rsp+170h+var_120], rax; PFILE_OBJECT
0x140037788  movzx   eax, [rsp+170h+var_110]
0x14003778d  mov     [rsp+170h+var_128], al; char
0x140037791  mov     rax, qword ptr [rbp+70h+var_D8]
0x140037795  mov     [rsp+170h+var_130], r13; __int64
0x14003779a  mov     [rsp+170h+var_138], rdx; __int64
0x14003779f  mov     rdx, r15; int
0x1400377a2  mov     [rsp+170h+var_140], r12d; int
0x1400377a7  mov     dword ptr [rsp+170h+UserData], eax; char
0x1400377ab  mov     [rsp+170h+ReturnLength], r8; int
0x1400377b0  mov     r8, r14; int
0x1400377b3  call    SrpVerifyProcess
0x1400377b8  xor     r8d, r8d
0x1400377bb  lea     rcx, qword_1400196C0
0x1400377c2  mov     rdx, rbx
0x1400377c5  mov     edi, eax
0x1400377c7  call    AiUpdatePerfTime
0x1400377cc  xor     edx, edx; Tag
0x1400377ce  mov     rcx, r13; P
0x1400377d1  call    cs:__imp_ExFreePoolWithTag
0x1400377d8  nop     dword ptr [rax+rax+00h]
0x1400377dd  jmp     short loc_1400377E3
0x1400377df  mov     rsi, [rbp+70h+var_90.Ptr]
0x1400377e3  test    r15, r15
0x1400377e6  jz      short loc_1400377F7
0x1400377e8  mov     rcx, r15; Handle
0x1400377eb  call    cs:__imp_ZwClose
0x1400377f2  nop     dword ptr [rax+rax+00h]
0x1400377f7  test    rsi, rsi
0x1400377fa  jz      short loc_140037810
0x1400377fc  cmp     rsi, r15
0x1400377ff  jz      short loc_140037810
0x140037801  mov     rcx, rsi; Handle
0x140037804  call    cs:__imp_ZwClose
0x14003780b  nop     dword ptr [rax+rax+00h]
0x140037810  mov     rcx, [rbp+70h+Handle]; Handle
0x140037814  test    rcx, rcx
0x140037817  jz      short loc_140037825
0x140037819  call    cs:__imp_ZwClose
0x140037820  nop     dword ptr [rax+rax+00h]
0x140037825  mov     ecx, 80000000h
0x14003782a  lea     eax, [rdi+rcx]
0x14003782d  test    ecx, eax
0x14003782f  jnz     loc_140037A25
0x140037835  cmp     edi, 0C0000364h
0x14003783b  jz      loc_140037A25
0x140037841  mov     rcx, cs:WPP_GLOBAL_Control
0x140037848  lea     r15, WPP_GLOBAL_Control
0x14003784f  mov     rsi, [rbp+70h+var_E0]
0x140037853  cmp     rcx, r15
0x140037856  jz      short loc_14003787B
0x140037858  mov     eax, [rcx+2Ch]
0x14003785b  test    al, 4
0x14003785d  jz      short loc_14003787B
  ... truncated ...
```
