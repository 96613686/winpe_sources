# AfdTLConnectEventHandler

- ea: `0x140003d20`
- end: `0x1400044f4`
- name: `AfdTLConnectEventHandler`
- size: `2004`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400023ec`
- `0x140002508`
- `0x14000271c`
- `0x140003670`
- `0x140003d20`
- `0x1400044fc`
- `0x140004848`
- `0x1400049b0`
- `0x140004c10`
- `0x140005b60`
- `0x140009fb0`
- `0x14000dc90`
- `0x14000f390`
- `0x140013030`
- `0x140015990`
- `0x14001b5c4`
- `0x14001c708`
- `0x14002d8d0`
- `0x14002e820`
- `0x140036708`
- `0x14004d4e4`
- `0x140072980`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140003ff9`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140004192`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140004309`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400043cd`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140003ff9`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140004192`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140004309`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400043cd`
- `ntoskrnl!IofCompleteRequest` at `0x14000400e`
- `ntoskrnl!IofCompleteRequest` at `0x1400041a7`
- `ntoskrnl!IofCompleteRequest` at `0x14000431e`
- `ntoskrnl!IofCompleteRequest` at `0x1400043e2`
- `ntoskrnl!IofCompleteRequest` at `0x14000400e`
- `ntoskrnl!IofCompleteRequest` at `0x1400041a7`
- `ntoskrnl!IofCompleteRequest` at `0x14000431e`
- `ntoskrnl!IofCompleteRequest` at `0x1400043e2`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140003fea`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140004183`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400042fa`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400043be`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140003fea`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140004183`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400042fa`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400043be`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004293`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004370`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004293`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004370`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140004256`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140004256`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003e93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000402b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400040b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003e93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000402b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400040b8`

## pseudocode

