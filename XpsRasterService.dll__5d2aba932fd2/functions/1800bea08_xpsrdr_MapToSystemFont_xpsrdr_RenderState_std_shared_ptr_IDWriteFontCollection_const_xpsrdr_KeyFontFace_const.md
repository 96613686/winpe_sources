# xpsrdr::MapToSystemFont(xpsrdr::RenderState &,std::shared_ptr<IDWriteFontCollection> const &,xpsrdr::KeyFontFace const &)

- ea: `0x1800bea08`
- end: `0x1800bf008`
- name: `?MapToSystemFont@xpsrdr@@YA?AV?$shared_ptr@UIDWriteFontFace@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIDWriteFontCollection@@@3@AEBUKeyFontFace@1@@Z`
- size: `1536`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800bdc84`

## callees

- `0x180003180`
- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800a9530`
- `0x1800aba64`
- `0x1800adcc0`
- `0x1800b20e8`
- `0x1800b8a30`
- `0x1800bd63c`
- `0x1800be440`
- `0x1800be794`
- `0x1800bea08`
- `0x1800c3010`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
_QWORD *__fastcall xpsrdr::MapToSystemFont(_QWORD *a1, __int64 a2, __int64 **a3, __int64 a4)
{
  __int64 *v8; // rcx
  __int64 v9; // rax
  int v10; // ebx
  int v11; // edx
  const char *v12; // r8
  int v13; // r9d
  __int64 v14; // rax
  int v15; // ebx
  int v16; // edx
  const char *v17; // r8
  int v18; // r9d
  int v19; // eax
  std::_Ref_count_base *v20; // rcx
  __int64 v21; // rax
  int v22; // ebx
  int v23; // edx
  const char *v24; // r8
  int v25; // r9d
  __int64 v26; // rax
  int v27; // ebx
  int v28; // edx
  const char *v29; // r8
  int v30; // r9d
  std::_Ref_count_base *v31; // rcx
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
  __int64 (__fastcall *v63)(__int64, _QWORD, __int64, std::_Ref_count_base **, int, int, _QWORD *); // rsi
  int v64; // edi
  int v65; // ebx
  unsigned int v66; // eax
  int v67; // ebx
  int v68; // edx
  const char *v69; // r8
  int v70; // r9d
  xpsrdr *v72; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v73[2]; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base **v74; // [rsp+58h] [rbp-A8h]
  int v75; // [rsp+60h] [rbp-A0h] BYREF
  int v76; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v77; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v78[2]; // [rsp+70h] [rbp-90h] BYREF
  std::_Ref_count_base *v79[2]; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base *v80[2]; // [rsp+90h] [rbp-70h] BYREF
  std::_Ref_count_base **v81; // [rsp+A0h] [rbp-60h]
  int v82; // [rsp+A8h] [rbp-58h]
  std::_Ref_count_base *v83[2]; // [rsp+B0h] [rbp-50h] BYREF
  std::_Ref_count_base *v84[2]; // [rsp+C0h] [rbp-40h] BYREF
  std::_Ref_count_base *v85[2]; // [rsp+D0h] [rbp-30h] BYREF
  std::_Ref_count_base *v86[2]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v87[4]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v88[32]; // [rsp+110h] [rbp+10h] BYREF

  v87[3] = a1;
  *a1 = 0;
  a1[1] = 0;
  v82 = 1;
  if ( (*(unsigned int (__fastcall **)(__int64 *))(**a3 + 24))(*a3) != 1 )
    return a1;
  *(_OWORD *)v79 = 0;
  LODWORD(v72) = 0;
  v8 = *a3;
  v9 = **a3;
  v73[0] = 0;
  v73[1] = (std::_Ref_count_base *)&v72;
  v74 = v79;
  v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, std::_Ref_count_base **))(v9 + 32))(v8, 0, v73);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v73);
  if ( (int)v72 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v72, v11, v12, v13);
  if ( v10 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v10, v11, v12, v13);
  if ( (*(unsigned int (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v79[0] + 32LL))(v79[0]) > 1 )
  {
    *(_OWORD *)v78 = 0;
    LODWORD(v72) = 0;
    v14 = *(_QWORD *)v79[0];
    v73[0] = 0;
    v73[1] = (std::_Ref_count_base *)&v72;
    v74 = v78;
    v15 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64, std::_Ref_count_base **))(v14 + 40))(
            v79[0],
            1,
            v73);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v73);
    if ( (int)v72 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v72, v16, v17, v18);
    if ( v15 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v15, v16, v17, v18);
    v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v78[0] + 80LL))(v78[0]);
    v20 = v78[1];
    if ( !v19 )
      goto LABEL_66;
    if ( v78[1] )
      std::_Ref_count_base::_Decref(v78[1]);
  }
  *(_OWORD *)v84 = 0;
  LODWORD(v72) = 0;
  v21 = *(_QWORD *)v79[0];
  v73[0] = 0;
  v73[1] = (std::_Ref_count_base *)&v72;
  v74 = v84;
  v22 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, std::_Ref_count_base **))(v21 + 40))(v79[0], 0, v73);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v73);
  if ( (int)v72 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v72, v23, v24, v25);
  if ( v22 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v22, v23, v24, v25);
  std::wstring::wstring(v88);
  v72 = 0;
  *(_OWORD *)v80 = 0;
  v75 = 0;
  v26 = *(_QWORD *)v79[0];
  v73[0] = 0;
  v73[1] = (std::_Ref_count_base *)&v75;
  v74 = v80;
  v27 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(v26 + 48))(v79[0], v73);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v73);
  if ( v75 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v75, v28, v29, v30);
  if ( v27 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v27, v28, v29, v30);
  if ( (*(unsigned int (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v80[0] + 24LL))(v80[0]) )
  {
    v32 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, const wchar_t *, xpsrdr **, char *))(*(_QWORD *)v80[0]
                                                                                                + 32LL))(
            v80[0],
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
    xpsrdr::GetName<std::shared_ptr<IDWriteLocalizedStrings>>(v80, v36, (__int64)v88);
    if ( v80[1] )
      std::_Ref_count_base::_Decref(v80[1]);
    v77 = 0;
    v76 = 0;
    *(_OWORD *)v83 = 0;
    HIDWORD(v72) = 0;
    v37 = *(__int64 **)(a2 + 32);
    v38 = *v37;
    v73[0] = 0;
    v73[1] = (std::_Ref_count_base *)((char *)&v72 + 4);
    v74 = v83;
    v39 = (*(__int64 (__fastcall **)(__int64 *, std::_Ref_count_base **, _QWORD))(v38 + 24))(v37, v73, 0);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v73);
    if ( SHIDWORD(v72) < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)HIDWORD(v72), v40, v41, v42);
    if ( v39 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v39, v40, v41, v42);
    v43 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v88);
    v46 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *, int *))(v44 + 40))(v45, v43, &v77, &v76);
    if ( v46 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v46, v47, v48, v49);
    if ( v76 )
    {
      *(_OWORD *)v86 = 0;
      HIDWORD(v72) = 0;
      v50 = *(_QWORD *)v83[0];
      v73[0] = 0;
      v73[1] = (std::_Ref_count_base *)((char *)&v72 + 4);
      v74 = v86;
      v51 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, std::_Ref_count_base **))(v50 + 32))(
              v83[0],
              v77,
              v73);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v73);
      if ( SHIDWORD(v72) < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)HIDWORD(v72), v52, v53, v54);
      if ( v51 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v51, v52, v53, v54);
      *(_OWORD *)v85 = 0;
      if ( (unsigned __int8)xpsrdr::GetMatchingSystemFont(v86, v84, v85) )
      {
        *(_OWORD *)v78 = 0;
        HIDWORD(v72) = 0;
        v55 = *(_QWORD *)v85[0];
        v73[0] = 0;
        v73[1] = (std::_Ref_count_base *)((char *)&v72 + 4);
        v74 = v78;
        v56 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(v55 + 104))(v85[0], v73);
        detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v73);
        if ( SHIDWORD(v72) < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)HIDWORD(v72), v57, v58, v59);
        if ( v56 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v56, v57, v58, v59);
        if ( *(_DWORD *)(a4 + 32) == 1 )
        {
          std::shared_ptr<ID2D1Brush>::operator=(a1, v78);
        }
        else
        {
          LODWORD(v72) = 1;
          *(_OWORD *)v73 = 0;
          v75 = 0;
          v60 = *(_QWORD *)v78[0];
          v80[0] = 0;
          v80[1] = (std::_Ref_count_base *)&v75;
          v81 = v73;
          v61 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, xpsrdr **, std::_Ref_count_base **))(v60 + 32))(
                  v78[0],
                  &v72,
                  v80);
          detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v80);
          if ( v61 >= 0 )
          {
            v80[0] = v73[0];
            HIDWORD(v72) = 0;
            v62 = *(_QWORD *)(a2 + 32);
            v63 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, std::_Ref_count_base **, int, int, _QWORD *))(*(_QWORD *)v62 + 72LL);
            v87[0] = 0;
            v87[1] = (char *)&v72 + 4;
            v87[2] = a1;
            v64 = xpsrdr::DWriteFromXpsSimulations(*(unsigned int *)(a4 + 32));
            v65 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v78[0] + 40LL))(v78[0]);
            v66 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v78[0] + 24LL))(v78[0]);
            v67 = v63(v62, v66, 1, v80, v65, v64, v87);
            detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v87);
            if ( SHIDWORD(v72) < 0 )
              xpsrdr::ThrowHRException((xpsrdr *)HIDWORD(v72), v68, v69, v70);
            if ( v67 < 0 )
              xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v67, v68, v69, v70);
          }
          if ( v73[1] )
            std::_Ref_count_base::_Decref(v73[1]);
        }
        if ( v78[1] )
          std::_Ref_count_base::_Decref(v78[1]);
      }
      if ( v85[1] )
        std::_Ref_count_base::_Decref(v85[1]);
      if ( v86[1] )
        std::_Ref_count_base::_Decref(v86[1]);
    }
    v31 = v83[1];
  }
  else
  {
    v31 = v80[1];
  }
  if ( v31 )
    std::_Ref_count_base::_Decref(v31);
  std::wstring::_Tidy_deallocate(v88);
  v20 = v84[1];
