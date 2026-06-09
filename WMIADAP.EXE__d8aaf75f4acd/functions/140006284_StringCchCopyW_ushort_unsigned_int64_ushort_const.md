# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140006284`
- end: `0x1400062ef`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x140006d24`
- `0x140006df0`
- `0x14000887c`
- `0x140009de8`
- `0x14000a67c`
- `0x14000a828`
- `0x14000a96c`
- `0x14000acd8`
- `0x14000b9c8`
- `0x14000c5b0`
- `0x14000d94c`
- `0x14000e2b8`
- `0x14000e470`
- `0x14000eca0`
- `0x14000ef8c`
- `0x140012500`
- `0x140013860`

## callees

- `0x140006284`

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
0x140006284  xor     r10d, r10d
0x140006287  mov     r9, rcx
0x14000628a  test    rdx, rdx
0x14000628d  jz      short loc_1400062E0
0x14000628f  cmp     rdx, 7FFFFFFFh
0x140006296  jbe     short loc_14000629F
0x140006298  mov     eax, 80070057h
0x14000629d  jmp     short loc_1400062EA
0x14000629f  mov     eax, 7FFFFFFEh
0x1400062a4  test    rax, rax
0x1400062a7  jz      short loc_1400062C7
0x1400062a9  movzx   ecx, word ptr [r8]
0x1400062ad  test    cx, cx
0x1400062b0  jz      short loc_1400062C7
0x1400062b2  mov     [r9], cx
0x1400062b6  add     r8, 2
0x1400062ba  add     r9, 2
0x1400062be  dec     rax
0x1400062c1  sub     rdx, 1
0x1400062c5  jnz     short loc_1400062A4
0x1400062c7  test    rdx, rdx
0x1400062ca  lea     rcx, [r9-2]
0x1400062ce  cmovnz  rcx, r9
0x1400062d2  neg     rdx
0x1400062d5  sbb     eax, eax
0x1400062d7  not     eax
0x1400062d9  and     eax, 8007007Ah
0x1400062de  jmp     short loc_1400062EA
0x1400062e0  mov     eax, 80070057h
0x1400062e5  test    rdx, rdx
0x1400062e8  jz      short locret_1400062EE
0x1400062ea  mov     [rcx], r10w
0x1400062ee  retn
```
