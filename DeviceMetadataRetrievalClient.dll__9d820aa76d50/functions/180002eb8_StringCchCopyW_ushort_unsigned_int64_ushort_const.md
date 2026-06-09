# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180002eb8`
- end: `0x180002f23`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002dc8`
- `0x1800047c4`
- `0x1800049bc`
- `0x18000c708`
- `0x18000eed0`

## callees

- `0x180002eb8`

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
0x180002eb8  xor     r10d, r10d
0x180002ebb  mov     r9, rcx
0x180002ebe  test    rdx, rdx
0x180002ec1  jz      short loc_180002F14
0x180002ec3  cmp     rdx, 7FFFFFFFh
0x180002eca  jbe     short loc_180002ED3
0x180002ecc  mov     eax, 80070057h
0x180002ed1  jmp     short loc_180002F1E
0x180002ed3  mov     eax, 7FFFFFFEh
0x180002ed8  test    rax, rax
0x180002edb  jz      short loc_180002EFB
0x180002edd  movzx   ecx, word ptr [r8]
0x180002ee1  test    cx, cx
0x180002ee4  jz      short loc_180002EFB
0x180002ee6  mov     [r9], cx
0x180002eea  add     r8, 2
0x180002eee  add     r9, 2
0x180002ef2  dec     rax
0x180002ef5  sub     rdx, 1
0x180002ef9  jnz     short loc_180002ED8
0x180002efb  test    rdx, rdx
0x180002efe  lea     rcx, [r9-2]
0x180002f02  cmovnz  rcx, r9
0x180002f06  neg     rdx
0x180002f09  sbb     eax, eax
0x180002f0b  not     eax
0x180002f0d  and     eax, 8007007Ah
0x180002f12  jmp     short loc_180002F1E
0x180002f14  mov     eax, 80070057h
0x180002f19  test    rdx, rdx
0x180002f1c  jz      short locret_180002F22
0x180002f1e  mov     [rcx], r10w
0x180002f22  retn
```
