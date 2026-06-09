# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::Run(void)

- ea: `0x14000ebd0`
- end: `0x14000efb1`
- name: `?Run@?$ThreadPool@V?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@VWriteFaultTagInfo@Streaming@@@kernel@shared@appv@@AEAAJXZ`
- size: `993`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000efe0`

## callees

- `0x140003bd8`
- `0x140003c58`
- `0x14000e6d0`
- `0x14000ebd0`
- `0x140014dcc`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ec7e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ecc2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ee73`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000eed4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ef91`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ec7e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ecc2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ee73`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000eed4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ef91`
- `ntoskrnl!ObfReferenceObject` at `0x14000ec8f`
- `ntoskrnl!ObfReferenceObject` at `0x14000ec8f`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000ec05`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000ece0`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000ec05`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000ece0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ec72`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ecb6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ee67`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000eec8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ef85`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ec72`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ecb6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ee67`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000eec8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ef85`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000ec38`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000ee16`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000ef13`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000ec38`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000ee16`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000ef13`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14000ed34`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14000ed34`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ec25`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ee03`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ef00`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ec25`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ee03`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ef00`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ee8d`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ef4f`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ee8d`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ef4f`
- `FLTMGR!FltCompletePendedPreOperation` at `0x14000ed8b`
- `FLTMGR!FltCompletePendedPreOperation` at `0x14000ed8b`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::Run(
        __int64 a1)
{
  struct _KTHREAD *CurrentThread; // r15
  bool v3; // bl
  int v4; // edx
  int v5; // r14d
  struct _ERESOURCE *v6; // rcx
  struct _ERESOURCE *v7; // rcx
  NTSTATUS v9; // r12d
  Streaming::WriteFault *v10; // rbx
  enum _FLT_PREOP_CALLBACK_STATUS v11; // eax
  volatile signed __int32 *v12; // rbx
  unsigned int v13; // r14d
  bool v14; // bl
  unsigned int v15; // ecx
  __int64 v16; // r8
  unsigned int v17; // eax
  __int64 v18; // r14
  char v19; // r14
  struct _ERESOURCE *v20; // rcx
  struct _ERESOURCE *v21; // rcx
  bool v22; // bl
  unsigned int v23; // ecx
  __int64 v24; // r8
  unsigned int v25; // eax
  __int64 v26; // rsi
  struct _ERESOURCE *v27; // rcx
  Streaming::WriteFault *v28[2]; // [rsp+40h] [rbp-78h] BYREF
  PVOID Object[2]; // [rsp+50h] [rbp-68h] BYREF
  __int128 v30; // [rsp+60h] [rbp-58h] BYREF

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
      && (v5 = appv::shared::kernel::ThreadHandles<Streaming::WriteFaultTagInfo>::ResizeNoLock(
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
        *(_OWORD *)v28 = 0;
        v30 = 0;
        if ( (unsigned __int8)appv::shared::kernel::SafeQueue<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::Get(
                                a1,
                                v28) )
        {
          v10 = v28[0];
          v11 = Streaming::WriteFault::ProcessFault(v28[0]);
          FltCompletePendedPreOperation(*((PFLT_CALLBACK_DATA *)v10 + 1), v11, 0);
          v28[0] = 0;
          kernel_std::detail::shared_count::operator=(&v28[1], (char *)&v30 + 8);
        }
        v12 = (volatile signed __int32 *)v28[1];
        if ( v28[1] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v28[1] + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
            if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 16LL))(v12);
          }
        }
      }
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 208));
      v13 = *(_DWORD *)(a1 + 212);
      v14 = 0;
      if ( *(_QWORD *)(a1 + 112) )
      {
        KeEnterCriticalRegion();
        v14 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 112), 1u) == 1;
      }
      v15 = *(_DWORD *)(a1 + 92);
      if ( v15 <= v13 )
      {
        if ( v14 )
        {
          v21 = *(struct _ERESOURCE **)(a1 + 112);
          if ( v21 )
          {
            ExReleaseResourceLite(v21);
            KeLeaveCriticalRegion();
          }
        }
      }
      else
      {
        if ( *(_BYTE *)(a1 + 96) && v15 )
        {
          v16 = *(_QWORD *)(a1 + 64);
          v17 = 0;
          while ( 1 )
          {
            v18 = v17;
            if ( CurrentThread == *(struct _KTHREAD **)(v16 + 8LL * v17) )
              break;
            if ( ++v17 >= v15 )
              goto LABEL_32;
          }
          ObfDereferenceObject(*(PVOID *)(v16 + 8LL * v17));
          *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8 * v18) = *(_QWORD *)(*(_QWORD *)(a1 + 64)
                                                                  + 8LL * (unsigned int)--*(_DWORD *)(a1 + 92));
          v19 = 1;
          *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL * *(unsigned int *)(a1 + 92)) = 0;
        }
        else
        {
LABEL_32:
          v19 = 0;
        }
        if ( v14 )
        {
          v20 = *(struct _ERESOURCE **)(a1 + 112);
          if ( v20 )
          {
            ExReleaseResourceLite(v20);
            KeLeaveCriticalRegion();
          }
        }
        if ( v19 )
          return 0;
      }
    }
    while ( v9 == 1 || v9 == -1073741670 );
    v22 = 0;
    if ( *(_QWORD *)(a1 + 112) )
    {
      KeEnterCriticalRegion();
      v22 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 112), 1u) == 1;
    }
    if ( *(_BYTE *)(a1 + 96) )
    {
      v23 = *(_DWORD *)(a1 + 92);
      if ( v23 )
      {
        v24 = *(_QWORD *)(a1 + 64);
        v25 = 0;
        while ( 1 )
        {
          v26 = v25;
          if ( CurrentThread == *(struct _KTHREAD **)(v24 + 8LL * v25) )
            break;
          if ( ++v25 >= v23 )
            goto LABEL_53;
        }
        ObfDereferenceObject(*(PVOID *)(v24 + 8LL * v25));
        *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8 * v26) = *(_QWORD *)(*(_QWORD *)(a1 + 64)
                                                                + 8LL * (unsigned int)--*(_DWORD *)(a1 + 92));
        *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL * *(unsigned int *)(a1 + 92)) = 0;
      }
    }