```c
__int64 __fastcall AfdTLConnectEventHandler(__int64 a1, __int64 a2)
{
  char v4; // r15
  signed __int64 v5; // rax
  signed __int64 v6; // rcx
  signed __int64 v7; // rtt
  unsigned int v8; // ebx
  UCHAR v9; // al
  ADDRESS_FAMILY *v10; // rcx
  signed int v11; // r12d
  UCHAR v12; // al
  __int64 v13; // rdx
  int v14; // ecx
  __int64 FreeConnection; // rax
  __int64 v16; // rcx
  __int64 v17; // rbx
  void *v18; // rax
  signed int *v19; // r13
  size_t v20; // rsi
  __int64 v21; // rcx
  void *v22; // rax
  signed int *v23; // rsi
  int v24; // eax
  unsigned int v25; // edx
  signed __int64 v26; // rax
  bool v27; // cc
  signed __int64 v28; // rax
  IRP *v29; // rbx
  __int64 v30; // rcx
  size_t v31; // r12
  signed int v32; // r13d
  int v33; // eax
  unsigned int v34; // edx
  signed __int64 v35; // rax
  signed __int64 v36; // rax
  IRP *v37; // rbx
  __int64 v38; // rcx
  IRP *v39; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r12
  unsigned int LowPart; // ecx
  LARGE_INTEGER DefaultTimeout; // r13
  int v43; // eax
  unsigned int v44; // r12d
  __int64 v45; // rcx
  signed __int64 v46; // rax
  signed __int64 v47; // rax
  __int64 (__fastcall **v48)(); // rax
  int v49; // edx
  __int64 v51; // [rsp+28h] [rbp-28h]
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // [rsp+30h] [rbp-20h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+38h] [rbp-18h] BYREF
  IRP *Irql; // [rsp+90h] [rbp+40h] BYREF
  signed int v55; // [rsp+A0h] [rbp+50h]
  signed int v56; // [rsp+A8h] [rbp+58h]

  Irql = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v4 = 1;
  if ( (BYTE1(xmmword_1400875E0) & 1) != 0 )
    WPP_SF_q(1032, 27, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids, a1);
  _m_prefetchw((const void *)(a1 + 64));
  v5 = *(_QWORD *)(a1 + 64);
  do
  {
    v6 = v5 + 1;
    if ( (unsigned __int64)(v5 + 1) <= 1 )
    {
      if ( v5 )
        __fastfail(0xEu);
      v4 = 0;
      v49 = 6506;
      goto LABEL_99;
    }
    v7 = v5;
    v5 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 64), v6, v5);
  }
  while ( v7 != v5 );
  if ( (*(_DWORD *)(a1 + 8) & 2) != 0 )
  {
    v8 = AfdTLDelayedAcceptCompletion(a1, a2, 0);
    if ( !v8 )
      AfdDereferenceEndpoint(a1);
    goto LABEL_100;
  }
  if ( *(_BYTE *)(a1 + 2) == 6 || (*(_DWORD *)(a1 + 8) & 0x800) != 0 )
  {
    if ( (BYTE9(xmmword_1400875D0) & 1) != 0 )
      WPP_SF_q(776, 28, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids, a1);
    v49 = 6507;
LABEL_99:
    v8 = -1073741670;
    AFDETW_TRACECONNECT_INDICATION(v6, v49, a1, -1073741670, *(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 48));
    goto LABEL_100;
  }
  v9 = SOCKADDR_SIZE(**(_WORD **)(a2 + 24));
  v10 = *(ADDRESS_FAMILY **)(a2 + 16);
  v11 = v9;
  v55 = v9;
  v12 = SOCKADDR_SIZE(*v10);
  v51 = *(_QWORD *)(a2 + 48);
  v56 = v12;
  AFDETW_TRACECONNECT_INDICATION(v14, 6501, a1, 0, v13, v51);
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        FreeConnection = AfdGetFreeConnection(a1, 0, &Irql);
        v17 = FreeConnection;
        if ( !FreeConnection )
        {
LABEL_90:
          if ( (BYTE9(xmmword_1400875D0) & 1) != 0 )
            WPP_SF_q(776, 30, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids, a1);
          v8 = -1073741670;
          goto LABEL_100;
        }
        if ( (BYTE1(xmmword_1400875E0) & 1) != 0 )
          WPP_SF_q(1032, 29, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids, FreeConnection);
        v18 = *(void **)(v17 + 152);
        v19 = (signed int *)(v17 + 160);
        if ( v18 )
        {
          if ( *v19 >= (unsigned int)v11 )
          {
            v20 = v11;
            break;
          }
          if ( *v19 > (unsigned int)AfdStandardAddressLength )
            ExFreePoolWithTag(*(PVOID *)(v17 + 152), 0x52646641u);
          else
            PplFreeToLookasideList(PplAddressPool, *(_QWORD *)(v17 + 152));
          *(_QWORD *)(v17 + 152) = 0;
        }
        v20 = v11;
        v18 = (void *)(v11 > (unsigned int)AfdStandardAddressLength
                     ? AfdAllocatePoolPriority(64, v11, 1382311489, 0)
                     : AfdAllocateZeroedFromLookasideList(v16, v11));
        *(_QWORD *)(v17 + 152) = v18;
        if ( v18 )
          break;
        v24 = *(_DWORD *)(v17 + 4);
        if ( (v24 & 0x40000) != 0 )
        {
          *(_DWORD *)(v17 + 4) = v24 & 0xFFFBFFFF;
          v25 = 8 * (unsigned int)*(unsigned __int16 *)(a1 + 190) / 0xA;
          if ( _InterlockedDecrement((volatile signed __int32 *)(a1 + 176)) == v25 )
            AfdTLHandleListenBacklog(a1, 0, 0);
        }
        v26 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v17 + 48), 0xFFFFFFFFFFFFFFFFuLL);
        v27 = v26 <= 1;
        v28 = v26 - 1;
        if ( v27 )
        {
          if ( v28 )
            __fastfail(0xEu);
          AfdCloseConnection(v17);
        }
        v29 = Irql;
        if ( !Irql )
          goto LABEL_90;
        AFDETW_TRACEWAITLISTEN(1, 6210, a1, 3221225760LL);
        AFDETW_TRACEACCEPT_ERROR(v30, 6213, v29, 3221225760LL);
        AfdCleanupSuperAccept(v29, 3221225760LL);
        if ( v29->Cancel )
        {
          LOBYTE(Irql) = 0;
          IoAcquireCancelSpinLock((PKIRQL)&Irql);
          IoReleaseCancelSpinLock((KIRQL)Irql);
        }
        IofCompleteRequest(v29, AfdPriorityBoost);
        Irql = 0;
      }
      *v19 = v11;
      memmove(v18, *(const void **)(a2 + 24), v20);
      v22 = *(void **)(v17 + 224);
      v23 = (signed int *)(v17 + 168);
      if ( v22 )
      {
        if ( *v23 >= (unsigned int)v56 )
        {
          v32 = v56;
          v31 = v56;
          goto LABEL_63;
        }
        if ( *v23 > (unsigned int)AfdStandardAddressLength )
          ExFreePoolWithTag(*(PVOID *)(v17 + 224), 0x52646641u);
        else
          PplFreeToLookasideList(PplAddressPool, *(_QWORD *)(v17 + 224));
        *(_QWORD *)(v17 + 224) = 0;
        *v23 = 0;
      }
      v31 = v56;
      v22 = (void *)(v56 > (unsigned int)AfdStandardAddressLength
                   ? AfdAllocatePoolPriority(64, v56, 1382311489, 0)
                   : AfdAllocateZeroedFromLookasideList(v21, v56));
      *(_QWORD *)(v17 + 224) = v22;
      if ( v22 )
        break;
      if ( *v19 > (unsigned int)AfdStandardAddressLength )
        ExFreePoolWithTag(*(PVOID *)(v17 + 152), 0x52646641u);
      else
        PplFreeToLookasideList(PplAddressPool, *(_QWORD *)(v17 + 152));
      v33 = *(_DWORD *)(v17 + 4);
      *(_QWORD *)(v17 + 152) = 0;
      if ( (v33 & 0x40000) != 0 )
      {
        *(_DWORD *)(v17 + 4) = v33 & 0xFFFBFFFF;
        v34 = 8 * (unsigned int)*(unsigned __int16 *)(a1 + 190) / 0xA;
        if ( _InterlockedDecrement((volatile signed __int32 *)(a1 + 176)) == v34 )
          AfdTLHandleListenBacklog(a1, 0, 0);
      }
      v35 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v17 + 48), 0xFFFFFFFFFFFFFFFFuLL);
      v27 = v35 <= 1;
      v36 = v35 - 1;
      if ( v27 )
      {
        if ( v36 )
          __fastfail(0xEu);
        AfdCloseConnection(v17);
      }
      v37 = Irql;
      if ( !Irql )
        goto LABEL_90;
      AFDETW_TRACEWAITLISTEN(1, 6211, a1, 3221225760LL);
      AFDETW_TRACEACCEPT_ERROR(v38, 6214, v37, 3221225760LL);
      AfdCleanupSuperAccept(v37, 3221225760LL);
      if ( v37->Cancel )
      {
        LOBYTE(Irql) = 0;
        IoAcquireCancelSpinLock((PKIRQL)&Irql);
        IoReleaseCancelSpinLock((KIRQL)Irql);
      }
      IofCompleteRequest(v37, AfdPriorityBoost);
      v11 = v55;
      Irql = 0;
    }
    v32 = v56;
LABEL_63:
    *v23 = v32;
    memmove(v22, *(const void **)(a2 + 16), v31);
    v39 = Irql;
    if ( !Irql )
    {
      *(_QWORD *)(v17 + 8) = a1;
      *(_QWORD *)(v17 + 24) = *(_QWORD *)(a2 + 40);
      *(_QWORD *)(v17 + 16) = *(_QWORD *)(a2 + 32);
      AfdTLPrepareConnectionForAccept(v17);
      AfdRestartAccept(0, 0, v17);
      goto LABEL_87;
    }
    CurrentStackLocation = Irql->Tail.Overlay.CurrentStackLocation;
    if ( v55 + 6 > CurrentStackLocation->Parameters.Create.Options
      || (LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart) != 0 && v32 + 6 > LowPart )
    {
      v44 = -1073741789;
      goto LABEL_72;
    }
    Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
    DefaultTimeout = Parameters->DefaultTimeout;
    v43 = AfdMapMdlChain(Irql->MdlAddress);
    if ( v43 >= 0 )
      break;
    v44 = v43;
LABEL_72:
    AFDETW_TRACEWAITLISTEN(1, 6212, a1, 3221225760LL);
    AFDETW_TRACEACCEPT_ERROR(v45, 6215, v39, 3221225760LL);
    AfdCleanupSuperAccept(v39, v44);
    if ( v39->Cancel )
    {
      LOBYTE(Irql) = 0;
      IoAcquireCancelSpinLock((PKIRQL)&Irql);
      IoReleaseCancelSpinLock((KIRQL)Irql);
    }
    IofCompleteRequest(v39, AfdPriorityBoost);
    Irql = 0;
    if ( *(_QWORD *)(v17 + 16) )
    {
      *(_QWORD *)(v17 + 24) = 0;
      *(_QWORD *)(v17 + 16) = 0;
    }
    v46 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v17 + 48), 0xFFFFFFFFFFFFFFFFuLL);
    v11 = v55;
    v27 = v46 <= 1;
    v47 = v46 - 1;
    if ( v27 )
    {
      if ( v47 )
        __fastfail(0xEu);
      AfdCloseConnection(v17);
    }
  }
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))AfdTLCopyRemoteAndLocalAddresses)(
    (LARGE_INTEGER)DefaultTimeout.QuadPart,
    *(_QWORD *)(a2 + 16),
    (unsigned int)v56,
    *(_QWORD *)(a2 + 24),
    v55,
    v39);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(DefaultTimeout.QuadPart + 56), &LockHandle);
  *(_QWORD *)(v17 + 8) = a1;
  *(_QWORD *)(v17 + 24) = *(_QWORD *)(a2 + 40);
  *(_QWORD *)(v17 + 16) = *(_QWORD *)(a2 + 32);
  LODWORD(Irql) = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))AfdSetupAcceptEndpoint)(
                    a1,
                    (LARGE_INTEGER)DefaultTimeout.QuadPart,
                    v17);
  if ( (_DWORD)Irql )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v44 = (unsigned int)Irql;
    *(_QWORD *)(v17 + 8) = 0;
    goto LABEL_72;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( (*(_DWORD *)(DefaultTimeout.QuadPart + 8) & 0x2000) != 0 )
    ((void (__fastcall *)(_QWORD))AfdDerefTLBaseEndpoint)((LARGE_INTEGER)DefaultTimeout.QuadPart);
  CurrentStackLocation->Parameters.Read.ByteOffset.LowPart = 0;
  AfdTLPrepareConnectionForAccept(v17);
  if ( !(unsigned int)AfdRestartSuperAccept(0, v39, Parameters) )
  {
    if ( v39->Cancel )
    {
      LOBYTE(Irql) = 0;
      IoAcquireCancelSpinLock((PKIRQL)&Irql);
      IoReleaseCancelSpinLock((KIRQL)Irql);
    }
    IofCompleteRequest(v39, AfdPriorityBoost);
  }
LABEL_87:
  *(_QWORD *)(a2 + 56) = v17;
  v48 = AfdTlClientConnectDispatch;
  if ( (*(_BYTE *)(a1 + 7) & 0x10) != 0 )
    v48 = AfdRioTlClientConnectDispatch;
  v8 = 0;
  *(_QWORD *)(a2 + 64) = v48;
LABEL_100:
  if ( v4 && v8 )
    AfdDereferenceEndpoint(a1);
  return v8;
}

```

