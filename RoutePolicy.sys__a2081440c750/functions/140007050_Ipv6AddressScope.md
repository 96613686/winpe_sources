# Ipv6AddressScope

- ea: `0x140007050`
- end: `0x140007109`
- name: `Ipv6AddressScope`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140006f7c`
- `0x140007280`

## callees

- `0x140007050`

## pseudocode

```c
__int64 __fastcall Ipv6AddressScope(__m128i *a1)
{
  __int8 v2; // cl
  __int64 result; // rax
  __int8 v4; // r8
  __m128i *v5; // rcx
  __m128i v6; // [rsp+0h] [rbp-18h] BYREF

  v2 = a1->m128i_i8[0];
  if ( v2 == -1 )
    return a1->m128i_i8[1] & 0xF;
  v6 = 0;
  if ( ((unsigned __int8)a1 & 1) != 0 )
  {
    v6 = *a1;
    v4 = _mm_cvtsi128_si32(v6);
  }
  else
  {
    v4 = v2;
  }
  v5 = &v6;
  if ( ((unsigned __int8)a1 & 1) == 0 )
    v5 = a1;
  if ( v4 == -2 && (v5->m128i_i8[1] & 0xC0) == 0x80
    || !v5->m128i_i16[0]
    && !v5->m128i_i16[1]
    && !v5->m128i_i16[2]
    && !v5->m128i_i16[3]
    && !v5->m128i_i16[4]
    && !v5->m128i_i16[5]
    && !v5->m128i_i16[6]
    && v5->m128i_i16[7] == 256 )
  {
    return 2;
  }
  if ( v5->m128i_i8[0] != -2 )
    return 14;
  result = 5;
  if ( (v5->m128i_i8[1] & 0xC0) != 0xC0 )
    return 14;
  return result;
}

```

## disassembly

```asm
0x140007050  sub     rsp, 18h
0x140007054  mov     rax, rcx
0x140007057  mov     cl, [rcx]
0x140007059  cmp     cl, 0FFh
0x14000705c  jnz     short loc_14000706A
0x14000705e  movzx   eax, byte ptr [rax+1]
0x140007062  and     eax, 0Fh
0x140007065  jmp     loc_140007103
0x14000706a  mov     rdx, rax
0x14000706d  xorps   xmm0, xmm0
0x140007070  movups  [rsp+18h+var_18], xmm0
0x140007074  and     edx, 1
0x140007077  jz      short loc_140007087
0x140007079  movups  xmm0, xmmword ptr [rax]
0x14000707c  movups  [rsp+18h+var_18], xmm0
0x140007080  movd    r8d, xmm0
0x140007085  jmp     short loc_14000708A
0x140007087  mov     r8b, cl
0x14000708a  xor     r9d, r9d
0x14000708d  lea     rcx, [rsp+18h+var_18]
0x140007091  test    rdx, rdx
0x140007094  mov     dl, 0C0h
0x140007096  cmovz   rcx, rax
0x14000709a  cmp     r8b, 0FEh
0x14000709e  jnz     short loc_1400070A9
0x1400070a0  mov     al, [rcx+1]
0x1400070a3  and     al, dl
0x1400070a5  cmp     al, 80h
0x1400070a7  jz      short loc_1400070E4
0x1400070a9  cmp     [rcx], r9w
0x1400070ad  jnz     short loc_1400070EB
0x1400070af  cmp     [rcx+2], r9w
0x1400070b4  jnz     short loc_1400070EB
0x1400070b6  cmp     [rcx+4], r9w
0x1400070bb  jnz     short loc_1400070EB
0x1400070bd  cmp     [rcx+6], r9w
0x1400070c2  jnz     short loc_1400070EB
0x1400070c4  cmp     [rcx+8], r9w
0x1400070c9  jnz     short loc_1400070EB
0x1400070cb  cmp     [rcx+0Ah], r9w
0x1400070d0  jnz     short loc_1400070EB
0x1400070d2  cmp     [rcx+0Ch], r9w
0x1400070d7  jnz     short loc_1400070EB
0x1400070d9  mov     eax, 100h
0x1400070de  cmp     [rcx+0Eh], ax
0x1400070e2  jnz     short loc_1400070EB
0x1400070e4  mov     eax, 2
0x1400070e9  jmp     short loc_140007103
0x1400070eb  cmp     byte ptr [rcx], 0FEh
0x1400070ee  jnz     short loc_1400070FE
0x1400070f0  mov     al, [rcx+1]
0x1400070f3  and     al, dl
0x1400070f5  cmp     al, dl
0x1400070f7  mov     eax, 5
0x1400070fc  jz      short loc_140007103
0x1400070fe  mov     eax, 0Eh
0x140007103  add     rsp, 18h
0x140007107  retn
```
