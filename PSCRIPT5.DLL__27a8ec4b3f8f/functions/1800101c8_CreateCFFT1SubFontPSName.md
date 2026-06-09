# CreateCFFT1SubFontPSName

- ea: `0x1800101c8`
- end: `0x180010365`
- name: `CreateCFFT1SubFontPSName`
- size: `413`
- prototype: `_BYTE *__fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001036c`

## callees

- `0x180001f20`
- `0x180002938`
- `0x1800101c8`
- `0x1800118c4`
- `0x180017644`

## import_xrefs

- `GDI32!FONTOBJ_pifi` at `0x180010233`
- `GDI32!FONTOBJ_pifi` at `0x180010233`

## pseudocode

```c
_BYTE *__fastcall CreateCFFT1SubFontPSName(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rdi
  __int64 v7; // r8
  int v8; // eax
  IFIMETRICS *v9; // rax
  BYTE jWinCharSet; // al
  int v11; // r8d
  __int64 v12; // r9
  __int64 v13; // rcx
  _BYTE *v14; // r10
  __int64 v15; // rax
  char *v16; // rcx
  _BYTE *result; // rax
  __int16 v18; // dx
  char v19[128]; // [rsp+40h] [rbp-A8h] BYREF

  v6 = 128;
  memset_0(v19, 0, sizeof(v19));
  VGetPSName(a1, v19, v7, 0);
  v8 = *(_DWORD *)(a2 + 192);
  if ( (v8 & 0x40) != 0 )
  {
    v9 = *(IFIMETRICS **)(a1 + 3544);
    if ( !v9 )
    {
      v9 = FONTOBJ_pifi(*(FONTOBJ **)(a1 + 3536));
      *(_QWORD *)(a1 + 3544) = v9;
    }
    jWinCharSet = v9->jWinCharSet;
    v11 = (unsigned __int8)((jWinCharSet & 0xF) + 65);
    v12 = (unsigned __int8)((jWinCharSet >> 4) + 65);
    v13 = a3 + 10;
    return (_BYTE *)OPSprintf(v13, 128, "ADCF%c%c+%s", v12, v11, v19);
  }
  v14 = (_BYTE *)(a3 + 10);
  if ( (v8 & 0x10) != 0 )
  {
    v15 = 2147483646;
    v16 = v19;
    do
    {
      if ( !v15 )
        break;
      if ( !*v16 )
        break;
      *v14++ = *v16++;
      --v15;
      --v6;
    }
    while ( v6 );
    result = v14 - 1;
    if ( v6 )
      result = v14;
    *result = 0;
  }
  else
  {
    v18 = *(_WORD *)(a3 + 8);
    v11 = (unsigned __int8)((v18 & 0xF) + 65);
    if ( v18 < 256 )
    {
      v12 = ((*(__int16 *)(a3 + 8) >> 4) & 0xFu) + 65;
      v13 = a3 + 10;
      return (_BYTE *)OPSprintf(v13, 128, "ADCF%c%c+%s", v12, v11, v19);
    }
    return (_BYTE *)OPSprintf(
                      a3 + 10,
                      128,
                      "AD%c%c%c%c+%s",
                      ((v18 >> 12) & 0xFu) + 65,
                      ((v18 >> 8) & 0xFu) + 65,
                      ((*(__int16 *)(a3 + 8) >> 4) & 0xFu) + 65,
                      (unsigned __int8)((*(_WORD *)(a3 + 8) & 0xF) + 65),
                      v19);
  }
  return result;
}

```

## disassembly

