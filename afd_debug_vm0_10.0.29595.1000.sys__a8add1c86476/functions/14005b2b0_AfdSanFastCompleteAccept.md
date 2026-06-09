# AfdSanFastCompleteAccept

- ea: `0x14005b2b0`
- end: `0x14005b7b1`
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
- `0x14002fd7c`
- `0x14003f99c`
- `0x1400445d8`
- `0x14005b2b0`
- `0x14005d9d8`
- `0x140072840`
- `0x140072870`
- `0x140092110`
- `0x140093008`
- `0x1400931d0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14005b33e`
- `ntoskrnl!ExRaiseStatus` at `0x14005b3b5`
- `ntoskrnl!ExRaiseStatus` at `0x14005b424`
- `ntoskrnl!ExRaiseStatus` at `0x14005b443`
- `ntoskrnl!ExRaiseStatus` at `0x14005b33e`
- `ntoskrnl!ExRaiseStatus` at `0x14005b3b5`
- `ntoskrnl!ExRaiseStatus` at `0x14005b424`
- `ntoskrnl!ExRaiseStatus` at `0x14005b443`
- `ntoskrnl!ProbeForRead` at `0x14005b488`
- `ntoskrnl!ProbeForRead` at `0x14005b488`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005b354`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005b3cb`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005b354`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005b3cb`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005b668`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005b668`
- `ntoskrnl!IofCompleteRequest` at `0x14005b71b`
- `ntoskrnl!IofCompleteRequest` at `0x14005b71b`
- `ntoskrnl!ObfDereferenceObject` at `0x14005b72a`
- `ntoskrnl!ObfDereferenceObject` at `0x14005b77b`
- `ntoskrnl!ObfDereferenceObject` at `0x14005b72a`
- `ntoskrnl!ObfDereferenceObject` at `0x14005b77b`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005b658`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005b658`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005b744`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005b75c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005b744`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005b75c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005b4f7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005b4f7`
- `ntoskrnl!IoIs32bitProcess` at `0x14005b31a`
- `ntoskrnl!IoIs32bitProcess` at `0x14005b31a`
- `ntoskrnl!ProbeForWrite` at `0x14005b464`
- `ntoskrnl!ProbeForWrite` at `0x14005b464`
- `NETIO!RtlCopyBufferToMdlFromMode` at `0x14005b6b5`
- `NETIO!RtlCopyBufferToMdlFromMode` at `0x14005b6b5`

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
0x14005b2b0  push    rbx
0x14005b2b2  push    rsi
0x14005b2b3  push    rdi
0x14005b2b4  push    r12
0x14005b2b6  push    r13
0x14005b2b8  push    r14
0x14005b2ba  sub     rsp, 0C8h
0x14005b2c1  mov     rax, cs:__security_cookie
0x14005b2c8  xor     rax, rsp
0x14005b2cb  mov     [rsp+0F8h+var_48], rax
0x14005b2d3  mov     rbx, r9
0x14005b2d6  mov     r14b, r8b
0x14005b2d9  mov     edi, edx
0x14005b2db  mov     r13, rcx
0x14005b2de  mov     r12, [rsp+0F8h+arg_28]
0x14005b2e6  mov     [rsp+0F8h+var_88], r12
0x14005b2eb  mov     rax, [rsp+0F8h+arg_38]
0x14005b2f3  mov     [rsp+0F8h+var_80], rax
0x14005b2f8  xorps   xmm0, xmm0
0x14005b2fb  xor     ecx, ecx; Irp
0x14005b2fd  movups  xmmword ptr [rsp+0F8h+LockHandle.LockQueue.Next], xmm0
0x14005b302  mov     qword ptr [rsp+0F8h+LockHandle.OldIrql], rcx
0x14005b307  xor     esi, esi
0x14005b309  mov     [rsp+0F8h+Object], rsi
0x14005b30e  movups  xmmword ptr [rsp+0F8h+Address], xmm0
0x14005b313  mov     [rax], rsi
0x14005b316  mov     [rsp+0F8h+var_C4], esi
0x14005b31a  call    cs:__imp_IoIs32bitProcess
0x14005b321  nop     dword ptr [rax+rax+00h]
0x14005b326  test    al, al
0x14005b328  jz      short loc_14005B3A0
0x14005b32a  mov     [rsp+0F8h+var_C0], rsi
0x14005b32f  cmp     [rsp+0F8h+arg_20], 8
0x14005b337  jnb     short loc_14005B34A
0x14005b339  mov     ecx, 0C000000Dh; Status
0x14005b33e  call    cs:__imp_ExRaiseStatus
0x14005b34a  test    r14b, r14b
0x14005b34d  jz      short loc_14005B375
0x14005b34f  test    bl, 3
0x14005b352  jz      short loc_14005B361
0x14005b354  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005b35b  nop     dword ptr [rax+rax+00h]
0x14005b360  int     3; Trap to Debugger
0x14005b361  test    r14b, r14b
0x14005b364  jz      short loc_14005B375
0x14005b366  mov     rcx, rbx
0x14005b369  call    RtlReadULong64FromUser
0x14005b36e  mov     [rsp+0F8h+var_C0], rax
0x14005b373  jmp     short loc_14005B38D
0x14005b375  mov     r8d, 8; Size
0x14005b37b  mov     rdx, rbx; Src
0x14005b37e  lea     rcx, [rsp+0F8h+var_C0]; void *
0x14005b383  call    RtlCopyVolatileMemory
0x14005b388  mov     rax, [rsp+0F8h+var_C0]
0x14005b38d  movsxd  rcx, eax
0x14005b390  mov     [rsp+0F8h+Address], rcx
0x14005b395  mov     eax, dword ptr [rsp+0F8h+var_C0+4]
0x14005b399  mov     [rsp+0F8h+Address+8], rax
0x14005b39e  jmp     short loc_14005B3F9
0x14005b3a0  mov     r8d, 10h; Size
0x14005b3a6  cmp     [rsp+0F8h+arg_20], r8d
0x14005b3ae  jnb     short loc_14005B3C1
0x14005b3b0  mov     ecx, 0C000000Dh; Status
0x14005b3b5  call    cs:__imp_ExRaiseStatus
0x14005b3c1  test    r14b, r14b
0x14005b3c4  jz      short loc_14005B3EC
0x14005b3c6  test    bl, 3
0x14005b3c9  jz      short loc_14005B3D8
0x14005b3cb  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005b3d2  nop     dword ptr [rax+rax+00h]
0x14005b3d7  int     3; Trap to Debugger
0x14005b3d8  test    r14b, r14b
0x14005b3db  jz      short loc_14005B3EC
0x14005b3dd  mov     rdx, rbx; Src
0x14005b3e0  lea     rcx, [rsp+0F8h+Address]; void *
0x14005b3e5  call    RtlCopyFromUser
0x14005b3ea  jmp     short loc_14005B3F9
0x14005b3ec  mov     rdx, rbx; Src
0x14005b3ef  lea     rcx, [rsp+0F8h+Address]; void *
0x14005b3f4  call    RtlCopyVolatileMemory
0x14005b3f9  cmp     [rsp+0F8h+Address+8], rsi
0x14005b3fe  jnz     short loc_14005B430
0x14005b400  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005b407  jz      short loc_14005B41F
0x14005b409  mov     edx, 1Eh
0x14005b40e  mov     ecx, 413h
0x14005b413  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005b41a  call    WPP_SF_
0x14005b41f  mov     ecx, 0C000000Dh; Status
0x14005b424  call    cs:__imp_ExRaiseStatus
0x14005b430  cmp     dword ptr [rsp+0F8h+Length], esi
0x14005b437  jbe     short loc_14005B44F
0x14005b439  test    r12, r12
0x14005b43c  jnz     short loc_14005B44F
0x14005b43e  mov     ecx, 0C000000Dh; Status
0x14005b443  call    cs:__imp_ExRaiseStatus
0x14005b44f  mov     esi, 4
0x14005b454  test    r14b, r14b
0x14005b457  jz      short loc_14005B495
0x14005b459  mov     r8d, esi; Alignment
0x14005b45c  lea     edx, [rsi+10h]; Length
0x14005b45f  mov     rcx, [rsp+0F8h+Address+8]; Address
0x14005b464  call    cs:__imp_ProbeForWrite
0x14005b46b  nop     dword ptr [rax+rax+00h]
0x14005b470  cmp     dword ptr [rsp+0F8h+Length], 0
0x14005b478  jbe     short loc_14005B495
0x14005b47a  mov     edx, dword ptr [rsp+0F8h+Length]; Length
0x14005b481  lea     r8d, [rsi-3]; Alignment
0x14005b485  mov     rcx, r12; Address
0x14005b488  call    cs:__imp_ProbeForRead
0x14005b48f  nop     dword ptr [rax+rax+00h]
0x14005b494  nop
0x14005b495  shr     edi, 0Eh
0x14005b498  and     edi, 3
0x14005b49b  lea     rax, [rsp+0F8h+Object]
0x14005b4a0  mov     [rsp+0F8h+var_D0], rax; __int64
0x14005b4a5  mov     rax, [rsp+0F8h+Address+8]
0x14005b4aa  mov     [rsp+0F8h+var_D8], rax; __int64
0x14005b4af  mov     r9, [r13+18h]
0x14005b4b3  mov     r8b, r14b; AccessMode
0x14005b4b6  mov     edx, edi; DesiredAccess
0x14005b4b8  mov     rcx, [rsp+0F8h+Address]; Handle
0x14005b4bd  call    AfdSanReferenceSwitchSocketByHandle
0x14005b4c2  test    eax, eax
0x14005b4c4  js      loc_14005B78F
0x14005b4ca  mov     r13, [rsp+0F8h+Object]
0x14005b4cf  mov     rbx, [r13+18h]
0x14005b4d3  mov     [rsp+0F8h+var_70], rbx
0x14005b4db  mov     rcx, rbx
0x14005b4de  call    AfdLockEndpointContext
0x14005b4e3  mov     r12, rax
0x14005b4e6  mov     [rsp+0F8h+var_78], rax
0x14005b4ee  lea     rcx, [rbx+38h]; SpinLock
0x14005b4f2  lea     rdx, [rsp+0F8h+LockHandle]; LockHandle
0x14005b4f7  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005b4fe  nop     dword ptr [rax+rax+00h]
0x14005b503  test    dword ptr [rbx+8], 800h
0x14005b50a  jnz     loc_14005B757
0x14005b510  cmp     byte ptr [rbx+2], 1
0x14005b514  jz      short loc_14005B52D
0x14005b516  mov     eax, [rbx+8]
0x14005b519  bt      eax, 8
0x14005b51d  jnb     loc_14005B757
0x14005b523  cmp     byte ptr [rbx+2], 2
0x14005b527  jnz     loc_14005B757
0x14005b52d  lea     rax, [rbx+80h]
0x14005b534  mov     rcx, [rax]
0x14005b537  cmp     rcx, rax
0x14005b53a  jz      loc_14005B73F
0x14005b540  xorps   xmm0, xmm0
0x14005b543  movups  [rsp+0F8h+var_60], xmm0
0x14005b54b  xor     eax, eax
0x14005b54d  mov     [rsp+0F8h+var_50], eax
0x14005b554  mov     rdx, [rcx]
0x14005b557  cmp     [rdx+8], rcx
0x14005b55b  jnz     loc_14005B738
0x14005b561  mov     rax, [rcx+8]
0x14005b565  cmp     [rax], rcx
0x14005b568  jnz     loc_14005B738
0x14005b56e  lea     rdi, [rcx-0A8h]
0x14005b575  mov     [rsp+0F8h+var_68], rdi
0x14005b57d  mov     [rax], rdx
0x14005b580  mov     [rdx+8], rax
0x14005b584  mov     qword ptr [rcx], 0
0x14005b58b  mov     [rbx+98h], esi
0x14005b591  mov     [rbx+2], sil
0x14005b595  mov     byte ptr [rbx+20h], 1
0x14005b599  mov     byte ptr [rbx+21h], 1
0x14005b59d  mov     eax, [rbx+8]
0x14005b5a0  bts     eax, 19h
0x14005b5a4  mov     [rbx+8], eax
0x14005b5a7  lea     rax, [rsp+0F8h+var_60]
0x14005b5af  mov     [rbx+78h], rax
0x14005b5b3  xor     eax, eax
0x14005b5b5  xchg    eax, [rbx+170h]
0x14005b5bb  xor     r8d, r8d
0x14005b5be  mov     edx, esi
0x14005b5c0  mov     rcx, rbx
0x14005b5c3  call    AfdIndicateEventSelectEvent
0x14005b5c8  xor     r8d, r8d
0x14005b5cb  mov     edx, esi
0x14005b5cd  mov     rcx, rbx
0x14005b5d0  call    AfdNotifySockEventsChangedUnderLock
0x14005b5d5  lea     r9, [rsp+0F8h+LockHandle]
0x14005b5da  xor     r8d, r8d
0x14005b5dd  mov     edx, esi
0x14005b5df  call    AfdIndicatePollEvent
0x14005b5e4  lea     rdx, [rsp+0F8h+LockHandle]
0x14005b5e9  xor     ecx, ecx
0x14005b5eb  test    al, al
0x14005b5ed  cmovnz  rdx, rcx
0x14005b5f1  xor     r8d, r8d
0x14005b5f4  mov     rcx, rbx
0x14005b5f7  call    AfdNotifySockIndicateEventsUnlock
0x14005b5fc  mov     r8b, r14b
0x14005b5ff  lea     rdx, [rsp+0F8h+var_60]
0x14005b607  mov     rcx, rbx
0x14005b60a  call    AfdSanPollMerge
0x14005b60f  mov     esi, eax
0x14005b611  mov     [rsp+0F8h+var_C4], eax
0x14005b615  mov     qword ptr [rbx+78h], 0
0x14005b61d  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005b624  jz      short loc_14005B644
0x14005b626  mov     edx, 1Fh
0x14005b62b  mov     ecx, 413h
0x14005b630  mov     [rsp+0F8h+var_D8], rdi
0x14005b635  mov     r9, rbx
0x14005b638  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005b63f  call    WPP_SF_qq
0x14005b644  xor     eax, eax
0x14005b646  xchg    rax, [rdi+68h]
0x14005b64a  test    rax, rax
0x14005b64d  jnz     short loc_14005B674
0x14005b64f  mov     [rsp+0F8h+Irql], al
0x14005b653  lea     rcx, [rsp+0F8h+Irql]; Irql
0x14005b658  call    cs:__imp_IoAcquireCancelSpinLock
0x14005b65f  nop     dword ptr [rax+rax+00h]
0x14005b664  mov     cl, [rsp+0F8h+Irql]; Irql
0x14005b668  call    cs:__imp_IoReleaseCancelSpinLock
0x14005b66f  nop     dword ptr [rax+rax+00h]
0x14005b674  cmp     dword ptr [rsp+0F8h+Length], 0
0x14005b67c  jbe     loc_14005B707
0x14005b682  mov     rcx, [rdi+8]
0x14005b686  test    rcx, rcx
0x14005b689  jz      short loc_14005B707
0x14005b68b  mov     [rsp+0F8h+var_C0], 0
0x14005b694  mov     eax, dword ptr [rsp+0F8h+Length]
0x14005b69b  lea     rdx, [rsp+0F8h+var_C0]
0x14005b6a0  mov     [rsp+0F8h+var_D0], rdx
0x14005b6a5  mov     [rsp+0F8h+var_D8], rax
0x14005b6aa  mov     r9b, r14b
0x14005b6ad  xor     r8d, r8d
0x14005b6b0  mov     rdx, [rsp+0F8h+var_88]
0x14005b6b5  call    cs:__imp_RtlCopyBufferToMdlFromMode
0x14005b6bc  nop     dword ptr [rax+rax+00h]
0x14005b6c1  mov     [rsp+0F8h+var_C4], eax
0x14005b6c5  mov     eax, [rsp+0F8h+var_C4]
0x14005b6c9  test    eax, eax
0x14005b6cb  js      short loc_14005B6DE
0x14005b6cd  mov     rax, [rsp+0F8h+var_C0]
0x14005b6d2  mov     rcx, [rsp+0F8h+var_80]
0x14005b6d7  mov     [rcx], rax
0x14005b6da  mov     [rdi+38h], rax
0x14005b6de  mov     esi, [rsp+0F8h+var_C4]
0x14005b6e2  jmp     short loc_14005B70F
0x14005b6e4  mov     esi, [rsp+0F8h+var_C4]
0x14005b6e8  mov     r13, [rsp+0F8h+Object]
0x14005b6ed  mov     r12, [rsp+0F8h+var_78]
0x14005b6f5  mov     rbx, [rsp+0F8h+var_70]
0x14005b6fd  mov     rdi, [rsp+0F8h+var_68]
0x14005b705  jmp     short loc_14005B70F
0x14005b707  mov     qword ptr [rdi+38h], 0
0x14005b70f  mov     [rdi+30h], esi
0x14005b712  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14005b718  mov     rcx, rdi; Irp
0x14005b71b  call    cs:__imp_IofCompleteRequest
0x14005b722  nop     dword ptr [rax+rax+00h]
0x14005b727  mov     rcx, r13; Object
0x14005b72a  call    cs:__imp_ObfDereferenceObject
0x14005b731  nop     dword ptr [rax+rax+00h]
0x14005b736  jmp     short loc_14005B76D
0x14005b738  mov     ecx, 3
0x14005b73d  int     29h; Win8: RtlFailFast(ecx)
0x14005b73f  lea     rcx, [rsp+0F8h+LockHandle]; LockHandle
0x14005b744  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005b74b  nop     dword ptr [rax+rax+00h]
0x14005b750  mov     esi, 0C000013Bh
0x14005b755  jmp     short loc_14005B76D
0x14005b757  lea     rcx, [rsp+0F8h+LockHandle]; LockHandle
0x14005b75c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005b763  nop     dword ptr [rax+rax+00h]
0x14005b768  mov     esi, 0C0000008h
0x14005b76d  mov     rdx, r12
0x14005b770  mov     rcx, rbx
0x14005b773  call    AfdUnlockEndpointContext
0x14005b778  mov     rcx, r13; Object
0x14005b77b  call    cs:__imp_ObfDereferenceObject
0x14005b782  nop     dword ptr [rax+rax+00h]
0x14005b787  mov     eax, esi
0x14005b789  jmp     short loc_14005B78F
0x14005b78b  mov     eax, [rsp+0F8h+var_C4]
0x14005b78f  mov     rcx, [rsp+0F8h+var_48]
0x14005b797  xor     rcx, rsp; StackCookie
0x14005b79a  call    __security_check_cookie
0x14005b79f  add     rsp, 0C8h
0x14005b7a6  pop     r14
0x14005b7a8  pop     r13
0x14005b7aa  pop     r12
0x14005b7ac  pop     rdi
0x14005b7ad  pop     rsi
0x14005b7ae  pop     rbx
0x14005b7af  retn
0x14007435e  push    rbp
0x140074360  sub     rsp, 30h
0x140074364  mov     rbp, rdx
0x140074367  mov     r8, rcx
0x14007436a  lea     r9, [rbp+34h]
0x14007436e  mov     edx, 705h
0x140074373  lea     rcx, aMinioSocketsWi_11; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x14007437a  call    AfdExceptionFilter
  ... truncated ...
```
