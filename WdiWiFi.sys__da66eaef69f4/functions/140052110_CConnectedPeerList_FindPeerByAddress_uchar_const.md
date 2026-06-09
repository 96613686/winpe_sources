# CConnectedPeerList::FindPeerByAddress(uchar * const)

- ea: `0x140052110`
- end: `0x140052171`
- name: `?FindPeerByAddress@CConnectedPeerList@@UEAAPEAVCConnectedPeer@@QEAE@Z`
- size: `97`
- prototype: `struct CConnectedPeer *(CConnectedPeerList *__hidden this, unsigned __int8 *const)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140052110`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140052145`
- `ntoskrnl!RtlCompareMemory` at `0x140052145`

## pseudocode

```c
struct CConnectedPeer *__fastcall CConnectedPeerList::FindPeerByAddress(
        CConnectedPeerList *this,
        unsigned __int8 *const a2)
{
  __int64 i; // rbx
  CConnectedPeer *m_pPeerTable; // rax

  for ( i = 0; (unsigned int)i < this->m_MaxPeerCount; i = (unsigned int)(i + 1) )
  {
    m_pPeerTable = this->m_pPeerTable;
    if ( m_pPeerTable[i].m_IsValid && RtlCompareMemory(m_pPeerTable[i].m_MacAddress, a2, 6u) == 6 )
      return &this->m_pPeerTable[i];
  }
  return 0;
}

```

## disassembly

```asm
0x140052110  push    rbx
0x140052112  push    rbp
0x140052113  push    rsi
0x140052114  push    rdi
0x140052115  sub     rsp, 28h
0x140052119  mov     rbp, rdx
0x14005211c  mov     rdi, rcx
0x14005211f  xor     ebx, ebx
0x140052121  cmp     ebx, [rdi+14h]
0x140052124  jnb     short loc_14005216D
0x140052126  mov     rax, [rdi+18h]
0x14005212a  lea     rsi, [rbx+rbx*8]
0x14005212e  cmp     byte ptr [rax+rsi*8], 0
0x140052132  jz      short loc_140052169
0x140052134  lea     rcx, [rax+1]
0x140052138  mov     r8d, 6; Length
0x14005213e  lea     rcx, [rcx+rsi*8]; Source1
0x140052142  mov     rdx, rbp; Source2
0x140052145  call    cs:__imp_RtlCompareMemory
0x14005214c  nop     dword ptr [rax+rax+00h]
0x140052151  cmp     rax, 6
0x140052155  jnz     short loc_140052169
0x140052157  mov     rax, [rdi+18h]
0x14005215b  lea     rax, [rax+rsi*8]
0x14005215f  add     rsp, 28h
0x140052163  pop     rdi
0x140052164  pop     rsi
0x140052165  pop     rbp
0x140052166  pop     rbx
0x140052167  retn
0x140052169  inc     ebx
0x14005216b  jmp     short loc_140052121
0x14005216d  xor     eax, eax
0x14005216f  jmp     short loc_14005215F
```
