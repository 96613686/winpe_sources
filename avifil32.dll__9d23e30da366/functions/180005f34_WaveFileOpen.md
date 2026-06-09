# WaveFileOpen

- ea: `0x180005f34`
- end: `0x180006164`
- name: `WaveFileOpen`
- size: `560`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180006230`

## callees

- `0x180001460`
- `0x180001d0c`
- `0x1800059c0`
- `0x180005c14`
- `0x180005f34`
- `0x180014744`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180006047`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180006047`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006025`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000603e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006025`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000603e`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180005f68`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180005fad`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180005f68`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180005fad`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x18000607d`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x18000607d`

## pseudocode

```c
__int64 __fastcall WaveFileOpen(__int64 a1, WCHAR *a2, int a3)
{
  __int64 v3; // rbx
  UINT v6; // ebp
  __int64 v7; // rdx
  _DWORD *v8; // rax
  __int64 v9; // rdx
  HINSTANCE v11; // rcx
  __int64 v12; // rbp
  const WCHAR *i; // r9
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx
  _WORD *v17; // rax
  wchar_t *v18; // rdx
  _WORD *v19; // rcx
  unsigned int v20; // ecx
  WCHAR Buffer[80]; // [rsp+20h] [rbp-2E8h] BYREF
  wchar_t pszDest[264]; // [rsp+C0h] [rbp-248h] BYREF

  v3 = a1 - 8;
  v6 = SetErrorMode(0x8000u);
  v8 = shfileOpen(a2, v7, a3 | 0x10000u);
  *(_QWORD *)(v3 + 40) = v8;
  if ( !v8 && (a3 & 3) == 0 )
  {
    a3 &= 0xFFFFFF8F;
    *(_QWORD *)(v3 + 40) = shfileOpen(a2, v9, a3 | 0x10000u);
  }
  SetErrorMode(v6);
  *(_DWORD *)(v3 + 296) = a3;
  if ( !*(_QWORD *)(v3 + 40) )
    return 2147762285LL;
  memset_0((void *)(v3 + 72), 0, 0xCCu);
  memset_0((void *)(v3 + 320), 0, 0xACu);
  v11 = ghMod;
  v12 = 64;
  *(_DWORD *)(v3 + 352) = 1000;
  *(_DWORD *)(v3 + 348) = 1;
  *(_DWORD *)(v3 + 332) = 1;
  LoadStringW(v11, 0x65u, (LPWSTR)(v3 + 364), 64);
  LoadStringW(ghMod, 0x64u, Buffer, 80);
  for ( i = &a2[lstrlenW(a2)]; i > a2; i = CharPrevW(a2, i) )
  {
    v14 = *i;
    LOWORD(v14) = v14 - 47;
    if ( (unsigned __int16)v14 <= 0x2Du )
    {
      v15 = 0x200000000801LL;
      if ( _bittest64(&v15, v14) )
        break;
    }
  }
  if ( i != a2 )
    ++i;
  StringCbPrintfW(pszDest, 0x208u, Buffer, i);
  v16 = 63;
  v17 = (_WORD *)(v3 + 148);
  v18 = pszDest;
  do
  {
    if ( !v16 )
      break;
    if ( !*v18 )
      break;
    *v17++ = *v18++;
    --v16;
    --v12;
  }
  while ( v12 );
  v19 = v17 - 1;
  if ( v12 )
    v19 = v17;
  *v19 = 0;
  *(_WORD *)(v3 + 274) = 0;
  if ( (a3 & 0x1000) != 0 )
  {
    v20 = 0;
    *(_QWORD *)(v3 + 72) = 1935963489;
    *(_DWORD *)(v3 + 80) = 0;
    *(_QWORD *)(v3 + 88) = 0;
    *(_QWORD *)(v3 + 104) = 0;
    *(_QWORD *)(v3 + 96) = 0;
    *(_DWORD *)(v3 + 112) = 0;
    *(_DWORD *)(v3 + 120) = 0;
    *(_DWORD *)(v3 + 292) = 1;
  }
  else
  {
    return (unsigned int)ParseWaveFile(v3);
  }
  return v20;
}

```

## disassembly

