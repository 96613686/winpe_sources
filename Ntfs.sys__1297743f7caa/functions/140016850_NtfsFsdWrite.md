# NtfsFsdWrite

- ea: `0x140016850`
- end: `0x140016e8d`
- name: `NtfsFsdWrite`
- size: `1597`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x140013bb0`
- `0x14001519c`
- `0x1400151d0`
- `0x140015228`
- `0x140015260`
- `0x140015b90`
- `0x140016850`
- `0x140016ea0`
- `0x140017030`
- `0x140017480`
- `0x1400177d0`
- `0x1400291f0`
- `0x140029d80`
- `0x1400592c0`
- `0x140059740`
- `0x14013add0`
- `0x14018a28c`
- `0x14026f7c4`

## import_xrefs

- `ntoskrnl!IoGetStackLimits` at `0x140016a90`
- `ntoskrnl!IoGetStackLimits` at `0x140016bd8`
- `ntoskrnl!IoGetStackLimits` at `0x140016a90`
- `ntoskrnl!IoGetStackLimits` at `0x140016bd8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140016971`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140016cd7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140016971`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140016cd7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140016c8f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140016c8f`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14001699f`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14001699f`
- `ntoskrnl!IoIsOperationSynchronous` at `0x140016926`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14005e4bb`
- `ntoskrnl!IoIsOperationSynchronous` at `0x140016926`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14005e4bb`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x140016a3b`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x140016d0b`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x140016a3b`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x140016d0b`
- `ntoskrnl!CcErrorCallbackRoutine` at `0x140016b4f`
- `ntoskrnl!CcErrorCallbackRoutine` at `0x140016b4f`
- `HAL!KeQueryPerformanceCounter` at `0x1400169f2`
- `HAL!KeQueryPerformanceCounter` at `0x1400169f2`

## pseudocode

```c
__int64 __fastcall NtfsFsdWrite(__int64 a1, IRP *a2)
{
  _DWORD *v3; // rbx
  bool v4; // r12
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *p_CurrentStackLocation; // rdx
  _DWORD *FsContext; // rdi
  ULONG *p_Flags; // r14
  PDEVICE_OBJECT DeviceObject; // rcx
  __int64 v9; // rsi
  __int64 v10; // r9
  BOOLEAN IsOperationSynchronous; // al
  unsigned int Status; // edi
  __int64 v13; // r9
  char v14; // al
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rdx
  int v18; // edx
  int v19; // edx
  unsigned int v20; // edx
  unsigned __int64 v21; // rax
  _DWORD *v22; // r14
  unsigned int v23; // eax
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  char v28; // bl
  __int64 v29; // r8
  __int64 v30; // r9
  void *v32; // rsp
  _DWORD v33[164]; // [rsp+0h] [rbp-290h] BYREF
  bool v34; // [rsp+290h] [rbp+0h]
  int v35; // [rsp+294h] [rbp+4h]
  unsigned __int64 v36; // [rsp+298h] [rbp+8h] BYREF
  int v37; // [rsp+2A0h] [rbp+10h] BYREF
  unsigned int v38; // [rsp+2A4h] [rbp+14h]
  ULONG_PTR BugCheckParameter2; // [rsp+2A8h] [rbp+18h] BYREF
  int v40[2]; // [rsp+2B0h] [rbp+20h]
  unsigned __int64 v41; // [rsp+2B8h] [rbp+28h] BYREF
  unsigned __int64 v42; // [rsp+2C0h] [rbp+30h] BYREF
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *v43; // [rsp+2C8h] [rbp+38h]
  unsigned __int64 HighLimit; // [rsp+2D0h] [rbp+40h] BYREF
  unsigned __int64 LowLimit; // [rsp+2D8h] [rbp+48h] BYREF
  _DWORD *v46; // [rsp+2E0h] [rbp+50h]
  IRP *v47; // [rsp+2E8h] [rbp+58h]
  __int64 v48; // [rsp+2F0h] [rbp+60h]
  _DWORD *v49; // [rsp+2F8h] [rbp+68h]
  unsigned __int64 v50; // [rsp+300h] [rbp+70h]
  _OWORD v51[2]; // [rsp+308h] [rbp+78h] BYREF
  __int64 v52; // [rsp+328h] [rbp+98h]

  memset(v51, 0, sizeof(v51));
  v52 = 0;
  v3 = 0;
  BugCheckParameter2 = 0;
  v4 = 0;
  v34 = 0;
  LOWORD(v38) = 0;
  v37 = 0;
  p_CurrentStackLocation = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&a2->Tail.Overlay.CurrentStackLocation;
  v43 = p_CurrentStackLocation;
  FsContext = p_CurrentStackLocation->CurrentStackLocation->FileObject->FsContext;
  *(_QWORD *)v40 = FsContext;
  v49 = FsContext;
  if ( FsContext )
  {
    if ( (*(_DWORD *)(*((_QWORD *)FsContext + 23) + 4LL) & 4) != 0 )
      v4 = (FsContext[50] & 0x10) != 0;
    v34 = v4;
  }
  p_Flags = 0;
  DeviceObject = p_CurrentStackLocation->CurrentStackLocation->DeviceObject;
  if ( DeviceObject->Size >= 0x33C0u )
    p_Flags = &DeviceObject[1].Flags;
  v9 = NtfsInitializeTopLevelIrp(v51, 0, p_Flags);
  v48 = v9;
  if ( !v4 )
  {
    IsOperationSynchronous = IoIsOperationSynchronous(a2);
    Status = NtfsInitializeIrpContextInternal(a2, IsOperationSynchronous, 0, (__int64 *)&BugCheckParameter2);
    v36 = 12288;
    if ( Status == -1073741670
      && (v36 = 12288, IoIsOperationSynchronous(a2))
      && (v36 = 12288, (a2->Flags & 2) != 0)
      && (v36 = 12288, v43->CurrentStackLocation->Parameters.Read.Length <= 0x1000) )
    {
      v32 = alloca(656);
      v3 = v33;
      BugCheckParameter2 = (ULONG_PTR)v33;
      v36 = (unsigned __int64)v33;
      memset(v33, 0, sizeof(v33));
      Status = NtfsInitializeIrpContextInternal(a2, 1, 0, (__int64 *)&v36);
      if ( !Status )
        *(_WORD *)(v36 + 2) = 656;
      v36 = 12944;
    }
    else
    {
      v3 = (_DWORD *)BugCheckParameter2;
    }
    if ( (Status & 0x80000000) != 0 )
    {
      if ( NtfsStatusDebugFlags
        && Status < 0xFFFFFFED
        && Status != -1073741802
        && Status != -1073741807
        && Status + 2147483643 > 1
        && Status != -1073741608 )
      {
        NtfsStatusTraceAndDebugInternal(0, Status, 2491174);
      }
      LOBYTE(v13) = a2 != 0;
      NtfsExtendedCompleteRequestInternal(0, a2, Status, v13, (Status & 0x80000000) == 0);
      return Status;
    }
    v14 = *((_BYTE *)v3 + 33);
    if ( (v14 & 2) != 0 && (v14 & 4) == 0 )
      a2->MdlAddress = 0;
    KeEnterCriticalRegion();
    v17 = *(_QWORD *)(v9 + 32);
    if ( v17 )
    {
      v18 = *(_DWORD *)(v17 + 436);
    }
    else
    {
      *(_DWORD *)(v9 + 4) = 1397118030;
      *(_QWORD *)(v9 + 32) = v3;
      v3[3] |= 0x100000u;
      IoSetTopLevelIrp((PIRP)v9);
      if ( !*(_BYTE *)(v9 + 1) )
      {
        v19 = v3[108];
        goto LABEL_16;
      }
      v15 = *(_QWORD *)(*(_QWORD *)(v9 + 24) + 32LL);
      v18 = *(_DWORD *)(v15 + 436);
    }
    v19 = v3[108] | v18;
LABEL_16:
    v20 = v19 & 0xFFFFFBFF;
    v3[108] = v20;
    v3[109] |= v20;
    *((_QWORD *)v3 + 18) = *(_QWORD *)(v9 + 32);
    if ( *((_BYTE *)p_Flags + 10496) )
      *((LARGE_INTEGER *)v3 + 62) = KeQueryPerformanceCounter(0);
    v21 = v36;
LABEL_19:
    v47 = a2;
    v22 = 0;
    v46 = 0;
    v50 = v21;
    while ( !v4 )
    {
      if ( Status == -1073741432 )
      {
        NtfsCheckpointForLogFileFull(v3);
      }
      else if ( Status == 871 )
      {
        v43->CurrentStackLocation->Control &= ~1u;
        v24 = *((_QWORD *)v3 + 26) + 8LL;
        v33[162] = 0;
        NtfsWaitForOplockCompletionEvent(v15, a2, v16, v24);
        v35 = 0;
        NtfsFreeIoContext(v3, v25, v26);
        Status = a2->IoStatus.Status;
        v35 = Status;
        if ( (Status & 0x80000000) != 0 )
        {
          if ( NtfsStatusDebugFlags
            && Status < 0xFFFFFFED
            && Status != -1073741802
            && Status != -1073741807
            && Status + 2147483643 > 1
            && Status != -1073741608 )
          {
            NtfsStatusTraceAndDebugInternal(v3, Status, 2491297);
          }
          LOBYTE(v27) = v47 != 0;
          NtfsExtendedCompleteRequestInternal(v3, a2, Status, v27, 0);
          goto LABEL_54;
        }
      }
      else if ( (unsigned __int8)CcIsCacheManagerCallbackNeeded(Status) )
      {
        v37 = 8;
        v38 = Status;
        CcErrorCallbackRoutine(&v37);
      }
      if ( v3 )
        NtfsPreRequestProcessingExtend((_DWORD)v3);
      if ( (*((_BYTE *)v3 + 33) & 4) != 0 )
      {
        v23 = NtfsCompleteMdl(v3, a2);
      }
      else
      {
        if ( !v22 )
        {
          v22 = &v33[140];
          v46 = &v33[140];
        }
        HighLimit = 0;
        LowLimit = 0;
        IoGetStackLimits(&LowLimit, &HighLimit);
        if ( (unsigned __int64)&HighLimit - LowLimit <= v36 )
          v23 = NtfsCommonWriteOnNewStack(v3, a2, v22, *(_QWORD *)v40);
        else
          v23 = NtfsCommonWrite((LARGE_INTEGER *)v3, a2, (LARGE_INTEGER)v22);
      }
      Status = v23;
      v35 = v23;
      if ( !v23
        || v23 != 871
        && v23 != -1073741608
        && v23 != -1073741432
        && !(unsigned __int8)CcIsCacheManagerCallbackNeeded(v23)
        || (_OWORD *)v9 != v51 )
      {
        goto LABEL_54;
      }
    }
    if ( (_OWORD *)v9 == v51 )
      v28 = 0;
    else
      v28 = NtfsSetTopLevelWithoutIrpContext(v9);
    v41 = 0;
    v42 = 0;
    IoGetStackLimits(&v42, &v41);
    if ( (unsigned __int64)&v41 - v42 <= 0x2000 )
      NtfsPagingFileIoOnNewStack(a2, *(_QWORD *)v40);
    else
      NtfsPagingFileIo(a2, *(__int64 *)v40, v29, v30);
    if ( v28 )
      NtfsRestoreTopLevelIrpWithoutContext();
    Status = 259;
    v35 = 259;
LABEL_54:
    KeLeaveCriticalRegion();
    return Status;
  }
  if ( (*(_DWORD *)(*((_QWORD *)FsContext + 23) + 4LL) & 1) == 0 )
  {
    Status = 0;
    KeEnterCriticalRegion();
    v21 = 12288;
    v36 = 12288;
    goto LABEL_19;
  }
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 3221225763LL, 2491208);
  LOBYTE(v10) = a2 != 0;
  NtfsExtendedCompleteRequestInternal(0, a2, 3221225763LL, v10, 0);
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 3221225763LL, 2491209);
  return 3221225763LL;
}

