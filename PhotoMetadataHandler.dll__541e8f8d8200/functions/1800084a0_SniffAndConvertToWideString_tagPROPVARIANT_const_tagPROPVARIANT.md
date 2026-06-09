# SniffAndConvertToWideString(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x1800084a0`
- end: `0x180008838`
- name: `?SniffAndConvertToWideString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `920`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarSrc, PROPVARIANT *pvarDest)`
- caller_count: `7`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006860`
- `0x180007de0`
- `0x1800081a0`
- `0x180008370`
- `0x180008840`
- `0x180012620`
- `0x18001defc`

## callees

- `0x180007d90`
- `0x1800084a0`
- `0x180008b60`
- `0x1800129d8`
- `0x1800169b8`
- `0x180016c26`
- `0x180016c5c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000882d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000882d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800084b9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008644`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800084b9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008644`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000866f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000866f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000856f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000856f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800087bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800087bd`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x1800087d7`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x1800087d7`

## pseudocode

```c
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
0x1800084a0  mov     [rsp+arg_18], rbx
0x1800084a5  push    rbp
0x1800084a6  push    rsi
0x1800084a7  push    rdi
0x1800084a8  push    r14
0x1800084aa  push    r15
0x1800084ac  sub     rsp, 30h
0x1800084b0  mov     rbx, rcx
0x1800084b3  mov     r14, rdx
0x1800084b6  mov     rcx, rdx; pvar
0x1800084b9  call    cs:__imp_PropVariantClear
0x1800084bf  movzx   ecx, word ptr [rbx]
0x1800084c2  mov     eax, 1Eh
0x1800084c7  cmp     ax, cx
0x1800084ca  jnz     loc_18000857D
0x1800084d0  mov     rbp, [rbx+8]
0x1800084d4  xor     edi, edi
0x1800084d6  mov     esi, edi
0x1800084d8  mov     ebx, edi
0x1800084da  test    rbp, rbp
0x1800084dd  jz      short loc_180008527
0x1800084df  mov     [rsp+58h+cchWideChar], edi; cchWideChar
0x1800084e3  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x1800084e9  mov     r8, rbp; lpMultiByteStr
0x1800084ec  mov     [rsp+58h+lpWideCharStr], rdi; lpWideCharStr
0x1800084f1  mov     edx, 8; dwFlags
0x1800084f6  mov     dword ptr [rsp+58h+CodePage], 0FDE9h
0x1800084fe  mov     ecx, 0FDE9h; CodePage
0x180008503  call    MultiByteToWideChar_0
0x180008508  mov     r15d, eax
0x18000850b  test    eax, eax
0x18000850d  jz      loc_1800086DC
0x180008513  test    ebx, ebx
0x180008515  jns     short loc_180008544
0x180008517  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18000851d  jnz     loc_1800085B9
0x180008523  test    ebx, ebx
0x180008525  js      short loc_18000856C
0x180008527  mov     word ptr [r14], 1Fh
0x18000852d  mov     [r14+8], rsi
0x180008531  mov     eax, ebx
0x180008533  mov     rbx, [rsp+58h+arg_18]
0x180008538  add     rsp, 30h
0x18000853c  pop     r15
0x18000853e  pop     r14
0x180008540  pop     rdi
0x180008541  pop     rsi
0x180008542  pop     rbp
0x180008543  retn
0x180008544  movsxd  rcx, r15d
0x180008547  mov     eax, 2
0x18000854c  mul     rcx
0x18000854f  mov     rbx, rax
0x180008552  test    rdx, rdx
0x180008555  jz      loc_18000866C
0x18000855b  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180008561  mov     ebx, 80070216h
0x180008566  jnz     loc_18000868E
0x18000856c  mov     rcx, rsi; pv
0x18000856f  call    cs:__imp_CoTaskMemFree
0x180008575  mov     rsi, rdi
0x180008578  jmp     loc_1800086CF
0x18000857d  mov     eax, 101Eh
0x180008582  cmp     ax, cx
0x180008585  jz      short loc_1800085C5
0x180008587  mov     eax, 1Fh
0x18000858c  cmp     ax, cx
0x18000858f  jz      loc_180008827
0x180008595  mov     eax, 101Fh
0x18000859a  cmp     ax, cx
0x18000859d  jz      loc_180008827
0x1800085a3  mov     eax, 80070057h
0x1800085a8  mov     rbx, [rsp+58h+arg_18]
0x1800085ad  add     rsp, 30h
0x1800085b1  pop     r15
0x1800085b3  pop     r14
0x1800085b5  pop     rdi
0x1800085b6  pop     rsi
0x1800085b7  pop     rbp
0x1800085b8  retn
0x1800085b9  mov     ecx, ebx; int
0x1800085bb  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800085c0  jmp     loc_180008523
0x1800085c5  mov     ecx, [rbx+8]
0x1800085c8  xor     edi, edi
0x1800085ca  mov     eax, 8
0x1800085cf  mov     [rsp+58h+CodePage], rdi
0x1800085d4  mul     rcx
0x1800085d7  test    rdx, rdx
0x1800085da  jnz     short loc_180008656
0x1800085dc  lea     rdx, [r14+10h]; void **
0x1800085e0  mov     [rsp+58h+arg_8], r12
0x1800085e5  mov     rcx, rax; Size
0x1800085e8  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x1800085ed  mov     ebp, eax
0x1800085ef  test    eax, eax
0x1800085f1  js      short loc_18000864C
0x1800085f3  mov     word ptr [r14], 101Fh
0x1800085f9  mov     esi, edi
0x1800085fb  nop     dword ptr [rax+rax+00h]
0x180008600  cmp     esi, [rbx+8]
0x180008603  jnb     short loc_18000864A
0x180008605  mov     rcx, [rbx+10h]
0x180008609  lea     r8, [rsp+58h+CodePage]; unsigned __int16 **
0x18000860e  mov     eax, esi
0x180008610  lea     r15, ds:0[rax*8]
0x180008618  mov     [rsp+58h+CodePage], rdi
0x18000861d  mov     rcx, [rcx+r15]; lpMultiByteStr
0x180008621  call    ?SniffAndConvertToWideString@@YAJPEBDPEAHPEAPEAG@Z; SniffAndConvertToWideString(char const *,int *,ushort * *)
0x180008626  mov     ebp, eax
0x180008628  test    eax, eax
0x18000862a  js      short loc_180008641
0x18000862c  mov     rcx, [r14+10h]
0x180008630  inc     esi
0x180008632  mov     rax, [rsp+58h+CodePage]
0x180008637  mov     [r15+rcx], rax
0x18000863b  mov     [r14+8], esi
0x18000863f  jmp     short loc_180008600
0x180008641  mov     rcx, r14; pvar
0x180008644  call    cs:__imp_PropVariantClear
0x18000864a  mov     eax, ebp
0x18000864c  mov     r12, [rsp+58h+arg_8]
0x180008651  jmp     loc_180008533
0x180008656  mov     rbx, [rsp+58h+arg_18]
0x18000865b  mov     eax, 80070216h
0x180008660  add     rsp, 30h
0x180008664  pop     r15
0x180008666  pop     r14
0x180008668  pop     rdi
0x180008669  pop     rsi
0x18000866a  pop     rbp
0x18000866b  retn
0x18000866c  mov     rcx, rbx; cb
0x18000866f  call    cs:__imp_CoTaskMemAlloc
0x180008675  mov     rsi, rax
0x180008678  test    rax, rax
0x18000867b  jnz     short loc_18000869A
0x18000867d  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180008683  mov     ebx, 8007000Eh
0x180008688  jz      loc_18000856C
0x18000868e  mov     ecx, ebx; int
0x180008690  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180008695  jmp     loc_18000856C
0x18000869a  mov     r8, rbx; Size
0x18000869d  xor     edx, edx; Val
0x18000869f  mov     rcx, rsi; void *
0x1800086a2  call    memset_0
0x1800086a7  mov     ecx, dword ptr [rsp+58h+CodePage]; CodePage
0x1800086ab  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x1800086b1  mov     r8, rbp; lpMultiByteStr
0x1800086b4  mov     [rsp+58h+cchWideChar], r15d; cchWideChar
0x1800086b9  xor     edx, edx; dwFlags
0x1800086bb  mov     [rsp+58h+lpWideCharStr], rsi; lpWideCharStr
0x1800086c0  mov     ebx, edi
0x1800086c2  call    MultiByteToWideChar_0
0x1800086c7  test    eax, eax
0x1800086c9  jz      loc_18000878E
0x1800086cf  test    ebx, ebx
0x1800086d1  js      loc_180008531
0x1800086d7  jmp     loc_180008527
0x1800086dc  call    GetLastError_0
0x1800086e1  mov     ebx, eax
0x1800086e3  test    eax, eax
0x1800086e5  jle     short loc_1800086F0
0x1800086e7  movzx   ebx, ax
0x1800086ea  or      ebx, 80070000h
0x1800086f0  mov     ecx, 80000000h
0x1800086f5  lea     eax, [rbx+rcx]
0x1800086f8  test    ecx, eax
0x1800086fa  jnz     loc_1800087BB
0x180008700  cmp     ebx, 80070459h
0x180008706  jz      loc_1800087BB
0x18000870c  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180008712  jz      loc_180008523
0x180008718  mov     ecx, ebx; int
0x18000871a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000871f  jmp     loc_180008517
0x180008724  call    GetLastError_0
0x180008729  mov     ebx, eax
0x18000872b  test    eax, eax
0x18000872d  jle     short loc_180008738
0x18000872f  movzx   ebx, ax
0x180008732  or      ebx, 80070000h
0x180008738  test    ebx, ebx
0x18000873a  mov     eax, 88982F94h
0x18000873f  cmovns  ebx, eax
0x180008742  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180008748  jz      loc_1800087E5
0x18000874e  mov     ecx, ebx; int
0x180008750  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180008755  jmp     loc_1800087E5
0x18000875a  call    GetLastError_0
0x18000875f  mov     ebx, eax
0x180008761  test    eax, eax
0x180008763  jle     short loc_18000876E
0x180008765  movzx   ebx, ax
0x180008768  or      ebx, 80070000h
0x18000876e  test    ebx, ebx
0x180008770  jns     loc_180008544
0x180008776  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18000877c  jz      loc_18000881A
0x180008782  mov     ecx, ebx; int
0x180008784  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180008789  jmp     loc_180008517
0x18000878e  call    GetLastError_0
0x180008793  mov     ebx, eax
0x180008795  test    eax, eax
0x180008797  jle     short loc_1800087A2
0x180008799  movzx   ebx, ax
0x18000879c  or      ebx, 80070000h
0x1800087a2  test    ebx, ebx
0x1800087a4  jns     loc_180008527
0x1800087aa  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800087b0  jz      loc_180008523
0x1800087b6  jmp     loc_1800085B9
0x1800087bb  xor     ecx, ecx; dwErrCode
0x1800087bd  call    cs:__imp_SetLastError
0x1800087c3  mov     r9d, 2; cchData
0x1800087c9  lea     r8, [rsp+58h+CodePage]; lpLCData
0x1800087ce  mov     edx, 20001004h; LCType
0x1800087d3  xor     ecx, ecx; lpLocaleName
0x1800087d5  mov     ebx, edi
0x1800087d7  call    cs:__imp_GetLocaleInfoEx
0x1800087dd  test    eax, eax
0x1800087df  jz      loc_180008724
0x1800087e5  test    ebx, ebx
0x1800087e7  js      loc_180008517
0x1800087ed  mov     ecx, dword ptr [rsp+58h+CodePage]; CodePage
0x1800087f1  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x1800087f7  mov     [rsp+58h+cchWideChar], edi; cchWideChar
0x1800087fb  mov     r8, rbp; lpMultiByteStr
0x1800087fe  xor     edx, edx; dwFlags
0x180008800  mov     [rsp+58h+lpWideCharStr], rdi; lpWideCharStr
0x180008805  call    MultiByteToWideChar_0
0x18000880a  mov     r15d, eax
0x18000880d  test    eax, eax
0x18000880f  jnz     loc_180008513
0x180008815  jmp     loc_18000875A
0x18000881a  test    ebx, ebx
0x18000881c  js      loc_180008517
0x180008822  jmp     loc_180008513
0x180008827  mov     rdx, rbx; pvarSrc
0x18000882a  mov     rcx, r14; pvarDest
0x18000882d  call    cs:__imp_PropVariantCopy
0x180008833  jmp     loc_180008533
```
