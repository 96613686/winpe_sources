# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005210`
- end: `0x18000525f`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `79`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003c90`
- `0x180009280`
- `0x18000c150`

## callees

- `0x180005210`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // rax
  __int64 v4; // r9
  unsigned __int16 *v5; // rdx
  __int64 result; // rax

  v3 = 2147483646;
  v4 = 260;
  do
  {
    if ( !v3 )
      break;
    if ( !*a3 )
      break;
    *a1++ = *a3++;
    --v3;
    --v4;
  }
  while ( v4 );
  v5 = a1 - 1;
  result = v4 == 0 ? 0x8007007A : 0;
  if ( v4 )
    v5 = a1;
  *v5 = 0;
  return result;
}

```

## disassembly

```asm
0x180005210  mov     eax, 7FFFFFFEh
0x180005215  mov     r9d, 104h
0x18000521b  xor     r10d, r10d
0x18000521e  test    rax, rax
0x180005221  jz      short loc_180005240
0x180005223  movzx   edx, word ptr [r8]
0x180005227  test    dx, dx
0x18000522a  jz      short loc_180005240
0x18000522c  mov     [rcx], dx
0x18000522f  add     r8, 2
0x180005233  add     rcx, 2
0x180005237  dec     rax
0x18000523a  sub     r9, 1
0x18000523e  jnz     short loc_18000521E
0x180005240  mov     rax, r9
0x180005243  lea     rdx, [rcx-2]
0x180005247  neg     rax
0x18000524a  sbb     eax, eax
0x18000524c  not     eax
0x18000524e  and     eax, 8007007Ah
0x180005253  test    r9, r9
0x180005256  cmovnz  rdx, rcx
0x18000525a  mov     [rdx], r10w
0x18000525e  retn
```
