# AfdTLFastDgramSendComplete

- ea: `0x14000ea50`
- end: `0x14000f388`
- name: `AfdTLFastDgramSendComplete`
- size: `2360`
- prototype: `__int64 __fastcall(char *Entry, int, int, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1400563d8`

## callees

- `0x14000ea50`
- `0x14000f390`
- `0x14000f450`
- `0x14000f744`
- `0x14000fa00`
- `0x140010948`
- `0x140013990`
- `0x14001b800`
- `0x140050be4`
- `0x14005d8e4`
- `0x1400726a0`
- `0x140072780`
- `0x1400930cc`
- `0x140093658`

## import_xrefs

- `ntoskrnl!PsReturnPoolQuota` at `0x14000eec5`
- `ntoskrnl!PsReturnPoolQuota` at `0x14000f020`
- `ntoskrnl!PsReturnPoolQuota` at `0x14000f03e`
- `ntoskrnl!PsReturnPoolQuota` at `0x14000f261`
- `ntoskrnl!PsReturnPoolQuota` at `0x14000eec5`
- `ntoskrnl!PsReturnPoolQuota` at `0x14000f020`
- `ntoskrnl!PsReturnPoolQuota` at `0x14000f03e`
- `ntoskrnl!PsReturnPoolQuota` at `0x14000f261`
- `ntoskrnl!MmSizeOfMdl` at `0x14000ee4d`
- `ntoskrnl!MmSizeOfMdl` at `0x14000ee4d`
- `ntoskrnl!KeSetEvent` at `0x14000eff5`
- `ntoskrnl!KeSetEvent` at `0x14000eff5`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140075af5`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140075af5`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140075b2f`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140075b2f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000ec45`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000ee2c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000ef76`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000ec45`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000ee2c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000ef76`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000ebaf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140075b1c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000ebaf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140075b1c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000eb26`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000eb26`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ed31`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ed31`
- `ntoskrnl!EtwWrite` at `0x14000f1de`
- `ntoskrnl!EtwWrite` at `0x14000f1de`
- `TDI!TdiReturnChainedReceives` at `0x14000f079`
- `TDI!TdiReturnChainedReceives` at `0x14000f079`

## pseudocode

```c
__int64 __fastcall AfdTLFastDgramSendComplete(char *Entry, int a2, int a3, __int64 a4)
{
  int v4; // esi
  char *v5; // rdi
  __int64 v6; // rcx
  PVOID *v7; // r12
  __int64 result; // rax
  __int64 v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  unsigned int v14; // eax
  int v15; // eax
  __int64 v16; // rax
  unsigned int v17; // esi
  struct _KPROCESS *v18; // r13
  int v19; // r14d
  _BYTE *v20; // r14
  ULONG_PTR v21; // r8
  unsigned __int64 v22; // rsi
  bool v23; // zf
  unsigned __int16 v24; // dx
  int v25; // ecx
  __int16 v26; // ax
  _QWORD *v27; // rcx
  PVOID *v28; // rsi
  char *v29; // rsi
  unsigned int v30; // edx
  char *v31; // r14
  int v32; // esi
  __int64 v33; // r9
  __int64 v34; // [rsp+28h] [rbp-D8h]
  __int64 v35; // [rsp+40h] [rbp-C0h]
  char *v36; // [rsp+48h] [rbp-B8h]
  char v37; // [rsp+60h] [rbp-A0h]
  int v38; // [rsp+68h] [rbp-98h] BYREF
  int v39; // [rsp+70h] [rbp-90h] BYREF
  int v40; // [rsp+78h] [rbp-88h] BYREF
  int v41; // [rsp+80h] [rbp-80h] BYREF
  int v42; // [rsp+88h] [rbp-78h] BYREF
  __int64 v43; // [rsp+90h] [rbp-70h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+98h] [rbp-68h] BYREF
  __int64 v45; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v46; // [rsp+B8h] [rbp-48h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v48; // [rsp+D0h] [rbp-30h] BYREF
  __int64 (__fastcall *v49)(); // [rsp+E0h] [rbp-20h] BYREF
  __int64 v50; // [rsp+E8h] [rbp-18h]
  _QWORD *v51; // [rsp+F0h] [rbp-10h]
  GUID ActivityId; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v53; // [rsp+108h] [rbp+8h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+110h] [rbp+10h] BYREF
  int *v55; // [rsp+120h] [rbp+20h]
  __int64 v56; // [rsp+128h] [rbp+28h]
  __int64 *v57; // [rsp+130h] [rbp+30h]
  __int64 v58; // [rsp+138h] [rbp+38h]
  __int64 *v59; // [rsp+140h] [rbp+40h]
  __int64 v60; // [rsp+148h] [rbp+48h]
  int *v61; // [rsp+150h] [rbp+50h]
  __int64 v62; // [rsp+158h] [rbp+58h]
  __int64 *v63; // [rsp+160h] [rbp+60h]
  __int64 v64; // [rsp+168h] [rbp+68h]
  int *v65; // [rsp+170h] [rbp+70h]
  __int64 v66; // [rsp+178h] [rbp+78h]
  int *v67; // [rsp+180h] [rbp+80h]
  __int64 v68; // [rsp+188h] [rbp+88h]

  v4 = *((_DWORD *)Entry + 16);
  v5 = Entry;
  v6 = *((_QWORD *)Entry + 7);
  memset(&LockHandle, 0, sizeof(LockHandle));
  *(_DWORD *)(v6 + 40) = *((_DWORD *)v5 + 18);
  if ( a2 == -1073741252 )
    goto LABEL_2;
  if ( a2 <= -1073741503 )
  {
    if ( a2 == -1073741503 )
      goto LABEL_2;
    if ( a2 > -1073741790 )
    {
      if ( a2 == -1073741670 || a2 == -1073741634 || a2 == -1073741536 )
        goto LABEL_2;
      goto LABEL_35;
    }
    if ( a2 == -1073741790 || a2 == -1073741823 || a2 == -1073741811 )
      goto LABEL_2;
    v23 = a2 == -1073741801;
  }
  else
  {
    if ( a2 <= -1073741251 )
    {
      if ( a2 == -1073741251 || a2 == -1073741306 || a2 == -1073741305 || a2 == -1073741275 )
        goto LABEL_2;
      goto LABEL_35;
    }
    if ( !a2 )
      goto LABEL_2;
    v23 = a2 == 259;
  }
  if ( !v23 )
LABEL_35:
    a2 = 0;
LABEL_2:
  v7 = (PVOID *)(v5 + 104);
  *(_DWORD *)(*((_QWORD *)v5 + 13) + 48LL) = a2;
  result = _InterlockedCompareExchange64((volatile signed __int64 *)v5 + 6, -1, 0);
  v9 = result;
  if ( !result )
    return result;
  if ( *((_QWORD *)v5 + 3) )
  {
    v36 = v5;
    v35 = *((_QWORD *)v5 + 5);
    v34 = *((_QWORD *)v5 + 7);
    AFDETW_TRACESENDMSG(1, 3102, result);
  }
  else if ( *((_DWORD *)v5 + 8) )
  {
    v36 = v5;
    v35 = *((_QWORD *)v5 + 5);
    v34 = *((_QWORD *)v5 + 7);
    AFDETW_TRACESENDTO(1, 3049, result);
  }
  else
  {
    v10 = *((_QWORD *)v5 + 7);
    v48 = 0;
    if ( g_AfdEtwTraceEnable || Microsoft_Windows_Networking_CorrelationEnabled )
    {
      v50 = 0;
      v49 = (__int64 (__fastcall *)())result;
      v48 = (unsigned __int64)v5;
    }
    if ( g_AfdEtwTraceEnable )
    {
      v23 = *(_WORD *)result == 0xAFD1;
      *(_DWORD *)&EventDescriptor.Id = AFD_EVENT_SEND;
      *(_WORD *)&EventDescriptor.Opcode = -5364;
      HIBYTE(EventDescriptor.Task) = 3;
      v42 = a2;
      v41 = a3;
      v46 = v10;
      EventDescriptor.Keyword = (!v23 + 17LL) | 0x8000000000000004uLL;
      v43 = 0;
      v40 = 1;
      v45 = result;
      EventDescriptor.Level = ((a2 >> 31) & 0xFE) + 4;
      v39 = 3403;
      v38 = 1;
      *(_QWORD *)ActivityId.Data4 = 0;
      *(_QWORD *)&ActivityId.Data1 = v5;
      v43 = *(_QWORD *)(result + 48);
      UserData.Ptr = (ULONGLONG)&v38;
      v55 = &v39;
      v57 = &v43;
      v59 = &v45;
      v61 = &v40;
      v63 = &v46;
      v65 = &v41;
      v67 = &v42;
      *(_QWORD *)&UserData.Size = 4;
      v56 = 4;
      v58 = 8;
      v60 = 8;
      v62 = 4;
      v64 = 8;
      v66 = 4;
      v68 = 4;
      EtwWrite(g_AfdEtwHandle, &EventDescriptor, &ActivityId, 8u, &UserData);
      if ( g_AfdEtwTraceEnable )
        goto LABEL_92;
    }
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
    {
LABEL_92:
      if ( Microsoft_Windows_Networking_CorrelationEnabled )
        EtwEx_tidActivityInfo(v10, &ActivityStop, &v48, a4, 2);
    }
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v9 + 56), &LockHandle);
  *(_DWORD *)(v9 + 156) -= v4;
  v14 = *(_DWORD *)(v9 + 156);
  if ( v14 >= *(_DWORD *)(v9 + 160) && v14 )
    goto LABEL_16;
  if ( *(_WORD *)v9 == 6909 )
  {
    v11 = *(unsigned int *)(v9 + 400);
    if ( (int)v11 >= 0 )
    {
      if ( *(_QWORD *)(v9 + 120) )
      {
        AfdSanPollUpdate(v9);
        *(_DWORD *)(v9 + 400) |= 0x80000000;
      }
    }
  }
  v15 = *(_DWORD *)(v9 + 8);
  if ( (v15 & 0x2000000) != 0 )
  {
    *(_DWORD *)(v9 + 8) = v15 & 0xFDFFFFFF;
    v32 = *(_DWORD *)(v9 + 72);
    *(_DWORD *)(v9 + 72) = v32 | 4;
    *(_DWORD *)(v9 + 412) = 0;
    if ( (xmmword_1400875E0 & 0x20) != 0 )
    {
      LODWORD(v34) = *(_DWORD *)(v9 + 400);
      WPP_SF_qqLLL(v12, v11, v13, v9, *(_QWORD *)(v9 + 456), v34, v32 | 4, 4, v35, v36);
    }
    if ( ((unsigned __int8)~(_BYTE)v32 & *(_BYTE *)(v9 + 400) & 4) != 0 )
    {
      v33 = *(_QWORD *)(v9 + 456);
      if ( v33 )
      {
        if ( (xmmword_1400875E0 & 0x20) != 0 )
          WPP_SF_q(1029, 15, WPP_e3713146daf23867649962a1742965d7_Traceguids, v33);
        KeSetEvent(*(PRKEVENT *)(v9 + 456), AfdPriorityBoost, 0);
      }
    }
  }
  v16 = *(_QWORD *)(v9 + 384);
  if ( v16 )
    *(_WORD *)(v16 + 100) |= 4u;
  if ( (unsigned __int8)AfdIndicatePollEvent(v9, 4, 0, &LockHandle) )
  {
    AfdNotifySockIndicateEventsUnlock(v9, 0, 0);
    goto LABEL_17;
  }
  ActivityId = 0;
  v53 = 0;
  if ( !*(_QWORD *)(v9 + 384) || !ExAcquireRundownProtection((PEX_RUNDOWN_REF)(v9 + 392)) )
  {
LABEL_16:
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    goto LABEL_17;
  }
  AfdNotifyPostEvents(v9, &LockHandle, 0);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  ExReleaseRundownProtection((PEX_RUNDOWN_REF)(v9 + 392));
