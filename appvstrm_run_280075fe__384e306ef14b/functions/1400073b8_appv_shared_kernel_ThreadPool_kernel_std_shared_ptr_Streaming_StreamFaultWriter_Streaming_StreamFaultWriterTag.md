# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool(void)

- ea: `0x1400073b8`
- end: `0x1400075c7`
- name: `?StopThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAAXXZ`
- size: `527`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x14000528c`
- `0x14000600c`
- `0x140006158`
- `0x140006710`
- `0x140006864`
- `0x1400078a0`
- `0x140007ae0`
- `0x140007b80`

## callees

- `0x140003bd8`
- `0x140003c58`
- `0x1400073b8`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400074d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007507`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400074d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007507`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400074cd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400074fb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400074cd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400074fb`
- `ntoskrnl!KeSetEvent` at `0x1400073d0`
- `ntoskrnl!KeSetEvent` at `0x140007405`
- `ntoskrnl!KeSetEvent` at `0x1400073d0`
- `ntoskrnl!KeSetEvent` at `0x140007405`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000749c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000749c`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140007558`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140007558`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140007484`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140007484`
- `ntoskrnl!ObfDereferenceObject` at `0x140007587`
- `ntoskrnl!ObfDereferenceObject` at `0x140007587`

## pseudocode

```c
void __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool(
        __int64 a1)
{
  __int64 v2; // rcx
  volatile signed __int32 *v3; // rbx
  bool v4; // bl
  unsigned int v5; // esi
  struct _ERESOURCE *v6; // rcx
  struct _ERESOURCE *v7; // rcx
  int v8; // ebx
  unsigned int i; // ebp
  ULONG v10; // ecx
  NTSTATUS v11; // eax
  __int64 v12; // rbx
  __int64 v13; // rdx
  unsigned int v14; // eax
  int v15; // eax
  __int128 v16; // [rsp+40h] [rbp-48h] BYREF
  __int128 v17; // [rsp+50h] [rbp-38h] BYREF

  KeSetEvent(*(PRKEVENT *)(a1 + 128), 0, 0);
  v16 = 0;
  v17 = 0;
  while ( (unsigned __int8)appv::shared::kernel::SafeQueue<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::Get(
                             a1,
                             &v16) )
  {
    v2 = v16;
    *(_DWORD *)(v16 + 36) = -1073741536;
    KeSetEvent(*(PRKEVENT *)(v2 + 48), 0, 0);
    *(_QWORD *)&v16 = 0;
    kernel_std::detail::shared_count::operator=((char *)&v16 + 8, (char *)&v17 + 8);
  }
  v3 = (volatile signed __int32 *)*((_QWORD *)&v16 + 1);
  if ( *((_QWORD *)&v16 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v16 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
      if ( !_InterlockedDecrement(v3 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 16LL))(v3);
    }
  }
  v4 = 0;
  if ( *(_QWORD *)(a1 + 112) )
  {
    KeEnterCriticalRegion();
    v4 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 112), 1u) == 1;
  }
  v5 = *(_DWORD *)(a1 + 92);
  if ( v5 )
  {
    *(_BYTE *)(a1 + 96) = 0;
    if ( v4 )
    {
      v7 = *(struct _ERESOURCE **)(a1 + 112);
      if ( v7 )
      {
        ExReleaseResourceLite(v7);
        KeLeaveCriticalRegion();
      }
    }
    v8 = 0;
    for ( i = 0; i < v5; i += 64 )
    {
      v10 = 64;
      if ( v5 - i < 0x40 )
        v10 = v5 - i;
      v11 = KeWaitForMultipleObjects(
              v10,
              (PVOID *)(*(_QWORD *)(a1 + 64) + i),
              WaitAll,
              Executive,
              0,
              0,
              0,
              (PKWAIT_BLOCK)(i + *(_QWORD *)(a1 + 80)));
      if ( v11 < 0 )
        v8 = v11;
    }
    if ( v8 >= 0 )
    {
      while ( 1 )
      {
        v15 = *(_DWORD *)(a1 + 92);
        if ( !v15 )
          break;
        v12 = (unsigned int)(v15 - 1);
        ObfDereferenceObject(*(PVOID *)(*(_QWORD *)(a1 + 64) + 8 * v12));
        v13 = *(_QWORD *)(a1 + 64);
        v14 = *(_DWORD *)(a1 + 92) - 1;
        *(_DWORD *)(a1 + 92) = v14;
        *(_QWORD *)(v13 + 8 * v12) = *(_QWORD *)(v13 + 8LL * v14);
        *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL * *(unsigned int *)(a1 + 92)) = 0;
      }
    }
  }
  else if ( v4 )
  {
    v6 = *(struct _ERESOURCE **)(a1 + 112);
    if ( v6 )
    {
      ExReleaseResourceLite(v6);
      KeLeaveCriticalRegion();
    }
  }
}

