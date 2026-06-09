# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::StopThreadPool(void)

- ea: `0x1400048a8`
- end: `0x140004a96`
- name: `?StopThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFault@Streaming@@@kernel_std@@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAAXXZ`
- size: `494`
- prototype: `void __fastcall(__int64)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x140003aa8`
- `0x140003d40`
- `0x140003ef8`
- `0x140004c00`
- `0x140005334`
- `0x1400078a0`
- `0x14000e088`
- `0x14000e1dc`

## callees

- `0x140003bd8`
- `0x140003c58`
- `0x1400048a8`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400049a8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400049d6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400049a8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400049d6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000499c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400049ca`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000499c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400049ca`
- `ntoskrnl!KeSetEvent` at `0x1400048c0`
- `ntoskrnl!KeSetEvent` at `0x1400048c0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000496b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000496b`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140004a27`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140004a27`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140004953`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140004953`
- `ntoskrnl!ObfDereferenceObject` at `0x140004a56`
- `ntoskrnl!ObfDereferenceObject` at `0x140004a56`

## pseudocode

```c
void __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::StopThreadPool(
        __int64 a1)
{
  volatile signed __int32 *v2; // rbx
  bool v3; // bl
  unsigned int v4; // esi
  struct _ERESOURCE *v5; // rcx
  struct _ERESOURCE *v6; // rcx
  int v7; // ebx
  unsigned int i; // ebp
  ULONG v9; // ecx
  NTSTATUS v10; // eax
  __int64 v11; // rbx
  __int64 v12; // rdx
  unsigned int v13; // eax
  int v14; // eax
  __int128 v15; // [rsp+40h] [rbp-48h] BYREF
  __int128 v16; // [rsp+50h] [rbp-38h] BYREF

  KeSetEvent(*(PRKEVENT *)(a1 + 128), 0, 0);
  v15 = 0;
  v16 = 0;
  while ( appv::shared::kernel::SafeQueue<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::Get(
            a1,
            (__int64)&v15) )
  {
    *(_QWORD *)&v15 = 0;
    kernel_std::detail::shared_count::operator=(
      (volatile signed __int32 **)&v15 + 1,
      (volatile signed __int32 **)&v16 + 1);
  }
  v2 = (volatile signed __int32 *)*((_QWORD *)&v15 + 1);
  if ( *((_QWORD *)&v15 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v15 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
      if ( !_InterlockedDecrement(v2 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 16LL))(v2);
    }
  }
  v3 = 0;
  if ( *(_QWORD *)(a1 + 112) )
  {
    KeEnterCriticalRegion();
    v3 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 112), 1u) == 1;
  }
  v4 = *(_DWORD *)(a1 + 92);
  if ( v4 )
  {
    *(_BYTE *)(a1 + 96) = 0;
    if ( v3 )
    {
      v6 = *(struct _ERESOURCE **)(a1 + 112);
      if ( v6 )
      {
        ExReleaseResourceLite(v6);
        KeLeaveCriticalRegion();
      }
    }
    v7 = 0;
    for ( i = 0; i < v4; i += 64 )
    {
      v9 = 64;
      if ( v4 - i < 0x40 )
        v9 = v4 - i;
      v10 = KeWaitForMultipleObjects(
              v9,
              (PVOID *)(*(_QWORD *)(a1 + 64) + i),
              WaitAll,
              Executive,
              0,
              0,
              0,
              (PKWAIT_BLOCK)(i + *(_QWORD *)(a1 + 80)));
      if ( v10 < 0 )
        v7 = v10;
    }
    if ( v7 >= 0 )
    {
      while ( 1 )
      {
        v14 = *(_DWORD *)(a1 + 92);
        if ( !v14 )
          break;
        v11 = (unsigned int)(v14 - 1);
        ObfDereferenceObject(*(PVOID *)(*(_QWORD *)(a1 + 64) + 8 * v11));
        v12 = *(_QWORD *)(a1 + 64);
        v13 = *(_DWORD *)(a1 + 92) - 1;
        *(_DWORD *)(a1 + 92) = v13;
        *(_QWORD *)(v12 + 8 * v11) = *(_QWORD *)(v12 + 8LL * v13);
        *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL * *(unsigned int *)(a1 + 92)) = 0;
      }
    }
  }
  else if ( v3 )
  {
    v5 = *(struct _ERESOURCE **)(a1 + 112);
    if ( v5 )
    {
      ExReleaseResourceLite(v5);
      KeLeaveCriticalRegion();
    }
  }
}

```

