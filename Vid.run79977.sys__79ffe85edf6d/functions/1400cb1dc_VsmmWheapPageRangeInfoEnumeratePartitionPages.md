# VsmmWheapPageRangeInfoEnumeratePartitionPages

- ea: `0x1400cb1dc`
- end: `0x1400cb68a`
- name: `VsmmWheapPageRangeInfoEnumeratePartitionPages`
- size: `1198`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400c96c0`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x14002f724`
- `0x1400347a4`
- `0x1400347d4`
- `0x1400cb084`
- `0x1400cb1dc`
- `0x1400cbb38`
- `0x1400fbfd4`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400cb453`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400cb453`
- `ntoskrnl!ObfDereferenceObject` at `0x1400cb4bc`
- `ntoskrnl!ObfDereferenceObject` at `0x1400cb4bc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400cb3a4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400cb4ac`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400cb3a4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400cb4ac`
- `ntoskrnl!ZwClose` at `0x1400cb471`
- `ntoskrnl!ZwClose` at `0x1400cb471`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cb50b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cb50b`
- `ntoskrnl!ExAllocatePool2` at `0x1400cb2dc`
- `ntoskrnl!ExAllocatePool2` at `0x1400cb2dc`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400cb40f`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400cb40f`
- `ntoskrnl!PsCreateSystemThread` at `0x1400cb3d3`
- `ntoskrnl!PsCreateSystemThread` at `0x1400cb3d3`
- `HAL!KeQueryPerformanceCounter` at `0x1400cb22d`
- `HAL!KeQueryPerformanceCounter` at `0x1400cb524`
- `HAL!KeQueryPerformanceCounter` at `0x1400cb22d`
- `HAL!KeQueryPerformanceCounter` at `0x1400cb524`

## pseudocode

