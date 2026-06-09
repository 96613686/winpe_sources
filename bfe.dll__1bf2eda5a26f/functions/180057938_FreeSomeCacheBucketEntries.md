# FreeSomeCacheBucketEntries

- ea: `0x180057938`
- end: `0x1800579bf`
- name: `FreeSomeCacheBucketEntries`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18007c32c`

## callees

- `0x180057938`
- `0x1800579c8`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x18005798b`
- `ntdll!RtlRemoveEntryHashTable` at `0x18005798b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057951`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057951`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800579b8`

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
0x180057938  push    rbx
0x18005793a  push    rbp
0x18005793b  push    rsi
0x18005793c  push    rdi
0x18005793d  sub     rsp, 28h
0x180057941  mov     rsi, rcx
0x180057944  xor     ebp, ebp
0x180057946  mov     rcx, [rcx+18h]
0x18005794a  mov     rdi, rdx
0x18005794d  add     rcx, 8; lpCriticalSection
0x180057951  call    cs:__imp_EnterCriticalSection
0x180057957  mov     rbx, [rdi]
0x18005795a  cmp     rbx, rdi
0x18005795d  jz      short loc_1800579A8
0x18005795f  cmp     ebp, 32h ; '2'
0x180057962  jnb     short loc_1800579A8
0x180057964  cmp     [rbx+8], rdi
0x180057968  jnz     short loc_1800579A1
0x18005796a  mov     rax, [rbx]
0x18005796d  cmp     [rax+8], rbx
0x180057971  jnz     short loc_1800579A1
0x180057973  mov     [rdi], rax
0x180057976  lea     rdx, [rbx-20h]
0x18005797a  mov     [rax+8], rdi
0x18005797e  xorps   xmm0, xmm0
0x180057981  movups  xmmword ptr [rbx], xmm0
0x180057984  mov     rcx, [rsi+8]
0x180057988  xor     r8d, r8d
0x18005798b  call    cs:__imp_RtlRemoveEntryHashTable
0x180057991  lea     rdx, [rbx-20h]
0x180057995  mov     rcx, rsi
0x180057998  call    FreeCacheEntry
0x18005799d  inc     ebp
0x18005799f  jmp     short loc_180057957
0x1800579a1  mov     ecx, 3
0x1800579a6  int     29h; Win8: RtlFailFast(ecx)
0x1800579a8  mov     rcx, [rsi+18h]
0x1800579ac  add     rcx, 8
0x1800579b0  add     rsp, 28h
0x1800579b4  pop     rdi
0x1800579b5  pop     rsi
0x1800579b6  pop     rbp
0x1800579b7  pop     rbx
0x1800579b8  jmp     cs:__imp_LeaveCriticalSection
```