## disassembly

```asm
0x1400048a8  push    rbx
0x1400048aa  push    rbp
0x1400048ab  push    rsi
0x1400048ac  push    rdi
0x1400048ad  sub     rsp, 68h
0x1400048b1  mov     rdi, rcx
0x1400048b4  xor     r8d, r8d; Wait
0x1400048b7  mov     rcx, [rcx+80h]; Event
0x1400048be  xor     edx, edx; Increment
0x1400048c0  call    cs:__imp_KeSetEvent
0x1400048c7  nop     dword ptr [rax+rax+00h]
0x1400048cc  xorps   xmm0, xmm0
0x1400048cf  xorps   xmm1, xmm1
0x1400048d2  movdqu  [rsp+88h+var_48], xmm0
0x1400048d8  movdqu  [rsp+88h+var_38], xmm1
0x1400048de  jmp     short loc_1400048F8
0x1400048e0  lea     rdx, [rsp+88h+var_38+8]
0x1400048e5  mov     qword ptr [rsp+88h+var_48], 0
0x1400048ee  lea     rcx, [rsp+88h+var_48+8]
0x1400048f3  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x1400048f8  lea     rdx, [rsp+88h+var_48]
0x1400048fd  mov     rcx, rdi
0x140004900  call    ?Get@?$SafeQueue@V?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@VWriteFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAA_NAEAV?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@@Z; appv::shared::kernel::SafeQueue<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::Get(kernel_std::shared_ptr<Streaming::WriteFault> &)
0x140004905  test    al, al
0x140004907  jnz     short loc_1400048E0
0x140004909  mov     rbx, qword ptr [rsp+88h+var_48+8]
0x14000490e  test    rbx, rbx
0x140004911  jz      short loc_14000494A
0x140004913  or      esi, 0FFFFFFFFh
0x140004916  mov     eax, esi
0x140004918  lock xadd [rbx+8], eax
0x14000491d  add     eax, esi
0x14000491f  jnz     short loc_14000494A
0x140004921  mov     rax, [rbx]
0x140004924  mov     rcx, rbx
0x140004927  mov     rax, [rax+8]
0x14000492b  call    _guard_dispatch_icall
0x140004930  mov     eax, esi
0x140004932  lock xadd [rbx+0Ch], eax
0x140004937  add     eax, esi
0x140004939  jnz     short loc_14000494A
0x14000493b  mov     rax, [rbx]
0x14000493e  mov     rcx, rbx
0x140004941  mov     rax, [rax+10h]
0x140004945  call    _guard_dispatch_icall
0x14000494a  xor     bl, bl
0x14000494c  cmp     qword ptr [rdi+70h], 0
0x140004951  jz      short loc_140004980
0x140004953  call    cs:__imp_KeEnterCriticalRegion
0x14000495a  nop     dword ptr [rax+rax+00h]
0x14000495f  mov     rcx, [rdi+70h]; Resource
0x140004963  mov     esi, 1
0x140004968  mov     dl, sil; Wait
0x14000496b  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140004972  nop     dword ptr [rax+rax+00h]
0x140004977  cmp     al, sil
0x14000497a  movzx   ebx, bl
0x14000497d  cmovz   ebx, esi
0x140004980  mov     esi, [rdi+5Ch]
0x140004983  test    esi, esi
0x140004985  jnz     short loc_1400049B9
0x140004987  test    bl, bl
0x140004989  jz      loc_140004A8C
0x14000498f  mov     rcx, [rdi+70h]; Resource
0x140004993  test    rcx, rcx
0x140004996  jz      loc_140004A8C
0x14000499c  call    cs:__imp_ExReleaseResourceLite
0x1400049a3  nop     dword ptr [rax+rax+00h]
0x1400049a8  call    cs:__imp_KeLeaveCriticalRegion
0x1400049af  nop     dword ptr [rax+rax+00h]
0x1400049b4  jmp     loc_140004A8C
0x1400049b9  mov     byte ptr [rdi+60h], 0
0x1400049bd  test    bl, bl
0x1400049bf  jz      short loc_1400049E2
0x1400049c1  mov     rcx, [rdi+70h]; Resource
0x1400049c5  test    rcx, rcx
0x1400049c8  jz      short loc_1400049E2
0x1400049ca  call    cs:__imp_ExReleaseResourceLite
0x1400049d1  nop     dword ptr [rax+rax+00h]
0x1400049d6  call    cs:__imp_KeLeaveCriticalRegion
0x1400049dd  nop     dword ptr [rax+rax+00h]
0x1400049e2  xor     ebx, ebx
0x1400049e4  xor     ebp, ebp
0x1400049e6  test    esi, esi
0x1400049e8  jz      loc_140004A85
0x1400049ee  mov     r8, [rdi+50h]
0x1400049f2  mov     ecx, 40h ; '@'
0x1400049f7  mov     eax, esi
0x1400049f9  mov     edx, ebp
0x1400049fb  sub     eax, ebp
0x1400049fd  cmp     eax, ecx
0x1400049ff  cmovb   ecx, eax; Count
0x140004a02  add     r8, rdx
0x140004a05  add     rdx, [rdi+40h]; Object
0x140004a09  xor     r9d, r9d; WaitReason
0x140004a0c  mov     [rsp+88h+WaitBlockArray], r8; WaitBlockArray
0x140004a11  xor     r8d, r8d; WaitType
0x140004a14  mov     [rsp+88h+Timeout], 0; Timeout
0x140004a1d  mov     [rsp+88h+Alertable], 0; Alertable
0x140004a22  mov     [rsp+88h+WaitMode], 0; WaitMode
0x140004a27  call    cs:__imp_KeWaitForMultipleObjects
0x140004a2e  nop     dword ptr [rax+rax+00h]
0x140004a33  test    eax, eax
0x140004a35  cmovs   ebx, eax
0x140004a38  add     ebp, 40h ; '@'
0x140004a3b  cmp     ebp, esi
0x140004a3d  jb      short loc_1400049EE
0x140004a3f  test    ebx, ebx
0x140004a41  js      short loc_140004A8C
0x140004a43  jmp     short loc_140004A85
0x140004a45  lea     ecx, [rax-1]
0x140004a48  cmp     ecx, eax
0x140004a4a  jnb     short loc_140004A85
0x140004a4c  mov     ebx, ecx
0x140004a4e  mov     rcx, [rdi+40h]
0x140004a52  mov     rcx, [rcx+rbx*8]; Object
0x140004a56  call    cs:__imp_ObfDereferenceObject
0x140004a5d  nop     dword ptr [rax+rax+00h]
0x140004a62  mov     eax, [rdi+5Ch]
0x140004a65  mov     rdx, [rdi+40h]
0x140004a69  dec     eax
0x140004a6b  mov     [rdi+5Ch], eax
0x140004a6e  mov     rcx, [rdx+rax*8]
0x140004a72  mov     [rdx+rbx*8], rcx
0x140004a76  mov     ecx, [rdi+5Ch]
0x140004a79  mov     rax, [rdi+40h]
0x140004a7d  mov     qword ptr [rax+rcx*8], 0
0x140004a85  mov     eax, [rdi+5Ch]
0x140004a88  test    eax, eax
0x140004a8a  jnz     short loc_140004A45
0x140004a8c  add     rsp, 68h
0x140004a90  pop     rdi
0x140004a91  pop     rsi
0x140004a92  pop     rbp
0x140004a93  pop     rbx
0x140004a94  retn
```
