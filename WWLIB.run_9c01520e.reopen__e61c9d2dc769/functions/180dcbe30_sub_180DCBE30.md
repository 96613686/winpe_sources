# sub_180DCBE30

- ea: `0x180dcbe30`
- end: `0x180dcc997`
- name: `sub_180DCBE30`
- size: `2919`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `37`
- tags: ``

## callees

- `0x180013e58`
- `0x180013e98`
- `0x180018c58`
- `0x180056784`
- `0x180076a80`
- `0x18007eb7c`
- `0x18007f3d0`
- `0x180086f40`
- `0x1800a71b0`
- `0x1800c77c0`
- `0x1800ef8f0`
- `0x18024b71c`
- `0x18025c554`
- `0x1802608b8`
- `0x180296500`
- `0x1802bd1fc`
- `0x1802bd274`
- `0x1802da350`
- `0x18048c758`
- `0x180874424`
- `0x180908e70`
- `0x180908e78`
- `0x18090a640`
- `0x18090a660`
- `0x180947a60`
- `0x1809cd498`
- `0x1809cd57c`
- `0x180d1e938`
- `0x180dcb488`
- `0x180dcb8cc`
- `0x180dcbb84`
- `0x180dcbc54`
- `0x180dcbe30`
- `0x180dcc998`
- `0x180dccffc`
- `0x180dcd244`
- `0x1813cea08`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x180dcc561`
- `KERNEL32!TlsGetValue` at `0x180dcc585`
- `KERNEL32!TlsGetValue` at `0x180dcc561`
- `KERNEL32!TlsGetValue` at `0x180dcc585`
- `VCRUNTIME140!wcschr` at `0x180dcc479`
- `VCRUNTIME140!wcschr` at `0x180dcc490`
- `VCRUNTIME140!wcschr` at `0x180dcc479`
- `VCRUNTIME140!wcschr` at `0x180dcc490`
- `Mso30Win32Client!Mso30Win32Client_38134` at `0x180dcc462`
- `Mso30Win32Client!Mso30Win32Client_38134` at `0x180dcc462`
- `Mso20Win32Client!Mso20Win32Client_7228` at `0x180dcc688`
- `Mso20Win32Client!Mso20Win32Client_7228` at `0x180dcc688`
- `Mso20Win32Client!Mso20Win32Client_21217` at `0x180dcc516`
- `Mso20Win32Client!Mso20Win32Client_21217` at `0x180dcc516`
- `Mso20Win32Client!Mso20Win32Client_55533` at `0x180dcc83a`
- `Mso20Win32Client!Mso20Win32Client_55533` at `0x180dcc83a`
- `USER32!DefWindowProcW` at `0x180dcbe90`
- `USER32!DefWindowProcW` at `0x180dcbe90`
- `USER32!GetWindowLongPtrW` at `0x180dcbf97`
- `USER32!GetWindowLongPtrW` at `0x180dcbf97`
- `USER32!GetClientRect` at `0x180dcc158`
- `USER32!GetClientRect` at `0x180dcc34f`
- `USER32!GetClientRect` at `0x180dcc158`
- `USER32!GetClientRect` at `0x180dcc34f`
- `USER32!GetWindowRect` at `0x180dcc11c`
- `USER32!GetWindowRect` at `0x180dcc312`
- `USER32!GetWindowRect` at `0x180dcc11c`
- `USER32!GetWindowRect` at `0x180dcc312`
- `USER32!GetWindowLongW` at `0x180dcbeea`
- `USER32!GetWindowLongW` at `0x180dcbf66`
- `USER32!GetWindowLongW` at `0x180dcbf77`
- `USER32!GetWindowLongW` at `0x180dcbfb5`
- `USER32!GetWindowLongW` at `0x180dcbfca`
- `USER32!GetWindowLongW` at `0x180dcbeea`
- `USER32!GetWindowLongW` at `0x180dcbf66`
- `USER32!GetWindowLongW` at `0x180dcbf77`
- `USER32!GetWindowLongW` at `0x180dcbfb5`
- `USER32!GetWindowLongW` at `0x180dcbfca`
- `USER32!EndPaint` at `0x180dcc265`
- `USER32!EndPaint` at `0x180dcc265`
- `USER32!BeginPaint` at `0x180dcbed0`
- `USER32!BeginPaint` at `0x180dcbed0`
- `USER32!MoveWindow` at `0x180dcc94b`
- `USER32!MoveWindow` at `0x180dcc988`
- `USER32!MoveWindow` at `0x180dcc94b`
- `USER32!MoveWindow` at `0x180dcc988`

## pseudocode

```c
LRESULT __fastcall sub_180DCBE30(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)
{
  HWND v7; // rsi
  HDC v9; // rax
  LONG WindowLongW; // eax
  __int64 v11; // rbx
  __int64 v12; // r14
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rdi
  LONG v17; // r15d
  __int64 v18; // rax
  __int64 v19; // r12
  __int64 v20; // rax
  unsigned int v21; // eax
  __int64 v22; // r9
  __int64 v23; // r15
  int v24; // edi
  int v25; // eax
  int v26; // r9d
  int v27; // ecx
  int v28; // r10d
  bool v29; // cc
  __int64 v30; // rdi
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  unsigned __int64 v34; // rcx
  void (__fastcall *v35)(__int64, __int64); // rax
  LONG v36; // eax
  int v37; // r14d
  int v38; // esi
  int v39; // ecx
  bool v40; // cc
  int v41; // esi
  wchar_t *v42; // rdi
  __int64 v43; // rsi
  int v44; // r15d
  __int64 v45; // r9
  int v46; // r15d
  char *Value; // rax
  __int64 v48; // r14
  int v49; // eax
  LONG v50; // edi
  size_t v51; // r8
  __int64 v52; // rcx
  int v53; // eax
  __int64 v54; // rdx
  unsigned __int64 v55; // rcx
  unsigned int v57; // edi
  __int64 v58; // rax
  _QWORD *v59; // rdi
  __int64 v60; // r14
  LONG v61; // ebx
  int v62; // r13d
  LONG v63; // eax
  __int64 v64; // r15
  int v65; // r9d
  int nHeight; // [rsp+20h] [rbp-E0h]
  int bRepaint; // [rsp+28h] [rbp-D8h]
  int v68; // [rsp+30h] [rbp-D0h]
  char v69; // [rsp+50h] [rbp-B0h]
  unsigned int v70; // [rsp+54h] [rbp-ACh]
  struct tagRECT Rect; // [rsp+58h] [rbp-A8h] BYREF
  LONG v72; // [rsp+68h] [rbp-98h]
  __int64 v73; // [rsp+70h] [rbp-90h] BYREF
  __int64 v74; // [rsp+78h] [rbp-88h] BYREF
  int v75; // [rsp+80h] [rbp-80h]
  LONG v76; // [rsp+84h] [rbp-7Ch]
  unsigned int v77; // [rsp+88h] [rbp-78h]
  LONG v78; // [rsp+8Ch] [rbp-74h]
  LONG_PTR WindowLongPtrW; // [rsp+90h] [rbp-70h]
  int v80; // [rsp+98h] [rbp-68h]
  int v81; // [rsp+9Ch] [rbp-64h]
  __int64 v82; // [rsp+A0h] [rbp-60h]
  HWND hWnda; // [rsp+A8h] [rbp-58h]
  __int64 v84; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v85; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v86; // [rsp+C0h] [rbp-40h]
  _BYTE v87[16]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v88; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v89; // [rsp+E8h] [rbp-18h]
  __int128 v90; // [rsp+F8h] [rbp-8h]
  struct tagPAINTSTRUCT Paint; // [rsp+110h] [rbp+10h] BYREF
  wchar_t Str[256]; // [rsp+160h] [rbp+60h] BYREF
  _WORD v93[256]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE Src[1536]; // [rsp+560h] [rbp+460h] BYREF

  v7 = hWnd;
  hWnda = hWnd;
  if ( Msg != 15 )
  {
    if ( Msg != 20 )
    {
      if ( Msg == 129 )
        Mso20Win32Client_55533();
      return DefWindowProcW(v7, Msg, wParam, lParam);
    }
    return 1;
  }
  memset(&Paint, 0, sizeof(Paint));
  v9 = BeginPaint(v7, &Paint);
  sub_18048C758(&v84, v9);
  WindowLongW = GetWindowLongW(v7, 8);
  v11 = v84;
  if ( WindowLongW )
  {
    Rect = 0;
    LODWORD(v12) = 0;
    v13 = qword_1829F6F40;
    if ( qword_182B02938 )
      v13 = qword_182B02938;
    v14 = *(_QWORD *)(v13 + 960);
    v15 = *(_QWORD *)(v14 + 56);
    if ( v15 )
      _InterlockedAdd((volatile signed __int32 *)(v15 + 8), 1u);
    v16 = *(_QWORD *)(v14 + 48);
    v82 = v16;
    v86 = *(_QWORD *)(v14 + 56);
    v81 = 90;
    v75 = sub_180DCD244(v16) + 8 * *(_DWORD *)(v16 + 16);
    v77 = GetWindowLongW(v7, 0);
    v78 = GetWindowLongW(v7, 4);
    v88 = 0;
    v89 = 0;
    v90 = 0;
    WindowLongPtrW = GetWindowLongPtrW(v7, 16);
    v69 = sub_18024B71C(WindowLongPtrW);
    v17 = GetWindowLongW(v7, 24);
    v70 = v17;
    v76 = GetWindowLongW(v7, 28);
    v18 = sub_180874424(v16);
    if ( v18 )
    {
      if ( *(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v18 + 112LL) == sub_180296500 )
        sub_180296500(v18, &v74);
      else
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 112LL))(v18, &v74);
    }
    else
    {
      v74 = 0;
    }
    sub_1802BD1FC(v87, v11, v74);
    v19 = -1;
    if ( v17 == -1 )
      goto LABEL_15;
    v20 = qword_182B02938;
    if ( !qword_182B02938 )
      goto LABEL_16;
    if ( !(unsigned __int8)sub_180013E58() || !v69 )
    {
LABEL_15:
      v20 = qword_182B02938;
LABEL_16:
      v73 = 0;
      Str[0] = 0;
      if ( v20 && *(_BYTE *)(v20 + 2135) )
      {
        v21 = sub_18007EB7C(WindowLongPtrW);
        sub_180DCBB84(qword_182B02938, v77, v21, Str);
        v22 = -1;
        do
          ++v22;
        while ( Str[v22] );
        sub_180DCBC54(v11, v16, (unsigned int)Str, v22, (__int64)&v73);
        v23 = -1;
        do
          ++v23;
        while ( Str[v23] );
        LODWORD(v84) = 0;
        if ( (int)v73 > 170 - 12 * dword_182A18878 )
        {
          LODWORD(v73) = 170 - 12 * dword_182A18878;
          sub_180DCB488(v11, Str);
          v64 = -1;
          do
            ++v64;
          while ( Str[v64] );
        }
        goto LABEL_23;
      }
      if ( qword_182A22B00 )
        (**(void (__fastcall ***)(__int64, __int64, wchar_t *, __int64))qword_182A22B00)(
          qword_182A22B00,
          2534069085LL,
          Str,
          255);
      else
        Mso30Win32Client_38134(qword_182A00670, 2534069085LL, Str, 256);
      if ( wcschr(Str, 0x20u) )
      {
        v42 = wcschr(Str, 0x20u) + 1;
      }
      else
      {
        v58 = -1;
        do
          ++v58;
        while ( Str[v58] );
        v42 = &Str[(int)v58];
      }
      v43 = v42 - Str;
      v84 = v43;
      v44 = 255 - v43;
      v72 = 255 - v43;
      if ( (_WORD)v78 != 0xFFFF )
      {
        v45 = 30;
        if ( v44 < 30 )
          v45 = (unsigned int)v44;
        bRepaint = 0;
        LOWORD(nHeight) = word_182A22618;
        v46 = sub_1802608B8(v77, v42, (unsigned int)(__int16)v78, v45, nHeight);
        if ( v46 )
          goto LABEL_67;
        v44 = v72;
      }
      bRepaint = 1;
      v46 = sub_1800EF8F0(v77, v42, (unsigned int)v44, 1, 10);
LABEL_67:
      v42[v46] = 0;
      if ( !v11 )
      {
        Mso20Win32Client_21217(507263040, 0);
        return 1;
      }
      (*(void (__fastcall **)(__int64, wchar_t *, _QWORD, __int64 *))(*(_QWORD *)v11 + 632LL))(
        v11,
        Str,
        (unsigned int)(v43 + v46),
        &v73);
      v7 = hWnda;
LABEL_23:
      v24 = v73 + 12 * dword_182A18878;
      if ( v81 >= v24 )
        v24 = v81;
      v25 = v75;
      if ( v75 < SHIDWORD(v73) )
        v25 = HIDWORD(v73);
      v75 = v25;
      if ( v70 != -1 || v69 && (unsigned int)sub_1809CD498(WindowLongPtrW, 0, 1) )
      {
        v36 = 0;
        if ( v70 != -1 )
          v36 = v12;
        v72 = v36;
        if ( v24 < 170 )
          v24 = 170;
        GetWindowRect(v7, &Rect);
        v37 = Rect.right - Rect.left;
        v38 = Rect.bottom - Rect.top;
        v39 = 2 * v75;
        v40 = Rect.bottom - Rect.top < 2 * v75;
        if ( Rect.bottom - Rect.top >= 2 * v75 )
        {
          if ( v37 >= v24 )
          {
LABEL_55:
            GetClientRect(hWnda, &Rect);
            sub_180DCCFFC(v11, &Rect, v82, 0, 0);
            v41 = v38 >> 1;
            Rect.top += v41;
            v34 = (unsigned int)(Rect.left + 4 * *(_DWORD *)(v82 + 12));
            Rect.left += 4 * *(_DWORD *)(v82 + 12);
            if ( (unsigned __int64)(2LL * v72) >= 0x200 )
              goto LABEL_44;
            v93[v72] = 0;
            sub_180DCB488(v11, v93);
            do
              ++v19;
            while ( v93[v19] );
            v68 = 0;
            v30 = v82;
            sub_180DCCFFC(v11, &Rect, v82, v93, v19);
            Rect.top += 2 * *(_DWORD *)(v30 + 16) - v41;
            v7 = hWnda;
            goto LABEL_34;
          }
          v40 = v38 < v39;
        }
        if ( !v40 )
          v39 = Rect.bottom - Rect.top;
        v78 = v39;
        v65 = v24;
        if ( v37 >= v24 )
          v65 = Rect.right - Rect.left;
        Rect.top += (v38 >> 1) - (v39 >> 1);
        MoveWindow(hWnda, Rect.right - v65, Rect.top, v65, v39, 1);
        v38 = v78;
        goto LABEL_55;
      }
      if ( v24 < 90 )
        v24 = 90;
      GetWindowRect(v7, &Rect);
      v26 = Rect.right - Rect.left;
      v27 = Rect.bottom - Rect.top;
      v28 = v75;
      v29 = Rect.bottom - Rect.top < v75;
      if ( Rect.bottom - Rect.top >= v75 )
      {
        if ( v26 >= v24 )
        {
LABEL_33:
          GetClientRect(v7, &Rect);
          v68 = 1;
          v30 = v82;
          sub_180DCCFFC(v11, &Rect, v82, 0, 0);
          Rect.top += 2 * *(_DWORD *)(v30 + 16);
          Rect.left += 4 * *(_DWORD *)(v30 + 12);
LABEL_34:
          v31 = sub_180DCC998(Str);
          v33 = v31;
          v34 = 2LL * v31;
          if ( v34 >= 0x200 )
            goto LABEL_44;
          Str[v31] = 0;
          if ( qword_182B02938 && *(_BYTE *)(qword_182B02938 + 2135) )
            sub_180DCB8CC(v11, v30, (unsigned int)&Rect, (unsigned int)Str, v31, bRepaint, v68, v74);
          else
            sub_180DCCFFC(v11, &Rect, v30, Str, v31);
          sub_1802BD274(v87);
          if ( v74 )
          {
            v35 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v74 + 64LL);
            if ( (char *)v35 == (char *)sub_1802DA350 )
              sub_1802DA350(v74, 1);
            else
              v35(v74, 1);
          }
          v74 = 19937;
          sub_180018C58(&v88);
          if ( v86 )
            sub_1800A71B0(v86);
          goto LABEL_41;
        }
        v29 = v27 < v75;
      }
      if ( !v29 )
        v28 = Rect.bottom - Rect.top;
      if ( v24 >= v26 )
        v26 = v24;
      Rect.top += (v27 >> 1) - (v28 >> 1);
      Rect.bottom = v28 + Rect.top;
      Rect.left = Rect.right - v26;
      MoveWindow(v7, Rect.right - v26, Rect.top, v26, v28, 1);
      goto LABEL_33;
    }
    v80 = 1;
    v81 = 170;
