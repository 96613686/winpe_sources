# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180008438`
- end: `0x1800084a3`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180016de4`
- `0x18001a82c`
- `0x180028ef0`
- `0x18002c7bc`
- `0x18002f2c4`
- `0x1800312c4`
- `0x180031c24`
- `0x1800322bc`
- `0x180032688`
- `0x18003291c`
- `0x180032b8c`
- `0x180032d88`
- `0x180033184`

## callees

- `0x180008438`

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
0x180008438  xor     r10d, r10d
0x18000843b  mov     r9, rcx
0x18000843e  test    rdx, rdx
0x180008441  jz      short loc_180008494
0x180008443  cmp     rdx, 7FFFFFFFh
0x18000844a  jbe     short loc_180008453
0x18000844c  mov     eax, 80070057h
0x180008451  jmp     short loc_18000849E
0x180008453  mov     eax, 7FFFFFFEh
0x180008458  test    rax, rax
0x18000845b  jz      short loc_18000847B
0x18000845d  movzx   ecx, word ptr [r8]
0x180008461  test    cx, cx
0x180008464  jz      short loc_18000847B
0x180008466  mov     [r9], cx
0x18000846a  add     r8, 2
0x18000846e  add     r9, 2
0x180008472  dec     rax
0x180008475  sub     rdx, 1
0x180008479  jnz     short loc_180008458
0x18000847b  test    rdx, rdx
0x18000847e  lea     rcx, [r9-2]
0x180008482  cmovnz  rcx, r9
0x180008486  neg     rdx
0x180008489  sbb     eax, eax
0x18000848b  not     eax
0x18000848d  and     eax, 8007007Ah
0x180008492  jmp     short loc_18000849E
0x180008494  mov     eax, 80070057h
0x180008499  test    rdx, rdx
0x18000849c  jz      short locret_1800084A2
0x18000849e  mov     [rcx], r10w
0x1800084a2  retn
```
