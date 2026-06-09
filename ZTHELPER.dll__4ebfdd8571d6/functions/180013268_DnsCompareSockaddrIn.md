# DnsCompareSockaddrIn

- ea: `0x180013268`
- end: `0x180013297`
- name: `DnsCompareSockaddrIn`
- size: `47`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800132f0`

## callees

- `0x180013268`

## pseudocode

```c
__int64 __fastcall DnsCompareSockaddrIn(__int64 a1, __int64 a2)
{
  unsigned __int16 v2; // r8
  int v5; // edx
  bool v6; // cf
  bool v7; // zf
  unsigned int v8; // ecx

  v2 = *(_WORD *)(a1 + 2);
  if ( v2 == *(_WORD *)(a2 + 2) )
  {
    v8 = *(_DWORD *)(a2 + 4);
    v5 = 0;
    v6 = *(_DWORD *)(a1 + 4) < v8;
    v7 = *(_DWORD *)(a1 + 4) == v8;
  }
  else
  {
    v5 = 0;
    v6 = v2 < *(_WORD *)(a2 + 2);
    v7 = v2 == *(_WORD *)(a2 + 2);
  }
  LOBYTE(v5) = v6;
  return (unsigned int)(!v6 && !v7) - v5;
}

```

## disassembly

```asm
0x180013268  movzx   r8d, word ptr [rcx+2]
0x18001326d  mov     r9, rdx
0x180013270  mov     r10, rcx
0x180013273  cmp     r8w, [rdx+2]
0x180013278  jz      short loc_180013283
0x18001327a  xor     edx, edx
0x18001327c  cmp     r8w, [r9+2]
0x180013281  jmp     short loc_18001328C
0x180013283  mov     ecx, [rdx+4]
0x180013286  xor     edx, edx
0x180013288  cmp     [r10+4], ecx
0x18001328c  mov     eax, edx
0x18001328e  setb    dl
0x180013291  setnbe  al
0x180013294  sub     eax, edx
0x180013296  retn
```
