# StringCbCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180002dbc`
- end: `0x180002e7c`
- name: `?StringCbCatW@@YAJPEAG_KPEBG@Z`
- size: `192`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800022a0`

## callees

- `0x180002dbc`

## pseudocode

```c
__int64 __fastcall StringCbCatW(unsigned __int16 *a1, unsigned __int64 a2, char *a3)
{
  unsigned __int64 v4; // r9
  unsigned __int64 v5; // rdx
  unsigned __int16 *v6; // rax
  __int64 result; // rax
  unsigned __int64 v8; // r8
  unsigned __int16 *v9; // rdx
  unsigned __int64 v10; // rcx
  __int64 v11; // rax
  char *v12; // r11
  unsigned __int16 v13; // r8
  unsigned __int16 *v14; // rax

  v4 = a2 >> 1;
  if ( (a2 >> 1) - 1 > 0x7FFFFFFE )
    return 2147942487LL;
  v5 = a2 >> 1;
  v6 = a1;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v5;
  }
  while ( v5 );
  result = v5 == 0 ? 0x80070057 : 0;
  if ( v5 )
    v8 = v4 - v5;
  else
    v8 = 0;
  if ( v5 )
  {
    v9 = &a1[v8];
    v10 = v4 - v8;
    if ( v4 != v8 )
    {
      v11 = 2147483646;
      v12 = (char *)(a3 - (char *)v9);
      do
      {
        if ( !v11 )
          break;
        v13 = *(unsigned __int16 *)((char *)v9 + (_QWORD)v12);
        if ( !v13 )
          break;
        *v9 = v13;
        --v11;
        ++v9;
        --v10;
      }
      while ( v10 );
    }
    v14 = v9 - 1;
    if ( v10 )
      v14 = v9;
    *v14 = 0;
    return v10 == 0 ? 0x8007007A : 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002dbc  mov     [rsp+arg_0], rbx
0x180002dc1  mov     r9, rdx
0x180002dc4  mov     r11, r8
0x180002dc7  shr     r9, 1
0x180002dca  mov     r10, rcx
0x180002dcd  lea     rax, [r9-1]
0x180002dd1  cmp     rax, 7FFFFFFEh
0x180002dd7  ja      loc_180002E71
0x180002ddd  mov     rdx, r9
0x180002de0  mov     rax, rcx
0x180002de3  xor     ebx, ebx
0x180002de5  cmp     [rax], bx
0x180002de8  jz      short loc_180002DF4
0x180002dea  add     rax, 2
0x180002dee  sub     rdx, 1
0x180002df2  jnz     short loc_180002DE5
0x180002df4  mov     rax, rdx
0x180002df7  neg     rax
0x180002dfa  sbb     eax, eax
0x180002dfc  not     eax
0x180002dfe  and     eax, 80070057h
0x180002e03  test    rdx, rdx
0x180002e06  jz      short loc_180002E10
0x180002e08  mov     r8, r9
0x180002e0b  sub     r8, rdx
0x180002e0e  jmp     short loc_180002E13
0x180002e10  mov     r8, rbx
0x180002e13  test    rdx, rdx
0x180002e16  jz      short loc_180002E76
0x180002e18  mov     rcx, r9
0x180002e1b  lea     rdx, [r10+r8*2]
0x180002e1f  sub     rcx, r8
0x180002e22  jz      short loc_180002E55
0x180002e24  sub     r8, r9
0x180002e27  lea     rax, [rcx+7FFFFFFEh]
0x180002e2e  add     rax, r8
0x180002e31  sub     r11, rdx
0x180002e34  test    rax, rax
0x180002e37  jz      short loc_180002E55
0x180002e39  movzx   r8d, word ptr [r11+rdx]
0x180002e3e  test    r8w, r8w
0x180002e42  jz      short loc_180002E55
0x180002e44  mov     [rdx], r8w
0x180002e48  dec     rax
0x180002e4b  add     rdx, 2
0x180002e4f  sub     rcx, 1
0x180002e53  jnz     short loc_180002E34
0x180002e55  test    rcx, rcx
0x180002e58  lea     rax, [rdx-2]
0x180002e5c  cmovnz  rax, rdx
0x180002e60  neg     rcx
0x180002e63  mov     [rax], bx
0x180002e66  sbb     eax, eax
0x180002e68  not     eax
0x180002e6a  and     eax, 8007007Ah
0x180002e6f  jmp     short loc_180002E76
0x180002e71  mov     eax, 80070057h
0x180002e76  mov     rbx, [rsp+arg_0]
0x180002e7b  retn
```
