# AfdSanFastCompleteAccept

- ea: `0x14005b110`
- end: `0x14005b611`
- name: `AfdSanFastCompleteAccept`
- size: `1281`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x14000f450`
- `0x1400137a0`
- `0x140019190`
- `0x1400191f0`
- `0x14001b0d0`
- `0x14001b800`
- `0x14002fd5c`
- `0x14003f97c`
- `0x1400445b8`
- `0x14005b110`
- `0x14005d838`
- `0x1400726a0`
- `0x1400726d0`
- `0x140092110`
- `0x140093008`
- `0x1400931d0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14005b19e`
- `ntoskrnl!ExRaiseStatus` at `0x14005b215`
- `ntoskrnl!ExRaiseStatus` at `0x14005b284`
- `ntoskrnl!ExRaiseStatus` at `0x14005b2a3`
- `ntoskrnl!ExRaiseStatus` at `0x14005b19e`
- `ntoskrnl!ExRaiseStatus` at `0x14005b215`
- `ntoskrnl!ExRaiseStatus` at `0x14005b284`
- `ntoskrnl!ExRaiseStatus` at `0x14005b2a3`
- `ntoskrnl!ProbeForRead` at `0x14005b2e8`
- `ntoskrnl!ProbeForRead` at `0x14005b2e8`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005b1b4`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005b22b`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005b1b4`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005b22b`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005b4c8`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005b4c8`
- `ntoskrnl!IofCompleteRequest` at `0x14005b57b`
- `ntoskrnl!IofCompleteRequest` at `0x14005b57b`
- `ntoskrnl!ObfDereferenceObject` at `0x14005b58a`
- `ntoskrnl!ObfDereferenceObject` at `0x14005b5db`
- `ntoskrnl!ObfDereferenceObject` at `0x14005b58a`
- `ntoskrnl!ObfDereferenceObject` at `0x14005b5db`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005b4b8`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005b4b8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005b5a4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005b5bc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005b5a4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005b5bc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005b357`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005b357`
- `ntoskrnl!IoIs32bitProcess` at `0x14005b17a`
- `ntoskrnl!IoIs32bitProcess` at `0x14005b17a`
- `ntoskrnl!ProbeForWrite` at `0x14005b2c4`
- `ntoskrnl!ProbeForWrite` at `0x14005b2c4`
- `NETIO!RtlCopyBufferToMdlFromMode` at `0x14005b515`
- `NETIO!RtlCopyBufferToMdlFromMode` at `0x14005b515`

## pseudocode

