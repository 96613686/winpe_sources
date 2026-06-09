# HampConnectionStart

- ea: `0x180003a08`
- end: `0x180003ae7`
- name: `HampConnectionStart`
- size: `223`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001e00`
- `0x1800030a0`
- `0x180003170`
- `0x180003270`

## callees

- `0x180003a08`
- `0x180003b50`
- `0x180003b80`
- `0x18001ae8e`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x180003a67`
- `ntdll!RtlInitializeSRWLock` at `0x180003a67`
- `ntdll!TpAllocWork` at `0x180003a9c`
- `ntdll!TpAllocWork` at `0x180003a9c`
- `ntdll!RtlAllocateHeap` at `0x180003a3a`
- `ntdll!RtlAllocateHeap` at `0x180003a3a`

## pseudocode

```c
__int64 __fastcall HampConnectionStart(__int64 a1)
{
  _QWORD *Heap; // rax
  unsigned int v3; // ebx
  _QWORD *v4; // rdi
  int v5; // eax
  int v6; // esi

  if ( *(_BYTE *)(a1 + 156) != 6 )
    return 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x48u);
  v3 = 0;
  v4 = Heap;
  if ( Heap )
  {
    memset_0(Heap, 0, 0x48u);
    v4[6] = *(_QWORD *)(a1 + 16);
    RtlInitializeSRWLock(v4 + 4);
    v4[3] = v4 + 2;
    v4[2] = v4 + 2;
    *((_DWORD *)v4 + 16) &= ~1u;
    v4[5] = HampConnectionDeliverStateChangePayload;
    v4[1] = a1;
    v5 = TpAllocWork(v4 + 7, RmpClientWnfMessageQueueWorker, v4, 0);
    v6 = 0;
    if ( v5 < 0 )
      v6 = v5;
    if ( v6 >= 0 )
    {
      v6 = RmSubscriptionStart(a1 + 16, v4);
      if ( v6 >= 0 )
      {
        *(_QWORD *)(a1 + 24) = v4;
        return v3;
      }
    }
    RmpClientWnfDestroySubscription(v4);
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003a08  push    rbx
0x180003a0a  push    rbp
0x180003a0b  push    rsi
0x180003a0c  push    rdi
0x180003a0d  push    r14
0x180003a0f  sub     rsp, 20h
0x180003a13  cmp     byte ptr [rcx+9Ch], 6
0x180003a1a  mov     rbp, rcx
0x180003a1d  jnz     loc_180003ADC
0x180003a23  mov     rcx, gs:60h
0x180003a2c  mov     esi, 48h ; 'H'
0x180003a31  mov     r8d, esi; Size
0x180003a34  xor     edx, edx; Flags
0x180003a36  mov     rcx, [rcx+30h]; HeapHandle
0x180003a3a  call    cs:__imp_RtlAllocateHeap
0x180003a40  xor     ebx, ebx
0x180003a42  mov     rdi, rax
0x180003a45  test    rax, rax
0x180003a48  jz      loc_180003AE0
0x180003a4e  mov     r8d, esi; Size
0x180003a51  xor     edx, edx; Val
0x180003a53  mov     rcx, rax; void *
0x180003a56  call    memset_0
0x180003a5b  mov     rax, [rbp+10h]
0x180003a5f  lea     rcx, [rdi+20h]
0x180003a63  mov     [rdi+30h], rax
0x180003a67  call    cs:__imp_RtlInitializeSRWLock
0x180003a6d  lea     rax, [rdi+10h]
0x180003a71  xor     r9d, r9d
0x180003a74  mov     [rax+8], rax
0x180003a78  lea     rcx, [rdi+38h]
0x180003a7c  mov     [rax], rax
0x180003a7f  lea     rdx, RmpClientWnfMessageQueueWorker
0x180003a86  and     dword ptr [rdi+40h], 0FFFFFFFEh
0x180003a8a  lea     rax, HampConnectionDeliverStateChangePayload
0x180003a91  mov     r8, rdi
0x180003a94  mov     [rdi+28h], rax
0x180003a98  mov     [rdi+8], rbp
0x180003a9c  call    cs:__imp_TpAllocWork
0x180003aa2  test    eax, eax
0x180003aa4  mov     esi, ebx
0x180003aa6  cmovs   esi, eax
0x180003aa9  test    esi, esi
0x180003aab  jns     short loc_180003AC4
0x180003aad  mov     rcx, rdi
0x180003ab0  call    RmpClientWnfDestroySubscription
0x180003ab5  mov     ebx, esi
0x180003ab7  mov     eax, ebx
0x180003ab9  add     rsp, 20h
0x180003abd  pop     r14
0x180003abf  pop     rdi
0x180003ac0  pop     rsi
0x180003ac1  pop     rbp
0x180003ac2  pop     rbx
0x180003ac3  retn
0x180003ac4  mov     rdx, rdi
0x180003ac7  lea     rcx, [rbp+10h]
0x180003acb  call    RmSubscriptionStart
0x180003ad0  mov     esi, eax
0x180003ad2  test    eax, eax
0x180003ad4  js      short loc_180003AAD
0x180003ad6  mov     [rbp+18h], rdi
0x180003ada  jmp     short loc_180003AB7
0x180003adc  xor     ebx, ebx
0x180003ade  jmp     short loc_180003AB7
0x180003ae0  mov     esi, 0C0000017h
0x180003ae5  jmp     short loc_180003AB5
```