LABEL_53:
    if ( v22 )
    {
      v27 = *(struct _ERESOURCE **)(a1 + 112);
      if ( v27 )
      {
        ExReleaseResourceLite(v27);
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
0x14000ebd0  push    rbx
0x14000ebd2  push    rbp
0x14000ebd3  push    rsi
0x14000ebd4  push    rdi
0x14000ebd5  push    r12
0x14000ebd7  push    r13
0x14000ebd9  push    r14
0x14000ebdb  push    r15
0x14000ebdd  sub     rsp, 78h
0x14000ebe1  mov     r15, gs:188h
0x14000ebea  xor     r13d, r13d
0x14000ebed  mov     rdi, rcx
0x14000ebf0  test    r15, r15
0x14000ebf3  jnz     short loc_14000EC16
0x14000ebf5  add     rcx, 0B0h; Semaphore
0x14000ebfc  lea     r8d, [r13+1]; Adjustment
0x14000ec00  xor     r9d, r9d; Wait
0x14000ec03  xor     edx, edx; Increment
0x14000ec05  call    cs:__imp_KeReleaseSemaphore
0x14000ec0c  nop     dword ptr [rax+rax+00h]
0x14000ec11  jmp     loc_14000EF9D
0x14000ec16  mov     ebp, 1
0x14000ec1b  movzx   ebx, r13b
0x14000ec1f  cmp     [rcx+70h], r13
0x14000ec23  jz      short loc_14000EC4A
0x14000ec25  call    cs:__imp_KeEnterCriticalRegion
0x14000ec2c  nop     dword ptr [rax+rax+00h]
0x14000ec31  mov     rcx, [rdi+70h]; Resource
0x14000ec35  mov     dl, bpl; Wait
0x14000ec38  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000ec3f  nop     dword ptr [rax+rax+00h]
0x14000ec44  cmp     al, bpl
0x14000ec47  cmovz   ebx, ebp
0x14000ec4a  mov     edx, [rdi+58h]
0x14000ec4d  cmp     [rdi+5Ch], edx
0x14000ec50  jnz     short loc_14000EC8C
0x14000ec52  add     edx, 0Ah
0x14000ec55  lea     rcx, [rdi+38h]
0x14000ec59  call    ?ResizeNoLock@?$ThreadHandles@VWriteFaultTagInfo@Streaming@@@kernel@shared@appv@@AEAAJK@Z; appv::shared::kernel::ThreadHandles<Streaming::WriteFaultTagInfo>::ResizeNoLock(ulong)
0x14000ec5e  mov     r14d, eax
0x14000ec61  test    eax, eax
0x14000ec63  jns     short loc_14000EC8C
0x14000ec65  test    bl, bl
0x14000ec67  jz      short loc_14000ECD1
0x14000ec69  mov     rcx, [rdi+70h]; Resource
0x14000ec6d  test    rcx, rcx
0x14000ec70  jz      short loc_14000ECD1
0x14000ec72  call    cs:__imp_ExReleaseResourceLite
0x14000ec79  nop     dword ptr [rax+rax+00h]
0x14000ec7e  call    cs:__imp_KeLeaveCriticalRegion
0x14000ec85  nop     dword ptr [rax+rax+00h]
0x14000ec8a  jmp     short loc_14000ECD1
0x14000ec8c  mov     rcx, r15; Object
0x14000ec8f  call    cs:__imp_ObfReferenceObject
0x14000ec96  nop     dword ptr [rax+rax+00h]
0x14000ec9b  mov     ecx, [rdi+5Ch]
0x14000ec9e  mov     rax, [rdi+40h]
0x14000eca2  mov     [rax+rcx*8], r15
0x14000eca6  add     [rdi+5Ch], ebp
0x14000eca9  test    bl, bl
0x14000ecab  jz      short loc_14000ECCE
0x14000ecad  mov     rcx, [rdi+70h]; Resource
0x14000ecb1  test    rcx, rcx
0x14000ecb4  jz      short loc_14000ECCE
0x14000ecb6  call    cs:__imp_ExReleaseResourceLite
0x14000ecbd  nop     dword ptr [rax+rax+00h]
0x14000ecc2  call    cs:__imp_KeLeaveCriticalRegion
0x14000ecc9  nop     dword ptr [rax+rax+00h]
0x14000ecce  mov     r14d, r13d
0x14000ecd1  lea     rcx, [rdi+0B0h]; Semaphore
0x14000ecd8  xor     r9d, r9d; Wait
0x14000ecdb  mov     r8d, ebp; Adjustment
0x14000ecde  xor     edx, edx; Increment
0x14000ece0  call    cs:__imp_KeReleaseSemaphore
0x14000ece7  nop     dword ptr [rax+rax+00h]
0x14000ecec  test    r14d, r14d
0x14000ecef  jns     short loc_14000ECF9
0x14000ecf1  mov     eax, r14d
0x14000ecf4  jmp     loc_14000EF9F
0x14000ecf9  mov     rax, [rdi+80h]
0x14000ed00  mov     [rsp+0B8h+Object], rax
0x14000ed05  lea     rax, [rdi+90h]
0x14000ed0c  mov     [rsp+0B8h+var_60], rax
0x14000ed11  mov     [rsp+0B8h+WaitBlockArray], r13; WaitBlockArray
0x14000ed16  lea     rdx, [rsp+0B8h+Object]; Object
0x14000ed1b  xor     r9d, r9d; WaitReason
0x14000ed1e  mov     [rsp+0B8h+Timeout], r13; Timeout
0x14000ed23  mov     [rsp+0B8h+Alertable], r13b; Alertable
0x14000ed28  mov     r8d, ebp; WaitType
0x14000ed2b  mov     [rsp+0B8h+WaitMode], r13b; WaitMode
0x14000ed30  lea     ecx, [r9+2]; Count
0x14000ed34  call    cs:__imp_KeWaitForMultipleObjects
0x14000ed3b  nop     dword ptr [rax+rax+00h]
0x14000ed40  mov     r12d, eax
0x14000ed43  lock add [rdi+0D0h], ebp
0x14000ed4a  cmp     eax, ebp
0x14000ed4c  jnz     loc_14000EDEB
0x14000ed52  xorps   xmm0, xmm0
0x14000ed55  lea     rdx, [rsp+0B8h+var_78]
0x14000ed5a  xorps   xmm1, xmm1
0x14000ed5d  mov     rcx, rdi
0x14000ed60  movdqu  xmmword ptr [rsp+0B8h+var_78], xmm0
0x14000ed66  movdqu  [rsp+0B8h+var_58], xmm1
0x14000ed6c  call    ?Get@?$SafeQueue@V?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@VWriteFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAA_NAEAV?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@@Z; appv::shared::kernel::SafeQueue<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::Get(kernel_std::shared_ptr<Streaming::WriteFault> &)
0x14000ed71  test    al, al
0x14000ed73  jz      short loc_14000EDAB
0x14000ed75  mov     rbx, [rsp+0B8h+var_78]
0x14000ed7a  mov     rcx, rbx; this
0x14000ed7d  call    ?ProcessFault@WriteFault@Streaming@@QEAA?AW4_FLT_PREOP_CALLBACK_STATUS@@XZ; Streaming::WriteFault::ProcessFault(void)
0x14000ed82  mov     rcx, [rbx+8]; CallbackData
0x14000ed86  xor     r8d, r8d; Context
0x14000ed89  mov     edx, eax; CallbackStatus
0x14000ed8b  call    cs:__imp_FltCompletePendedPreOperation
0x14000ed92  nop     dword ptr [rax+rax+00h]
0x14000ed97  lea     rdx, [rsp+0B8h+var_58+8]
0x14000ed9c  mov     [rsp+0B8h+var_78], r13
0x14000eda1  lea     rcx, [rsp+0B8h+var_78+8]
0x14000eda6  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x14000edab  mov     rbx, [rsp+0B8h+var_78+8]
0x14000edb0  test    rbx, rbx
0x14000edb3  jz      short loc_14000EDEB
0x14000edb5  or      eax, 0FFFFFFFFh
0x14000edb8  lock xadd [rbx+8], eax
0x14000edbd  cmp     eax, ebp
0x14000edbf  jnz     short loc_14000EDEB
0x14000edc1  mov     rax, [rbx]
0x14000edc4  mov     rcx, rbx
0x14000edc7  mov     rax, [rax+8]
0x14000edcb  call    _guard_dispatch_icall
0x14000edd0  or      eax, 0FFFFFFFFh
0x14000edd3  lock xadd [rbx+0Ch], eax
0x14000edd8  cmp     eax, ebp
0x14000edda  jnz     short loc_14000EDEB
0x14000eddc  mov     rax, [rbx]
0x14000eddf  mov     rcx, rbx
0x14000ede2  mov     rax, [rax+10h]
0x14000ede6  call    _guard_dispatch_icall
0x14000edeb  lock dec dword ptr [rdi+0D0h]
0x14000edf2  mov     r14d, [rdi+0D4h]
0x14000edf9  movzx   ebx, r13b
0x14000edfd  cmp     [rdi+70h], r13
0x14000ee01  jz      short loc_14000EE28
0x14000ee03  call    cs:__imp_KeEnterCriticalRegion
0x14000ee0a  nop     dword ptr [rax+rax+00h]
0x14000ee0f  mov     rcx, [rdi+70h]; Resource
0x14000ee13  mov     dl, bpl; Wait
0x14000ee16  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000ee1d  nop     dword ptr [rax+rax+00h]
0x14000ee22  cmp     al, bpl
0x14000ee25  cmovz   ebx, ebp
0x14000ee28  mov     ecx, [rdi+5Ch]
0x14000ee2b  cmp     ecx, r14d
0x14000ee2e  jbe     loc_14000EEBB
0x14000ee34  cmp     [rdi+60h], r13b
0x14000ee38  jz      short loc_14000EE57
0x14000ee3a  test    ecx, ecx
0x14000ee3c  jz      short loc_14000EE57
0x14000ee3e  mov     r8, [rdi+40h]
0x14000ee42  mov     eax, r13d
0x14000ee45  mov     r14d, eax
0x14000ee48  mov     rdx, [r8+r14*8]
0x14000ee4c  cmp     r15, rdx
0x14000ee4f  jz      short loc_14000EE8A
0x14000ee51  add     eax, ebp
0x14000ee53  cmp     eax, ecx
0x14000ee55  jb      short loc_14000EE45
0x14000ee57  mov     r14b, r13b
0x14000ee5a  test    bl, bl
0x14000ee5c  jz      short loc_14000EE7F
0x14000ee5e  mov     rcx, [rdi+70h]; Resource
0x14000ee62  test    rcx, rcx
0x14000ee65  jz      short loc_14000EE7F
0x14000ee67  call    cs:__imp_ExReleaseResourceLite
0x14000ee6e  nop     dword ptr [rax+rax+00h]
0x14000ee73  call    cs:__imp_KeLeaveCriticalRegion
0x14000ee7a  nop     dword ptr [rax+rax+00h]
0x14000ee7f  test    r14b, r14b
0x14000ee82  jnz     loc_14000EF9D
0x14000ee88  jmp     short loc_14000EEE0
0x14000ee8a  mov     rcx, rdx; Object
0x14000ee8d  call    cs:__imp_ObfDereferenceObject
0x14000ee94  nop     dword ptr [rax+rax+00h]
0x14000ee99  dec     dword ptr [rdi+5Ch]
0x14000ee9c  mov     rcx, [rdi+40h]
0x14000eea0  mov     eax, [rdi+5Ch]
0x14000eea3  mov     rax, [rcx+rax*8]
0x14000eea7  mov     [rcx+r14*8], rax
0x14000eeab  mov     r14b, bpl
0x14000eeae  mov     ecx, [rdi+5Ch]
0x14000eeb1  mov     rax, [rdi+40h]
0x14000eeb5  mov     [rax+rcx*8], r13
0x14000eeb9  jmp     short loc_14000EE5A
0x14000eebb  test    bl, bl
0x14000eebd  jz      short loc_14000EEE0
0x14000eebf  mov     rcx, [rdi+70h]; Resource
0x14000eec3  test    rcx, rcx
0x14000eec6  jz      short loc_14000EEE0
0x14000eec8  call    cs:__imp_ExReleaseResourceLite
0x14000eecf  nop     dword ptr [rax+rax+00h]
0x14000eed4  call    cs:__imp_KeLeaveCriticalRegion
0x14000eedb  nop     dword ptr [rax+rax+00h]
0x14000eee0  cmp     r12d, ebp
0x14000eee3  jz      loc_14000ED11
0x14000eee9  cmp     r12d, 0C000009Ah
0x14000eef0  jz      loc_14000ED11
0x14000eef6  movzx   ebx, r13b
0x14000eefa  cmp     [rdi+70h], r13
0x14000eefe  jz      short loc_14000EF25
0x14000ef00  call    cs:__imp_KeEnterCriticalRegion
0x14000ef07  nop     dword ptr [rax+rax+00h]
0x14000ef0c  mov     rcx, [rdi+70h]; Resource
0x14000ef10  mov     dl, bpl; Wait
0x14000ef13  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000ef1a  nop     dword ptr [rax+rax+00h]
0x14000ef1f  cmp     al, bpl
0x14000ef22  cmovz   ebx, ebp
0x14000ef25  cmp     [rdi+60h], r13b
0x14000ef29  jz      short loc_14000EF78
0x14000ef2b  mov     ecx, [rdi+5Ch]
0x14000ef2e  test    ecx, ecx
0x14000ef30  jz      short loc_14000EF78
0x14000ef32  mov     r8, [rdi+40h]
0x14000ef36  mov     eax, r13d
0x14000ef39  mov     esi, eax
0x14000ef3b  mov     rdx, [r8+rsi*8]
0x14000ef3f  cmp     r15, rdx
0x14000ef42  jz      short loc_14000EF4C
0x14000ef44  add     eax, ebp
0x14000ef46  cmp     eax, ecx
0x14000ef48  jb      short loc_14000EF39
0x14000ef4a  jmp     short loc_14000EF78
0x14000ef4c  mov     rcx, rdx; Object
0x14000ef4f  call    cs:__imp_ObfDereferenceObject
0x14000ef56  nop     dword ptr [rax+rax+00h]
0x14000ef5b  dec     dword ptr [rdi+5Ch]
0x14000ef5e  mov     rcx, [rdi+40h]
0x14000ef62  mov     eax, [rdi+5Ch]
0x14000ef65  mov     rax, [rcx+rax*8]
0x14000ef69  mov     [rcx+rsi*8], rax
0x14000ef6d  mov     ecx, [rdi+5Ch]
0x14000ef70  mov     rax, [rdi+40h]
0x14000ef74  mov     [rax+rcx*8], r13
0x14000ef78  test    bl, bl
0x14000ef7a  jz      short loc_14000EF9D
0x14000ef7c  mov     rcx, [rdi+70h]; Resource
0x14000ef80  test    rcx, rcx
0x14000ef83  jz      short loc_14000EF9D
0x14000ef85  call    cs:__imp_ExReleaseResourceLite
0x14000ef8c  nop     dword ptr [rax+rax+00h]
0x14000ef91  call    cs:__imp_KeLeaveCriticalRegion
0x14000ef98  nop     dword ptr [rax+rax+00h]
0x14000ef9d  xor     eax, eax
0x14000ef9f  add     rsp, 78h
0x14000efa3  pop     r15
0x14000efa5  pop     r14
0x14000efa7  pop     r13
0x14000efa9  pop     r12
0x14000efab  pop     rdi
0x14000efac  pop     rsi
0x14000efad  pop     rbp
0x14000efae  pop     rbx
0x14000efaf  retn
```
