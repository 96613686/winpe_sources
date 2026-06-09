# av_adler32_update

- ea: `0x180029a50`
- end: `0x180029af9`
- name: `av_adler32_update`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18003ccd0`

## callees

- `0x180029a50`

## pseudocode

```c
__int64 __fastcall av_adler32_update(unsigned int a1, unsigned __int8 *a2, unsigned __int64 a3)
{
  unsigned int v3; // r11d
  unsigned int v4; // r9d
  unsigned __int64 i; // rbx
  unsigned int v7; // r8d
  unsigned int v8; // edx
  unsigned int v9; // ecx
  int v10; // eax
  unsigned int v11; // r11d
  unsigned int v12; // r9d

  v3 = (unsigned __int16)a1;
  v4 = HIWORD(a1);
  for ( i = a3; i; --i )
  {
    while ( i > 4 && v4 < 0x80000000 )
    {
      v7 = v3 + *a2;
      v8 = v7 + a2[1];
      v9 = v8 + a2[2];
      v3 = v9 + a2[3];
      a2 += 4;
      v4 += v3 + v7 + v9 + v8;
      i -= 4LL;
    }
    v10 = *a2++;
    v11 = v10 + v3;
    v12 = v11 + v4;
    v3 = v11 % 0xFFF1;
    v4 = v12 % 0xFFF1;
  }
  return v3 | (v4 << 16);
}

```

## disassembly

```asm
0x180029a50  mov     [rsp+arg_0], rbx
0x180029a55  mov     r9d, ecx
0x180029a58  movzx   r11d, cx
0x180029a5c  shr     r9d, 10h
0x180029a60  mov     rbx, r8
0x180029a63  mov     r10, rdx
0x180029a66  test    r8, r8
0x180029a69  jz      short loc_180029AE9
0x180029a6b  jmp     short loc_180029AA8
0x180029a6d  cmp     r9d, 80000000h
0x180029a74  jnb     short loc_180029AAE
0x180029a76  movzx   r8d, byte ptr [r10]
0x180029a7a  movzx   edx, byte ptr [r10+1]
0x180029a7f  add     r8d, r11d
0x180029a82  movzx   ecx, byte ptr [r10+2]
0x180029a87  add     edx, r8d
0x180029a8a  movzx   r11d, byte ptr [r10+3]
0x180029a8f  add     ecx, edx
0x180029a91  add     r11d, ecx
0x180029a94  add     r10, 4
0x180029a98  lea     eax, [rcx+rdx]
0x180029a9b  add     eax, r8d
0x180029a9e  add     eax, r11d
0x180029aa1  add     r9d, eax
0x180029aa4  sub     rbx, 4
0x180029aa8  cmp     rbx, 4
0x180029aac  ja      short loc_180029A6D
0x180029aae  movzx   eax, byte ptr [r10]
0x180029ab2  inc     r10
0x180029ab5  add     r11d, eax
0x180029ab8  mov     eax, 80078071h
0x180029abd  mul     r11d
0x180029ac0  add     r9d, r11d
0x180029ac3  shr     edx, 0Fh
0x180029ac6  imul    eax, edx, 0FFF1h
0x180029acc  sub     r11d, eax
0x180029acf  mov     eax, 80078071h
0x180029ad4  mul     r9d
0x180029ad7  shr     edx, 0Fh
0x180029ada  imul    eax, edx, 0FFF1h
0x180029ae0  sub     r9d, eax
0x180029ae3  sub     rbx, 1
0x180029ae7  jnz     short loc_180029AA8
0x180029ae9  mov     rbx, [rsp+arg_0]
0x180029aee  shl     r9d, 10h
0x180029af2  or      r9d, r11d
0x180029af5  mov     eax, r9d
0x180029af8  retn
```
