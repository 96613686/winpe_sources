# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000da80`
- end: `0x18000daeb`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180007dd0`
- `0x18000d630`
- `0x18000e1c0`
- `0x180013ed0`
- `0x180016158`

## callees

- `0x18000da80`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 v4; // rax
  __int64 result; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
  }
  else
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v4;
      --a2;
    }
    while ( a2 );
    a1 = v3 - 1;
    if ( a2 )
      a1 = v3;
    result = a2 == 0 ? 0x8007007A : 0;
  }
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x18000da80  xor     r10d, r10d
0x18000da83  mov     r9, rcx
0x18000da86  test    rdx, rdx
0x18000da89  jz      short loc_18000DADF
0x18000da8b  cmp     rdx, 7FFFFFFFh
0x18000da92  ja      short loc_18000DAD8
0x18000da94  mov     eax, 7FFFFFFEh
0x18000da99  test    rax, rax
0x18000da9c  jz      short loc_18000DABC
0x18000da9e  movzx   ecx, word ptr [r8]
0x18000daa2  test    cx, cx
0x18000daa5  jz      short loc_18000DABC
0x18000daa7  mov     [r9], cx
0x18000daab  add     r8, 2
0x18000daaf  add     r9, 2
0x18000dab3  dec     rax
0x18000dab6  sub     rdx, 1
0x18000daba  jnz     short loc_18000DA99
0x18000dabc  test    rdx, rdx
0x18000dabf  lea     rcx, [r9-2]
0x18000dac3  cmovnz  rcx, r9
0x18000dac7  neg     rdx
0x18000daca  sbb     eax, eax
0x18000dacc  not     eax
0x18000dace  and     eax, 8007007Ah
0x18000dad3  mov     [rcx], r10w
0x18000dad7  retn
0x18000dad8  mov     eax, 80070057h
0x18000dadd  jmp     short loc_18000DAD3
0x18000dadf  mov     eax, 80070057h
0x18000dae4  test    rdx, rdx
0x18000dae7  jz      short locret_18000DAD7
0x18000dae9  jmp     short loc_18000DAD3
```
