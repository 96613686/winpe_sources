# AfdUnBindSocket

- ea: `0x140046be0`
- end: `0x1400475a2`
- name: `AfdUnBindSocket`
- size: `2498`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x14000d4b0`
- `0x14000dc90`
- `0x14002fd5c`
- `0x140032778`
- `0x140033bdc`
- `0x14003f254`
- `0x140046b14`
- `0x140046b80`
- `0x140046be0`
- `0x1400726d0`
- `0x140072780`
- `0x140072b00`
- `0x140092110`
- `0x1400931d0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140046e6f`
- `ntoskrnl!KeInitializeEvent` at `0x140047254`
- `ntoskrnl!KeInitializeEvent` at `0x140046e6f`
- `ntoskrnl!KeInitializeEvent` at `0x140047254`
- `ntoskrnl!KeWaitForSingleObject` at `0x140046f27`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004701a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400470b2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400471e7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004730a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400473b9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140046f27`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004701a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400470b2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400471e7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004730a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400473b9`
- `ntoskrnl!KeResetEvent` at `0x140046f7e`
- `ntoskrnl!KeResetEvent` at `0x140047062`
- `ntoskrnl!KeResetEvent` at `0x1400471a3`
- `ntoskrnl!KeResetEvent` at `0x140047371`
- `ntoskrnl!KeResetEvent` at `0x140046f7e`
- `ntoskrnl!KeResetEvent` at `0x140047062`
- `ntoskrnl!KeResetEvent` at `0x1400471a3`
- `ntoskrnl!KeResetEvent` at `0x140047371`
- `ntoskrnl!ZwClose` at `0x1400473fd`
- `ntoskrnl!ZwClose` at `0x140047493`
- `ntoskrnl!ZwClose` at `0x1400473fd`
- `ntoskrnl!ZwClose` at `0x140047493`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14004751c`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14004751c`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400474fb`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400474fb`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140046d23`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140046d23`
- `ntoskrnl!IofCompleteRequest` at `0x140046db8`
- `ntoskrnl!IofCompleteRequest` at `0x140046db8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400473ea`
- `ntoskrnl!ObfDereferenceObject` at `0x140047467`
- `ntoskrnl!ObfDereferenceObject` at `0x1400473ea`
- `ntoskrnl!ObfDereferenceObject` at `0x140047467`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140047192`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140047192`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004716d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004716d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004714a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400474d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047534`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004714a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400474d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047534`

## pseudocode

```c
__int64 __fastcall AfdUnBindSocket(PIRP Irp, __int64 a2)
{
  NTSTATUS v4; // r15d
  char v5; // di
  _WORD *v6; // rsi
  __int64 v7; // rdx
  KPROCESSOR_MODE RequestorMode; // cl
  __int64 ULong64FromUser; // rax
  __int64 v10; // rdx
  __int64 v12; // rcx
  int v13; // ebx
  unsigned int (__fastcall **v14)(PVOID, __int128 *); // rax
  PVOID v15; // rcx
  unsigned int (__fastcall **v16)(PVOID, __int128 *); // rdi
  __int64 v17; // rdi
  unsigned int (__fastcall **v18)(__int64, __int128 *); // rbx
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // r15
  unsigned int (__fastcall **v22)(__int64, __int128 *); // rbx
  void *v23; // rbx
  PVOID Object[4]; // [rsp+30h] [rbp-158h] BYREF
  int v25; // [rsp+50h] [rbp-138h]
  unsigned int (__fastcall **v26)(PVOID, __int128 *); // [rsp+58h] [rbp-130h]
  __int128 v27; // [rsp+60h] [rbp-128h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+70h] [rbp-118h] BYREF
  _QWORD v29[10]; // [rsp+90h] [rbp-F8h] BYREF
  struct _KEVENT Event; // [rsp+E0h] [rbp-A8h] BYREF
  _QWORD v31[17]; // [rsp+100h] [rbp-88h] BYREF
  __int64 v32; // [rsp+1A0h] [rbp+18h] BYREF
  PVOID v33; // [rsp+1A8h] [rbp+20h]

  v4 = 0;
  v25 = 0;
  v5 = 0;
  v32 = 0;
  v6 = *(_WORD **)(*(_QWORD *)(a2 + 48) + 24LL);
  v33 = v6;
  if ( *(_DWORD *)(a2 + 16) < 8u )
  {
    if ( (xmmword_1400875E0 & 0x40) == 0 )
    {
LABEL_5:
      v4 = -1073741811;
      goto LABEL_34;
    }
    v7 = 28;
LABEL_4:
    WPP_SF_(1030, v7, WPP_654a54d5d1a93919ecbd46fb90bee823_Traceguids);
    goto LABEL_5;
  }
  if ( !*(_QWORD *)(a2 + 32) )
  {
    if ( (xmmword_1400875E0 & 0x40) == 0 )
      goto LABEL_5;
    v7 = 29;
    goto LABEL_4;
  }
  if ( ((*((_BYTE *)v6 + 5) & 0x10) == 0 || (v6[3] & 1) == 0) && *v6 != 6909 && *v6 != 0xAFD1 )
  {
    if ( _InterlockedCompareExchange((volatile signed __int32 *)v6 + 92, 3, 0) )
    {
      if ( (xmmword_1400875E0 & 0x40) == 0 )
        goto LABEL_5;
      v7 = 31;
      goto LABEL_4;
    }
    if ( !(unsigned __int8)AfdPreventUnbind(v6) )
    {
      if ( (xmmword_1400875E0 & 0x40) != 0 )
        WPP_SF_(1030, 32, WPP_654a54d5d1a93919ecbd46fb90bee823_Traceguids);
      v4 = -1073741436;
      _InterlockedExchange((volatile __int32 *)v6 + 92, 0);
      goto LABEL_34;
    }
    if ( *((_BYTE *)v6 + 2) != 3 || (*((_DWORD *)v6 + 2) & 1) != 0 )
    {
      v4 = -1073741811;
      goto LABEL_33;
    }
    RequestorMode = Irp->RequestorMode;
    if ( RequestorMode && (*(_BYTE *)(a2 + 32) & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    if ( RequestorMode )
    {
      ULong64FromUser = RtlReadULong64FromUser(*(_QWORD *)(a2 + 32));
      v32 = ULong64FromUser;
    }
    else
    {
      RtlCopyVolatileMemory(&v32, *(const void **)(a2 + 32), 8u);
      LODWORD(ULong64FromUser) = v32;
    }
    if ( (_DWORD)ULong64FromUser != 2 && (_DWORD)ULong64FromUser != 23 )
    {
      if ( (xmmword_1400875E0 & 0x40) == 0 )
      {
LABEL_33:
        v5 = 1;
        goto LABEL_34;
      }
      v10 = 33;
LABEL_32:
      WPP_SF_(1030, v10, WPP_654a54d5d1a93919ecbd46fb90bee823_Traceguids);
      goto LABEL_33;
    }
    if ( (*((_DWORD *)v6 + 2) & 0x100) != 0 )
    {
      memset(Object, 0, sizeof(Object));
      memset(v29, 0, sizeof(v29));
      memset(&Event, 0, sizeof(Event));
      if ( (unsigned __int8)AfdRefTLBaseEndpoint(v6) )
      {
        Object[0] = &Event;
        KeInitializeEvent(&Event, NotificationEvent, 0);
        v29[0] = AfdSynchronousTlCreateRequestComplete;
        v29[1] = Object;
        LOWORD(v29[3]) = v32;
        v12 = *((_QWORD *)v6 + 34);
        WORD1(v29[3]) = *(_WORD *)(v12 + 28);
        WORD2(v29[3]) = WORD2(v32);
        v29[5] = *((_QWORD *)v6 + 6);
        v29[6] = KeGetCurrentThread();
        v29[7] = 0;
        v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)(v12 + 40) + 16LL))(*(_QWORD *)(v12 + 32), v29);
        if ( v4 == 259 )
        {
          KeWaitForSingleObject(Object[0], Executive, 0, 0, 0);
          v4 = (NTSTATUS)Object[1];
        }
        v13 = v4;
        v14 = (unsigned int (__fastcall **)(PVOID, __int128 *))Object[3];
        v26 = (unsigned int (__fastcall **)(PVOID, __int128 *))Object[3];
        v15 = Object[2];
        v33 = Object[2];
        if ( v4 >= 0 )
        {
          if ( (*((_DWORD *)v6 + 2) & 0x100000) != 0 )
          {
            memset(v31, 0, 0x50u);
            KeResetEvent((PRKEVENT)Object[0]);
            v31[0] = AfdSynchronousTlIORequestComplete;
            v31[1] = Object;
            v31[2] = 0x2900000001LL;
            LODWORD(v31[3]) = 27;
            v31[4] = &AfdTLSockOptDisable;
            v31[5] = 4;
            v16 = v26;
            v4 = v26[1](v33, (__int128 *)v31);
            if ( v4 == 259 )
            {
              KeWaitForSingleObject(Object[0], Executive, 0, 0, 0);
              v4 = (NTSTATUS)Object[1];
            }
            v13 = v4;
            if ( v4 >= 0 )
            {
              v14 = v16;
              v15 = v33;
            }
            else
            {
              v27 = 0;
              if ( (xmmword_1400875E0 & 0x40) != 0 )
                WPP_SF_(1030, 35, WPP_654a54d5d1a93919ecbd46fb90bee823_Traceguids);
              KeResetEvent((PRKEVENT)Object[0]);
              *(_QWORD *)&v27 = AfdSynchronousTlCloseRequestComplete;
              *((_QWORD *)&v27 + 1) = Object;
              if ( (*v16)(v33, &v27) == 259 )
                KeWaitForSingleObject(Object[0], Executive, 0, 0, 0);
              v14 = v16;
              v15 = v33;
            }
          }
          else
          {
            v14 = v26;
          }
        }
        if ( v13 >= 0 )
        {
          v27 = 0;
          memset(&LockHandle, 0, sizeof(LockHandle));
          v17 = *((_QWORD *)v6 + 2);
          v18 = (unsigned int (__fastcall **)(__int64, __int128 *))*((_QWORD *)v6 + 3);
          *((_QWORD *)v6 + 2) = v15;
          *((_QWORD *)v6 + 3) = v14;
          *((_BYTE *)v6 + 2) = 2;
          ExFreePoolWithTag(*((PVOID *)v6 + 30), 0x6C646641u);
          *((_QWORD *)v6 + 30) = 0;
          *((_DWORD *)v6 + 59) = 0;
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v6 + 7, &LockHandle);
          *((_DWORD *)v6 + 2) &= ~0x80000000;
          *((_DWORD *)v6 + 2) &= ~0x40000000u;
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          KeResetEvent((PRKEVENT)Object[0]);
          *(_QWORD *)&v27 = AfdSynchronousTlCloseRequestComplete;
          *((_QWORD *)&v27 + 1) = Object;
          if ( (*v18)(v17, &v27) == 259 )
            KeWaitForSingleObject(Object[0], Executive, 0, 0, 0);
        }
        else if ( (xmmword_1400875E0 & 0x40) != 0 )
        {
          WPP_SF_(1030, 36, WPP_654a54d5d1a93919ecbd46fb90bee823_Traceguids);
        }
        AfdDerefTLBaseEndpoint(v6);
      }
      else
      {
        if ( (xmmword_1400875E0 & 0x40) != 0 )
          WPP_SF_(1030, 34, WPP_654a54d5d1a93919ecbd46fb90bee823_Traceguids);
        v4 = -1073741816;
      }
      goto LABEL_33;
    }
    if ( (*((_DWORD *)v6 + 2) & 0x200) != 0 )
    {
      memset(&Object[1], 0, 24);
      memset(v29, 0, sizeof(v29));
      memset(&LockHandle, 0, sizeof(LockHandle));
      Object[0] = &LockHandle;
      KeInitializeEvent((PRKEVENT)&LockHandle, NotificationEvent, 0);
      v29[0] = AfdSynchronousTlCreateRequestComplete;
      v29[1] = Object;
      LOWORD(v29[3]) = v32;
      v19 = *((_QWORD *)v6 + 64);
      WORD1(v29[3]) = *(_WORD *)(v19 + 28);
      WORD2(v29[3]) = WORD2(v32);
      v29[5] = *((_QWORD *)v6 + 6);
      v29[6] = KeGetCurrentThread();
      v29[7] = 0;
      v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)(v19 + 40) + 16LL))(*(_QWORD *)(v19 + 32), v29);
      v4 = v20;
      if ( v20 == 259 )
      {
        KeWaitForSingleObject(Object[0], Executive, 0, 0, 0);
        v4 = (NTSTATUS)Object[1];
        v20 = (int)Object[1];
      }
      if ( v20 < 0 )
      {
        if ( (xmmword_1400875E0 & 0x40) == 0 )
          goto LABEL_33;
        v10 = 37;
        goto LABEL_32;
      }
      v27 = 0;
      v21 = *((_QWORD *)v6 + 62);
      v22 = (unsigned int (__fastcall **)(__int64, __int128 *))*((_QWORD *)v6 + 63);
      *((_OWORD *)v6 + 31) = *(_OWORD *)&Object[2];
      if ( v22 )
      {
        KeResetEvent((PRKEVENT)Object[0]);
        *(_QWORD *)&v27 = AfdSynchronousTlCloseRequestComplete;
        *((_QWORD *)&v27 + 1) = Object;
        if ( (*v22)(v21, &v27) == 259 )
          KeWaitForSingleObject(Object[0], Executive, 0, 0, 0);
      }
      else if ( (xmmword_1400875E0 & 0x40) != 0 )
      {
        WPP_SF_(1030, 38, WPP_654a54d5d1a93919ecbd46fb90bee823_Traceguids);
      }
    }
    ObfDereferenceObject(*((PVOID *)v6 + 3));
    ZwClose(*((HANDLE *)v6 + 32));
    *((_QWORD *)v6 + 3) = 0;
    *((_QWORD *)v6 + 5) = 0;
    *((_QWORD *)v6 + 32) = 0;
    if ( (*((_DWORD *)v6 + 2) & 0x200000) != 0 )
    {
      AfdDereferenceTransport(*((_QWORD *)v6 + 34));
      *((_QWORD *)v6 + 34) = *((_QWORD *)v6 + 35);
      *((_QWORD *)v6 + 35) = 0;
      AfdTdiSetInet4Mapped(v6);
    }
    else if ( (*((_DWORD *)v6 + 2) & 0x400000) != 0 )
    {
      ObfDereferenceObject(*(PVOID *)(*((_QWORD *)v6 + 35) + 8LL));
      *(_QWORD *)(*((_QWORD *)v6 + 35) + 8LL) = 0;
      *(_QWORD *)(*((_QWORD *)v6 + 35) + 16LL) = 0;
      ZwClose(**((HANDLE **)v6 + 35));
      **((_QWORD **)v6 + 35) = 0;
      AfdDereferenceTransport(*(_QWORD *)(*((_QWORD *)v6 + 35) + 24LL));
      *(_QWORD *)(*((_QWORD *)v6 + 35) + 24LL) = 0;
      ExFreePoolWithTag(*((PVOID *)v6 + 35), 0x56646641u);
      *((_QWORD *)v6 + 35) = 0;
      AfdTdiSetDualInet(v6, 0);
    }
    v23 = (void *)*((_QWORD *)v6 + 30);
    ExEnterCriticalRegionAndAcquireResourceExclusive(AfdGlobalData);
    *((_QWORD *)v6 + 30) = 0;
    *((_DWORD *)v6 + 59) = 0;
    ExReleaseResourceAndLeaveCriticalRegion(AfdGlobalData);
    *((_BYTE *)v6 + 2) = 1;
    ExFreePoolWithTag(v23, 0x6C646641u);
    v4 = 0;
    goto LABEL_33;
  }
  if ( (xmmword_1400875E0 & 0x40) != 0 )
    WPP_SF_(1030, 30, WPP_654a54d5d1a93919ecbd46fb90bee823_Traceguids);
  v4 = -1073741637;