```

## disassembly

```asm
0x1400073b8  push    rbx
0x1400073ba  push    rbp
0x1400073bb  push    rsi
0x1400073bc  push    rdi
0x1400073bd  sub     rsp, 68h
0x1400073c1  mov     rdi, rcx
0x1400073c4  xor     r8d, r8d; Wait
0x1400073c7  mov     rcx, [rcx+80h]; Event
0x1400073ce  xor     edx, edx; Increment
0x1400073d0  call    cs:__imp_KeSetEvent
0x1400073d7  nop     dword ptr [rax+rax+00h]
0x1400073dc  xorps   xmm0, xmm0
0x1400073df  xorps   xmm1, xmm1
0x1400073e2  movdqu  [rsp+88h+var_48], xmm0
0x1400073e8  movdqu  [rsp+88h+var_38], xmm1
0x1400073ee  jmp     short loc_140007429
0x1400073f0  mov     rcx, qword ptr [rsp+88h+var_48]
0x1400073f5  xor     r8d, r8d; Wait
0x1400073f8  xor     edx, edx; Increment
0x1400073fa  mov     dword ptr [rcx+24h], 0C0000120h
0x140007401  mov     rcx, [rcx+30h]; Event
0x140007405  call    cs:__imp_KeSetEvent
0x14000740c  nop     dword ptr [rax+rax+00h]
0x140007411  lea     rdx, [rsp+88h+var_38+8]
0x140007416  mov     qword ptr [rsp+88h+var_48], 0
0x14000741f  lea     rcx, [rsp+88h+var_48+8]
0x140007424  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x140007429  lea     rdx, [rsp+88h+var_48]
0x14000742e  mov     rcx, rdi
0x140007431  call    ?Get@?$SafeQueue@V?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@VWriteFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAA_NAEAV?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@@Z; appv::shared::kernel::SafeQueue<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::Get(kernel_std::shared_ptr<Streaming::WriteFault> &)
0x140007436  test    al, al
0x140007438  jnz     short loc_1400073F0
0x14000743a  mov     rbx, qword ptr [rsp+88h+var_48+8]
0x14000743f  test    rbx, rbx
0x140007442  jz      short loc_14000747B
0x140007444  or      esi, 0FFFFFFFFh
0x140007447  mov     eax, esi
0x140007449  lock xadd [rbx+8], eax
0x14000744e  add     eax, esi
0x140007450  jnz     short loc_14000747B
0x140007452  mov     rax, [rbx]
0x140007455  mov     rcx, rbx
0x140007458  mov     rax, [rax+8]
0x14000745c  call    _guard_dispatch_icall
0x140007461  mov     eax, esi
0x140007463  lock xadd [rbx+0Ch], eax
0x140007468  add     eax, esi
0x14000746a  jnz     short loc_14000747B
0x14000746c  mov     rax, [rbx]
0x14000746f  mov     rcx, rbx
0x140007472  mov     rax, [rax+10h]
0x140007476  call    _guard_dispatch_icall
0x14000747b  xor     bl, bl
0x14000747d  cmp     qword ptr [rdi+70h], 0
0x140007482  jz      short loc_1400074B1
0x140007484  call    cs:__imp_KeEnterCriticalRegion
0x14000748b  nop     dword ptr [rax+rax+00h]
0x140007490  mov     rcx, [rdi+70h]; Resource
0x140007494  mov     esi, 1
0x140007499  mov     dl, sil; Wait
0x14000749c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400074a3  nop     dword ptr [rax+rax+00h]
0x1400074a8  cmp     al, sil
0x1400074ab  movzx   ebx, bl
0x1400074ae  cmovz   ebx, esi
0x1400074b1  mov     esi, [rdi+5Ch]
0x1400074b4  test    esi, esi
0x1400074b6  jnz     short loc_1400074EA
0x1400074b8  test    bl, bl
0x1400074ba  jz      loc_1400075BD
0x1400074c0  mov     rcx, [rdi+70h]; Resource
0x1400074c4  test    rcx, rcx
0x1400074c7  jz      loc_1400075BD
0x1400074cd  call    cs:__imp_ExReleaseResourceLite
0x1400074d4  nop     dword ptr [rax+rax+00h]
0x1400074d9  call    cs:__imp_KeLeaveCriticalRegion
0x1400074e0  nop     dword ptr [rax+rax+00h]
0x1400074e5  jmp     loc_1400075BD
0x1400074ea  mov     byte ptr [rdi+60h], 0
0x1400074ee  test    bl, bl
0x1400074f0  jz      short loc_140007513
0x1400074f2  mov     rcx, [rdi+70h]; Resource
0x1400074f6  test    rcx, rcx
0x1400074f9  jz      short loc_140007513
0x1400074fb  call    cs:__imp_ExReleaseResourceLite
0x140007502  nop     dword ptr [rax+rax+00h]
0x140007507  call    cs:__imp_KeLeaveCriticalRegion
0x14000750e  nop     dword ptr [rax+rax+00h]
0x140007513  xor     ebx, ebx
0x140007515  xor     ebp, ebp
0x140007517  test    esi, esi
0x140007519  jz      loc_1400075B6
0x14000751f  mov     r8, [rdi+50h]
0x140007523  mov     ecx, 40h ; '@'
0x140007528  mov     eax, esi
0x14000752a  mov     edx, ebp
0x14000752c  sub     eax, ebp
0x14000752e  cmp     eax, ecx
0x140007530  cmovb   ecx, eax; Count
0x140007533  add     r8, rdx
0x140007536  add     rdx, [rdi+40h]; Object
0x14000753a  xor     r9d, r9d; WaitReason
0x14000753d  mov     [rsp+88h+WaitBlockArray], r8; WaitBlockArray
0x140007542  xor     r8d, r8d; WaitType
0x140007545  mov     [rsp+88h+Timeout], 0; Timeout
0x14000754e  mov     [rsp+88h+Alertable], 0; Alertable
0x140007553  mov     [rsp+88h+WaitMode], 0; WaitMode
0x140007558  call    cs:__imp_KeWaitForMultipleObjects
0x14000755f  nop     dword ptr [rax+rax+00h]
0x140007564  test    eax, eax
0x140007566  cmovs   ebx, eax
0x140007569  add     ebp, 40h ; '@'
0x14000756c  cmp     ebp, esi
0x14000756e  jb      short loc_14000751F
0x140007570  test    ebx, ebx
0x140007572  js      short loc_1400075BD
0x140007574  jmp     short loc_1400075B6
0x140007576  lea     ecx, [rax-1]
0x140007579  cmp     ecx, eax
0x14000757b  jnb     short loc_1400075B6
0x14000757d  mov     ebx, ecx
0x14000757f  mov     rcx, [rdi+40h]
0x140007583  mov     rcx, [rcx+rbx*8]; Object
0x140007587  call    cs:__imp_ObfDereferenceObject
0x14000758e  nop     dword ptr [rax+rax+00h]
0x140007593  mov     eax, [rdi+5Ch]
0x140007596  mov     rdx, [rdi+40h]
0x14000759a  dec     eax
0x14000759c  mov     [rdi+5Ch], eax
0x14000759f  mov     rcx, [rdx+rax*8]
0x1400075a3  mov     [rdx+rbx*8], rcx
0x1400075a7  mov     ecx, [rdi+5Ch]
0x1400075aa  mov     rax, [rdi+40h]
0x1400075ae  mov     qword ptr [rax+rcx*8], 0
0x1400075b6  mov     eax, [rdi+5Ch]
0x1400075b9  test    eax, eax
0x1400075bb  jnz     short loc_140007576
0x1400075bd  add     rsp, 68h
0x1400075c1  pop     rdi
0x1400075c2  pop     rsi
0x1400075c3  pop     rbp
0x1400075c4  pop     rbx
0x1400075c5  retn
```
