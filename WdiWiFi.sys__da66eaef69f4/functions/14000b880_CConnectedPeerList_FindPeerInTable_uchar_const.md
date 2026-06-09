# CConnectedPeerList::FindPeerInTable(uchar * const)

- ea: `0x14000b880`
- end: `0x14000b8e2`
- name: `?FindPeerInTable@CConnectedPeerList@@AEAAPEAVCConnectedPeer@@QEAE@Z`
- size: `98`
- prototype: `struct CConnectedPeer *(CConnectedPeerList *__hidden this, unsigned __int8 *const)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000b520`
- `0x14000b7c4`

## callees

- `0x14000b880`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000b8b2`
- `ntoskrnl!RtlCompareMemory` at `0x14000b8b2`

## pseudocode

```c
struct CConnectedPeer *__fastcall CConnectedPeerList::FindPeerInTable(
        CConnectedPeerList *this,
        unsigned __int8 *const a2)
{
  CConnectedPeer *v2; // rsi
  __int64 i; // rbx

  v2 = 0;
  for ( i = 0; (unsigned int)i < this->m_MaxPeerCount; i = (unsigned int)(i + 1) )
  {
    if ( RtlCompareMemory(a2, this->m_pPeerTable[i].m_MacAddress, 6u) == 6 )
      v2 = &this->m_pPeerTable[i];
  }
  return v2;
}

```

## disassembly

```asm
0x14000b880  push    rbx
0x14000b882  push    rbp
0x14000b883  push    rsi
0x14000b884  push    rdi
0x14000b885  push    r14
0x14000b887  sub     rsp, 20h
0x14000b88b  xor     esi, esi
0x14000b88d  xor     ebx, ebx
0x14000b88f  mov     r14, rdx
0x14000b892  mov     rdi, rcx
0x14000b895  cmp     [rcx+14h], ebx
0x14000b898  jbe     short loc_14000B8D3
0x14000b89a  mov     rdx, [rdi+18h]
0x14000b89e  lea     rbp, [rbx+rbx*8]
0x14000b8a2  inc     rdx
0x14000b8a5  mov     r8d, 6; Length
0x14000b8ab  mov     rcx, r14; Source1
0x14000b8ae  lea     rdx, [rdx+rbp*8]; Source2
0x14000b8b2  call    cs:__imp_RtlCompareMemory
0x14000b8b9  nop     dword ptr [rax+rax+00h]
0x14000b8be  cmp     rax, 6
0x14000b8c2  jnz     short loc_14000B8CC
0x14000b8c4  mov     rax, [rdi+18h]
0x14000b8c8  lea     rsi, [rax+rbp*8]
0x14000b8cc  inc     ebx
0x14000b8ce  cmp     ebx, [rdi+14h]
0x14000b8d1  jb      short loc_14000B89A
0x14000b8d3  mov     rax, rsi
0x14000b8d6  add     rsp, 20h
0x14000b8da  pop     r14
0x14000b8dc  pop     rdi
0x14000b8dd  pop     rsi
0x14000b8de  pop     rbp
0x14000b8df  pop     rbx
0x14000b8e0  retn
```
