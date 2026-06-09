# DnsCompareSockaddrIn6

- ea: `0x1800132a0`
- end: `0x1800132e7`
- name: `DnsCompareSockaddrIn6`
- size: `71`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800132f0`

## callees

- `0x1800132a0`
- `0x180013f0d`

## pseudocode

```c
int __fastcall DnsCompareSockaddrIn6(__int64 a1, __int64 a2)
{
  unsigned __int16 v2; // r9
  unsigned __int16 v4; // dx
  int v5; // ecx
  bool v6; // cf
  bool v7; // zf
  unsigned int v9; // edx

  v2 = *(_WORD *)(a1 + 2);
  v4 = *(_WORD *)(a2 + 2);
  if ( v2 != v4 )
  {
    v5 = 0;
    v6 = v2 < v4;
    v7 = v2 == v4;
LABEL_3:
    LOBYTE(v5) = v6;
    return (!v6 && !v7) - v5;
  }
  v9 = *(_DWORD *)(a1 + 24);
  if ( v9 != *(_DWORD *)(a2 + 24) )
  {
    v5 = 0;
    v6 = v9 < *(_DWORD *)(a2 + 24);
    v7 = v9 == *(_DWORD *)(a2 + 24);
    goto LABEL_3;
  }
  return memcmp_0((const void *)(a1 + 8), (const void *)(a2 + 8), 0x10u);
}

```

## disassembly

```asm
0x1800132a0  movzx   r9d, word ptr [rcx+2]
0x1800132a5  mov     r8, rdx
0x1800132a8  movzx   edx, word ptr [rdx+2]
0x1800132ac  cmp     r9w, dx
0x1800132b0  jz      short loc_1800132C3
0x1800132b2  xor     ecx, ecx
0x1800132b4  cmp     r9w, dx
0x1800132b8  mov     eax, ecx
0x1800132ba  setb    cl
0x1800132bd  setnbe  al
0x1800132c0  sub     eax, ecx
0x1800132c2  retn
0x1800132c3  mov     edx, [rcx+18h]
0x1800132c6  cmp     edx, [r8+18h]
0x1800132ca  jz      short loc_1800132D4
0x1800132cc  xor     ecx, ecx
0x1800132ce  cmp     edx, [r8+18h]
0x1800132d2  jmp     short loc_1800132B8
0x1800132d4  lea     rdx, [r8+8]; Buf2
0x1800132d8  add     rcx, 8; Buf1
0x1800132dc  mov     r8d, 10h; Size
0x1800132e2  jmp     memcmp_0
```