```asm
0x1800101c8  mov     [rsp+arg_8], rbx
0x1800101cd  push    rbp
0x1800101ce  push    rsi
0x1800101cf  push    rdi
0x1800101d0  sub     rsp, 0D0h
0x1800101d7  mov     rax, cs:__security_cookie
0x1800101de  xor     rax, rsp
0x1800101e1  mov     [rsp+0E8h+var_28], rax
0x1800101e9  mov     rbp, r8
0x1800101ec  mov     rbx, rdx
0x1800101ef  mov     rsi, rcx
0x1800101f2  mov     edi, 80h
0x1800101f7  mov     r8d, edi; Size
0x1800101fa  lea     rcx, [rsp+0E8h+var_A8]; void *
0x1800101ff  xor     edx, edx; Val
0x180010201  call    memset_0
0x180010206  xor     r9d, r9d
0x180010209  lea     rdx, [rsp+0E8h+var_A8]
0x18001020e  mov     rcx, rsi
0x180010211  call    VGetPSName
0x180010216  mov     eax, [rbx+0C0h]
0x18001021c  test    al, 40h
0x18001021e  jz      short loc_180010263
0x180010220  mov     rax, [rsi+0DD8h]
0x180010227  test    rax, rax
0x18001022a  jnz     short loc_180010246
0x18001022c  mov     rcx, [rsi+0DD0h]; pfo
0x180010233  call    cs:__imp_FONTOBJ_pifi
0x18001023a  nop     dword ptr [rax+rax+00h]
0x18001023f  mov     [rsi+0DD8h], rax
0x180010246  mov     cl, [rax+2Ch]
0x180010249  mov     al, cl
0x18001024b  shr     cl, 4
0x18001024e  and     al, 0Fh
0x180010250  add     al, 41h ; 'A'
0x180010252  add     cl, 41h ; 'A'
0x180010255  movzx   r8d, al
0x180010259  movzx   r9d, cl
0x18001025d  lea     rcx, [rbp+0Ah]
0x180010261  jmp     short loc_1800102D6
0x180010263  lea     r10, [rbp+0Ah]
0x180010267  test    al, 10h
0x180010269  jz      short loc_1800102A5
0x18001026b  mov     eax, 7FFFFFFEh
0x180010270  lea     rcx, [rsp+0E8h+var_A8]
0x180010275  test    rax, rax
0x180010278  jz      short loc_180010292
0x18001027a  mov     dl, [rcx]
0x18001027c  test    dl, dl
0x18001027e  jz      short loc_180010292
0x180010280  mov     [r10], dl
0x180010283  inc     rcx
0x180010286  inc     r10
0x180010289  dec     rax
0x18001028c  sub     rdi, 1
0x180010290  jnz     short loc_180010275
0x180010292  test    rdi, rdi
0x180010295  lea     rax, [r10-1]
0x180010299  cmovnz  rax, r10
0x18001029d  mov     byte ptr [rax], 0
0x1800102a0  jmp     loc_180010341
0x1800102a5  movzx   edx, word ptr [rbp+8]
0x1800102a9  mov     al, dl
0x1800102ab  and     al, 0Fh
0x1800102ad  add     al, 41h ; 'A'
0x1800102af  movzx   r8d, al
0x1800102b3  movzx   eax, dx
0x1800102b6  sar     ax, 4
0x1800102ba  and     ax, 0Fh
0x1800102be  movzx   r11d, ax
0x1800102c2  mov     eax, 100h
0x1800102c7  add     r11d, 41h ; 'A'
0x1800102cb  cmp     dx, ax
0x1800102ce  jge     short loc_1800102F6
0x1800102d0  mov     r9d, r11d
0x1800102d3  mov     rcx, r10
0x1800102d6  lea     rax, [rsp+0E8h+var_A8]
0x1800102db  mov     rdx, rdi
0x1800102de  mov     [rsp+0E8h+var_C0], rax
0x1800102e3  mov     [rsp+0E8h+var_C8], r8d
0x1800102e8  lea     r8, aAdcfCCS; "ADCF%c%c+%s"
0x1800102ef  call    OPSprintf
0x1800102f4  jmp     short loc_180010341
0x1800102f6  movzx   eax, dx
0x1800102f9  sar     dx, 0Ch
0x1800102fd  sar     ax, 8
0x180010301  and     dx, 0Fh
0x180010305  and     ax, 0Fh
0x180010309  movzx   r9d, dx
0x18001030d  movzx   ecx, ax
0x180010310  add     r9d, 41h ; 'A'
0x180010314  add     ecx, 41h ; 'A'
0x180010317  lea     rax, [rsp+0E8h+var_A8]
0x18001031c  mov     [rsp+0E8h+var_B0], rax
0x180010321  mov     rdx, rdi
0x180010324  mov     [rsp+0E8h+var_B8], r8d
0x180010329  lea     r8, aAdCCCCS; "AD%c%c%c%c+%s"
0x180010330  mov     dword ptr [rsp+0E8h+var_C0], r11d
0x180010335  mov     [rsp+0E8h+var_C8], ecx
0x180010339  mov     rcx, r10
0x18001033c  call    OPSprintf
0x180010341  mov     rcx, [rsp+0E8h+var_28]
0x180010349  xor     rcx, rsp; StackCookie
0x18001034c  call    __security_check_cookie
0x180010351  mov     rbx, [rsp+0E8h+arg_8]
0x180010359  add     rsp, 0D0h
0x180010360  pop     rdi
0x180010361  pop     rsi
0x180010362  pop     rbp
0x180010363  retn
```
