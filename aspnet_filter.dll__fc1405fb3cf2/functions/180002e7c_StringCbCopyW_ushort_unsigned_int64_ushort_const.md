# StringCbCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180002e7c`
- end: `0x180002ee8`
- name: `?StringCbCopyW@@YAJPEAG_KPEBG@Z`
- size: `108`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800022a0`

## callees

- `0x180002e7c`

## pseudocode

```c
__int64 __fastcall StringCbCopyW(char *a1, unsigned __int64 a2, char *a3)
{
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // r9
  signed __int64 v5; // r10
  unsigned __int16 v6; // ax
  unsigned __int16 *v7; // rax
  __int64 result; // rax

  v3 = a2 >> 1;
  if ( v3 - 1 > 0x7FFFFFFE )
  {
    result = 2147942487LL;
    if ( v3 )
      *(_WORD *)a1 = 0;
  }
  else
  {
    v4 = 2147483646 - v3;
    v5 = a3 - a1;
    do
    {
      if ( !(v4 + v3) )
        break;
      v6 = *(_WORD *)&a1[v5];
      if ( !v6 )
        break;
      *(_WORD *)a1 = v6;
      a1 += 2;
      --v3;
    }
    while ( v3 );
    v7 = (unsigned __int16 *)(a1 - 2);
    if ( v3 )
      v7 = (unsigned __int16 *)a1;
    *v7 = 0;
    return v3 == 0 ? 0x8007007A : 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002e7c  shr     rdx, 1
0x180002e7f  mov     r9d, 7FFFFFFEh
0x180002e85  mov     r10, r8
0x180002e88  lea     rax, [rdx-1]
0x180002e8c  cmp     rax, r9
0x180002e8f  ja      short loc_180002ED6
0x180002e91  sub     r9, rdx
0x180002e94  sub     r10, rcx
0x180002e97  xor     r8d, r8d
0x180002e9a  lea     rax, [r9+rdx]
0x180002e9e  test    rax, rax
0x180002ea1  jz      short loc_180002EBA
0x180002ea3  movzx   eax, word ptr [r10+rcx]
0x180002ea8  test    ax, ax
0x180002eab  jz      short loc_180002EBA
0x180002ead  mov     [rcx], ax
0x180002eb0  add     rcx, 2
0x180002eb4  sub     rdx, 1
0x180002eb8  jnz     short loc_180002E9A
0x180002eba  test    rdx, rdx
0x180002ebd  lea     rax, [rcx-2]
0x180002ec1  cmovnz  rax, rcx
0x180002ec5  neg     rdx
0x180002ec8  mov     [rax], r8w
0x180002ecc  sbb     eax, eax
0x180002ece  not     eax
0x180002ed0  and     eax, 8007007Ah
0x180002ed5  retn
0x180002ed6  xor     r8d, r8d
0x180002ed9  mov     eax, 80070057h
0x180002ede  test    rdx, rdx
0x180002ee1  jz      short locret_180002EE7
0x180002ee3  mov     [rcx], r8w
0x180002ee7  retn
```
