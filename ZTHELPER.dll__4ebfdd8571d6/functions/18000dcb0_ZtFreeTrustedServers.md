# ZtFreeTrustedServers

- ea: `0x18000dcb0`
- end: `0x18000dcfb`
- name: `ZtFreeTrustedServers`
- size: `75`
- prototype: `void __fastcall(unsigned int, void *)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180003e00`
- `0x1800049b0`
- `0x180006f9c`
- `0x18001036c`
- `0x1800105c0`
- `0x180010908`
- `0x180010a50`
- `0x180010c18`

## callees

- `0x18000c750`
- `0x18000dcb0`
- `0x1800125d4`

## pseudocode

```c
void __fastcall ZtFreeTrustedServers(unsigned int a1, void *a2)
{
  unsigned int i; // ebx

  if ( a2 )
  {
    for ( i = 0; i < a1; ++i )
      DnsFreeZtTrustedServerMembers((__int64)a2 + 64 * (unsigned __int64)i);
    Dns_Free(a2);
  }
}

```

## disassembly

```asm
0x18000dcb0  test    rdx, rdx
0x18000dcb3  jz      short locret_18000DCFA
0x18000dcb5  mov     [rsp+arg_0], rbx
0x18000dcba  mov     [rsp+arg_8], rsi
0x18000dcbf  push    rdi
0x18000dcc0  sub     rsp, 20h
0x18000dcc4  xor     ebx, ebx
0x18000dcc6  mov     rdi, rdx
0x18000dcc9  mov     esi, ecx
0x18000dccb  test    ecx, ecx
0x18000dccd  jz      short loc_18000DCE3
0x18000dccf  mov     ecx, ebx
0x18000dcd1  shl     rcx, 6
0x18000dcd5  add     rcx, rdi
0x18000dcd8  call    DnsFreeZtTrustedServerMembers
0x18000dcdd  inc     ebx
0x18000dcdf  cmp     ebx, esi
0x18000dce1  jb      short loc_18000DCCF
0x18000dce3  mov     rcx, rdi; lpMem
0x18000dce6  call    Dns_Free
0x18000dceb  mov     rbx, [rsp+28h+arg_0]
0x18000dcf0  mov     rsi, [rsp+28h+arg_8]
0x18000dcf5  add     rsp, 20h
0x18000dcf9  pop     rdi
0x18000dcfa  retn
```
