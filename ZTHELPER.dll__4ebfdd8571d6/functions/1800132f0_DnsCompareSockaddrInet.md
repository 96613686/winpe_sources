# DnsCompareSockaddrInet

- ea: `0x1800132f0`
- end: `0x18001333d`
- name: `DnsCompareSockaddrInet`
- size: `77`
- prototype: `int __fastcall(_WORD *, _WORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010274`
- `0x180010480`
- `0x1800105c0`
- `0x180010c18`

## callees

- `0x180013268`
- `0x1800132a0`
- `0x1800132f0`

## pseudocode

```c
int __fastcall DnsCompareSockaddrInet(_WORD *a1, _WORD *a2)
{
  int result; // eax

  if ( *a1 != *a2 )
    return (*a1 > *a2) - (*a1 < *a2);
  if ( *a1 == 2 )
    return DnsCompareSockaddrIn((__int64)a1, (__int64)a2);
  result = 0;
  if ( *a1 == 23 )
    return DnsCompareSockaddrIn6((__int64)a1, (__int64)a2);
  return result;
}

```

## disassembly

```asm
0x1800132f0  sub     rsp, 28h
0x1800132f4  movzx   r9d, word ptr [rdx]
0x1800132f8  mov     r8, rcx
0x1800132fb  cmp     [rcx], r9w
0x1800132ff  jz      short loc_180013316
0x180013301  xor     ecx, ecx
0x180013303  cmp     [r8], r9w
0x180013307  mov     eax, ecx
0x180013309  setnbe  al
0x18001330c  setb    cl
0x18001330f  sub     eax, ecx
0x180013311  add     rsp, 28h
0x180013315  retn
0x180013316  cmp     word ptr [rcx], 2
0x18001331a  jz      short loc_180013333
0x18001331c  xor     ecx, ecx
0x18001331e  cmp     word ptr [r8], 17h
0x180013323  mov     eax, ecx
0x180013325  jnz     short loc_180013338
0x180013327  mov     rcx, r8
0x18001332a  add     rsp, 28h
0x18001332e  jmp     DnsCompareSockaddrIn6
0x180013333  call    DnsCompareSockaddrIn
0x180013338  add     rsp, 28h
0x18001333c  retn
```