```asm
0x180005f34  mov     [rsp+arg_18], rbx
0x180005f39  push    rbp
0x180005f3a  push    rsi
0x180005f3b  push    rdi
0x180005f3c  push    r14
0x180005f3e  push    r15
0x180005f40  sub     rsp, 2E0h
0x180005f47  mov     rax, cs:__security_cookie
0x180005f4e  xor     rax, rsp
0x180005f51  mov     [rsp+308h+var_38], rax
0x180005f59  lea     rbx, [rcx-8]
0x180005f5d  mov     edi, r8d
0x180005f60  mov     ecx, 8000h; uMode
0x180005f65  mov     rsi, rdx
0x180005f68  call    cs:__imp_SetErrorMode
0x180005f6e  mov     r8d, edi
0x180005f71  mov     r14d, 10000h
0x180005f77  or      r8d, r14d
0x180005f7a  mov     rcx, rsi; lpFileName
0x180005f7d  mov     ebp, eax
0x180005f7f  call    shfileOpen
0x180005f84  xor     r15d, r15d
0x180005f87  mov     [rbx+28h], rax
0x180005f8b  test    rax, rax
0x180005f8e  jnz     short loc_180005FAB
0x180005f90  test    dil, 3
0x180005f94  jnz     short loc_180005FAB
0x180005f96  and     edi, 0FFFFFF8Fh
0x180005f99  mov     rcx, rsi; lpFileName
0x180005f9c  mov     r8d, edi
0x180005f9f  or      r8d, r14d
0x180005fa2  call    shfileOpen
0x180005fa7  mov     [rbx+28h], rax
0x180005fab  mov     ecx, ebp; uMode
0x180005fad  call    cs:__imp_SetErrorMode
0x180005fb3  mov     [rbx+128h], edi
0x180005fb9  cmp     [rbx+28h], r15
0x180005fbd  jnz     short loc_180005FC9
0x180005fbf  mov     eax, 8004406Dh
0x180005fc4  jmp     loc_18000613D
0x180005fc9  xor     edx, edx; Val
0x180005fcb  lea     rcx, [rbx+48h]; void *
0x180005fcf  mov     r8d, 0CCh; Size
0x180005fd5  call    memset_0
0x180005fda  lea     rcx, [rbx+140h]; void *
0x180005fe1  xor     edx, edx; Val
0x180005fe3  mov     r8d, 0ACh; Size
0x180005fe9  call    memset_0
0x180005fee  mov     rcx, cs:ghMod; hInstance
0x180005ff5  lea     r8, [rbx+16Ch]; lpBuffer
0x180005ffc  mov     ebp, 40h ; '@'
0x180006001  mov     dword ptr [rbx+160h], 3E8h
0x18000600b  mov     r9d, ebp; cchBufferMax
0x18000600e  mov     dword ptr [rbx+15Ch], 1
0x180006018  mov     dword ptr [rbx+14Ch], 1
0x180006022  lea     edx, [rbp+25h]; uID
0x180006025  call    cs:__imp_LoadStringW
0x18000602b  mov     rcx, cs:ghMod; hInstance
0x180006032  lea     r9d, [rbp+10h]; cchBufferMax
0x180006036  lea     r8, [rsp+308h+Buffer]; lpBuffer
0x18000603b  lea     edx, [rbp+24h]; uID
0x18000603e  call    cs:__imp_LoadStringW
0x180006044  mov     rcx, rsi; lpString
0x180006047  call    cs:__imp_lstrlenW
0x18000604d  movsxd  rcx, eax
0x180006050  lea     r9, [rsi+rcx*2]
0x180006054  cmp     r9, rsi
0x180006057  jbe     short loc_18000608B
0x180006059  movzx   eax, word ptr [r9]
0x18000605d  sub     ax, 2Fh ; '/'
0x180006061  cmp     ax, 2Dh ; '-'
0x180006065  ja      short loc_180006077
0x180006067  mov     rcx, 200000000801h
0x180006071  bt      rcx, rax
0x180006075  jb      short loc_18000608B
0x180006077  mov     rdx, r9; lpszCurrent
0x18000607a  mov     rcx, rsi; lpszStart
0x18000607d  call    cs:__imp_CharPrevW
0x180006083  mov     r9, rax
0x180006086  cmp     rax, rsi
0x180006089  ja      short loc_180006059
0x18000608b  cmp     r9, rsi
0x18000608e  lea     rax, [r9+2]
0x180006092  lea     r8, [rsp+308h+Buffer]; pszFormat
0x180006097  mov     edx, 208h; cbDest
0x18000609c  cmovnz  r9, rax
0x1800060a0  lea     rcx, [rsp+308h+pszDest]; pszDest
0x1800060a8  call    StringCbPrintfW
0x1800060ad  lea     r9, [rbx+94h]
0x1800060b4  mov     ecx, 3Fh ; '?'
0x1800060b9  mov     rax, r9
0x1800060bc  lea     rdx, [rsp+308h+pszDest]
0x1800060c4  test    rcx, rcx
0x1800060c7  jz      short loc_1800060E8
0x1800060c9  movzx   r8d, word ptr [rdx]
0x1800060cd  test    r8w, r8w
0x1800060d1  jz      short loc_1800060E8
0x1800060d3  mov     [rax], r8w
0x1800060d7  add     rdx, 2
0x1800060db  add     rax, 2
0x1800060df  dec     rcx
0x1800060e2  sub     rbp, 1
0x1800060e6  jnz     short loc_1800060C4
0x1800060e8  test    rbp, rbp
0x1800060eb  lea     rcx, [rax-2]
0x1800060ef  cmovnz  rcx, rax
0x1800060f3  mov     [rcx], r15w
0x1800060f7  mov     [r9+7Eh], r15w
0x1800060fc  bt      edi, 0Ch
0x180006100  jnb     short loc_180006131
0x180006102  mov     ecx, r15d
0x180006105  mov     qword ptr [rbx+48h], 73647561h
0x18000610d  mov     [rbx+50h], r15d
0x180006111  mov     [rbx+58h], r15
0x180006115  mov     [rbx+68h], r15
0x180006119  mov     [rbx+60h], r15
0x18000611d  mov     [rbx+70h], r15d
0x180006121  mov     [rbx+78h], r15d
0x180006125  mov     dword ptr [rbx+124h], 1
0x18000612f  jmp     short loc_18000613B
0x180006131  mov     rcx, rbx
0x180006134  call    ParseWaveFile
0x180006139  mov     ecx, eax
0x18000613b  mov     eax, ecx
0x18000613d  mov     rcx, [rsp+308h+var_38]
0x180006145  xor     rcx, rsp; StackCookie
0x180006148  call    __security_check_cookie
0x18000614d  mov     rbx, [rsp+308h+arg_18]
0x180006155  add     rsp, 2E0h
0x18000615c  pop     r15
0x18000615e  pop     r14
0x180006160  pop     rdi
0x180006161  pop     rsi
0x180006162  pop     rbp
0x180006163  retn
```