```c
__int64 __fastcall AfdSanFastCompleteAccept(
        __int64 a1,
        unsigned __int16 a2,
        KPROCESSOR_MODE a3,
        void *a4,
        unsigned int a5,
        volatile void *a6,
        unsigned int Length,
        __int64 *a8)
{
  __int64 ULong64FromUser; // rax
  __int64 result; // rax
  PVOID v13; // r13
  __int64 v14; // rbx
  __int64 v15; // r12
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  _QWORD *v18; // rax
  _QWORD *v19; // rdi
  __int64 v20; // rcx
  char v21; // al
  struct _KLOCK_QUEUE_HANDLE *p_LockHandle; // rdx
  __int64 v23; // r8
  unsigned int v24; // esi
  __int64 v25; // r9
  __int64 v26; // rcx
  __int64 v27; // rax
  KIRQL Irql[4]; // [rsp+30h] [rbp-C8h] BYREF
  int v29; // [rsp+34h] [rbp-C4h]
  __int64 v30; // [rsp+38h] [rbp-C0h] BYREF
  volatile void *Address[2]; // [rsp+40h] [rbp-B8h] BYREF
  PVOID Object; // [rsp+50h] [rbp-A8h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+58h] [rbp-A0h] BYREF
  volatile void *v34; // [rsp+70h] [rbp-88h]
  __int64 *v35; // [rsp+78h] [rbp-80h]
  __int64 v36; // [rsp+80h] [rbp-78h]
  __int64 v37; // [rsp+88h] [rbp-70h]
  _QWORD *v38; // [rsp+90h] [rbp-68h]
  __int128 v39; // [rsp+98h] [rbp-60h] BYREF
  int v40; // [rsp+A8h] [rbp-50h]

  v34 = a6;
  v35 = a8;
  memset(&LockHandle, 0, sizeof(LockHandle));
  Object = 0;
  *(_OWORD *)Address = 0;
  *a8 = 0;
  v29 = 0;
  if ( IoIs32bitProcess(0) )
  {
    v30 = 0;
    if ( a5 < 8 )
      ExRaiseStatus(-1073741811);
    if ( a3 )
    {
      if ( ((unsigned __int8)a4 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      ULong64FromUser = RtlReadULong64FromUser(a4);
      v30 = ULong64FromUser;
    }
    else
    {
      RtlCopyVolatileMemory(&v30, a4, 8u);
      LODWORD(ULong64FromUser) = v30;
    }
    Address[0] = (volatile void *)(int)ULong64FromUser;
    Address[1] = (volatile void *)HIDWORD(v30);
  }
  else
  {
    if ( a5 < 0x10 )
      ExRaiseStatus(-1073741811);
    if ( a3 )
    {
      if ( ((unsigned __int8)a4 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyFromUser(Address, a4, 0x10u);
    }
    else
    {
      RtlCopyVolatileMemory(Address, a4, 0x10u);
    }
  }
  if ( !Address[1] )
  {
    if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
      WPP_SF_(1043, 30, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids);
    ExRaiseStatus(-1073741811);
  }
  if ( Length && !a6 )
    ExRaiseStatus(-1073741811);
  if ( a3 )
  {
    ProbeForWrite(Address[1], 0x14u, 4u);
    if ( Length )
      ProbeForRead(a6, Length, 1u);
  }
  result = AfdSanReferenceSwitchSocketByHandle((HANDLE)Address[0], a2 >> 14, a3, (__int64)Address[1], (__int64)&Object);
  if ( (int)result >= 0 )
  {
    v13 = Object;
    v14 = *((_QWORD *)Object + 3);
    v37 = v14;
    v15 = AfdLockEndpointContext(v14);
    v36 = v15;
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v14 + 56), &LockHandle);
    if ( (*(_DWORD *)(v14 + 8) & 0x800) == 0
      && (*(_BYTE *)(v14 + 2) == 1 || (*(_DWORD *)(v14 + 8) & 0x100) != 0 && *(_BYTE *)(v14 + 2) == 2) )
    {
      v16 = *(_QWORD **)(v14 + 128);
      if ( v16 == (_QWORD *)(v14 + 128) )
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        v24 = -1073741509;
      }
      else
      {
        v39 = 0;
        v40 = 0;
        v17 = *v16;
        if ( *(_QWORD **)(*v16 + 8LL) != v16 || (v18 = (_QWORD *)v16[1], (_QWORD *)*v18 != v16) )
          __fastfail(3u);
        v19 = v16 - 21;
        v38 = v16 - 21;
        *v18 = v17;
        *(_QWORD *)(v17 + 8) = v18;
        *v16 = 0;
        *(_DWORD *)(v14 + 152) = 4;
        *(_BYTE *)(v14 + 2) = 4;
        *(_BYTE *)(v14 + 32) = 1;
        *(_BYTE *)(v14 + 33) = 1;
        *(_DWORD *)(v14 + 8) |= 0x2000000u;
        *(_QWORD *)(v14 + 120) = &v39;
        _InterlockedExchange((volatile __int32 *)(v14 + 368), 0);
        AfdIndicateEventSelectEvent(v14, 4, 0);
        AfdNotifySockEventsChangedUnderLock(v14, 4, 0);
        v21 = AfdIndicatePollEvent(v20, 4, 0, &LockHandle);
        p_LockHandle = &LockHandle;
        if ( v21 )
          p_LockHandle = 0;
        AfdNotifySockIndicateEventsUnlock(v14, p_LockHandle, 0);
        LOBYTE(v23) = a3;
        v24 = AfdSanPollMerge(v14, &v39, v23);
        v29 = v24;
        *(_QWORD *)(v14 + 120) = 0;
        if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
          WPP_SF_qq(1043, 31, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v14, v19);
        if ( !_InterlockedExchange64(v19 + 13, 0) )
        {
          Irql[0] = 0;
          IoAcquireCancelSpinLock(Irql);
          IoReleaseCancelSpinLock(Irql[0]);
        }
        if ( Length && (v26 = v19[1]) != 0 )
        {
          v30 = 0;
          LOBYTE(v25) = a3;
          v29 = RtlCopyBufferToMdlFromMode(v26, v34, 0, v25, Length, &v30);
          if ( v29 >= 0 )
          {
            v27 = v30;
            *v35 = v30;
            v19[7] = v27;
          }
          v24 = v29;
        }
        else
        {
          v19[7] = 0;
        }
        *((_DWORD *)v19 + 12) = v24;
        IofCompleteRequest((PIRP)v19, AfdPriorityBoost);
        ObfDereferenceObject(v13);
      }
    }
    else
    {
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v24 = -1073741816;
    }
    AfdUnlockEndpointContext(v14, v15);
    ObfDereferenceObject(v13);
    return v24;
  }
  return result;
}

```

