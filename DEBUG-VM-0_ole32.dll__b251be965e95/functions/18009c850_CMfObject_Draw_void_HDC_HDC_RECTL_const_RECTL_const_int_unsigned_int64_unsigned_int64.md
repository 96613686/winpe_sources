# CMfObject::Draw(void *,HDC__ *,HDC__ *,_RECTL const *,_RECTL const *,int (*)(unsigned __int64),unsigned __int64)

- ea: `0x18009c850`
- end: `0x18009cb94`
- name: `?Draw@CMfObject@@UEAAJPEAXPEAUHDC__@@1PEBU_RECTL@@2P6AH_K@Z3@Z`
- size: `836`
- prototype: `HRESULT __fastcall(CMfObject *this, void *__formal, HDC__ *__formal, HDC__ *hdcDraw, const _RECTL *lprcBounds, const _RECTL *lprcWBounds, int (__fastcall *pfnContinue)(unsigned __int64), unsigned __int64 dwContinue)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180052390`
- `0x18009c850`
- `0x18009cfd4`
- `0x18009d45c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009caf9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009cb15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009caf9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009cb15`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009ca11`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009ca11`
- `GDI32!DeleteObject` at `0x18009cb5b`
- `GDI32!DeleteObject` at `0x18009cb5b`
- `GDI32!DeleteEnhMetaFile` at `0x18009c995`
- `GDI32!DeleteEnhMetaFile` at `0x18009c995`
- `GDI32!SetMapMode` at `0x18009c9b5`
- `GDI32!SetMapMode` at `0x18009c9b5`
- `GDI32!SaveDC` at `0x18009c8bd`
- `GDI32!SaveDC` at `0x18009c8bd`
- `GDI32!IntersectClipRect` at `0x18009c903`
- `GDI32!IntersectClipRect` at `0x18009c903`
- `GDI32!GetGraphicsMode` at `0x18009c925`
- `GDI32!GetGraphicsMode` at `0x18009c925`
- `GDI32!CreateEnhMetaFileW` at `0x18009c957`
- `GDI32!CreateEnhMetaFileW` at `0x18009c957`
- `GDI32!PlayMetaFile` at `0x18009c967`
- `GDI32!PlayMetaFile` at `0x18009c967`
- `GDI32!CloseEnhMetaFile` at `0x18009c970`
- `GDI32!CloseEnhMetaFile` at `0x18009c970`
- `GDI32!PlayEnhMetaFile` at `0x18009c98c`
- `GDI32!PlayEnhMetaFile` at `0x18009c98c`
- `GDI32!LPtoDP` at `0x18009c9a7`
- `GDI32!LPtoDP` at `0x18009c9a7`
- `GDI32!SetViewportOrgEx` at `0x18009c9c8`
- `GDI32!SetViewportOrgEx` at `0x18009c9c8`
- `GDI32!SetViewportExtEx` at `0x18009c9e2`
- `GDI32!SetViewportExtEx` at `0x18009c9e2`
- `GDI32!EnumMetaFile` at `0x18009cad9`
- `GDI32!EnumMetaFile` at `0x18009cad9`
- `GDI32!GetStockObject` at `0x18009cb34`
- `GDI32!GetStockObject` at `0x18009cb34`
- `GDI32!SelectPalette` at `0x18009cb51`
- `GDI32!SelectPalette` at `0x18009cb51`
- `GDI32!RestoreDC` at `0x18009cb6b`
- `GDI32!RestoreDC` at `0x18009cb6b`
- `USER32!GetDC` at `0x18009c938`
- `USER32!GetDC` at `0x18009c938`

## pseudocode

