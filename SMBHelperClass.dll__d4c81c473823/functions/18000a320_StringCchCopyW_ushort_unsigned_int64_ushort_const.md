# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000a320`
- end: `0x18000a38b`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180002974`
- `0x180005360`
- `0x18000aa6c`
- `0x18000c244`
- `0x18000ca40`
- `0x18000def4`
- `0x18000e010`
- `0x18000e10c`
- `0x18000e3b8`
- `0x18000e49c`
- `0x18000e594`
- `0x18000e6a8`
- `0x18000ea24`
- `0x18000eb74`

## callees

- `0x18000a320`

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
0x18000a320  xor     r10d, r10d
0x18000a323  mov     r9, rcx
0x18000a326  test    rdx, rdx
0x18000a329  jz      short loc_18000A37C
0x18000a32b  cmp     rdx, 7FFFFFFFh
0x18000a332  jbe     short loc_18000A33B
0x18000a334  mov     eax, 80070057h
0x18000a339  jmp     short loc_18000A386
0x18000a33b  mov     eax, 7FFFFFFEh
0x18000a340  test    rax, rax
0x18000a343  jz      short loc_18000A363
0x18000a345  movzx   ecx, word ptr [r8]
0x18000a349  test    cx, cx
0x18000a34c  jz      short loc_18000A363
0x18000a34e  mov     [r9], cx
0x18000a352  add     r8, 2
0x18000a356  add     r9, 2
0x18000a35a  dec     rax
0x18000a35d  sub     rdx, 1
0x18000a361  jnz     short loc_18000A340
0x18000a363  test    rdx, rdx
0x18000a366  lea     rcx, [r9-2]
0x18000a36a  cmovnz  rcx, r9
0x18000a36e  neg     rdx
0x18000a371  sbb     eax, eax
0x18000a373  not     eax
0x18000a375  and     eax, 8007007Ah
0x18000a37a  jmp     short loc_18000A386
0x18000a37c  mov     eax, 80070057h
0x18000a381  test    rdx, rdx
0x18000a384  jz      short locret_18000A38A
0x18000a386  mov     [rcx], r10w
0x18000a38a  retn
```