LABEL_17:
  v17 = *((_DWORD *)v5 + 18);
  v18 = *(struct _KPROCESS **)(v9 + 48);
  if ( v17 == AfdBufferTagSize )
  {
    v26 = *((_WORD *)v5 + 48);
    if ( (v26 & 0x10) != 0 )
    {
      v51 = (_QWORD *)*((_QWORD *)v5 + 6);
      v50 = 0;
      v27 = (_QWORD *)*v51;
      *v51 = 0;
      *((_WORD *)v5 + 48) &= 0xFFEDu;
      v49 = AfdTLDontCareIOCompletion;
      (*(void (__fastcall **)(_QWORD, __int64 (__fastcall **)()))(v27[1] + 48LL))(*v27, &v49);
    }
    else if ( (v26 & 8) != 0 )
    {
      *((_WORD *)v5 + 48) = v26 & 0xFFF7;
      TdiReturnChainedReceives((PVOID *)v5 + 6, 1u);
    }
    v28 = (PVOID *)*((_QWORD *)v5 + 5);
    if ( v28 != v7 )
    {
      if ( v28 )
      {
        v31 = (char *)PplAddressPool + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
        if ( !v31[176] )
          PplpLazyInitializeLookasideList(PplAddressPool, v31 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v31 + 64), v28);
        *((_QWORD *)v5 + 5) = 0;
      }
      if ( (*((_WORD *)v5 + 48) & 0x100) == 0 )
      {
        if ( v18 )
          PsReturnPoolQuota(v18, (POOL_TYPE)512, *((unsigned __int16 *)v5 + 49) + 104LL);
        *((_WORD *)v5 + 48) |= 0x100u;
      }
      v29 = (char *)AfdPplBufferTagPool + 128 * (unsigned __int64)(unsigned int)(*((_DWORD *)v5 + 23) + 1);
      if ( !v29[176] )
        PplpLazyInitializeLookasideList(AfdPplBufferTagPool, v29 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v29 + 64), v5);
      return AfdDereferenceEndpoint(v9);
    }
    if ( v18 )
      PsReturnPoolQuota(v18, (POOL_TYPE)512, *((unsigned __int16 *)v5 + 49) + 104LL);
  }
  else
  {
    v19 = *((unsigned __int16 *)v5 + 49);
    if ( v19 == (_DWORD)AfdStandardAddressLength && v17 <= (unsigned int)AfdHugeBufferSize )
    {
      if ( v17 == (_DWORD)AfdSmallBufferSize )
      {
        v20 = AfdPplSmallBufferPool;
        v21 = AfdPplSmallBufferSize;
      }
      else if ( v17 == (_DWORD)AfdMediumBufferSize )
      {
        v20 = AfdPplMediumBufferPool;
        v21 = AfdPplMediumBufferSize;
      }
      else if ( v17 == (_DWORD)AfdLargeBufferSize )
      {
        v20 = AfdPplLargeBufferPool;
        v21 = AfdPplLargeBufferSize;
      }
      else
      {
        v20 = AfdPplHugeBufferPool;
        v21 = AfdPplHugeBufferSize;
      }
      if ( (*((_WORD *)v5 + 48) & 0x100) == 0 )
      {
        if ( v18 )
          PsReturnPoolQuota(*(PEPROCESS *)(v9 + 48), (POOL_TYPE)512, v21);
        *((_WORD *)v5 + 48) |= 0x100u;
      }
      v22 = (unsigned __int64)(unsigned int)(*((_DWORD *)v5 + 23) + 1) << 7;
      if ( !v20[v22 + 176] )
        PplpLazyInitializeLookasideList(v20, &v20[v22 + 64]);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)&v20[v22 + 64], v5);
      return AfdDereferenceEndpoint(v9);
    }
    if ( v18 )
    {
      v37 = AfdTdiStackSize;
      v30 = ((v17 + 15) & 0xFFFFFFF0)
          + 128
          + ((MmSizeOfMdl(0, *((unsigned int *)v5 + 18)) + 15) & 0xFFFFFFF0)
          + v19
          + (((unsigned __int16)(72 * v37 + 208) + 15) & 0xFFFFFFF0);
      if ( v30 < 0x1000 )
      {
        v30 += v37 == AfdTdiStackSize ? AfdAlignmentOverhead : AfdBufferAlignment - 16;
        if ( v30 >= 0x1000 )
          v30 = 4096;
      }
      PsReturnPoolQuota(v18, (POOL_TYPE)512, v30);
    }
    v24 = *((_WORD *)v5 + 48);
    v25 = (v24 >> 5) & 3;
    if ( v25 == 1 )
    {
      v5 = (char *)*v7;
    }
    else if ( v25 )
    {
      if ( v25 == 2 )
        v5 = (char *)*((_QWORD *)v5 + 7);
      else
        v5 = (char *)*((_QWORD *)v5 + 14);
    }
    if ( (v24 & 0x80u) != 0 )
      v5 -= *((_QWORD *)v5 - 1);
  }
  ExFreePoolWithTag(v5, 0x42646641u);
  return AfdDereferenceEndpoint(v9);
}