```c
__int64 __fastcall CMfObject::Draw(
        CMfObject *this,
        void *__formal,
        HDC__ *a3,
        HDC hdcDraw,
        tagRECT *lprcBounds,
        const _RECTL *lprcWBounds,
        int (__fastcall *pfnContinue)(unsigned __int64),
        unsigned __int64 dwContinue)
{
  int v11; // r14d
  int IsDcMeta; // eax
  int v13; // eax
  HDC DC; // rax
  HDC v15; // rbx
  HENHMETAFILE v16; // rax
  HENHMETAFILE v17; // rbx
  _METAINFO *v18; // rax
  HMETAFILE__ *m_hPres; // rdx
  _METAINFO *m_pMetaInfo; // r8
  _METADC *pNext; // rcx
  HPALETTE StockObject; // rax
  tagRECT rect; // [rsp+30h] [rbp-30h] BYREF
  RECT rc; // [rsp+40h] [rbp-20h] BYREF

  this->m_error = 0;
  rect = 0;
  if ( !this->m_hPres && !CMfObject::LoadHPRES(this) )
    return 2147745799LL;
  rect = *lprcBounds;
  v11 = SaveDC(hdcDraw);
  if ( !v11 )
    return 2147942414LL;
  this->m_nRecord = 16;
  IsDcMeta = OleIsDcMeta(hdcDraw);
  this->m_fMetaDC = IsDcMeta;
  if ( IsDcMeta )
  {
    if ( !lprcWBounds )
      return 2147746112LL;
    v11 = -1;
    v18 = (_METAINFO *)HeapAlloc(g_hHeap, 0, 0x38u);
    this->m_pMetaInfo = v18;
    if ( !v18 )
    {
      this->m_error = -2147024882;
      goto $errRtn_151;
    }
    this->m_pCurMdc = &v18->headDc;
    v18->xwo = lprcWBounds->left;
    this->m_pMetaInfo->ywo = lprcWBounds->top;
    this->m_pMetaInfo->xwe = lprcWBounds->right;
    this->m_pMetaInfo->ywe = lprcWBounds->bottom;
    this->m_pMetaInfo->xro = rect.left - lprcWBounds->left;
    this->m_pMetaInfo->yro = rect.top - lprcWBounds->top;
    this->m_pCurMdc->xre = rect.right - rect.left;
    this->m_pCurMdc->yre = rect.bottom - rect.top;
    this->m_pCurMdc->xMwo = 0;
    this->m_pCurMdc->yMwo = 0;
    this->m_pCurMdc->xMwe = 0;
    this->m_pCurMdc->yMwe = 0;
    this->m_pCurMdc->pNext = 0;
    goto LABEL_19;
  }
  v13 = IntersectClipRect(hdcDraw, rect.left, rect.top, rect.right, rect.bottom);
  if ( v13 != 1 )
  {
    if ( !v13 )
    {
      this->m_error = -2147467259;
      goto $errRtn_151;
    }
    if ( GetGraphicsMode(hdcDraw) == 2 )
    {
      DC = GetDC(0);
      rc = (RECT)_mm_load_si128((const __m128i *)&_xmm);
      v15 = CreateEnhMetaFileW(DC, 0, &rc, 0);
      PlayMetaFile(v15, this->m_hPres);
      v16 = CloseEnhMetaFile(v15);
      v17 = v16;
      if ( v16 )
      {
        PlayEnhMetaFile(hdcDraw, v16, &rect);
        DeleteEnhMetaFile(v17);
      }
      goto $errRtn_151;
    }
    LPtoDP(hdcDraw, (LPPOINT)&rect, 2);
    SetMapMode(hdcDraw, 8);
    SetViewportOrgEx(hdcDraw, rect.left, rect.top, 0);
    SetViewportExtEx(hdcDraw, rect.right - rect.left, rect.bottom - rect.top, 0);
LABEL_19:
    m_hPres = this->m_hPres;
    this->m_pfnContinue = pfnContinue;
    this->m_dwContinue = dwContinue;
    this->m_hPalDCOriginal = 0;
    this->m_hPalLast = 0;
    EnumMetaFile(hdcDraw, m_hPres, MfCallbackFuncForDraw, (LPARAM)this);
    if ( this->m_fMetaDC )
    {
      while ( 1 )
      {
        m_pMetaInfo = this->m_pMetaInfo;
        pNext = m_pMetaInfo->headDc.pNext;
        if ( !pNext )
          break;
        m_pMetaInfo->headDc.pNext = pNext->pNext;
        HeapFree(g_hHeap, 0, pNext);
      }
      HeapFree(g_hHeap, 0, m_pMetaInfo);
      this->m_pCurMdc = 0;
      this->m_pMetaInfo = 0;
    }
    if ( this->m_hPalLast )
    {
      if ( this->m_fMetaDC )
        StockObject = (HPALETTE)GetStockObject(15);
      else
        StockObject = this->m_hPalDCOriginal;
      if ( StockObject )
        SelectPalette(hdcDraw, StockObject, 1);
      DeleteObject(this->m_hPalLast);
    }
    this->m_fMetaDC = 0;
  }
$errRtn_151:
  RestoreDC(hdcDraw, v11);
  return (unsigned int)this->m_error;
}

```