## disassembly

```asm
0x140003d20  mov     [rsp-38h+arg_8], rbx
0x140003d25  push    rbp
0x140003d26  push    rsi
0x140003d27  push    rdi
0x140003d28  push    r12
0x140003d2a  push    r13
0x140003d2c  push    r14
0x140003d2e  push    r15
0x140003d30  mov     rbp, rsp
0x140003d33  sub     rsp, 50h
0x140003d37  xor     esi, esi
0x140003d39  xorps   xmm0, xmm0
0x140003d3c  xor     eax, eax
0x140003d3e  mov     [rbp+Irql], rsi
0x140003d42  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140003d46  mov     r14, rdx
0x140003d49  mov     rdi, rcx
0x140003d4c  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140003d50  lea     r15d, [rsi+1]
0x140003d54  test    byte ptr cs:xmmword_1400875E0+1, r15b
0x140003d5b  jz      short loc_140003D74
0x140003d5d  lea     edx, [rsi+1Bh]
0x140003d60  mov     ecx, 408h
0x140003d65  mov     r9, rdi
0x140003d68  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x140003d6f  call    WPP_SF_q
0x140003d74  prefetchw byte ptr [rdi+40h]
0x140003d78  mov     rax, [rdi+40h]
0x140003d7c  lea     rcx, [rax+1]
0x140003d80  cmp     rcx, r15
0x140003d83  jbe     loc_140004491
0x140003d89  lock cmpxchg [rdi+40h], rcx
0x140003d8f  jnz     short loc_140003D7C
0x140003d91  mov     eax, [rdi+8]
0x140003d94  test    al, 2
0x140003d96  jz      short loc_140003DBD
0x140003d98  xor     r8d, r8d
0x140003d9b  mov     rdx, r14
0x140003d9e  mov     rcx, rdi
0x140003da1  call    AfdTLDelayedAcceptCompletion
0x140003da6  mov     ebx, eax
0x140003da8  test    eax, eax
0x140003daa  jnz     loc_1400044C5
0x140003db0  mov     rcx, rdi
0x140003db3  call    AfdDereferenceEndpoint
0x140003db8  jmp     loc_1400044C5
0x140003dbd  cmp     byte ptr [rdi+2], 6
0x140003dc1  jz      loc_140004468
0x140003dc7  mov     eax, [rdi+8]
0x140003dca  bt      eax, 0Bh
0x140003dce  jb      loc_140004468
0x140003dd4  mov     rdx, [r14+18h]
0x140003dd8  movzx   ecx, word ptr [rdx]; af
0x140003ddb  call    SOCKADDR_SIZE
0x140003de0  mov     rcx, [r14+10h]
0x140003de4  movzx   r12d, al
0x140003de8  mov     [rbp+arg_10], r12d
0x140003dec  movzx   ecx, word ptr [rcx]; af
0x140003def  call    SOCKADDR_SIZE
0x140003df4  movzx   r13d, al
0x140003df8  xor     r9d, r9d
0x140003dfb  mov     rax, [r14+30h]
0x140003dff  mov     r8, rdi
0x140003e02  mov     [rsp+50h+var_28], rax
0x140003e07  mov     [rsp+50h+var_30], rdx
0x140003e0c  mov     edx, 1965h
0x140003e11  mov     [rbp+arg_18], r13d
0x140003e15  call    AFDETW_TRACECONNECT_INDICATION
0x140003e1a  lea     r8, [rbp+Irql]
0x140003e1e  xor     edx, edx
0x140003e20  mov     rcx, rdi
0x140003e23  call    AfdGetFreeConnection
0x140003e28  mov     rbx, rax
0x140003e2b  test    rax, rax
0x140003e2e  jz      loc_14000443F
0x140003e34  test    byte ptr cs:xmmword_1400875E0+1, r15b
0x140003e3b  jz      short loc_140003E56
0x140003e3d  mov     edx, 1Dh
0x140003e42  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x140003e49  mov     ecx, 408h
0x140003e4e  mov     r9, rax
0x140003e51  call    WPP_SF_q
0x140003e56  mov     rax, [rbx+98h]
0x140003e5d  lea     r13, [rbx+0A0h]
0x140003e64  test    rax, rax
0x140003e67  jz      short loc_140003EA6
0x140003e69  mov     ecx, [r13+0]
0x140003e6d  cmp     ecx, r12d
0x140003e70  jnb     short loc_140003EBC
0x140003e72  cmp     ecx, cs:AfdStandardAddressLength
0x140003e78  ja      short loc_140003E8B
0x140003e7a  mov     rcx, cs:PplAddressPool
0x140003e81  mov     rdx, rax
0x140003e84  call    PplFreeToLookasideList
0x140003e89  jmp     short loc_140003E9F
0x140003e8b  mov     edx, 52646641h; Tag
0x140003e90  mov     rcx, rax; P
0x140003e93  call    cs:__imp_ExFreePoolWithTag
0x140003e9a  nop     dword ptr [rax+rax+00h]
0x140003e9f  mov     [rbx+98h], rsi
0x140003ea6  cmp     r12d, cs:AfdStandardAddressLength
0x140003ead  movsxd  rsi, r12d
0x140003eb0  mov     rdx, rsi
0x140003eb3  ja      short loc_140003F14
0x140003eb5  call    AfdAllocateZeroedFromLookasideList
0x140003eba  jmp     short loc_140003F26
0x140003ebc  movsxd  rsi, r12d
0x140003ebf  mov     [r13+0], r12d
0x140003ec3  mov     r8, rsi; Size
0x140003ec6  mov     rdx, [r14+18h]; Src
0x140003eca  mov     rcx, rax; void *
0x140003ecd  call    memmove
0x140003ed2  mov     rax, [rbx+0E0h]
0x140003ed9  lea     rsi, [rbx+0A8h]
0x140003ee0  test    rax, rax
0x140003ee3  jz      loc_140004048
0x140003ee9  mov     ecx, [rsi]
0x140003eeb  cmp     ecx, [rbp+arg_18]
0x140003eee  jnb     loc_140004061
0x140003ef4  cmp     ecx, cs:AfdStandardAddressLength
0x140003efa  ja      loc_140004023
0x140003f00  mov     rcx, cs:PplAddressPool
0x140003f07  mov     rdx, rax
0x140003f0a  call    PplFreeToLookasideList
0x140003f0f  jmp     loc_140004037
0x140003f14  xor     r9d, r9d
0x140003f17  mov     r8d, 52646641h
0x140003f1d  lea     ecx, [r9+40h]
0x140003f21  call    AfdAllocatePoolPriority
0x140003f26  mov     [rbx+98h], rax
0x140003f2d  test    rax, rax
0x140003f30  jnz     short loc_140003EBF
0x140003f32  mov     eax, [rbx+4]
0x140003f35  bt      eax, 12h
0x140003f39  jnb     short loc_140003F74
0x140003f3b  btr     eax, 12h
0x140003f3f  mov     [rbx+4], eax
0x140003f42  mov     eax, 0CCCCCCCDh
0x140003f47  movzx   ecx, word ptr [rdi+0BEh]
0x140003f4e  shl     ecx, 3
0x140003f51  mul     ecx
0x140003f53  shr     edx, 3
0x140003f56  or      eax, 0FFFFFFFFh
0x140003f59  lock xadd [rdi+0B0h], eax
0x140003f61  dec     eax
0x140003f63  cmp     eax, edx
0x140003f65  jnz     short loc_140003F74
0x140003f67  xor     r8d, r8d
0x140003f6a  xor     edx, edx
0x140003f6c  mov     rcx, rdi
0x140003f6f  call    AfdTLHandleListenBacklog
0x140003f74  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003f78  lock xadd [rbx+30h], rax
0x140003f7e  xor     esi, esi
0x140003f80  sub     rax, r15
0x140003f83  jg      short loc_140003F9B
0x140003f85  test    rax, rax
0x140003f88  jnz     short loc_140003F94
0x140003f8a  mov     rcx, rbx
0x140003f8d  call    AfdCloseConnection
0x140003f92  jmp     short loc_140003F9B
0x140003f94  mov     ecx, 0Eh
0x140003f99  int     29h; Win8: RtlFailFast(ecx)
0x140003f9b  mov     rbx, [rbp+Irql]
0x140003f9f  test    rbx, rbx
0x140003fa2  jz      loc_14000443F
0x140003fa8  mov     r13d, 0C0000120h
0x140003fae  mov     r8, rdi
0x140003fb1  mov     r9d, r13d
0x140003fb4  mov     edx, 1842h
0x140003fb9  mov     ecx, r15d
0x140003fbc  call    AFDETW_TRACEWAITLISTEN
0x140003fc1  mov     r9d, r13d
0x140003fc4  mov     r8, rbx
0x140003fc7  mov     edx, 1845h
0x140003fcc  call    AFDETW_TRACEACCEPT_ERROR
0x140003fd1  mov     edx, r13d
0x140003fd4  mov     rcx, rbx
0x140003fd7  call    AfdCleanupSuperAccept
0x140003fdc  cmp     [rbx+44h], sil
0x140003fe0  jz      short loc_140004005
0x140003fe2  lea     rcx, [rbp+Irql]; Irql
0x140003fe6  mov     byte ptr [rbp+Irql], sil
0x140003fea  call    cs:__imp_IoAcquireCancelSpinLock
0x140003ff1  nop     dword ptr [rax+rax+00h]
0x140003ff6  mov     cl, byte ptr [rbp+Irql]; Irql
0x140003ff9  call    cs:__imp_IoReleaseCancelSpinLock
0x140004000  nop     dword ptr [rax+rax+00h]
0x140004005  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14000400b  mov     rcx, rbx; Irp
0x14000400e  call    cs:__imp_IofCompleteRequest
0x140004015  nop     dword ptr [rax+rax+00h]
0x14000401a  mov     [rbp+Irql], rsi
0x14000401e  jmp     loc_140003E1A
0x140004023  mov     edx, 52646641h; Tag
0x140004028  mov     rcx, rax; P
0x14000402b  call    cs:__imp_ExFreePoolWithTag
0x140004032  nop     dword ptr [rax+rax+00h]
0x140004037  mov     qword ptr [rbx+0E0h], 0
0x140004042  mov     dword ptr [rsi], 0
0x140004048  movsxd  rax, [rbp+arg_18]
0x14000404c  cmp     eax, cs:AfdStandardAddressLength
0x140004052  mov     r12, rax
0x140004055  mov     rdx, rax
0x140004058  ja      short loc_14000406D
0x14000405a  call    AfdAllocateZeroedFromLookasideList
0x14000405f  jmp     short loc_14000407F
0x140004061  movsxd  r13, [rbp+arg_18]
0x140004065  mov     r12, r13
0x140004068  jmp     loc_1400041C4
0x14000406d  xor     r9d, r9d
0x140004070  mov     r8d, 52646641h
0x140004076  lea     ecx, [r9+40h]
0x14000407a  call    AfdAllocatePoolPriority
0x14000407f  mov     [rbx+0E0h], rax
0x140004086  test    rax, rax
0x140004089  jnz     loc_1400041C0
0x14000408f  mov     eax, cs:AfdStandardAddressLength
0x140004095  mov     rcx, [rbx+98h]; P
0x14000409c  cmp     [r13+0], eax
0x1400040a0  ja      short loc_1400040B3
0x1400040a2  mov     rdx, rcx
0x1400040a5  mov     rcx, cs:PplAddressPool
0x1400040ac  call    PplFreeToLookasideList
0x1400040b1  jmp     short loc_1400040C4
0x1400040b3  mov     edx, 52646641h; Tag
0x1400040b8  call    cs:__imp_ExFreePoolWithTag
0x1400040bf  nop     dword ptr [rax+rax+00h]
0x1400040c4  mov     eax, [rbx+4]
0x1400040c7  xor     esi, esi
0x1400040c9  mov     [rbx+98h], rsi
0x1400040d0  bt      eax, 12h
0x1400040d4  jnb     short loc_14000410F
0x1400040d6  btr     eax, 12h
0x1400040da  mov     [rbx+4], eax
0x1400040dd  mov     eax, 0CCCCCCCDh
0x1400040e2  movzx   ecx, word ptr [rdi+0BEh]
0x1400040e9  shl     ecx, 3
0x1400040ec  mul     ecx
0x1400040ee  shr     edx, 3
0x1400040f1  or      eax, 0FFFFFFFFh
0x1400040f4  lock xadd [rdi+0B0h], eax
0x1400040fc  dec     eax
0x1400040fe  cmp     eax, edx
0x140004100  jnz     short loc_14000410F
0x140004102  xor     r8d, r8d
0x140004105  xor     edx, edx
0x140004107  mov     rcx, rdi
0x14000410a  call    AfdTLHandleListenBacklog
0x14000410f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004113  lock xadd [rbx+30h], rax
0x140004119  sub     rax, r15
0x14000411c  jg      short loc_140004134
0x14000411e  test    rax, rax
0x140004121  jnz     short loc_14000412D
0x140004123  mov     rcx, rbx
0x140004126  call    AfdCloseConnection
0x14000412b  jmp     short loc_140004134
0x14000412d  mov     ecx, 0Eh
0x140004132  int     29h; Win8: RtlFailFast(ecx)
0x140004134  mov     rbx, [rbp+Irql]
0x140004138  test    rbx, rbx
0x14000413b  jz      loc_14000443F
0x140004141  mov     r13d, 0C0000120h
0x140004147  mov     r8, rdi
0x14000414a  mov     r9d, r13d
0x14000414d  mov     edx, 1843h
0x140004152  mov     ecx, r15d
0x140004155  call    AFDETW_TRACEWAITLISTEN
0x14000415a  mov     r9d, r13d
0x14000415d  mov     r8, rbx
0x140004160  mov     edx, 1846h
0x140004165  call    AFDETW_TRACEACCEPT_ERROR
0x14000416a  mov     edx, r13d
0x14000416d  mov     rcx, rbx
0x140004170  call    AfdCleanupSuperAccept
0x140004175  cmp     [rbx+44h], sil
0x140004179  jz      short loc_14000419E
0x14000417b  lea     rcx, [rbp+Irql]; Irql
0x14000417f  mov     byte ptr [rbp+Irql], sil
0x140004183  call    cs:__imp_IoAcquireCancelSpinLock
0x14000418a  nop     dword ptr [rax+rax+00h]
0x14000418f  mov     cl, byte ptr [rbp+Irql]; Irql
0x140004192  call    cs:__imp_IoReleaseCancelSpinLock
0x140004199  nop     dword ptr [rax+rax+00h]
0x14000419e  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x1400041a4  mov     rcx, rbx; Irp
0x1400041a7  call    cs:__imp_IofCompleteRequest
0x1400041ae  nop     dword ptr [rax+rax+00h]
0x1400041b3  mov     r12d, [rbp+arg_10]
0x1400041b7  mov     [rbp+Irql], rsi
0x1400041bb  jmp     loc_140003E1A
0x1400041c0  mov     r13d, [rbp+arg_18]
0x1400041c4  mov     [rsi], r13d
0x1400041c7  mov     r8, r12; Size
0x1400041ca  mov     rdx, [r14+10h]; Src
0x1400041ce  mov     rcx, rax; void *
0x1400041d1  call    memmove
0x1400041d6  mov     rsi, [rbp+Irql]
0x1400041da  test    rsi, rsi
  ... truncated ...
```
