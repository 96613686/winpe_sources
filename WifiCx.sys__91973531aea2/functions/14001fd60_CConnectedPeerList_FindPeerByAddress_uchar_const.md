# CConnectedPeerList::FindPeerByAddress(uchar * const)

- ea: `0x14001fd60`
- end: `0x14001fdc3`
- name: `?FindPeerByAddress@CConnectedPeerList@@UEAAPEAVCConnectedPeer@@QEAE@Z`
- size: `99`
- prototype: `struct CConnectedPeer *(CConnectedPeerList *__hidden this, unsigned __int8 *const)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001fd60`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14001fd98`
- `ntoskrnl!RtlCompareMemory` at `0x14001fd98`

## pseudocode

```c
struct CConnectedPeer *__fastcall CConnectedPeerList::FindPeerByAddress(
        CConnectedPeerList *this,
        unsigned __int8 *const a2)
{
  __int64 i; // rbx
  __int64 v5; // rax
  __int64 v6; // rdi

  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 5); i = (unsigned int)(i + 1) )
  {
    v5 = *((_QWORD *)this + 3);
    v6 = 80 * i;
    if ( *(_BYTE *)(v5 + 80 * i) && RtlCompareMemory((const void *)(v6 + v5 + 1), a2, 6u) == 6 )
      return (struct CConnectedPeer *)(v6 + *((_QWORD *)this + 3));
  }
  return 0;
}

```

## disassembly

```asm
0x14001fd60  push    rbx
0x14001fd62  push    rbp
0x14001fd63  push    rsi
0x14001fd64  push    rdi
0x14001fd65  sub     rsp, 28h
0x14001fd69  mov     rbp, rdx
0x14001fd6c  mov     rsi, rcx
0x14001fd6f  xor     ebx, ebx
0x14001fd71  cmp     ebx, [rsi+14h]
0x14001fd74  jnb     short loc_14001FDB7
0x14001fd76  mov     rax, [rsi+18h]
0x14001fd7a  lea     rdi, [rbx+rbx*4]
0x14001fd7e  shl     rdi, 4
0x14001fd82  cmp     byte ptr [rax+rdi], 0
0x14001fd86  jz      short loc_14001FDAA
0x14001fd88  lea     rcx, [rax+1]
0x14001fd8c  mov     r8d, 6; Length
0x14001fd92  add     rcx, rdi; Source1
0x14001fd95  mov     rdx, rbp; Source2
0x14001fd98  call    cs:__imp_RtlCompareMemory
0x14001fd9f  nop     dword ptr [rax+rax+00h]
0x14001fda4  cmp     rax, 6
0x14001fda8  jz      short loc_14001FDAE
0x14001fdaa  inc     ebx
0x14001fdac  jmp     short loc_14001FD71
0x14001fdae  mov     rax, [rsi+18h]
0x14001fdb2  add     rax, rdi
0x14001fdb5  jmp     short loc_14001FDB9
0x14001fdb7  xor     eax, eax
0x14001fdb9  add     rsp, 28h
0x14001fdbd  pop     rdi
0x14001fdbe  pop     rsi
0x14001fdbf  pop     rbp
0x14001fdc0  pop     rbx
0x14001fdc1  retn
```
