# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180017b20`
- end: `0x180017b97`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `119`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a140`
- `0x18000f9f0`
- `0x1800110a0`
- `0x180025f84`
- `0x180027270`
- `0x180032f00`
- `0x180067160`

## callees

- `0x180017b20`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  __int64 result; // rax
  __int64 v4; // rax
  unsigned __int16 *v5; // rax

  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*a3 )
        break;
      *a1++ = *a3++;
      --v4;
      --a2;
    }
    while ( a2 );
    v5 = a1 - 1;
    if ( a2 )
      v5 = a1;
    *v5 = 0;
    result = 2147942522LL;
    if ( a2 )
      return 0;
  }
  else
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180017b20  test    rdx, rdx
0x180017b23  jz      short loc_180017B85
0x180017b25  cmp     rdx, 7FFFFFFFh
0x180017b2c  jbe     short loc_180017B3C
0x180017b2e  xor     r8d, r8d
0x180017b31  mov     eax, 80070057h
0x180017b36  mov     [rcx], r8w
0x180017b3a  retn
0x180017b3c  mov     eax, 7FFFFFFEh
0x180017b41  test    rax, rax
0x180017b44  jz      short loc_180017B65
0x180017b46  movzx   r9d, word ptr [r8]
0x180017b4a  test    r9w, r9w
0x180017b4e  jz      short loc_180017B65
0x180017b50  mov     [rcx], r9w
0x180017b54  add     r8, 2
0x180017b58  add     rcx, 2
0x180017b5c  dec     rax
0x180017b5f  sub     rdx, 1
0x180017b63  jnz     short loc_180017B41
0x180017b65  test    rdx, rdx
0x180017b68  lea     rax, [rcx-2]
0x180017b6c  cmovnz  rax, rcx
0x180017b70  xor     r8d, r8d
0x180017b73  test    rdx, rdx
0x180017b76  mov     [rax], r8w
0x180017b7a  mov     eax, 8007007Ah
0x180017b7f  cmovnz  eax, r8d
0x180017b83  retn
0x180017b85  mov     eax, 80070057h
0x180017b8a  test    rdx, rdx
0x180017b8d  jz      short locret_180017B96
0x180017b8f  xor     r8d, r8d
0x180017b92  mov     [rcx], r8w
0x180017b96  retn
```
