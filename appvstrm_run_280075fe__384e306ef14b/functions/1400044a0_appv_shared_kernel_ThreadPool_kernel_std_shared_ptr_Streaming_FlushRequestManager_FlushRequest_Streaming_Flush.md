# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::Run(void)

- ea: `0x1400044a0`
- end: `0x1400048a1`
- name: `?Run@?$ThreadPool@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@VFlushRequestTagInfo@Streaming@@@kernel@shared@appv@@AEAAJXZ`
- size: `1025`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140004aa0`

## callees

- `0x140003bd8`
- `0x140003c58`
- `0x140004378`
- `0x1400044a0`
- `0x14000b448`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000454f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140004594`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140004761`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400047c3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140004881`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000454f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140004594`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140004761`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400047c3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140004881`
- `ntoskrnl!ObfReferenceObject` at `0x140004560`
- `ntoskrnl!ObfReferenceObject` at `0x140004560`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400044d5`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400045b2`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400044d5`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400045b2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140004543`
- `ntoskrnl!ExReleaseResourceLite` at `0x140004588`
- `ntoskrnl!ExReleaseResourceLite` at `0x140004755`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400047b7`
- `ntoskrnl!ExReleaseResourceLite` at `0x140004875`
- `ntoskrnl!ExReleaseResourceLite` at `0x140004543`
- `ntoskrnl!ExReleaseResourceLite` at `0x140004588`
- `ntoskrnl!ExReleaseResourceLite` at `0x140004755`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400047b7`
- `ntoskrnl!ExReleaseResourceLite` at `0x140004875`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140004508`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140004703`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140004802`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140004508`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140004703`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140004802`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140004606`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140004606`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400044f5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400046f0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400047ef`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400044f5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400046f0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400047ef`
- `ntoskrnl!ObfDereferenceObject` at `0x14000477b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000483e`
- `ntoskrnl!ObfDereferenceObject` at `0x14000477b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000483e`
- `FLTMGR!FltFlushBuffers` at `0x140004660`
- `FLTMGR!FltFlushBuffers` at `0x140004660`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::Run(
        __int64 a1)
{
  struct _KTHREAD *CurrentThread; // r12
  bool v3; // bp
  int v4; // edx
  int v5; // r14d
  struct _ERESOURCE *v6; // rcx
  struct _ERESOURCE *v7; // rcx
  NTSTATUS v9; // r13d
  __int64 v10; // r14
  struct _FILE_OBJECT *v11; // rbp
  struct _FLT_INSTANCE *v12; // r15
  volatile signed __int32 *v13; // r14
  unsigned int v14; // r14d
  bool v15; // bp
  unsigned int v16; // ecx
  __int64 v17; // r8
  unsigned int v18; // eax
  __int64 v19; // r14
  char v20; // r14
  struct _ERESOURCE *v21; // rcx
  struct _ERESOURCE *v22; // rcx
  bool v23; // di
  unsigned int v24; // ecx
  __int64 v25; // r8
  unsigned int v26; // eax
  __int64 v27; // rbp
  struct _ERESOURCE *v28; // rcx
  __int128 v29; // [rsp+40h] [rbp-78h] BYREF
  PVOID Object[2]; // [rsp+50h] [rbp-68h] BYREF
  __int128 v31; // [rsp+60h] [rbp-58h] BYREF

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
      && (v5 = appv::shared::kernel::ThreadHandles<Streaming::FlushRequestTagInfo>::ResizeNoLock(
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
        v29 = 0;
        v31 = 0;
        if ( (unsigned __int8)appv::shared::kernel::SafeQueue<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::Get(
                                a1,
                                &v29) )
        {
          v10 = **(_QWORD **)v29;
          v11 = *(struct _FILE_OBJECT **)(*(_QWORD *)v29 + 8LL);
          v12 = *(struct _FLT_INSTANCE **)(v10 + 104);
          if ( FltFlushBuffers(v12, v11) >= 0 )
            Streaming::Context::StreamingBitmapBuilder::UpdateStreamingInformation(
              v12,
              v11,
              *(struct Streaming::Context::StreamingBitMap **)(v10 + 88));
          *(_QWORD *)&v29 = 0;
          kernel_std::detail::shared_count::operator=((char *)&v29 + 8, (char *)&v31 + 8);
        }
        v13 = (volatile signed __int32 *)*((_QWORD *)&v29 + 1);
        if ( *((_QWORD *)&v29 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v29 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
            if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 16LL))(v13);
          }
        }
      }
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 208));
      v14 = *(_DWORD *)(a1 + 212);
      v15 = 0;
      if ( *(_QWORD *)(a1 + 112) )
      {
        KeEnterCriticalRegion();
        v15 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 112), 1u) == 1;
      }
      v16 = *(_DWORD *)(a1 + 92);
      if ( v16 <= v14 )
      {
        if ( v15 )
        {
          v22 = *(struct _ERESOURCE **)(a1 + 112);
          if ( v22 )
          {
            ExReleaseResourceLite(v22);
            KeLeaveCriticalRegion();
          }
        }
      }
      else
      {
        if ( *(_BYTE *)(a1 + 96) && v16 )
        {
          v17 = *(_QWORD *)(a1 + 64);
          v18 = 0;
          while ( 1 )
          {
            v19 = v18;
            if ( CurrentThread == *(struct _KTHREAD **)(v17 + 8LL * v18) )
              break;
            if ( ++v18 >= v16 )
              goto LABEL_34;
          }
          ObfDereferenceObject(*(PVOID *)(v17 + 8LL * v18));
          *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8 * v19) = *(_QWORD *)(*(_QWORD *)(a1 + 64)
                                                                  + 8LL * (unsigned int)--*(_DWORD *)(a1 + 92));
          v20 = 1;
          *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL * *(unsigned int *)(a1 + 92)) = 0;
        }
        else
        {
LABEL_34:
          v20 = 0;
        }
        if ( v15 )
        {
          v21 = *(struct _ERESOURCE **)(a1 + 112);
          if ( v21 )
          {
            ExReleaseResourceLite(v21);
            KeLeaveCriticalRegion();
          }
        }
        if ( v20 )
          return 0;
      }
    }
    while ( v9 == 1 || v9 == -1073741670 );
    v23 = 0;
    if ( *(_QWORD *)(a1 + 112) )
    {
      KeEnterCriticalRegion();
      v23 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 112), 1u) == 1;
    }
    if ( *(_BYTE *)(a1 + 96) )
    {
      v24 = *(_DWORD *)(a1 + 92);
      if ( v24 )
      {
        v25 = *(_QWORD *)(a1 + 64);
        v26 = 0;
        while ( 1 )
        {
          v27 = v26;
          if ( CurrentThread == *(struct _KTHREAD **)(v25 + 8LL * v26) )
            break;
          if ( ++v26 >= v24 )
            goto LABEL_55;
        }
        ObfDereferenceObject(*(PVOID *)(v25 + 8LL * v26));
        *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8 * v27) = *(_QWORD *)(*(_QWORD *)(a1 + 64)
                                                                + 8LL * (unsigned int)--*(_DWORD *)(a1 + 92));
        *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL * *(unsigned int *)(a1 + 92)) = 0;
      }
    }
LABEL_55:
    if ( v23 )
    {
      v28 = *(struct _ERESOURCE **)(a1 + 112);
      if ( v28 )
      {
        ExReleaseResourceLite(v28);
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
0x1400044a0  push    rbx
0x1400044a2  push    rbp
0x1400044a3  push    rsi
0x1400044a4  push    rdi
0x1400044a5  push    r12
0x1400044a7  push    r13
0x1400044a9  push    r14
0x1400044ab  push    r15
0x1400044ad  sub     rsp, 78h
0x1400044b1  mov     r12, gs:188h
0x1400044ba  xor     r15d, r15d
0x1400044bd  mov     rbx, rcx
0x1400044c0  test    r12, r12
0x1400044c3  jnz     short loc_1400044E6
0x1400044c5  add     rcx, 0B0h; Semaphore
0x1400044cc  lea     r8d, [r15+1]; Adjustment
0x1400044d0  xor     r9d, r9d; Wait
0x1400044d3  xor     edx, edx; Increment
0x1400044d5  call    cs:__imp_KeReleaseSemaphore
0x1400044dc  nop     dword ptr [rax+rax+00h]
0x1400044e1  jmp     loc_14000488D
0x1400044e6  mov     esi, 1
0x1400044eb  movzx   ebp, r15b
0x1400044ef  cmp     [rcx+70h], r15
0x1400044f3  jz      short loc_14000451A
0x1400044f5  call    cs:__imp_KeEnterCriticalRegion
0x1400044fc  nop     dword ptr [rax+rax+00h]
0x140004501  mov     rcx, [rbx+70h]; Resource
0x140004505  mov     dl, sil; Wait
0x140004508  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000450f  nop     dword ptr [rax+rax+00h]
0x140004514  cmp     al, sil
0x140004517  cmovz   ebp, esi
0x14000451a  mov     edx, [rbx+58h]
0x14000451d  cmp     [rbx+5Ch], edx
0x140004520  jnz     short loc_14000455D
0x140004522  add     edx, 0Ah
0x140004525  lea     rcx, [rbx+38h]
0x140004529  call    ?ResizeNoLock@?$ThreadHandles@VFlushRequestTagInfo@Streaming@@@kernel@shared@appv@@AEAAJK@Z; appv::shared::kernel::ThreadHandles<Streaming::FlushRequestTagInfo>::ResizeNoLock(ulong)
0x14000452e  mov     r14d, eax
0x140004531  test    eax, eax
0x140004533  jns     short loc_14000455D
0x140004535  test    bpl, bpl
0x140004538  jz      short loc_1400045A3
0x14000453a  mov     rcx, [rbx+70h]; Resource
0x14000453e  test    rcx, rcx
0x140004541  jz      short loc_1400045A3
0x140004543  call    cs:__imp_ExReleaseResourceLite
0x14000454a  nop     dword ptr [rax+rax+00h]
0x14000454f  call    cs:__imp_KeLeaveCriticalRegion
0x140004556  nop     dword ptr [rax+rax+00h]
0x14000455b  jmp     short loc_1400045A3
0x14000455d  mov     rcx, r12; Object
0x140004560  call    cs:__imp_ObfReferenceObject
0x140004567  nop     dword ptr [rax+rax+00h]
0x14000456c  mov     ecx, [rbx+5Ch]
0x14000456f  mov     rax, [rbx+40h]
0x140004573  mov     [rax+rcx*8], r12
0x140004577  add     [rbx+5Ch], esi
0x14000457a  test    bpl, bpl
0x14000457d  jz      short loc_1400045A0
0x14000457f  mov     rcx, [rbx+70h]; Resource
0x140004583  test    rcx, rcx
0x140004586  jz      short loc_1400045A0
0x140004588  call    cs:__imp_ExReleaseResourceLite
0x14000458f  nop     dword ptr [rax+rax+00h]
0x140004594  call    cs:__imp_KeLeaveCriticalRegion
0x14000459b  nop     dword ptr [rax+rax+00h]
0x1400045a0  mov     r14d, r15d
0x1400045a3  lea     rcx, [rbx+0B0h]; Semaphore
0x1400045aa  xor     r9d, r9d; Wait
0x1400045ad  mov     r8d, esi; Adjustment
0x1400045b0  xor     edx, edx; Increment
0x1400045b2  call    cs:__imp_KeReleaseSemaphore
0x1400045b9  nop     dword ptr [rax+rax+00h]
0x1400045be  test    r14d, r14d
0x1400045c1  jns     short loc_1400045CB
0x1400045c3  mov     eax, r14d
0x1400045c6  jmp     loc_14000488F
0x1400045cb  mov     rax, [rbx+80h]
0x1400045d2  mov     [rsp+0B8h+Object], rax
0x1400045d7  lea     rax, [rbx+90h]
0x1400045de  mov     [rsp+0B8h+var_60], rax
0x1400045e3  mov     [rsp+0B8h+WaitBlockArray], r15; WaitBlockArray
0x1400045e8  lea     rdx, [rsp+0B8h+Object]; Object
0x1400045ed  xor     r9d, r9d; WaitReason
0x1400045f0  mov     [rsp+0B8h+Timeout], r15; Timeout
0x1400045f5  mov     [rsp+0B8h+Alertable], r15b; Alertable
0x1400045fa  mov     r8d, esi; WaitType
0x1400045fd  mov     [rsp+0B8h+WaitMode], r15b; WaitMode
0x140004602  lea     ecx, [r9+2]; Count
0x140004606  call    cs:__imp_KeWaitForMultipleObjects
0x14000460d  nop     dword ptr [rax+rax+00h]
0x140004612  mov     r13d, eax
0x140004615  lock add [rbx+0D0h], esi
0x14000461c  cmp     eax, esi
0x14000461e  jnz     loc_1400046D8
0x140004624  xorps   xmm0, xmm0
0x140004627  lea     rdx, [rsp+0B8h+var_78]
0x14000462c  xorps   xmm1, xmm1
0x14000462f  mov     rcx, rbx
0x140004632  movdqu  [rsp+0B8h+var_78], xmm0
0x140004638  movdqu  [rsp+0B8h+var_58], xmm1
0x14000463e  call    ?Get@?$SafeQueue@V?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@VWriteFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAA_NAEAV?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@@Z; appv::shared::kernel::SafeQueue<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::Get(kernel_std::shared_ptr<Streaming::WriteFault> &)
0x140004643  test    al, al
0x140004645  jz      short loc_140004696
0x140004647  mov     rax, qword ptr [rsp+0B8h+var_78]
0x14000464c  mov     rcx, [rax]
0x14000464f  mov     r14, [rcx]
0x140004652  mov     rbp, [rcx+8]
0x140004656  mov     rdx, rbp; FileObject
0x140004659  mov     r15, [r14+68h]
0x14000465d  mov     rcx, r15; Instance
0x140004660  call    cs:__imp_FltFlushBuffers
0x140004667  nop     dword ptr [rax+rax+00h]
0x14000466c  test    eax, eax
0x14000466e  js      short loc_14000467F
0x140004670  mov     r8, [r14+58h]; struct Streaming::Context::StreamingBitMap *
0x140004674  mov     rdx, rbp; FileObject
0x140004677  mov     rcx, r15; Instance
0x14000467a  call    ?UpdateStreamingInformation@StreamingBitmapBuilder@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAVStreamingBitMap@23@@Z; Streaming::Context::StreamingBitmapBuilder::UpdateStreamingInformation(_FLT_INSTANCE *,_FILE_OBJECT &,Streaming::Context::StreamingBitMap &)
0x14000467f  xor     r15d, r15d
0x140004682  lea     rdx, [rsp+0B8h+var_58+8]
0x140004687  lea     rcx, [rsp+0B8h+var_78+8]
0x14000468c  mov     qword ptr [rsp+0B8h+var_78], r15
0x140004691  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x140004696  mov     r14, qword ptr [rsp+0B8h+var_78+8]
0x14000469b  test    r14, r14
0x14000469e  jz      short loc_1400046D8
0x1400046a0  or      eax, 0FFFFFFFFh
0x1400046a3  lock xadd [r14+8], eax
0x1400046a9  cmp     eax, esi
0x1400046ab  jnz     short loc_1400046D8
0x1400046ad  mov     rax, [r14]
0x1400046b0  mov     rcx, r14
0x1400046b3  mov     rax, [rax+8]
0x1400046b7  call    _guard_dispatch_icall
0x1400046bc  or      eax, 0FFFFFFFFh
0x1400046bf  lock xadd [r14+0Ch], eax
0x1400046c5  cmp     eax, esi
0x1400046c7  jnz     short loc_1400046D8
0x1400046c9  mov     rax, [r14]
0x1400046cc  mov     rcx, r14
0x1400046cf  mov     rax, [rax+10h]
0x1400046d3  call    _guard_dispatch_icall
0x1400046d8  lock dec dword ptr [rbx+0D0h]
0x1400046df  mov     r14d, [rbx+0D4h]
0x1400046e6  movzx   ebp, r15b
0x1400046ea  cmp     [rbx+70h], r15
0x1400046ee  jz      short loc_140004715
0x1400046f0  call    cs:__imp_KeEnterCriticalRegion
0x1400046f7  nop     dword ptr [rax+rax+00h]
0x1400046fc  mov     rcx, [rbx+70h]; Resource
0x140004700  mov     dl, sil; Wait
0x140004703  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000470a  nop     dword ptr [rax+rax+00h]
0x14000470f  cmp     al, sil
0x140004712  cmovz   ebp, esi
0x140004715  mov     ecx, [rbx+5Ch]
0x140004718  cmp     ecx, r14d
0x14000471b  jbe     loc_1400047A9
0x140004721  cmp     [rbx+60h], r15b
0x140004725  jz      short loc_140004744
0x140004727  test    ecx, ecx
0x140004729  jz      short loc_140004744
0x14000472b  mov     r8, [rbx+40h]
0x14000472f  mov     eax, r15d
0x140004732  mov     r14d, eax
0x140004735  mov     rdx, [r8+r14*8]
0x140004739  cmp     r12, rdx
0x14000473c  jz      short loc_140004778
0x14000473e  add     eax, esi
0x140004740  cmp     eax, ecx
0x140004742  jb      short loc_140004732
0x140004744  mov     r14b, r15b
0x140004747  test    bpl, bpl
0x14000474a  jz      short loc_14000476D
0x14000474c  mov     rcx, [rbx+70h]; Resource
0x140004750  test    rcx, rcx
0x140004753  jz      short loc_14000476D
0x140004755  call    cs:__imp_ExReleaseResourceLite
0x14000475c  nop     dword ptr [rax+rax+00h]
0x140004761  call    cs:__imp_KeLeaveCriticalRegion
0x140004768  nop     dword ptr [rax+rax+00h]
0x14000476d  test    r14b, r14b
0x140004770  jnz     loc_14000488D
0x140004776  jmp     short loc_1400047CF
0x140004778  mov     rcx, rdx; Object
0x14000477b  call    cs:__imp_ObfDereferenceObject
0x140004782  nop     dword ptr [rax+rax+00h]
0x140004787  dec     dword ptr [rbx+5Ch]
0x14000478a  mov     rcx, [rbx+40h]
0x14000478e  mov     eax, [rbx+5Ch]
0x140004791  mov     rax, [rcx+rax*8]
0x140004795  mov     [rcx+r14*8], rax
0x140004799  mov     r14b, sil
0x14000479c  mov     ecx, [rbx+5Ch]
0x14000479f  mov     rax, [rbx+40h]
0x1400047a3  mov     [rax+rcx*8], r15
0x1400047a7  jmp     short loc_140004747
0x1400047a9  test    bpl, bpl
0x1400047ac  jz      short loc_1400047CF
0x1400047ae  mov     rcx, [rbx+70h]; Resource
0x1400047b2  test    rcx, rcx
0x1400047b5  jz      short loc_1400047CF
0x1400047b7  call    cs:__imp_ExReleaseResourceLite
0x1400047be  nop     dword ptr [rax+rax+00h]
0x1400047c3  call    cs:__imp_KeLeaveCriticalRegion
0x1400047ca  nop     dword ptr [rax+rax+00h]
0x1400047cf  cmp     r13d, esi
0x1400047d2  jz      loc_1400045E3
0x1400047d8  cmp     r13d, 0C000009Ah
0x1400047df  jz      loc_1400045E3
0x1400047e5  movzx   edi, r15b
0x1400047e9  cmp     [rbx+70h], r15
0x1400047ed  jz      short loc_140004814
0x1400047ef  call    cs:__imp_KeEnterCriticalRegion
0x1400047f6  nop     dword ptr [rax+rax+00h]
0x1400047fb  mov     rcx, [rbx+70h]; Resource
0x1400047ff  mov     dl, sil; Wait
0x140004802  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140004809  nop     dword ptr [rax+rax+00h]
0x14000480e  cmp     al, sil
0x140004811  cmovz   edi, esi
0x140004814  cmp     [rbx+60h], r15b
0x140004818  jz      short loc_140004867
0x14000481a  mov     ecx, [rbx+5Ch]
0x14000481d  test    ecx, ecx
0x14000481f  jz      short loc_140004867
0x140004821  mov     r8, [rbx+40h]
0x140004825  mov     eax, r15d
0x140004828  mov     ebp, eax
0x14000482a  mov     rdx, [r8+rbp*8]
0x14000482e  cmp     r12, rdx
0x140004831  jz      short loc_14000483B
0x140004833  add     eax, esi
0x140004835  cmp     eax, ecx
0x140004837  jb      short loc_140004828
0x140004839  jmp     short loc_140004867
0x14000483b  mov     rcx, rdx; Object
0x14000483e  call    cs:__imp_ObfDereferenceObject
0x140004845  nop     dword ptr [rax+rax+00h]
0x14000484a  dec     dword ptr [rbx+5Ch]
0x14000484d  mov     rcx, [rbx+40h]
0x140004851  mov     eax, [rbx+5Ch]
0x140004854  mov     rax, [rcx+rax*8]
0x140004858  mov     [rcx+rbp*8], rax
0x14000485c  mov     ecx, [rbx+5Ch]
0x14000485f  mov     rax, [rbx+40h]
0x140004863  mov     [rax+rcx*8], r15
0x140004867  test    dil, dil
0x14000486a  jz      short loc_14000488D
0x14000486c  mov     rcx, [rbx+70h]; Resource
0x140004870  test    rcx, rcx
0x140004873  jz      short loc_14000488D
0x140004875  call    cs:__imp_ExReleaseResourceLite
0x14000487c  nop     dword ptr [rax+rax+00h]
0x140004881  call    cs:__imp_KeLeaveCriticalRegion
0x140004888  nop     dword ptr [rax+rax+00h]
0x14000488d  xor     eax, eax
0x14000488f  add     rsp, 78h
0x140004893  pop     r15
0x140004895  pop     r14
0x140004897  pop     r13
0x140004899  pop     r12
0x14000489b  pop     rdi
0x14000489c  pop     rsi
0x14000489d  pop     rbp
0x14000489e  pop     rbx
0x14000489f  retn
```
