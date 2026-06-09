# AfdTLBufferedSendCompleteBatch

- ea: `0x140011bf0`
- end: `0x14001232f`
- name: `AfdTLBufferedSendCompleteBatch`
- size: `1855`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140010948`
- `0x140011bf0`
- `0x140012338`
- `0x1400129d0`
- `0x140013030`
- `0x140013990`
- `0x14001c708`
- `0x14001ccdc`
- `0x14001ceb0`
- `0x14001db90`
- `0x1400726a0`
- `0x140072780`

## import_xrefs

- `ntoskrnl!PsReturnPoolQuota` at `0x1400120c7`
- `ntoskrnl!PsReturnPoolQuota` at `0x14001212a`
- `ntoskrnl!PsReturnPoolQuota` at `0x140012148`
- `ntoskrnl!PsReturnPoolQuota` at `0x140012267`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400120c7`
- `ntoskrnl!PsReturnPoolQuota` at `0x14001212a`
- `ntoskrnl!PsReturnPoolQuota` at `0x140012148`
- `ntoskrnl!PsReturnPoolQuota` at `0x140012267`
- `ntoskrnl!IofCallDriver` at `0x140012309`
- `ntoskrnl!IofCallDriver` at `0x140012309`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140011d7b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140011f07`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140011d7b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140011f07`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400121dc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400121dc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140011c68`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140012221`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140011c68`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140012221`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011e3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011e3e`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400122e1`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400122e1`
- `ntoskrnl!EtwWrite` at `0x14001204e`
- `ntoskrnl!EtwWrite` at `0x14001204e`
- `TDI!TdiReturnChainedReceives` at `0x140012184`
- `TDI!TdiReturnChainedReceives` at `0x140012184`

## pseudocode

```c
__int64 __fastcall AfdTLBufferedSendCompleteBatch(__int64 *a1)
{
  __int64 v1; // rbx
  unsigned int v2; // r15d
  unsigned __int64 v4; // rdi
  int v5; // edx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rcx
  int v9; // ecx
  SIZE_T v10; // rcx
  struct _KPROCESS *v11; // r13
  _BYTE *v12; // r12
  ULONG_PTR v13; // r8
  unsigned __int64 v14; // r14
  __int64 result; // rax
  signed __int64 v16; // rcx
  unsigned __int16 v17; // dx
  int v18; // ecx
  __int16 v19; // ax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  char *v22; // r14
  __int64 v23; // rax
  PEPROCESS v24; // rax
  unsigned int v25; // eax
  IRP *v26; // r13
  __int64 v27; // rdx
  signed __int64 v28; // rcx
  int v29; // [rsp+30h] [rbp-D0h] BYREF
  int v30; // [rsp+38h] [rbp-C8h] BYREF
  int v31; // [rsp+40h] [rbp-C0h] BYREF
  int v32; // [rsp+48h] [rbp-B8h] BYREF
  int v33; // [rsp+50h] [rbp-B0h] BYREF
  PEPROCESS v34; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A0h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+68h] [rbp-98h] BYREF
  __int64 v37; // [rsp+80h] [rbp-80h] BYREF
  __int64 v38; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v39[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v40; // [rsp+A0h] [rbp-60h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v42; // [rsp+B8h] [rbp-48h] BYREF
  GUID ActivityId; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v44; // [rsp+D8h] [rbp-28h]
  __int64 v45; // [rsp+E0h] [rbp-20h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+F0h] [rbp-10h] BYREF
  int *v47; // [rsp+100h] [rbp+0h]
  __int64 v48; // [rsp+108h] [rbp+8h]
  PEPROCESS *v49; // [rsp+110h] [rbp+10h]
  __int64 v50; // [rsp+118h] [rbp+18h]
  __int64 *v51; // [rsp+120h] [rbp+20h]
  __int64 v52; // [rsp+128h] [rbp+28h]
  int *v53; // [rsp+130h] [rbp+30h]
  __int64 v54; // [rsp+138h] [rbp+38h]
  __int64 *v55; // [rsp+140h] [rbp+40h]
  __int64 v56; // [rsp+148h] [rbp+48h]
  int *v57; // [rsp+150h] [rbp+50h]
  __int64 v58; // [rsp+158h] [rbp+58h]
  int *v59; // [rsp+160h] [rbp+60h]
  __int64 v60; // [rsp+168h] [rbp+68h]

  v1 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v2 = 0;
  do
  {
    v4 = a1[1];
    if ( v1 != *(_QWORD *)(v4 + 48) )
    {
      if ( v1 )
      {
        AfdCompleteBufferedSendsUnlock(v1, &LockHandle);
        v28 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v1 + 48), -v2) - v2;
        if ( v28 <= 0 )
        {
          if ( v28 )
            __fastfail(0xEu);
          AfdCloseConnection(v1);
        }
      }
      v1 = *(_QWORD *)(v4 + 48);
      v2 = 0;
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(*(_QWORD *)(v1 + 8) + 56LL), &LockHandle);
    }
    v5 = *((_DWORD *)a1 + 4);
    v6 = *((unsigned int *)a1 + 6);
    v7 = *(_QWORD *)(v4 + 56);
    v8 = *(_QWORD *)(v1 + 8);
    v42 = 0;
    if ( g_AfdEtwTraceEnable || Microsoft_Windows_Networking_CorrelationEnabled )
    {
      v45 = 0;
      v44 = v8;
      v42 = v4;
    }
    if ( g_AfdEtwTraceEnable )
    {
      *(_DWORD *)&EventDescriptor.Id = AFD_EVENT_SEND;
      *(_WORD *)&EventDescriptor.Opcode = -5364;
      HIBYTE(EventDescriptor.Task) = 3;
      v23 = 0;
      if ( v8 )
      {
        LOBYTE(v23) = *(_WORD *)v8 != 0xAFD1;
        ++v23;
      }
      v33 = v5;
      EventDescriptor.Keyword = v23 | 0x8000000000000024uLL;
      v32 = v6;
      v38 = v7;
      EventDescriptor.Level = ((v5 >> 31) & 0xFE) + 4;
      v31 = 1;
      v37 = v8;
      v30 = 3073;
      v29 = 1;
      v34 = 0;
      *(_QWORD *)ActivityId.Data4 = 0;
      *(_QWORD *)&ActivityId.Data1 = v4;
      v24 = v8 ? *(PEPROCESS *)(v8 + 48) : IoGetCurrentProcess();
      v34 = v24;
      *(_QWORD *)&UserData.Size = 4;
      UserData.Ptr = (ULONGLONG)&v29;
      v48 = 4;
      v47 = &v30;
      v49 = &v34;
      v51 = &v37;
      v53 = &v31;
      v55 = &v38;
      v57 = &v32;
      v59 = &v33;
      v50 = 8;
      v52 = 8;
      v54 = 4;
      v56 = 8;
      v58 = 4;
      v60 = 4;
      EtwWrite(g_AfdEtwHandle, &EventDescriptor, &ActivityId, 8u, &UserData);
      if ( g_AfdEtwTraceEnable )
        goto LABEL_49;
    }
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
    {
LABEL_49:
      if ( Microsoft_Windows_Networking_CorrelationEnabled )
        EtwEx_tidActivityInfo(v8, &ActivityStop, &v42, v7, 2);
    }
    v9 = *((_DWORD *)a1 + 4);
    *(_DWORD *)(v1 + 120) -= *((_DWORD *)a1 + 6);
    --*(_DWORD *)(v1 + 124);
    if ( v9 < 0 )
    {
      v26 = *(IRP **)(v1 + 128);
      v35 = *(_QWORD *)(v1 + 8);
      if ( v26 )
        *(_QWORD *)(v1 + 128) = 0;
      if ( (unsigned int)(v9 + 1073741300) <= 1 || v9 == -1073741508 )
        *(_DWORD *)(v1 + 4) |= 0x2000u;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      AFDETW_TRACEABORT(2, 8022, v35, 15);
      AfdBeginAbort(v1);
      if ( v26 )
        IofCallDriver(*(PDEVICE_OBJECT *)(v1 + 24), v26);
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v35 + 56), &LockHandle);
      LOBYTE(v27) = 1;
      AfdDeleteConnectedReference(v1, v27);
    }
    *(_DWORD *)(*(_QWORD *)(v4 + 56) + 40LL) = *(_DWORD *)(v4 + 72);
    v10 = *(unsigned int *)(v4 + 72);
    v11 = *(struct _KPROCESS **)(v1 + 32);
    if ( (_DWORD)v10 == AfdBufferTagSize )
    {
      v19 = *(_WORD *)(v4 + 96);
      if ( (v19 & 0x10) != 0 )
      {
        v40 = *(_QWORD **)(v4 + 48);
        v39[1] = 0;
        v20 = (_QWORD *)*v40;
        *v40 = 0;
        *(_WORD *)(v4 + 96) &= 0xFFEDu;
        v39[0] = AfdTLDontCareIOCompletion;
        (*(void (__fastcall **)(_QWORD, _QWORD *, __int64, __int64))(v20[1] + 48LL))(*v20, v39, v6, v7);
      }
      else if ( (v19 & 8) != 0 )
      {
        *(_WORD *)(v4 + 96) = v19 & 0xFFF7;
        TdiReturnChainedReceives((PVOID *)(v4 + 48), 1u);
      }
      v21 = *(_QWORD *)(v4 + 40);
      if ( v21 == v4 + 104 )
      {
        if ( v11 )
          PsReturnPoolQuota(v11, (POOL_TYPE)512, *(unsigned __int16 *)(v4 + 98) + 104LL);
        goto LABEL_33;
      }
      if ( v21 )
      {
        PplFreeToLookasideList(PplAddressPool, v21);
        *(_QWORD *)(v4 + 40) = 0;
      }
      if ( (*(_WORD *)(v4 + 96) & 0x100) == 0 )
      {
        if ( v11 )
          PsReturnPoolQuota(v11, (POOL_TYPE)512, *(unsigned __int16 *)(v4 + 98) + 104LL);
        *(_WORD *)(v4 + 96) |= 0x100u;
      }
      v22 = (char *)AfdPplBufferTagPool + 128 * (unsigned __int64)(unsigned int)(*(_DWORD *)(v4 + 92) + 1);
      if ( !v22[176] )
        PplpLazyInitializeLookasideList((__int64)AfdPplBufferTagPool, (__int64)(v22 + 64));
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v22 + 64), (PVOID)v4);
    }
    else
    {
      if ( *(unsigned __int16 *)(v4 + 98) != (_DWORD)AfdStandardAddressLength
        || (unsigned int)v10 > (unsigned int)AfdHugeBufferSize )
      {
        if ( v11 )
        {
          v25 = AfdCalculateBufferSize(v10);
          PsReturnPoolQuota(v11, (POOL_TYPE)512, v25);
        }
        v17 = *(_WORD *)(v4 + 96);
        v18 = (v17 >> 5) & 3;
        if ( v18 == 1 )
        {
          v4 = *(_QWORD *)(v4 + 104);
        }
        else if ( v18 )
        {
          if ( v18 == 2 )
            v4 = *(_QWORD *)(v4 + 56);
          else
            v4 = *(_QWORD *)(v4 + 112);
        }
        if ( (v17 & 0x80u) != 0 )
          v4 -= *(_QWORD *)(v4 - 8);
LABEL_33:
        ExFreePoolWithTag((PVOID)v4, 0x42646641u);
        goto LABEL_20;
      }
      if ( (_DWORD)v10 == (_DWORD)AfdSmallBufferSize )
      {
        v12 = AfdPplSmallBufferPool;
        v13 = AfdPplSmallBufferSize;
      }
      else if ( (_DWORD)v10 == (_DWORD)AfdMediumBufferSize )
      {
        v12 = AfdPplMediumBufferPool;
        v13 = AfdPplMediumBufferSize;
      }
      else if ( (_DWORD)v10 == (_DWORD)AfdLargeBufferSize )
      {
        v12 = AfdPplLargeBufferPool;
        v13 = AfdPplLargeBufferSize;
      }
      else
      {
        v12 = AfdPplHugeBufferPool;
        v13 = AfdPplHugeBufferSize;
      }
      if ( (*(_WORD *)(v4 + 96) & 0x100) == 0 )
      {
        if ( v11 )
          PsReturnPoolQuota(*(PEPROCESS *)(v1 + 32), (POOL_TYPE)512, v13);
        *(_WORD *)(v4 + 96) |= 0x100u;
      }
      v14 = (unsigned __int64)(unsigned int)(*(_DWORD *)(v4 + 92) + 1) << 7;
      if ( !v12[v14 + 176] )
        PplpLazyInitializeLookasideList((__int64)v12, (__int64)&v12[v14 + 64]);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)&v12[v14 + 64], (PVOID)v4);
    }
