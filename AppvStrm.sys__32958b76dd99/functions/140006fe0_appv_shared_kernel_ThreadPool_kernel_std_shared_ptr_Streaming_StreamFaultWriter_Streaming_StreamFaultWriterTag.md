# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::Run(void)

- ea: `0x140006fe0`
- end: `0x1400073b0`
- name: `?Run@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@AEAAJXZ`
- size: `976`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400079a0`

## callees

- `0x140003bd8`
- `0x140003c58`
- `0x140006ae0`
- `0x140006fe0`
- `0x14000f244`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000708f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400070d4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007270`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400072d2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007390`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000708f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400070d4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007270`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400072d2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007390`
- `ntoskrnl!ObfReferenceObject` at `0x1400070a0`
- `ntoskrnl!ObfReferenceObject` at `0x1400070a0`
- `ntoskrnl!KeReleaseSemaphore` at `0x140007015`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400070f2`
- `ntoskrnl!KeReleaseSemaphore` at `0x140007015`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400070f2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140007083`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400070c8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140007264`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400072c6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140007384`
- `ntoskrnl!ExReleaseResourceLite` at `0x140007083`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400070c8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140007264`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400072c6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140007384`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140007048`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140007212`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140007311`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140007048`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140007212`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140007311`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140007146`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140007146`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140007035`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400071ff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400072fe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140007035`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400071ff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400072fe`
- `ntoskrnl!ObfDereferenceObject` at `0x14000728a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000734d`
- `ntoskrnl!ObfDereferenceObject` at `0x14000728a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000734d`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::Run(
        __int64 a1)
{
  struct _KTHREAD *CurrentThread; // r15
  bool v3; // bp
  int v4; // edx
  int v5; // r14d
  struct _ERESOURCE *v6; // rcx
  struct _ERESOURCE *v7; // rcx
  NTSTATUS v9; // r12d
  const wchar_t *v10; // rdx
  bool v11; // r8
  volatile signed __int32 *v12; // r14
  unsigned int v13; // r14d
  bool v14; // bp
  unsigned int v15; // ecx
  __int64 v16; // r8
  unsigned int v17; // eax
  __int64 v18; // r14
  char v19; // r14
  struct _ERESOURCE *v20; // rcx
  struct _ERESOURCE *v21; // rcx
  bool v22; // di
  unsigned int v23; // ecx
  __int64 v24; // r8
  unsigned int v25; // eax
  __int64 v26; // rbp
  struct _ERESOURCE *v27; // rcx
  Streaming::StreamFaultWriter *v28[2]; // [rsp+40h] [rbp-78h] BYREF
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
      && (v5 = appv::shared::kernel::ThreadHandles<Streaming::StreamFaultWriterTagInfo>::ResizeNoLock(
                 (unsigned int *)(a1 + 56),
                 v4 + 10),
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
        if ( appv::shared::kernel::SafeQueue<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::Get(
               a1,
               (__int64)v28) )
        {
          Streaming::StreamFaultWriter::Execute(v28[0], v10, v11);
          v28[0] = 0;
          kernel_std::detail::shared_count::operator=(
            (volatile signed __int32 **)&v28[1],
            (volatile signed __int32 **)&v30 + 1);
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
0x140006fe0  push    rbx
0x140006fe2  push    rbp
0x140006fe3  push    rsi
0x140006fe4  push    rdi
0x140006fe5  push    r12
0x140006fe7  push    r13
0x140006fe9  push    r14
0x140006feb  push    r15
0x140006fed  sub     rsp, 78h
0x140006ff1  mov     r15, gs:188h
0x140006ffa  xor     r13d, r13d
0x140006ffd  mov     rbx, rcx
0x140007000  test    r15, r15
0x140007003  jnz     short loc_140007026
0x140007005  add     rcx, 0B0h; Semaphore
0x14000700c  lea     r8d, [r13+1]; Adjustment
0x140007010  xor     r9d, r9d; Wait
0x140007013  xor     edx, edx; Increment
0x140007015  call    cs:__imp_KeReleaseSemaphore
0x14000701c  nop     dword ptr [rax+rax+00h]
0x140007021  jmp     loc_14000739C
0x140007026  mov     esi, 1
0x14000702b  movzx   ebp, r13b
0x14000702f  cmp     [rcx+70h], r13
0x140007033  jz      short loc_14000705A
0x140007035  call    cs:__imp_KeEnterCriticalRegion
0x14000703c  nop     dword ptr [rax+rax+00h]
0x140007041  mov     rcx, [rbx+70h]; Resource
0x140007045  mov     dl, sil; Wait
0x140007048  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000704f  nop     dword ptr [rax+rax+00h]
0x140007054  cmp     al, sil
0x140007057  cmovz   ebp, esi
0x14000705a  mov     edx, [rbx+58h]
0x14000705d  cmp     [rbx+5Ch], edx
0x140007060  jnz     short loc_14000709D
0x140007062  add     edx, 0Ah
0x140007065  lea     rcx, [rbx+38h]
0x140007069  call    ?ResizeNoLock@?$ThreadHandles@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@AEAAJK@Z; appv::shared::kernel::ThreadHandles<Streaming::StreamFaultWriterTagInfo>::ResizeNoLock(ulong)
0x14000706e  mov     r14d, eax
0x140007071  test    eax, eax
0x140007073  jns     short loc_14000709D
0x140007075  test    bpl, bpl
0x140007078  jz      short loc_1400070E3
0x14000707a  mov     rcx, [rbx+70h]; Resource
0x14000707e  test    rcx, rcx
0x140007081  jz      short loc_1400070E3
0x140007083  call    cs:__imp_ExReleaseResourceLite
0x14000708a  nop     dword ptr [rax+rax+00h]
0x14000708f  call    cs:__imp_KeLeaveCriticalRegion
0x140007096  nop     dword ptr [rax+rax+00h]
0x14000709b  jmp     short loc_1400070E3
0x14000709d  mov     rcx, r15; Object
0x1400070a0  call    cs:__imp_ObfReferenceObject
0x1400070a7  nop     dword ptr [rax+rax+00h]
0x1400070ac  mov     ecx, [rbx+5Ch]
0x1400070af  mov     rax, [rbx+40h]
0x1400070b3  mov     [rax+rcx*8], r15
0x1400070b7  add     [rbx+5Ch], esi
0x1400070ba  test    bpl, bpl
0x1400070bd  jz      short loc_1400070E0
0x1400070bf  mov     rcx, [rbx+70h]; Resource
0x1400070c3  test    rcx, rcx
0x1400070c6  jz      short loc_1400070E0
0x1400070c8  call    cs:__imp_ExReleaseResourceLite
0x1400070cf  nop     dword ptr [rax+rax+00h]
0x1400070d4  call    cs:__imp_KeLeaveCriticalRegion
0x1400070db  nop     dword ptr [rax+rax+00h]
0x1400070e0  mov     r14d, r13d
0x1400070e3  lea     rcx, [rbx+0B0h]; Semaphore
0x1400070ea  xor     r9d, r9d; Wait
0x1400070ed  mov     r8d, esi; Adjustment
0x1400070f0  xor     edx, edx; Increment
0x1400070f2  call    cs:__imp_KeReleaseSemaphore
0x1400070f9  nop     dword ptr [rax+rax+00h]
0x1400070fe  test    r14d, r14d
0x140007101  jns     short loc_14000710B
0x140007103  mov     eax, r14d
0x140007106  jmp     loc_14000739E
0x14000710b  mov     rax, [rbx+80h]
0x140007112  mov     [rsp+0B8h+Object], rax
0x140007117  lea     rax, [rbx+90h]
0x14000711e  mov     [rsp+0B8h+var_60], rax
0x140007123  mov     [rsp+0B8h+WaitBlockArray], r13; WaitBlockArray
0x140007128  lea     rdx, [rsp+0B8h+Object]; Object
0x14000712d  xor     r9d, r9d; WaitReason
0x140007130  mov     [rsp+0B8h+Timeout], r13; Timeout
0x140007135  mov     [rsp+0B8h+Alertable], r13b; Alertable
0x14000713a  mov     r8d, esi; WaitType
0x14000713d  mov     [rsp+0B8h+WaitMode], r13b; WaitMode
0x140007142  lea     ecx, [r9+2]; Count
0x140007146  call    cs:__imp_KeWaitForMultipleObjects
0x14000714d  nop     dword ptr [rax+rax+00h]
0x140007152  mov     r12d, eax
0x140007155  lock add [rbx+0D0h], esi
0x14000715c  cmp     eax, esi
0x14000715e  jnz     loc_1400071E7
0x140007164  xorps   xmm0, xmm0
0x140007167  lea     rdx, [rsp+0B8h+var_78]
0x14000716c  xorps   xmm1, xmm1
0x14000716f  mov     rcx, rbx
0x140007172  movdqu  xmmword ptr [rsp+0B8h+var_78], xmm0
0x140007178  movdqu  [rsp+0B8h+var_58], xmm1
0x14000717e  call    ?Get@?$SafeQueue@V?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@VWriteFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAA_NAEAV?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@@Z; appv::shared::kernel::SafeQueue<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::Get(kernel_std::shared_ptr<Streaming::WriteFault> &)
0x140007183  test    al, al
0x140007185  jz      short loc_1400071A5
0x140007187  mov     rcx, [rsp+0B8h+var_78]; this
0x14000718c  call    ?Execute@StreamFaultWriter@Streaming@@QEAAJXZ; Streaming::StreamFaultWriter::Execute(void)
0x140007191  lea     rdx, [rsp+0B8h+var_58+8]
0x140007196  mov     [rsp+0B8h+var_78], r13
0x14000719b  lea     rcx, [rsp+0B8h+var_78+8]
0x1400071a0  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x1400071a5  mov     r14, [rsp+0B8h+var_78+8]
0x1400071aa  test    r14, r14
0x1400071ad  jz      short loc_1400071E7
0x1400071af  or      eax, 0FFFFFFFFh
0x1400071b2  lock xadd [r14+8], eax
0x1400071b8  cmp     eax, esi
0x1400071ba  jnz     short loc_1400071E7
0x1400071bc  mov     rax, [r14]
0x1400071bf  mov     rcx, r14
0x1400071c2  mov     rax, [rax+8]
0x1400071c6  call    _guard_dispatch_icall
0x1400071cb  or      eax, 0FFFFFFFFh
0x1400071ce  lock xadd [r14+0Ch], eax
0x1400071d4  cmp     eax, esi
0x1400071d6  jnz     short loc_1400071E7
0x1400071d8  mov     rax, [r14]
0x1400071db  mov     rcx, r14
0x1400071de  mov     rax, [rax+10h]
0x1400071e2  call    _guard_dispatch_icall
0x1400071e7  lock dec dword ptr [rbx+0D0h]
0x1400071ee  mov     r14d, [rbx+0D4h]
0x1400071f5  movzx   ebp, r13b
0x1400071f9  cmp     [rbx+70h], r13
0x1400071fd  jz      short loc_140007224
0x1400071ff  call    cs:__imp_KeEnterCriticalRegion
0x140007206  nop     dword ptr [rax+rax+00h]
0x14000720b  mov     rcx, [rbx+70h]; Resource
0x14000720f  mov     dl, sil; Wait
0x140007212  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140007219  nop     dword ptr [rax+rax+00h]
0x14000721e  cmp     al, sil
0x140007221  cmovz   ebp, esi
0x140007224  mov     ecx, [rbx+5Ch]
0x140007227  cmp     ecx, r14d
0x14000722a  jbe     loc_1400072B8
0x140007230  cmp     [rbx+60h], r13b
0x140007234  jz      short loc_140007253
0x140007236  test    ecx, ecx
0x140007238  jz      short loc_140007253
0x14000723a  mov     r8, [rbx+40h]
0x14000723e  mov     eax, r13d
0x140007241  mov     r14d, eax
0x140007244  mov     rdx, [r8+r14*8]
0x140007248  cmp     r15, rdx
0x14000724b  jz      short loc_140007287
0x14000724d  add     eax, esi
0x14000724f  cmp     eax, ecx
0x140007251  jb      short loc_140007241
0x140007253  mov     r14b, r13b
0x140007256  test    bpl, bpl
0x140007259  jz      short loc_14000727C
0x14000725b  mov     rcx, [rbx+70h]; Resource
0x14000725f  test    rcx, rcx
0x140007262  jz      short loc_14000727C
0x140007264  call    cs:__imp_ExReleaseResourceLite
0x14000726b  nop     dword ptr [rax+rax+00h]
0x140007270  call    cs:__imp_KeLeaveCriticalRegion
0x140007277  nop     dword ptr [rax+rax+00h]
0x14000727c  test    r14b, r14b
0x14000727f  jnz     loc_14000739C
0x140007285  jmp     short loc_1400072DE
0x140007287  mov     rcx, rdx; Object
0x14000728a  call    cs:__imp_ObfDereferenceObject
0x140007291  nop     dword ptr [rax+rax+00h]
0x140007296  dec     dword ptr [rbx+5Ch]
0x140007299  mov     rcx, [rbx+40h]
0x14000729d  mov     eax, [rbx+5Ch]
0x1400072a0  mov     rax, [rcx+rax*8]
0x1400072a4  mov     [rcx+r14*8], rax
0x1400072a8  mov     r14b, sil
0x1400072ab  mov     ecx, [rbx+5Ch]
0x1400072ae  mov     rax, [rbx+40h]
0x1400072b2  mov     [rax+rcx*8], r13
0x1400072b6  jmp     short loc_140007256
0x1400072b8  test    bpl, bpl
0x1400072bb  jz      short loc_1400072DE
0x1400072bd  mov     rcx, [rbx+70h]; Resource
0x1400072c1  test    rcx, rcx
0x1400072c4  jz      short loc_1400072DE
0x1400072c6  call    cs:__imp_ExReleaseResourceLite
0x1400072cd  nop     dword ptr [rax+rax+00h]
0x1400072d2  call    cs:__imp_KeLeaveCriticalRegion
0x1400072d9  nop     dword ptr [rax+rax+00h]
0x1400072de  cmp     r12d, esi
0x1400072e1  jz      loc_140007123
0x1400072e7  cmp     r12d, 0C000009Ah
0x1400072ee  jz      loc_140007123
0x1400072f4  movzx   edi, r13b
0x1400072f8  cmp     [rbx+70h], r13
0x1400072fc  jz      short loc_140007323
0x1400072fe  call    cs:__imp_KeEnterCriticalRegion
0x140007305  nop     dword ptr [rax+rax+00h]
0x14000730a  mov     rcx, [rbx+70h]; Resource
0x14000730e  mov     dl, sil; Wait
0x140007311  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140007318  nop     dword ptr [rax+rax+00h]
0x14000731d  cmp     al, sil
0x140007320  cmovz   edi, esi
0x140007323  cmp     [rbx+60h], r13b
0x140007327  jz      short loc_140007376
0x140007329  mov     ecx, [rbx+5Ch]
0x14000732c  test    ecx, ecx
0x14000732e  jz      short loc_140007376
0x140007330  mov     r8, [rbx+40h]
0x140007334  mov     eax, r13d
0x140007337  mov     ebp, eax
0x140007339  mov     rdx, [r8+rbp*8]
0x14000733d  cmp     r15, rdx
0x140007340  jz      short loc_14000734A
0x140007342  add     eax, esi
0x140007344  cmp     eax, ecx
0x140007346  jb      short loc_140007337
0x140007348  jmp     short loc_140007376
0x14000734a  mov     rcx, rdx; Object
0x14000734d  call    cs:__imp_ObfDereferenceObject
0x140007354  nop     dword ptr [rax+rax+00h]
0x140007359  dec     dword ptr [rbx+5Ch]
0x14000735c  mov     rcx, [rbx+40h]
0x140007360  mov     eax, [rbx+5Ch]
0x140007363  mov     rax, [rcx+rax*8]
0x140007367  mov     [rcx+rbp*8], rax
0x14000736b  mov     ecx, [rbx+5Ch]
0x14000736e  mov     rax, [rbx+40h]
0x140007372  mov     [rax+rcx*8], r13
0x140007376  test    dil, dil
0x140007379  jz      short loc_14000739C
0x14000737b  mov     rcx, [rbx+70h]; Resource
0x14000737f  test    rcx, rcx
0x140007382  jz      short loc_14000739C
0x140007384  call    cs:__imp_ExReleaseResourceLite
0x14000738b  nop     dword ptr [rax+rax+00h]
0x140007390  call    cs:__imp_KeLeaveCriticalRegion
0x140007397  nop     dword ptr [rax+rax+00h]
0x14000739c  xor     eax, eax
0x14000739e  add     rsp, 78h
0x1400073a2  pop     r15
0x1400073a4  pop     r14
0x1400073a6  pop     r13
0x1400073a8  pop     r12
0x1400073aa  pop     rdi
0x1400073ab  pop     rsi
0x1400073ac  pop     rbp
0x1400073ad  pop     rbx
0x1400073ae  retn
```
