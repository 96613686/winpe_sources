# CPreviewDC::MirrorFont(void)

- ea: `0x18004e4b0`
- end: `0x18004e69f`
- name: `?MirrorFont@CPreviewDC@@IEAAXXZ`
- size: `495`
- prototype: `void __fastcall(CPreviewDC *__hidden this)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x18004e9d0`
- `0x18004eb80`
- `0x18004ebf0`
- `0x18004eca0`
- `0x18004ed80`
- `0x18004edf0`

## callees

- `0x180021bc0`
- `0x18004e4b0`
- `0x1800d1f92`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `KERNEL32!MulDiv` at `0x18004e616`
- `KERNEL32!MulDiv` at `0x18004e627`
- `KERNEL32!MulDiv` at `0x18004e616`
- `KERNEL32!MulDiv` at `0x18004e627`
- `GDI32!GetViewportExtEx` at `0x18004e5f2`
- `GDI32!GetViewportExtEx` at `0x18004e5f2`
- `GDI32!GetWindowExtEx` at `0x18004e5e4`
- `GDI32!GetWindowExtEx` at `0x18004e5e4`
- `GDI32!GetTextFaceW` at `0x18004e54f`
- `GDI32!GetTextFaceW` at `0x18004e54f`
- `GDI32!DeleteObject` at `0x18004e665`
- `GDI32!DeleteObject` at `0x18004e665`
- `GDI32!GetTextMetricsW` at `0x18004e55d`
- `GDI32!GetTextMetricsW` at `0x18004e5c3`
- `GDI32!GetTextMetricsW` at `0x18004e55d`
- `GDI32!GetTextMetricsW` at `0x18004e5c3`
- `GDI32!SelectObject` at `0x18004e5b5`
- `GDI32!SelectObject` at `0x18004e65c`
- `GDI32!SelectObject` at `0x18004e5b5`
- `GDI32!SelectObject` at `0x18004e65c`
- `GDI32!CreateFontIndirectW` at `0x18004e5a5`
- `GDI32!CreateFontIndirectW` at `0x18004e64c`
- `GDI32!CreateFontIndirectW` at `0x18004e5a5`
- `GDI32!CreateFontIndirectW` at `0x18004e64c`
- `GDI32!GetObjectW` at `0x18004e52b`
- `GDI32!GetObjectW` at `0x18004e52b`

## pseudocode

```c
void __fastcall CPreviewDC::MirrorFont(CPreviewDC *this)
{
  HDC v2; // rcx
  HFONT v3; // r14
  int v4; // ebx
  int v5; // esi
  LONG cy; // r8d
  LONG v7; // edx
  int v8; // ebx
  HFONT v9; // rbx
  struct tagSIZE size; // [rsp+20h] [rbp-79h] BYREF
  struct tagSIZE v11; // [rsp+28h] [rbp-71h] BYREF
  struct tagTEXTMETRICW tm; // [rsp+30h] [rbp-69h] BYREF
  LOGFONTW pv; // [rsp+70h] [rbp-29h] BYREF

  if ( *((_QWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 8) )
    {
      if ( *((_QWORD *)this + 1) )
      {
        memset_0(&pv, 0, sizeof(pv));
        GetObjectW(*((HANDLE *)this + 8), 92, &pv);
        v2 = (HDC)*((_QWORD *)this + 2);
        memset(&tm, 0, sizeof(tm));
        GetTextFaceW(v2, 32, pv.lfFaceName);
        GetTextMetricsW(*((HDC *)this + 2), &tm);
        if ( tm.tmHeight >= 0 )
          pv.lfHeight = tm.tmInternalLeading - tm.tmHeight;
        else
          pv.lfHeight = tm.tmHeight;
        pv.lfWidth = tm.tmAveCharWidth;
        pv.lfWeight = tm.tmWeight;
        pv.lfItalic = tm.tmItalic;
        pv.lfUnderline = tm.tmUnderlined;
        pv.lfStrikeOut = tm.tmStruckOut;
        pv.lfCharSet = tm.tmCharSet;
        pv.lfPitchAndFamily = tm.tmPitchAndFamily;
        v3 = CreateFontIndirectW(&pv);
        SelectObject(*((HDC *)this + 1), v3);
        GetTextMetricsW(*((HDC *)this + 1), &tm);
        v4 = -pv.lfHeight;
        if ( tm.tmHeight >= 0 )
          v5 = tm.tmHeight - tm.tmInternalLeading;
        else
          v5 = -tm.tmHeight;
        GetWindowExtEx(*((HDC *)this + 1), &size);
        GetViewportExtEx(*((HDC *)this + 1), &v11);
        cy = size.cy;
        if ( size.cy < 0 )
        {
          cy = -size.cy;
          size.cy = -size.cy;
        }
        v7 = v11.cy;
        if ( v11.cy < 0 )
        {
          v7 = -v11.cy;
          v11.cy = -v11.cy;
        }
        v8 = MulDiv(v4, v7, cy);
        if ( v8 < MulDiv(v5, v11.cy, size.cy) )
        {
          HIBYTE(pv.lfFaceName[0]) = 0;
          *(_WORD *)&pv.lfPitchAndFamily = (pv.lfPitchAndFamily & 0xF0) != 80 ? 0 : 0x50;
          v9 = CreateFontIndirectW(&pv);
          SelectObject(*((HDC *)this + 1), v9);
          DeleteObject(v3);
          v3 = v9;
        }
        AfxDeleteObject((void **)this + 7);
        *((_QWORD *)this + 7) = v3;
      }
    }
    else
    {
      (*(void (__fastcall **)(CPreviewDC *, __int64))(*(_QWORD *)this + 88LL))(this, 14);
    }
  }
}

```

