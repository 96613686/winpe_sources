# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>::Run(void)

- ea: `0x140006c08`
- end: `0x140006fd8`
- name: `?Run@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VPackageWriterTagInfo@Streaming@@@kernel@shared@appv@@AEAAJXZ`
- size: `976`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140007980`

## callees

- `0x140003bd8`
- `0x140003c58`
- `0x1400069b8`
- `0x140006c08`
- `0x14000f244`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006cb7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006cfc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006e98`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006efa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006fb8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006cb7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006cfc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006e98`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006efa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006fb8`
- `ntoskrnl!ObfReferenceObject` at `0x140006cc8`
- `ntoskrnl!ObfReferenceObject` at `0x140006cc8`
- `ntoskrnl!KeReleaseSemaphore` at `0x140006c3d`
- `ntoskrnl!KeReleaseSemaphore` at `0x140006d1a`
- `ntoskrnl!KeReleaseSemaphore` at `0x140006c3d`
- `ntoskrnl!KeReleaseSemaphore` at `0x140006d1a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006cab`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006cf0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006e8c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006eee`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006fac`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006cab`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006cf0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006e8c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006eee`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006fac`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140006c70`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140006e3a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140006f39`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140006c70`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140006e3a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140006f39`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140006d6e`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140006d6e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006c5d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006e27`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006f26`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006c5d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006e27`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006f26`
- `ntoskrnl!ObfDereferenceObject` at `0x140006eb2`
- `ntoskrnl!ObfDereferenceObject` at `0x140006f75`
- `ntoskrnl!ObfDereferenceObject` at `0x140006eb2`
- `ntoskrnl!ObfDereferenceObject` at `0x140006f75`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>::Run(
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
  volatile signed __int32 *v11; // r14
  unsigned int v12; // r14d
  bool v13; // bp
  unsigned int v14; // ecx
  __int64 v15; // r8
  unsigned int v16; // eax
  __int64 v17; // r14
  char v18; // r14
  struct _ERESOURCE *v19; // rcx
  struct _ERESOURCE *v20; // rcx
  bool v21; // di
  unsigned int v22; // ecx
  __int64 v23; // r8
  unsigned int v24; // eax
  __int64 v25; // rbp
  struct _ERESOURCE *v26; // rcx
  Streaming::StreamFaultWriter *v27[2]; // [rsp+40h] [rbp-78h] BYREF
  PVOID Object[2]; // [rsp+50h] [rbp-68h] BYREF
  __int128 v29; // [rsp+60h] [rbp-58h] BYREF

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
      && (v5 = appv::shared::kernel::ThreadHandles<Streaming::PackageWriterTagInfo>::ResizeNoLock(
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
        *(_OWORD *)v27 = 0;
        v29 = 0;
        if ( (unsigned __int8)appv::shared::kernel::SafeQueue<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::Get(
                                a1,
                                v27) )
        {
          Streaming::StreamFaultWriter::Execute(v27[0], v10);
          v27[0] = 0;
          kernel_std::detail::shared_count::operator=(&v27[1], (char *)&v29 + 8);
        }
        v11 = (volatile signed __int32 *)v27[1];
        if ( v27[1] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v27[1] + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
            if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 16LL))(v11);
          }
        }
      }
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 208));
      v12 = *(_DWORD *)(a1 + 212);
      v13 = 0;
      if ( *(_QWORD *)(a1 + 112) )
      {
        KeEnterCriticalRegion();
        v13 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 112), 1u) == 1;
      }
      v14 = *(_DWORD *)(a1 + 92);
      if ( v14 <= v12 )
      {
        if ( v13 )
        {
          v20 = *(struct _ERESOURCE **)(a1 + 112);
          if ( v20 )
          {
            ExReleaseResourceLite(v20);
            KeLeaveCriticalRegion();
          }
        }
      }
      else
      {
        if ( *(_BYTE *)(a1 + 96) && v14 )
        {
          v15 = *(_QWORD *)(a1 + 64);
          v16 = 0;
          while ( 1 )
          {
            v17 = v16;
            if ( CurrentThread == *(struct _KTHREAD **)(v15 + 8LL * v16) )
              break;
            if ( ++v16 >= v14 )
              goto LABEL_32;
          }
          ObfDereferenceObject(*(PVOID *)(v15 + 8LL * v16));
          *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8 * v17) = *(_QWORD *)(*(_QWORD *)(a1 + 64)
                                                                  + 8LL * (unsigned int)--*(_DWORD *)(a1 + 92));
          v18 = 1;
          *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL * *(unsigned int *)(a1 + 92)) = 0;
        }
        else
        {
LABEL_32:
          v18 = 0;
        }
        if ( v13 )
        {
          v19 = *(struct _ERESOURCE **)(a1 + 112);
          if ( v19 )
          {
            ExReleaseResourceLite(v19);
            KeLeaveCriticalRegion();
          }
        }
        if ( v18 )
          return 0;
      }
    }
    while ( v9 == 1 || v9 == -1073741670 );
    v21 = 0;
    if ( *(_QWORD *)(a1 + 112) )
    {
      KeEnterCriticalRegion();
      v21 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 112), 1u) == 1;
    }
    if ( *(_BYTE *)(a1 + 96) )
    {
      v22 = *(_DWORD *)(a1 + 92);
      if ( v22 )
      {
        v23 = *(_QWORD *)(a1 + 64);
        v24 = 0;
        while ( 1 )
        {
          v25 = v24;
          if ( CurrentThread == *(struct _KTHREAD **)(v23 + 8LL * v24) )
            break;
          if ( ++v24 >= v22 )
            goto LABEL_53;
        }
        ObfDereferenceObject(*(PVOID *)(v23 + 8LL * v24));
        *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8 * v25) = *(_QWORD *)(*(_QWORD *)(a1 + 64)
                                                                + 8LL * (unsigned int)--*(_DWORD *)(a1 + 92));
        *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL * *(unsigned int *)(a1 + 92)) = 0;
      }
    }
