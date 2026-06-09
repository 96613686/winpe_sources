# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800078fc`
- end: `0x180007967`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180018cec`

## callees

- `0x1800078fc`

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
0x1800078fc  xor     r10d, r10d
0x1800078ff  mov     r9, rcx
0x180007902  test    rdx, rdx
0x180007905  jz      short loc_180007958
0x180007907  cmp     rdx, 7FFFFFFFh
0x18000790e  jbe     short loc_180007917
0x180007910  mov     eax, 80070057h
0x180007915  jmp     short loc_180007962
0x180007917  mov     eax, 7FFFFFFEh
0x18000791c  test    rax, rax
0x18000791f  jz      short loc_18000793F
0x180007921  movzx   ecx, word ptr [r8]
0x180007925  test    cx, cx
0x180007928  jz      short loc_18000793F
0x18000792a  mov     [r9], cx
0x18000792e  add     r8, 2
0x180007932  add     r9, 2
0x180007936  dec     rax
0x180007939  sub     rdx, 1
0x18000793d  jnz     short loc_18000791C
0x18000793f  test    rdx, rdx
0x180007942  lea     rcx, [r9-2]
0x180007946  cmovnz  rcx, r9
0x18000794a  neg     rdx
0x18000794d  sbb     eax, eax
0x18000794f  not     eax
0x180007951  and     eax, 8007007Ah
0x180007956  jmp     short loc_180007962
0x180007958  mov     eax, 80070057h
0x18000795d  test    rdx, rdx
0x180007960  jz      short locret_180007966
0x180007962  mov     [rcx], r10w
0x180007966  retn
```
