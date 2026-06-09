# AfdUnBindSocket

- ea: `0x140046c60`
- end: `0x140047621`
- name: `AfdUnBindSocket`
- size: `2497`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x14000d4b0`
- `0x14000dc90`
- `0x14002fd7c`
- `0x140032798`
- `0x140033bfc`
- `0x14003f274`
- `0x140046b94`
- `0x140046c00`
- `0x140046c60`
- `0x140072870`
- `0x140072920`
- `0x140072c80`
- `0x140092110`
- `0x1400931d0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140046eee`
- `ntoskrnl!KeInitializeEvent` at `0x1400472d3`
- `ntoskrnl!KeInitializeEvent` at `0x140046eee`
- `ntoskrnl!KeInitializeEvent` at `0x1400472d3`
- `ntoskrnl!KeWaitForSingleObject` at `0x140046fa6`
- `ntoskrnl!KeWaitForSingleObject` at `0x140047099`
- `ntoskrnl!KeWaitForSingleObject` at `0x140047131`
- `ntoskrnl!KeWaitForSingleObject` at `0x140047266`
- `ntoskrnl!KeWaitForSingleObject` at `0x140047389`
- `ntoskrnl!KeWaitForSingleObject` at `0x140047438`
- `ntoskrnl!KeWaitForSingleObject` at `0x140046fa6`
- `ntoskrnl!KeWaitForSingleObject` at `0x140047099`
- `ntoskrnl!KeWaitForSingleObject` at `0x140047131`
- `ntoskrnl!KeWaitForSingleObject` at `0x140047266`
- `ntoskrnl!KeWaitForSingleObject` at `0x140047389`
- `ntoskrnl!KeWaitForSingleObject` at `0x140047438`
- `ntoskrnl!KeResetEvent` at `0x140046ffd`
- `ntoskrnl!KeResetEvent` at `0x1400470e1`
- `ntoskrnl!KeResetEvent` at `0x140047222`
- `ntoskrnl!KeResetEvent` at `0x1400473f0`
- `ntoskrnl!KeResetEvent` at `0x140046ffd`
- `ntoskrnl!KeResetEvent` at `0x1400470e1`
- `ntoskrnl!KeResetEvent` at `0x140047222`
- `ntoskrnl!KeResetEvent` at `0x1400473f0`
- `ntoskrnl!ZwClose` at `0x14004747c`
- `ntoskrnl!ZwClose` at `0x140047512`
- `ntoskrnl!ZwClose` at `0x14004747c`
- `ntoskrnl!ZwClose` at `0x140047512`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14004759b`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14004759b`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14004757a`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14004757a`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140046da3`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140046da3`
- `ntoskrnl!IofCompleteRequest` at `0x140046e37`
- `ntoskrnl!IofCompleteRequest` at `0x140046e37`
- `ntoskrnl!ObfDereferenceObject` at `0x140047469`
- `ntoskrnl!ObfDereferenceObject` at `0x1400474e6`
- `ntoskrnl!ObfDereferenceObject` at `0x140047469`
- `ntoskrnl!ObfDereferenceObject` at `0x1400474e6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140047211`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140047211`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400471ec`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400471ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400471c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004754f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400475b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400471c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004754f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400475b3`

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
    WPP_SF_(1030, v7, WPP_43911188515d396c99d3028411eb93bd_Traceguids);
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
        WPP_SF_(1030, 32, WPP_43911188515d396c99d3028411eb93bd_Traceguids);
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
      WPP_SF_(1030, v10, WPP_43911188515d396c99d3028411eb93bd_Traceguids);
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
                WPP_SF_(1030, 35, WPP_43911188515d396c99d3028411eb93bd_Traceguids);
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
          WPP_SF_(1030, 36, WPP_43911188515d396c99d3028411eb93bd_Traceguids);
        }
        AfdDerefTLBaseEndpoint(v6);
      }
      else
      {
        if ( (xmmword_1400875E0 & 0x40) != 0 )
          WPP_SF_(1030, 34, WPP_43911188515d396c99d3028411eb93bd_Traceguids);
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
        WPP_SF_(1030, 38, WPP_43911188515d396c99d3028411eb93bd_Traceguids);
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
    WPP_SF_(1030, 30, WPP_43911188515d396c99d3028411eb93bd_Traceguids);
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
0x140046c60  mov     rax, rsp
0x140046c63  mov     [rax+8], rcx
0x140046c67  push    rbx
0x140046c68  push    rsi
0x140046c69  push    rdi
0x140046c6a  push    r12
0x140046c6c  push    r13
0x140046c6e  push    r14
0x140046c70  push    r15
0x140046c72  sub     rsp, 150h
0x140046c79  mov     rbx, rdx
0x140046c7c  mov     r13, rcx
0x140046c7f  xor     r14d, r14d
0x140046c82  mov     r15d, r14d
0x140046c85  mov     [rsp+188h+var_138], r14d
0x140046c8a  mov     dil, r14b
0x140046c8d  mov     [rax+18h], r14
0x140046c91  mov     rax, [rdx+30h]
0x140046c95  mov     rsi, [rax+18h]
0x140046c99  mov     [rsp+188h+arg_18], rsi
0x140046ca1  cmp     dword ptr [rdx+10h], 8
0x140046ca5  jnb     short loc_140046CD0
0x140046ca7  test    byte ptr cs:xmmword_1400875E0, 40h
0x140046cae  jz      short loc_140046CC5
0x140046cb0  lea     edx, [r14+1Ch]
0x140046cb4  mov     ecx, 406h
0x140046cb9  lea     r8, WPP_43911188515d396c99d3028411eb93bd_Traceguids
0x140046cc0  call    WPP_SF_
0x140046cc5  mov     r15d, 0C000000Dh
0x140046ccb  jmp     loc_140046E15
0x140046cd0  cmp     [rdx+20h], r14
0x140046cd4  jnz     short loc_140046CE6
0x140046cd6  test    byte ptr cs:xmmword_1400875E0, 40h
0x140046cdd  jz      short loc_140046CC5
0x140046cdf  mov     edx, 1Dh
0x140046ce4  jmp     short loc_140046CB4
0x140046ce6  test    byte ptr [rsi+5], 10h
0x140046cea  jz      short loc_140046CF6
0x140046cec  test    byte ptr [rsi+6], 1
0x140046cf0  jnz     loc_1400475F7
0x140046cf6  movzx   eax, word ptr [rsi]
0x140046cf9  mov     ecx, 1AFDh
0x140046cfe  cmp     ax, cx
0x140046d01  jz      loc_1400475F7
0x140046d07  mov     ecx, 0AFD1h
0x140046d0c  cmp     ax, cx
0x140046d0f  jz      loc_1400475F7
0x140046d15  xor     eax, eax
0x140046d17  lea     r12d, [rax+3]
0x140046d1b  lock cmpxchg [rsi+170h], r12d
0x140046d24  jz      short loc_140046D39
0x140046d26  test    byte ptr cs:xmmword_1400875E0, 40h
0x140046d2d  jz      short loc_140046CC5
0x140046d2f  lea     edx, [r12+1Ch]
0x140046d34  jmp     loc_140046CB4
0x140046d39  mov     rcx, rsi
0x140046d3c  call    AfdPreventUnbind
0x140046d41  test    al, al
0x140046d43  jnz     short loc_140046D78
0x140046d45  test    byte ptr cs:xmmword_1400875E0, 40h
0x140046d4c  jz      short loc_140046D64
0x140046d4e  mov     edx, 20h ; ' '
0x140046d53  mov     ecx, 406h
0x140046d58  lea     r8, WPP_43911188515d396c99d3028411eb93bd_Traceguids
0x140046d5f  call    WPP_SF_
0x140046d64  mov     r15d, 0C0000184h
0x140046d6a  mov     eax, r14d
0x140046d6d  xchg    eax, [rsi+170h]
0x140046d73  jmp     loc_140046E15
0x140046d78  mov     [rsp+188h+arg_8], 1
0x140046d80  cmp     [rsi+2], r12b
0x140046d84  jnz     loc_1400475EC
0x140046d8a  mov     eax, [rsi+8]
0x140046d8d  test    al, 1
0x140046d8f  jnz     loc_1400475EC
0x140046d95  mov     cl, [r13+40h]
0x140046d99  test    cl, cl
0x140046d9b  jz      short loc_140046DAF
0x140046d9d  test    [rbx+20h], r12b
0x140046da1  jz      short loc_140046DAF
0x140046da3  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140046daa  nop     dword ptr [rax+rax+00h]
0x140046daf  mov     rdx, [rbx+20h]; Src
0x140046db3  test    cl, cl
0x140046db5  jz      short loc_140046DC9
0x140046db7  mov     rcx, rdx
0x140046dba  call    RtlReadULong64FromUser
0x140046dbf  mov     [rsp+188h+arg_10], rax
0x140046dc7  jmp     short loc_140046DE4
0x140046dc9  mov     r8d, 8; Size
0x140046dcf  lea     rcx, [rsp+188h+arg_10]; void *
0x140046dd7  call    RtlCopyVolatileMemory
0x140046ddc  mov     rax, [rsp+188h+arg_10]
0x140046de4  cmp     eax, 2
0x140046de7  jz      short loc_140046E5A
0x140046de9  cmp     eax, 17h
0x140046dec  jz      short loc_140046E5A
0x140046dee  test    byte ptr cs:xmmword_1400875E0, 40h
0x140046df5  jz      short loc_140046E0D
0x140046df7  mov     edx, 21h ; '!'
0x140046dfc  mov     ecx, 406h
0x140046e01  lea     r8, WPP_43911188515d396c99d3028411eb93bd_Traceguids
0x140046e08  call    WPP_SF_
0x140046e0d  mov     dil, [rsp+188h+arg_8]
0x140046e15  cmp     dil, 1
0x140046e19  jnz     short loc_140046E2A
0x140046e1b  mov     rcx, rsi
0x140046e1e  call    AfdReallowUnbind
0x140046e23  xchg    r14d, [rsi+170h]
0x140046e2a  mov     [r13+30h], r15d
0x140046e2e  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140046e34  mov     rcx, r13; Irp
0x140046e37  call    cs:__imp_IofCompleteRequest
0x140046e3e  nop     dword ptr [rax+rax+00h]
0x140046e43  mov     eax, r15d
0x140046e46  add     rsp, 150h
0x140046e4d  pop     r15
0x140046e4f  pop     r14
0x140046e51  pop     r13
0x140046e53  pop     r12
0x140046e55  pop     rdi
0x140046e56  pop     rsi
0x140046e57  pop     rbx
0x140046e58  retn
0x140046e5a  mov     eax, [rsi+8]
0x140046e5d  bt      eax, 8
0x140046e61  jnb     loc_14004727F
0x140046e67  xorps   xmm0, xmm0
0x140046e6a  movups  xmmword ptr [rsp+188h+Object], xmm0
0x140046e6f  movups  [rsp+188h+var_148], xmm0
0x140046e74  mov     edi, 50h ; 'P'
0x140046e79  mov     r8d, edi; Size
0x140046e7c  xor     edx, edx; Val
0x140046e7e  lea     rcx, [rsp+188h+var_F8]; void *
0x140046e86  call    memset
0x140046e8b  xorps   xmm0, xmm0
0x140046e8e  xor     eax, eax
0x140046e90  movups  xmmword ptr [rsp+188h+Event.Header], xmm0
0x140046e98  mov     [rsp+188h+Event.Header.WaitListHead.Blink], rax
0x140046ea0  mov     rcx, rsi
0x140046ea3  call    AfdRefTLBaseEndpoint
0x140046ea8  test    al, al
0x140046eaa  jnz     short loc_140046ED4
0x140046eac  test    byte ptr cs:xmmword_1400875E0, 40h
0x140046eb3  jz      short loc_140046EC9
0x140046eb5  lea     edx, [rdi-2Eh]
0x140046eb8  mov     ecx, 406h
0x140046ebd  lea     r8, WPP_43911188515d396c99d3028411eb93bd_Traceguids
0x140046ec4  call    WPP_SF_
0x140046ec9  mov     r15d, 0C0000008h
0x140046ecf  jmp     loc_140046E0D
0x140046ed4  lea     rax, [rsp+188h+Event]
0x140046edc  mov     [rsp+188h+Object], rax
0x140046ee1  xor     r8d, r8d; State
0x140046ee4  xor     edx, edx; Type
0x140046ee6  lea     rcx, [rsp+188h+Event]; Event
0x140046eee  call    cs:__imp_KeInitializeEvent
0x140046ef5  nop     dword ptr [rax+rax+00h]
0x140046efa  lea     rax, AfdSynchronousTlCreateRequestComplete
0x140046f01  mov     [rsp+188h+var_F8], rax
0x140046f09  lea     rax, [rsp+188h+Object]
0x140046f0e  mov     [rsp+188h+var_F0], rax
0x140046f16  mov     rax, [rsp+188h+arg_10]
0x140046f1e  mov     [rsp+188h+var_E0], ax
0x140046f26  mov     rcx, [rsi+110h]
0x140046f2d  movzx   eax, word ptr [rcx+1Ch]
0x140046f31  mov     [rsp+188h+var_DE], ax
0x140046f39  mov     eax, dword ptr [rsp+188h+arg_10+4]
0x140046f40  mov     [rsp+188h+var_DC], ax
0x140046f48  mov     rax, [rsi+30h]
0x140046f4c  mov     [rsp+188h+var_D0], rax
0x140046f54  mov     rax, gs:188h
0x140046f5d  mov     [rsp+188h+var_C8], rax
0x140046f65  mov     [rsp+188h+var_C0], r14
0x140046f6d  mov     rax, [rcx+28h]
0x140046f71  mov     rax, [rax+10h]
0x140046f75  lea     rdx, [rsp+188h+var_F8]
0x140046f7d  mov     rcx, [rcx+20h]
0x140046f81  call    _guard_dispatch_icall
0x140046f86  mov     r15d, eax
0x140046f89  mov     r12d, 103h
0x140046f8f  cmp     eax, r12d
0x140046f92  jnz     short loc_140046FB7
0x140046f94  mov     [rsp+188h+Timeout], r14; Timeout
0x140046f99  xor     r9d, r9d; Alertable
0x140046f9c  xor     r8d, r8d; WaitMode
0x140046f9f  xor     edx, edx; WaitReason
0x140046fa1  mov     rcx, [rsp+188h+Object]; Object
0x140046fa6  call    cs:__imp_KeWaitForSingleObject
0x140046fad  nop     dword ptr [rax+rax+00h]
0x140046fb2  mov     r15d, dword ptr [rsp+188h+Object+8]
0x140046fb7  mov     ebx, r15d
0x140046fba  mov     rax, qword ptr [rsp+188h+var_148+8]
0x140046fbf  mov     [rsp+188h+var_130], rax
0x140046fc4  mov     rcx, qword ptr [rsp+188h+var_148]
0x140046fc9  mov     [rsp+188h+arg_18], rcx
0x140046fd1  test    ebx, ebx
0x140046fd3  js      loc_14004715C
0x140046fd9  mov     eax, [rsi+8]
0x140046fdc  bt      eax, 14h
0x140046fe0  jnb     loc_140047157
0x140046fe6  mov     r8, rdi; Size
0x140046fe9  xor     edx, edx; Val
0x140046feb  lea     rcx, [rsp+188h+var_88]; void *
0x140046ff3  call    memset
0x140046ff8  mov     rcx, [rsp+188h+Object]; Event
0x140046ffd  call    cs:__imp_KeResetEvent
0x140047004  nop     dword ptr [rax+rax+00h]
0x140047009  lea     rax, AfdSynchronousTlIORequestComplete
0x140047010  mov     [rsp+188h+var_88], rax
0x140047018  lea     rax, [rsp+188h+Object]
0x14004701d  mov     [rsp+188h+var_80], rax
0x140047025  mov     [rsp+188h+var_78], 1
0x140047030  mov     [rsp+188h+var_74], 29h ; ')'
0x14004703b  mov     [rsp+188h+var_70], 1Bh
0x140047046  lea     rax, AfdTLSockOptDisable
0x14004704d  mov     [rsp+188h+var_68], rax
0x140047055  mov     [rsp+188h+var_60], 4
0x140047061  mov     rdi, [rsp+188h+var_130]
0x140047066  mov     rax, [rdi+8]
0x14004706a  lea     rdx, [rsp+188h+var_88]
0x140047072  mov     rcx, [rsp+188h+arg_18]
0x14004707a  call    _guard_dispatch_icall
0x14004707f  mov     r15d, eax
0x140047082  cmp     eax, r12d
0x140047085  jnz     short loc_1400470AA
0x140047087  mov     [rsp+188h+Timeout], r14; Timeout
0x14004708c  xor     r9d, r9d; Alertable
0x14004708f  xor     r8d, r8d; WaitMode
0x140047092  xor     edx, edx; WaitReason
0x140047094  mov     rcx, [rsp+188h+Object]; Object
0x140047099  call    cs:__imp_KeWaitForSingleObject
0x1400470a0  nop     dword ptr [rax+rax+00h]
0x1400470a5  mov     r15d, dword ptr [rsp+188h+Object+8]
0x1400470aa  mov     ebx, r15d
0x1400470ad  test    ebx, ebx
0x1400470af  jns     loc_14004714A
0x1400470b5  xorps   xmm0, xmm0
0x1400470b8  movups  [rsp+188h+var_128], xmm0
0x1400470bd  test    byte ptr cs:xmmword_1400875E0, 40h
0x1400470c4  jz      short loc_1400470DC
0x1400470c6  mov     edx, 23h ; '#'
0x1400470cb  mov     ecx, 406h
0x1400470d0  lea     r8, WPP_43911188515d396c99d3028411eb93bd_Traceguids
0x1400470d7  call    WPP_SF_
0x1400470dc  mov     rcx, [rsp+188h+Object]; Event
0x1400470e1  call    cs:__imp_KeResetEvent
0x1400470e8  nop     dword ptr [rax+rax+00h]
0x1400470ed  lea     r12, AfdSynchronousTlCloseRequestComplete
0x1400470f4  mov     qword ptr [rsp+188h+var_128], r12
0x1400470f9  lea     rax, [rsp+188h+Object]
0x1400470fe  mov     qword ptr [rsp+188h+var_128+8], rax
0x140047103  mov     rax, [rdi]
0x140047106  lea     rdx, [rsp+188h+var_128]
0x14004710b  mov     rcx, [rsp+188h+arg_18]
0x140047113  call    _guard_dispatch_icall
0x140047118  cmp     eax, 103h
0x14004711d  jnz     short loc_14004713D
0x14004711f  mov     [rsp+188h+Timeout], r14; Timeout
0x140047124  xor     r9d, r9d; Alertable
0x140047127  xor     r8d, r8d; WaitMode
0x14004712a  xor     edx, edx; WaitReason
0x14004712c  mov     rcx, [rsp+188h+Object]; Object
0x140047131  call    cs:__imp_KeWaitForSingleObject
0x140047138  nop     dword ptr [rax+rax+00h]
0x14004713d  mov     rax, rdi
0x140047140  mov     rcx, [rsp+188h+arg_18]
0x140047148  jmp     short loc_140047163
0x14004714a  mov     rax, rdi
0x14004714d  mov     rcx, [rsp+188h+arg_18]
0x140047155  jmp     short loc_14004715C
0x140047157  mov     rax, [rsp+188h+var_130]
0x14004715c  lea     r12, AfdSynchronousTlCloseRequestComplete
0x140047163  test    ebx, ebx
0x140047165  jns     short loc_14004718F
0x140047167  test    byte ptr cs:xmmword_1400875E0, 40h
0x14004716e  jz      loc_140047272
0x140047174  mov     edx, 24h ; '$'
0x140047179  mov     ecx, 406h
0x14004717e  lea     r8, WPP_43911188515d396c99d3028411eb93bd_Traceguids
0x140047185  call    WPP_SF_
0x14004718a  jmp     loc_140047272
0x14004718f  xorps   xmm0, xmm0
0x140047192  movups  [rsp+188h+var_128], xmm0
0x140047197  xorps   xmm1, xmm1
0x14004719a  xor     edx, edx
0x14004719c  movups  xmmword ptr [rsp+188h+LockHandle.LockQueue.Next], xmm1
0x1400471a1  mov     qword ptr [rsp+188h+LockHandle.OldIrql], rdx
0x1400471a9  mov     rdi, [rsi+10h]
0x1400471ad  mov     rbx, [rsi+18h]
0x1400471b1  mov     [rsi+10h], rcx
0x1400471b5  mov     [rsi+18h], rax
0x1400471b9  mov     byte ptr [rsi+2], 2
0x1400471bd  mov     edx, 6C646641h; Tag
0x1400471c2  mov     rcx, [rsi+0F0h]; P
0x1400471c9  call    cs:__imp_ExFreePoolWithTag
0x1400471d0  nop     dword ptr [rax+rax+00h]
0x1400471d5  mov     [rsi+0F0h], r14
0x1400471dc  mov     [rsi+0ECh], r14d
0x1400471e3  lea     rcx, [rsi+38h]; SpinLock
  ... truncated ...
```
