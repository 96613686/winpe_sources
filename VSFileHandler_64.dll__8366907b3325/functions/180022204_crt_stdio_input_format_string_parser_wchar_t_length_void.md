# __crt_stdio_input::format_string_parser<wchar_t>::length(void)

- ea: `0x180022204`
- end: `0x18002229d`
- name: `?length@?$format_string_parser@_W@__crt_stdio_input@@QEBA_KXZ`
- size: `153`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180022480`
- `0x1800225a0`
- `0x1800226c4`
- `0x180022734`
- `0x180022b20`
- `0x180022bac`
- `0x180023b40`
- `0x180023bb8`

## callees

- `0x180022204`

## pseudocode

```c
__int64 __fastcall __crt_stdio_input::format_string_parser<wchar_t>::length(__int64 a1)
{
  int v1; // eax
  __int64 v2; // rdx
  int v4; // eax
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  bool v8; // zf
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx

  v1 = *(_DWORD *)(a1 + 48);
  if ( v1 < 0 )
    return 0;
  if ( v1 > 1 )
  {
    v2 = 8;
    if ( v1 <= 6 )
    {
LABEL_13:
      v5 = *(_DWORD *)(a1 + 40);
      if ( v5 > 5 )
      {
        v10 = v5 - 6;
        if ( !v10 )
          return v2;
        v11 = v10 - 1;
        if ( !v11 )
          return v2;
        v9 = v11 - 2;
        v8 = v9 == 0;
LABEL_19:
        if ( !v8 )
        {
          if ( v9 != 1 )
            return 0;
          return v2;
        }
        return 4;
      }
      if ( v5 == 5 )
        return v2;
      if ( v5 )
      {
        v6 = v5 - 1;
        if ( !v6 )
          return 1;
        v7 = v6 - 1;
        if ( v7 )
        {
          v9 = v7 - 1;
          v8 = v9 == 0;
          goto LABEL_19;
        }
        return 2;
      }
      return 4;
    }
    if ( v1 == 7 )
    {
      v4 = *(_DWORD *)(a1 + 40);
      if ( v4 )
      {
        if ( v4 != 3 && v4 != 8 )
          return 0;
        return v2;
      }
      return 4;
    }
    if ( v1 != 8 )
    {
      if ( v1 != 9 )
        return 0;
      goto LABEL_13;
    }
  }
  return (*(_BYTE *)(a1 + 44) != 0) + 1LL;
}

```

## disassembly

```asm
0x180022204  mov     eax, [rcx+30h]
0x180022207  xor     r8d, r8d
0x18002220a  test    eax, eax
0x18002220c  js      short loc_18002222A
0x18002220e  cmp     eax, 1
0x180022211  jle     short loc_18002228E
0x180022213  lea     edx, [r8+8]
0x180022217  cmp     eax, 6
0x18002221a  jle     short loc_180022241
0x18002221c  cmp     eax, 7
0x18002221f  jz      short loc_18002222D
0x180022221  cmp     eax, edx
0x180022223  jz      short loc_18002228E
0x180022225  cmp     eax, 9
0x180022228  jz      short loc_180022241
0x18002222a  xor     eax, eax
0x18002222c  retn
0x18002222d  mov     eax, [rcx+28h]
0x180022230  test    eax, eax
0x180022232  jz      short loc_180022285
0x180022234  cmp     eax, 3
0x180022237  jz      short loc_18002228A
0x180022239  cmp     eax, edx
0x18002223b  cmovnz  rdx, r8
0x18002223f  jmp     short loc_18002228A
0x180022241  mov     ecx, [rcx+28h]
0x180022244  cmp     ecx, 5
0x180022247  jg      short loc_180022276
0x180022249  jz      short loc_18002228A
0x18002224b  test    ecx, ecx
0x18002224d  jz      short loc_180022285
0x18002224f  sub     ecx, 1
0x180022252  jz      short loc_18002226F
0x180022254  sub     ecx, 1
0x180022257  jz      short loc_180022268
0x180022259  sub     ecx, 1
0x18002225c  jz      short loc_180022285
0x18002225e  cmp     ecx, 1
0x180022261  jz      short loc_18002228A
0x180022263  mov     rdx, r8
0x180022266  jmp     short loc_18002228A
0x180022268  mov     edx, 2
0x18002226d  jmp     short loc_18002228A
0x18002226f  mov     edx, 1
0x180022274  jmp     short loc_18002228A
0x180022276  sub     ecx, 6
0x180022279  jz      short loc_18002228A
0x18002227b  sub     ecx, 1
0x18002227e  jz      short loc_18002228A
0x180022280  sub     ecx, 2
0x180022283  jmp     short loc_18002225C
0x180022285  mov     edx, 4
0x18002228a  mov     rax, rdx
0x18002228d  retn
0x18002228e  mov     al, [rcx+2Ch]
0x180022291  neg     al
0x180022293  sbb     rax, rax
0x180022296  neg     rax
0x180022299  inc     rax
0x18002229c  retn
```
