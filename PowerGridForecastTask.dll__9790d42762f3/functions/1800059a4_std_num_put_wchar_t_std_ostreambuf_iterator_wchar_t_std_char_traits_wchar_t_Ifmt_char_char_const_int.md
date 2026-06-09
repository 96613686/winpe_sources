# std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t,std::char_traits<wchar_t>>>::_Ifmt(char *,char const *,int)

- ea: `0x1800059a4`
- end: `0x180005a1d`
- name: `?_Ifmt@?$num_put@_WV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBAPEADPEADPEBDH@Z`
- size: `121`
- prototype: `_BYTE *__fastcall(__int64, _BYTE *, _BYTE *, __int16)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180007810`
- `0x1800078d0`
- `0x180007da0`
- `0x180007e60`
- `0x18001ad70`
- `0x18001ae30`
- `0x18001b300`
- `0x18001b3c0`
- `0x18001b6c0`
- `0x18001b780`
- `0x18001bc50`
- `0x18001bd10`

## callees

- `0x1800059a4`

## pseudocode

```c
_BYTE *__fastcall std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Ifmt(
        __int64 a1,
        _BYTE *a2,
        _BYTE *a3,
        __int16 a4)
{
  _BYTE *v4; // rax
  char *v5; // rcx
  int v6; // eax
  char v7; // r9
  _BYTE *result; // rax

  *a2 = 37;
  v4 = a2 + 1;
  if ( (a4 & 0x20) != 0 )
  {
    *v4 = 43;
    v4 = a2 + 2;
  }
  if ( (a4 & 8) != 0 )
    *v4++ = 35;
  v5 = v4 + 1;
  if ( *a3 == 76 )
  {
    *v4 = 73;
    *(_WORD *)v5 = 13366;
    v5 = v4 + 3;
  }
  else
  {
    *v4 = *a3;
  }
  v6 = a4 & 0xE00;
  if ( v6 == 1024 )
  {
    v7 = 111;
  }
  else if ( v6 == 2048 )
  {
    v7 = ~(8 * a4) & 0x20 | 0x58;
  }
  else
  {
    v7 = a3[1];
  }
  *v5 = v7;
  result = a2;
  v5[1] = 0;
  return result;
}

```

## disassembly

```asm
0x1800059a4  mov     byte ptr [rdx], 25h ; '%'
0x1800059a7  mov     r10, rdx
0x1800059aa  lea     rax, [rdx+1]
0x1800059ae  test    r9b, 20h
0x1800059b2  jz      short loc_1800059BA
0x1800059b4  mov     byte ptr [rax], 2Bh ; '+'
0x1800059b7  inc     rax
0x1800059ba  test    r9b, 8
0x1800059be  jz      short loc_1800059C6
0x1800059c0  mov     byte ptr [rax], 23h ; '#'
0x1800059c3  inc     rax
0x1800059c6  mov     dl, [r8]
0x1800059c9  lea     rcx, [rax+1]
0x1800059cd  cmp     dl, 4Ch ; 'L'
0x1800059d0  jz      short loc_1800059D6
0x1800059d2  mov     [rax], dl
0x1800059d4  jmp     short loc_1800059E2
0x1800059d6  mov     byte ptr [rax], 49h ; 'I'
0x1800059d9  mov     word ptr [rcx], 3436h
0x1800059de  add     rcx, 2
0x1800059e2  mov     eax, r9d
0x1800059e5  and     eax, 0E00h
0x1800059ea  cmp     eax, 400h
0x1800059ef  jnz     short loc_1800059F6
0x1800059f1  mov     r9b, 6Fh ; 'o'
0x1800059f4  jmp     short loc_180005A12
0x1800059f6  cmp     eax, 800h
0x1800059fb  jz      short loc_180005A03
0x1800059fd  mov     r9b, [r8+1]
0x180005a01  jmp     short loc_180005A12
0x180005a03  shl     r9b, 3
0x180005a07  not     r9b
0x180005a0a  and     r9b, 20h
0x180005a0e  or      r9b, 58h
0x180005a12  mov     [rcx], r9b
0x180005a15  mov     rax, r10
0x180005a18  mov     byte ptr [rcx+1], 0
0x180005a1c  retn
```