```c
NTSTATUS __fastcall VsmmWheapPageRangeInfoEnumeratePartitionPages(__int64 *a1, __int64 a2, void *a3)
{
  int v6; // eax
  __int64 v7; // rax
  __int64 *i; // rbx
  PVOID *Pool2; // rax
  PVOID *v10; // rcx
  PVOID **v11; // rax
  PVOID *StartContext; // rbx
  NTSTATUS v13; // eax
  void *v14; // rcx
  PVOID *j; // rbx
  PVOID v16; // rcx
  PVOID *v17; // rax
  NTSTATUS result; // eax
  __int64 v19; // r9
  PVOID P[2]; // [rsp+40h] [rbp-C0h] BYREF
  void *ThreadHandle; // [rsp+50h] [rbp-B0h] BYREF
  PVOID Object; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h] BYREF
  __int64 v25; // [rsp+70h] [rbp-90h] BYREF
  __int64 v26; // [rsp+78h] [rbp-88h] BYREF
  __int64 v27; // [rsp+80h] [rbp-80h] BYREF
  __int128 v28; // [rsp+88h] [rbp-78h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+98h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+A0h] [rbp-60h] BYREF
  char v31[16]; // [rsp+C0h] [rbp-40h] BYREF
  char v32[16]; // [rsp+D0h] [rbp-30h] BYREF
  PVOID *p_Object; // [rsp+E0h] [rbp-20h]
  __int64 v34; // [rsp+E8h] [rbp-18h]
  __int64 *v35; // [rsp+F0h] [rbp-10h]
  __int64 v36; // [rsp+F8h] [rbp-8h]
  __int64 *v37; // [rsp+100h] [rbp+0h]
  __int64 v38; // [rsp+108h] [rbp+8h]
  __int64 *v39; // [rsp+110h] [rbp+10h]
  __int64 v40; // [rsp+118h] [rbp+18h]
  __int64 *v41; // [rsp+120h] [rbp+20h]
  __int64 v42; // [rsp+128h] [rbp+28h]
  void **p_ThreadHandle; // [rsp+130h] [rbp+30h]
  __int64 v44; // [rsp+138h] [rbp+38h]
  __int64 *v45; // [rsp+140h] [rbp+40h]
  __int64 v46; // [rsp+148h] [rbp+48h]

  PerformanceFrequency.QuadPart = 0;
  v28 = 0;
  ThreadHandle = 0;
  *(LARGE_INTEGER *)&v28 = KeQueryPerformanceCounter(0);
  P[1] = P;
  P[0] = P;
  VidObjectLockAcquireShared((char *)VidDeviceExtension + 104);
  while ( 1 )
  {
    v7 = VidPartitionTableEnumerateById(&ThreadHandle);
    if ( !v7 )
      break;
    if ( !a2 || a2 == *(_QWORD *)(v7 + 648) )
    {
      v6 = VsmmWheapPageRangeInfoAddPartition(a1, v7);
      if ( v6 >= 0 )
        ++*((_DWORD *)a1 + 5);
      else
        VidTraceErrorStatusInternal0(
          "VsmmWheapPageRangeInfoEnumeratePartitionPages",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c",
          4002,
          (unsigned int)v6);
    }
  }
  VidObjectLockRelease((char *)VidDeviceExtension + 104);
  for ( i = (__int64 *)a1[3]; i != a1 + 3; i = (__int64 *)*i )
  {
    Pool2 = (PVOID *)ExAllocatePool2(256, 64, 1833788502);
    v10 = Pool2;
    if ( Pool2 )
    {
      Pool2[1] = Pool2;
      *Pool2 = Pool2;
      Pool2[2] = i;
      Pool2[3] = a1;
      Pool2[4] = a3;
      Pool2[5] = a1 + 5;
      v11 = (PVOID **)P[1];
      if ( *(PVOID **)P[1] != P )
LABEL_30:
        __fastfail(3u);
      v10[1] = P[1];
      *v10 = P;
      *v11 = v10;
      P[1] = v10;
    }
    else
    {
      VidTraceErrorStatusInternal0(
        "VsmmWheapPageRangeInfoEnumeratePartitionPages",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c",
        4033,
        3221225626LL);
    }
  }
  for ( StartContext = (PVOID *)P[0]; StartContext != P; StartContext = (PVOID *)*StartContext )
  {
    ThreadHandle = 0;
    if ( _InterlockedCompareExchange64(a1 + 5, 0, 0) >= (unsigned __int64)*a1 )
      break;
    KeWaitForSingleObject(&VsmmWheapPageRangeInfoEnumeratePartitionPagesConcurrentLimit, Executive, 0, 0, 0);
    v13 = PsCreateSystemThread(
            &ThreadHandle,
            0x1FFFFFu,
            0,
            0,
            0,
            (PKSTART_ROUTINE)VsmmWheapPartitionInfoEnumeratePagesThreadRoutine,
            StartContext);
    if ( v13 >= 0 )
    {
      Object = 0;
      ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, &Object, 0);
      v14 = ThreadHandle;
      StartContext[6] = Object;
      *((_BYTE *)StartContext + 56) = 1;
      ZwClose(v14);
    }
    else
    {
      VidTraceErrorStatusInternal0(
        "VsmmWheapPageRangeInfoEnumeratePartitionPages",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c",
        4101,
        (unsigned int)v13);
      KeReleaseSemaphore(&VsmmWheapPageRangeInfoEnumeratePartitionPagesConcurrentLimit, 0, 1, 0);
      VsmmWheapPartitionInfoEnumeratePages(StartContext[2], StartContext[3], StartContext[4], StartContext[5]);
    }
  }
  for ( j = (PVOID *)P[0]; j != P; j = (PVOID *)*j )
  {
    if ( *((_BYTE *)j + 56) )
    {
      KeWaitForSingleObject(j[6], Executive, 0, 0, 0);
      ObfDereferenceObject(j[6]);
    }
  }
  while ( P[0] != P )
  {
    v16 = P[1];
    if ( *(PVOID **)P[1] != P )
      goto LABEL_30;
    v17 = (PVOID *)*((_QWORD *)P[1] + 1);
    if ( *v17 != P[1] )
      goto LABEL_30;
    P[1] = *((PVOID *)P[1] + 1);
    *v17 = P;
    ExFreePoolWithTag(v16, 0x6D4D6456u);
  }
  *((LARGE_INTEGER *)&v28 + 1) = KeQueryPerformanceCounter(&PerformanceFrequency);
  result = dword_140065110;
  if ( (unsigned int)dword_140065110 > 4 )
  {
    result = tlgKeywordOn(&dword_140065110, 256);
    if ( (_BYTE)result )
    {
      tlgCreate1Sz_char(v31, "VsmmWheapPageRangeInfoEnumeratePartitionPages");
      tlgCreate1Sz_char(v32, "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c");
      v34 = v19;
      p_Object = &Object;
      v23 = a1[1];
      v35 = &v23;
      v24 = *a1;
      v37 = &v24;
      v39 = &v25;
      v44 = v19;
      LODWORD(Object) = 4196;
      v36 = 8;
      v26 = 1000000LL * (*((_QWORD *)&v28 + 1) - (_QWORD)v28) / PerformanceFrequency.QuadPart;
      v41 = &v26;
      LODWORD(ThreadHandle) = *((_DWORD *)a1 + 5);
      p_ThreadHandle = &ThreadHandle;
      v27 = a1[5];
      v45 = &v27;
      v38 = 8;
      v25 = a2;
      v40 = 8;
      v42 = 8;
      v46 = 8;
      return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140065110, byte_14005340F, 0, 0, 0xBu, &v30);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400cb1dc  mov     [rsp-8+arg_8], rbx
0x1400cb1e1  mov     [rsp-8+arg_10], rsi
0x1400cb1e6  push    rbp
0x1400cb1e7  push    rdi
0x1400cb1e8  push    r12
0x1400cb1ea  push    r14
0x1400cb1ec  push    r15
0x1400cb1ee  lea     rbp, [rsp-60h]
0x1400cb1f3  sub     rsp, 160h
0x1400cb1fa  mov     rax, cs:__security_cookie
0x1400cb201  xor     rax, rsp
0x1400cb204  mov     [rbp+80h+var_30], rax
0x1400cb208  xorps   xmm0, xmm0
0x1400cb20b  mov     rdi, rcx
0x1400cb20e  xor     eax, eax
0x1400cb210  xor     r12d, r12d
0x1400cb213  xor     ecx, ecx; PerformanceFrequency
0x1400cb215  mov     qword ptr [rbp+80h+PerformanceFrequency], rax
0x1400cb219  movups  [rbp+80h+var_F8], xmm0
0x1400cb21d  mov     [rsp+180h+ThreadHandle], r12
0x1400cb222  mov     r15, r8
0x1400cb225  movups  xmmword ptr [rsp+180h+P], xmm0
0x1400cb22a  mov     r14, rdx
0x1400cb22d  call    cs:__imp_KeQueryPerformanceCounter
0x1400cb234  nop     dword ptr [rax+rax+00h]
0x1400cb239  mov     rcx, cs:VidDeviceExtension
0x1400cb240  mov     qword ptr [rbp+80h+var_F8], rax
0x1400cb244  add     rcx, 68h ; 'h'
0x1400cb248  lea     rax, [rsp+180h+P]
0x1400cb24d  mov     [rsp+180h+P+8], rax
0x1400cb252  lea     rax, [rsp+180h+P]
0x1400cb257  mov     [rsp+180h+P], rax
0x1400cb25c  call    VidObjectLockAcquireShared
0x1400cb261  jmp     short loc_1400CB2A1
0x1400cb263  test    r14, r14
0x1400cb266  jz      short loc_1400CB271
0x1400cb268  cmp     r14, [rax+288h]
0x1400cb26f  jnz     short loc_1400CB2A1
0x1400cb271  mov     rdx, rax
0x1400cb274  mov     rcx, rdi
0x1400cb277  call    VsmmWheapPageRangeInfoAddPartition
0x1400cb27c  test    eax, eax
0x1400cb27e  jns     short loc_1400CB29E
0x1400cb280  mov     r9d, eax
0x1400cb283  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400cb28a  mov     r8d, 0FA2h
0x1400cb290  lea     rcx, aVsmmwheappager; "VsmmWheapPageRangeInfoEnumeratePartitio"...
0x1400cb297  call    VidTraceErrorStatusInternal0
0x1400cb29c  jmp     short loc_1400CB2A1
0x1400cb29e  inc     dword ptr [rdi+14h]
0x1400cb2a1  lea     rcx, [rsp+180h+ThreadHandle]
0x1400cb2a6  call    VidPartitionTableEnumerateById
0x1400cb2ab  test    rax, rax
0x1400cb2ae  jnz     short loc_1400CB263
0x1400cb2b0  mov     rcx, cs:VidDeviceExtension
0x1400cb2b7  add     rcx, 68h ; 'h'
0x1400cb2bb  call    VidObjectLockRelease
0x1400cb2c0  lea     rsi, [rdi+18h]
0x1400cb2c4  mov     rbx, [rsi]
0x1400cb2c7  jmp     loc_1400CB356
0x1400cb2cc  mov     edx, 40h ; '@'
0x1400cb2d1  mov     ecx, 100h
0x1400cb2d6  mov     r8d, 6D4D6456h
0x1400cb2dc  call    cs:__imp_ExAllocatePool2
0x1400cb2e3  nop     dword ptr [rax+rax+00h]
0x1400cb2e8  mov     rcx, rax
0x1400cb2eb  test    rax, rax
0x1400cb2ee  jnz     short loc_1400CB311
0x1400cb2f0  mov     r9d, 0C000009Ah
0x1400cb2f6  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400cb2fd  mov     r8d, 0FC1h
0x1400cb303  lea     rcx, aVsmmwheappager; "VsmmWheapPageRangeInfoEnumeratePartitio"...
0x1400cb30a  call    VidTraceErrorStatusInternal0
0x1400cb30f  jmp     short loc_1400CB353
0x1400cb311  mov     [rax+8], rcx
0x1400cb315  lea     rdx, [rsp+180h+P]
0x1400cb31a  mov     [rax], rcx
0x1400cb31d  mov     [rax+10h], rbx
0x1400cb321  mov     [rax+18h], rdi
0x1400cb325  mov     [rax+20h], r15
0x1400cb329  lea     rax, [rdi+28h]
0x1400cb32d  mov     [rcx+28h], rax
0x1400cb331  mov     rax, [rsp+180h+P+8]
0x1400cb336  cmp     [rax], rdx
0x1400cb339  jnz     loc_1400CB519
0x1400cb33f  mov     [rcx+8], rax
0x1400cb343  lea     rdx, [rsp+180h+P]
0x1400cb348  mov     [rcx], rdx
0x1400cb34b  mov     [rax], rcx
0x1400cb34e  mov     [rsp+180h+P+8], rcx
0x1400cb353  mov     rbx, [rbx]
0x1400cb356  cmp     rbx, rsi
0x1400cb359  jnz     loc_1400CB2CC
0x1400cb35f  mov     rbx, [rsp+180h+P]
0x1400cb364  lea     rax, [rsp+180h+P]
0x1400cb369  cmp     rbx, rax
0x1400cb36c  jz      loc_1400CB48E
0x1400cb372  mov     esi, 1FFFFFh
0x1400cb377  mov     [rsp+180h+ThreadHandle], r12
0x1400cb37c  mov     rcx, r12
0x1400cb37f  xor     eax, eax
0x1400cb381  lock cmpxchg [rdi+28h], rcx
0x1400cb387  cmp     rax, [rdi]
0x1400cb38a  jnb     loc_1400CB48E
0x1400cb390  xor     r9d, r9d; Alertable
0x1400cb393  mov     [rsp+180h+Timeout], r12; Timeout
0x1400cb398  xor     r8d, r8d; WaitMode
0x1400cb39b  lea     rcx, VsmmWheapPageRangeInfoEnumeratePartitionPagesConcurrentLimit; Object
0x1400cb3a2  xor     edx, edx; WaitReason
0x1400cb3a4  call    cs:__imp_KeWaitForSingleObject
0x1400cb3ab  nop     dword ptr [rax+rax+00h]
0x1400cb3b0  lea     rax, VsmmWheapPartitionInfoEnumeratePagesThreadRoutine
0x1400cb3b7  mov     [rsp+180h+StartContext], rbx; StartContext
0x1400cb3bc  mov     [rsp+180h+StartRoutine], rax; StartRoutine
0x1400cb3c1  lea     rcx, [rsp+180h+ThreadHandle]; ThreadHandle
0x1400cb3c6  xor     r9d, r9d; ProcessHandle
0x1400cb3c9  mov     [rsp+180h+Timeout], r12; ClientId
0x1400cb3ce  xor     r8d, r8d; ObjectAttributes
0x1400cb3d1  mov     edx, esi; DesiredAccess
0x1400cb3d3  call    cs:__imp_PsCreateSystemThread
0x1400cb3da  nop     dword ptr [rax+rax+00h]
0x1400cb3df  test    eax, eax
0x1400cb3e1  jns     short loc_1400CB432
0x1400cb3e3  mov     r9d, eax
0x1400cb3e6  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400cb3ed  mov     r8d, 1005h
0x1400cb3f3  lea     rcx, aVsmmwheappager; "VsmmWheapPageRangeInfoEnumeratePartitio"...
0x1400cb3fa  call    VidTraceErrorStatusInternal0
0x1400cb3ff  xor     r9d, r9d; Wait
0x1400cb402  lea     rcx, VsmmWheapPageRangeInfoEnumeratePartitionPagesConcurrentLimit; Semaphore
0x1400cb409  xor     edx, edx; Increment
0x1400cb40b  lea     r8d, [r9+1]; Adjustment
0x1400cb40f  call    cs:__imp_KeReleaseSemaphore
0x1400cb416  nop     dword ptr [rax+rax+00h]
0x1400cb41b  mov     r9, [rbx+28h]
0x1400cb41f  mov     r8, [rbx+20h]
0x1400cb423  mov     rdx, [rbx+18h]
0x1400cb427  mov     rcx, [rbx+10h]
0x1400cb42b  call    VsmmWheapPartitionInfoEnumeratePages
0x1400cb430  jmp     short loc_1400CB47D
0x1400cb432  mov     rcx, [rsp+180h+ThreadHandle]; Handle
0x1400cb437  lea     rax, [rsp+180h+Object]
0x1400cb43c  mov     [rsp+180h+StartRoutine], r12; HandleInformation
0x1400cb441  xor     r9d, r9d; AccessMode
0x1400cb444  xor     r8d, r8d; ObjectType
0x1400cb447  mov     [rsp+180h+Timeout], rax; Object
0x1400cb44c  mov     edx, esi; DesiredAccess
0x1400cb44e  mov     [rsp+180h+Object], r12
0x1400cb453  call    cs:__imp_ObReferenceObjectByHandle
0x1400cb45a  nop     dword ptr [rax+rax+00h]
0x1400cb45f  mov     rax, [rsp+180h+Object]
0x1400cb464  mov     rcx, [rsp+180h+ThreadHandle]; Handle
0x1400cb469  mov     [rbx+30h], rax
0x1400cb46d  mov     byte ptr [rbx+38h], 1
0x1400cb471  call    cs:__imp_ZwClose
0x1400cb478  nop     dword ptr [rax+rax+00h]
0x1400cb47d  mov     rbx, [rbx]
0x1400cb480  lea     rax, [rsp+180h+P]
0x1400cb485  cmp     rbx, rax
0x1400cb488  jnz     loc_1400CB377
0x1400cb48e  mov     rbx, [rsp+180h+P]
0x1400cb493  jmp     short loc_1400CB4CB
0x1400cb495  cmp     [rbx+38h], r12b
0x1400cb499  jz      short loc_1400CB4C8
0x1400cb49b  mov     rcx, [rbx+30h]; Object
0x1400cb49f  xor     r9d, r9d; Alertable
0x1400cb4a2  xor     r8d, r8d; WaitMode
0x1400cb4a5  mov     [rsp+180h+Timeout], r12; Timeout
0x1400cb4aa  xor     edx, edx; WaitReason
0x1400cb4ac  call    cs:__imp_KeWaitForSingleObject
0x1400cb4b3  nop     dword ptr [rax+rax+00h]
0x1400cb4b8  mov     rcx, [rbx+30h]; Object
0x1400cb4bc  call    cs:__imp_ObfDereferenceObject
0x1400cb4c3  nop     dword ptr [rax+rax+00h]
0x1400cb4c8  mov     rbx, [rbx]
0x1400cb4cb  lea     rax, [rsp+180h+P]
0x1400cb4d0  cmp     rbx, rax
0x1400cb4d3  jnz     short loc_1400CB495
0x1400cb4d5  lea     rax, [rsp+180h+P]
0x1400cb4da  cmp     [rsp+180h+P], rax
0x1400cb4df  jz      short loc_1400CB520
0x1400cb4e1  mov     rcx, [rsp+180h+P+8]; P
0x1400cb4e6  lea     rax, [rsp+180h+P]
0x1400cb4eb  cmp     [rcx], rax
0x1400cb4ee  jnz     short loc_1400CB519
0x1400cb4f0  mov     rax, [rcx+8]
0x1400cb4f4  cmp     [rax], rcx
0x1400cb4f7  jnz     short loc_1400CB519
0x1400cb4f9  lea     rdx, [rsp+180h+P]
0x1400cb4fe  mov     [rsp+180h+P+8], rax
0x1400cb503  mov     [rax], rdx
0x1400cb506  mov     edx, 6D4D6456h; Tag
0x1400cb50b  call    cs:__imp_ExFreePoolWithTag
0x1400cb512  nop     dword ptr [rax+rax+00h]
0x1400cb517  jmp     short loc_1400CB4D5
0x1400cb519  mov     ecx, 3
0x1400cb51e  int     29h; Win8: RtlFailFast(ecx)
0x1400cb520  lea     rcx, [rbp+80h+PerformanceFrequency]; PerformanceFrequency
0x1400cb524  call    cs:__imp_KeQueryPerformanceCounter
0x1400cb52b  nop     dword ptr [rax+rax+00h]
0x1400cb530  mov     qword ptr [rbp+80h+var_F8+8], rax
0x1400cb534  mov     r9d, 4
0x1400cb53a  mov     eax, cs:dword_140065110
0x1400cb540  cmp     eax, r9d
0x1400cb543  jbe     loc_1400CB661
0x1400cb549  mov     edx, 100h
0x1400cb54e  lea     rcx, dword_140065110
0x1400cb555  call    _tlgKeywordOn
0x1400cb55a  test    al, al
0x1400cb55c  jz      loc_1400CB661
0x1400cb562  lea     rdx, aVsmmwheappager; "VsmmWheapPageRangeInfoEnumeratePartitio"...
0x1400cb569  lea     rcx, [rbp+80h+var_C0]
0x1400cb56d  call    _tlgCreate1Sz_char
0x1400cb572  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400cb579  lea     rcx, [rbp+80h+var_B0]
0x1400cb57d  call    _tlgCreate1Sz_char
0x1400cb582  lea     rax, [rsp+180h+Object]
0x1400cb587  mov     [rbp+80h+var_98], r9
0x1400cb58b  mov     [rbp+80h+var_A0], rax
0x1400cb58f  lea     rcx, dword_140065110
0x1400cb596  mov     rax, [rdi+8]
0x1400cb59a  xor     r8d, r8d
0x1400cb59d  mov     [rsp+180h+var_120], rax
0x1400cb5a2  lea     rax, [rsp+180h+var_120]
0x1400cb5a7  mov     [rbp+80h+var_90], rax
0x1400cb5ab  mov     rax, [rdi]
0x1400cb5ae  mov     [rsp+180h+var_118], rax
0x1400cb5b3  lea     rax, [rsp+180h+var_118]
0x1400cb5b8  mov     [rbp+80h+var_80], rax
0x1400cb5bc  lea     rax, [rsp+180h+var_110]
0x1400cb5c1  mov     [rbp+80h+var_70], rax
0x1400cb5c5  mov     rax, qword ptr [rbp+80h+var_F8+8]
0x1400cb5c9  sub     rax, qword ptr [rbp+80h+var_F8]
0x1400cb5cd  imul    rax, 0F4240h
0x1400cb5d4  mov     [rbp+80h+var_48], r9
0x1400cb5d8  xor     r9d, r9d
0x1400cb5db  cqo
0x1400cb5dd  mov     dword ptr [rsp+180h+Object], 1064h
0x1400cb5e5  idiv    qword ptr [rbp+80h+PerformanceFrequency]
0x1400cb5e9  lea     rdx, byte_14005340F
0x1400cb5f0  mov     [rbp+80h+var_88], 8
0x1400cb5f8  mov     [rsp+180h+var_108], rax
0x1400cb5fd  lea     rax, [rsp+180h+var_108]
0x1400cb602  mov     [rbp+80h+var_60], rax
0x1400cb606  mov     eax, [rdi+14h]
0x1400cb609  mov     dword ptr [rsp+180h+ThreadHandle], eax
0x1400cb60d  lea     rax, [rsp+180h+ThreadHandle]
0x1400cb612  mov     [rbp+80h+var_50], rax
0x1400cb616  mov     rax, [rdi+28h]
0x1400cb61a  mov     [rbp+80h+var_100], rax
0x1400cb61e  lea     rax, [rbp+80h+var_100]
0x1400cb622  mov     [rbp+80h+var_40], rax
0x1400cb626  lea     rax, [rbp+80h+var_E0]
0x1400cb62a  mov     [rsp+180h+StartRoutine], rax
0x1400cb62f  mov     dword ptr [rsp+180h+Timeout], 0Bh
0x1400cb637  mov     [rbp+80h+var_78], 8
0x1400cb63f  mov     [rsp+180h+var_110], r14
0x1400cb644  mov     [rbp+80h+var_68], 8
0x1400cb64c  mov     [rbp+80h+var_58], 8
0x1400cb654  mov     [rbp+80h+var_38], 8
0x1400cb65c  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400cb661  mov     rcx, [rbp+80h+var_30]
0x1400cb665  xor     rcx, rsp; StackCookie
0x1400cb668  call    __security_check_cookie
0x1400cb66d  lea     r11, [rsp+180h+var_20]
0x1400cb675  mov     rbx, [r11+38h]
0x1400cb679  mov     rsi, [r11+40h]
0x1400cb67d  mov     rsp, r11
0x1400cb680  pop     r15
0x1400cb682  pop     r14
0x1400cb684  pop     r12
0x1400cb686  pop     rdi
0x1400cb687  pop     rbp
0x1400cb688  retn
```
