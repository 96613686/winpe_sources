# CRC32Compute(uchar *,uint,ulong)

- ea: `0x1800172dc`
- end: `0x18001730b`
- name: `?CRC32Compute@@YAKPEAEIK@Z`
- size: `47`
- prototype: `__int64 __fastcall(unsigned __int8 *, int, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800126c0`
- `0x1800156b8`
- `0x1800166cc`

## callees

- `0x1800172dc`

## pseudocode

```c
__int64 __fastcall CRC32Compute(unsigned __int8 *a1, int a2, int a3)
{
  unsigned int i; // r8d
  __int64 v4; // rax

  for ( i = ~a3; a2; --a2 )
  {
    v4 = *a1++;
    i = *((_DWORD *)qword_1800209E0 + (v4 ^ (unsigned __int8)i)) ^ (i >> 8);
  }
  return ~i;
}

```

## disassembly

```asm
0x1800172dc  not     r8d
0x1800172df  test    edx, edx
0x1800172e1  jz      short loc_180017304
0x1800172e3  movzx   eax, byte ptr [rcx]
0x1800172e6  inc     rcx
0x1800172e9  movzx   r9d, r8b
0x1800172ed  xor     r9, rax
0x1800172f0  shr     r8d, 8
0x1800172f4  lea     rax, qword_1800209E0
0x1800172fb  xor     r8d, [rax+r9*4]
0x1800172ff  add     edx, 0FFFFFFFFh
0x180017302  jnz     short loc_1800172E3
0x180017304  not     r8d
0x180017307  mov     eax, r8d
0x18001730a  retn
```
