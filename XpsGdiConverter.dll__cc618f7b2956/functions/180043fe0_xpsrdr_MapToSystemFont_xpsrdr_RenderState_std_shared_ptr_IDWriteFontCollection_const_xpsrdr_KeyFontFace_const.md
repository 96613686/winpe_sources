# xpsrdr::MapToSystemFont(xpsrdr::RenderState &,std::shared_ptr<IDWriteFontCollection> const &,xpsrdr::KeyFontFace const &)

- ea: `0x180043fe0`
- end: `0x1800445c9`
- name: `?MapToSystemFont@xpsrdr@@YA?AV?$shared_ptr@UIDWriteFontFace@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIDWriteFontCollection@@@3@AEBUKeyFontFace@1@@Z`
- size: `1513`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800432dc`

## callees

- `0x180008830`
- `0x18000e15c`
- `0x18000e4c4`
- `0x18000e5ec`
- `0x180011b0c`
- `0x180012704`
- `0x1800184e8`
- `0x18001cf2c`
- `0x180037278`
- `0x180042ec8`
- `0x180043a48`
- `0x180043d74`
- `0x180043fe0`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall xpsrdr::MapToSystemFont(__int64 a1, __int64 a2, __int64 **a3, __int64 a4)
{
  _QWORD *v8; // r8
  __int64 *v9; // rcx
  __int64 v10; // rax
  int v11; // ebx
  int v12; // edx
  const char *v13; // r8
  int v14; // r9d
  __int64 v15; // rax
  int v16; // ebx
  int v17; // edx
  const char *v18; // r8
  int v19; // r9d
  int v20; // eax
  _BYTE *v21; // rcx
  __int64 v22; // rax
  int v23; // ebx
  int v24; // edx
  const char *v25; // r8
  int v26; // r9d
  __int64 v27; // rax
  int v28; // ebx
  int v29; // edx
  const char *v30; // r8
  int v31; // r9d
  int v32; // eax
  int v33; // edx
  const char *v34; // r8
  int v35; // r9d
  __int64 v36; // rdx
  __int64 *v37; // rcx
  __int64 v38; // rax
  int v39; // ebx
  int v40; // edx
  const char *v41; // r8
  int v42; // r9d
  __int64 v43; // rax
  __int64 v44; // r8
  __int64 v45; // r10
  int v46; // eax
  int v47; // edx
  const char *v48; // r8
  int v49; // r9d
  __int64 v50; // rax
  int v51; // ebx
  int v52; // edx
  const char *v53; // r8
  int v54; // r9d
  __int64 v55; // rax
  int v56; // ebx
  int v57; // edx
  const char *v58; // r8
  int v59; // r9d
  __int64 v60; // rax
  int v61; // ebx
  __int64 v62; // r14
  __int64 (__fastcall *v63)(__int64, _QWORD, __int64, _QWORD *, int, int, _QWORD *); // rsi
  int v64; // edi
  int v65; // ebx
  unsigned int v66; // eax
  int v67; // ebx
  int v68; // edx
  const char *v69; // r8
  int v70; // r9d
  xpsrdr *v72; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v73; // [rsp+48h] [rbp-B8h] BYREF
  xpsrdr **v74; // [rsp+50h] [rbp-B0h]
  _QWORD *v75; // [rsp+58h] [rbp-A8h]
  int v76; // [rsp+60h] [rbp-A0h] BYREF
  int v77; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v78; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v79[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v80[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v81[3]; // [rsp+90h] [rbp-70h] BYREF
  int v82; // [rsp+A8h] [rbp-58h]
  _QWORD v83[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v84[16]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v85[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v86[16]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v87[4]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v88[32]; // [rsp+110h] [rbp+10h] BYREF

  v87[3] = a1;
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(a1);
  v82 = 1;
  if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 24LL))(*v8) == 1 )
  {
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v80);
    LODWORD(v72) = 0;
    v9 = *a3;
    v10 = **a3;
    v73 = 0;
    v74 = &v72;
    v75 = v80;
    v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v10 + 32))(v9, 0, &v73);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v73);
    if ( (int)v72 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v72, v12, v13, v14);
    if ( v11 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v11, v12, v13, v14);
    if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v80[0] + 32LL))(v80[0]) > 1 )
    {
      std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v79);
      LODWORD(v72) = 0;
      v15 = *(_QWORD *)v80[0];
      v73 = 0;
      v74 = &v72;
      v75 = v79;
      v16 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(v15 + 40))(v80[0], 1, &v73);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v73);
      if ( (int)v72 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v72, v17, v18, v19);
      if ( v16 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v16, v17, v18, v19);
      v20 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v79[0] + 80LL))(v79[0]);
      v21 = v79;
      if ( !v20 )
        goto LABEL_56;
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(v79);
    }
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v84);
    LODWORD(v72) = 0;
    v22 = *(_QWORD *)v80[0];
    v73 = 0;
    v74 = &v72;
    v75 = v84;
    v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(v22 + 40))(v80[0], 0, &v73);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v73);
    if ( (int)v72 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v72, v24, v25, v26);
    if ( v23 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v23, v24, v25, v26);
    std::wstring::wstring(v88);
    v72 = 0;
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v81);
    v76 = 0;
    v27 = *(_QWORD *)v80[0];
    v73 = 0;
    v74 = (xpsrdr **)&v76;
    v75 = v81;
    v28 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(v27 + 48))(v80[0], &v73);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v73);
    if ( v76 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v76, v29, v30, v31);
    if ( v28 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v28, v29, v30, v31);
    if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v81[0] + 24LL))(v81[0]) )
    {
      v32 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, xpsrdr **, char *))(*(_QWORD *)v81[0] + 32LL))(
              v81[0],
              L"en-us",
              &v72,
              (char *)&v72 + 4);
      if ( v32 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v32, v33, v34, v35);
      if ( HIDWORD(v72) )
      {
        v36 = (unsigned int)v72;
      }
      else
      {
        v36 = 0;
        LODWORD(v72) = 0;
      }
      xpsrdr::GetName<std::shared_ptr<IDWriteLocalizedStrings>>(v81, v36, v88);
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(v81);
      v78 = 0;
      v77 = 0;
      std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v83);
      HIDWORD(v72) = 0;
      v37 = *(__int64 **)(a2 + 32);
      v38 = *v37;
      v73 = 0;
      v74 = (xpsrdr **)((char *)&v72 + 4);
      v75 = v83;
      v39 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, _QWORD))(v38 + 24))(v37, &v73, 0);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v73);
      if ( SHIDWORD(v72) < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)HIDWORD(v72), v40, v41, v42);
      if ( v39 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v39, v40, v41, v42);
      v43 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v88);
      v46 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *, int *))(v44 + 40))(v45, v43, &v78, &v77);
      if ( v46 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v46, v47, v48, v49);
      if ( v77 )
      {
        std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v86);
        HIDWORD(v72) = 0;
        v50 = *(_QWORD *)v83[0];
        v73 = 0;
        v74 = (xpsrdr **)((char *)&v72 + 4);
        v75 = v86;
        v51 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(v50 + 32))(v83[0], v78, &v73);
        detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v73);
        if ( SHIDWORD(v72) < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)HIDWORD(v72), v52, v53, v54);
        if ( v51 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v51, v52, v53, v54);
        std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v85);
        if ( (unsigned __int8)xpsrdr::GetMatchingSystemFont(v86, v84, v85) )
        {
          std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v79);
          HIDWORD(v72) = 0;
          v55 = *(_QWORD *)v85[0];
          v73 = 0;
          v74 = (xpsrdr **)((char *)&v72 + 4);
          v75 = v79;
          v56 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(v55 + 104))(v85[0], &v73);
          detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v73);
          if ( SHIDWORD(v72) < 0 )
            xpsrdr::ThrowHRException((xpsrdr *)HIDWORD(v72), v57, v58, v59);
          if ( v56 < 0 )
            xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v56, v57, v58, v59);
          if ( *(_DWORD *)(a4 + 32) == 1 )
          {
            std::shared_ptr<ID2D1Brush>::operator=(a1, v79);
          }
          else
          {
            LODWORD(v72) = 1;
            std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v73);
            v76 = 0;
            v60 = *(_QWORD *)v79[0];
            v81[0] = 0;
            v81[1] = &v76;
            v81[2] = &v73;
            v61 = (*(__int64 (__fastcall **)(_QWORD, xpsrdr **, _QWORD *))(v60 + 32))(v79[0], &v72, v81);
            detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v81);
            if ( v61 >= 0 )
            {
              v81[0] = v73;
              HIDWORD(v72) = 0;
              v62 = *(_QWORD *)(a2 + 32);
              v63 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD *, int, int, _QWORD *))(*(_QWORD *)v62 + 72LL);
              v87[0] = 0;
              v87[1] = (char *)&v72 + 4;
              v87[2] = a1;
              v64 = xpsrdr::DWriteFromXpsSimulations(*(unsigned int *)(a4 + 32));
              v65 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v79[0] + 40LL))(v79[0]);
              v66 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v79[0] + 24LL))(v79[0]);
              v67 = v63(v62, v66, 1, v81, v65, v64, v87);
              detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v87);
              if ( SHIDWORD(v72) < 0 )
                xpsrdr::ThrowHRException((xpsrdr *)HIDWORD(v72), v68, v69, v70);
              if ( v67 < 0 )
                xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v67, v68, v69, v70);
            }
            std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v73);
          }
          std::_Ptr_base<ID2D1RenderTarget>::_Decref(v79);
        }
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(v85);
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(v86);
      }
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(v83);
    }
    else
    {
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(v81);
    }
    std::wstring::~wstring(v88);
    v21 = v84;
LABEL_56:
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v21);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v80);
  }
  return a1;
}

```

