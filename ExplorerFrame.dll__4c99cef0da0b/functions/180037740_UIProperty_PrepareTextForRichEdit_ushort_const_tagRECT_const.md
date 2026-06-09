# UIProperty::_PrepareTextForRichEdit(ushort const *,tagRECT const *)

- ea: `0x180037740`
- end: `0x180037c1d`
- name: `?_PrepareTextForRichEdit@UIProperty@@IEAAJPEBGPEBUtagRECT@@@Z`
- size: `1245`
- prototype: `__int64 __fastcall(UIProperty *__hidden this, LPCWSTR lpString2, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000d594`

## callees

- `0x18000d360`
- `0x18000d440`
- `0x180033370`
- `0x180037240`
- `0x180037740`
- `0x180037c24`
- `0x180037ce0`
- `0x180079de0`
- `0x18007bc74`
- `0x18013f7d0`
- `0x1801406ec`
- `0x180210010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037892`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037892`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037864`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037a96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037c11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037864`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037a96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037c11`
- `KERNEL32!lstrcmpW` at `0x1800379d9`
- `KERNEL32!lstrcmpW` at `0x180037a52`
- `KERNEL32!lstrcmpW` at `0x1800379d9`
- `KERNEL32!lstrcmpW` at `0x180037a52`
- `USER32!DrawTextW` at `0x1800379ac`
- `USER32!DrawTextW` at `0x1800379ac`
- `GDI32!CreateCompatibleDC` at `0x180037be8`
- `GDI32!CreateCompatibleDC` at `0x180037be8`
- `DUI70!?ShowAccel@HWNDElement@DirectUI@@QEAA_NXZ` at `0x180037bbf`
- `DUI70!?ShowAccel@HWNDElement@DirectUI@@QEAA_NXZ` at `0x180037bbf`
- `DUI70!?GetShortcut@Element@DirectUI@@QEAAHXZ` at `0x180037791`
- `DUI70!?GetShortcut@Element@DirectUI@@QEAAHXZ` at `0x180037791`
- `DUI70!?GetContentAlign@Element@DirectUI@@QEAAHXZ` at `0x1800377bc`
- `DUI70!?GetContentAlign@Element@DirectUI@@QEAAHXZ` at `0x1800377bc`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x1800377c7`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x1800377c7`
- `DUI70!?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180037ba5`
- `DUI70!?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180037ba5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UIProperty::_PrepareTextForRichEdit(LPCWSTR *this, LPCWSTR lpString2, const struct tagRECT *a3)
{
  signed int v6; // edi
  int v7; // ebx
  int v8; // esi
  __int16 ContentAlign; // bx
  int v10; // edx
  int v11; // eax
  int v12; // ebp
  UINT format; // ebp
  __int64 v14; // rax
  unsigned __int64 v15; // r13
  WCHAR *v16; // rbx
  unsigned __int64 v17; // rsi
  __int64 v18; // rcx
  const WCHAR *v19; // rax
  unsigned __int64 v20; // rdx
  WCHAR *v21; // r8
  __int64 v22; // r10
  WCHAR v23; // r9
  __int64 v24; // r9
  WCHAR *v25; // rcx
  struct UIItemsView *UIItemsView; // rax
  struct UIItemsView *v27; // rsi
  HDC v28; // rsi
  unsigned int v29; // r9d
  WCHAR *v30; // rcx
  WCHAR i; // ax
  __int64 v32; // rax
  unsigned int v33; // esi
  unsigned int j; // r10d
  LPVOID *v35; // rsi
  WCHAR *v36; // rbp
  __int64 v38; // rsi
  bool v39; // cf
  LPCWSTR v40; // r11
  unsigned int v41; // edx
  unsigned int v42; // ecx
  unsigned int v43; // eax
  struct DirectUI::Element *Root; // rax
  DirectUI::HWNDElement *v45; // rax
  HDC HDC; // rax
  _QWORD v47[4]; // [rsp+38h] [rbp-70h] BYREF
  struct tagRECT rc; // [rsp+58h] [rbp-50h] BYREF

  UIProperty::_UpdatePARAFORMAT((UIProperty *)this);
  memset_0((char *)this + 380, 0, 0x5Cu);
  v6 = 0;
  v7 = 2048;
  if ( DirectUI::Element::GetShortcut((DirectUI::Element *)this) )
  {
    v7 = 0;
    Root = DirectUI::Element::GetRoot((DirectUI::Element *)this);
    v45 = (DirectUI::HWNDElement *)element_cast<DirectUI::HWNDElement>(Root);
    if ( v45 )
    {
      if ( !DirectUI::HWNDElement::ShowAccel(v45) )
        v7 = 0x100000;
    }
  }
  v8 = v7 | 0x20000;
  if ( !(*((unsigned __int8 (__fastcall **)(LPCWSTR *))*this + 1))(this) )
    v8 = v7;
  ContentAlign = DirectUI::Element::GetContentAlign((DirectUI::Element *)this);
  if ( DirectUI::Element::IsRTL((DirectUI::Element *)this) )
  {
    if ( (ContentAlign & 3) != 0 )
    {
      if ( (ContentAlign & 3) == 2 )
        ContentAlign &= 0xFFFCu;
    }
    else
    {
      ContentAlign = ContentAlign & 0xFFFC | 2;
    }
  }
  v10 = ((ContentAlign & 0x10) << 11) | 0x4000;
  if ( (ContentAlign & 0x40) == 0 )
    v10 = (ContentAlign & 0x10) << 11;
  if ( (ContentAlign & 0x100) != 0 )
    v10 |= 0x40000u;
  if ( (ContentAlign & 3) != 0 )
  {
    if ( (ContentAlign & 3) == 1 )
    {
      v10 |= 1u;
    }
    else if ( (ContentAlign & 3) == 2 )
    {
      v10 |= 2u;
    }
  }
  v11 = ContentAlign & 0xC;
  if ( (ContentAlign & 0xC) != 0 )
  {
    switch ( v11 )
    {
      case 4:
        v10 |= 0x24u;
        break;
      case 8:
        v10 |= 0x28u;
        break;
      case 12:
        v10 |= 0x10u;
        break;
    }
  }
  else
  {
    v10 |= 0x20u;
  }
  v12 = v10 | 0x2000;
  if ( (ContentAlign & 0x200) == 0 )
    v12 = v10;
  format = v8 | v12 | 0x10000;
  if ( (format & 0x4C000) != 0 )
  {
    v14 = -1;
    do
      ++v14;
    while ( lpString2[v14] );
    v15 = v14 + 5;
    CoTaskMemFree(0);
    v16 = 0;
    v17 = v15 + 1;
    if ( v15 + 1 >= v15 && is_mul_ok(v17, 2u) )
    {
      v16 = (WCHAR *)CoTaskMemAlloc(2 * v17);
      v6 = v16 == 0 ? 0x8007000E : 0;
      if ( v16 )
      {
        if ( v17 > 0x7FFFFFFF )
          goto LABEL_78;
        if ( v15 < 0x7FFFFFFF )
        {
          v18 = v15 & -(__int64)(lpString2 != 0);
          v19 = &WindowName;
          if ( lpString2 )
            v19 = lpString2;
          v20 = v15 + 1;
          v21 = v16;
          v22 = 0;
          do
          {
            if ( !v18 )
              break;
            v23 = *v19;
            if ( !*v19 )
              break;
            ++v19;
            *v21++ = v23;
            --v18;
            ++v22;
            --v20;
          }
          while ( v20 );
          v24 = v22 - 1;
          if ( v20 )
            v24 = v22;
          v25 = v21 - 1;
          if ( v20 )
            v25 = v21;
          *v25 = 0;
          if ( v20 )
          {
            v39 = v17 == v24;
            v38 = v17 - v24;
            if ( !v39 && v38 != 1 && (unsigned __int64)(2 * v38) > 2 )
              memset_0(&v16[v24 + 1], 0, 2 * v38 - 2);
          }
          goto LABEL_39;
        }
        if ( v15 != -1 )
LABEL_78:
          *v16 = 0;
LABEL_39:
        v6 = -2147467259;
        UIItemsView = GetUIItemsView((struct DirectUI::Element *)this);
        v27 = UIItemsView;
        if ( UIItemsView )
        {
          if ( !*((_QWORD *)UIItemsView + 70) )
          {
            HDC = UIItemsView::GetHDC(UIItemsView);
            if ( HDC )
              *((_QWORD *)v27 + 70) = CreateCompatibleDC(HDC);
          }
          v28 = (HDC)*((_QWORD *)v27 + 70);
          if ( v28 )
          {
            CAutoFont::CAutoFont((CAutoFont *)v47, (struct DirectUI::Element *)this, v28);
            if ( v47[0] )
            {
              v6 = 0;
              rc = *a3;
              DrawTextW(v28, v16, -1, &rc, format);
              CAutoFont::Release((CAutoFont *)v47);
            }
            CAutoFont::Release((CAutoFont *)v47);
            if ( v6 >= 0 )
            {
              if ( lstrcmpW(v16, lpString2) )
              {
                StringCchCatW(v16, v15, &qword_180235D20);
                v29 = 0;
                v30 = v16;
                for ( i = *lpString2; *v30 == *lpString2; i = *lpString2 )
                {
                  if ( !i )
                    break;
                  ++v29;
                  ++v30;
                  ++lpString2;
                }
                v32 = -1;
                do
                  ++v32;
                while ( v16[v32] );
                v33 = v32 - 1;
                for ( j = 0; j < *((_DWORD *)this + 140); ++j )
                {
                  v40 = this[69];
                  v41 = *(_DWORD *)&v40[4 * j];
                  if ( v41 < v29 )
                  {
                    v42 = v41 + *(_DWORD *)&v40[4 * j + 2];
                    if ( v29 < v42 )
                      v42 = v33;
                  }
                  else
                  {
                    v42 = *(_DWORD *)&v40[4 * j];
                  }
                  v43 = v42;
                  if ( v42 >= v41 )
                    v43 = *(_DWORD *)&v40[4 * j];
                  *(_DWORD *)&v40[4 * j] = v43;
                  *(_DWORD *)&this[69][4 * j + 2] = v42 - v43;
                }
              }
              v35 = (LPVOID *)(this + 61);
              if ( lstrcmpW(v16, this[61]) )
              {
                *((_DWORD *)this + 128) = 1;
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(this + 61);
                v36 = v16;
                v16 = 0;
                if ( *v35 )
                  CoTaskMemFree(*v35);
                *v35 = v36;
                this[63] = (LPCWSTR)-1LL;
                this[62] = (LPCWSTR)-1LL;
              }
            }
          }
        }
      }
    }
    else
    {
      v6 = -2147024362;
    }
    CoTaskMemFree(v16);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180037740  mov     [rsp+arg_18], rbx
0x180037745  push    rbp
0x180037746  push    rsi
0x180037747  push    rdi
0x180037748  push    r12
0x18003774a  push    r13
0x18003774c  push    r14
0x18003774e  push    r15
0x180037750  sub     rsp, 70h
0x180037754  mov     rax, cs:__security_cookie
0x18003775b  xor     rax, rsp
0x18003775e  mov     [rsp+0A8h+var_40], rax
0x180037763  mov     r12, r8
0x180037766  mov     r15, rdx
0x180037769  mov     r14, rcx
0x18003776c  call    ?_UpdatePARAFORMAT@UIProperty@@IEAAXXZ; UIProperty::_UpdatePARAFORMAT(void)
0x180037771  lea     rcx, [r14+17Ch]; void *
0x180037778  xor     edx, edx; Val
0x18003777a  lea     r8d, [rdx+5Ch]; Size
0x18003777e  call    memset_0
0x180037783  xor     r13d, r13d
0x180037786  mov     edi, r13d
0x180037789  mov     ebx, 800h
0x18003778e  mov     rcx, r14
0x180037791  call    cs:__imp_?GetShortcut@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetShortcut(void)
0x180037797  test    eax, eax
0x180037799  jnz     loc_180037B9F
0x18003779f  mov     rax, [r14]
0x1800377a2  mov     rcx, r14
0x1800377a5  mov     rax, [rax+8]
0x1800377a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377ae  mov     esi, ebx
0x1800377b0  bts     esi, 11h
0x1800377b4  test    al, al
0x1800377b6  cmovz   esi, ebx
0x1800377b9  mov     rcx, r14
0x1800377bc  call    cs:__imp_?GetContentAlign@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetContentAlign(void)
0x1800377c2  mov     ebx, eax
0x1800377c4  mov     rcx, r14
0x1800377c7  call    cs:__imp_?IsRTL@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsRTL(void)
0x1800377cd  test    al, al
0x1800377cf  jnz     loc_180037B15
0x1800377d5  mov     ecx, ebx
0x1800377d7  and     ecx, 10h
0x1800377da  shl     ecx, 0Bh
0x1800377dd  mov     edx, ecx
0x1800377df  bts     edx, 0Eh
0x1800377e3  test    bl, 40h
0x1800377e6  cmovz   edx, ecx
0x1800377e9  bt      ebx, 8
0x1800377ed  jnb     short loc_1800377F3
0x1800377ef  bts     edx, 12h
0x1800377f3  mov     ecx, ebx
0x1800377f5  and     ecx, 3
0x1800377f8  jz      short loc_18003780C
0x1800377fa  sub     ecx, 1
0x1800377fd  jz      loc_180037B0D
0x180037803  cmp     ecx, 1
0x180037806  jz      loc_180037B05
0x18003780c  mov     eax, ebx
0x18003780e  and     eax, 0Ch
0x180037811  jz      loc_180037ACB
0x180037817  cmp     eax, 4
0x18003781a  jz      loc_180037AC3
0x180037820  cmp     eax, 8
0x180037823  jz      loc_180037B2D
0x180037829  cmp     eax, 0Ch
0x18003782c  jnz     short loc_180037831
0x18003782e  or      edx, 10h
0x180037831  mov     ebp, edx
0x180037833  bts     ebp, 0Dh
0x180037837  bt      ebx, 9
0x18003783b  cmovnb  ebp, edx
0x18003783e  or      ebp, esi
0x180037840  bts     ebp, 10h
0x180037844  test    ebp, 4C000h
0x18003784a  jz      loc_180037A9C
0x180037850  or      rax, 0FFFFFFFFFFFFFFFFh
0x180037854  inc     rax
0x180037857  cmp     [r15+rax*2], r13w
0x18003785c  jnz     short loc_180037854
0x18003785e  lea     r13, [rax+5]
0x180037862  xor     ecx, ecx; pv
0x180037864  call    cs:__imp_CoTaskMemFree
0x18003786a  xor     ecx, ecx
0x18003786c  mov     ebx, ecx
0x18003786e  lea     rsi, [r13+1]
0x180037872  cmp     rsi, r13
0x180037875  jb      loc_180037A8E
0x18003787b  mov     [rsp+0A8h+var_78], rcx
0x180037880  lea     eax, [rcx+2]
0x180037883  mul     rsi
0x180037886  test    rdx, rdx
0x180037889  jnz     loc_180037A8E
0x18003788f  mov     rcx, rax; cb
0x180037892  call    cs:__imp_CoTaskMemAlloc
0x180037898  mov     rbx, rax
0x18003789b  mov     [rsp+0A8h+var_78], rax
0x1800378a0  neg     rax
0x1800378a3  sbb     edi, edi
0x1800378a5  not     edi
0x1800378a7  and     edi, 8007000Eh
0x1800378ad  xor     r11d, r11d
0x1800378b0  test    rbx, rbx
0x1800378b3  jz      loc_180037A93
0x1800378b9  mov     eax, 7FFFFFFFh
0x1800378be  cmp     rsi, rax
0x1800378c1  ja      loc_180037B96
0x1800378c7  cmp     r13, rax
0x1800378ca  jnb     loc_180037B8D
0x1800378d0  mov     rax, r15
0x1800378d3  neg     rax
0x1800378d6  sbb     rcx, rcx
0x1800378d9  and     rcx, r13
0x1800378dc  lea     rax, WindowName
0x1800378e3  test    r15, r15
0x1800378e6  cmovnz  rax, r15
0x1800378ea  test    rsi, rsi
0x1800378ed  jz      short loc_18003793C
0x1800378ef  mov     rdx, rsi
0x1800378f2  mov     r8, rbx
0x1800378f5  mov     r10d, r11d
0x1800378f8  test    rcx, rcx
0x1800378fb  jz      short loc_18003791F
0x1800378fd  movzx   r9d, word ptr [rax]
0x180037901  test    r9w, r9w
0x180037905  jz      short loc_18003791F
0x180037907  add     rax, 2
0x18003790b  mov     [r8], r9w
0x18003790f  add     r8, 2
0x180037913  dec     rcx
0x180037916  inc     r10
0x180037919  sub     rdx, 1
0x18003791d  jnz     short loc_1800378F8
0x18003791f  lea     r9, [r10-1]
0x180037923  test    rdx, rdx
0x180037926  cmovnz  r9, r10
0x18003792a  lea     rcx, [r8-2]
0x18003792e  cmovnz  rcx, r8
0x180037932  mov     [rcx], r11w
0x180037936  jnz     loc_180037AD3
0x18003793c  mov     edi, 80004005h
0x180037941  mov     rcx, r14; struct DirectUI::Element *
0x180037944  call    ?GetUIItemsView@@YAPEAVUIItemsView@@PEAVElement@DirectUI@@@Z; GetUIItemsView(DirectUI::Element *)
0x180037949  mov     rsi, rax
0x18003794c  test    rax, rax
0x18003794f  jz      loc_180037A93
0x180037955  cmp     qword ptr [rax+230h], 0
0x18003795d  jz      loc_180037BD4
0x180037963  mov     rsi, [rsi+230h]
0x18003796a  test    rsi, rsi
0x18003796d  jz      loc_180037A93
0x180037973  mov     r8, rsi; HDC
0x180037976  mov     rdx, r14; struct DirectUI::Element *
0x180037979  lea     rcx, [rsp+0A8h+var_70]; this
0x18003797e  call    ??0CAutoFont@@QEAA@PEAVElement@DirectUI@@PEAUHDC__@@@Z; CAutoFont::CAutoFont(DirectUI::Element *,HDC__ *)
0x180037983  nop
0x180037984  cmp     [rsp+0A8h+var_70], 0
0x18003798a  jz      short loc_1800379BD
0x18003798c  xor     edi, edi
0x18003798e  movups  xmm0, xmmword ptr [r12]
0x180037993  movdqu  xmmword ptr [rsp+0A8h+rc.left], xmm0
0x180037999  mov     [rsp+0A8h+format], ebp; format
0x18003799d  lea     r9, [rsp+0A8h+rc]; lprc
0x1800379a2  or      r8d, 0FFFFFFFFh; cchText
0x1800379a6  mov     rdx, rbx; lpchText
0x1800379a9  mov     rcx, rsi; hdc
0x1800379ac  call    cs:__imp_DrawTextW
0x1800379b2  lea     rcx, [rsp+0A8h+var_70]; this
0x1800379b7  call    ?Release@CAutoFont@@QEAAXXZ; CAutoFont::Release(void)
0x1800379bc  nop
0x1800379bd  lea     rcx, [rsp+0A8h+var_70]; this
0x1800379c2  call    ?Release@CAutoFont@@QEAAXXZ; CAutoFont::Release(void)
0x1800379c7  nop
0x1800379c8  xor     r12d, r12d
0x1800379cb  test    edi, edi
0x1800379cd  js      loc_180037A93
0x1800379d3  mov     rdx, r15; lpString2
0x1800379d6  mov     rcx, rbx; lpString1
0x1800379d9  call    cs:__imp_lstrcmpW
0x1800379df  test    eax, eax
0x1800379e1  jz      loc_180037B84
0x1800379e7  lea     r8, qword_180235D20; unsigned __int16 *
0x1800379ee  mov     rdx, r13; unsigned __int64
0x1800379f1  mov     rcx, rbx; unsigned __int16 *
0x1800379f4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800379f9  mov     r9d, r12d
0x1800379fc  mov     rcx, rbx
0x1800379ff  movzx   eax, word ptr [r15]
0x180037a03  cmp     [rbx], ax
0x180037a06  jnz     short loc_180037A21
0x180037a08  test    ax, ax
0x180037a0b  jz      short loc_180037A21
0x180037a0d  inc     r9d
0x180037a10  add     rcx, 2
0x180037a14  add     r15, 2
0x180037a18  movzx   eax, word ptr [r15]
0x180037a1c  cmp     [rcx], ax
0x180037a1f  jz      short loc_180037A08
0x180037a21  or      r15, 0FFFFFFFFFFFFFFFFh
0x180037a25  mov     rax, r15
0x180037a28  inc     rax
0x180037a2b  cmp     [rbx+rax*2], r12w
0x180037a30  jnz     short loc_180037A28
0x180037a32  lea     esi, [rax-1]
0x180037a35  mov     r10d, r12d
0x180037a38  cmp     [r14+230h], r12d
0x180037a3f  ja      loc_180037B40
0x180037a45  lea     rsi, [r14+1E8h]
0x180037a4c  mov     rdx, [rsi]; lpString2
0x180037a4f  mov     rcx, rbx; lpString1
0x180037a52  call    cs:__imp_lstrcmpW
0x180037a58  test    eax, eax
0x180037a5a  jz      short loc_180037A93
0x180037a5c  mov     dword ptr [r14+200h], 1
0x180037a67  mov     rcx, rsi
0x180037a6a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180037a6f  mov     rbp, rbx
0x180037a72  mov     rbx, r12
0x180037a75  mov     rcx, [rsi]; pv
0x180037a78  test    rcx, rcx
0x180037a7b  jnz     loc_180037C11
0x180037a81  mov     [rsi], rbp
0x180037a84  mov     [rsi+10h], r15
0x180037a88  mov     [rsi+8], r15
0x180037a8c  jmp     short loc_180037A93
0x180037a8e  mov     edi, 80070216h
0x180037a93  mov     rcx, rbx; pv
0x180037a96  call    cs:__imp_CoTaskMemFree
0x180037a9c  mov     eax, edi
0x180037a9e  mov     rcx, [rsp+0A8h+var_40]
0x180037aa3  xor     rcx, rsp; StackCookie
0x180037aa6  call    __security_check_cookie
0x180037aab  mov     rbx, [rsp+0A8h+arg_18]
0x180037ab3  add     rsp, 70h
0x180037ab7  pop     r15
0x180037ab9  pop     r14
0x180037abb  pop     r13
0x180037abd  pop     r12
0x180037abf  pop     rdi
0x180037ac0  pop     rsi
0x180037ac1  pop     rbp
0x180037ac2  retn
0x180037ac3  or      edx, 24h
0x180037ac6  jmp     loc_180037831
0x180037acb  or      edx, 20h
0x180037ace  jmp     loc_180037831
0x180037ad3  sub     rsi, r9
0x180037ad6  cmp     rsi, 1
0x180037ada  jbe     loc_18003793C
0x180037ae0  lea     r8, [rsi+rsi]
0x180037ae4  cmp     r8, 2
0x180037ae8  jbe     loc_18003793C
0x180037aee  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180037af2  inc     r9
0x180037af5  lea     rcx, [rbx+r9*2]; void *
0x180037af9  xor     edx, edx; Val
0x180037afb  call    memset_0
0x180037b00  jmp     loc_18003793C
0x180037b05  or      edx, 2
0x180037b08  jmp     loc_18003780C
0x180037b0d  or      edx, 1
0x180037b10  jmp     loc_18003780C
0x180037b15  mov     eax, ebx
0x180037b17  and     eax, 3
0x180037b1a  jz      short loc_180037B35
0x180037b1c  cmp     eax, 2
0x180037b1f  jnz     loc_1800377D5
0x180037b25  and     ebx, 0FFFFFFFCh
0x180037b28  jmp     loc_1800377D5
0x180037b2d  or      edx, 28h
0x180037b30  jmp     loc_180037831
0x180037b35  and     ebx, 0FFFFFFFEh
0x180037b38  or      ebx, 2
0x180037b3b  jmp     loc_1800377D5
0x180037b40  mov     r8d, r10d
0x180037b43  mov     r11, [r14+228h]
0x180037b4a  mov     edx, [r11+r8*8]
0x180037b4e  cmp     edx, r9d
0x180037b51  jb      loc_180037BFA
0x180037b57  mov     ecx, edx
0x180037b59  mov     eax, ecx
0x180037b5b  cmp     ecx, edx
0x180037b5d  cmovnb  eax, edx
0x180037b60  mov     [r11+r8*8], eax
0x180037b64  sub     ecx, eax
0x180037b66  mov     rax, [r14+228h]
0x180037b6d  mov     [rax+r8*8+4], ecx
0x180037b72  inc     r10d
0x180037b75  cmp     r10d, [r14+230h]
0x180037b7c  jnb     loc_180037A45
0x180037b82  jmp     short loc_180037B40
0x180037b84  or      r15, 0FFFFFFFFFFFFFFFFh
0x180037b88  jmp     loc_180037A45
0x180037b8d  test    rsi, rsi
0x180037b90  jz      loc_18003793C
0x180037b96  mov     [rbx], r11w
0x180037b9a  jmp     loc_18003793C
0x180037b9f  mov     ebx, r13d
0x180037ba2  mov     rcx, r14
  ... truncated ...
```
