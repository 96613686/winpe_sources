# ec_dec_normalize

- ea: `0x180009040`
- end: `0x1800090d9`
- name: `ec_dec_normalize`
- size: `153`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x180008eb0`
- `0x180008f80`
- `0x180008fe0`
- `0x1800090e0`
- `0x180009290`

## callees

- `0x180009040`

## pseudocode

```c
__int64 __fastcall ec_dec_normalize(__int64 a1)
{
  unsigned int v1; // r8d
  int v2; // r11d
  int v3; // ebx
  unsigned int v4; // esi
  int v5; // edi
  __int64 v6; // r9
  int v7; // r10d
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 32);
  if ( v1 <= 0x800000 )
  {
    v2 = *(_DWORD *)(a1 + 24);
    v3 = *(_DWORD *)(a1 + 44);
    v4 = *(_DWORD *)(a1 + 8);
    v5 = *(_DWORD *)(a1 + 36);
    do
    {
      v6 = *(unsigned int *)(a1 + 28);
      v2 += 8;
      v1 <<= 8;
      *(_DWORD *)(a1 + 24) = v2;
      *(_DWORD *)(a1 + 32) = v1;
      if ( (unsigned int)v6 >= v4 )
      {
        v7 = 0;
      }
      else
      {
        v7 = *(unsigned __int8 *)(v6 + *(_QWORD *)a1);
        *(_DWORD *)(a1 + 28) = v6 + 1;
      }
      *(_DWORD *)(a1 + 44) = v7;
      result = (unsigned __int8)~((v7 | (v3 << 8)) >> 1);
      v3 = v7;
      v5 = (result + (v5 << 8)) & 0x7FFFFFFF;
      *(_DWORD *)(a1 + 36) = v5;
    }
    while ( v1 <= 0x800000 );
  }
  return result;
}

```

## disassembly

```asm
0x180009040  sub     rsp, 8
0x180009044  mov     r8d, [rcx+20h]
0x180009048  cmp     r8d, 800000h
0x18000904f  ja      loc_1800090D4
0x180009055  mov     r11d, [rcx+18h]
0x180009059  mov     [rsp+8+arg_0], rbx
0x18000905e  mov     ebx, [rcx+2Ch]
0x180009061  mov     [rsp+8+arg_8], rsi
0x180009066  mov     esi, [rcx+8]
0x180009069  mov     [rsp+8+var_8], rdi
0x18000906d  mov     edi, [rcx+24h]
0x180009070  mov     r9d, [rcx+1Ch]
0x180009074  add     r11d, 8
0x180009078  shl     r8d, 8
0x18000907c  mov     [rcx+18h], r11d
0x180009080  mov     [rcx+20h], r8d
0x180009084  cmp     r9d, esi
0x180009087  jnb     short loc_18000909A
0x180009089  mov     rax, [rcx]
0x18000908c  movzx   r10d, byte ptr [r9+rax]
0x180009091  lea     eax, [r9+1]
0x180009095  mov     [rcx+1Ch], eax
0x180009098  jmp     short loc_18000909D
0x18000909a  xor     r10d, r10d
0x18000909d  shl     ebx, 8
0x1800090a0  or      ebx, r10d
0x1800090a3  shl     edi, 8
0x1800090a6  sar     ebx, 1
0x1800090a8  not     ebx
0x1800090aa  mov     [rcx+2Ch], r10d
0x1800090ae  movzx   eax, bl
0x1800090b1  mov     ebx, r10d
0x1800090b4  add     edi, eax
0x1800090b6  btr     edi, 1Fh
0x1800090ba  mov     [rcx+24h], edi
0x1800090bd  cmp     r8d, 800000h
0x1800090c4  jbe     short loc_180009070
0x1800090c6  mov     rdi, [rsp+8+var_8]
0x1800090ca  mov     rsi, [rsp+8+arg_8]
0x1800090cf  mov     rbx, [rsp+8+arg_0]
0x1800090d4  add     rsp, 8
0x1800090d8  retn
```
