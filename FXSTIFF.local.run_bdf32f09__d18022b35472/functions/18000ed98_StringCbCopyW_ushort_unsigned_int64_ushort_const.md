# StringCbCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000ed98`
- end: `0x18000ee0b`
- name: `?StringCbCopyW@@YAJPEAG_KPEBG@Z`
- size: `115`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eafc`

## callees

- `0x18000ed98`

## pseudocode

```c
__int64 __fastcall StringCbCopyW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3)
{
  unsigned __int64 v3; // rdx
  __int64 result; // rax
  __int64 v5; // rax
  char *v6; // r9
  unsigned __int16 *v7; // rax

  v3 = a2 >> 1;
  if ( !v3 )
    return 2147942487LL;
  if ( v3 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    v6 = byte_18006C978;
    do
    {
      if ( !v5 )
        break;
      if ( !*(_WORD *)v6 )
        break;
      *a1 = *(_WORD *)v6;
      v6 += 2;
      ++a1;
      --v5;
      --v3;
    }
    while ( v3 );
    v7 = a1 - 1;
    if ( v3 )
      v7 = a1;
    *v7 = 0;
    return v3 == 0 ? 0x8007007A : 0;
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
0x18000ed98  xor     r8d, r8d
0x18000ed9b  shr     rdx, 1
0x18000ed9e  jz      short loc_18000EDFC
0x18000eda0  cmp     rdx, 7FFFFFFFh
0x18000eda7  jbe     short loc_18000EDB0
0x18000eda9  mov     eax, 80070057h
0x18000edae  jmp     short loc_18000EE06
0x18000edb0  mov     eax, 7FFFFFFEh
0x18000edb5  lea     r9, byte_18006C978
0x18000edbc  test    rax, rax
0x18000edbf  jz      short loc_18000EDE0
0x18000edc1  movzx   r10d, word ptr [r9]
0x18000edc5  test    r10w, r10w
0x18000edc9  jz      short loc_18000EDE0
0x18000edcb  mov     [rcx], r10w
0x18000edcf  add     r9, 2
0x18000edd3  add     rcx, 2
0x18000edd7  dec     rax
0x18000edda  sub     rdx, 1
0x18000edde  jnz     short loc_18000EDBC
0x18000ede0  test    rdx, rdx
0x18000ede3  lea     rax, [rcx-2]
0x18000ede7  cmovnz  rax, rcx
0x18000edeb  neg     rdx
0x18000edee  mov     [rax], r8w
0x18000edf2  sbb     eax, eax
0x18000edf4  not     eax
0x18000edf6  and     eax, 8007007Ah
0x18000edfb  retn
0x18000edfc  mov     eax, 80070057h
0x18000ee01  test    rdx, rdx
0x18000ee04  jz      short locret_18000EE0A
0x18000ee06  mov     [rcx], r8w
0x18000ee0a  retn
```
