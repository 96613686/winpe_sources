# CUIHostLocale::MungeDialogFont(ulong,uchar *,uchar * *)

- ea: `0x180079d1c`
- end: `0x18007a477`
- name: `?MungeDialogFont@CUIHostLocale@@UEAAJKPEAEPEAPEAE@Z`
- size: `1883`
- prototype: `__int64 __fastcall(CUIHostLocale *__hidden this, unsigned int, unsigned __int8 *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x18000ae00`
- `0x1800187f0`
- `0x1800587cc`
- `0x18005b540`
- `0x18005b5e4`
- `0x180079d1c`
- `0x18007a480`
- `0x18007a4e8`
- `0x18007a560`
- `0x180379380`
- `0x180379520`
- `0x180379546`
- `0x1803796a6`

## import_xrefs

- `KERNEL32!RaiseException` at `0x18007a2ae`
- `KERNEL32!RaiseException` at `0x18007a2ae`
- `KERNEL32!MulDiv` at `0x18007a240`
- `KERNEL32!MulDiv` at `0x18007a26b`
- `KERNEL32!MulDiv` at `0x18007a351`
- `KERNEL32!MulDiv` at `0x18007a240`
- `KERNEL32!MulDiv` at `0x18007a26b`
- `KERNEL32!MulDiv` at `0x18007a351`
- `USER32!GetSystemMetrics` at `0x18007a321`
- `USER32!GetSystemMetrics` at `0x18007a330`
- `USER32!GetSystemMetrics` at `0x18007a321`
- `USER32!GetSystemMetrics` at `0x18007a330`
- `USER32!DrawTextA` at `0x18007a2cf`
- `USER32!DrawTextA` at `0x18007a2cf`
- `GDI32!CreateCompatibleDC` at `0x180079dc9`
- `GDI32!CreateCompatibleDC` at `0x180079dc9`
- `GDI32!DeleteDC` at `0x18007a430`
- `GDI32!DeleteDC` at `0x18007a430`
- `GDI32!SelectObject` at `0x180079de2`
- `GDI32!SelectObject` at `0x180079de2`

## pseudocode