LABEL_53:
    if ( v21 )
    {
      v26 = *(struct _ERESOURCE **)(a1 + 112);
      if ( v26 )
      {
        ExReleaseResourceLite(v26);
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
0x140006c08  push    rbx
0x140006c0a  push    rbp
0x140006c0b  push    rsi
0x140006c0c  push    rdi
0x140006c0d  push    r12
0x140006c0f  push    r13
0x140006c11  push    r14
0x140006c13  push    r15
0x140006c15  sub     rsp, 78h
0x140006c19  mov     r15, gs:188h
0x140006c22  xor     r13d, r13d
0x140006c25  mov     rbx, rcx
0x140006c28  test    r15, r15
0x140006c2b  jnz     short loc_140006C4E
0x140006c2d  add     rcx, 0B0h; Semaphore
0x140006c34  lea     r8d, [r13+1]; Adjustment
0x140006c38  xor     r9d, r9d; Wait
0x140006c3b  xor     edx, edx; Increment
0x140006c3d  call    cs:__imp_KeReleaseSemaphore
0x140006c44  nop     dword ptr [rax+rax+00h]
0x140006c49  jmp     loc_140006FC4
0x140006c4e  mov     esi, 1
0x140006c53  movzx   ebp, r13b
0x140006c57  cmp     [rcx+70h], r13
0x140006c5b  jz      short loc_140006C82
0x140006c5d  call    cs:__imp_KeEnterCriticalRegion
0x140006c64  nop     dword ptr [rax+rax+00h]
0x140006c69  mov     rcx, [rbx+70h]; Resource
0x140006c6d  mov     dl, sil; Wait
0x140006c70  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140006c77  nop     dword ptr [rax+rax+00h]
0x140006c7c  cmp     al, sil
0x140006c7f  cmovz   ebp, esi
0x140006c82  mov     edx, [rbx+58h]
0x140006c85  cmp     [rbx+5Ch], edx
0x140006c88  jnz     short loc_140006CC5
0x140006c8a  add     edx, 0Ah
0x140006c8d  lea     rcx, [rbx+38h]
0x140006c91  call    ?ResizeNoLock@?$ThreadHandles@VPackageWriterTagInfo@Streaming@@@kernel@shared@appv@@AEAAJK@Z; appv::shared::kernel::ThreadHandles<Streaming::PackageWriterTagInfo>::ResizeNoLock(ulong)
0x140006c96  mov     r14d, eax
0x140006c99  test    eax, eax
0x140006c9b  jns     short loc_140006CC5
0x140006c9d  test    bpl, bpl
0x140006ca0  jz      short loc_140006D0B
0x140006ca2  mov     rcx, [rbx+70h]; Resource
0x140006ca6  test    rcx, rcx
0x140006ca9  jz      short loc_140006D0B
0x140006cab  call    cs:__imp_ExReleaseResourceLite
0x140006cb2  nop     dword ptr [rax+rax+00h]
0x140006cb7  call    cs:__imp_KeLeaveCriticalRegion
0x140006cbe  nop     dword ptr [rax+rax+00h]
0x140006cc3  jmp     short loc_140006D0B
0x140006cc5  mov     rcx, r15; Object
0x140006cc8  call    cs:__imp_ObfReferenceObject
0x140006ccf  nop     dword ptr [rax+rax+00h]
0x140006cd4  mov     ecx, [rbx+5Ch]
0x140006cd7  mov     rax, [rbx+40h]
0x140006cdb  mov     [rax+rcx*8], r15
0x140006cdf  add     [rbx+5Ch], esi
0x140006ce2  test    bpl, bpl
0x140006ce5  jz      short loc_140006D08
0x140006ce7  mov     rcx, [rbx+70h]; Resource
0x140006ceb  test    rcx, rcx
0x140006cee  jz      short loc_140006D08
0x140006cf0  call    cs:__imp_ExReleaseResourceLite
0x140006cf7  nop     dword ptr [rax+rax+00h]
0x140006cfc  call    cs:__imp_KeLeaveCriticalRegion
0x140006d03  nop     dword ptr [rax+rax+00h]
0x140006d08  mov     r14d, r13d
0x140006d0b  lea     rcx, [rbx+0B0h]; Semaphore
0x140006d12  xor     r9d, r9d; Wait
0x140006d15  mov     r8d, esi; Adjustment
0x140006d18  xor     edx, edx; Increment
0x140006d1a  call    cs:__imp_KeReleaseSemaphore
0x140006d21  nop     dword ptr [rax+rax+00h]
0x140006d26  test    r14d, r14d
0x140006d29  jns     short loc_140006D33
0x140006d2b  mov     eax, r14d
0x140006d2e  jmp     loc_140006FC6
0x140006d33  mov     rax, [rbx+80h]
0x140006d3a  mov     [rsp+0B8h+Object], rax
0x140006d3f  lea     rax, [rbx+90h]
0x140006d46  mov     [rsp+0B8h+var_60], rax
0x140006d4b  mov     [rsp+0B8h+WaitBlockArray], r13; WaitBlockArray
0x140006d50  lea     rdx, [rsp+0B8h+Object]; Object
0x140006d55  xor     r9d, r9d; WaitReason
0x140006d58  mov     [rsp+0B8h+Timeout], r13; Timeout
0x140006d5d  mov     [rsp+0B8h+Alertable], r13b; Alertable
0x140006d62  mov     r8d, esi; WaitType
0x140006d65  mov     [rsp+0B8h+WaitMode], r13b; WaitMode
0x140006d6a  lea     ecx, [r9+2]; Count
0x140006d6e  call    cs:__imp_KeWaitForMultipleObjects
0x140006d75  nop     dword ptr [rax+rax+00h]
0x140006d7a  mov     r12d, eax
0x140006d7d  lock add [rbx+0D0h], esi
0x140006d84  cmp     eax, esi
0x140006d86  jnz     loc_140006E0F
0x140006d8c  xorps   xmm0, xmm0
0x140006d8f  lea     rdx, [rsp+0B8h+var_78]
0x140006d94  xorps   xmm1, xmm1
0x140006d97  mov     rcx, rbx
0x140006d9a  movdqu  xmmword ptr [rsp+0B8h+var_78], xmm0
0x140006da0  movdqu  [rsp+0B8h+var_58], xmm1
0x140006da6  call    ?Get@?$SafeQueue@V?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@VWriteFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAA_NAEAV?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@@Z; appv::shared::kernel::SafeQueue<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::Get(kernel_std::shared_ptr<Streaming::WriteFault> &)
0x140006dab  test    al, al
0x140006dad  jz      short loc_140006DCD
0x140006daf  mov     rcx, [rsp+0B8h+var_78]; this
0x140006db4  call    ?Execute@StreamFaultWriter@Streaming@@QEAAJXZ; Streaming::StreamFaultWriter::Execute(void)
0x140006db9  lea     rdx, [rsp+0B8h+var_58+8]
0x140006dbe  mov     [rsp+0B8h+var_78], r13
0x140006dc3  lea     rcx, [rsp+0B8h+var_78+8]
0x140006dc8  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x140006dcd  mov     r14, [rsp+0B8h+var_78+8]
0x140006dd2  test    r14, r14
0x140006dd5  jz      short loc_140006E0F
0x140006dd7  or      eax, 0FFFFFFFFh
0x140006dda  lock xadd [r14+8], eax
0x140006de0  cmp     eax, esi
0x140006de2  jnz     short loc_140006E0F
0x140006de4  mov     rax, [r14]
0x140006de7  mov     rcx, r14
0x140006dea  mov     rax, [rax+8]
0x140006dee  call    _guard_dispatch_icall
0x140006df3  or      eax, 0FFFFFFFFh
0x140006df6  lock xadd [r14+0Ch], eax
0x140006dfc  cmp     eax, esi
0x140006dfe  jnz     short loc_140006E0F
0x140006e00  mov     rax, [r14]
0x140006e03  mov     rcx, r14
0x140006e06  mov     rax, [rax+10h]
0x140006e0a  call    _guard_dispatch_icall
0x140006e0f  lock dec dword ptr [rbx+0D0h]
0x140006e16  mov     r14d, [rbx+0D4h]
0x140006e1d  movzx   ebp, r13b
0x140006e21  cmp     [rbx+70h], r13
0x140006e25  jz      short loc_140006E4C
0x140006e27  call    cs:__imp_KeEnterCriticalRegion
0x140006e2e  nop     dword ptr [rax+rax+00h]
0x140006e33  mov     rcx, [rbx+70h]; Resource
0x140006e37  mov     dl, sil; Wait
0x140006e3a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140006e41  nop     dword ptr [rax+rax+00h]
0x140006e46  cmp     al, sil
0x140006e49  cmovz   ebp, esi
0x140006e4c  mov     ecx, [rbx+5Ch]
0x140006e4f  cmp     ecx, r14d
0x140006e52  jbe     loc_140006EE0
0x140006e58  cmp     [rbx+60h], r13b
0x140006e5c  jz      short loc_140006E7B
0x140006e5e  test    ecx, ecx
0x140006e60  jz      short loc_140006E7B
0x140006e62  mov     r8, [rbx+40h]
0x140006e66  mov     eax, r13d
0x140006e69  mov     r14d, eax
0x140006e6c  mov     rdx, [r8+r14*8]
0x140006e70  cmp     r15, rdx
0x140006e73  jz      short loc_140006EAF
0x140006e75  add     eax, esi
0x140006e77  cmp     eax, ecx
0x140006e79  jb      short loc_140006E69
0x140006e7b  mov     r14b, r13b
0x140006e7e  test    bpl, bpl
0x140006e81  jz      short loc_140006EA4
0x140006e83  mov     rcx, [rbx+70h]; Resource
0x140006e87  test    rcx, rcx
0x140006e8a  jz      short loc_140006EA4
0x140006e8c  call    cs:__imp_ExReleaseResourceLite
0x140006e93  nop     dword ptr [rax+rax+00h]
0x140006e98  call    cs:__imp_KeLeaveCriticalRegion
0x140006e9f  nop     dword ptr [rax+rax+00h]
0x140006ea4  test    r14b, r14b
0x140006ea7  jnz     loc_140006FC4
0x140006ead  jmp     short loc_140006F06
0x140006eaf  mov     rcx, rdx; Object
0x140006eb2  call    cs:__imp_ObfDereferenceObject
0x140006eb9  nop     dword ptr [rax+rax+00h]
0x140006ebe  dec     dword ptr [rbx+5Ch]
0x140006ec1  mov     rcx, [rbx+40h]
0x140006ec5  mov     eax, [rbx+5Ch]
0x140006ec8  mov     rax, [rcx+rax*8]
0x140006ecc  mov     [rcx+r14*8], rax
0x140006ed0  mov     r14b, sil
0x140006ed3  mov     ecx, [rbx+5Ch]
0x140006ed6  mov     rax, [rbx+40h]
0x140006eda  mov     [rax+rcx*8], r13
0x140006ede  jmp     short loc_140006E7E
0x140006ee0  test    bpl, bpl
0x140006ee3  jz      short loc_140006F06
0x140006ee5  mov     rcx, [rbx+70h]; Resource
0x140006ee9  test    rcx, rcx
0x140006eec  jz      short loc_140006F06
0x140006eee  call    cs:__imp_ExReleaseResourceLite
0x140006ef5  nop     dword ptr [rax+rax+00h]
0x140006efa  call    cs:__imp_KeLeaveCriticalRegion
0x140006f01  nop     dword ptr [rax+rax+00h]
0x140006f06  cmp     r12d, esi
0x140006f09  jz      loc_140006D4B
0x140006f0f  cmp     r12d, 0C000009Ah
0x140006f16  jz      loc_140006D4B
0x140006f1c  movzx   edi, r13b
0x140006f20  cmp     [rbx+70h], r13
0x140006f24  jz      short loc_140006F4B
0x140006f26  call    cs:__imp_KeEnterCriticalRegion
0x140006f2d  nop     dword ptr [rax+rax+00h]
0x140006f32  mov     rcx, [rbx+70h]; Resource
0x140006f36  mov     dl, sil; Wait
0x140006f39  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140006f40  nop     dword ptr [rax+rax+00h]
0x140006f45  cmp     al, sil
0x140006f48  cmovz   edi, esi
0x140006f4b  cmp     [rbx+60h], r13b
0x140006f4f  jz      short loc_140006F9E
0x140006f51  mov     ecx, [rbx+5Ch]
0x140006f54  test    ecx, ecx
0x140006f56  jz      short loc_140006F9E
0x140006f58  mov     r8, [rbx+40h]
0x140006f5c  mov     eax, r13d
0x140006f5f  mov     ebp, eax
0x140006f61  mov     rdx, [r8+rbp*8]
0x140006f65  cmp     r15, rdx
0x140006f68  jz      short loc_140006F72
0x140006f6a  add     eax, esi
0x140006f6c  cmp     eax, ecx
0x140006f6e  jb      short loc_140006F5F
0x140006f70  jmp     short loc_140006F9E
0x140006f72  mov     rcx, rdx; Object
0x140006f75  call    cs:__imp_ObfDereferenceObject
0x140006f7c  nop     dword ptr [rax+rax+00h]
0x140006f81  dec     dword ptr [rbx+5Ch]
0x140006f84  mov     rcx, [rbx+40h]
0x140006f88  mov     eax, [rbx+5Ch]
0x140006f8b  mov     rax, [rcx+rax*8]
0x140006f8f  mov     [rcx+rbp*8], rax
0x140006f93  mov     ecx, [rbx+5Ch]
0x140006f96  mov     rax, [rbx+40h]
0x140006f9a  mov     [rax+rcx*8], r13
0x140006f9e  test    dil, dil
0x140006fa1  jz      short loc_140006FC4
0x140006fa3  mov     rcx, [rbx+70h]; Resource
0x140006fa7  test    rcx, rcx
0x140006faa  jz      short loc_140006FC4
0x140006fac  call    cs:__imp_ExReleaseResourceLite
0x140006fb3  nop     dword ptr [rax+rax+00h]
0x140006fb8  call    cs:__imp_KeLeaveCriticalRegion
0x140006fbf  nop     dword ptr [rax+rax+00h]
0x140006fc4  xor     eax, eax
0x140006fc6  add     rsp, 78h
0x140006fca  pop     r15
0x140006fcc  pop     r14
0x140006fce  pop     r13
0x140006fd0  pop     r12
0x140006fd2  pop     rdi
0x140006fd3  pop     rsi
0x140006fd4  pop     rbp
0x140006fd5  pop     rbx
0x140006fd6  retn
```