LABEL_74:
    Value = (char *)TlsGetValue(dwTlsIndex);
    sub_180086F40(Value + 8, WindowLongPtrW, v70, 5);
    v72 = *((_DWORD *)TlsGetValue(dwTlsIndex) + 3);
    while ( 1 )
    {
      if ( (dword_182A01BE8 & 0x4000) != 0 )
      {
        v59 = (_QWORD *)qword_1829FD1F0;
        v60 = qword_1829FD1F8;
        while ( v59 != (_QWORD *)v60 )
          sub_180056784(*v59++);
      }
      v85 = 0;
      sub_18025C554(qword_182B02938, WindowLongPtrW, v17, 0, 0, (__int64)&v88, (__int64)&v85);
      v48 = v85;
      sub_180018C58(&v88);
      v88 = 0;
      v89 = 0;
      v90 = 0;
      *((_QWORD *)&v90 + 1) = *(_QWORD *)(v48 + 64);
      if ( *(_QWORD *)(v48 + 344) )
      {
        *(_QWORD *)&v88 = *(_QWORD *)(v48 + 344);
        sub_180D1E938(*(_QWORD *)(v48 + 344));
      }
      v49 = sub_180947A60((unsigned int)Src, 768, v48, 0x7FFFFFFF, 0, 1152);
      if ( v49 > 255 )
        v49 = 255;
      LODWORD(v73) = v49;
      v50 = v17 + 1;
      v17 = sub_18007F3D0(v48);
      if ( v17 < v50 )
        v17 = v50;
      if ( (unsigned __int64)(int)v73 > 0x3FFFFFFF )
        v51 = -1;
      else
        v51 = 2LL * (int)v73;
      if ( v51 == -1 )
      {
        v52 = 24651290;
      }
      else
      {
        if ( v51 <= 0x7FFFFFFF )
        {
          memcpy(v93, Src, v51);
          goto LABEL_88;
        }
        v52 = 24651287;
      }
      Mso20Win32Client_7228(v52);
LABEL_88:
      sub_180DCC998(v93);
      v53 = sub_1800C77C0(v93);
      v12 = v53;
      v55 = 2LL * v53;
      if ( v55 >= 0x200 )
        sub_1813CEA08(v55, v54, v33);
      v93[v53] = 0;
      v32 = v85;
      if ( v85 )
      {
        v85 = 0;
        if ( (*(_DWORD *)(v32 + 1232))-- == 1 )
          sub_180076A80();
      }
      if ( (_DWORD)v12 )
      {
        v34 = (unsigned int)(v12 - 1);
        if ( Str[v12 + 255] == 13 )
          LODWORD(v12) = v12 - 1;
        goto LABEL_108;
      }
      if ( v17 >= v76 || v17 >= v72 )
      {
        v57 = v70;
        v17 = sub_1809CD57C(WindowLongPtrW, v70, 0, v80, 0);
        v70 = v17;
        if ( v17 >= v76 )
        {
          v80 = 0;
          v61 = v76;
          v62 = WindowLongPtrW;
          do
          {
            v63 = sub_1809CD57C(v62, v57, 0, 0, 0);
            v70 = v63;
          }
          while ( v63 >= v61 );
          v11 = v84;
          v19 = -1;
          v7 = hWnda;
          v17 = v63;
        }
        if ( v17 != -1 )
          goto LABEL_74;
LABEL_108:
        if ( (unsigned __int64)(2LL * (int)v12) < 0x200 )
        {
          v93[(int)v12] = 0;
          sub_180013E98();
          LODWORD(v16) = v82;
          goto LABEL_15;
        }
LABEL_44:
        sub_1813CEA08(v34, v32, v33);
      }
    }
  }