## disassembly

```asm
0x18004e4b0  mov     [rsp-8+arg_8], rbx
0x18004e4b5  mov     [rsp-8+arg_10], rsi
0x18004e4ba  push    rbp
0x18004e4bb  push    rdi
0x18004e4bc  push    r14
0x18004e4be  lea     rbp, [rsp-47h]
0x18004e4c3  sub     rsp, 0E0h
0x18004e4ca  mov     rax, cs:__security_cookie
0x18004e4d1  xor     rax, rsp
0x18004e4d4  mov     [rbp+57h+var_20], rax
0x18004e4d8  cmp     qword ptr [rcx+10h], 0
0x18004e4dd  mov     rdi, rcx
0x18004e4e0  jz      loc_18004E67B
0x18004e4e6  cmp     qword ptr [rcx+40h], 0
0x18004e4eb  jnz     short loc_18004E503
0x18004e4ed  mov     rax, [rcx]
0x18004e4f0  mov     edx, 0Eh
0x18004e4f5  mov     rax, [rax+58h]
0x18004e4f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4fe  jmp     loc_18004E67B
0x18004e503  cmp     qword ptr [rcx+8], 0
0x18004e508  jz      loc_18004E67B
0x18004e50e  mov     ebx, 5Ch ; '\'
0x18004e513  lea     rcx, [rbp+57h+pv]; void *
0x18004e517  mov     r8d, ebx; Size
0x18004e51a  xor     edx, edx; Val
0x18004e51c  call    memset_0
0x18004e521  mov     rcx, [rdi+40h]; h
0x18004e525  lea     r8, [rbp+57h+pv]; pv
0x18004e529  mov     edx, ebx; c
0x18004e52b  call    cs:__imp_GetObjectW
0x18004e531  mov     rcx, [rdi+10h]; hdc
0x18004e535  lea     r8, [rbp+57h+Name]; lpName
0x18004e539  xorps   xmm0, xmm0
0x18004e53c  lea     edx, [rbx-3Ch]; c
0x18004e53f  movups  xmmword ptr [rbp+57h+tm.tmOverhang], xmm0
0x18004e543  movups  xmmword ptr [rbp+57h+tm.tmFirstChar], xmm0
0x18004e547  movups  xmmword ptr [rbp+57h+tm.tmHeight], xmm0
0x18004e54b  movups  xmmword ptr [rbp+57h+tm.tmExternalLeading], xmm0
0x18004e54f  call    cs:__imp_GetTextFaceW
0x18004e555  mov     rcx, [rdi+10h]; hdc
0x18004e559  lea     rdx, [rbp+57h+tm]; lptm
0x18004e55d  call    cs:__imp_GetTextMetricsW
0x18004e563  mov     ecx, [rbp+57h+tm.tmHeight]
0x18004e566  test    ecx, ecx
0x18004e568  jns     short loc_18004E56F
0x18004e56a  mov     [rbp+57h+pv], ecx
0x18004e56d  jmp     short loc_18004E577
0x18004e56f  mov     eax, [rbp+57h+tm.tmInternalLeading]
0x18004e572  sub     eax, ecx
0x18004e574  mov     [rbp+57h+pv], eax
0x18004e577  mov     eax, [rbp+57h+tm.tmAveCharWidth]
0x18004e57a  lea     rcx, [rbp+57h+pv]; lplf
0x18004e57e  mov     [rbp+57h+var_7C], eax
0x18004e581  mov     eax, [rbp+57h+tm.tmWeight]
0x18004e584  mov     [rbp+57h+var_70], eax
0x18004e587  mov     al, [rbp+57h+tm.tmItalic]
0x18004e58a  mov     [rbp+57h+var_6C], al
0x18004e58d  mov     al, [rbp+57h+tm.tmUnderlined]
0x18004e590  mov     [rbp+57h+var_6B], al
0x18004e593  mov     al, [rbp+57h+tm.tmStruckOut]
0x18004e596  mov     [rbp+57h+var_6A], al
0x18004e599  mov     al, [rbp+57h+tm.tmCharSet]
0x18004e59c  mov     [rbp+57h+var_69], al
0x18004e59f  mov     al, [rbp+57h+tm.tmPitchAndFamily]
0x18004e5a2  mov     [rbp+57h+var_65], al
0x18004e5a5  call    cs:__imp_CreateFontIndirectW
0x18004e5ab  mov     rcx, [rdi+8]; hdc
0x18004e5af  mov     rdx, rax; h
0x18004e5b2  mov     r14, rax
0x18004e5b5  call    cs:__imp_SelectObject
0x18004e5bb  mov     rcx, [rdi+8]; hdc
0x18004e5bf  lea     rdx, [rbp+57h+tm]; lptm
0x18004e5c3  call    cs:__imp_GetTextMetricsW
0x18004e5c9  mov     ebx, [rbp+57h+pv]
0x18004e5cc  mov     esi, [rbp+57h+tm.tmHeight]
0x18004e5cf  neg     ebx
0x18004e5d1  test    esi, esi
0x18004e5d3  jns     short loc_18004E5D9
0x18004e5d5  neg     esi
0x18004e5d7  jmp     short loc_18004E5DC
0x18004e5d9  sub     esi, [rbp+57h+tm.tmInternalLeading]
0x18004e5dc  mov     rcx, [rdi+8]; hdc
0x18004e5e0  lea     rdx, [rbp+57h+size]; lpsize
0x18004e5e4  call    cs:__imp_GetWindowExtEx
0x18004e5ea  mov     rcx, [rdi+8]; hdc
0x18004e5ee  lea     rdx, [rbp+57h+var_C8]; lpsize
0x18004e5f2  call    cs:__imp_GetViewportExtEx
0x18004e5f8  mov     r8d, [rbp+57h+size.cy]
0x18004e5fc  test    r8d, r8d
0x18004e5ff  jns     short loc_18004E608
0x18004e601  neg     r8d; nDenominator
0x18004e604  mov     [rbp+57h+size.cy], r8d
0x18004e608  mov     edx, [rbp+57h+var_C8.cy]
0x18004e60b  test    edx, edx
0x18004e60d  jns     short loc_18004E614
0x18004e60f  neg     edx; nNumerator
0x18004e611  mov     [rbp+57h+var_C8.cy], edx
0x18004e614  mov     ecx, ebx; nNumber
0x18004e616  call    cs:__imp_MulDiv
0x18004e61c  mov     r8d, [rbp+57h+size.cy]; nDenominator
0x18004e620  mov     ecx, esi; nNumber
0x18004e622  mov     edx, [rbp+57h+var_C8.cy]; nNumerator
0x18004e625  mov     ebx, eax
0x18004e627  call    cs:__imp_MulDiv
0x18004e62d  cmp     ebx, eax
0x18004e62f  jge     short loc_18004E66E
0x18004e631  xor     eax, eax
0x18004e633  lea     rcx, [rbp+57h+pv]; lplf
0x18004e637  mov     [rbp+57h+Name], ax
0x18004e63b  mov     al, [rbp+57h+var_65]
0x18004e63e  and     al, 0F0h
0x18004e640  cmp     al, 50h ; 'P'
0x18004e642  setnz   al
0x18004e645  dec     al
0x18004e647  and     al, 50h
0x18004e649  mov     [rbp+57h+var_65], al
0x18004e64c  call    cs:__imp_CreateFontIndirectW
0x18004e652  mov     rcx, [rdi+8]; hdc
0x18004e656  mov     rdx, rax; h
0x18004e659  mov     rbx, rax
0x18004e65c  call    cs:__imp_SelectObject
0x18004e662  mov     rcx, r14; ho
0x18004e665  call    cs:__imp_DeleteObject
0x18004e66b  mov     r14, rbx
0x18004e66e  lea     rcx, [rdi+38h]; void **
0x18004e672  call    ?AfxDeleteObject@@YAXPEAPEAX@Z; AfxDeleteObject(void * *)
0x18004e677  mov     [rdi+38h], r14
0x18004e67b  mov     rcx, [rbp+57h+var_20]
0x18004e67f  xor     rcx, rsp; StackCookie
0x18004e682  call    __security_check_cookie
0x18004e687  lea     r11, [rsp+0F0h+var_10]
0x18004e68f  mov     rbx, [r11+28h]
0x18004e693  mov     rsi, [r11+30h]
0x18004e697  mov     rsp, r11
0x18004e69a  pop     r14
0x18004e69c  pop     rdi
0x18004e69d  pop     rbp
0x18004e69e  retn
```
