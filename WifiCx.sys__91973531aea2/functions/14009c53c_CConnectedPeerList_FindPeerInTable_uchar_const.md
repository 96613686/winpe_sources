# CConnectedPeerList::FindPeerInTable(uchar * const)

- ea: `0x14009c53c`
- end: `0x14009c5a0`
- name: `?FindPeerInTable@CConnectedPeerList@@AEAAPEAVCConnectedPeer@@QEAE@Z`
- size: `100`
- prototype: `struct CConnectedPeer *(CConnectedPeerList *__hidden this, unsigned __int8 *const)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14009c3d0`
- `0x14009c498`

## callees

- `0x14009c53c`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14009c571`
- `ntoskrnl!RtlCompareMemory` at `0x14009c571`

## pseudocode

```c
struct CConnectedPeer *__fastcall CConnectedPeerList::FindPeerInTable(
        CConnectedPeerList *this,
        unsigned __int8 *const a2)
{
  __int64 v2; // rsi
  __int64 i; // rbx

  v2 = 0;
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 5); i = (unsigned int)(i + 1) )
  {
    if ( RtlCompareMemory(a2, (const void *)(80 * i + *((_QWORD *)this + 3) + 1LL), 6u) == 6 )
      v2 = 80 * i + *((_QWORD *)this + 3);
  }
  return (struct CConnectedPeer *)v2;
}

```

## disassembly

```asm
0x14009c53c  push    rbx
0x14009c53e  push    rbp
0x14009c53f  push    rsi
0x14009c540  push    rdi
0x14009c541  push    r14
0x14009c543  sub     rsp, 20h
0x14009c547  xor     esi, esi
0x14009c549  xor     ebx, ebx
0x14009c54b  mov     rbp, rdx
0x14009c54e  mov     rdi, rcx
0x14009c551  cmp     [rcx+14h], ebx
0x14009c554  jbe     short loc_14009C591
0x14009c556  mov     rdx, [rdi+18h]
0x14009c55a  lea     r14, [rbx+rbx*4]
0x14009c55e  inc     rdx
0x14009c561  shl     r14, 4
0x14009c565  add     rdx, r14; Source2
0x14009c568  mov     r8d, 6; Length
0x14009c56e  mov     rcx, rbp; Source1
0x14009c571  call    cs:__imp_RtlCompareMemory
0x14009c578  nop     dword ptr [rax+rax+00h]
0x14009c57d  cmp     rax, 6
0x14009c581  jnz     short loc_14009C58A
0x14009c583  mov     rsi, [rdi+18h]
0x14009c587  add     rsi, r14
0x14009c58a  inc     ebx
0x14009c58c  cmp     ebx, [rdi+14h]
0x14009c58f  jb      short loc_14009C556
0x14009c591  mov     rax, rsi
0x14009c594  add     rsp, 20h
0x14009c598  pop     r14
0x14009c59a  pop     rdi
0x14009c59b  pop     rsi
0x14009c59c  pop     rbp
0x14009c59d  pop     rbx
0x14009c59e  retn
```
