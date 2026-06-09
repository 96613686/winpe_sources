# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006aa4`
- end: `0x180006b0f`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005ed0`
- `0x180017098`

## callees

- `0x180006aa4`

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
0x180006aa4  xor     r10d, r10d
0x180006aa7  mov     r9, rcx
0x180006aaa  test    rdx, rdx
0x180006aad  jz      short loc_180006B00
0x180006aaf  cmp     rdx, 7FFFFFFFh
0x180006ab6  jbe     short loc_180006ABF
0x180006ab8  mov     eax, 80070057h
0x180006abd  jmp     short loc_180006B0A
0x180006abf  mov     eax, 7FFFFFFEh
0x180006ac4  test    rax, rax
0x180006ac7  jz      short loc_180006AE7
0x180006ac9  movzx   ecx, word ptr [r8]
0x180006acd  test    cx, cx
0x180006ad0  jz      short loc_180006AE7
0x180006ad2  mov     [r9], cx
0x180006ad6  add     r8, 2
0x180006ada  add     r9, 2
0x180006ade  dec     rax
0x180006ae1  sub     rdx, 1
0x180006ae5  jnz     short loc_180006AC4
0x180006ae7  test    rdx, rdx
0x180006aea  lea     rcx, [r9-2]
0x180006aee  cmovnz  rcx, r9
0x180006af2  neg     rdx
0x180006af5  sbb     eax, eax
0x180006af7  not     eax
0x180006af9  and     eax, 8007007Ah
0x180006afe  jmp     short loc_180006B0A
0x180006b00  mov     eax, 80070057h
0x180006b05  test    rdx, rdx
0x180006b08  jz      short locret_180006B0E
0x180006b0a  mov     [rcx], r10w
0x180006b0e  retn
```
