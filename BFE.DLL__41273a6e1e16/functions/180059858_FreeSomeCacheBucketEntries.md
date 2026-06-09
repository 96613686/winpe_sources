# FreeSomeCacheBucketEntries

- ea: `0x180059858`
- end: `0x1800598f0`
- name: `FreeSomeCacheBucketEntries`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18007f04c`

## callees

- `0x180059858`
- `0x1800598f8`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x1800598b1`
- `ntdll!RtlRemoveEntryHashTable` at `0x1800598b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059871`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059871`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800598e4`

## pseudocode

```c
void __fastcall FreeSomeCacheBucketEntries(__int64 a1, _QWORD **a2)
{
  unsigned int v3; // ebp
  _QWORD *v5; // rbx
  _QWORD *v6; // rax

  v3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 24) + 8LL));
  while ( 1 )
  {
    v5 = *a2;
    if ( *a2 == a2 || v3 >= 0x32 )
      break;
    if ( (_QWORD **)v5[1] != a2 || (v6 = (_QWORD *)*v5, *(_QWORD **)(*v5 + 8LL) != v5) )
      __fastfail(3u);
    *a2 = v6;
    v6[1] = a2;
    *(_OWORD *)v5 = 0;
    RtlRemoveEntryHashTable(*(_QWORD *)(a1 + 8), v5 - 4, 0);
    FreeCacheEntry(a1, v5 - 4);
    ++v3;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 24) + 8LL));
}

```

## disassembly

```asm
0x180059858  push    rbx
0x18005985a  push    rbp
0x18005985b  push    rsi
0x18005985c  push    rdi
0x18005985d  sub     rsp, 28h
0x180059861  mov     rsi, rcx
0x180059864  xor     ebp, ebp
0x180059866  mov     rcx, [rcx+18h]
0x18005986a  mov     rdi, rdx
0x18005986d  add     rcx, 8; lpCriticalSection
0x180059871  call    cs:__imp_EnterCriticalSection
0x180059878  nop     dword ptr [rax+rax+00h]
0x18005987d  mov     rbx, [rdi]
0x180059880  cmp     rbx, rdi
0x180059883  jz      short loc_1800598D4
0x180059885  cmp     ebp, 32h ; '2'
0x180059888  jnb     short loc_1800598D4
0x18005988a  cmp     [rbx+8], rdi
0x18005988e  jnz     short loc_1800598CD
0x180059890  mov     rax, [rbx]
0x180059893  cmp     [rax+8], rbx
0x180059897  jnz     short loc_1800598CD
0x180059899  mov     [rdi], rax
0x18005989c  lea     rdx, [rbx-20h]
0x1800598a0  mov     [rax+8], rdi
0x1800598a4  xorps   xmm0, xmm0
0x1800598a7  movups  xmmword ptr [rbx], xmm0
0x1800598aa  mov     rcx, [rsi+8]
0x1800598ae  xor     r8d, r8d
0x1800598b1  call    cs:__imp_RtlRemoveEntryHashTable
0x1800598b8  nop     dword ptr [rax+rax+00h]
0x1800598bd  lea     rdx, [rbx-20h]
0x1800598c1  mov     rcx, rsi
0x1800598c4  call    FreeCacheEntry
0x1800598c9  inc     ebp
0x1800598cb  jmp     short loc_18005987D
0x1800598cd  mov     ecx, 3
0x1800598d2  int     29h; Win8: RtlFailFast(ecx)
0x1800598d4  mov     rcx, [rsi+18h]
0x1800598d8  add     rcx, 8
0x1800598dc  add     rsp, 28h
0x1800598e0  pop     rdi
0x1800598e1  pop     rsi
0x1800598e2  pop     rbp
0x1800598e3  pop     rbx
0x1800598e4  jmp     cs:__imp_LeaveCriticalSection
```
