# RtlStringCchCopyW

- ea: `0x1800160ec`
- end: `0x180016157`
- name: `RtlStringCchCopyW`
- size: `107`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180015a4c`
- `0x180015ce0`

## callees

- `0x1800160ec`

## pseudocode

```c
__int64 RtlStringCchCopyW(_WORD *a1, unsigned __int64 a2, _WORD *a3, ...)
{
  _WORD *v3; // r9
  __int64 result; // rax
  __int64 v5; // rax

  v3 = a1;
  if ( !a2 )
    return 3221225485LL;
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
    result = a2 == 0 ? 0x80000005 : 0;
  }
  else
  {
    result = 3221225485LL;
  }
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1800160ec  xor     r10d, r10d
0x1800160ef  mov     r9, rcx
0x1800160f2  test    rdx, rdx
0x1800160f5  jz      short loc_180016148
0x1800160f7  cmp     rdx, 7FFFFFFFh
0x1800160fe  jbe     short loc_180016107
0x180016100  mov     eax, 0C000000Dh
0x180016105  jmp     short loc_180016152
0x180016107  mov     eax, 7FFFFFFEh
0x18001610c  test    rax, rax
0x18001610f  jz      short loc_18001612F
0x180016111  movzx   ecx, word ptr [r8]
0x180016115  test    cx, cx
0x180016118  jz      short loc_18001612F
0x18001611a  mov     [r9], cx
0x18001611e  add     r8, 2
0x180016122  add     r9, 2
0x180016126  dec     rax
0x180016129  sub     rdx, 1
0x18001612d  jnz     short loc_18001610C
0x18001612f  test    rdx, rdx
0x180016132  lea     rcx, [r9-2]
0x180016136  cmovnz  rcx, r9
0x18001613a  neg     rdx
0x18001613d  sbb     eax, eax
0x18001613f  not     eax
0x180016141  and     eax, 80000005h
0x180016146  jmp     short loc_180016152
0x180016148  mov     eax, 0C000000Dh
0x18001614d  test    rdx, rdx
0x180016150  jz      short locret_180016156
0x180016152  mov     [rcx], r10w
0x180016156  retn
```
