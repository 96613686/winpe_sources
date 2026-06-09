# CopySockAddrToSockAddrStorage

- ea: `0x180001920`
- end: `0x18000199e`
- name: `CopySockAddrToSockAddrStorage`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001710`
- `0x180001e70`

## callees

- `0x180001920`
- `0x1800019b0`
- `0x18000a4c8`

## pseudocode

```c
__int64 __fastcall CopySockAddrToSockAddrStorage(__int64 a1, SOCKADDR_IN6_LH *a2)
{
  if ( a1 )
  {
    memset_0(a2, 0, 0x80u);
    *(_OWORD *)&a2->sin6_family = *(_OWORD *)a1;
    if ( *(_WORD *)a1 == 2 )
    {
      a2->sin6_port = *(_WORD *)(a1 + 2);
      a2->sin6_family = 2;
      a2->sin6_flowinfo = *(_DWORD *)(a1 + 4);
      *(_QWORD *)a2->sin6_addr.u.Byte = 0;
      return 0;
    }
    if ( *(_WORD *)a1 == 23 )
    {
      IN6ADDR_SETSOCKADDR(a2, (const IN6_ADDR *)(a1 + 8), *(SCOPE_ID *)(a1 + 24), *(_WORD *)(a1 + 2));
      return 0;
    }
  }
  return 87;
}

```

## disassembly

```asm
0x180001920  mov     [rsp+arg_0], rbx
0x180001925  push    rdi
0x180001926  sub     rsp, 20h
0x18000192a  mov     rdi, rdx
0x18000192d  mov     rbx, rcx
0x180001930  test    rcx, rcx
0x180001933  jz      short loc_180001973
0x180001935  xor     edx, edx; Val
0x180001937  mov     r8d, 80h; Size
0x18000193d  mov     rcx, rdi; void *
0x180001940  call    memset_0
0x180001945  movups  xmm0, xmmword ptr [rbx]
0x180001948  movaps  xmmword ptr [rdi], xmm0
0x18000194b  movzx   eax, word ptr [rbx]
0x18000194e  cmp     ax, 2
0x180001952  jz      short loc_180001983
0x180001954  cmp     ax, 17h
0x180001958  jnz     short loc_180001973
0x18000195a  movzx   r9d, word ptr [rbx+2]; port
0x18000195f  lea     rdx, [rbx+8]; addr
0x180001963  mov     r8d, [rbx+18h]; scope
0x180001967  mov     rcx, rdi; a
0x18000196a  call    IN6ADDR_SETSOCKADDR
0x18000196f  xor     eax, eax
0x180001971  jmp     short loc_180001978
0x180001973  mov     eax, 57h ; 'W'
0x180001978  mov     rbx, [rsp+28h+arg_0]
0x18000197d  add     rsp, 20h
0x180001981  pop     rdi
0x180001982  retn
0x180001983  movzx   eax, word ptr [rbx+2]
0x180001987  mov     [rdi+2], ax
0x18000198b  mov     word ptr [rdi], 2
0x180001990  mov     eax, [rbx+4]
0x180001993  mov     [rdi+4], eax
0x180001996  xor     eax, eax
0x180001998  mov     [rdi+8], rax
0x18000199c  jmp     short loc_18000196F
```