```

## disassembly

```asm
0x140016850  mov     [rsp-8+arg_8], rdx
0x140016855  push    rbp
0x140016856  push    rbx
0x140016857  push    rsi
0x140016858  push    rdi
0x140016859  push    r12
0x14001685b  push    r13
0x14001685d  push    r14
0x14001685f  push    r15
0x140016861  sub     rsp, 0E8h
0x140016868  lea     rbp, [rsp+30h]
0x14001686d  mov     rax, cs:__security_cookie
0x140016874  xor     rax, rbp
0x140016877  mov     [rbp+0F0h+var_50], rax
0x14001687e  mov     r13, rdx
0x140016881  xorps   xmm0, xmm0
0x140016884  xor     eax, eax
0x140016886  movups  [rbp+0F0h+var_78], xmm0
0x14001688a  movups  [rbp+0F0h+var_68], xmm0
0x140016891  mov     [rbp+0F0h+var_58], rax
0x140016898  xor     r15d, r15d
0x14001689b  mov     ebx, r15d
0x14001689e  mov     [rbp+0F0h+BugCheckParameter2], rbx
0x1400168a2  xor     r12b, r12b
0x1400168a5  mov     [rbp+0F0h+var_F0], r12b
0x1400168a9  mov     dword ptr [rbp+0F0h+var_E0+2], eax
0x1400168ac  mov     dword ptr [rbp+0F0h+var_E0], eax
0x1400168af  add     rdx, 0B8h
0x1400168b6  mov     [rbp+0F0h+var_B8], rdx
0x1400168ba  mov     rax, [rdx]
0x1400168bd  mov     rcx, [rax+30h]
0x1400168c1  mov     rdi, [rcx+18h]
0x1400168c5  mov     qword ptr [rbp+0F0h+var_D0], rdi
0x1400168c9  mov     [rbp+0F0h+var_88], rdi
0x1400168cd  test    rdi, rdi
0x1400168d0  jz      short loc_1400168E9
0x1400168d2  mov     rax, [rdi+0B8h]
0x1400168d9  mov     ecx, [rax+4]
0x1400168dc  test    cl, 4
0x1400168df  jnz     loc_140016D47
0x1400168e5  mov     [rbp+0F0h+var_F0], r12b
0x1400168e9  mov     r14, r15
0x1400168ec  mov     rax, [rdx]
0x1400168ef  mov     rcx, [rax+28h]
0x1400168f3  mov     eax, 33C0h
0x1400168f8  cmp     [rcx+2], ax
0x1400168fc  jb      short loc_140016905
0x1400168fe  lea     r14, [rcx+180h]
0x140016905  mov     r8, r14
0x140016908  xor     edx, edx
0x14001690a  lea     rcx, [rbp+0F0h+var_78]
0x14001690e  call    NtfsInitializeTopLevelIrp
0x140016913  mov     rsi, rax
0x140016916  mov     [rbp+0F0h+var_90], rax
0x14001691a  test    r12b, r12b
0x14001691d  jnz     loc_140016CC1
0x140016923  mov     rcx, r13; Irp
0x140016926  call    cs:__imp_IoIsOperationSynchronous
0x14001692d  nop     dword ptr [rax+rax+00h]
0x140016932  lea     r9, [rbp+0F0h+BugCheckParameter2]
0x140016936  xor     r8d, r8d
0x140016939  movzx   edx, al
0x14001693c  mov     rcx, r13; Irp
0x14001693f  call    NtfsInitializeIrpContextInternal
0x140016944  mov     edi, eax
0x140016946  mov     [rbp+0F0h+var_E8], 3000h
0x14001694e  cmp     eax, 0C000009Ah
0x140016953  jz      loc_14005E4B0
0x140016959  mov     rbx, [rbp+0F0h+BugCheckParameter2]
0x14001695d  test    edi, edi
0x14001695f  js      loc_140016DC1
0x140016965  movzx   eax, byte ptr [rbx+21h]
0x140016969  test    al, 2
0x14001696b  jnz     loc_140016E7C
0x140016971  call    cs:__imp_KeEnterCriticalRegion
0x140016978  nop     dword ptr [rax+rax+00h]
0x14001697d  mov     rdx, [rsi+20h]
0x140016981  test    rdx, rdx
0x140016984  jnz     loc_140016D31
0x14001698a  mov     dword ptr [rsi+4], 5346544Eh
0x140016991  mov     [rsi+20h], rbx
0x140016995  or      dword ptr [rbx+0Ch], 100000h
0x14001699c  mov     rcx, rsi; Irp
0x14001699f  call    cs:__imp_IoSetTopLevelIrp
0x1400169a6  nop     dword ptr [rax+rax+00h]
0x1400169ab  cmp     [rsi+1], r15b
0x1400169af  jz      loc_140016D3C
0x1400169b5  mov     rax, [rsi+18h]
0x1400169b9  mov     rcx, [rax+20h]
0x1400169bd  mov     edx, [rcx+1B4h]
0x1400169c3  or      edx, [rbx+1B0h]
0x1400169c9  btr     edx, 0Ah
0x1400169cd  mov     [rbx+1B0h], edx
0x1400169d3  or      [rbx+1B4h], edx
0x1400169d9  mov     rax, [rsi+20h]
0x1400169dd  mov     [rbx+90h], rax
0x1400169e4  movzx   eax, byte ptr [r14+2900h]
0x1400169ec  test    al, al
0x1400169ee  jz      short loc_140016A05
0x1400169f0  xor     ecx, ecx; PerformanceFrequency
0x1400169f2  call    cs:__imp_KeQueryPerformanceCounter
0x1400169f9  nop     dword ptr [rax+rax+00h]
0x1400169fe  mov     [rbx+1F0h], rax
0x140016a05  mov     rax, [rbp+0F0h+var_E8]
0x140016a09  mov     [rbp+0F0h+var_98], r13
0x140016a0d  mov     r14, r15
0x140016a10  mov     [rbp+0F0h+var_A0], r15
0x140016a14  mov     [rbp+0F0h+var_80], rax
0x140016a18  test    r12b, r12b
0x140016a1b  jnz     loc_140016BBD
0x140016a21  cmp     edi, 0C0000188h
0x140016a27  jz      loc_140016B60
0x140016a2d  cmp     edi, 367h
0x140016a33  jz      loc_140016AC1
0x140016a39  mov     ecx, edi
0x140016a3b  call    cs:__imp_CcIsCacheManagerCallbackNeeded
0x140016a42  nop     dword ptr [rax+rax+00h]
0x140016a47  test    al, al
0x140016a49  jnz     loc_140016B3B
0x140016a4f  test    rbx, rbx
0x140016a52  jz      short loc_140016A5E
0x140016a54  mov     edx, edi
0x140016a56  mov     rcx, rbx
0x140016a59  call    NtfsPreRequestProcessingExtend
0x140016a5e  test    byte ptr [rbx+21h], 4
0x140016a62  jnz     loc_140016B2B
0x140016a68  test    r14, r14
0x140016a6b  jnz     short loc_140016A80
0x140016a6d  mov     eax, [rsp+120h+var_120]
0x140016a70  sub     rsp, 60h
0x140016a74  lea     r14, [rsp+180h+var_150]
0x140016a79  mov     eax, [r14]
0x140016a7c  mov     [rbp+0F0h+var_A0], r14
0x140016a80  mov     [rbp+0F0h+HighLimit], r15
0x140016a84  mov     [rbp+0F0h+LowLimit], r15
0x140016a88  lea     rdx, [rbp+0F0h+HighLimit]; HighLimit
0x140016a8c  lea     rcx, [rbp+0F0h+LowLimit]; LowLimit
0x140016a90  call    cs:__imp_IoGetStackLimits
0x140016a97  nop     dword ptr [rax+rax+00h]
0x140016a9c  lea     rax, [rbp+0F0h+HighLimit]
0x140016aa0  sub     rax, [rbp+0F0h+LowLimit]
0x140016aa4  mov     r8, r14
0x140016aa7  mov     rdx, r13; Irp
0x140016aaa  mov     rcx, rbx; Context
0x140016aad  cmp     rax, [rbp+0F0h+var_E8]
0x140016ab1  jbe     loc_140016BB2
0x140016ab7  call    NtfsCommonWrite
0x140016abc  jmp     loc_140016C2E
0x140016ac1  mov     rax, [rbp+0F0h+var_B8]
0x140016ac5  mov     rax, [rax]
0x140016ac8  and     byte ptr [rax+3], 0FEh
0x140016acc  mov     r9, [rbx+0D0h]
0x140016ad3  add     r9, 8
0x140016ad7  mov     [rsp+120h+var_F8], r15d
0x140016adc  mov     rdx, r13
0x140016adf  call    NtfsWaitForOplockCompletionEvent
0x140016ae4  mov     [rbp+0F0h+var_EC], r15d
0x140016ae8  mov     rcx, rbx
0x140016aeb  call    NtfsFreeIoContext
0x140016af0  mov     edi, [r13+30h]
0x140016af4  mov     [rbp+0F0h+var_EC], edi
0x140016af7  test    edi, edi
0x140016af9  jns     loc_140016A4F
0x140016aff  movzx   eax, cs:NtfsStatusDebugFlags
0x140016b06  test    al, al
0x140016b08  jnz     short loc_140016B6D
0x140016b0a  cmp     [rbp+0F0h+var_98], 0
0x140016b0f  setnz   r9b
0x140016b13  mov     [rsp+120h+var_100], r15d
0x140016b18  mov     r8d, edi
0x140016b1b  mov     rdx, r13
0x140016b1e  mov     rcx, rbx
0x140016b21  call    NtfsExtendedCompleteRequestInternal
0x140016b26  jmp     loc_140016C8F
0x140016b2b  mov     rdx, r13
0x140016b2e  mov     rcx, rbx
0x140016b31  call    NtfsCompleteMdl
0x140016b36  jmp     loc_140016C2E
0x140016b3b  mov     [rbp+0F0h+var_E0], r15
0x140016b3f  mov     eax, 8
0x140016b44  mov     word ptr [rbp+0F0h+var_E0], ax
0x140016b48  mov     dword ptr [rbp+0F0h+var_E0+4], edi
0x140016b4b  lea     rcx, [rbp+0F0h+var_E0]
0x140016b4f  call    cs:__imp_CcErrorCallbackRoutine
0x140016b56  nop     dword ptr [rax+rax+00h]
0x140016b5b  jmp     loc_140016A4F
0x140016b60  mov     rcx, rbx
0x140016b63  call    NtfsCheckpointForLogFileFull
0x140016b68  jmp     loc_140016A4F
0x140016b6d  cmp     edi, 0FFFFFFEDh
0x140016b70  jnb     short loc_140016B0A
0x140016b72  cmp     edi, 0C0000016h
0x140016b78  jz      short loc_140016B0A
0x140016b7a  cmp     edi, 0C0000011h
0x140016b80  jz      short loc_140016B0A
0x140016b82  lea     eax, [rdi+7FFFFFFBh]
0x140016b88  cmp     eax, 1
0x140016b8b  jbe     loc_140016B0A
0x140016b91  cmp     edi, 0C00000D8h
0x140016b97  jz      loc_140016B0A
0x140016b9d  mov     r8d, 2603A1h
0x140016ba3  mov     edx, edi
0x140016ba5  mov     rcx, rbx
0x140016ba8  call    NtfsStatusTraceAndDebugInternal
0x140016bad  jmp     loc_140016B0A
0x140016bb2  mov     r9, qword ptr [rbp+0F0h+var_D0]
0x140016bb6  call    NtfsCommonWriteOnNewStack
0x140016bbb  jmp     short loc_140016C2E
0x140016bbd  lea     rax, [rbp+0F0h+var_78]
0x140016bc1  cmp     rsi, rax
0x140016bc4  jnz     short loc_140016C21
0x140016bc6  xor     bl, bl
0x140016bc8  mov     [rbp+0F0h+var_C8], r15
0x140016bcc  mov     [rbp+0F0h+var_C0], r15
0x140016bd0  lea     rdx, [rbp+0F0h+var_C8]; HighLimit
0x140016bd4  lea     rcx, [rbp+0F0h+var_C0]; LowLimit
0x140016bd8  call    cs:__imp_IoGetStackLimits
0x140016bdf  nop     dword ptr [rax+rax+00h]
0x140016be4  lea     rax, [rbp+0F0h+var_C8]
0x140016be8  sub     rax, [rbp+0F0h+var_C0]
0x140016bec  mov     rdx, qword ptr [rbp+0F0h+var_D0]; int
0x140016bf0  mov     rcx, r13; int
0x140016bf3  cmp     rax, 2000h
0x140016bf9  jbe     short loc_140016C1A
0x140016bfb  call    NtfsPagingFileIo
0x140016c00  test    bl, bl
0x140016c02  jz      short loc_140016C09
0x140016c04  call    NtfsRestoreTopLevelIrpWithoutContext
0x140016c09  movzx   eax, cs:NtfsStatusDebugFlags
0x140016c10  mov     edi, 103h
0x140016c15  mov     [rbp+0F0h+var_EC], edi
0x140016c18  jmp     short loc_140016C8F
0x140016c1a  call    NtfsPagingFileIoOnNewStack
0x140016c1f  jmp     short loc_140016C00
0x140016c21  mov     rcx, rsi
0x140016c24  call    NtfsSetTopLevelWithoutIrpContext
0x140016c29  movzx   ebx, al
0x140016c2c  jmp     short loc_140016BC8
0x140016c2e  mov     edi, eax
0x140016c30  mov     [rbp+0F0h+var_EC], eax
0x140016c33  jmp     short loc_140016C8B
0x140016c35  mov     r8d, eax
0x140016c38  mov     rbx, [rbp+0F0h+BugCheckParameter2]
0x140016c3c  cmp     eax, 0C0000123h
0x140016c41  jnz     short loc_140016C54
0x140016c43  movzx   eax, byte ptr [rbx+21h]
0x140016c47  and     al, 6
0x140016c49  cmp     al, 2
0x140016c4b  jz      short loc_140016C54
0x140016c4d  xor     r8d, r8d
0x140016c50  mov     [rbx+18h], r8d
0x140016c54  mov     r13, [rbp+0F0h+arg_8]
0x140016c5b  mov     rdx, r13
0x140016c5e  mov     rcx, rbx
0x140016c61  call    NtfsProcessException
0x140016c66  mov     edi, eax
0x140016c68  mov     [rbp+0F0h+var_EC], eax
0x140016c6b  xor     r15d, r15d
0x140016c6e  mov     rsi, [rbp+0F0h+var_90]
0x140016c72  mov     rax, [rbp+0F0h+var_88]
0x140016c76  mov     qword ptr [rbp+0F0h+var_D0], rax
0x140016c7a  movzx   r12d, [rbp+0F0h+var_F0]
0x140016c7f  mov     r14, [rbp+0F0h+var_A0]
0x140016c83  mov     rax, [rbp+0F0h+var_80]
0x140016c87  mov     [rbp+0F0h+var_E8], rax
0x140016c8b  test    edi, edi
0x140016c8d  jnz     short loc_140016CF1
0x140016c8f  call    cs:__imp_KeLeaveCriticalRegion
0x140016c96  nop     dword ptr [rax+rax+00h]
0x140016c9b  mov     eax, edi
0x140016c9d  mov     rcx, [rbp+0F0h+var_50]
0x140016ca4  xor     rcx, rbp; StackCookie
0x140016ca7  call    __security_check_cookie
0x140016cac  lea     rsp, [rbp+0B8h]
0x140016cb3  pop     r15
0x140016cb5  pop     r14
0x140016cb7  pop     r13
0x140016cb9  pop     r12
0x140016cbb  pop     rdi
0x140016cbc  pop     rsi
0x140016cbd  pop     rbx
0x140016cbe  pop     rbp
0x140016cbf  retn
0x140016cc1  mov     rax, [rdi+0B8h]
0x140016cc8  mov     ecx, [rax+4]
0x140016ccb  test    cl, 1
0x140016cce  jnz     loc_140016D5D
0x140016cd4  mov     edi, r15d
0x140016cd7  call    cs:__imp_KeEnterCriticalRegion
0x140016cde  nop     dword ptr [rax+rax+00h]
0x140016ce3  mov     eax, 3000h
0x140016ce8  mov     [rbp+0F0h+var_E8], rax
0x140016cec  jmp     loc_140016A09
0x140016cf1  cmp     edi, 367h
0x140016cf7  jz      short loc_140016D1F
0x140016cf9  cmp     edi, 0C00000D8h
0x140016cff  jz      short loc_140016D1F
0x140016d01  cmp     edi, 0C0000188h
0x140016d07  jz      short loc_140016D1F
0x140016d09  mov     ecx, edi
  ... truncated ...
```
