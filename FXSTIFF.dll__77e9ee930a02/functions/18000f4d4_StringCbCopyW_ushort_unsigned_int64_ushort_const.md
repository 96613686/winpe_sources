# StringCbCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000f4d4`
- end: `0x18000f548`
- name: `?StringCbCopyW@@YAJPEAG_KPEBG@Z`
- size: `116`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f20c`

## callees

- `0x18000f4d4`

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
    v6 = byte_18006C9A0;
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
0x18000f4d4  xor     r8d, r8d
0x18000f4d7  shr     rdx, 1
0x18000f4da  jz      short loc_18000F539
0x18000f4dc  cmp     rdx, 7FFFFFFFh
0x18000f4e3  jbe     short loc_18000F4EC
0x18000f4e5  mov     eax, 80070057h
0x18000f4ea  jmp     short loc_18000F543
0x18000f4ec  mov     eax, 7FFFFFFEh
0x18000f4f1  lea     r9, byte_18006C9A0
0x18000f4f8  test    rax, rax
0x18000f4fb  jz      short loc_18000F51C
0x18000f4fd  movzx   r10d, word ptr [r9]
0x18000f501  test    r10w, r10w
0x18000f505  jz      short loc_18000F51C
0x18000f507  mov     [rcx], r10w
0x18000f50b  add     r9, 2
0x18000f50f  add     rcx, 2
0x18000f513  dec     rax
0x18000f516  sub     rdx, 1
0x18000f51a  jnz     short loc_18000F4F8
0x18000f51c  test    rdx, rdx
0x18000f51f  lea     rax, [rcx-2]
0x18000f523  cmovnz  rax, rcx
0x18000f527  neg     rdx
0x18000f52a  mov     [rax], r8w
0x18000f52e  sbb     eax, eax
0x18000f530  not     eax
0x18000f532  and     eax, 8007007Ah
0x18000f537  retn
0x18000f539  mov     eax, 80070057h
0x18000f53e  test    rdx, rdx
0x18000f541  jz      short locret_18000F547
0x18000f543  mov     [rcx], r8w
0x18000f547  retn
```
