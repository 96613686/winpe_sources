# GetFieldString(ushort const *,int,ushort *,int)

- ea: `0x180015c74`
- end: `0x180015d2b`
- name: `?GetFieldString@@YAHPEBGHPEAGH@Z`
- size: `183`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, unsigned __int16 *, int)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a24c`
- `0x18000d564`
- `0x1800152d8`
- `0x180015aa0`
- `0x180016c0c`

## callees

- `0x180002268`
- `0x180015c74`

## pseudocode

```c
__int64 __fastcall GetFieldString(unsigned __int16 *a1, int a2, unsigned __int16 *a3, int a4)
{
  unsigned __int64 v5; // r10
  unsigned __int64 v7; // rcx
  __int64 v8; // r9
  unsigned __int16 v9; // ax
  const unsigned __int16 *i; // rcx
  int v11; // edx

  v5 = a4;
  while ( a2 > 0 )
  {
    if ( *(_BYTE *)a1 <= 0xDu )
      return 0;
    v7 = *a1;
    if ( (unsigned int)v7 <= 0x3D && (v8 = 0x2000100100000000LL, _bittest64(&v8, v7)) )
    {
      --a2;
      while ( (_WORD)v7 == 61 || (_WORD)v7 == 44 || (_WORD)v7 == 32 && *(_BYTE *)a1 > 0xDu )
        LOWORD(v7) = *++a1;
    }
    else
    {
      ++a1;
    }
  }
  if ( !a2 )
  {
    v9 = *a1;
    for ( i = a1; v9 != 61 && v9 != 44 && v9 != 32 && *(_BYTE *)i > 0xDu; v9 = *i )
      ++i;
    v11 = i - a1 + 2;
    if ( v11 <= 2 * (int)v5 )
    {
      StringCchCopyNW(a3, v5, a1, (unsigned __int64)v11 >> 1);
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180015c74  sub     rsp, 28h
0x180015c78  mov     r11, r8
0x180015c7b  movsxd  r10, r9d
0x180015c7e  mov     r8, rcx
0x180015c81  jmp     short loc_180015CCE
0x180015c83  cmp     byte ptr [r8], 0Dh
0x180015c87  jbe     loc_180015D24
0x180015c8d  movzx   ecx, word ptr [r8]
0x180015c91  cmp     ecx, 3Dh ; '='
0x180015c94  ja      short loc_180015CCA
0x180015c96  mov     r9, 2000100100000000h
0x180015ca0  bt      r9, rcx
0x180015ca4  jnb     short loc_180015CCA
0x180015ca6  dec     edx
0x180015ca8  cmp     cx, 3Dh ; '='
0x180015cac  jz      short loc_180015CC0
0x180015cae  cmp     cx, 2Ch ; ','
0x180015cb2  jz      short loc_180015CC0
0x180015cb4  cmp     cx, 20h ; ' '
0x180015cb8  jnz     short loc_180015CCE
0x180015cba  cmp     byte ptr [r8], 0Dh
0x180015cbe  jbe     short loc_180015CCE
0x180015cc0  add     r8, 2
0x180015cc4  movzx   ecx, word ptr [r8]
0x180015cc8  jmp     short loc_180015CA8
0x180015cca  add     r8, 2; unsigned __int16 *
0x180015cce  test    edx, edx
0x180015cd0  jg      short loc_180015C83
0x180015cd2  jnz     short loc_180015D24
0x180015cd4  movzx   eax, word ptr [r8]
0x180015cd8  mov     rcx, r8
0x180015cdb  jmp     short loc_180015CF5
0x180015cdd  cmp     ax, 2Ch ; ','
0x180015ce1  jz      short loc_180015CFB
0x180015ce3  cmp     ax, 20h ; ' '
0x180015ce7  jz      short loc_180015CFB
0x180015ce9  cmp     byte ptr [rcx], 0Dh
0x180015cec  jbe     short loc_180015CFB
0x180015cee  add     rcx, 2
0x180015cf2  movzx   eax, word ptr [rcx]
0x180015cf5  cmp     ax, 3Dh ; '='
0x180015cf9  jnz     short loc_180015CDD
0x180015cfb  sub     rcx, r8
0x180015cfe  sar     rcx, 1
0x180015d01  lea     edx, [rcx+2]
0x180015d04  lea     ecx, [r10+r10]
0x180015d08  cmp     edx, ecx
0x180015d0a  jg      short loc_180015D24
0x180015d0c  movsxd  r9, edx
0x180015d0f  mov     rcx, r11; unsigned __int16 *
0x180015d12  shr     r9, 1; unsigned __int64
0x180015d15  mov     rdx, r10; unsigned __int64
0x180015d18  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180015d1d  mov     eax, 1
0x180015d22  jmp     short loc_180015D26
0x180015d24  xor     eax, eax
0x180015d26  add     rsp, 28h
0x180015d2a  retn
```
