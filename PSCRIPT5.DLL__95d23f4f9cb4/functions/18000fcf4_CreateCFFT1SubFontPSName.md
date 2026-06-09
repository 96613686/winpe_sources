# CreateCFFT1SubFontPSName

- ea: `0x18000fcf4`
- end: `0x18000fe8a`
- name: `CreateCFFT1SubFontPSName`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000fe90`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x18000fcf4`
- `0x18001135c`
- `0x180016edc`

## import_xrefs

- `GDI32!FONTOBJ_pifi` at `0x18000fd5f`
- `GDI32!FONTOBJ_pifi` at `0x18000fd5f`

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
0x18000fcf4  mov     [rsp+arg_8], rbx
0x18000fcf9  push    rbp
0x18000fcfa  push    rsi
0x18000fcfb  push    rdi
0x18000fcfc  sub     rsp, 0D0h
0x18000fd03  mov     rax, cs:__security_cookie
0x18000fd0a  xor     rax, rsp
0x18000fd0d  mov     [rsp+0E8h+var_28], rax
0x18000fd15  mov     rbp, r8
0x18000fd18  mov     rbx, rdx
0x18000fd1b  mov     rsi, rcx
0x18000fd1e  mov     edi, 80h
0x18000fd23  mov     r8d, edi; Size
0x18000fd26  lea     rcx, [rsp+0E8h+var_A8]; void *
0x18000fd2b  xor     edx, edx; Val
0x18000fd2d  call    memset_0
0x18000fd32  xor     r9d, r9d
0x18000fd35  lea     rdx, [rsp+0E8h+var_A8]
0x18000fd3a  mov     rcx, rsi
0x18000fd3d  call    VGetPSName
0x18000fd42  mov     eax, [rbx+0C0h]
0x18000fd48  test    al, 40h
0x18000fd4a  jz      short loc_18000FD89
0x18000fd4c  mov     rax, [rsi+0DD8h]
0x18000fd53  test    rax, rax
0x18000fd56  jnz     short loc_18000FD6C
0x18000fd58  mov     rcx, [rsi+0DD0h]; pfo
0x18000fd5f  call    cs:__imp_FONTOBJ_pifi
0x18000fd65  mov     [rsi+0DD8h], rax
0x18000fd6c  mov     cl, [rax+2Ch]
0x18000fd6f  mov     al, cl
0x18000fd71  shr     cl, 4
0x18000fd74  and     al, 0Fh
0x18000fd76  add     al, 41h ; 'A'
0x18000fd78  add     cl, 41h ; 'A'
0x18000fd7b  movzx   r8d, al
0x18000fd7f  movzx   r9d, cl
0x18000fd83  lea     rcx, [rbp+0Ah]
0x18000fd87  jmp     short loc_18000FDFC
0x18000fd89  lea     r10, [rbp+0Ah]
0x18000fd8d  test    al, 10h
0x18000fd8f  jz      short loc_18000FDCB
0x18000fd91  mov     eax, 7FFFFFFEh
0x18000fd96  lea     rcx, [rsp+0E8h+var_A8]
0x18000fd9b  test    rax, rax
0x18000fd9e  jz      short loc_18000FDB8
0x18000fda0  mov     dl, [rcx]
0x18000fda2  test    dl, dl
0x18000fda4  jz      short loc_18000FDB8
0x18000fda6  mov     [r10], dl
0x18000fda9  inc     rcx
0x18000fdac  inc     r10
0x18000fdaf  dec     rax
0x18000fdb2  sub     rdi, 1
0x18000fdb6  jnz     short loc_18000FD9B
0x18000fdb8  test    rdi, rdi
0x18000fdbb  lea     rax, [r10-1]
0x18000fdbf  cmovnz  rax, r10
0x18000fdc3  mov     byte ptr [rax], 0
0x18000fdc6  jmp     loc_18000FE67
0x18000fdcb  movzx   edx, word ptr [rbp+8]
0x18000fdcf  mov     al, dl
0x18000fdd1  and     al, 0Fh
0x18000fdd3  add     al, 41h ; 'A'
0x18000fdd5  movzx   r8d, al
0x18000fdd9  movzx   eax, dx
0x18000fddc  sar     ax, 4
0x18000fde0  and     ax, 0Fh
0x18000fde4  movzx   r11d, ax
0x18000fde8  mov     eax, 100h
0x18000fded  add     r11d, 41h ; 'A'
0x18000fdf1  cmp     dx, ax
0x18000fdf4  jge     short loc_18000FE1C
0x18000fdf6  mov     r9d, r11d
0x18000fdf9  mov     rcx, r10
0x18000fdfc  lea     rax, [rsp+0E8h+var_A8]
0x18000fe01  mov     rdx, rdi
0x18000fe04  mov     [rsp+0E8h+var_C0], rax
0x18000fe09  mov     [rsp+0E8h+var_C8], r8d
0x18000fe0e  lea     r8, aAdcfCCS; "ADCF%c%c+%s"
0x18000fe15  call    OPSprintf
0x18000fe1a  jmp     short loc_18000FE67
0x18000fe1c  movzx   eax, dx
0x18000fe1f  sar     dx, 0Ch
0x18000fe23  sar     ax, 8
0x18000fe27  and     dx, 0Fh
0x18000fe2b  and     ax, 0Fh
0x18000fe2f  movzx   r9d, dx
0x18000fe33  movzx   ecx, ax
0x18000fe36  add     r9d, 41h ; 'A'
0x18000fe3a  add     ecx, 41h ; 'A'
0x18000fe3d  lea     rax, [rsp+0E8h+var_A8]
0x18000fe42  mov     [rsp+0E8h+var_B0], rax
0x18000fe47  mov     rdx, rdi
0x18000fe4a  mov     [rsp+0E8h+var_B8], r8d
0x18000fe4f  lea     r8, aAdCCCCS; "AD%c%c%c%c+%s"
0x18000fe56  mov     dword ptr [rsp+0E8h+var_C0], r11d
0x18000fe5b  mov     [rsp+0E8h+var_C8], ecx
0x18000fe5f  mov     rcx, r10
0x18000fe62  call    OPSprintf
0x18000fe67  mov     rcx, [rsp+0E8h+var_28]
0x18000fe6f  xor     rcx, rsp; StackCookie
0x18000fe72  call    __security_check_cookie
0x18000fe77  mov     rbx, [rsp+0E8h+arg_8]
0x18000fe7f  add     rsp, 0D0h
0x18000fe86  pop     rdi
0x18000fe87  pop     rsi
0x18000fe88  pop     rbp
0x18000fe89  retn
```