## disassembly

```asm
0x18009c850  mov     [rsp-28h+arg_8], rbx
0x18009c855  push    rbp
0x18009c856  push    rsi
0x18009c857  push    rdi
0x18009c858  push    r14
0x18009c85a  push    r15
0x18009c85c  mov     rbp, rsp
0x18009c85f  sub     rsp, 60h
0x18009c863  mov     rax, cs:__security_cookie
0x18009c86a  xor     rax, rsp
0x18009c86d  mov     [rbp+var_10], rax
0x18009c871  xor     r15d, r15d
0x18009c874  xorps   xmm0, xmm0
0x18009c877  mov     rsi, hdcDraw
0x18009c87a  mov     rdi, this
0x18009c87d  mov     [this+30h], r15d
0x18009c881  movups  xmmword ptr [rbp+rect.left], xmm0
0x18009c885  cmp     [this+10h], r15
0x18009c889  jnz     short loc_18009C89F
0x18009c88b  call    ?LoadHPRES@CMfObject@@AEAAPEAXXZ; CMfObject::LoadHPRES(void)
0x18009c890  test    rax, rax
0x18009c893  jnz     short loc_18009C89F
0x18009c895  mov     eax, 80040007h
0x18009c89a  jmp     loc_18009CB74
0x18009c89f  mov     this, [rbp+arg_20]
0x18009c8a3  mov     eax, [this]
0x18009c8a5  mov     [rbp+rect.left], eax
0x18009c8a8  mov     eax, [this+8]
0x18009c8ab  mov     [rbp+rect.right], eax
0x18009c8ae  mov     eax, [this+4]
0x18009c8b1  mov     [rbp+rect.top], eax
0x18009c8b4  mov     eax, [this+0Ch]
0x18009c8b7  mov     this, rsi; hdc
0x18009c8ba  mov     [rbp+rect.bottom], eax
0x18009c8bd  call    cs:__imp_SaveDC
0x18009c8c3  mov     r14d, eax
0x18009c8c6  test    eax, eax
0x18009c8c8  jnz     short loc_18009C8D4
0x18009c8ca  mov     eax, 8007000Eh
0x18009c8cf  jmp     loc_18009CB74
0x18009c8d4  mov     this, rsi; hdc
0x18009c8d7  mov     dword ptr [rdi+2Ch], 10h
0x18009c8de  call    OleIsDcMeta
0x18009c8e3  mov     [rdi+28h], eax
0x18009c8e6  test    eax, eax
0x18009c8e8  jnz     loc_18009C9ED
0x18009c8ee  mov     eax, [rbp+rect.bottom]
0x18009c8f1  mov     this, rsi; hdc
0x18009c8f4  mov     r9d, [rbp+rect.right]; right
0x18009c8f8  mov     r8d, [rbp+rect.top]; top
0x18009c8fc  mov     edx, [rbp+rect.left]; left
0x18009c8ff  mov     [rsp+60h+bottom], eax; bottom
0x18009c903  call    cs:__imp_IntersectClipRect
0x18009c909  cmp     eax, 1
0x18009c90c  jz      $errRtn_151
0x18009c912  test    eax, eax
0x18009c914  jnz     short loc_18009C922
0x18009c916  mov     dword ptr [rdi+30h], 80004005h
0x18009c91d  jmp     $errRtn_151
0x18009c922  mov     this, rsi; hdc
0x18009c925  call    cs:__imp_GetGraphicsMode
0x18009c92b  mov     r8d, 2; c
0x18009c931  cmp     eax, r8d
0x18009c934  jnz     short loc_18009C9A0
0x18009c936  xor     ecx, ecx; hWnd
0x18009c938  call    cs:__imp_GetDC
0x18009c93e  movdqa  xmm0, cs:__xmm@000003e8000003e80000000000000000
0x18009c946  lea     r8, [rbp+rc]; lprc
0x18009c94a  mov     this, rax; hdc
0x18009c94d  xor     r9d, r9d; lpDesc
0x18009c950  xor     edx, edx; lpFilename
0x18009c952  movdqu  xmmword ptr [rbp+rc.left], xmm0
0x18009c957  call    cs:__imp_CreateEnhMetaFileW
0x18009c95d  mov     __formal, [rdi+10h]; hmf
0x18009c961  mov     this, rax; hdc
0x18009c964  mov     rbx, rax
0x18009c967  call    cs:__imp_PlayMetaFile
0x18009c96d  mov     this, rbx; hdc
0x18009c970  call    cs:__imp_CloseEnhMetaFile
0x18009c976  mov     rbx, rax
0x18009c979  test    rax, rax
0x18009c97c  jz      $errRtn_151
0x18009c982  lea     r8, [rbp+rect]; lprect
0x18009c986  mov     __formal, rax; hmf
0x18009c989  mov     this, rsi; hdc
0x18009c98c  call    cs:__imp_PlayEnhMetaFile
0x18009c992  mov     this, rbx; hmf
0x18009c995  call    cs:__imp_DeleteEnhMetaFile
0x18009c99b  jmp     $errRtn_151
0x18009c9a0  lea     __formal, [rbp+rect]; lppt
0x18009c9a4  mov     this, rsi; hdc
0x18009c9a7  call    cs:__imp_LPtoDP
0x18009c9ad  mov     edx, 8; iMode
0x18009c9b2  mov     this, rsi; hdc
0x18009c9b5  call    cs:__imp_SetMapMode
0x18009c9bb  mov     r8d, [rbp+rect.top]; y
0x18009c9bf  xor     r9d, r9d; lppt
0x18009c9c2  mov     edx, [rbp+rect.left]; x
0x18009c9c5  mov     this, rsi; hdc
0x18009c9c8  call    cs:__imp_SetViewportOrgEx
0x18009c9ce  mov     r8d, [rbp+rect.bottom]
0x18009c9d2  xor     r9d, r9d; lpsz
0x18009c9d5  mov     edx, [rbp+rect.right]
0x18009c9d8  mov     this, rsi; hdc
0x18009c9db  sub     r8d, [rbp+rect.top]; y
0x18009c9df  sub     edx, [rbp+rect.left]; x
0x18009c9e2  call    cs:__imp_SetViewportExtEx
0x18009c9e8  jmp     loc_18009CAB0
0x18009c9ed  mov     rbx, [rbp+arg_28]
0x18009c9f1  test    rbx, rbx
0x18009c9f4  jnz     short loc_18009CA00
0x18009c9f6  mov     eax, 80040140h
0x18009c9fb  jmp     loc_18009CB74
0x18009ca00  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18009ca07  or      r14d, 0FFFFFFFFh
0x18009ca0b  xor     edx, edx; dwFlags
0x18009ca0d  lea     r8d, [r14+39h]; dwBytes
0x18009ca11  call    cs:__imp_HeapAlloc
0x18009ca17  mov     [rdi+18h], rax
0x18009ca1b  mov     this, rax
0x18009ca1e  test    rax, rax
0x18009ca21  jnz     short loc_18009CA2F
0x18009ca23  mov     dword ptr [rdi+30h], 8007000Eh
0x18009ca2a  jmp     $errRtn_151
0x18009ca2f  mov     [rdi+20h], this
0x18009ca33  mov     eax, [rbx]
0x18009ca35  mov     [this+20h], eax
0x18009ca38  mov     eax, [rbx+4]
0x18009ca3b  mov     this, [rdi+18h]
0x18009ca3f  mov     [this+24h], eax
0x18009ca42  mov     eax, [rbx+8]
0x18009ca45  mov     this, [rdi+18h]
0x18009ca49  mov     [this+28h], eax
0x18009ca4c  mov     this, [rdi+18h]
0x18009ca50  mov     eax, [rbx+0Ch]
0x18009ca53  mov     [this+2Ch], eax
0x18009ca56  mov     rax, [rdi+18h]
0x18009ca5a  mov     ecx, [rbp+rect.left]
0x18009ca5d  sub     ecx, [rbx]
0x18009ca5f  mov     [rax+30h], ecx
0x18009ca62  mov     rax, [rdi+18h]
0x18009ca66  mov     ecx, [rbp+rect.top]
0x18009ca69  sub     ecx, [rbx+4]
0x18009ca6c  mov     [rax+34h], ecx
0x18009ca6f  mov     rax, [rdi+20h]
0x18009ca73  mov     ecx, [rbp+rect.right]
0x18009ca76  sub     ecx, [rbp+rect.left]
0x18009ca79  mov     [rax+10h], ecx
0x18009ca7c  mov     rax, [rdi+20h]
0x18009ca80  mov     ecx, [rbp+rect.bottom]
0x18009ca83  sub     ecx, [rbp+rect.top]
0x18009ca86  mov     [rax+14h], ecx
0x18009ca89  mov     rax, [rdi+20h]
0x18009ca8d  mov     [rax], r15d
0x18009ca90  mov     rax, [rdi+20h]
0x18009ca94  mov     [rax+4], r15d
0x18009ca98  mov     rax, [rdi+20h]
0x18009ca9c  mov     [rax+8], r15d
0x18009caa0  mov     rax, [rdi+20h]
0x18009caa4  mov     [rax+0Ch], r15d
0x18009caa8  mov     rax, [rdi+20h]
0x18009caac  mov     [rax+18h], r15
0x18009cab0  mov     rax, [rbp+arg_30]
0x18009cab4  lea     r8, ?MfCallbackFuncForDraw@@YAHPEAUHDC__@@PEAUtagHANDLETABLE@@PEAUtagMETARECORD@@H_J@Z; proc
0x18009cabb  mov     __formal, [rdi+10h]; hmf
0x18009cabf  mov     hdcDraw, rdi; param
0x18009cac2  mov     [rdi+48h], rax
0x18009cac6  mov     this, rsi; hdc
0x18009cac9  mov     rax, [rbp+arg_38]
0x18009cacd  mov     [rdi+50h], rax
0x18009cad1  mov     [rdi+70h], r15
0x18009cad5  mov     [rdi+78h], r15
0x18009cad9  call    cs:__imp_EnumMetaFile
0x18009cadf  cmp     [rdi+28h], r15d
0x18009cae3  jz      short loc_18009CB23
0x18009cae5  jmp     short loc_18009CAFF
0x18009cae7  mov     rax, [this+18h]
0x18009caeb  mov     [r8+18h], rax
0x18009caef  mov     r8, this; lpMem
0x18009caf2  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18009caf9  call    cs:__imp_HeapFree
0x18009caff  mov     r8, [rdi+18h]; lpMem
0x18009cb03  xor     edx, edx; dwFlags
0x18009cb05  mov     this, [r8+18h]
0x18009cb09  test    this, this
0x18009cb0c  jnz     short loc_18009CAE7
0x18009cb0e  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18009cb15  call    cs:__imp_HeapFree
0x18009cb1b  mov     [rdi+20h], r15
0x18009cb1f  mov     [rdi+18h], r15
0x18009cb23  cmp     [rdi+78h], r15
0x18009cb27  jz      short loc_18009CB61
0x18009cb29  cmp     [rdi+28h], r15d
0x18009cb2d  jz      short loc_18009CB3C
0x18009cb2f  mov     ecx, 0Fh; i
0x18009cb34  call    cs:__imp_GetStockObject
0x18009cb3a  jmp     short loc_18009CB40
0x18009cb3c  mov     rax, [rdi+70h]
0x18009cb40  test    rax, rax
0x18009cb43  jz      short loc_18009CB57
0x18009cb45  mov     r8d, 1; bForceBkgd
0x18009cb4b  mov     __formal, rax; hPal
0x18009cb4e  mov     this, rsi; hdc
0x18009cb51  call    cs:__imp_SelectPalette
0x18009cb57  mov     this, [rdi+78h]; ho
0x18009cb5b  call    cs:__imp_DeleteObject
0x18009cb61  mov     [rdi+28h], r15d
0x18009cb65  mov     edx, r14d; nSavedDC
0x18009cb68  mov     this, rsi; hdc
0x18009cb6b  call    cs:__imp_RestoreDC
0x18009cb71  mov     eax, [rdi+30h]
0x18009cb74  mov     this, [rbp+var_10]
0x18009cb78  xor     this, rsp; StackCookie
0x18009cb7b  call    __security_check_cookie
0x18009cb80  mov     rbx, [rsp+60h+arg_8]
0x18009cb88  add     rsp, 60h
0x18009cb8c  pop     r15
0x18009cb8e  pop     r14
0x18009cb90  pop     rdi
0x18009cb91  pop     rsi
0x18009cb92  pop     rbp
0x18009cb93  retn
```
