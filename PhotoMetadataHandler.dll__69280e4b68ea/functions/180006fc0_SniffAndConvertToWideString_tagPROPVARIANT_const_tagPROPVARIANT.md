# SniffAndConvertToWideString(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x180006fc0`
- end: `0x180007387`
- name: `?SniffAndConvertToWideString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `967`
- prototype: `HRESULT __fastcall(PROPVARIANT *pvarSrc, PROPVARIANT *pvarDest)`
- caller_count: `7`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006890`
- `0x180006ca0`
- `0x180006e90`
- `0x180007390`
- `0x180007af0`
- `0x180012f00`
- `0x18001ed1c`

## callees

- `0x180006fc0`
- `0x1800076f0`
- `0x1800096a0`
- `0x1800132dc`
- `0x180017408`
- `0x180017676`
- `0x1800176ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180007376`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180007376`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006fd9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007174`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006fd9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007174`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800071a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800071a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007096`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007096`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800072fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800072fa`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18000731a`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18000731a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall SniffAndConvertToWideString(PROPVARIANT *pvarSrc, PROPVARIANT *pvarDest)
{
  VARTYPE vt; // cx
  const CHAR *pszVal; // rbp
  WCHAR *lpWideCharStr; // rsi
  signed int v7; // ebx
  int cchWideChar; // r15d
  HRESULT result; // eax
  unsigned __int64 ulVal; // rcx
  int *v11; // rdx
  int v12; // ebp
  unsigned int i; // esi
  BYTE *pData; // rcx
  __int64 v15; // r15
  WCHAR *v16; // rax
  signed int v17; // eax
  signed int v18; // eax
  signed int v19; // eax
  signed int LastError_0; // eax
  unsigned __int16 *CodePage; // [rsp+60h] [rbp+8h] BYREF

  PropVariantClear(pvarDest);
  vt = pvarSrc->vt;
  if ( pvarSrc->vt == 30 )
  {
    pszVal = pvarSrc->pszVal;
    lpWideCharStr = 0;
    v7 = 0;
    if ( !pszVal )
      goto LABEL_7;
    LODWORD(CodePage) = 65001;
    cchWideChar = MultiByteToWideChar_0(0xFDE9u, 8u, pszVal, -1, 0, 0);
    if ( cchWideChar )
    {
LABEL_9:
      if ( !is_mul_ok(cchWideChar, 2u) )
      {
        v7 = -2147024362;
        if ( !g_doStackCaptures )
          goto LABEL_11;
LABEL_29:
        DoStackCapture(v7);
        goto LABEL_11;
      }
      v16 = (WCHAR *)CoTaskMemAlloc(2LL * cchWideChar);
      lpWideCharStr = v16;
      if ( !v16 )
      {
        v7 = -2147024882;
        if ( !g_doStackCaptures )
          goto LABEL_11;
        goto LABEL_29;
      }
      memset_0(v16, 0, 2LL * cchWideChar);
      v7 = 0;
      if ( MultiByteToWideChar_0((UINT)CodePage, 0, pszVal, -1, lpWideCharStr, cchWideChar) )
      {
LABEL_31:
        if ( v7 < 0 )
          return v7;
        goto LABEL_7;
      }
      LastError_0 = GetLastError_0();
      v7 = LastError_0;
      if ( LastError_0 > 0 )
        v7 = (unsigned __int16)LastError_0 | 0x80070000;
      if ( v7 >= 0 )
      {
LABEL_7:
        pvarDest->vt = 31;
        pvarDest->hVal.QuadPart = (LONGLONG)lpWideCharStr;
        return v7;
      }
      if ( g_doStackCaptures )
LABEL_16:
        DoStackCapture(v7);
LABEL_6:
      if ( v7 < 0 )
      {
LABEL_11:
        CoTaskMemFree(lpWideCharStr);
        lpWideCharStr = 0;
        goto LABEL_31;
      }
      goto LABEL_7;
    }
    v17 = GetLastError_0();
    v7 = v17;
    if ( v17 > 0 )
      v7 = (unsigned __int16)v17 | 0x80070000;
    if ( (int)(v7 + 0x80000000) < 0 || v7 == -2147023783 )
    {
      SetLastError(0);
      v7 = 0;
      if ( !GetLocaleInfoEx(0, 0x20001004u, (LPWSTR)&CodePage, 2) )
      {
        v18 = GetLastError_0();
        v7 = v18;
        if ( v18 > 0 )
          v7 = (unsigned __int16)v18 | 0x80070000;
        if ( v7 >= 0 )
          v7 = -2003292268;
        if ( g_doStackCaptures )
          DoStackCapture(v7);
      }
      if ( v7 < 0 )
        goto LABEL_5;
      cchWideChar = MultiByteToWideChar_0((UINT)CodePage, 0, pszVal, -1, 0, 0);
      if ( cchWideChar )
        goto LABEL_9;
      v19 = GetLastError_0();
      v7 = v19;
      if ( v19 > 0 )
        v7 = (unsigned __int16)v19 | 0x80070000;
      if ( v7 >= 0 )
        goto LABEL_9;
      if ( !g_doStackCaptures )
      {
LABEL_5:
        if ( !g_doStackCaptures )
          goto LABEL_6;
        goto LABEL_16;
      }
    }
    else if ( !g_doStackCaptures )
    {
      goto LABEL_6;
    }
    DoStackCapture(v7);
    goto LABEL_5;
  }
  if ( vt == 4126 )
  {
    ulVal = pvarSrc->ulVal;
    CodePage = 0;
    if ( is_mul_ok(ulVal, 8u) )
    {
      result = CoTaskMemAllocWithInit(8 * ulVal, (void **)&pvarDest->bstrblobVal.pData);
      v12 = result;
      if ( result >= 0 )
      {
        pvarDest->vt = 4127;
        for ( i = 0; i < pvarSrc->lVal; pvarDest->lVal = i )
        {
          pData = pvarSrc->bstrblobVal.pData;
          v15 = 8LL * i;
          CodePage = 0;
          v12 = SniffAndConvertToWideString(*(LPCCH *)&pData[v15], v11, &CodePage);
          if ( v12 < 0 )
          {
            PropVariantClear(pvarDest);
            return v12;
          }
          ++i;
          *(_QWORD *)&pvarDest->bstrblobVal.pData[v15] = CodePage;
        }
        return v12;
      }
    }
    else
    {
      return -2147024362;
    }
  }
  else if ( vt == 31 || vt == 4127 )
  {
    return PropVariantCopy(pvarDest, pvarSrc);
  }
  else
  {
    return -2147024809;
  }
  return result;
}

```