LABEL_41:
  EndPaint(v7, &Paint);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return 0;
}

```

## disassembly

```asm
0x180dcbe30  push    rbp
0x180dcbe32  push    rbx
0x180dcbe33  push    rsi
0x180dcbe34  push    rdi
0x180dcbe35  push    r12
0x180dcbe37  push    r13
0x180dcbe39  push    r14
0x180dcbe3b  push    r15
0x180dcbe3d  lea     rbp, [rsp-0A78h]
0x180dcbe45  sub     rsp, 0B78h
0x180dcbe4c  mov     rax, cs:__security_cookie
0x180dcbe53  xor     rax, rsp
0x180dcbe56  mov     [rbp+0AB0h+var_50], rax
0x180dcbe5d  mov     r14, r9
0x180dcbe60  mov     rdi, r8
0x180dcbe63  mov     ebx, edx
0x180dcbe65  mov     rsi, rcx
0x180dcbe68  mov     [rbp+0AB0h+hWnd], rcx
0x180dcbe6c  mov     eax, edx
0x180dcbe6e  sub     eax, 0Fh
0x180dcbe71  jz      short loc_180DCBEBA
0x180dcbe73  sub     eax, 5
0x180dcbe76  jz      loc_180DCC51D
0x180dcbe7c  cmp     eax, 6Dh ; 'm'
0x180dcbe7f  jz      loc_180DCC83A
0x180dcbe85  mov     r9, r14; lParam
0x180dcbe88  mov     r8, rdi; wParam
0x180dcbe8b  mov     edx, ebx; Msg
0x180dcbe8d  mov     rcx, rsi; hWnd
0x180dcbe90  call    cs:DefWindowProcW
0x180dcbe96  nop
0x180dcbe97  mov     rcx, [rbp+0AB0h+var_50]
0x180dcbe9e  xor     rcx, rsp; StackCookie
0x180dcbea1  call    __security_check_cookie
0x180dcbea6  add     rsp, 0B78h
0x180dcbead  pop     r15
0x180dcbeaf  pop     r14
0x180dcbeb1  pop     r13
0x180dcbeb3  pop     r12
0x180dcbeb5  pop     rdi
0x180dcbeb6  pop     rsi
0x180dcbeb7  pop     rbx
0x180dcbeb8  pop     rbp
0x180dcbeb9  retn
0x180dcbeba  xor     edx, edx; Val
0x180dcbebc  lea     r8d, [rdx+48h]; Size
0x180dcbec0  lea     rcx, [rbp+0AB0h+Paint]; void *
0x180dcbec4  call    memset
0x180dcbec9  lea     rdx, [rbp+0AB0h+Paint]; lpPaint
0x180dcbecd  mov     rcx, rsi; hWnd
0x180dcbed0  call    cs:BeginPaint
0x180dcbed6  mov     rdx, rax
0x180dcbed9  lea     rcx, [rbp+0AB0h+var_B00]
0x180dcbedd  call    sub_18048C758
0x180dcbee2  mov     edx, 8; nIndex
0x180dcbee7  mov     rcx, rsi; hWnd
0x180dcbeea  call    cs:GetWindowLongW
0x180dcbef0  mov     rbx, [rbp+0AB0h+var_B00]
0x180dcbef4  xor     r12d, r12d
0x180dcbef7  test    eax, eax
0x180dcbef9  jz      loc_180DCC25E
0x180dcbeff  xorps   xmm0, xmm0
0x180dcbf02  movups  xmmword ptr [rsp+0BB0h+Rect.left], xmm0
0x180dcbf07  mov     r14d, r12d
0x180dcbf0a  mov     rcx, cs:qword_1829F6F40
0x180dcbf11  mov     rax, cs:qword_182B02938
0x180dcbf18  test    rax, rax
0x180dcbf1b  cmovnz  rcx, rax
0x180dcbf1f  mov     rdx, [rcx+3C0h]
0x180dcbf26  mov     rax, [rdx+38h]
0x180dcbf2a  lea     r13d, [r12+1]
0x180dcbf2f  test    rax, rax
0x180dcbf32  jz      short loc_180DCBF39
0x180dcbf34  lock add [rax+8], r13d
0x180dcbf39  mov     rdi, [rdx+30h]
0x180dcbf3d  mov     [rbp+0AB0h+var_B10], rdi
0x180dcbf41  mov     rax, [rdx+38h]
0x180dcbf45  mov     [rbp+0AB0h+var_AF0], rax
0x180dcbf49  mov     [rbp+0AB0h+var_B14], 5Ah ; 'Z'
0x180dcbf50  mov     rcx, rdi
0x180dcbf53  call    sub_180DCD244
0x180dcbf58  mov     ecx, [rdi+10h]
0x180dcbf5b  lea     ecx, [rax+rcx*8]
0x180dcbf5e  mov     [rbp+0AB0h+var_B30], ecx
0x180dcbf61  xor     edx, edx; nIndex
0x180dcbf63  mov     rcx, rsi; hWnd
0x180dcbf66  call    cs:GetWindowLongW
0x180dcbf6c  mov     [rbp+0AB0h+var_B28], eax
0x180dcbf6f  mov     edx, 4; nIndex
0x180dcbf74  mov     rcx, rsi; hWnd
0x180dcbf77  call    cs:GetWindowLongW
0x180dcbf7d  mov     [rbp+0AB0h+var_B24], eax
0x180dcbf80  xorps   xmm0, xmm0
0x180dcbf83  movups  [rbp+0AB0h+var_AD8], xmm0
0x180dcbf87  movups  [rbp+0AB0h+var_AC8], xmm0
0x180dcbf8b  movups  [rbp+0AB0h+var_AB8], xmm0
0x180dcbf8f  mov     edx, 10h; nIndex
0x180dcbf94  mov     rcx, rsi; hWnd
0x180dcbf97  call    cs:GetWindowLongPtrW
0x180dcbf9d  mov     [rbp+0AB0h+var_B20], rax
0x180dcbfa1  mov     rcx, rax
0x180dcbfa4  call    sub_18024B71C
0x180dcbfa9  mov     [rsp+0BB0h+var_B60], al
0x180dcbfad  mov     edx, 18h; nIndex
0x180dcbfb2  mov     rcx, rsi; hWnd
0x180dcbfb5  call    cs:GetWindowLongW
0x180dcbfbb  mov     r15d, eax
0x180dcbfbe  mov     [rsp+0BB0h+var_B5C], eax
0x180dcbfc2  mov     edx, 1Ch; nIndex
0x180dcbfc7  mov     rcx, rsi; hWnd
0x180dcbfca  call    cs:GetWindowLongW
0x180dcbfd0  mov     [rbp+0AB0h+var_B2C], eax
0x180dcbfd3  mov     rcx, rdi
0x180dcbfd6  call    sub_180874424
0x180dcbfdb  test    rax, rax
0x180dcbfde  jz      loc_180DCC818
0x180dcbfe4  mov     rcx, [rax]
0x180dcbfe7  mov     r8, [rcx+70h]
0x180dcbfeb  lea     rcx, sub_180296500
0x180dcbff2  lea     rdx, [rsp+0BB0h+var_B38]
0x180dcbff7  cmp     r8, rcx
0x180dcbffa  mov     rcx, rax
0x180dcbffd  jnz     loc_180DCC822
0x180dcc003  call    sub_180296500
0x180dcc008  mov     r8, [rsp+0BB0h+var_B38]
0x180dcc00d  mov     rdx, rbx
0x180dcc010  lea     rcx, [rbp+0AB0h+var_AE8]
0x180dcc014  call    sub_1802BD1FC
0x180dcc019  or      r12, 0FFFFFFFFFFFFFFFFh
0x180dcc01d  cmp     r15d, r12d
0x180dcc020  jnz     loc_180DCC527
0x180dcc026  mov     rax, cs:qword_182B02938
0x180dcc02d  xor     r15d, r15d
0x180dcc030  mov     [rsp+0BB0h+var_B40], r15
0x180dcc035  mov     [rbp+0AB0h+Str], r15w
0x180dcc03a  test    rax, rax
0x180dcc03d  jz      loc_180DCC43C
0x180dcc043  cmp     [rax+857h], r15b
0x180dcc04a  jz      loc_180DCC43C
0x180dcc050  mov     rcx, [rbp+0AB0h+var_B20]
0x180dcc054  call    sub_18007EB7C
0x180dcc059  lea     r9, [rbp+0AB0h+Str]
0x180dcc05d  mov     r8d, eax
0x180dcc060  mov     edx, [rbp+0AB0h+var_B28]
0x180dcc063  mov     rcx, cs:qword_182B02938
0x180dcc06a  call    sub_180DCBB84
0x180dcc06f  lea     rax, [rbp+0AB0h+Str]
0x180dcc073  mov     r9, r12
0x180dcc076  inc     r9
0x180dcc079  cmp     [rax+r9*2], r15w
0x180dcc07e  jnz     short loc_180DCC076
0x180dcc080  lea     rax, [rsp+0BB0h+var_B40]
0x180dcc085  mov     qword ptr [rsp+0BB0h+nHeight], rax
0x180dcc08a  lea     r8, [rbp+0AB0h+Str]
0x180dcc08e  mov     rdx, rdi
0x180dcc091  mov     rcx, rbx
0x180dcc094  call    sub_180DCBC54
0x180dcc099  lea     rax, [rbp+0AB0h+Str]
0x180dcc09d  mov     r15, r12
0x180dcc0a0  xor     edx, edx
0x180dcc0a2  inc     r15
0x180dcc0a5  cmp     [rax+r15*2], dx
0x180dcc0aa  jnz     short loc_180DCC0A2
0x180dcc0ac  mov     dword ptr [rbp+0AB0h+var_B00], edx
0x180dcc0af  mov     eax, cs:dword_182A18878
0x180dcc0b5  lea     ecx, [rax+rax*2]
0x180dcc0b8  shl     ecx, 2
0x180dcc0bb  mov     r8d, 0AAh
0x180dcc0c1  sub     r8d, ecx
0x180dcc0c4  cmp     dword ptr [rsp+0BB0h+var_B40], r8d
0x180dcc0c9  jg      loc_180DCC88F
0x180dcc0cf  mov     eax, cs:dword_182A18878
0x180dcc0d5  lea     ecx, [rax+rax*2]
0x180dcc0d8  mov     eax, dword ptr [rsp+0BB0h+var_B40]
0x180dcc0dc  lea     edi, [rax+rcx*4]
0x180dcc0df  cmp     [rbp+0AB0h+var_B14], edi
0x180dcc0e2  cmovge  edi, [rbp+0AB0h+var_B14]
0x180dcc0e6  mov     eax, [rbp+0AB0h+var_B30]
0x180dcc0e9  cmp     eax, dword ptr [rsp+0BB0h+var_B40+4]
0x180dcc0ed  cmovl   eax, dword ptr [rsp+0BB0h+var_B40+4]
0x180dcc0f2  mov     [rbp+0AB0h+var_B30], eax
0x180dcc0f5  cmp     [rsp+0BB0h+var_B5C], r12d
0x180dcc0fa  jnz     loc_180DCC2F1
0x180dcc100  cmp     [rsp+0BB0h+var_B60], dl
0x180dcc104  jnz     loc_180DCC2D9
0x180dcc10a  mov     eax, 5Ah ; 'Z'
0x180dcc10f  cmp     edi, eax
0x180dcc111  cmovl   edi, eax
0x180dcc114  lea     rdx, [rsp+0BB0h+Rect]; lpRect
0x180dcc119  mov     rcx, rsi; hWnd
0x180dcc11c  call    cs:GetWindowRect
0x180dcc122  mov     edx, [rsp+0BB0h+Rect.right]
0x180dcc126  mov     r9d, edx
0x180dcc129  sub     r9d, [rsp+0BB0h+Rect.left]
0x180dcc12e  mov     ecx, [rsp+0BB0h+Rect.bottom]
0x180dcc132  mov     r8d, [rsp+0BB0h+Rect.top]
0x180dcc137  sub     ecx, r8d
0x180dcc13a  mov     r10d, [rbp+0AB0h+var_B30]
0x180dcc13e  cmp     ecx, r10d
0x180dcc141  jl      loc_180DCC913
0x180dcc147  cmp     r9d, edi
0x180dcc14a  jl      loc_180DCC910
0x180dcc150  lea     rdx, [rsp+0BB0h+Rect]; lpRect
0x180dcc155  mov     rcx, rsi; hWnd
0x180dcc158  call    cs:GetClientRect
0x180dcc15e  mov     rax, [rsp+0BB0h+var_B38]
0x180dcc163  mov     [rsp+0BB0h+var_B70], rax
0x180dcc168  xor     r12d, r12d
0x180dcc16b  mov     dword ptr [rsp+0BB0h+var_B78], r12d
0x180dcc170  mov     dword ptr [rsp+0BB0h+var_B80], r13d
0x180dcc175  mov     [rsp+0BB0h+nHeight], r12d
0x180dcc17a  xor     r9d, r9d
0x180dcc17d  mov     rdi, [rbp+0AB0h+var_B10]
0x180dcc181  mov     r8, rdi
0x180dcc184  lea     rdx, [rsp+0BB0h+Rect]
0x180dcc189  mov     rcx, rbx
0x180dcc18c  call    sub_180DCCFFC
0x180dcc191  mov     ecx, [rdi+10h]
0x180dcc194  mov     eax, [rsp+0BB0h+Rect.top]
0x180dcc198  lea     ecx, [rax+rcx*2]
0x180dcc19b  mov     [rsp+0BB0h+Rect.top], ecx
0x180dcc19f  mov     ecx, [rdi+0Ch]
0x180dcc1a2  mov     eax, [rsp+0BB0h+Rect.left]
0x180dcc1a6  lea     ecx, [rax+rcx*4]
0x180dcc1a9  mov     [rsp+0BB0h+Rect.left], ecx
0x180dcc1ad  mov     rdx, [rbp+0AB0h+var_B00]
0x180dcc1b1  add     edx, r15d
0x180dcc1b4  mov     r9d, 30h ; '0'
0x180dcc1ba  mov     r8d, edx
0x180dcc1bd  lea     rcx, [rbp+0AB0h+Str]; Src
0x180dcc1c1  call    sub_180DCC998
0x180dcc1c6  movsxd  r8, eax
0x180dcc1c9  mov     rcx, r8
0x180dcc1cc  add     rcx, rcx
0x180dcc1cf  cmp     rcx, 200h
0x180dcc1d6  jnb     loc_180DCC287
0x180dcc1dc  mov     [rbp+rcx+0AB0h+Str], r12w
0x180dcc1e2  mov     rax, cs:qword_182B02938
0x180dcc1e9  test    rax, rax
0x180dcc1ec  jz      short loc_180DCC1FB
0x180dcc1ee  cmp     [rax+857h], r12b
0x180dcc1f5  jnz     loc_180DCC28D
0x180dcc1fb  mov     rax, [rsp+0BB0h+var_B38]
0x180dcc200  mov     [rsp+0BB0h+var_B70], rax
0x180dcc205  mov     dword ptr [rsp+0BB0h+var_B78], r12d
0x180dcc20a  mov     dword ptr [rsp+0BB0h+var_B80], r12d
0x180dcc20f  mov     [rsp+0BB0h+nHeight], r8d
0x180dcc214  lea     r9, [rbp+0AB0h+Str]
0x180dcc218  mov     r8, rdi
0x180dcc21b  lea     rdx, [rsp+0BB0h+Rect]
0x180dcc220  mov     rcx, rbx
0x180dcc223  call    sub_180DCCFFC
0x180dcc228  lea     rcx, [rbp+0AB0h+var_AE8]
0x180dcc22c  call    sub_1802BD274
0x180dcc231  mov     rcx, [rsp+0BB0h+var_B38]
0x180dcc236  test    rcx, rcx
0x180dcc239  jnz     short loc_180DCC2B5
0x180dcc23b  mov     [rsp+0BB0h+var_B38], 4DE1h
0x180dcc244  lea     rcx, [rbp+0AB0h+var_AD8]
0x180dcc248  call    sub_180018C58
0x180dcc24d  mov     rax, [rbp+0AB0h+var_AF0]
0x180dcc251  test    rax, rax
0x180dcc254  jz      short loc_180DCC25E
0x180dcc256  mov     rcx, rax
0x180dcc259  call    sub_1800A71B0
0x180dcc25e  lea     rdx, [rbp+0AB0h+Paint]; lpPaint
0x180dcc262  mov     rcx, rsi; hWnd
0x180dcc265  call    cs:EndPaint
0x180dcc26b  test    rbx, rbx
0x180dcc26e  jz      short loc_180DCC280
0x180dcc270  mov     rax, [rbx]
0x180dcc273  mov     rcx, rbx
0x180dcc276  mov     rax, [rax+10h]
0x180dcc27a  call    cs:__guard_dispatch_icall_fptr
0x180dcc280  xor     eax, eax
0x180dcc282  jmp     loc_180DCBE97
0x180dcc287  call    sub_1813CEA08
0x180dcc28d  mov     rax, [rsp+0BB0h+var_B38]
0x180dcc292  mov     [rsp+0BB0h+var_B78], rax
0x180dcc297  mov     [rsp+0BB0h+nHeight], r8d
0x180dcc29c  lea     r9, [rbp+0AB0h+Str]
0x180dcc2a0  lea     r8, [rsp+0BB0h+Rect]
0x180dcc2a5  mov     rdx, rdi
0x180dcc2a8  mov     rcx, rbx
0x180dcc2ab  call    sub_180DCB8CC
0x180dcc2b0  jmp     loc_180DCC228
0x180dcc2b5  mov     rax, [rcx]
0x180dcc2b8  mov     rax, [rax+40h]
0x180dcc2bc  lea     rdx, sub_1802DA350
0x180dcc2c3  cmp     rax, rdx
0x180dcc2c6  mov     edx, r13d
0x180dcc2c9  jnz     loc_180DCC7D6
0x180dcc2cf  call    sub_1802DA350
0x180dcc2d4  jmp     loc_180DCC23B
0x180dcc2d9  mov     r8d, r13d
0x180dcc2dc  xor     edx, edx
0x180dcc2de  mov     rcx, [rbp+0AB0h+var_B20]
0x180dcc2e2  call    sub_1809CD498
0x180dcc2e7  xor     edx, edx
0x180dcc2e9  test    eax, eax
  ... truncated ...
```