## disassembly

```asm
0x14005b110  push    rbx
0x14005b112  push    rsi
0x14005b113  push    rdi
0x14005b114  push    r12
0x14005b116  push    r13
0x14005b118  push    r14
0x14005b11a  sub     rsp, 0C8h
0x14005b121  mov     rax, cs:__security_cookie
0x14005b128  xor     rax, rsp
0x14005b12b  mov     [rsp+0F8h+var_48], rax
0x14005b133  mov     rbx, r9
0x14005b136  mov     r14b, r8b
0x14005b139  mov     edi, edx
0x14005b13b  mov     r13, rcx
0x14005b13e  mov     r12, [rsp+0F8h+arg_28]
0x14005b146  mov     [rsp+0F8h+var_88], r12
0x14005b14b  mov     rax, [rsp+0F8h+arg_38]
0x14005b153  mov     [rsp+0F8h+var_80], rax
0x14005b158  xorps   xmm0, xmm0
0x14005b15b  xor     ecx, ecx; Irp
0x14005b15d  movups  xmmword ptr [rsp+0F8h+LockHandle.LockQueue.Next], xmm0
0x14005b162  mov     qword ptr [rsp+0F8h+LockHandle.OldIrql], rcx
0x14005b167  xor     esi, esi
0x14005b169  mov     [rsp+0F8h+Object], rsi
0x14005b16e  movups  xmmword ptr [rsp+0F8h+Address], xmm0
0x14005b173  mov     [rax], rsi
0x14005b176  mov     [rsp+0F8h+var_C4], esi
0x14005b17a  call    cs:__imp_IoIs32bitProcess
0x14005b181  nop     dword ptr [rax+rax+00h]
0x14005b186  test    al, al
0x14005b188  jz      short loc_14005B200
0x14005b18a  mov     [rsp+0F8h+var_C0], rsi
0x14005b18f  cmp     [rsp+0F8h+arg_20], 8
0x14005b197  jnb     short loc_14005B1AA
0x14005b199  mov     ecx, 0C000000Dh; Status
0x14005b19e  call    cs:__imp_ExRaiseStatus
0x14005b1aa  test    r14b, r14b
0x14005b1ad  jz      short loc_14005B1D5
0x14005b1af  test    bl, 3
0x14005b1b2  jz      short loc_14005B1C1
0x14005b1b4  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005b1bb  nop     dword ptr [rax+rax+00h]
0x14005b1c0  int     3; Trap to Debugger
0x14005b1c1  test    r14b, r14b
0x14005b1c4  jz      short loc_14005B1D5
0x14005b1c6  mov     rcx, rbx
0x14005b1c9  call    RtlReadULong64FromUser
0x14005b1ce  mov     [rsp+0F8h+var_C0], rax
0x14005b1d3  jmp     short loc_14005B1ED
0x14005b1d5  mov     r8d, 8; Size
0x14005b1db  mov     rdx, rbx; Src
0x14005b1de  lea     rcx, [rsp+0F8h+var_C0]; void *
0x14005b1e3  call    RtlCopyVolatileMemory
0x14005b1e8  mov     rax, [rsp+0F8h+var_C0]
0x14005b1ed  movsxd  rcx, eax
0x14005b1f0  mov     [rsp+0F8h+Address], rcx
0x14005b1f5  mov     eax, dword ptr [rsp+0F8h+var_C0+4]
0x14005b1f9  mov     [rsp+0F8h+Address+8], rax
0x14005b1fe  jmp     short loc_14005B259
0x14005b200  mov     r8d, 10h; Size
0x14005b206  cmp     [rsp+0F8h+arg_20], r8d
0x14005b20e  jnb     short loc_14005B221
0x14005b210  mov     ecx, 0C000000Dh; Status
0x14005b215  call    cs:__imp_ExRaiseStatus
0x14005b221  test    r14b, r14b
0x14005b224  jz      short loc_14005B24C
0x14005b226  test    bl, 3
0x14005b229  jz      short loc_14005B238
0x14005b22b  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005b232  nop     dword ptr [rax+rax+00h]
0x14005b237  int     3; Trap to Debugger
0x14005b238  test    r14b, r14b
0x14005b23b  jz      short loc_14005B24C
0x14005b23d  mov     rdx, rbx; Src
0x14005b240  lea     rcx, [rsp+0F8h+Address]; void *
0x14005b245  call    RtlCopyFromUser
0x14005b24a  jmp     short loc_14005B259
0x14005b24c  mov     rdx, rbx; Src
0x14005b24f  lea     rcx, [rsp+0F8h+Address]; void *
0x14005b254  call    RtlCopyVolatileMemory
0x14005b259  cmp     [rsp+0F8h+Address+8], rsi
0x14005b25e  jnz     short loc_14005B290
0x14005b260  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005b267  jz      short loc_14005B27F
0x14005b269  mov     edx, 1Eh
0x14005b26e  mov     ecx, 413h
0x14005b273  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005b27a  call    WPP_SF_
0x14005b27f  mov     ecx, 0C000000Dh; Status
0x14005b284  call    cs:__imp_ExRaiseStatus
0x14005b290  cmp     dword ptr [rsp+0F8h+Length], esi
0x14005b297  jbe     short loc_14005B2AF
0x14005b299  test    r12, r12
0x14005b29c  jnz     short loc_14005B2AF
0x14005b29e  mov     ecx, 0C000000Dh; Status
0x14005b2a3  call    cs:__imp_ExRaiseStatus
0x14005b2af  mov     esi, 4
0x14005b2b4  test    r14b, r14b
0x14005b2b7  jz      short loc_14005B2F5
0x14005b2b9  mov     r8d, esi; Alignment
0x14005b2bc  lea     edx, [rsi+10h]; Length
0x14005b2bf  mov     rcx, [rsp+0F8h+Address+8]; Address
0x14005b2c4  call    cs:__imp_ProbeForWrite
0x14005b2cb  nop     dword ptr [rax+rax+00h]
0x14005b2d0  cmp     dword ptr [rsp+0F8h+Length], 0
0x14005b2d8  jbe     short loc_14005B2F5
0x14005b2da  mov     edx, dword ptr [rsp+0F8h+Length]; Length
0x14005b2e1  lea     r8d, [rsi-3]; Alignment
0x14005b2e5  mov     rcx, r12; Address
0x14005b2e8  call    cs:__imp_ProbeForRead
0x14005b2ef  nop     dword ptr [rax+rax+00h]
0x14005b2f4  nop
0x14005b2f5  shr     edi, 0Eh
0x14005b2f8  and     edi, 3
0x14005b2fb  lea     rax, [rsp+0F8h+Object]
0x14005b300  mov     [rsp+0F8h+var_D0], rax; __int64
0x14005b305  mov     rax, [rsp+0F8h+Address+8]
0x14005b30a  mov     [rsp+0F8h+var_D8], rax; __int64
0x14005b30f  mov     r9, [r13+18h]
0x14005b313  mov     r8b, r14b; AccessMode
0x14005b316  mov     edx, edi; DesiredAccess
0x14005b318  mov     rcx, [rsp+0F8h+Address]; Handle
0x14005b31d  call    AfdSanReferenceSwitchSocketByHandle
0x14005b322  test    eax, eax
0x14005b324  js      loc_14005B5EF
0x14005b32a  mov     r13, [rsp+0F8h+Object]
0x14005b32f  mov     rbx, [r13+18h]
0x14005b333  mov     [rsp+0F8h+var_70], rbx
0x14005b33b  mov     rcx, rbx
0x14005b33e  call    AfdLockEndpointContext
0x14005b343  mov     r12, rax
0x14005b346  mov     [rsp+0F8h+var_78], rax
0x14005b34e  lea     rcx, [rbx+38h]; SpinLock
0x14005b352  lea     rdx, [rsp+0F8h+LockHandle]; LockHandle
0x14005b357  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005b35e  nop     dword ptr [rax+rax+00h]
0x14005b363  test    dword ptr [rbx+8], 800h
0x14005b36a  jnz     loc_14005B5B7
0x14005b370  cmp     byte ptr [rbx+2], 1
0x14005b374  jz      short loc_14005B38D
0x14005b376  mov     eax, [rbx+8]
0x14005b379  bt      eax, 8
0x14005b37d  jnb     loc_14005B5B7
0x14005b383  cmp     byte ptr [rbx+2], 2
0x14005b387  jnz     loc_14005B5B7
0x14005b38d  lea     rax, [rbx+80h]
0x14005b394  mov     rcx, [rax]
0x14005b397  cmp     rcx, rax
0x14005b39a  jz      loc_14005B59F
0x14005b3a0  xorps   xmm0, xmm0
0x14005b3a3  movups  [rsp+0F8h+var_60], xmm0
0x14005b3ab  xor     eax, eax
0x14005b3ad  mov     [rsp+0F8h+var_50], eax
0x14005b3b4  mov     rdx, [rcx]
0x14005b3b7  cmp     [rdx+8], rcx
0x14005b3bb  jnz     loc_14005B598
0x14005b3c1  mov     rax, [rcx+8]
0x14005b3c5  cmp     [rax], rcx
0x14005b3c8  jnz     loc_14005B598
0x14005b3ce  lea     rdi, [rcx-0A8h]
0x14005b3d5  mov     [rsp+0F8h+var_68], rdi
0x14005b3dd  mov     [rax], rdx
0x14005b3e0  mov     [rdx+8], rax
0x14005b3e4  mov     qword ptr [rcx], 0
0x14005b3eb  mov     [rbx+98h], esi
0x14005b3f1  mov     [rbx+2], sil
0x14005b3f5  mov     byte ptr [rbx+20h], 1
0x14005b3f9  mov     byte ptr [rbx+21h], 1
0x14005b3fd  mov     eax, [rbx+8]
0x14005b400  bts     eax, 19h
0x14005b404  mov     [rbx+8], eax
0x14005b407  lea     rax, [rsp+0F8h+var_60]
0x14005b40f  mov     [rbx+78h], rax
0x14005b413  xor     eax, eax
0x14005b415  xchg    eax, [rbx+170h]
0x14005b41b  xor     r8d, r8d
0x14005b41e  mov     edx, esi
0x14005b420  mov     rcx, rbx
0x14005b423  call    AfdIndicateEventSelectEvent
0x14005b428  xor     r8d, r8d
0x14005b42b  mov     edx, esi
0x14005b42d  mov     rcx, rbx
0x14005b430  call    AfdNotifySockEventsChangedUnderLock
0x14005b435  lea     r9, [rsp+0F8h+LockHandle]
0x14005b43a  xor     r8d, r8d
0x14005b43d  mov     edx, esi
0x14005b43f  call    AfdIndicatePollEvent
0x14005b444  lea     rdx, [rsp+0F8h+LockHandle]
0x14005b449  xor     ecx, ecx
0x14005b44b  test    al, al
0x14005b44d  cmovnz  rdx, rcx
0x14005b451  xor     r8d, r8d
0x14005b454  mov     rcx, rbx
0x14005b457  call    AfdNotifySockIndicateEventsUnlock
0x14005b45c  mov     r8b, r14b
0x14005b45f  lea     rdx, [rsp+0F8h+var_60]
0x14005b467  mov     rcx, rbx
0x14005b46a  call    AfdSanPollMerge
0x14005b46f  mov     esi, eax
0x14005b471  mov     [rsp+0F8h+var_C4], eax
0x14005b475  mov     qword ptr [rbx+78h], 0
0x14005b47d  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005b484  jz      short loc_14005B4A4
0x14005b486  mov     edx, 1Fh
0x14005b48b  mov     ecx, 413h
0x14005b490  mov     [rsp+0F8h+var_D8], rdi
0x14005b495  mov     r9, rbx
0x14005b498  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005b49f  call    WPP_SF_qq
0x14005b4a4  xor     eax, eax
0x14005b4a6  xchg    rax, [rdi+68h]
0x14005b4aa  test    rax, rax
0x14005b4ad  jnz     short loc_14005B4D4
0x14005b4af  mov     [rsp+0F8h+Irql], al
0x14005b4b3  lea     rcx, [rsp+0F8h+Irql]; Irql
0x14005b4b8  call    cs:__imp_IoAcquireCancelSpinLock
0x14005b4bf  nop     dword ptr [rax+rax+00h]
0x14005b4c4  mov     cl, [rsp+0F8h+Irql]; Irql
0x14005b4c8  call    cs:__imp_IoReleaseCancelSpinLock
0x14005b4cf  nop     dword ptr [rax+rax+00h]
0x14005b4d4  cmp     dword ptr [rsp+0F8h+Length], 0
0x14005b4dc  jbe     loc_14005B567
0x14005b4e2  mov     rcx, [rdi+8]
0x14005b4e6  test    rcx, rcx
0x14005b4e9  jz      short loc_14005B567
0x14005b4eb  mov     [rsp+0F8h+var_C0], 0
0x14005b4f4  mov     eax, dword ptr [rsp+0F8h+Length]
0x14005b4fb  lea     rdx, [rsp+0F8h+var_C0]
0x14005b500  mov     [rsp+0F8h+var_D0], rdx
0x14005b505  mov     [rsp+0F8h+var_D8], rax
0x14005b50a  mov     r9b, r14b
0x14005b50d  xor     r8d, r8d
0x14005b510  mov     rdx, [rsp+0F8h+var_88]
0x14005b515  call    cs:__imp_RtlCopyBufferToMdlFromMode
0x14005b51c  nop     dword ptr [rax+rax+00h]
0x14005b521  mov     [rsp+0F8h+var_C4], eax
0x14005b525  mov     eax, [rsp+0F8h+var_C4]
0x14005b529  test    eax, eax
0x14005b52b  js      short loc_14005B53E
0x14005b52d  mov     rax, [rsp+0F8h+var_C0]
0x14005b532  mov     rcx, [rsp+0F8h+var_80]
0x14005b537  mov     [rcx], rax
0x14005b53a  mov     [rdi+38h], rax
0x14005b53e  mov     esi, [rsp+0F8h+var_C4]
0x14005b542  jmp     short loc_14005B56F
0x14005b544  mov     esi, [rsp+0F8h+var_C4]
0x14005b548  mov     r13, [rsp+0F8h+Object]
0x14005b54d  mov     r12, [rsp+0F8h+var_78]
0x14005b555  mov     rbx, [rsp+0F8h+var_70]
0x14005b55d  mov     rdi, [rsp+0F8h+var_68]
0x14005b565  jmp     short loc_14005B56F
0x14005b567  mov     qword ptr [rdi+38h], 0
0x14005b56f  mov     [rdi+30h], esi
0x14005b572  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14005b578  mov     rcx, rdi; Irp
0x14005b57b  call    cs:__imp_IofCompleteRequest
0x14005b582  nop     dword ptr [rax+rax+00h]
0x14005b587  mov     rcx, r13; Object
0x14005b58a  call    cs:__imp_ObfDereferenceObject
0x14005b591  nop     dword ptr [rax+rax+00h]
0x14005b596  jmp     short loc_14005B5CD
0x14005b598  mov     ecx, 3
0x14005b59d  int     29h; Win8: RtlFailFast(ecx)
0x14005b59f  lea     rcx, [rsp+0F8h+LockHandle]; LockHandle
0x14005b5a4  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005b5ab  nop     dword ptr [rax+rax+00h]
0x14005b5b0  mov     esi, 0C000013Bh
0x14005b5b5  jmp     short loc_14005B5CD
0x14005b5b7  lea     rcx, [rsp+0F8h+LockHandle]; LockHandle
0x14005b5bc  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005b5c3  nop     dword ptr [rax+rax+00h]
0x14005b5c8  mov     esi, 0C0000008h
0x14005b5cd  mov     rdx, r12
0x14005b5d0  mov     rcx, rbx
0x14005b5d3  call    AfdUnlockEndpointContext
0x14005b5d8  mov     rcx, r13; Object
0x14005b5db  call    cs:__imp_ObfDereferenceObject
0x14005b5e2  nop     dword ptr [rax+rax+00h]
0x14005b5e7  mov     eax, esi
0x14005b5e9  jmp     short loc_14005B5EF
0x14005b5eb  mov     eax, [rsp+0F8h+var_C4]
0x14005b5ef  mov     rcx, [rsp+0F8h+var_48]
0x14005b5f7  xor     rcx, rsp; StackCookie
0x14005b5fa  call    __security_check_cookie
0x14005b5ff  add     rsp, 0C8h
0x14005b606  pop     r14
0x14005b608  pop     r13
0x14005b60a  pop     r12
0x14005b60c  pop     rdi
0x14005b60d  pop     rsi
0x14005b60e  pop     rbx
0x14005b60f  retn
0x1400741de  push    rbp
0x1400741e0  sub     rsp, 30h
0x1400741e4  mov     rbp, rdx
0x1400741e7  mov     r8, rcx
0x1400741ea  lea     r9, [rbp+34h]
0x1400741ee  mov     edx, 705h
0x1400741f3  lea     rcx, aMinioSocketsWi_11; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x1400741fa  call    AfdExceptionFilter
  ... truncated ...
```