LABEL_20:
    a1 = (__int64 *)*a1;
    ++v2;
  }
  while ( a1 );
  AfdCompleteBufferedSendsUnlock(v1, &LockHandle);
  result = v2;
  v16 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v1 + 48), -v2) - v2;
  if ( v16 <= 0 )
  {
    if ( v16 )
      __fastfail(0xEu);
    return AfdCloseConnection(v1);
  }
  return result;
}

```

## disassembly

```asm
0x140011bf0  push    rbp
0x140011bf2  push    rbx
0x140011bf3  push    rsi
0x140011bf4  push    rdi
0x140011bf5  push    r12
0x140011bf7  push    r13
0x140011bf9  push    r14
0x140011bfb  push    r15
0x140011bfd  lea     rbp, [rsp-88h]
0x140011c05  sub     rsp, 188h
0x140011c0c  mov     rax, cs:__security_cookie
0x140011c13  xor     rax, rsp
0x140011c16  mov     [rbp+0C0h+var_50], rax
0x140011c1a  xor     eax, eax
0x140011c1c  xor     ebx, ebx
0x140011c1e  xorps   xmm0, xmm0
0x140011c21  mov     qword ptr [rsp+1C0h+LockHandle.OldIrql], rax
0x140011c26  movups  xmmword ptr [rsp+1C0h+LockHandle.LockQueue.Next], xmm0
0x140011c2b  xor     r15d, r15d
0x140011c2e  mov     rsi, rcx
0x140011c31  mov     r10d, 0AFD1h
0x140011c37  mov     r11, 8000000000000024h
0x140011c41  mov     rdi, [rsi+8]
0x140011c45  cmp     rbx, [rdi+30h]
0x140011c49  jz      short loc_140011C84
0x140011c4b  test    rbx, rbx
0x140011c4e  jnz     loc_14001229C
0x140011c54  mov     rbx, [rdi+30h]
0x140011c58  lea     rdx, [rsp+1C0h+LockHandle]; LockHandle
0x140011c5d  xor     r15d, r15d
0x140011c60  mov     rcx, [rbx+8]
0x140011c64  add     rcx, 38h ; '8'; SpinLock
0x140011c68  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140011c6f  nop     dword ptr [rax+rax+00h]
0x140011c74  mov     r10d, 0AFD1h
0x140011c7a  mov     r11, 8000000000000024h
0x140011c84  cmp     cs:g_AfdEtwTraceEnable, 0
0x140011c8b  xorps   xmm0, xmm0
0x140011c8e  mov     edx, [rsi+10h]
0x140011c91  mov     r8d, [rsi+18h]
0x140011c95  mov     r9, [rdi+38h]
0x140011c99  mov     rcx, [rbx+8]
0x140011c9d  movups  [rbp+0C0h+var_108], xmm0
0x140011ca1  jnz     loc_140012092
0x140011ca7  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140011cad  test    eax, eax
0x140011caf  jnz     loc_140012092
0x140011cb5  cmp     cs:g_AfdEtwTraceEnable, 0
0x140011cbc  jnz     loc_140011F18
0x140011cc2  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140011cc8  test    eax, eax
0x140011cca  jnz     loc_140012067
0x140011cd0  mov     ecx, [rsi+10h]
0x140011cd3  mov     eax, [rsi+18h]
0x140011cd6  sub     [rbx+78h], eax
0x140011cd9  dec     dword ptr [rbx+7Ch]
0x140011cdc  test    ecx, ecx
0x140011cde  js      loc_1400121A8
0x140011ce4  mov     rcx, [rdi+38h]
0x140011ce8  mov     eax, [rdi+48h]
0x140011ceb  mov     [rcx+28h], eax
0x140011cee  mov     ecx, [rdi+48h]; Length
0x140011cf1  cmp     ecx, cs:AfdBufferTagSize
0x140011cf7  mov     r13, [rbx+20h]
0x140011cfb  jz      loc_140011E62
0x140011d01  movzx   edx, word ptr [rdi+62h]
0x140011d05  cmp     edx, cs:AfdStandardAddressLength
0x140011d0b  jnz     loc_140011DFD
0x140011d11  cmp     ecx, cs:AfdHugeBufferSize
0x140011d17  ja      loc_140011DFD
0x140011d1d  cmp     ecx, cs:AfdSmallBufferSize
0x140011d23  jz      loc_140011E4F
0x140011d29  cmp     ecx, cs:AfdMediumBufferSize
0x140011d2f  jnz     loc_1400120D8
0x140011d35  mov     r12, cs:AfdPplMediumBufferPool
0x140011d3c  mov     r8, cs:AfdPplMediumBufferSize; Amount
0x140011d43  mov     r14d, 100h
0x140011d49  test    [rdi+60h], r14w
0x140011d4e  jz      loc_14001213B
0x140011d54  mov     r14d, [rdi+5Ch]
0x140011d58  inc     r14d
0x140011d5b  shl     r14, 7
0x140011d5f  movzx   eax, byte ptr [r14+r12+0B0h]
0x140011d68  test    al, al
0x140011d6a  jz      loc_14001223C
0x140011d70  lea     rcx, [r12+40h]
0x140011d75  mov     rdx, rdi; Entry
0x140011d78  add     rcx, r14; Lookaside
0x140011d7b  call    cs:__imp_ExFreeToLookasideListEx
0x140011d82  nop     dword ptr [rax+rax+00h]
0x140011d87  mov     rsi, [rsi]
0x140011d8a  inc     r15d
0x140011d8d  mov     r10d, 0AFD1h
0x140011d93  mov     r11, 8000000000000024h
0x140011d9d  test    rsi, rsi
0x140011da0  jnz     loc_140011C41
0x140011da6  lea     rdx, [rsp+1C0h+LockHandle]
0x140011dab  mov     rcx, rbx
0x140011dae  call    AfdCompleteBufferedSendsUnlock
0x140011db3  mov     eax, r15d
0x140011db6  neg     eax
0x140011db8  movsxd  rcx, eax
0x140011dbb  lock xadd [rbx+30h], rcx
0x140011dc1  mov     eax, r15d
0x140011dc4  sub     rcx, rax
0x140011dc7  test    rcx, rcx
0x140011dca  jle     short loc_140011DED
0x140011dcc  mov     rcx, [rbp+0C0h+var_50]
0x140011dd0  xor     rcx, rsp; StackCookie
0x140011dd3  call    __security_check_cookie
0x140011dd8  add     rsp, 188h
0x140011ddf  pop     r15
0x140011de1  pop     r14
0x140011de3  pop     r13
0x140011de5  pop     r12
0x140011de7  pop     rdi
0x140011de8  pop     rsi
0x140011de9  pop     rbx
0x140011dea  pop     rbp
0x140011deb  retn
0x140011ded  jnz     loc_140012323
0x140011df3  mov     rcx, rbx
0x140011df6  call    AfdCloseConnection
0x140011dfb  jmp     short loc_140011DCC
0x140011dfd  test    r13, r13
0x140011e00  jnz     loc_1400120AF
0x140011e06  movzx   edx, word ptr [rdi+60h]
0x140011e0a  mov     ecx, edx
0x140011e0c  shr     ecx, 5
0x140011e0f  and     ecx, 3
0x140011e12  cmp     ecx, 1
0x140011e15  jz      short loc_140011E2A
0x140011e17  test    ecx, ecx
0x140011e19  jz      short loc_140011E2E
0x140011e1b  cmp     ecx, 2
0x140011e1e  jz      loc_14001215E
0x140011e24  mov     rdi, [rdi+70h]
0x140011e28  jmp     short loc_140011E2E
0x140011e2a  mov     rdi, [rdi+68h]
0x140011e2e  test    dl, dl
0x140011e30  js      loc_14001231A
0x140011e36  mov     edx, 42646641h; Tag
0x140011e3b  mov     rcx, rdi; P
0x140011e3e  call    cs:__imp_ExFreePoolWithTag
0x140011e45  nop     dword ptr [rax+rax+00h]
0x140011e4a  jmp     loc_140011D87
0x140011e4f  mov     r12, cs:AfdPplSmallBufferPool
0x140011e56  mov     r8, cs:AfdPplSmallBufferSize
0x140011e5d  jmp     loc_140011D43
0x140011e62  movzx   eax, word ptr [rdi+60h]
0x140011e66  test    al, 10h
0x140011e68  jz      loc_140012167
0x140011e6e  mov     rax, [rdi+30h]
0x140011e72  mov     edx, 0FFEDh
0x140011e77  mov     [rbp+0C0h+var_120], rax
0x140011e7b  mov     [rbp+0C0h+var_128], 0
0x140011e83  mov     rcx, [rax]
0x140011e86  mov     qword ptr [rax], 0
0x140011e8d  lea     rax, AfdTLDontCareIOCompletion
0x140011e94  and     [rdi+60h], dx
0x140011e98  lea     rdx, [rbp+0C0h+var_130]
0x140011e9c  mov     [rbp+0C0h+var_130], rax
0x140011ea0  mov     rax, [rcx+8]
0x140011ea4  mov     rcx, [rcx]
0x140011ea7  mov     rax, [rax+30h]
0x140011eab  call    _guard_dispatch_icall
0x140011eb0  mov     rdx, [rdi+28h]
0x140011eb4  lea     rax, [rdi+68h]
0x140011eb8  cmp     rdx, rax
0x140011ebb  jz      loc_140012110
0x140011ec1  test    rdx, rdx
0x140011ec4  jnz     loc_1400120F7
0x140011eca  mov     r14d, 100h
0x140011ed0  test    [rdi+60h], r14w
0x140011ed5  jz      loc_140012251
0x140011edb  mov     r14d, [rdi+5Ch]
0x140011edf  mov     rcx, cs:AfdPplBufferTagPool
0x140011ee6  inc     r14d
0x140011ee9  shl     r14, 7
0x140011eed  add     r14, rcx
0x140011ef0  movzx   eax, byte ptr [r14+0B0h]
0x140011ef8  test    al, al
0x140011efa  jz      loc_14001228E
0x140011f00  mov     rdx, rdi; Entry
0x140011f03  lea     rcx, [r14+40h]; Lookaside
0x140011f07  call    cs:__imp_ExFreeToLookasideListEx
0x140011f0e  nop     dword ptr [rax+rax+00h]
0x140011f13  jmp     loc_140011D87
0x140011f18  mov     eax, cs:AFD_EVENT_SEND
0x140011f1e  mov     dword ptr [rbp+0C0h+EventDescriptor.Id], eax
0x140011f21  movzx   eax, cs:word_14007DA7D
0x140011f28  mov     word ptr [rbp+0C0h+EventDescriptor.Opcode], ax
0x140011f2c  movzx   eax, cs:byte_14007DA7F
0x140011f33  mov     byte ptr [rbp+0C0h+EventDescriptor.Task+1], al
0x140011f36  xor     eax, eax
0x140011f38  test    rcx, rcx
0x140011f3b  jz      short loc_140011F47
0x140011f3d  cmp     [rcx], r10w
0x140011f41  setnz   al
0x140011f44  inc     rax
0x140011f47  or      rax, r11
0x140011f4a  mov     [rsp+1C0h+var_170], edx
0x140011f4e  mov     [rbp+0C0h+EventDescriptor.Keyword], rax
0x140011f52  mov     eax, edx
0x140011f54  sar     eax, 1Fh
0x140011f57  and     al, 0FEh
0x140011f59  mov     [rsp+1C0h+var_178], r8d
0x140011f5e  add     al, 4
0x140011f60  mov     [rbp+0C0h+var_138], r9
0x140011f64  mov     [rbp+0C0h+EventDescriptor.Level], al
0x140011f67  mov     [rsp+1C0h+var_180], 1
0x140011f6f  mov     [rbp+0C0h+var_140], rcx
0x140011f73  mov     [rsp+1C0h+var_188], 0C01h
0x140011f7b  mov     [rsp+1C0h+var_190], 1
0x140011f83  mov     [rsp+1C0h+var_168], 0
0x140011f8c  mov     qword ptr [rbp+0C0h+ActivityId.Data4], 0
0x140011f94  mov     qword ptr [rbp+0C0h+ActivityId.Data1], rdi
0x140011f98  test    rcx, rcx
0x140011f9b  jz      loc_1400122E1
0x140011fa1  mov     rax, [rcx+30h]
0x140011fa5  mov     rcx, cs:g_AfdEtwHandle; RegHandle
0x140011fac  lea     r8, [rbp+0C0h+ActivityId]; ActivityId
0x140011fb0  mov     [rsp+1C0h+var_168], rax
0x140011fb5  lea     rdx, [rbp+0C0h+EventDescriptor]; EventDescriptor
0x140011fb9  lea     rax, [rsp+1C0h+var_190]
0x140011fbe  mov     qword ptr [rbp+0C0h+var_D0.Size], 4
0x140011fc6  mov     [rbp+0C0h+var_D0.Ptr], rax
0x140011fca  mov     r9d, 8; UserDataCount
0x140011fd0  lea     rax, [rsp+1C0h+var_188]
0x140011fd5  mov     [rbp+0C0h+var_B8], 4
0x140011fdd  mov     [rbp+0C0h+var_C0], rax
0x140011fe1  lea     rax, [rsp+1C0h+var_168]
0x140011fe6  mov     [rbp+0C0h+var_B0], rax
0x140011fea  lea     rax, [rbp+0C0h+var_140]
0x140011fee  mov     [rbp+0C0h+var_A0], rax
0x140011ff2  lea     rax, [rsp+1C0h+var_180]
0x140011ff7  mov     [rbp+0C0h+var_90], rax
0x140011ffb  lea     rax, [rbp+0C0h+var_138]
0x140011fff  mov     [rbp+0C0h+var_80], rax
0x140012003  lea     rax, [rsp+1C0h+var_178]
0x140012008  mov     [rbp+0C0h+var_70], rax
0x14001200c  lea     rax, [rsp+1C0h+var_170]
0x140012011  mov     [rbp+0C0h+var_60], rax
0x140012015  lea     rax, [rbp+0C0h+var_D0]
0x140012019  mov     [rsp+1C0h+UserData], rax; UserData
0x14001201e  mov     [rbp+0C0h+var_A8], 8
0x140012026  mov     [rbp+0C0h+var_98], 8
0x14001202e  mov     [rbp+0C0h+var_88], 4
0x140012036  mov     [rbp+0C0h+var_78], 8
0x14001203e  mov     [rbp+0C0h+var_68], 4
0x140012046  mov     [rbp+0C0h+var_58], 4
0x14001204e  call    cs:__imp_EtwWrite
0x140012055  nop     dword ptr [rax+rax+00h]
0x14001205a  cmp     cs:g_AfdEtwTraceEnable, 0
0x140012061  jz      loc_140011CC2
0x140012067  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14001206d  test    eax, eax
0x14001206f  jz      loc_140011CD0
0x140012075  lea     r8, [rbp+0C0h+var_108]
0x140012079  mov     dword ptr [rsp+1C0h+UserData], 2
0x140012081  lea     rdx, ActivityStop
0x140012088  call    EtwEx_tidActivityInfo
0x14001208d  jmp     loc_140011CD0
0x140012092  mov     [rbp+0C0h+var_E0], 0
0x14001209a  mov     [rbp+0C0h+var_E8], rcx
0x14001209e  mov     qword ptr [rbp+0C0h+var_108+8], 0
0x1400120a6  mov     qword ptr [rbp+0C0h+var_108], rdi
0x1400120aa  jmp     loc_140011CB5
0x1400120af  movzx   r8d, cs:AfdTdiStackSize
0x1400120b7  call    AfdCalculateBufferSize
0x1400120bc  mov     r8d, eax; Amount
0x1400120bf  mov     edx, 200h; PoolType
0x1400120c4  mov     rcx, r13; Process
0x1400120c7  call    cs:__imp_PsReturnPoolQuota
0x1400120ce  nop     dword ptr [rax+rax+00h]
0x1400120d3  jmp     loc_140011E06
0x1400120d8  cmp     ecx, cs:AfdLargeBufferSize
0x1400120de  jnz     loc_140012195
0x1400120e4  mov     r12, cs:AfdPplLargeBufferPool
0x1400120eb  mov     r8, cs:AfdPplLargeBufferSize
0x1400120f2  jmp     loc_140011D43
0x1400120f7  mov     rcx, cs:PplAddressPool
0x1400120fe  call    PplFreeToLookasideList
0x140012103  mov     qword ptr [rdi+28h], 0
0x14001210b  jmp     loc_140011ECA
0x140012110  test    r13, r13
0x140012113  jz      loc_140011E36
0x140012119  movzx   r8d, word ptr [rdi+62h]
0x14001211e  mov     edx, 200h; PoolType
0x140012123  add     r8, 68h ; 'h'; Amount
0x140012127  mov     rcx, r13; Process
0x14001212a  call    cs:__imp_PsReturnPoolQuota
0x140012131  nop     dword ptr [rax+rax+00h]
0x140012136  jmp     loc_140011E36
0x14001213b  test    r13, r13
0x14001213e  jz      short loc_140012154
0x140012140  mov     edx, 200h; PoolType
0x140012145  mov     rcx, r13; Process
0x140012148  call    cs:__imp_PsReturnPoolQuota
0x14001214f  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
