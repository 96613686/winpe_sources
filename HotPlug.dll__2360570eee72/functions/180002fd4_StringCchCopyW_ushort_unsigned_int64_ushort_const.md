# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180002fd4`
- end: `0x18000303f`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005140`
- `0x180005610`
- `0x180005c80`
- `0x180006eac`

## callees

- `0x180002fd4`

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
0x180002fd4  xor     r10d, r10d
0x180002fd7  mov     r9, rcx
0x180002fda  test    rdx, rdx
0x180002fdd  jz      short loc_180003030
0x180002fdf  cmp     rdx, 7FFFFFFFh
0x180002fe6  jbe     short loc_180002FEF
0x180002fe8  mov     eax, 80070057h
0x180002fed  jmp     short loc_18000303A
0x180002fef  mov     eax, 7FFFFFFEh
0x180002ff4  test    rax, rax
0x180002ff7  jz      short loc_180003017
0x180002ff9  movzx   ecx, word ptr [r8]
0x180002ffd  test    cx, cx
0x180003000  jz      short loc_180003017
0x180003002  mov     [r9], cx
0x180003006  add     r8, 2
0x18000300a  add     r9, 2
0x18000300e  dec     rax
0x180003011  sub     rdx, 1
0x180003015  jnz     short loc_180002FF4
0x180003017  test    rdx, rdx
0x18000301a  lea     rcx, [r9-2]
0x18000301e  cmovnz  rcx, r9
0x180003022  neg     rdx
0x180003025  sbb     eax, eax
0x180003027  not     eax
0x180003029  and     eax, 8007007Ah
0x18000302e  jmp     short loc_18000303A
0x180003030  mov     eax, 80070057h
0x180003035  test    rdx, rdx
0x180003038  jz      short locret_18000303E
0x18000303a  mov     [rcx], r10w
0x18000303e  retn
```
