# StringCbCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800278e8`
- end: `0x180027955`
- name: `?StringCbCopyW@@YAJPEAG_KPEBG@Z`
- size: `109`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800129e0`
- `0x180026b04`
- `0x180027e30`
- `0x18002c750`
- `0x18002d224`
- `0x180030314`

## callees

- `0x1800278e8`

## pseudocode

```c
__int64 __fastcall StringCbCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int64 v3; // rdx
  __int64 result; // rax
  __int64 v5; // rax
  unsigned __int16 *v6; // rax

  v3 = a2 >> 1;
  if ( !v3 )
    return 2147942487LL;
  if ( v3 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*a3 )
        break;
      *a1++ = *a3++;
      --v5;
      --v3;
    }
    while ( v3 );
    v6 = a1 - 1;
    if ( v3 )
      v6 = a1;
    *v6 = 0;
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
0x1800278e8  xor     r9d, r9d
0x1800278eb  shr     rdx, 1
0x1800278ee  jz      short loc_180027946
0x1800278f0  cmp     rdx, 7FFFFFFFh
0x1800278f7  jbe     short loc_180027900
0x1800278f9  mov     eax, 80070057h
0x1800278fe  jmp     short loc_180027950
0x180027900  mov     eax, 7FFFFFFEh
0x180027905  test    rax, rax
0x180027908  jz      short loc_180027929
0x18002790a  movzx   r10d, word ptr [r8]
0x18002790e  test    r10w, r10w
0x180027912  jz      short loc_180027929
0x180027914  mov     [rcx], r10w
0x180027918  add     r8, 2
0x18002791c  add     rcx, 2
0x180027920  dec     rax
0x180027923  sub     rdx, 1
0x180027927  jnz     short loc_180027905
0x180027929  test    rdx, rdx
0x18002792c  lea     rax, [rcx-2]
0x180027930  cmovnz  rax, rcx
0x180027934  neg     rdx
0x180027937  mov     [rax], r9w
0x18002793b  sbb     eax, eax
0x18002793d  not     eax
0x18002793f  and     eax, 8007007Ah
0x180027944  retn
0x180027946  mov     eax, 80070057h
0x18002794b  test    rdx, rdx
0x18002794e  jz      short locret_180027954
0x180027950  mov     [rcx], r9w
0x180027954  retn
```