## disassembly

```asm
0x180006fc0  mov     [rsp+arg_18], rbx
0x180006fc5  push    rbp
0x180006fc6  push    rsi
0x180006fc7  push    rdi
0x180006fc8  push    r14
0x180006fca  push    r15
0x180006fcc  sub     rsp, 30h
0x180006fd0  mov     rbx, rcx
0x180006fd3  mov     r14, rdx
0x180006fd6  mov     rcx, rdx; pvar
0x180006fd9  call    cs:__imp_PropVariantClear
0x180006fe0  nop     dword ptr [rax+rax+00h]
0x180006fe5  movzx   ecx, word ptr [rbx]
0x180006fe8  mov     eax, 1Eh
0x180006fed  cmp     ax, cx
0x180006ff0  jnz     loc_1800070AA
0x180006ff6  mov     rbp, [rbx+8]
0x180006ffa  xor     edi, edi
0x180006ffc  mov     esi, edi
0x180006ffe  mov     ebx, edi
0x180007000  test    rbp, rbp
0x180007003  jz      short loc_18000704D
0x180007005  mov     [rsp+58h+cchWideChar], edi; cchWideChar
0x180007009  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x18000700f  mov     r8, rbp; lpMultiByteStr
0x180007012  mov     [rsp+58h+lpWideCharStr], rdi; lpWideCharStr
0x180007017  mov     edx, 8; dwFlags
0x18000701c  mov     dword ptr [rsp+58h+CodePage], 0FDE9h
0x180007024  mov     ecx, 0FDE9h; CodePage
0x180007029  call    MultiByteToWideChar_0
0x18000702e  mov     r15d, eax
0x180007031  test    eax, eax
0x180007033  jz      loc_180007219
0x180007039  test    ebx, ebx
0x18000703b  jns     short loc_18000706B
0x18000703d  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180007043  jnz     loc_1800070E7
0x180007049  test    ebx, ebx
0x18000704b  js      short loc_180007093
0x18000704d  mov     word ptr [r14], 1Fh
0x180007053  mov     [r14+8], rsi
0x180007057  mov     eax, ebx
0x180007059  mov     rbx, [rsp+58h+arg_18]
0x18000705e  add     rsp, 30h
0x180007062  pop     r15
0x180007064  pop     r14
0x180007066  pop     rdi
0x180007067  pop     rsi
0x180007068  pop     rbp
0x180007069  retn
0x18000706b  movsxd  rcx, r15d
0x18000706e  mov     eax, 2
0x180007073  mul     rcx
0x180007076  mov     rbx, rax
0x180007079  test    rdx, rdx
0x18000707c  jz      loc_1800071A3
0x180007082  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180007088  mov     ebx, 80070216h
0x18000708d  jnz     loc_1800071CB
0x180007093  mov     rcx, rsi; pv
0x180007096  call    cs:__imp_CoTaskMemFree
0x18000709d  nop     dword ptr [rax+rax+00h]
0x1800070a2  mov     rsi, rdi
0x1800070a5  jmp     loc_18000720C
0x1800070aa  mov     eax, 101Eh
0x1800070af  cmp     ax, cx
0x1800070b2  jz      short loc_1800070F3
0x1800070b4  mov     eax, 1Fh
0x1800070b9  cmp     ax, cx
0x1800070bc  jz      loc_180007370
0x1800070c2  mov     eax, 101Fh
0x1800070c7  cmp     ax, cx
0x1800070ca  jz      loc_180007370
0x1800070d0  mov     eax, 80070057h
0x1800070d5  mov     rbx, [rsp+58h+arg_18]
0x1800070da  add     rsp, 30h
0x1800070de  pop     r15
0x1800070e0  pop     r14
0x1800070e2  pop     rdi
0x1800070e3  pop     rsi
0x1800070e4  pop     rbp
0x1800070e5  retn
0x1800070e7  mov     ecx, ebx; int
0x1800070e9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800070ee  jmp     loc_180007049
0x1800070f3  mov     ecx, [rbx+8]
0x1800070f6  xor     edi, edi
0x1800070f8  mov     eax, 8
0x1800070fd  mov     [rsp+58h+CodePage], rdi
0x180007102  mul     rcx
0x180007105  test    rdx, rdx
0x180007108  jnz     loc_18000718C
0x18000710e  lea     rdx, [r14+10h]; void **
0x180007112  mov     [rsp+58h+arg_8], r12
0x180007117  mov     rcx, rax; Size
0x18000711a  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x18000711f  mov     ebp, eax
0x180007121  test    eax, eax
0x180007123  js      short loc_180007182
0x180007125  mov     word ptr [r14], 101Fh
0x18000712b  mov     esi, edi
0x18000712d  nop     dword ptr [rax]
0x180007130  cmp     esi, [rbx+8]
0x180007133  jnb     short loc_180007180
0x180007135  mov     rcx, [rbx+10h]
0x180007139  lea     r8, [rsp+58h+CodePage]; unsigned __int16 **
0x18000713e  mov     eax, esi
0x180007140  lea     r15, ds:0[rax*8]
0x180007148  mov     [rsp+58h+CodePage], rdi
0x18000714d  mov     rcx, [rcx+r15]; lpMultiByteStr
0x180007151  call    ?SniffAndConvertToWideString@@YAJPEBDPEAHPEAPEAG@Z; SniffAndConvertToWideString(char const *,int *,ushort * *)
0x180007156  mov     ebp, eax
0x180007158  test    eax, eax
0x18000715a  js      short loc_180007171
0x18000715c  mov     rcx, [r14+10h]
0x180007160  inc     esi
0x180007162  mov     rax, [rsp+58h+CodePage]
0x180007167  mov     [r15+rcx], rax
0x18000716b  mov     [r14+8], esi
0x18000716f  jmp     short loc_180007130
0x180007171  mov     rcx, r14; pvar
0x180007174  call    cs:__imp_PropVariantClear
0x18000717b  nop     dword ptr [rax+rax+00h]
0x180007180  mov     eax, ebp
0x180007182  mov     r12, [rsp+58h+arg_8]
0x180007187  jmp     loc_180007059
0x18000718c  mov     rbx, [rsp+58h+arg_18]
0x180007191  mov     eax, 80070216h
0x180007196  add     rsp, 30h
0x18000719a  pop     r15
0x18000719c  pop     r14
0x18000719e  pop     rdi
0x18000719f  pop     rsi
0x1800071a0  pop     rbp
0x1800071a1  retn
0x1800071a3  mov     rcx, rbx; cb
0x1800071a6  call    cs:__imp_CoTaskMemAlloc
0x1800071ad  nop     dword ptr [rax+rax+00h]
0x1800071b2  mov     rsi, rax
0x1800071b5  test    rax, rax
0x1800071b8  jnz     short loc_1800071D7
0x1800071ba  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800071c0  mov     ebx, 8007000Eh
0x1800071c5  jz      loc_180007093
0x1800071cb  mov     ecx, ebx; int
0x1800071cd  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800071d2  jmp     loc_180007093
0x1800071d7  mov     r8, rbx; Size
0x1800071da  xor     edx, edx; Val
0x1800071dc  mov     rcx, rsi; void *
0x1800071df  call    memset_0
0x1800071e4  mov     ecx, dword ptr [rsp+58h+CodePage]; CodePage
0x1800071e8  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x1800071ee  mov     r8, rbp; lpMultiByteStr
0x1800071f1  mov     [rsp+58h+cchWideChar], r15d; cchWideChar
0x1800071f6  xor     edx, edx; dwFlags
0x1800071f8  mov     [rsp+58h+lpWideCharStr], rsi; lpWideCharStr
0x1800071fd  mov     ebx, edi
0x1800071ff  call    MultiByteToWideChar_0
0x180007204  test    eax, eax
0x180007206  jz      loc_1800072CB
0x18000720c  test    ebx, ebx
0x18000720e  js      loc_180007057
0x180007214  jmp     loc_18000704D
0x180007219  call    GetLastError_0
0x18000721e  mov     ebx, eax
0x180007220  test    eax, eax
0x180007222  jle     short loc_18000722D
0x180007224  movzx   ebx, ax
0x180007227  or      ebx, 80070000h
0x18000722d  mov     ecx, 80000000h
0x180007232  lea     eax, [rbx+rcx]
0x180007235  test    ecx, eax
0x180007237  jnz     loc_1800072F8
0x18000723d  cmp     ebx, 80070459h
0x180007243  jz      loc_1800072F8
0x180007249  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18000724f  jz      loc_180007049
0x180007255  mov     ecx, ebx; int
0x180007257  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000725c  jmp     loc_18000703D
0x180007261  call    GetLastError_0
0x180007266  mov     ebx, eax
0x180007268  test    eax, eax
0x18000726a  jle     short loc_180007275
0x18000726c  movzx   ebx, ax
0x18000726f  or      ebx, 80070000h
0x180007275  test    ebx, ebx
0x180007277  mov     eax, 88982F94h
0x18000727c  cmovns  ebx, eax
0x18000727f  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180007285  jz      loc_18000732E
0x18000728b  mov     ecx, ebx; int
0x18000728d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180007292  jmp     loc_18000732E
0x180007297  call    GetLastError_0
0x18000729c  mov     ebx, eax
0x18000729e  test    eax, eax
0x1800072a0  jle     short loc_1800072AB
0x1800072a2  movzx   ebx, ax
0x1800072a5  or      ebx, 80070000h
0x1800072ab  test    ebx, ebx
0x1800072ad  jns     loc_18000706B
0x1800072b3  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800072b9  jz      loc_180007363
0x1800072bf  mov     ecx, ebx; int
0x1800072c1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800072c6  jmp     loc_18000703D
0x1800072cb  call    GetLastError_0
0x1800072d0  mov     ebx, eax
0x1800072d2  test    eax, eax
0x1800072d4  jle     short loc_1800072DF
0x1800072d6  movzx   ebx, ax
0x1800072d9  or      ebx, 80070000h
0x1800072df  test    ebx, ebx
0x1800072e1  jns     loc_18000704D
0x1800072e7  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800072ed  jz      loc_180007049
0x1800072f3  jmp     loc_1800070E7
0x1800072f8  xor     ecx, ecx; dwErrCode
0x1800072fa  call    cs:__imp_SetLastError
0x180007301  nop     dword ptr [rax+rax+00h]
0x180007306  mov     r9d, 2; cchData
0x18000730c  lea     r8, [rsp+58h+CodePage]; lpLCData
0x180007311  mov     edx, 20001004h; LCType
0x180007316  xor     ecx, ecx; lpLocaleName
0x180007318  mov     ebx, edi
0x18000731a  call    cs:__imp_GetLocaleInfoEx
0x180007321  nop     dword ptr [rax+rax+00h]
0x180007326  test    eax, eax
0x180007328  jz      loc_180007261
0x18000732e  test    ebx, ebx
0x180007330  js      loc_18000703D
0x180007336  mov     ecx, dword ptr [rsp+58h+CodePage]; CodePage
0x18000733a  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180007340  mov     [rsp+58h+cchWideChar], edi; cchWideChar
0x180007344  mov     r8, rbp; lpMultiByteStr
0x180007347  xor     edx, edx; dwFlags
0x180007349  mov     [rsp+58h+lpWideCharStr], rdi; lpWideCharStr
0x18000734e  call    MultiByteToWideChar_0
0x180007353  mov     r15d, eax
0x180007356  test    eax, eax
0x180007358  jnz     loc_180007039
0x18000735e  jmp     loc_180007297
0x180007363  test    ebx, ebx
0x180007365  js      loc_18000703D
0x18000736b  jmp     loc_180007039
0x180007370  mov     rdx, rbx; pvarSrc
0x180007373  mov     rcx, r14; pvarDest
0x180007376  call    cs:__imp_PropVariantCopy
0x18000737d  nop     dword ptr [rax+rax+00h]
0x180007382  jmp     loc_180007059
```