```c
__int64 __fastcall CUIHostLocale::MungeDialogFont(CUIHostLocale *this, __int64 a2, unsigned __int8 *a3, wchar_t **a4)
{
  unsigned int v4; // edi
  unsigned __int8 *v5; // rbx
  wchar_t **v6; // r15
  int v7; // r13d
  unsigned int v8; // esi
  wchar_t *v9; // r10
  wchar_t *v10; // rax
  HDC CompatibleDC; // r14
  HFONT v12; // rax
  HFONT v13; // rax
  int v14; // edx
  int v15; // ecx
  int v16; // r14d
  unsigned __int8 *v17; // rbx
  int v18; // r15d
  wchar_t v19; // ax
  wchar_t v20; // r8
  wchar_t v21; // r9
  wchar_t v22; // r11
  wchar_t v23; // r12
  wchar_t v24; // bx
  CUIHostLocale *v25; // r12
  int v26; // esi
  int v27; // esi
  int v28; // esi
  unsigned __int8 *v29; // rcx
  wchar_t lfWeight; // r11
  BYTE lfItalic; // dl
  BYTE lfCharSet; // r8
  int v33; // eax
  unsigned __int8 *v34; // rax
  unsigned __int64 v35; // rcx
  int v36; // r8d
  int v37; // edx
  int v38; // ebx
  wchar_t v39; // r9
  wchar_t v40; // r11
  wchar_t v41; // r14
  wchar_t v42; // r15
  int v43; // r12d
  unsigned __int8 *v44; // rcx
  unsigned __int8 **v45; // r12
  CUIHostLocale *v46; // r15
  int v47; // eax
  wchar_t *v48; // r14
  wchar_t *v49; // rdx
  char *v50; // rax
  const CHAR *v51; // r14
  wchar_t *v52; // r12
  int v53; // eax
  int v54; // r15d
  __int64 v55; // r9
  int v56; // eax
  int v57; // ebx
  int right; // ecx
  LONG SystemMetrics; // eax
  LONG bottom; // edx
  wchar_t v61; // r15
  unsigned __int8 *v62; // r14
  unsigned __int64 v63; // rcx
  wchar_t *v65; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t v66; // [rsp+38h] [rbp-C8h]
  unsigned int v67; // [rsp+3Ch] [rbp-C4h]
  unsigned __int8 *v68; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v69[2]; // [rsp+48h] [rbp-B8h] BYREF
  int nDenominator; // [rsp+4Ch] [rbp-B4h] BYREF
  int nNumerator; // [rsp+50h] [rbp-B0h] BYREF
  int v72; // [rsp+54h] [rbp-ACh]
  unsigned __int8 **v73; // [rsp+58h] [rbp-A8h]
  HDC hdc; // [rsp+60h] [rbp-A0h]
  unsigned __int8 *lfFaceName; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v76; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v77; // [rsp+74h] [rbp-8Ch] BYREF
  int v78; // [rsp+78h] [rbp-88h]
  CUIHostLocale *v79; // [rsp+80h] [rbp-80h]
  unsigned __int8 **v80; // [rsp+88h] [rbp-78h]
  int v81; // [rsp+90h] [rbp-70h] BYREF
  __int64 v82; // [rsp+98h] [rbp-68h]
  wchar_t *v83; // [rsp+A0h] [rbp-60h]
  wchar_t *v84; // [rsp+A8h] [rbp-58h]
  unsigned __int8 *v85; // [rsp+B0h] [rbp-50h]
  struct tagRECT rc; // [rsp+B8h] [rbp-48h] BYREF
  tagLOGFONTW v87; // [rsp+D0h] [rbp-30h] BYREF

  v4 = 0;
  v5 = a3;
  v6 = a4;
  v80 = (unsigned __int8 **)a4;
  v79 = this;
  v7 = 0;
  v72 = 0;
  v8 = 0;
  v9 = 0;
  v65 = 0;
  v85 = a3;
  v81 = 0;
  v82 = 0;
  v67 = 0;
  while ( 1 )
  {
    hdc = 0;
    if ( v7 )
      break;
LABEL_5:
    v14 = 0;
    if ( *(_WORD *)v5 == 1 && *((_WORD *)v5 + 1) == 0xFFFF )
    {
      v14 = *((_DWORD *)v5 + 1);
      v15 = *((_DWORD *)v5 + 2);
      v16 = *((_DWORD *)v5 + 3);
      v17 = v5 + 16;
      v18 = 1;
    }
    else
    {
      v16 = *(_DWORD *)v5;
      v15 = *((_DWORD *)v5 + 1);
      v18 = 0;
      v17 = v5 + 8;
    }
    v19 = *(_WORD *)v17;
    v20 = *((_WORD *)v17 + 1);
    v21 = *((_WORD *)v17 + 2);
    v22 = *((_WORD *)v17 + 3);
    v23 = *((_WORD *)v17 + 4);
    v66 = *(_WORD *)v17;
    v68 = v17 + 10;
    if ( v7 )
    {
      v24 = v66;
      *v9 = 1;
      *++v65 = -1;
      *(_DWORD *)++v65 = v14;
      v65 += 2;
      *(_DWORD *)v65 = v15;
      v65 += 2;
      *(_DWORD *)v65 = v16 | 0x40;
      v65 += 2;
      *v65++ = v24;
      *v65++ = v20;
      *v65++ = v21;
      *v65++ = v22;
      *v65++ = v23;
    }
    else
    {
      v8 += 26;
      v24 = v19;
    }
    v25 = v79;
    v73 = (unsigned __int8 **)((unsigned __int64)&v65 & -(__int64)(v7 != 0));
    v26 = CUIHostLocale::m_CopyOrdinalOrName(v79, v73, v67, &v68, 0) + v8;
    v27 = CUIHostLocale::m_CopyOrdinalOrName(v25, v73, v67, &v68, 0) + v26;
    v28 = CUIHostLocale::m_CopyString(v25, v73, v67, &v68) + v27;
    if ( (v16 & 0x40) != 0 )
    {
      v29 = v68 + 2;
      v69[0] = *(_WORD *)v68;
      v68 += 2;
      if ( v18 )
        v68 = v29 + 4;
      CUIHostLocale::m_CopyString(v25, 0, 0, &v68);
    }
    CUIHostLocale::m_GetDialogFont(v25, &v87, v69);
    lfWeight = v87.lfWeight;
    lfItalic = v87.lfItalic;
    lfCharSet = v87.lfCharSet;
    if ( v7 )
    {
      *v65++ = v69[0];
      *v65++ = lfWeight;
      *(_BYTE *)v65 = lfItalic;
      v65 = (wchar_t *)((char *)v65 + 1);
      *(_BYTE *)v65 = lfCharSet;
      v65 = (wchar_t *)((char *)v65 + 1);
    }
    else
    {
      v28 += 6;
    }
    lfFaceName = (unsigned __int8 *)v87.lfFaceName;
    v33 = CUIHostLocale::m_CopyString(v25, v73, v67, &lfFaceName);
    v9 = v65;
    v8 = v33 + v28;
    if ( v7 )
    {
      v9 = (wchar_t *)(((unsigned __int64)v65 + 3) & 0xFFFFFFFFFFFFFFFCuLL);
      v65 = v9;
    }
    else
    {
      v8 = (v8 + 3) & 0xFFFFFFFC;
    }
    v34 = (unsigned __int8 *)v18;
    v35 = (unsigned __int64)(v68 + 3);
    lfFaceName = (unsigned __int8 *)v18;
    while ( 1 )
    {
      v63 = v35 & 0xFFFFFFFFFFFFFFFCuLL;
      if ( !v24 )
        break;
      v36 = *(_DWORD *)(v63 + 4);
      v66 = v24 - 1;
      if ( v34 )
      {
        v37 = *(_DWORD *)v63;
        v38 = *(_DWORD *)(v63 + 8);
        v39 = *(_WORD *)(v63 + 12);
        v40 = *(_WORD *)(v63 + 14);
        v41 = *(_WORD *)(v63 + 16);
        v42 = *(_WORD *)(v63 + 18);
        v43 = *(_DWORD *)(v63 + 20);
        v44 = (unsigned __int8 *)(v63 + 24);
      }
      else
      {
        v38 = *(_DWORD *)v63;
        v39 = *(_WORD *)(v63 + 8);
        v40 = *(_WORD *)(v63 + 10);
        v41 = *(_WORD *)(v63 + 12);
        v42 = *(_WORD *)(v63 + 14);
        v43 = *(unsigned __int16 *)(v63 + 16);
        v44 = (unsigned __int8 *)(v63 + 18);
        v37 = 0;
      }
      v68 = v44;
      if ( v7 )
      {
        *(_DWORD *)v9 = v37;
        v65 += 2;
        *(_DWORD *)v65 = v36;
        v65 += 2;
        *(_DWORD *)v65 = v38;
        v65 += 2;
        *v65++ = v39;
        *v65++ = v40;
        v84 = v65;
        *v65++ = v41;
        v83 = v65;
        *v65++ = v42;
        *(_DWORD *)v65 = v43;
        v65 += 2;
      }
      else
      {
        v8 += 24;
      }
      v45 = v73;
      v46 = v79;
      v47 = CUIHostLocale::m_CopyOrdinalOrName(v79, v73, v67, &v68, &v77);
      v48 = v65;
      v8 += CUIHostLocale::m_CopyOrdinalOrName(v46, v45, v67, &v68, &v76) + v47;
      if ( v7 && !v76 )
      {
        v49 = (wchar_t *)&strIn;
        if ( v48 )
          v49 = v48;
        AnsiBuffer::fConvert((AnsiBuffer *)&v81, v49);
        v50 = AnsiBuffer::szBuf((AnsiBuffer *)&v81);
        v51 = v50;
        if ( v50 && *v50 && MulDiv((__int16)*v83, nNumerator, 8) < (unsigned int)(2 * nNumerator) )
        {
          v52 = v84;
          v53 = MulDiv((__int16)*v84, nDenominator, 4);
          *(_QWORD *)&rc.left = 0;
          *(_QWORD *)&rc.right = 0;
          v54 = v53;
          v55 = -1;
          do
            ++v55;
          while ( v51[v55] );
          if ( (int)v55 >= 0 && (int)v55 == v55 )
          {
            v56 = v55;
            v78 = v55;
          }
          else
          {
            RaiseException(0xC0000095, 1u, 1u, (const ULONG_PTR *)v55);
            v56 = v78;
          }
          DrawTextA(hdc, v51, v56, &rc, 0x400u);
          if ( v77 && HIWORD(v77) == 128 )
          {
            v57 = v38 & 0xF;
            if ( v57 == 5 || v57 == 6 || v57 == 2 || v57 == 3 || v57 == 4 || v57 == 9 )
            {
              SystemMetrics = GetSystemMetrics(49);
              bottom = rc.bottom;
              if ( SystemMetrics > rc.bottom )
                bottom = GetSystemMetrics(49);
              right = bottom + rc.right;
            }
            else
            {
              right = rc.right + 5;
            }
            rc.right = right;
          }
          else
          {
            right = rc.right;
          }
          if ( v54 < right )
            *v52 = MulDiv(right, 4, nDenominator);
        }
      }
      v61 = *(_WORD *)v68;
      v62 = v68 + 2;
      if ( v7 )
      {
        *v65 = v61;
        v9 = ++v65;
      }
      else
      {
        v9 = v65;
        v8 += 2;
      }
      if ( v61 )
      {
        if ( v7 )
        {
          memcpy_0(v9, v62, v61);
          v9 = (wchar_t *)((char *)v65 + v61);
          v65 = v9;
        }
        else
        {
          v8 += v61;
        }
        v62 += v61;
      }
      if ( v7 )
      {
        v9 = (wchar_t *)(((unsigned __int64)v9 + 3) & 0xFFFFFFFFFFFFFFFCuLL);
        v65 = v9;
      }
      else
      {
        v8 = (v8 + 3) & 0xFFFFFFFC;
      }
      v24 = v66;
      v34 = lfFaceName;
      v35 = (unsigned __int64)(v62 + 3);
    }
    if ( v72 )
      goto LABEL_75;
    v5 = v85;
    v6 = (wchar_t **)v80;
    v7 = 1;
    v72 = 1;
    if ( hdc )
    {
      DeleteDC(hdc);
      v9 = v65;
    }
  }
  v10 = (wchar_t *)((__int64 (__fastcall *)(LPMALLOC, _QWORD, __int64))Rby_lpMalloc->lpVtbl->Alloc)(
                     Rby_lpMalloc,
                     v8,
                     0xFFFF);
  *v6 = v10;
  if ( v10 )
  {
    v67 = v8;
    memset_0(v10, 0, v8);
    v65 = *v6;
    CompatibleDC = CreateCompatibleDC(0);
    hdc = CompatibleDC;
    v12 = HfontIdeLight();
    SelectObject(CompatibleDC, v12);
    v13 = HfontIdeLight();
    DlgGetBaseUnitsOfHfont(v13, (unsigned int *)&nDenominator, (unsigned int *)&nNumerator);
    v9 = v65;
    goto LABEL_5;
  }
  v4 = -2147024882;
LABEL_75:
  CVerb::~CVerb((CVerb *)&v81);
  return v4;
}

```