```

## disassembly

```asm
0x14000ea50  push    rbp
0x14000ea52  push    rbx
0x14000ea53  push    rsi
0x14000ea54  push    rdi
0x14000ea55  push    r12
0x14000ea57  push    r13
0x14000ea59  push    r14
0x14000ea5b  push    r15
0x14000ea5d  lea     rbp, [rsp-0A8h]
0x14000ea65  sub     rsp, 1A8h
0x14000ea6c  mov     rax, cs:__security_cookie
0x14000ea73  xor     rax, rsp
0x14000ea76  mov     [rbp+0E0h+var_50], rax
0x14000ea7d  mov     esi, [rcx+40h]
0x14000ea80  xor     eax, eax
0x14000ea82  mov     rdi, rcx
0x14000ea85  mov     qword ptr [rbp+0E0h+LockHandle.OldIrql], rax
0x14000ea89  mov     rcx, [rcx+38h]
0x14000ea8d  xorps   xmm0, xmm0
0x14000ea90  xor     r13d, r13d
0x14000ea93  movups  xmmword ptr [rbp+0E0h+LockHandle.LockQueue.Next], xmm0
0x14000ea97  mov     eax, [rdi+48h]
0x14000ea9a  mov     [rcx+28h], eax
0x14000ea9d  cmp     edx, 0C000023Ch
0x14000eaa3  jnz     loc_14000ECC0
0x14000eaa9  mov     rax, [rdi+68h]
0x14000eaad  lea     r12, [rdi+68h]
0x14000eab1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000eab8  mov     [rax+30h], edx
0x14000eabb  xor     eax, eax
0x14000eabd  lock cmpxchg [rdi+30h], rcx
0x14000eac3  mov     rbx, rax
0x14000eac6  jz      loc_14000EC59
0x14000eacc  cmp     [rdi+18h], r13
0x14000ead0  jnz     loc_14000EC7D
0x14000ead6  cmp     [rdi+20h], r13d
0x14000eada  jnz     loc_14000EED6
0x14000eae0  cmp     cs:g_AfdEtwTraceEnable, r13d
0x14000eae7  mov     rcx, [rdi+38h]
0x14000eaeb  movups  [rbp+0E0h+var_110], xmm0
0x14000eaef  jnz     loc_14000F236
0x14000eaf5  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14000eafb  test    eax, eax
0x14000eafd  jnz     loc_14000F236
0x14000eb03  cmp     cs:g_AfdEtwTraceEnable, r13d
0x14000eb0a  jnz     loc_14000F0AD
0x14000eb10  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14000eb16  test    eax, eax
0x14000eb18  jnz     loc_14000F1F7
0x14000eb1e  lea     rcx, [rbx+38h]; SpinLock
0x14000eb22  lea     rdx, [rbp+0E0h+LockHandle]; LockHandle
0x14000eb26  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000eb2d  nop     dword ptr [rax+rax+00h]
0x14000eb32  sub     [rbx+9Ch], esi
0x14000eb38  mov     eax, [rbx+9Ch]
0x14000eb3e  cmp     eax, [rbx+0A0h]
0x14000eb44  jnb     loc_14000EF19
0x14000eb4a  mov     eax, 1AFDh
0x14000eb4f  cmp     [rbx], ax
0x14000eb52  jz      loc_14000F2F4
0x14000eb58  mov     eax, [rbx+8]
0x14000eb5b  bt      eax, 19h
0x14000eb5f  jb      loc_14000EF8F
0x14000eb65  mov     rax, [rbx+180h]
0x14000eb6c  test    rax, rax
0x14000eb6f  jnz     loc_14000F276
0x14000eb75  lea     r9, [rbp+0E0h+LockHandle]
0x14000eb79  xor     r8d, r8d
0x14000eb7c  mov     edx, 4
0x14000eb81  mov     rcx, rbx
0x14000eb84  call    AfdIndicatePollEvent
0x14000eb89  test    al, al
0x14000eb8b  jnz     loc_14000F36D
0x14000eb91  xor     eax, eax
0x14000eb93  xorps   xmm0, xmm0
0x14000eb96  movups  xmmword ptr [rbp+0E0h+ActivityId.Data1], xmm0
0x14000eb9a  mov     [rbp+0E0h+var_D8], rax
0x14000eb9e  cmp     [rbx+180h], rax
0x14000eba5  jnz     loc_140075AEE
0x14000ebab  lea     rcx, [rbp+0E0h+LockHandle]; LockHandle
0x14000ebaf  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000ebb6  nop     dword ptr [rax+rax+00h]
0x14000ebbb  mov     esi, [rdi+48h]
0x14000ebbe  cmp     esi, cs:AfdBufferTagSize
0x14000ebc4  mov     r13, [rbx+30h]
0x14000ebc8  jz      loc_14000ED90
0x14000ebce  movzx   r14d, word ptr [rdi+62h]
0x14000ebd3  cmp     r14d, cs:AfdStandardAddressLength
0x14000ebda  jnz     loc_14000ECF0
0x14000ebe0  cmp     esi, cs:AfdHugeBufferSize
0x14000ebe6  ja      loc_14000ECF0
0x14000ebec  cmp     esi, cs:AfdSmallBufferSize
0x14000ebf2  jz      loc_14000ED7D
0x14000ebf8  cmp     esi, cs:AfdMediumBufferSize
0x14000ebfe  jnz     loc_14000EF26
0x14000ec04  mov     r14, cs:AfdPplMediumBufferPool
0x14000ec0b  mov     r8, cs:AfdPplMediumBufferSize; Amount
0x14000ec12  mov     esi, 100h
0x14000ec17  test    [rdi+60h], si
0x14000ec1b  jz      loc_14000F031
0x14000ec21  mov     esi, [rdi+5Ch]
0x14000ec24  inc     esi
0x14000ec26  shl     rsi, 7
0x14000ec2a  movzx   eax, byte ptr [rsi+r14+0B0h]
0x14000ec33  test    al, al
0x14000ec35  jz      loc_14000F222
0x14000ec3b  lea     rcx, [rsi+40h]
0x14000ec3f  mov     rdx, rdi; Entry
0x14000ec42  add     rcx, r14; Lookaside
0x14000ec45  call    cs:__imp_ExFreeToLookasideListEx
0x14000ec4c  nop     dword ptr [rax+rax+00h]
0x14000ec51  mov     rcx, rbx
0x14000ec54  call    AfdDereferenceEndpoint
0x14000ec59  mov     rcx, [rbp+0E0h+var_50]
0x14000ec60  xor     rcx, rsp; StackCookie
0x14000ec63  call    __security_check_cookie
0x14000ec68  add     rsp, 1A8h
0x14000ec6f  pop     r15
0x14000ec71  pop     r14
0x14000ec73  pop     r13
0x14000ec75  pop     r12
0x14000ec77  pop     rdi
0x14000ec78  pop     rsi
0x14000ec79  pop     rbx
0x14000ec7a  pop     rbp
0x14000ec7b  retn
0x14000ec7d  mov     rax, [rdi+28h]
0x14000ec81  mov     r9d, 1
0x14000ec87  mov     [rsp+1E0h+var_198], rdi
0x14000ec8c  mov     ecx, r9d
0x14000ec8f  mov     [rsp+1E0h+var_1A0], rax
0x14000ec94  mov     rax, [rdi+38h]
0x14000ec98  mov     [rsp+1E0h+var_1A8], edx
0x14000ec9c  mov     edx, 0C1Eh
0x14000eca1  mov     [rsp+1E0h+var_1B0], r8d
0x14000eca6  mov     r8, rbx
0x14000eca9  mov     [rsp+1E0h+var_1B8], rax
0x14000ecae  mov     dword ptr [rsp+1E0h+UserData], 1
0x14000ecb6  call    AFDETW_TRACESENDMSG
0x14000ecbb  jmp     loc_14000EB1E
0x14000ecc0  cmp     edx, 0C0000141h
0x14000ecc6  jle     short loc_14000ED42
0x14000ecc8  cmp     edx, 0C000023Dh
0x14000ecce  jle     loc_14000F2C5
0x14000ecd4  test    edx, edx
0x14000ecd6  jz      loc_14000EAA9
0x14000ecdc  cmp     edx, 103h
0x14000ece2  jz      loc_14000EAA9
0x14000ece8  mov     edx, r13d
0x14000eceb  jmp     loc_14000EAA9
0x14000ecf0  test    r13, r13
0x14000ecf3  jnz     loc_14000EE3D
0x14000ecf9  movzx   edx, word ptr [rdi+60h]
0x14000ecfd  mov     ecx, edx
0x14000ecff  shr     ecx, 5
0x14000ed02  and     ecx, 3
0x14000ed05  cmp     ecx, 1
0x14000ed08  jz      short loc_14000ED1D
0x14000ed0a  test    ecx, ecx
0x14000ed0c  jz      short loc_14000ED21
0x14000ed0e  cmp     ecx, 2
0x14000ed11  jz      loc_14000F053
0x14000ed17  mov     rdi, [rdi+70h]
0x14000ed1b  jmp     short loc_14000ED21
0x14000ed1d  mov     rdi, [r12]
0x14000ed21  test    dl, dl
0x14000ed23  js      loc_14000F37F
0x14000ed29  mov     edx, 42646641h; Tag
0x14000ed2e  mov     rcx, rdi; P
0x14000ed31  call    cs:__imp_ExFreePoolWithTag
0x14000ed38  nop     dword ptr [rax+rax+00h]
0x14000ed3d  jmp     loc_14000EC51
0x14000ed42  jz      loc_14000EAA9
0x14000ed48  cmp     edx, 0C0000022h
0x14000ed4e  jg      loc_14000F29C
0x14000ed54  jz      loc_14000EAA9
0x14000ed5a  cmp     edx, 0C0000001h
0x14000ed60  jz      loc_14000EAA9
0x14000ed66  cmp     edx, 0C000000Dh
0x14000ed6c  jz      loc_14000EAA9
0x14000ed72  cmp     edx, 0C0000017h
0x14000ed78  jmp     loc_14000ECE2
0x14000ed7d  mov     r14, cs:AfdPplSmallBufferPool
0x14000ed84  mov     r8, cs:AfdPplSmallBufferSize
0x14000ed8b  jmp     loc_14000EC12
0x14000ed90  movzx   eax, word ptr [rdi+60h]
0x14000ed94  test    al, 10h
0x14000ed96  jz      loc_14000F05C
0x14000ed9c  mov     rax, [rdi+30h]
0x14000eda0  mov     edx, 0FFEDh
0x14000eda5  mov     [rbp+0E0h+var_F0], rax
0x14000eda9  mov     [rbp+0E0h+var_F8], 0
0x14000edb1  mov     rcx, [rax]
0x14000edb4  mov     qword ptr [rax], 0
0x14000edbb  lea     rax, AfdTLDontCareIOCompletion
0x14000edc2  and     [rdi+60h], dx
0x14000edc6  lea     rdx, [rbp+0E0h+var_100]
0x14000edca  mov     [rbp+0E0h+var_100], rax
0x14000edce  mov     rax, [rcx+8]
0x14000edd2  mov     rcx, [rcx]
0x14000edd5  mov     rax, [rax+30h]
0x14000edd9  call    _guard_dispatch_icall
0x14000edde  mov     rsi, [rdi+28h]
0x14000ede2  cmp     rsi, r12
0x14000ede5  jz      loc_14000F006
0x14000edeb  test    rsi, rsi
0x14000edee  jnz     loc_14000EF45
0x14000edf4  mov     esi, 100h
0x14000edf9  test    [rdi+60h], si
0x14000edfd  jz      loc_14000F24B
0x14000ee03  mov     esi, [rdi+5Ch]
0x14000ee06  mov     rcx, cs:AfdPplBufferTagPool
0x14000ee0d  inc     esi
0x14000ee0f  shl     rsi, 7
0x14000ee13  add     rsi, rcx
0x14000ee16  movzx   eax, byte ptr [rsi+0B0h]
0x14000ee1d  test    al, al
0x14000ee1f  jz      loc_14000F280
0x14000ee25  mov     rdx, rdi; Entry
0x14000ee28  lea     rcx, [rsi+40h]; Lookaside
0x14000ee2c  call    cs:__imp_ExFreeToLookasideListEx
0x14000ee33  nop     dword ptr [rax+rax+00h]
0x14000ee38  jmp     loc_14000EC51
0x14000ee3d  movzx   eax, cs:AfdTdiStackSize
0x14000ee44  mov     rdx, rsi; Length
0x14000ee47  xor     ecx, ecx; Base
0x14000ee49  mov     [rsp+1E0h+var_180], al
0x14000ee4d  call    cs:__imp_MmSizeOfMdl
0x14000ee54  nop     dword ptr [rax+rax+00h]
0x14000ee59  movsx   r9d, [rsp+1E0h+var_180]
0x14000ee5f  movzx   ecx, r9w
0x14000ee63  shl     cx, 3
0x14000ee67  lea     r8d, [rax+0Fh]
0x14000ee6b  mov     eax, 0D0h
0x14000ee70  and     r8d, 0FFFFFFF0h
0x14000ee74  lea     edx, [rcx+r9]
0x14000ee78  mov     ecx, 1000h
0x14000ee7d  shl     dx, 3
0x14000ee81  add     dx, ax
0x14000ee84  lea     eax, [rsi+0Fh]
0x14000ee87  movzx   edx, dx
0x14000ee8a  and     eax, 0FFFFFFF0h
0x14000ee8d  add     edx, 0Fh
0x14000ee90  sub     eax, 0FFFFFF80h
0x14000ee93  and     edx, 0FFFFFFF0h
0x14000ee96  add     edx, r14d
0x14000ee99  add     edx, r8d
0x14000ee9c  add     edx, eax
0x14000ee9e  cmp     edx, ecx
0x14000eea0  jnb     short loc_14000EEBA
0x14000eea2  cmp     r9b, cs:AfdTdiStackSize
0x14000eea9  jnz     loc_14000F09D
0x14000eeaf  add     edx, cs:AfdAlignmentOverhead
0x14000eeb5  cmp     edx, ecx
0x14000eeb7  cmovnb  edx, ecx
0x14000eeba  mov     r8d, edx; Amount
0x14000eebd  mov     rcx, r13; Process
0x14000eec0  mov     edx, 200h; PoolType
0x14000eec5  call    cs:__imp_PsReturnPoolQuota
0x14000eecc  nop     dword ptr [rax+rax+00h]
0x14000eed1  jmp     loc_14000ECF9
0x14000eed6  mov     rax, [rdi+28h]
0x14000eeda  mov     r9d, 1
0x14000eee0  mov     [rsp+1E0h+var_198], rdi
0x14000eee5  mov     ecx, r9d
0x14000eee8  mov     [rsp+1E0h+var_1A0], rax
0x14000eeed  mov     rax, [rdi+38h]
0x14000eef1  mov     [rsp+1E0h+var_1A8], edx
0x14000eef5  mov     edx, 0BE9h
0x14000eefa  mov     [rsp+1E0h+var_1B0], r8d
0x14000eeff  mov     r8, rbx
0x14000ef02  mov     [rsp+1E0h+var_1B8], rax
0x14000ef07  mov     dword ptr [rsp+1E0h+UserData], 1
0x14000ef0f  call    AFDETW_TRACESENDTO
0x14000ef14  jmp     loc_14000EB1E
0x14000ef19  test    eax, eax
0x14000ef1b  jnz     loc_14000EBAB
0x14000ef21  jmp     loc_14000EB4A
0x14000ef26  cmp     esi, cs:AfdLargeBufferSize
0x14000ef2c  jnz     loc_14000F08A
0x14000ef32  mov     r14, cs:AfdPplLargeBufferPool
0x14000ef39  mov     r8, cs:AfdPplLargeBufferSize
0x14000ef40  jmp     loc_14000EC12
0x14000ef45  mov     eax, gs:1A4h
0x14000ef4d  mov     rcx, cs:PplAddressPool
0x14000ef54  lea     r14d, [rax+1]
0x14000ef58  shl     r14, 7
0x14000ef5c  add     r14, rcx
0x14000ef5f  movzx   eax, byte ptr [r14+0B0h]
0x14000ef67  test    al, al
0x14000ef69  jz      loc_14000F28E
0x14000ef6f  mov     rdx, rsi; Entry
0x14000ef72  lea     rcx, [r14+40h]; Lookaside
0x14000ef76  call    cs:__imp_ExFreeToLookasideListEx
0x14000ef7d  nop     dword ptr [rax+rax+00h]
0x14000ef82  mov     qword ptr [rdi+28h], 0
0x14000ef8a  jmp     loc_14000EDF4
0x14000ef8f  btr     eax, 19h
0x14000ef93  mov     [rbx+8], eax
0x14000ef96  mov     esi, [rbx+48h]
  ... truncated ...
```
