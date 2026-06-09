# Common::Array<StateRepository::CacheContextEntry,Common::ContainerOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>,ushort,Common::ContainerOperations<ushort,StateRepository::CacheContextEntry>,Common::ArrayOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>>::EnsureCapacity(unsigned __int64)

- ea: `0x18000f7c0`
- end: `0x18000f877`
- name: `?EnsureCapacity@?$Array@VCacheContextEntry@StateRepository@@V?$ContainerOperations@VCacheContextEntry@StateRepository@@V12@@Common@@GV?$ContainerOperations@GVCacheContextEntry@StateRepository@@@4@V?$ArrayOperations@VCacheContextEntry@StateRepository@@V12@@4@@Common@@QEAAJ_K@Z`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f5c8`

## callees

- `0x18000e670`
- `0x18000f7c0`
- `0x18001007c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000f829`
- `ntdll!RtlAllocateHeap` at `0x18000f829`

## pseudocode

```c
__int64 __fastcall Common::Array<StateRepository::CacheContextEntry,Common::ContainerOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>,unsigned short,Common::ContainerOperations<unsigned short,StateRepository::CacheContextEntry>,Common::ArrayOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>>::EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rax
  unsigned __int64 v5; // rbx
  PVOID Heap; // rax
  PVOID v7; // rsi

  v2 = *(_QWORD *)(a1 + 8);
  if ( a2 > v2 )
  {
    if ( v2 == 0x3FFFFFFF )
      return 2147483659LL;
    if ( v2 )
      v5 = ((3 * v2) >> 1) + 1;
    else
      v5 = 16;
    if ( a2 > v5 )
      v5 = a2;
    if ( v5 > 0x3FFFFFFF )
      v5 = 0x3FFFFFFF;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 8 * v5);
    v7 = Heap;
    if ( !Heap )
      return 2147942414LL;
    if ( *(_QWORD *)a1 )
    {
      memmove_0(Heap, *(const void **)a1, 8LL * *(_QWORD *)(a1 + 16));
      Common::ArrayOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>::MemFree(*(PVOID *)a1);
    }
    *(_QWORD *)a1 = v7;
    *(_QWORD *)(a1 + 8) = v5;
  }
  return 0;
}

```

## disassembly

```asm
0x18000f7c0  mov     [rsp+arg_0], rbx
0x18000f7c5  mov     [rsp+arg_8], rsi
0x18000f7ca  push    rdi
0x18000f7cb  sub     rsp, 20h
0x18000f7cf  mov     rax, [rcx+8]
0x18000f7d3  mov     rdi, rcx
0x18000f7d6  cmp     rdx, rax
0x18000f7d9  jbe     loc_18000F865
0x18000f7df  mov     ecx, 3FFFFFFFh
0x18000f7e4  cmp     rax, rcx
0x18000f7e7  jnz     short loc_18000F7F0
0x18000f7e9  mov     eax, 8000000Bh
0x18000f7ee  jmp     short loc_18000F867
0x18000f7f0  test    rax, rax
0x18000f7f3  jnz     short loc_18000F7FA
0x18000f7f5  lea     ebx, [rax+10h]
0x18000f7f8  jmp     short loc_18000F804
0x18000f7fa  lea     rbx, [rax+rax*2]
0x18000f7fe  shr     rbx, 1
0x18000f801  inc     rbx
0x18000f804  cmp     rdx, rbx
0x18000f807  cmova   rbx, rdx
0x18000f80b  cmp     rbx, rcx
0x18000f80e  cmova   rbx, rcx
0x18000f812  mov     rcx, gs:60h
0x18000f81b  xor     edx, edx; Flags
0x18000f81d  mov     rcx, [rcx+30h]; HeapHandle
0x18000f821  lea     r8, ds:0[rbx*8]; Size
0x18000f829  call    cs:__imp_RtlAllocateHeap
0x18000f82f  mov     rsi, rax
0x18000f832  test    rax, rax
0x18000f835  jnz     short loc_18000F83E
0x18000f837  mov     eax, 8007000Eh
0x18000f83c  jmp     short loc_18000F867
0x18000f83e  mov     rdx, [rdi]; Src
0x18000f841  test    rdx, rdx
0x18000f844  jz      short loc_18000F85E
0x18000f846  mov     r8, [rdi+10h]
0x18000f84a  mov     rcx, rsi; void *
0x18000f84d  shl     r8, 3; Size
0x18000f851  call    memmove_0
0x18000f856  mov     rcx, [rdi]; P
0x18000f859  call    ?MemFree@?$ArrayOperations@VCacheContextEntry@StateRepository@@V12@@Common@@SAXPEAPEAVCacheContextEntry@StateRepository@@@Z; Common::ArrayOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>::MemFree(StateRepository::CacheContextEntry * *)
0x18000f85e  mov     [rdi], rsi
0x18000f861  mov     [rdi+8], rbx
0x18000f865  xor     eax, eax
0x18000f867  mov     rbx, [rsp+28h+arg_0]
0x18000f86c  mov     rsi, [rsp+28h+arg_8]
0x18000f871  add     rsp, 20h
0x18000f875  pop     rdi
0x18000f876  retn
```