LABEL_34:
  if ( v5 == 1 )
  {
    AfdReallowUnbind(v6);
    _InterlockedExchange((volatile __int32 *)v6 + 92, 0);
  }
  Irp->IoStatus.Status = v4;
  IofCompleteRequest(Irp, AfdPriorityBoost);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140046be0  mov     rax, rsp
0x140046be3  mov     [rax+8], rcx
0x140046be7  push    rbx
0x140046be8  push    rsi
0x140046be9  push    rdi
0x140046bea  push    r12
0x140046bec  push    r13
0x140046bee  push    r14
0x140046bf0  push    r15
0x140046bf2  sub     rsp, 150h
0x140046bf9  mov     rbx, rdx
0x140046bfc  mov     r13, rcx
0x140046bff  xor     r14d, r14d
0x140046c02  mov     r15d, r14d
0x140046c05  mov     [rsp+188h+var_138], r14d
0x140046c0a  mov     dil, r14b
0x140046c0d  mov     [rax+18h], r14
0x140046c11  mov     rax, [rdx+30h]
0x140046c15  mov     rsi, [rax+18h]
0x140046c19  mov     [rsp+188h+arg_18], rsi
0x140046c21  cmp     dword ptr [rdx+10h], 8
0x140046c25  jnb     short loc_140046C50
0x140046c27  test    byte ptr cs:xmmword_1400875E0, 40h
0x140046c2e  jz      short loc_140046C45
0x140046c30  lea     edx, [r14+1Ch]
0x140046c34  mov     ecx, 406h
0x140046c39  lea     r8, WPP_654a54d5d1a93919ecbd46fb90bee823_Traceguids
0x140046c40  call    WPP_SF_
0x140046c45  mov     r15d, 0C000000Dh
0x140046c4b  jmp     loc_140046D96
0x140046c50  cmp     [rdx+20h], r14
0x140046c54  jnz     short loc_140046C66
0x140046c56  test    byte ptr cs:xmmword_1400875E0, 40h
0x140046c5d  jz      short loc_140046C45
0x140046c5f  mov     edx, 1Dh
0x140046c64  jmp     short loc_140046C34
0x140046c66  test    byte ptr [rsi+5], 10h
0x140046c6a  jz      short loc_140046C76
0x140046c6c  test    byte ptr [rsi+6], 1
0x140046c70  jnz     loc_140047578
0x140046c76  movzx   eax, word ptr [rsi]
0x140046c79  mov     ecx, 1AFDh
0x140046c7e  cmp     ax, cx
0x140046c81  jz      loc_140047578
0x140046c87  mov     ecx, 0AFD1h
0x140046c8c  cmp     ax, cx
0x140046c8f  jz      loc_140047578
0x140046c95  xor     eax, eax
0x140046c97  lea     r12d, [rax+3]
0x140046c9b  lock cmpxchg [rsi+170h], r12d
0x140046ca4  jz      short loc_140046CB9
0x140046ca6  test    byte ptr cs:xmmword_1400875E0, 40h
0x140046cad  jz      short loc_140046C45
0x140046caf  lea     edx, [r12+1Ch]
0x140046cb4  jmp     loc_140046C34
0x140046cb9  mov     rcx, rsi
0x140046cbc  call    AfdPreventUnbind
0x140046cc1  test    al, al
0x140046cc3  jnz     short loc_140046CF8
0x140046cc5  test    byte ptr cs:xmmword_1400875E0, 40h
0x140046ccc  jz      short loc_140046CE4
0x140046cce  mov     edx, 20h ; ' '
0x140046cd3  mov     ecx, 406h
0x140046cd8  lea     r8, WPP_654a54d5d1a93919ecbd46fb90bee823_Traceguids
0x140046cdf  call    WPP_SF_
0x140046ce4  mov     r15d, 0C0000184h
0x140046cea  mov     eax, r14d
0x140046ced  xchg    eax, [rsi+170h]
0x140046cf3  jmp     loc_140046D96
0x140046cf8  mov     [rsp+188h+arg_8], 1
0x140046d00  cmp     [rsi+2], r12b
0x140046d04  jnz     loc_14004756D
0x140046d0a  mov     eax, [rsi+8]
0x140046d0d  test    al, 1
0x140046d0f  jnz     loc_14004756D
0x140046d15  mov     cl, [r13+40h]
0x140046d19  test    cl, cl
0x140046d1b  jz      short loc_140046D30
0x140046d1d  test    [rbx+20h], r12b
0x140046d21  jz      short loc_140046D30
0x140046d23  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140046d2a  nop     dword ptr [rax+rax+00h]
0x140046d2f  int     3; Trap to Debugger
0x140046d30  mov     rdx, [rbx+20h]; Src
0x140046d34  test    cl, cl
0x140046d36  jz      short loc_140046D4A
0x140046d38  mov     rcx, rdx
0x140046d3b  call    RtlReadULong64FromUser
0x140046d40  mov     [rsp+188h+arg_10], rax
0x140046d48  jmp     short loc_140046D65
0x140046d4a  mov     r8d, 8; Size
0x140046d50  lea     rcx, [rsp+188h+arg_10]; void *
0x140046d58  call    RtlCopyVolatileMemory
0x140046d5d  mov     rax, [rsp+188h+arg_10]
0x140046d65  cmp     eax, 2
0x140046d68  jz      short loc_140046DDB
0x140046d6a  cmp     eax, 17h
0x140046d6d  jz      short loc_140046DDB
0x140046d6f  test    byte ptr cs:xmmword_1400875E0, 40h
0x140046d76  jz      short loc_140046D8E
0x140046d78  mov     edx, 21h ; '!'
0x140046d7d  mov     ecx, 406h
0x140046d82  lea     r8, WPP_654a54d5d1a93919ecbd46fb90bee823_Traceguids
0x140046d89  call    WPP_SF_
0x140046d8e  mov     dil, [rsp+188h+arg_8]
0x140046d96  cmp     dil, 1
0x140046d9a  jnz     short loc_140046DAB
0x140046d9c  mov     rcx, rsi
0x140046d9f  call    AfdReallowUnbind
0x140046da4  xchg    r14d, [rsi+170h]
0x140046dab  mov     [r13+30h], r15d
0x140046daf  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140046db5  mov     rcx, r13; Irp
0x140046db8  call    cs:__imp_IofCompleteRequest
0x140046dbf  nop     dword ptr [rax+rax+00h]
0x140046dc4  mov     eax, r15d
0x140046dc7  add     rsp, 150h
0x140046dce  pop     r15
0x140046dd0  pop     r14
0x140046dd2  pop     r13
0x140046dd4  pop     r12
0x140046dd6  pop     rdi
0x140046dd7  pop     rsi
0x140046dd8  pop     rbx
0x140046dd9  retn
0x140046ddb  mov     eax, [rsi+8]
0x140046dde  bt      eax, 8
0x140046de2  jnb     loc_140047200
0x140046de8  xorps   xmm0, xmm0
0x140046deb  movups  xmmword ptr [rsp+188h+Object], xmm0
0x140046df0  movups  [rsp+188h+var_148], xmm0
0x140046df5  mov     edi, 50h ; 'P'
0x140046dfa  mov     r8d, edi; Size
0x140046dfd  xor     edx, edx; Val
0x140046dff  lea     rcx, [rsp+188h+var_F8]; void *
0x140046e07  call    memset
0x140046e0c  xorps   xmm0, xmm0
0x140046e0f  xor     eax, eax
0x140046e11  movups  xmmword ptr [rsp+188h+Event.Header], xmm0
0x140046e19  mov     [rsp+188h+Event.Header.WaitListHead.Blink], rax
0x140046e21  mov     rcx, rsi
0x140046e24  call    AfdRefTLBaseEndpoint
0x140046e29  test    al, al
0x140046e2b  jnz     short loc_140046E55
0x140046e2d  test    byte ptr cs:xmmword_1400875E0, 40h
0x140046e34  jz      short loc_140046E4A
0x140046e36  lea     edx, [rdi-2Eh]
0x140046e39  mov     ecx, 406h
0x140046e3e  lea     r8, WPP_654a54d5d1a93919ecbd46fb90bee823_Traceguids
0x140046e45  call    WPP_SF_
0x140046e4a  mov     r15d, 0C0000008h
0x140046e50  jmp     loc_140046D8E
0x140046e55  lea     rax, [rsp+188h+Event]
0x140046e5d  mov     [rsp+188h+Object], rax
0x140046e62  xor     r8d, r8d; State
0x140046e65  xor     edx, edx; Type
0x140046e67  lea     rcx, [rsp+188h+Event]; Event
0x140046e6f  call    cs:__imp_KeInitializeEvent
0x140046e76  nop     dword ptr [rax+rax+00h]
0x140046e7b  lea     rax, AfdSynchronousTlCreateRequestComplete
0x140046e82  mov     [rsp+188h+var_F8], rax
0x140046e8a  lea     rax, [rsp+188h+Object]
0x140046e8f  mov     [rsp+188h+var_F0], rax
0x140046e97  mov     rax, [rsp+188h+arg_10]
0x140046e9f  mov     [rsp+188h+var_E0], ax
0x140046ea7  mov     rcx, [rsi+110h]
0x140046eae  movzx   eax, word ptr [rcx+1Ch]
0x140046eb2  mov     [rsp+188h+var_DE], ax
0x140046eba  mov     eax, dword ptr [rsp+188h+arg_10+4]
0x140046ec1  mov     [rsp+188h+var_DC], ax
0x140046ec9  mov     rax, [rsi+30h]
0x140046ecd  mov     [rsp+188h+var_D0], rax
0x140046ed5  mov     rax, gs:188h
0x140046ede  mov     [rsp+188h+var_C8], rax
0x140046ee6  mov     [rsp+188h+var_C0], r14
0x140046eee  mov     rax, [rcx+28h]
0x140046ef2  mov     rax, [rax+10h]
0x140046ef6  lea     rdx, [rsp+188h+var_F8]
0x140046efe  mov     rcx, [rcx+20h]
0x140046f02  call    _guard_dispatch_icall
0x140046f07  mov     r15d, eax
0x140046f0a  mov     r12d, 103h
0x140046f10  cmp     eax, r12d
0x140046f13  jnz     short loc_140046F38
0x140046f15  mov     [rsp+188h+Timeout], r14; Timeout
0x140046f1a  xor     r9d, r9d; Alertable
0x140046f1d  xor     r8d, r8d; WaitMode
0x140046f20  xor     edx, edx; WaitReason
0x140046f22  mov     rcx, [rsp+188h+Object]; Object
0x140046f27  call    cs:__imp_KeWaitForSingleObject
0x140046f2e  nop     dword ptr [rax+rax+00h]
0x140046f33  mov     r15d, dword ptr [rsp+188h+Object+8]
0x140046f38  mov     ebx, r15d
0x140046f3b  mov     rax, qword ptr [rsp+188h+var_148+8]
0x140046f40  mov     [rsp+188h+var_130], rax
0x140046f45  mov     rcx, qword ptr [rsp+188h+var_148]
0x140046f4a  mov     [rsp+188h+arg_18], rcx
0x140046f52  test    ebx, ebx
0x140046f54  js      loc_1400470DD
0x140046f5a  mov     eax, [rsi+8]
0x140046f5d  bt      eax, 14h
0x140046f61  jnb     loc_1400470D8
0x140046f67  mov     r8, rdi; Size
0x140046f6a  xor     edx, edx; Val
0x140046f6c  lea     rcx, [rsp+188h+var_88]; void *
0x140046f74  call    memset
0x140046f79  mov     rcx, [rsp+188h+Object]; Event
0x140046f7e  call    cs:__imp_KeResetEvent
0x140046f85  nop     dword ptr [rax+rax+00h]
0x140046f8a  lea     rax, AfdSynchronousTlIORequestComplete
0x140046f91  mov     [rsp+188h+var_88], rax
0x140046f99  lea     rax, [rsp+188h+Object]
0x140046f9e  mov     [rsp+188h+var_80], rax
0x140046fa6  mov     [rsp+188h+var_78], 1
0x140046fb1  mov     [rsp+188h+var_74], 29h ; ')'
0x140046fbc  mov     [rsp+188h+var_70], 1Bh
0x140046fc7  lea     rax, AfdTLSockOptDisable
0x140046fce  mov     [rsp+188h+var_68], rax
0x140046fd6  mov     [rsp+188h+var_60], 4
0x140046fe2  mov     rdi, [rsp+188h+var_130]
0x140046fe7  mov     rax, [rdi+8]
0x140046feb  lea     rdx, [rsp+188h+var_88]
0x140046ff3  mov     rcx, [rsp+188h+arg_18]
0x140046ffb  call    _guard_dispatch_icall
0x140047000  mov     r15d, eax
0x140047003  cmp     eax, r12d
0x140047006  jnz     short loc_14004702B
0x140047008  mov     [rsp+188h+Timeout], r14; Timeout
0x14004700d  xor     r9d, r9d; Alertable
0x140047010  xor     r8d, r8d; WaitMode
0x140047013  xor     edx, edx; WaitReason
0x140047015  mov     rcx, [rsp+188h+Object]; Object
0x14004701a  call    cs:__imp_KeWaitForSingleObject
0x140047021  nop     dword ptr [rax+rax+00h]
0x140047026  mov     r15d, dword ptr [rsp+188h+Object+8]
0x14004702b  mov     ebx, r15d
0x14004702e  test    ebx, ebx
0x140047030  jns     loc_1400470CB
0x140047036  xorps   xmm0, xmm0
0x140047039  movups  [rsp+188h+var_128], xmm0
0x14004703e  test    byte ptr cs:xmmword_1400875E0, 40h
0x140047045  jz      short loc_14004705D
0x140047047  mov     edx, 23h ; '#'
0x14004704c  mov     ecx, 406h
0x140047051  lea     r8, WPP_654a54d5d1a93919ecbd46fb90bee823_Traceguids
0x140047058  call    WPP_SF_
0x14004705d  mov     rcx, [rsp+188h+Object]; Event
0x140047062  call    cs:__imp_KeResetEvent
0x140047069  nop     dword ptr [rax+rax+00h]
0x14004706e  lea     r12, AfdSynchronousTlCloseRequestComplete
0x140047075  mov     qword ptr [rsp+188h+var_128], r12
0x14004707a  lea     rax, [rsp+188h+Object]
0x14004707f  mov     qword ptr [rsp+188h+var_128+8], rax
0x140047084  mov     rax, [rdi]
0x140047087  lea     rdx, [rsp+188h+var_128]
0x14004708c  mov     rcx, [rsp+188h+arg_18]
0x140047094  call    _guard_dispatch_icall
0x140047099  cmp     eax, 103h
0x14004709e  jnz     short loc_1400470BE
0x1400470a0  mov     [rsp+188h+Timeout], r14; Timeout
0x1400470a5  xor     r9d, r9d; Alertable
0x1400470a8  xor     r8d, r8d; WaitMode
0x1400470ab  xor     edx, edx; WaitReason
0x1400470ad  mov     rcx, [rsp+188h+Object]; Object
0x1400470b2  call    cs:__imp_KeWaitForSingleObject
0x1400470b9  nop     dword ptr [rax+rax+00h]
0x1400470be  mov     rax, rdi
0x1400470c1  mov     rcx, [rsp+188h+arg_18]
0x1400470c9  jmp     short loc_1400470E4
0x1400470cb  mov     rax, rdi
0x1400470ce  mov     rcx, [rsp+188h+arg_18]
0x1400470d6  jmp     short loc_1400470DD
0x1400470d8  mov     rax, [rsp+188h+var_130]
0x1400470dd  lea     r12, AfdSynchronousTlCloseRequestComplete
0x1400470e4  test    ebx, ebx
0x1400470e6  jns     short loc_140047110
0x1400470e8  test    byte ptr cs:xmmword_1400875E0, 40h
0x1400470ef  jz      loc_1400471F3
0x1400470f5  mov     edx, 24h ; '$'
0x1400470fa  mov     ecx, 406h
0x1400470ff  lea     r8, WPP_654a54d5d1a93919ecbd46fb90bee823_Traceguids
0x140047106  call    WPP_SF_
0x14004710b  jmp     loc_1400471F3
0x140047110  xorps   xmm0, xmm0
0x140047113  movups  [rsp+188h+var_128], xmm0
0x140047118  xorps   xmm1, xmm1
0x14004711b  xor     edx, edx
0x14004711d  movups  xmmword ptr [rsp+188h+LockHandle.LockQueue.Next], xmm1
0x140047122  mov     qword ptr [rsp+188h+LockHandle.OldIrql], rdx
0x14004712a  mov     rdi, [rsi+10h]
0x14004712e  mov     rbx, [rsi+18h]
0x140047132  mov     [rsi+10h], rcx
0x140047136  mov     [rsi+18h], rax
0x14004713a  mov     byte ptr [rsi+2], 2
0x14004713e  mov     edx, 6C646641h; Tag
0x140047143  mov     rcx, [rsi+0F0h]; P
0x14004714a  call    cs:__imp_ExFreePoolWithTag
0x140047151  nop     dword ptr [rax+rax+00h]
0x140047156  mov     [rsi+0F0h], r14
0x14004715d  mov     [rsi+0ECh], r14d
  ... truncated ...
```
