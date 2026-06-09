# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000c2d0`
- end: `0x18000c33b`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001ac0`
- `0x180004da0`
- `0x18000f7d0`
- `0x1800167c8`

## callees

- `0x18000c2d0`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 result; // rax
  __int64 v5; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v5;
      --a2;
    }
    while ( a2 );
    a1 = v3 - 1;
    if ( a2 )
      a1 = v3;
    result = a2 == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = 2147942487LL;
  }
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x18000c2d0  xor     r10d, r10d
0x18000c2d3  mov     r9, rcx
0x18000c2d6  test    rdx, rdx
0x18000c2d9  jz      short loc_18000C32C
0x18000c2db  cmp     rdx, 7FFFFFFFh
0x18000c2e2  jbe     short loc_18000C2EB
0x18000c2e4  mov     eax, 80070057h
0x18000c2e9  jmp     short loc_18000C336
0x18000c2eb  mov     eax, 7FFFFFFEh
0x18000c2f0  test    rax, rax
0x18000c2f3  jz      short loc_18000C313
0x18000c2f5  movzx   ecx, word ptr [r8]
0x18000c2f9  test    cx, cx
0x18000c2fc  jz      short loc_18000C313
0x18000c2fe  mov     [r9], cx
0x18000c302  add     r8, 2
0x18000c306  add     r9, 2
0x18000c30a  dec     rax
0x18000c30d  sub     rdx, 1
0x18000c311  jnz     short loc_18000C2F0
0x18000c313  test    rdx, rdx
0x18000c316  lea     rcx, [r9-2]
0x18000c31a  cmovnz  rcx, r9
0x18000c31e  neg     rdx
0x18000c321  sbb     eax, eax
0x18000c323  not     eax
0x18000c325  and     eax, 8007007Ah
0x18000c32a  jmp     short loc_18000C336
0x18000c32c  mov     eax, 80070057h
0x18000c331  test    rdx, rdx
0x18000c334  jz      short locret_18000C33A
0x18000c336  mov     [rcx], r10w
0x18000c33a  retn
```
