# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::Run(void)

- ea: `0x14000e7f8`
- end: `0x14000ebc8`
- name: `?Run@?$ThreadPool@V?$shared_ptr@VStreamFault@Streaming@@@kernel_std@@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@AEAAJXZ`
- size: `976`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000efc0`

## callees

- `0x140003bd8`
- `0x140003c58`
- `0x14000c4ac`
- `0x14000e5a8`
- `0x14000e7f8`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e8a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e8ec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ea88`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000eaea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000eba8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e8a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e8ec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ea88`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000eaea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000eba8`
- `ntoskrnl!ObfReferenceObject` at `0x14000e8b8`
- `ntoskrnl!ObfReferenceObject` at `0x14000e8b8`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000e82d`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000e90a`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000e82d`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000e90a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e89b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e8e0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ea7c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000eade`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000eb9c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e89b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e8e0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ea7c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000eade`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000eb9c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000e860`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000ea2a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000eb29`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000e860`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000ea2a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000eb29`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14000e95e`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14000e95e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e84d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ea17`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000eb16`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e84d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ea17`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000eb16`
- `ntoskrnl!ObfDereferenceObject` at `0x14000eaa2`
- `ntoskrnl!ObfDereferenceObject` at `0x14000eb65`
- `ntoskrnl!ObfDereferenceObject` at `0x14000eaa2`
- `ntoskrnl!ObfDereferenceObject` at `0x14000eb65`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::Run(
        __int64 a1)
{
  struct _KTHREAD *CurrentThread; // r15
  bool v3; // bp
  int v4; // edx
  int v5; // r14d
  struct _ERESOURCE *v6; // rcx
  struct _ERESOURCE *v7; // rcx
  NTSTATUS v9; // r12d
  volatile signed __int32 *v10; // r14
  unsigned int v11; // r14d
  bool v12; // bp
  unsigned int v13; // ecx
  __int64 v14; // r8
  unsigned int v15; // eax
  __int64 v16; // r14
  char v17; // r14
  struct _ERESOURCE *v18; // rcx
  struct _ERESOURCE *v19; // rcx
  bool v20; // di
  unsigned int v21; // ecx
  __int64 v22; // r8
  unsigned int v23; // eax
  __int64 v24; // rbp
  struct _ERESOURCE *v25; // rcx
  Streaming::StreamFault *v26[2]; // [rsp+40h] [rbp-78h] BYREF
  PVOID Object[2]; // [rsp+50h] [rbp-68h] BYREF
  __int128 v28; // [rsp+60h] [rbp-58h] BYREF

  CurrentThread = KeGetCurrentThread();
  if ( CurrentThread )
  {
    v3 = 0;
    if ( *(_QWORD *)(a1 + 112) )
    {
      KeEnterCriticalRegion();
      v3 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 112), 1u) == 1;
    }
    v4 = *(_DWORD *)(a1 + 88);
    if ( *(_DWORD *)(a1 + 92) == v4
      && (v5 = appv::shared::kernel::ThreadHandles<Streaming::StreamFaultTagInfo>::ResizeNoLock(
                 a1 + 56,
                 (unsigned int)(v4 + 10)),
          v5 < 0) )
    {
      if ( v3 )
      {
        v6 = *(struct _ERESOURCE **)(a1 + 112);
        if ( v6 )
        {
          ExReleaseResourceLite(v6);
          KeLeaveCriticalRegion();
        }
      }
    }
    else
    {
      ObfReferenceObject(CurrentThread);
      *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL * (unsigned int)(*(_DWORD *)(a1 + 92))++) = CurrentThread;
      if ( v3 )
      {
        v7 = *(struct _ERESOURCE **)(a1 + 112);
        if ( v7 )
        {
          ExReleaseResourceLite(v7);
          KeLeaveCriticalRegion();
        }
      }
      v5 = 0;
    }
    KeReleaseSemaphore((PRKSEMAPHORE)(a1 + 176), 0, 1, 0);
    if ( v5 < 0 )
      return (unsigned int)v5;
    Object[0] = *(PVOID *)(a1 + 128);
    Object[1] = (PVOID)(a1 + 144);
    do
    {
      v9 = KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, 0, 0);
      _InterlockedAdd((volatile signed __int32 *)(a1 + 208), 1u);
      if ( v9 == 1 )
      {
        *(_OWORD *)v26 = 0;
        v28 = 0;
        if ( (unsigned __int8)appv::shared::kernel::SafeQueue<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::Get(
                                a1,
                                v26) )
        {
          Streaming::StreamFault::Execute(v26[0]);
          v26[0] = 0;
          kernel_std::detail::shared_count::operator=(&v26[1], (char *)&v28 + 8);
        }
        v10 = (volatile signed __int32 *)v26[1];
        if ( v26[1] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v26[1] + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
            if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
          }
        }
      }
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 208));
      v11 = *(_DWORD *)(a1 + 212);
      v12 = 0;
      if ( *(_QWORD *)(a1 + 112) )
      {
        KeEnterCriticalRegion();
        v12 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 112), 1u) == 1;
      }
      v13 = *(_DWORD *)(a1 + 92);
      if ( v13 <= v11 )
      {
        if ( v12 )
        {
          v19 = *(struct _ERESOURCE **)(a1 + 112);
          if ( v19 )
          {
            ExReleaseResourceLite(v19);
            KeLeaveCriticalRegion();
          }
        }
      }
      else
      {
        if ( *(_BYTE *)(a1 + 96) && v13 )
        {
          v14 = *(_QWORD *)(a1 + 64);
          v15 = 0;
          while ( 1 )
          {
            v16 = v15;
            if ( CurrentThread == *(struct _KTHREAD **)(v14 + 8LL * v15) )
              break;
            if ( ++v15 >= v13 )
              goto LABEL_32;
          }
          ObfDereferenceObject(*(PVOID *)(v14 + 8LL * v15));
          *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8 * v16) = *(_QWORD *)(*(_QWORD *)(a1 + 64)
                                                                  + 8LL * (unsigned int)--*(_DWORD *)(a1 + 92));
          v17 = 1;
          *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL * *(unsigned int *)(a1 + 92)) = 0;
        }
        else
        {
LABEL_32:
          v17 = 0;
        }
        if ( v12 )
        {
          v18 = *(struct _ERESOURCE **)(a1 + 112);
          if ( v18 )
          {
            ExReleaseResourceLite(v18);
            KeLeaveCriticalRegion();
          }
        }
        if ( v17 )
          return 0;
      }
    }
    while ( v9 == 1 || v9 == -1073741670 );
    v20 = 0;
    if ( *(_QWORD *)(a1 + 112) )
    {
      KeEnterCriticalRegion();
      v20 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 112), 1u) == 1;
    }
    if ( *(_BYTE *)(a1 + 96) )
    {
      v21 = *(_DWORD *)(a1 + 92);
      if ( v21 )
      {
        v22 = *(_QWORD *)(a1 + 64);
        v23 = 0;
        while ( 1 )
        {
          v24 = v23;
          if ( CurrentThread == *(struct _KTHREAD **)(v22 + 8LL * v23) )
            break;
          if ( ++v23 >= v21 )
            goto LABEL_53;
        }
        ObfDereferenceObject(*(PVOID *)(v22 + 8LL * v23));
        *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8 * v24) = *(_QWORD *)(*(_QWORD *)(a1 + 64)
                                                                + 8LL * (unsigned int)--*(_DWORD *)(a1 + 92));
        *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL * *(unsigned int *)(a1 + 92)) = 0;
      }
    }