## disassembly

```asm
0x180079d1c  mov     [rsp-8+arg_0], rbx
0x180079d21  push    rbp
0x180079d22  push    rsi
0x180079d23  push    rdi
0x180079d24  push    r12
0x180079d26  push    r13
0x180079d28  push    r14
0x180079d2a  push    r15
0x180079d2c  lea     rbp, [rsp-40h]
0x180079d31  mov     eax, 140h
0x180079d36  call    _alloca_probe
0x180079d3b  sub     rsp, rax
0x180079d3e  mov     rax, cs:__security_cookie
0x180079d45  xor     rax, rsp
0x180079d48  mov     [rbp+70h+var_40], rax
0x180079d4c  xor     edi, edi
0x180079d4e  mov     rbx, r8
0x180079d51  mov     r15, r9
0x180079d54  mov     [rbp+70h+var_E8], r9
0x180079d58  mov     [rbp+70h+var_F0], rcx
0x180079d5c  lea     r12d, [rdi+1]
0x180079d60  mov     r13d, edi
0x180079d63  mov     [rsp+170h+var_11C], edi
0x180079d67  mov     esi, edi
0x180079d69  mov     r10d, edi
0x180079d6c  mov     [rsp+170h+var_140], rdi
0x180079d71  mov     [rbp+70h+var_C0], rbx
0x180079d75  mov     [rbp+70h+var_E0], edi
0x180079d78  mov     [rbp+70h+var_D8], rdi
0x180079d7c  mov     [rsp+170h+var_134], edi
0x180079d80  mov     r8d, 0FFFFh
0x180079d86  mov     [rsp+170h+hdc], rdi
0x180079d8b  test    r13d, r13d
0x180079d8e  jz      short loc_180079E0A
0x180079d90  mov     rcx, cs:?Rby_lpMalloc@@3PEAUIMalloc@@EA; IMalloc * Rby_lpMalloc
0x180079d97  mov     edx, esi
0x180079d99  mov     r14d, esi
0x180079d9c  mov     rax, [rcx]
0x180079d9f  call    qword ptr [rax+18h]
0x180079da2  mov     [r15], rax
0x180079da5  test    rax, rax
0x180079da8  jz      loc_18007A440
0x180079dae  mov     r8d, r14d; Size
0x180079db1  xor     edx, edx; Val
0x180079db3  mov     rcx, rax; void *
0x180079db6  mov     [rsp+170h+var_134], esi
0x180079dba  call    memset_0
0x180079dbf  mov     r11, [r15]
0x180079dc2  xor     ecx, ecx; hdc
0x180079dc4  mov     [rsp+170h+var_140], r11
0x180079dc9  call    cs:__imp_CreateCompatibleDC
0x180079dcf  mov     r14, rax
0x180079dd2  mov     [rsp+170h+hdc], rax
0x180079dd7  call    ?HfontIdeLight@@YAPEAUHFONT__@@XZ; HfontIdeLight(void)
0x180079ddc  mov     rdx, rax; h
0x180079ddf  mov     rcx, r14; hdc
0x180079de2  call    cs:__imp_SelectObject
0x180079de8  call    ?HfontIdeLight@@YAPEAUHFONT__@@XZ; HfontIdeLight(void)
0x180079ded  lea     r8, [rsp+170h+nNumerator]; unsigned int *
0x180079df2  lea     rdx, [rsp+170h+nDenominator]; unsigned int *
0x180079df7  mov     rcx, rax; HFONT
0x180079dfa  call    ?DlgGetBaseUnitsOfHfont@@YAXPEAUHFONT__@@PEAI1@Z; DlgGetBaseUnitsOfHfont(HFONT__ *,uint *,uint *)
0x180079dff  mov     r10, [rsp+170h+var_140]
0x180079e04  mov     r8d, 0FFFFh
0x180079e0a  movzx   ecx, word ptr [rbx+2]
0x180079e0e  mov     edx, edi
0x180079e10  cmp     [rbx], r12w
0x180079e14  jnz     short loc_180079E2F
0x180079e16  cmp     cx, r8w
0x180079e1a  jnz     short loc_180079E2F
0x180079e1c  mov     edx, [rbx+4]
0x180079e1f  mov     ecx, [rbx+8]
0x180079e22  mov     r14d, [rbx+0Ch]
0x180079e26  add     rbx, 10h
0x180079e2a  mov     r15d, r12d
0x180079e2d  jmp     short loc_180079E3C
0x180079e2f  mov     r14d, [rbx]
0x180079e32  mov     ecx, [rbx+4]
0x180079e35  mov     r15d, edi
0x180079e38  add     rbx, 8
0x180079e3c  movzx   eax, word ptr [rbx]
0x180079e3f  movzx   r8d, word ptr [rbx+2]
0x180079e44  movzx   r9d, word ptr [rbx+4]
0x180079e49  movzx   r11d, word ptr [rbx+6]
0x180079e4e  movzx   r12d, word ptr [rbx+8]
0x180079e53  add     rbx, 0Ah
0x180079e57  mov     [rsp+170h+var_138], ax
0x180079e5c  mov     [rsp+170h+var_130], rbx
0x180079e61  test    r13d, r13d
0x180079e64  jz      loc_180079F27
0x180079e6a  movzx   ebx, [rsp+170h+var_138]
0x180079e6f  mov     eax, 1
0x180079e74  mov     [r10], ax
0x180079e78  mov     rax, [rsp+170h+var_140]
0x180079e7d  mov     r10d, 0FFFFh
0x180079e83  add     rax, 2
0x180079e87  mov     [rsp+170h+var_140], rax
0x180079e8c  mov     [rax], r10w
0x180079e90  mov     rax, [rsp+170h+var_140]
0x180079e95  add     rax, 2
0x180079e99  mov     [rsp+170h+var_140], rax
0x180079e9e  mov     [rax], edx
0x180079ea0  mov     rax, [rsp+170h+var_140]
0x180079ea5  add     rax, 4
0x180079ea9  mov     [rsp+170h+var_140], rax
0x180079eae  mov     [rax], ecx
0x180079eb0  mov     rcx, [rsp+170h+var_140]
0x180079eb5  mov     eax, r14d
0x180079eb8  or      eax, 40h
0x180079ebb  add     rcx, 4
0x180079ebf  mov     [rsp+170h+var_140], rcx
0x180079ec4  mov     [rcx], eax
0x180079ec6  mov     rax, [rsp+170h+var_140]
0x180079ecb  add     rax, 4
0x180079ecf  mov     [rsp+170h+var_140], rax
0x180079ed4  mov     [rax], bx
0x180079ed7  mov     rax, [rsp+170h+var_140]
0x180079edc  add     rax, 2
0x180079ee0  mov     [rsp+170h+var_140], rax
0x180079ee5  mov     [rax], r8w
0x180079ee9  mov     rax, [rsp+170h+var_140]
0x180079eee  add     rax, 2
0x180079ef2  mov     [rsp+170h+var_140], rax
0x180079ef7  mov     [rax], r9w
0x180079efb  mov     rax, [rsp+170h+var_140]
0x180079f00  add     rax, 2
0x180079f04  mov     [rsp+170h+var_140], rax
0x180079f09  mov     [rax], r11w
0x180079f0d  mov     rax, [rsp+170h+var_140]
0x180079f12  add     rax, 2
0x180079f16  mov     [rsp+170h+var_140], rax
0x180079f1b  mov     [rax], r12w
0x180079f1f  add     [rsp+170h+var_140], 2
0x180079f25  jmp     short loc_180079F2D
0x180079f27  add     esi, 1Ah
0x180079f2a  movzx   ebx, ax
0x180079f2d  mov     r12, [rbp+70h+var_F0]
0x180079f31  mov     r8d, [rsp+170h+var_134]; unsigned int
0x180079f36  mov     eax, r13d
0x180079f39  neg     eax
0x180079f3b  lea     rcx, [rsp+170h+var_140]
0x180079f40  lea     r9, [rsp+170h+var_130]; unsigned __int8 **
0x180079f45  sbb     rax, rax
0x180079f48  mov     qword ptr [rsp+170h+format], rdi; unsigned int *
0x180079f4d  and     rax, rcx
0x180079f50  mov     rcx, r12; this
0x180079f53  mov     rdx, rax; unsigned __int8 **
0x180079f56  mov     [rsp+170h+var_118], rax
0x180079f5b  call    ?m_CopyOrdinalOrName@CUIHostLocale@@AEAAHPEAPEAEK0PEAK@Z; CUIHostLocale::m_CopyOrdinalOrName(uchar * *,ulong,uchar * *,ulong *)
0x180079f60  mov     r8d, [rsp+170h+var_134]; unsigned int
0x180079f65  mov     rdx, [rsp+170h+var_118]; unsigned __int8 **
0x180079f6a  lea     r9, [rsp+170h+var_130]; unsigned __int8 **
0x180079f6f  mov     rcx, r12; this
0x180079f72  add     esi, eax
0x180079f74  mov     qword ptr [rsp+170h+format], rdi; unsigned int *
0x180079f79  call    ?m_CopyOrdinalOrName@CUIHostLocale@@AEAAHPEAPEAEK0PEAK@Z; CUIHostLocale::m_CopyOrdinalOrName(uchar * *,ulong,uchar * *,ulong *)
0x180079f7e  mov     r8d, [rsp+170h+var_134]; unsigned int
0x180079f83  mov     rdx, [rsp+170h+var_118]; unsigned __int8 **
0x180079f88  lea     r9, [rsp+170h+var_130]; unsigned __int8 **
0x180079f8d  mov     rcx, r12; this
0x180079f90  add     esi, eax
0x180079f92  call    ?m_CopyString@CUIHostLocale@@AEAAHPEAPEAEK0@Z; CUIHostLocale::m_CopyString(uchar * *,ulong,uchar * *)
0x180079f97  add     esi, eax
0x180079f99  test    r14b, 40h
0x180079f9d  jz      short loc_180079FD5
0x180079f9f  mov     rcx, [rsp+170h+var_130]
0x180079fa4  movzx   eax, word ptr [rcx]
0x180079fa7  add     rcx, 2
0x180079fab  mov     [rsp+170h+var_128], ax
0x180079fb0  mov     [rsp+170h+var_130], rcx
0x180079fb5  test    r15d, r15d
0x180079fb8  jz      short loc_180079FC3
0x180079fba  add     rcx, 4
0x180079fbe  mov     [rsp+170h+var_130], rcx
0x180079fc3  lea     r9, [rsp+170h+var_130]; unsigned __int8 **
0x180079fc8  xor     r8d, r8d; unsigned int
0x180079fcb  xor     edx, edx; unsigned __int8 **
0x180079fcd  mov     rcx, r12; this
0x180079fd0  call    ?m_CopyString@CUIHostLocale@@AEAAHPEAPEAEK0@Z; CUIHostLocale::m_CopyString(uchar * *,ulong,uchar * *)
0x180079fd5  lea     r8, [rsp+170h+var_128]; unsigned __int16 *
0x180079fda  lea     rdx, [rbp+70h+var_A0]; struct tagLOGFONTW *
0x180079fde  mov     rcx, r12; this
0x180079fe1  call    ?m_GetDialogFont@CUIHostLocale@@AEAAJPEAUtagLOGFONTW@@PEAG@Z; CUIHostLocale::m_GetDialogFont(tagLOGFONTW *,ushort *)
0x180079fe6  movzx   r11d, word ptr [rbp+70h+var_A0.lfWeight]
0x180079feb  mov     dl, [rbp+70h+var_A0.lfItalic]
0x180079fee  mov     r8b, [rbp+70h+var_A0.lfCharSet]
0x180079ff2  test    r13d, r13d
0x180079ff5  jz      short loc_18007A042
0x180079ff7  mov     rcx, [rsp+170h+var_140]
0x180079ffc  movzx   eax, [rsp+170h+var_128]
0x18007a001  mov     [rcx], ax
0x18007a004  mov     rax, [rsp+170h+var_140]
0x18007a009  mov     ecx, 1
0x18007a00e  add     rax, 2
0x18007a012  mov     [rsp+170h+var_140], rax
0x18007a017  mov     [rax], r11w
0x18007a01b  mov     rax, [rsp+170h+var_140]
0x18007a020  add     rax, 2
0x18007a024  mov     [rsp+170h+var_140], rax
0x18007a029  mov     [rax], dl
0x18007a02b  mov     rax, [rsp+170h+var_140]
0x18007a030  add     rax, rcx
0x18007a033  mov     [rsp+170h+var_140], rax
0x18007a038  mov     [rax], r8b
0x18007a03b  add     [rsp+170h+var_140], rcx
0x18007a040  jmp     short loc_18007A045
0x18007a042  add     esi, 6
0x18007a045  mov     r8d, [rsp+170h+var_134]; unsigned int
0x18007a04a  mov     rdx, [rsp+170h+var_118]; unsigned __int8 **
0x18007a04f  lea     rax, [rbp+70h+var_A0.lfFaceName]
0x18007a053  lea     r9, [rsp+170h+var_108]; unsigned __int8 **
0x18007a058  mov     rcx, r12; this
0x18007a05b  mov     [rsp+170h+var_108], rax
0x18007a060  call    ?m_CopyString@CUIHostLocale@@AEAAHPEAPEAEK0@Z; CUIHostLocale::m_CopyString(uchar * *,ulong,uchar * *)
0x18007a065  mov     r10, [rsp+170h+var_140]
0x18007a06a  add     esi, eax
0x18007a06c  test    r13d, r13d
0x18007a06f  jz      short loc_18007A080
0x18007a071  add     r10, 3
0x18007a075  and     r10, 0FFFFFFFFFFFFFFFCh
0x18007a079  mov     [rsp+170h+var_140], r10
0x18007a07e  jmp     short loc_18007A086
0x18007a080  add     esi, 3
0x18007a083  and     esi, 0FFFFFFFCh
0x18007a086  mov     rcx, [rsp+170h+var_130]
0x18007a08b  movsxd  rax, r15d
0x18007a08e  movsxd  r13, r13d
0x18007a091  add     rcx, 3
0x18007a095  mov     [rsp+170h+var_108], rax
0x18007a09a  jmp     loc_18007A3F0
0x18007a09f  mov     r8d, [rcx+4]
0x18007a0a3  mov     edx, 0FFFFh
0x18007a0a8  add     bx, dx
0x18007a0ab  mov     [rsp+170h+var_138], bx
0x18007a0b0  test    rax, rax
0x18007a0b3  jz      short loc_18007A0D8
0x18007a0b5  mov     edx, [rcx]
0x18007a0b7  mov     ebx, [rcx+8]
0x18007a0ba  movzx   r9d, word ptr [rcx+0Ch]
0x18007a0bf  movzx   r11d, word ptr [rcx+0Eh]
0x18007a0c4  movzx   r14d, word ptr [rcx+10h]
0x18007a0c9  movzx   r15d, word ptr [rcx+12h]
0x18007a0ce  mov     r12d, [rcx+14h]
0x18007a0d2  add     rcx, 18h
0x18007a0d6  jmp     short loc_18007A0F9
0x18007a0d8  mov     ebx, [rcx]
0x18007a0da  movzx   r9d, word ptr [rcx+8]
0x18007a0df  movzx   r11d, word ptr [rcx+0Ah]
0x18007a0e4  movzx   r14d, word ptr [rcx+0Ch]
0x18007a0e9  movzx   r15d, word ptr [rcx+0Eh]
0x18007a0ee  movzx   r12d, word ptr [rcx+10h]
0x18007a0f3  add     rcx, 12h
0x18007a0f7  mov     edx, edi
0x18007a0f9  mov     [rsp+170h+var_130], rcx
0x18007a0fe  test    r13, r13
0x18007a101  jz      loc_18007A194
0x18007a107  mov     [r10], edx
0x18007a10a  mov     rax, [rsp+170h+var_140]
0x18007a10f  add     rax, 4
0x18007a113  mov     [rsp+170h+var_140], rax
0x18007a118  mov     [rax], r8d
0x18007a11b  mov     rax, [rsp+170h+var_140]
0x18007a120  add     rax, 4
0x18007a124  mov     [rsp+170h+var_140], rax
0x18007a129  mov     [rax], ebx
0x18007a12b  mov     rax, [rsp+170h+var_140]
0x18007a130  add     rax, 4
0x18007a134  mov     [rsp+170h+var_140], rax
0x18007a139  mov     [rax], r9w
0x18007a13d  mov     rax, [rsp+170h+var_140]
0x18007a142  add     rax, 2
0x18007a146  mov     [rsp+170h+var_140], rax
0x18007a14b  mov     [rax], r11w
0x18007a14f  mov     rax, [rsp+170h+var_140]
0x18007a154  add     rax, 2
0x18007a158  mov     [rsp+170h+var_140], rax
0x18007a15d  mov     [rbp+70h+var_C8], rax
0x18007a161  mov     [rax], r14w
0x18007a165  mov     rax, [rsp+170h+var_140]
0x18007a16a  add     rax, 2
0x18007a16e  mov     [rsp+170h+var_140], rax
0x18007a173  mov     [rbp+70h+var_D0], rax
0x18007a177  mov     [rax], r15w
0x18007a17b  mov     rax, [rsp+170h+var_140]
0x18007a180  add     rax, 2
0x18007a184  mov     [rsp+170h+var_140], rax
0x18007a189  mov     [rax], r12d
0x18007a18c  add     [rsp+170h+var_140], 4
0x18007a192  jmp     short loc_18007A197
0x18007a194  add     esi, 18h
0x18007a197  mov     r12, [rsp+170h+var_118]
0x18007a19c  mov     r15, [rbp+70h+var_F0]
0x18007a1a0  mov     r8d, [rsp+170h+var_134]; unsigned int
0x18007a1a5  lea     rax, [rsp+170h+var_FC]
0x18007a1aa  lea     r9, [rsp+170h+var_130]; unsigned __int8 **
0x18007a1af  mov     rdx, r12; unsigned __int8 **
0x18007a1b2  mov     rcx, r15; this
0x18007a1b5  mov     qword ptr [rsp+170h+format], rax; unsigned int *
0x18007a1ba  call    ?m_CopyOrdinalOrName@CUIHostLocale@@AEAAHPEAPEAEK0PEAK@Z; CUIHostLocale::m_CopyOrdinalOrName(uchar * *,ulong,uchar * *,ulong *)
0x18007a1bf  mov     r8d, [rsp+170h+var_134]; unsigned int
  ... truncated ...
```