LABEL_66:
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  if ( v79[1] )
    std::_Ref_count_base::_Decref(v79[1]);
  return a1;
}

```

## disassembly

```asm
0x1800bea08  push    rbp
0x1800bea0a  push    rbx
0x1800bea0b  push    rsi
0x1800bea0c  push    rdi
0x1800bea0d  push    r12
0x1800bea0f  push    r13
0x1800bea11  push    r14
0x1800bea13  push    r15
0x1800bea15  lea     rbp, [rsp-48h]
0x1800bea1a  sub     rsp, 148h
0x1800bea21  mov     rax, cs:__security_cookie
0x1800bea28  xor     rax, rsp
0x1800bea2b  mov     [rbp+80h+var_50], rax
0x1800bea2f  mov     rdi, r9
0x1800bea32  mov     rbx, r8
0x1800bea35  mov     r14, rdx
0x1800bea38  mov     r15, rcx
0x1800bea3b  mov     [rbp+80h+var_78], rcx
0x1800bea3f  mov     r13d, 1
0x1800bea45  mov     [rbp+80h+var_D8], r13d
0x1800bea49  xor     r12d, r12d
0x1800bea4c  mov     [rcx], r12
0x1800bea4f  mov     [rcx+8], r12
0x1800bea53  mov     [rbp+80h+var_D8], r13d
0x1800bea57  mov     rcx, [r8]
0x1800bea5a  mov     rax, [rcx]
0x1800bea5d  mov     rax, [rax+18h]
0x1800bea61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bea66  cmp     eax, r13d
0x1800bea69  jnz     loc_1800BEFE5
0x1800bea6f  xorps   xmm0, xmm0
0x1800bea72  movdqu  xmmword ptr [rbp+80h+var_100], xmm0
0x1800bea77  mov     dword ptr [rsp+180h+var_140], r12d
0x1800bea7c  mov     rcx, [rbx]
0x1800bea7f  mov     rax, [rcx]
0x1800bea82  mov     [rsp+180h+var_138], r12
0x1800bea87  lea     rdx, [rsp+180h+var_140]
0x1800bea8c  mov     [rsp+180h+var_138+8], rdx
0x1800bea91  lea     rdx, [rbp+80h+var_100]
0x1800bea95  mov     [rsp+180h+var_128], rdx
0x1800bea9a  lea     r8, [rsp+180h+var_138]
0x1800bea9f  xor     edx, edx
0x1800beaa1  mov     rax, [rax+20h]
0x1800beaa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beaaa  mov     ebx, eax
0x1800beaac  lea     rcx, [rsp+180h+var_138]
0x1800beab1  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800beab6  mov     ecx, dword ptr [rsp+180h+var_140]; this
0x1800beaba  test    ecx, ecx
0x1800beabc  jns     short loc_1800BEAC4
0x1800beabe  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800beac4  test    ebx, ebx
0x1800beac6  jns     short loc_1800BEAD0
0x1800beac8  mov     ecx, ebx; this
0x1800beaca  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bead0  mov     rcx, [rbp+80h+var_100]
0x1800bead4  mov     rax, [rcx]
0x1800bead7  mov     rax, [rax+20h]
0x1800beadb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beae0  cmp     eax, r13d
0x1800beae3  jbe     loc_1800BEB77
0x1800beae9  xorps   xmm0, xmm0
0x1800beaec  movdqu  xmmword ptr [rsp+180h+var_110], xmm0
0x1800beaf2  mov     dword ptr [rsp+180h+var_140], r12d
0x1800beaf7  mov     rcx, [rbp+80h+var_100]
0x1800beafb  mov     rax, [rcx]
0x1800beafe  mov     [rsp+180h+var_138], r12
0x1800beb03  lea     rdx, [rsp+180h+var_140]
0x1800beb08  mov     [rsp+180h+var_138+8], rdx
0x1800beb0d  lea     rdx, [rsp+180h+var_110]
0x1800beb12  mov     [rsp+180h+var_128], rdx
0x1800beb17  lea     r8, [rsp+180h+var_138]
0x1800beb1c  mov     edx, r13d
0x1800beb1f  mov     rax, [rax+28h]
0x1800beb23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beb28  mov     ebx, eax
0x1800beb2a  lea     rcx, [rsp+180h+var_138]
0x1800beb2f  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800beb34  mov     ecx, dword ptr [rsp+180h+var_140]; this
0x1800beb38  test    ecx, ecx
0x1800beb3a  jns     short loc_1800BEB42
0x1800beb3c  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800beb42  test    ebx, ebx
0x1800beb44  jns     short loc_1800BEB4E
0x1800beb46  mov     ecx, ebx; this
0x1800beb48  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800beb4e  mov     rcx, [rsp+180h+var_110]
0x1800beb53  mov     rax, [rcx]
0x1800beb56  mov     rax, [rax+50h]
0x1800beb5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beb5f  nop
0x1800beb60  mov     rcx, [rsp+180h+var_110+8]; this
0x1800beb65  test    eax, eax
0x1800beb67  jz      loc_1800BEFCB
0x1800beb6d  test    rcx, rcx
0x1800beb70  jz      short loc_1800BEB77
0x1800beb72  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800beb77  xorps   xmm0, xmm0
0x1800beb7a  movdqu  xmmword ptr [rbp+80h+var_C0], xmm0
0x1800beb7f  mov     dword ptr [rsp+180h+var_140], r12d
0x1800beb84  mov     rcx, [rbp+80h+var_100]
0x1800beb88  mov     rax, [rcx]
0x1800beb8b  mov     [rsp+180h+var_138], r12
0x1800beb90  lea     rdx, [rsp+180h+var_140]
0x1800beb95  mov     [rsp+180h+var_138+8], rdx
0x1800beb9a  lea     rdx, [rbp+80h+var_C0]
0x1800beb9e  mov     [rsp+180h+var_128], rdx
0x1800beba3  lea     r8, [rsp+180h+var_138]
0x1800beba8  xor     edx, edx
0x1800bebaa  mov     rax, [rax+28h]
0x1800bebae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bebb3  mov     ebx, eax
0x1800bebb5  lea     rcx, [rsp+180h+var_138]
0x1800bebba  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800bebbf  mov     ecx, dword ptr [rsp+180h+var_140]; this
0x1800bebc3  test    ecx, ecx
0x1800bebc5  jns     short loc_1800BEBCD
0x1800bebc7  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bebcd  test    ebx, ebx
0x1800bebcf  jns     short loc_1800BEBD9
0x1800bebd1  mov     ecx, ebx; this
0x1800bebd3  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bebd9  lea     rcx, [rbp+80h+var_70]
0x1800bebdd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800bebe2  nop
0x1800bebe3  mov     dword ptr [rsp+180h+var_140], r12d
0x1800bebe8  mov     dword ptr [rsp+180h+var_140+4], r12d
0x1800bebed  xorps   xmm0, xmm0
0x1800bebf0  movdqu  xmmword ptr [rbp+80h+var_F0], xmm0
0x1800bebf5  mov     dword ptr [rsp+180h+var_120], r12d
0x1800bebfa  mov     rcx, [rbp+80h+var_100]
0x1800bebfe  mov     rax, [rcx]
0x1800bec01  mov     [rsp+180h+var_138], r12
0x1800bec06  lea     rdx, [rsp+180h+var_120]
0x1800bec0b  mov     [rsp+180h+var_138+8], rdx
0x1800bec10  lea     rdx, [rbp+80h+var_F0]
0x1800bec14  mov     [rsp+180h+var_128], rdx
0x1800bec19  lea     rdx, [rsp+180h+var_138]
0x1800bec1e  mov     rax, [rax+30h]
0x1800bec22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bec27  mov     ebx, eax
0x1800bec29  lea     rcx, [rsp+180h+var_138]
0x1800bec2e  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800bec33  mov     ecx, dword ptr [rsp+180h+var_120]; this
0x1800bec37  test    ecx, ecx
0x1800bec39  jns     short loc_1800BEC41
0x1800bec3b  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bec41  test    ebx, ebx
0x1800bec43  jns     short loc_1800BEC4D
0x1800bec45  mov     ecx, ebx; this
0x1800bec47  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bec4d  mov     rcx, [rbp+80h+var_F0]
0x1800bec51  mov     rax, [rcx]
0x1800bec54  mov     rax, [rax+18h]
0x1800bec58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bec5d  cmp     eax, r13d
0x1800bec60  jnb     short loc_1800BEC6B
0x1800bec62  mov     rcx, [rbp+80h+var_F0+8]
0x1800bec66  jmp     loc_1800BEFB2
0x1800bec6b  mov     rcx, [rbp+80h+var_F0]
0x1800bec6f  mov     rax, [rcx]
0x1800bec72  lea     r9, [rsp+180h+var_140+4]
0x1800bec77  lea     r8, [rsp+180h+var_140]
0x1800bec7c  lea     rdx, aEnUs; "en-us"
0x1800bec83  mov     rax, [rax+20h]
0x1800bec87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bec8c  test    eax, eax
0x1800bec8e  jns     short loc_1800BEC98
0x1800bec90  mov     ecx, eax; this
0x1800bec92  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bec98  cmp     dword ptr [rsp+180h+var_140+4], r12d
0x1800bec9d  jnz     short loc_1800BECA8
0x1800bec9f  mov     edx, r12d
0x1800beca2  mov     dword ptr [rsp+180h+var_140], edx
0x1800beca6  jmp     short loc_1800BECAC
0x1800beca8  mov     edx, dword ptr [rsp+180h+var_140]
0x1800becac  lea     r8, [rbp+80h+var_70]
0x1800becb0  lea     rcx, [rbp+80h+var_F0]
0x1800becb4  call    ??$GetName@V?$shared_ptr@UIDWriteLocalizedStrings@@@std@@@xpsrdr@@YAXAEBV?$shared_ptr@UIDWriteLocalizedStrings@@@std@@IAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; xpsrdr::GetName<std::shared_ptr<IDWriteLocalizedStrings>>(std::shared_ptr<IDWriteLocalizedStrings> const &,uint,std::wstring &)
0x1800becb9  nop
0x1800becba  mov     rcx, [rbp+80h+var_F0+8]; this
0x1800becbe  test    rcx, rcx
0x1800becc1  jz      short loc_1800BECC8
0x1800becc3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800becc8  mov     [rsp+180h+var_118], r12d
0x1800beccd  mov     dword ptr [rsp+180h+var_120+4], r12d
0x1800becd2  xorps   xmm0, xmm0
0x1800becd5  movdqu  xmmword ptr [rbp+80h+var_D0], xmm0
0x1800becda  mov     dword ptr [rsp+180h+var_140+4], r12d
0x1800becdf  mov     rcx, [r14+20h]
0x1800bece3  mov     rax, [rcx]
0x1800bece6  mov     [rsp+180h+var_138], r12
0x1800beceb  lea     rdx, [rsp+180h+var_140+4]
0x1800becf0  mov     [rsp+180h+var_138+8], rdx
0x1800becf5  lea     rdx, [rbp+80h+var_D0]
0x1800becf9  mov     [rsp+180h+var_128], rdx
0x1800becfe  xor     r8d, r8d
0x1800bed01  lea     rdx, [rsp+180h+var_138]
0x1800bed06  mov     rax, [rax+18h]
0x1800bed0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bed0f  mov     ebx, eax
0x1800bed11  lea     rcx, [rsp+180h+var_138]
0x1800bed16  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800bed1b  mov     ecx, dword ptr [rsp+180h+var_140+4]; this
0x1800bed1f  test    ecx, ecx
0x1800bed21  jns     short loc_1800BED29
0x1800bed23  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bed29  test    ebx, ebx
0x1800bed2b  jns     short loc_1800BED35
0x1800bed2d  mov     ecx, ebx; this
0x1800bed2f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bed35  mov     r10, [rbp+80h+var_D0]
0x1800bed39  mov     r8, [r10]
0x1800bed3c  lea     rcx, [rbp+80h+var_70]
0x1800bed40  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800bed45  mov     rdx, rax
0x1800bed48  mov     rax, [r8+28h]
0x1800bed4c  lea     r9, [rsp+180h+var_120+4]
0x1800bed51  lea     r8, [rsp+180h+var_118]
0x1800bed56  mov     rcx, r10
0x1800bed59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bed5e  test    eax, eax
0x1800bed60  jns     short loc_1800BED6A
0x1800bed62  mov     ecx, eax; this
0x1800bed64  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bed6a  cmp     dword ptr [rsp+180h+var_120+4], r12d
0x1800bed6f  jz      loc_1800BEFAE
0x1800bed75  xorps   xmm0, xmm0
0x1800bed78  movdqu  xmmword ptr [rbp+80h+var_A0], xmm0
0x1800bed7d  mov     dword ptr [rsp+180h+var_140+4], r12d
0x1800bed82  mov     rcx, [rbp+80h+var_D0]
0x1800bed86  mov     rax, [rcx]
0x1800bed89  mov     [rsp+180h+var_138], r12
0x1800bed8e  lea     rdx, [rsp+180h+var_140+4]
0x1800bed93  mov     [rsp+180h+var_138+8], rdx
0x1800bed98  lea     rdx, [rbp+80h+var_A0]
0x1800bed9c  mov     [rsp+180h+var_128], rdx
0x1800beda1  lea     r8, [rsp+180h+var_138]
0x1800beda6  mov     edx, [rsp+180h+var_118]
0x1800bedaa  mov     rax, [rax+20h]
0x1800bedae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bedb3  mov     ebx, eax
0x1800bedb5  lea     rcx, [rsp+180h+var_138]
0x1800bedba  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800bedbf  mov     ecx, dword ptr [rsp+180h+var_140+4]; this
0x1800bedc3  test    ecx, ecx
0x1800bedc5  jns     short loc_1800BEDCD
0x1800bedc7  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bedcd  test    ebx, ebx
0x1800bedcf  jns     short loc_1800BEDD9
0x1800bedd1  mov     ecx, ebx; this
0x1800bedd3  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bedd9  xorps   xmm0, xmm0
0x1800beddc  movdqu  xmmword ptr [rbp+80h+var_B0], xmm0
0x1800bede1  lea     r8, [rbp+80h+var_B0]
0x1800bede5  lea     rdx, [rbp+80h+var_C0]
0x1800bede9  lea     rcx, [rbp+80h+var_A0]
0x1800beded  call    ?GetMatchingSystemFont@xpsrdr@@YA_NAEBV?$shared_ptr@UIDWriteFontFamily@@@std@@AEBV?$shared_ptr@UIDWriteFont@@@3@AEAV43@@Z; xpsrdr::GetMatchingSystemFont(std::shared_ptr<IDWriteFontFamily> const &,std::shared_ptr<IDWriteFont> const &,std::shared_ptr<IDWriteFont> &)
0x1800bedf2  test    al, al
0x1800bedf4  jz      loc_1800BEF90
0x1800bedfa  xorps   xmm0, xmm0
0x1800bedfd  movdqu  xmmword ptr [rsp+180h+var_110], xmm0
0x1800bee03  mov     dword ptr [rsp+180h+var_140+4], r12d
0x1800bee08  mov     rcx, [rbp+80h+var_B0]
0x1800bee0c  mov     rax, [rcx]
0x1800bee0f  mov     [rsp+180h+var_138], r12
0x1800bee14  lea     rdx, [rsp+180h+var_140+4]
0x1800bee19  mov     [rsp+180h+var_138+8], rdx
0x1800bee1e  lea     rdx, [rsp+180h+var_110]
0x1800bee23  mov     [rsp+180h+var_128], rdx
0x1800bee28  lea     rdx, [rsp+180h+var_138]
0x1800bee2d  mov     rax, [rax+68h]
0x1800bee31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bee36  mov     ebx, eax
0x1800bee38  lea     rcx, [rsp+180h+var_138]
0x1800bee3d  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800bee42  mov     ecx, dword ptr [rsp+180h+var_140+4]; this
0x1800bee46  test    ecx, ecx
0x1800bee48  jns     short loc_1800BEE50
0x1800bee4a  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bee50  test    ebx, ebx
0x1800bee52  jns     short loc_1800BEE5C
0x1800bee54  mov     ecx, ebx; this
0x1800bee56  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bee5c  cmp     [rdi+20h], r13d
0x1800bee60  jnz     short loc_1800BEE74
0x1800bee62  lea     rdx, [rsp+180h+var_110]
0x1800bee67  mov     rcx, r15
0x1800bee6a  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x1800bee6f  jmp     loc_1800BEF80
0x1800bee74  mov     dword ptr [rsp+180h+var_140], r13d
0x1800bee79  xorps   xmm0, xmm0
0x1800bee7c  movdqu  xmmword ptr [rsp+180h+var_138], xmm0
0x1800bee82  mov     dword ptr [rsp+180h+var_120], r12d
0x1800bee87  mov     rcx, [rsp+180h+var_110]
0x1800bee8c  mov     rax, [rcx]
0x1800bee8f  mov     [rbp+80h+var_F0], r12
0x1800bee93  lea     rdx, [rsp+180h+var_120]
0x1800bee98  mov     [rbp+80h+var_F0+8], rdx
0x1800bee9c  lea     rdx, [rsp+180h+var_138]
  ... truncated ...
```