LABEL_53:
    if ( v20 )
    {
      v25 = *(struct _ERESOURCE **)(a1 + 112);
      if ( v25 )
      {
        ExReleaseResourceLite(v25);
        KeLeaveCriticalRegion();
      }
    }
  }
  else
  {
    KeReleaseSemaphore((PRKSEMAPHORE)(a1 + 176), 0, 1, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14000e7f8  push    rbx
0x14000e7fa  push    rbp
0x14000e7fb  push    rsi
0x14000e7fc  push    rdi
0x14000e7fd  push    r12
0x14000e7ff  push    r13
0x14000e801  push    r14
0x14000e803  push    r15
0x14000e805  sub     rsp, 78h
0x14000e809  mov     r15, gs:188h
0x14000e812  xor     r13d, r13d
0x14000e815  mov     rbx, rcx
0x14000e818  test    r15, r15
0x14000e81b  jnz     short loc_14000E83E
0x14000e81d  add     rcx, 0B0h; Semaphore
0x14000e824  lea     r8d, [r13+1]; Adjustment
0x14000e828  xor     r9d, r9d; Wait
0x14000e82b  xor     edx, edx; Increment
0x14000e82d  call    cs:__imp_KeReleaseSemaphore
0x14000e834  nop     dword ptr [rax+rax+00h]
0x14000e839  jmp     loc_14000EBB4
0x14000e83e  mov     esi, 1
0x14000e843  movzx   ebp, r13b
0x14000e847  cmp     [rcx+70h], r13
0x14000e84b  jz      short loc_14000E872
0x14000e84d  call    cs:__imp_KeEnterCriticalRegion
0x14000e854  nop     dword ptr [rax+rax+00h]
0x14000e859  mov     rcx, [rbx+70h]; Resource
0x14000e85d  mov     dl, sil; Wait
0x14000e860  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000e867  nop     dword ptr [rax+rax+00h]
0x14000e86c  cmp     al, sil
0x14000e86f  cmovz   ebp, esi
0x14000e872  mov     edx, [rbx+58h]
0x14000e875  cmp     [rbx+5Ch], edx
0x14000e878  jnz     short loc_14000E8B5
0x14000e87a  add     edx, 0Ah
0x14000e87d  lea     rcx, [rbx+38h]
0x14000e881  call    ?ResizeNoLock@?$ThreadHandles@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@AEAAJK@Z; appv::shared::kernel::ThreadHandles<Streaming::StreamFaultTagInfo>::ResizeNoLock(ulong)
0x14000e886  mov     r14d, eax
0x14000e889  test    eax, eax
0x14000e88b  jns     short loc_14000E8B5
0x14000e88d  test    bpl, bpl
0x14000e890  jz      short loc_14000E8FB
0x14000e892  mov     rcx, [rbx+70h]; Resource
0x14000e896  test    rcx, rcx
0x14000e899  jz      short loc_14000E8FB
0x14000e89b  call    cs:__imp_ExReleaseResourceLite
0x14000e8a2  nop     dword ptr [rax+rax+00h]
0x14000e8a7  call    cs:__imp_KeLeaveCriticalRegion
0x14000e8ae  nop     dword ptr [rax+rax+00h]
0x14000e8b3  jmp     short loc_14000E8FB
0x14000e8b5  mov     rcx, r15; Object
0x14000e8b8  call    cs:__imp_ObfReferenceObject
0x14000e8bf  nop     dword ptr [rax+rax+00h]
0x14000e8c4  mov     ecx, [rbx+5Ch]
0x14000e8c7  mov     rax, [rbx+40h]
0x14000e8cb  mov     [rax+rcx*8], r15
0x14000e8cf  add     [rbx+5Ch], esi
0x14000e8d2  test    bpl, bpl
0x14000e8d5  jz      short loc_14000E8F8
0x14000e8d7  mov     rcx, [rbx+70h]; Resource
0x14000e8db  test    rcx, rcx
0x14000e8de  jz      short loc_14000E8F8
0x14000e8e0  call    cs:__imp_ExReleaseResourceLite
0x14000e8e7  nop     dword ptr [rax+rax+00h]
0x14000e8ec  call    cs:__imp_KeLeaveCriticalRegion
0x14000e8f3  nop     dword ptr [rax+rax+00h]
0x14000e8f8  mov     r14d, r13d
0x14000e8fb  lea     rcx, [rbx+0B0h]; Semaphore
0x14000e902  xor     r9d, r9d; Wait
0x14000e905  mov     r8d, esi; Adjustment
0x14000e908  xor     edx, edx; Increment
0x14000e90a  call    cs:__imp_KeReleaseSemaphore
0x14000e911  nop     dword ptr [rax+rax+00h]
0x14000e916  test    r14d, r14d
0x14000e919  jns     short loc_14000E923
0x14000e91b  mov     eax, r14d
0x14000e91e  jmp     loc_14000EBB6
0x14000e923  mov     rax, [rbx+80h]
0x14000e92a  mov     [rsp+0B8h+Object], rax
0x14000e92f  lea     rax, [rbx+90h]
0x14000e936  mov     [rsp+0B8h+var_60], rax
0x14000e93b  mov     [rsp+0B8h+WaitBlockArray], r13; WaitBlockArray
0x14000e940  lea     rdx, [rsp+0B8h+Object]; Object
0x14000e945  xor     r9d, r9d; WaitReason
0x14000e948  mov     [rsp+0B8h+Timeout], r13; Timeout
0x14000e94d  mov     [rsp+0B8h+Alertable], r13b; Alertable
0x14000e952  mov     r8d, esi; WaitType
0x14000e955  mov     [rsp+0B8h+WaitMode], r13b; WaitMode
0x14000e95a  lea     ecx, [r9+2]; Count
0x14000e95e  call    cs:__imp_KeWaitForMultipleObjects
0x14000e965  nop     dword ptr [rax+rax+00h]
0x14000e96a  mov     r12d, eax
0x14000e96d  lock add [rbx+0D0h], esi
0x14000e974  cmp     eax, esi
0x14000e976  jnz     loc_14000E9FF
0x14000e97c  xorps   xmm0, xmm0
0x14000e97f  lea     rdx, [rsp+0B8h+var_78]
0x14000e984  xorps   xmm1, xmm1
0x14000e987  mov     rcx, rbx
0x14000e98a  movdqu  xmmword ptr [rsp+0B8h+var_78], xmm0
0x14000e990  movdqu  [rsp+0B8h+var_58], xmm1
0x14000e996  call    ?Get@?$SafeQueue@V?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@VWriteFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAA_NAEAV?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@@Z; appv::shared::kernel::SafeQueue<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::Get(kernel_std::shared_ptr<Streaming::WriteFault> &)
0x14000e99b  test    al, al
0x14000e99d  jz      short loc_14000E9BD
0x14000e99f  mov     rcx, [rsp+0B8h+var_78]; this
0x14000e9a4  call    ?Execute@StreamFault@Streaming@@QEAAJXZ; Streaming::StreamFault::Execute(void)
0x14000e9a9  lea     rdx, [rsp+0B8h+var_58+8]
0x14000e9ae  mov     [rsp+0B8h+var_78], r13
0x14000e9b3  lea     rcx, [rsp+0B8h+var_78+8]
0x14000e9b8  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x14000e9bd  mov     r14, [rsp+0B8h+var_78+8]
0x14000e9c2  test    r14, r14
0x14000e9c5  jz      short loc_14000E9FF
0x14000e9c7  or      eax, 0FFFFFFFFh
0x14000e9ca  lock xadd [r14+8], eax
0x14000e9d0  cmp     eax, esi
0x14000e9d2  jnz     short loc_14000E9FF
0x14000e9d4  mov     rax, [r14]
0x14000e9d7  mov     rcx, r14
0x14000e9da  mov     rax, [rax+8]
0x14000e9de  call    _guard_dispatch_icall
0x14000e9e3  or      eax, 0FFFFFFFFh
0x14000e9e6  lock xadd [r14+0Ch], eax
0x14000e9ec  cmp     eax, esi
0x14000e9ee  jnz     short loc_14000E9FF
0x14000e9f0  mov     rax, [r14]
0x14000e9f3  mov     rcx, r14
0x14000e9f6  mov     rax, [rax+10h]
0x14000e9fa  call    _guard_dispatch_icall
0x14000e9ff  lock dec dword ptr [rbx+0D0h]
0x14000ea06  mov     r14d, [rbx+0D4h]
0x14000ea0d  movzx   ebp, r13b
0x14000ea11  cmp     [rbx+70h], r13
0x14000ea15  jz      short loc_14000EA3C
0x14000ea17  call    cs:__imp_KeEnterCriticalRegion
0x14000ea1e  nop     dword ptr [rax+rax+00h]
0x14000ea23  mov     rcx, [rbx+70h]; Resource
0x14000ea27  mov     dl, sil; Wait
0x14000ea2a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000ea31  nop     dword ptr [rax+rax+00h]
0x14000ea36  cmp     al, sil
0x14000ea39  cmovz   ebp, esi
0x14000ea3c  mov     ecx, [rbx+5Ch]
0x14000ea3f  cmp     ecx, r14d
0x14000ea42  jbe     loc_14000EAD0
0x14000ea48  cmp     [rbx+60h], r13b
0x14000ea4c  jz      short loc_14000EA6B
0x14000ea4e  test    ecx, ecx
0x14000ea50  jz      short loc_14000EA6B
0x14000ea52  mov     r8, [rbx+40h]
0x14000ea56  mov     eax, r13d
0x14000ea59  mov     r14d, eax
0x14000ea5c  mov     rdx, [r8+r14*8]
0x14000ea60  cmp     r15, rdx
0x14000ea63  jz      short loc_14000EA9F
0x14000ea65  add     eax, esi
0x14000ea67  cmp     eax, ecx
0x14000ea69  jb      short loc_14000EA59
0x14000ea6b  mov     r14b, r13b
0x14000ea6e  test    bpl, bpl
0x14000ea71  jz      short loc_14000EA94
0x14000ea73  mov     rcx, [rbx+70h]; Resource
0x14000ea77  test    rcx, rcx
0x14000ea7a  jz      short loc_14000EA94
0x14000ea7c  call    cs:__imp_ExReleaseResourceLite
0x14000ea83  nop     dword ptr [rax+rax+00h]
0x14000ea88  call    cs:__imp_KeLeaveCriticalRegion
0x14000ea8f  nop     dword ptr [rax+rax+00h]
0x14000ea94  test    r14b, r14b
0x14000ea97  jnz     loc_14000EBB4
0x14000ea9d  jmp     short loc_14000EAF6
0x14000ea9f  mov     rcx, rdx; Object
0x14000eaa2  call    cs:__imp_ObfDereferenceObject
0x14000eaa9  nop     dword ptr [rax+rax+00h]
0x14000eaae  dec     dword ptr [rbx+5Ch]
0x14000eab1  mov     rcx, [rbx+40h]
0x14000eab5  mov     eax, [rbx+5Ch]
0x14000eab8  mov     rax, [rcx+rax*8]
0x14000eabc  mov     [rcx+r14*8], rax
0x14000eac0  mov     r14b, sil
0x14000eac3  mov     ecx, [rbx+5Ch]
0x14000eac6  mov     rax, [rbx+40h]
0x14000eaca  mov     [rax+rcx*8], r13
0x14000eace  jmp     short loc_14000EA6E
0x14000ead0  test    bpl, bpl
0x14000ead3  jz      short loc_14000EAF6
0x14000ead5  mov     rcx, [rbx+70h]; Resource
0x14000ead9  test    rcx, rcx
0x14000eadc  jz      short loc_14000EAF6
0x14000eade  call    cs:__imp_ExReleaseResourceLite
0x14000eae5  nop     dword ptr [rax+rax+00h]
0x14000eaea  call    cs:__imp_KeLeaveCriticalRegion
0x14000eaf1  nop     dword ptr [rax+rax+00h]
0x14000eaf6  cmp     r12d, esi
0x14000eaf9  jz      loc_14000E93B
0x14000eaff  cmp     r12d, 0C000009Ah
0x14000eb06  jz      loc_14000E93B
0x14000eb0c  movzx   edi, r13b
0x14000eb10  cmp     [rbx+70h], r13
0x14000eb14  jz      short loc_14000EB3B
0x14000eb16  call    cs:__imp_KeEnterCriticalRegion
0x14000eb1d  nop     dword ptr [rax+rax+00h]
0x14000eb22  mov     rcx, [rbx+70h]; Resource
0x14000eb26  mov     dl, sil; Wait
0x14000eb29  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000eb30  nop     dword ptr [rax+rax+00h]
0x14000eb35  cmp     al, sil
0x14000eb38  cmovz   edi, esi
0x14000eb3b  cmp     [rbx+60h], r13b
0x14000eb3f  jz      short loc_14000EB8E
0x14000eb41  mov     ecx, [rbx+5Ch]
0x14000eb44  test    ecx, ecx
0x14000eb46  jz      short loc_14000EB8E
0x14000eb48  mov     r8, [rbx+40h]
0x14000eb4c  mov     eax, r13d
0x14000eb4f  mov     ebp, eax
0x14000eb51  mov     rdx, [r8+rbp*8]
0x14000eb55  cmp     r15, rdx
0x14000eb58  jz      short loc_14000EB62
0x14000eb5a  add     eax, esi
0x14000eb5c  cmp     eax, ecx
0x14000eb5e  jb      short loc_14000EB4F
0x14000eb60  jmp     short loc_14000EB8E
0x14000eb62  mov     rcx, rdx; Object
0x14000eb65  call    cs:__imp_ObfDereferenceObject
0x14000eb6c  nop     dword ptr [rax+rax+00h]
0x14000eb71  dec     dword ptr [rbx+5Ch]
0x14000eb74  mov     rcx, [rbx+40h]
0x14000eb78  mov     eax, [rbx+5Ch]
0x14000eb7b  mov     rax, [rcx+rax*8]
0x14000eb7f  mov     [rcx+rbp*8], rax
0x14000eb83  mov     ecx, [rbx+5Ch]
0x14000eb86  mov     rax, [rbx+40h]
0x14000eb8a  mov     [rax+rcx*8], r13
0x14000eb8e  test    dil, dil
0x14000eb91  jz      short loc_14000EBB4
0x14000eb93  mov     rcx, [rbx+70h]; Resource
0x14000eb97  test    rcx, rcx
0x14000eb9a  jz      short loc_14000EBB4
0x14000eb9c  call    cs:__imp_ExReleaseResourceLite
0x14000eba3  nop     dword ptr [rax+rax+00h]
0x14000eba8  call    cs:__imp_KeLeaveCriticalRegion
0x14000ebaf  nop     dword ptr [rax+rax+00h]
0x14000ebb4  xor     eax, eax
0x14000ebb6  add     rsp, 78h
0x14000ebba  pop     r15
0x14000ebbc  pop     r14
0x14000ebbe  pop     r13
0x14000ebc0  pop     r12
0x14000ebc2  pop     rdi
0x14000ebc3  pop     rsi
0x14000ebc4  pop     rbp
0x14000ebc5  pop     rbx
0x14000ebc6  retn
```