## disassembly

```asm
0x180043fe0  push    rbp
0x180043fe2  push    rbx
0x180043fe3  push    rsi
0x180043fe4  push    rdi
0x180043fe5  push    r12
0x180043fe7  push    r13
0x180043fe9  push    r14
0x180043feb  push    r15
0x180043fed  lea     rbp, [rsp-48h]
0x180043ff2  sub     rsp, 148h
0x180043ff9  mov     rax, cs:__security_cookie
0x180044000  xor     rax, rsp
0x180044003  mov     [rbp+80h+var_50], rax
0x180044007  mov     rdi, r9
0x18004400a  mov     rbx, r8
0x18004400d  mov     r14, rdx
0x180044010  mov     r15, rcx
0x180044013  mov     [rbp+80h+var_78], rcx
0x180044017  mov     r13d, 1
0x18004401d  mov     [rbp+80h+var_D8], r13d
0x180044021  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180044026  nop
0x180044027  mov     [rbp+80h+var_D8], r13d
0x18004402b  mov     rcx, [r8]
0x18004402e  mov     rdx, [rcx]
0x180044031  mov     rax, [rdx+18h]
0x180044035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004403a  cmp     eax, r13d
0x18004403d  jnz     loc_1800445A6
0x180044043  lea     rcx, [rbp+80h+var_100]
0x180044047  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18004404c  nop
0x18004404d  xor     r12d, r12d
0x180044050  mov     dword ptr [rsp+180h+var_140], r12d
0x180044055  mov     rcx, [rbx]
0x180044058  mov     rax, [rcx]
0x18004405b  mov     [rsp+180h+var_138], r12
0x180044060  lea     rdx, [rsp+180h+var_140]
0x180044065  mov     [rsp+180h+var_130], rdx
0x18004406a  lea     rdx, [rbp+80h+var_100]
0x18004406e  mov     [rsp+180h+var_128], rdx
0x180044073  lea     r8, [rsp+180h+var_138]
0x180044078  xor     edx, edx
0x18004407a  mov     rax, [rax+20h]
0x18004407e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044083  mov     ebx, eax
0x180044085  lea     rcx, [rsp+180h+var_138]
0x18004408a  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18004408f  mov     ecx, dword ptr [rsp+180h+var_140]; this
0x180044093  test    ecx, ecx
0x180044095  jns     short loc_18004409D
0x180044097  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18004409d  test    ebx, ebx
0x18004409f  jns     short loc_1800440A9
0x1800440a1  mov     ecx, ebx; this
0x1800440a3  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800440a9  mov     rcx, [rbp+80h+var_100]
0x1800440ad  mov     rax, [rcx]
0x1800440b0  mov     rax, [rax+20h]
0x1800440b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800440b9  cmp     eax, r13d
0x1800440bc  jbe     loc_18004414D
0x1800440c2  lea     rcx, [rsp+180h+var_110]
0x1800440c7  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800440cc  nop
0x1800440cd  mov     dword ptr [rsp+180h+var_140], r12d
0x1800440d2  mov     rcx, [rbp+80h+var_100]
0x1800440d6  mov     rax, [rcx]
0x1800440d9  mov     [rsp+180h+var_138], r12
0x1800440de  lea     rdx, [rsp+180h+var_140]
0x1800440e3  mov     [rsp+180h+var_130], rdx
0x1800440e8  lea     rdx, [rsp+180h+var_110]
0x1800440ed  mov     [rsp+180h+var_128], rdx
0x1800440f2  lea     r8, [rsp+180h+var_138]
0x1800440f7  mov     edx, r13d
0x1800440fa  mov     rax, [rax+28h]
0x1800440fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044103  mov     ebx, eax
0x180044105  lea     rcx, [rsp+180h+var_138]
0x18004410a  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18004410f  mov     ecx, dword ptr [rsp+180h+var_140]; this
0x180044113  test    ecx, ecx
0x180044115  jns     short loc_18004411D
0x180044117  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18004411d  test    ebx, ebx
0x18004411f  jns     short loc_180044129
0x180044121  mov     ecx, ebx; this
0x180044123  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180044129  mov     rcx, [rsp+180h+var_110]
0x18004412e  mov     rax, [rcx]
0x180044131  mov     rax, [rax+50h]
0x180044135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004413a  nop
0x18004413b  lea     rcx, [rsp+180h+var_110]
0x180044140  test    eax, eax
0x180044142  jz      loc_180044596
0x180044148  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18004414d  lea     rcx, [rbp+80h+var_C0]
0x180044151  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180044156  nop
0x180044157  mov     dword ptr [rsp+180h+var_140], r12d
0x18004415c  mov     rcx, [rbp+80h+var_100]
0x180044160  mov     rax, [rcx]
0x180044163  mov     [rsp+180h+var_138], r12
0x180044168  lea     rdx, [rsp+180h+var_140]
0x18004416d  mov     [rsp+180h+var_130], rdx
0x180044172  lea     rdx, [rbp+80h+var_C0]
0x180044176  mov     [rsp+180h+var_128], rdx
0x18004417b  lea     r8, [rsp+180h+var_138]
0x180044180  xor     edx, edx
0x180044182  mov     rax, [rax+28h]
0x180044186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004418b  mov     ebx, eax
0x18004418d  lea     rcx, [rsp+180h+var_138]
0x180044192  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180044197  mov     ecx, dword ptr [rsp+180h+var_140]; this
0x18004419b  test    ecx, ecx
0x18004419d  jns     short loc_1800441A5
0x18004419f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800441a5  test    ebx, ebx
0x1800441a7  jns     short loc_1800441B1
0x1800441a9  mov     ecx, ebx; this
0x1800441ab  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800441b1  lea     rcx, [rbp+80h+var_70]
0x1800441b5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800441ba  nop
0x1800441bb  mov     dword ptr [rsp+180h+var_140], r12d
0x1800441c0  mov     dword ptr [rsp+180h+var_140+4], r12d
0x1800441c5  lea     rcx, [rbp+80h+var_F0]
0x1800441c9  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800441ce  nop
0x1800441cf  mov     dword ptr [rsp+180h+var_120], r12d
0x1800441d4  mov     rcx, [rbp+80h+var_100]
0x1800441d8  mov     rax, [rcx]
0x1800441db  mov     [rsp+180h+var_138], r12
0x1800441e0  lea     rdx, [rsp+180h+var_120]
0x1800441e5  mov     [rsp+180h+var_130], rdx
0x1800441ea  lea     rdx, [rbp+80h+var_F0]
0x1800441ee  mov     [rsp+180h+var_128], rdx
0x1800441f3  lea     rdx, [rsp+180h+var_138]
0x1800441f8  mov     rax, [rax+30h]
0x1800441fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044201  mov     ebx, eax
0x180044203  lea     rcx, [rsp+180h+var_138]
0x180044208  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18004420d  mov     ecx, dword ptr [rsp+180h+var_120]; this
0x180044211  test    ecx, ecx
0x180044213  jns     short loc_18004421B
0x180044215  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18004421b  test    ebx, ebx
0x18004421d  jns     short loc_180044227
0x18004421f  mov     ecx, ebx; this
0x180044221  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180044227  mov     rcx, [rbp+80h+var_F0]
0x18004422b  mov     rax, [rcx]
0x18004422e  mov     rax, [rax+18h]
0x180044232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044237  cmp     eax, r13d
0x18004423a  jnb     short loc_18004424A
0x18004423c  lea     rcx, [rbp+80h+var_F0]
0x180044240  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180044245  jmp     loc_180044588
0x18004424a  mov     rcx, [rbp+80h+var_F0]
0x18004424e  mov     rax, [rcx]
0x180044251  lea     r9, [rsp+180h+var_140+4]
0x180044256  lea     r8, [rsp+180h+var_140]
0x18004425b  lea     rdx, aEnUs; "en-us"
0x180044262  mov     rax, [rax+20h]
0x180044266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004426b  test    eax, eax
0x18004426d  jns     short loc_180044277
0x18004426f  mov     ecx, eax; this
0x180044271  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180044277  cmp     dword ptr [rsp+180h+var_140+4], r12d
0x18004427c  jnz     short loc_180044287
0x18004427e  mov     edx, r12d
0x180044281  mov     dword ptr [rsp+180h+var_140], edx
0x180044285  jmp     short loc_18004428B
0x180044287  mov     edx, dword ptr [rsp+180h+var_140]
0x18004428b  lea     r8, [rbp+80h+var_70]
0x18004428f  lea     rcx, [rbp+80h+var_F0]
0x180044293  call    ??$GetName@V?$shared_ptr@UIDWriteLocalizedStrings@@@std@@@xpsrdr@@YAXAEBV?$shared_ptr@UIDWriteLocalizedStrings@@@std@@IAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; xpsrdr::GetName<std::shared_ptr<IDWriteLocalizedStrings>>(std::shared_ptr<IDWriteLocalizedStrings> const &,uint,std::wstring &)
0x180044298  nop
0x180044299  lea     rcx, [rbp+80h+var_F0]
0x18004429d  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800442a2  mov     [rsp+180h+var_118], r12d
0x1800442a7  mov     dword ptr [rsp+180h+var_120+4], r12d
0x1800442ac  lea     rcx, [rbp+80h+var_D0]
0x1800442b0  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800442b5  nop
0x1800442b6  mov     dword ptr [rsp+180h+var_140+4], r12d
0x1800442bb  mov     rcx, [r14+20h]
0x1800442bf  mov     rax, [rcx]
0x1800442c2  mov     [rsp+180h+var_138], r12
0x1800442c7  lea     rdx, [rsp+180h+var_140+4]
0x1800442cc  mov     [rsp+180h+var_130], rdx
0x1800442d1  lea     rdx, [rbp+80h+var_D0]
0x1800442d5  mov     [rsp+180h+var_128], rdx
0x1800442da  xor     r8d, r8d
0x1800442dd  lea     rdx, [rsp+180h+var_138]
0x1800442e2  mov     rax, [rax+18h]
0x1800442e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800442eb  mov     ebx, eax
0x1800442ed  lea     rcx, [rsp+180h+var_138]
0x1800442f2  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800442f7  mov     ecx, dword ptr [rsp+180h+var_140+4]; this
0x1800442fb  test    ecx, ecx
0x1800442fd  jns     short loc_180044305
0x1800442ff  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180044305  test    ebx, ebx
0x180044307  jns     short loc_180044311
0x180044309  mov     ecx, ebx; this
0x18004430b  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180044311  mov     r10, [rbp+80h+var_D0]
0x180044315  mov     r8, [r10]
0x180044318  lea     rcx, [rbp+80h+var_70]
0x18004431c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180044321  mov     rdx, rax
0x180044324  mov     rax, [r8+28h]
0x180044328  lea     r9, [rsp+180h+var_120+4]
0x18004432d  lea     r8, [rsp+180h+var_118]
0x180044332  mov     rcx, r10
0x180044335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004433a  test    eax, eax
0x18004433c  jns     short loc_180044346
0x18004433e  mov     ecx, eax; this
0x180044340  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180044346  cmp     dword ptr [rsp+180h+var_120+4], r12d
0x18004434b  jz      loc_18004457E
0x180044351  lea     rcx, [rbp+80h+var_A0]
0x180044355  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18004435a  nop
0x18004435b  mov     dword ptr [rsp+180h+var_140+4], r12d
0x180044360  mov     rcx, [rbp+80h+var_D0]
0x180044364  mov     rax, [rcx]
0x180044367  mov     [rsp+180h+var_138], r12
0x18004436c  lea     rdx, [rsp+180h+var_140+4]
0x180044371  mov     [rsp+180h+var_130], rdx
0x180044376  lea     rdx, [rbp+80h+var_A0]
0x18004437a  mov     [rsp+180h+var_128], rdx
0x18004437f  lea     r8, [rsp+180h+var_138]
0x180044384  mov     edx, [rsp+180h+var_118]
0x180044388  mov     rax, [rax+20h]
0x18004438c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044391  mov     ebx, eax
0x180044393  lea     rcx, [rsp+180h+var_138]
0x180044398  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18004439d  mov     ecx, dword ptr [rsp+180h+var_140+4]; this
0x1800443a1  test    ecx, ecx
0x1800443a3  jns     short loc_1800443AB
0x1800443a5  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800443ab  test    ebx, ebx
0x1800443ad  jns     short loc_1800443B7
0x1800443af  mov     ecx, ebx; this
0x1800443b1  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800443b7  lea     rcx, [rbp+80h+var_B0]
0x1800443bb  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800443c0  nop
0x1800443c1  lea     r8, [rbp+80h+var_B0]
0x1800443c5  lea     rdx, [rbp+80h+var_C0]
0x1800443c9  lea     rcx, [rbp+80h+var_A0]
0x1800443cd  call    ?GetMatchingSystemFont@xpsrdr@@YA_NAEBV?$shared_ptr@UIDWriteFontFamily@@@std@@AEBV?$shared_ptr@UIDWriteFont@@@3@AEAV43@@Z; xpsrdr::GetMatchingSystemFont(std::shared_ptr<IDWriteFontFamily> const &,std::shared_ptr<IDWriteFont> const &,std::shared_ptr<IDWriteFont> &)
0x1800443d2  test    al, al
0x1800443d4  jz      loc_18004456A
0x1800443da  lea     rcx, [rsp+180h+var_110]
0x1800443df  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800443e4  nop
0x1800443e5  mov     dword ptr [rsp+180h+var_140+4], r12d
0x1800443ea  mov     rcx, [rbp+80h+var_B0]
0x1800443ee  mov     rax, [rcx]
0x1800443f1  mov     [rsp+180h+var_138], r12
0x1800443f6  lea     rdx, [rsp+180h+var_140+4]
0x1800443fb  mov     [rsp+180h+var_130], rdx
0x180044400  lea     rdx, [rsp+180h+var_110]
0x180044405  mov     [rsp+180h+var_128], rdx
0x18004440a  lea     rdx, [rsp+180h+var_138]
0x18004440f  mov     rax, [rax+68h]
0x180044413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044418  mov     ebx, eax
0x18004441a  lea     rcx, [rsp+180h+var_138]
0x18004441f  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180044424  mov     ecx, dword ptr [rsp+180h+var_140+4]; this
0x180044428  test    ecx, ecx
0x18004442a  jns     short loc_180044432
0x18004442c  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180044432  test    ebx, ebx
0x180044434  jns     short loc_18004443E
0x180044436  mov     ecx, ebx; this
0x180044438  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18004443e  cmp     [rdi+20h], r13d
0x180044442  jnz     short loc_180044456
0x180044444  lea     rdx, [rsp+180h+var_110]
0x180044449  mov     rcx, r15
0x18004444c  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x180044451  jmp     loc_18004455F
0x180044456  mov     dword ptr [rsp+180h+var_140], r13d
0x18004445b  lea     rcx, [rsp+180h+var_138]
0x180044460  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180044465  nop
0x180044466  mov     dword ptr [rsp+180h+var_120], r12d
  ... truncated ...
```
