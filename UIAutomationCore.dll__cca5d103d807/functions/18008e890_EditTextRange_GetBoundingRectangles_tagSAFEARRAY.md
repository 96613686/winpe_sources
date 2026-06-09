# EditTextRange::GetBoundingRectangles(tagSAFEARRAY * *)

- ea: `0x18008e890`
- end: `0x18008f0a9`
- name: `?GetBoundingRectangles@EditTextRange@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `2073`
- prototype: `__int64 __fastcall(EditTextRange *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000f680`
- `0x18002f580`
- `0x18008e598`
- `0x18008e890`
- `0x18008f0b0`
- `0x18012b47c`
- `0x1801a8e74`
- `0x1801b7888`
- `0x1801bb114`
- `0x1801c37d0`
- `0x1801e8320`
- `0x1801e8344`
- `0x1801e9258`
- `0x18027e5ac`
- `0x18027e78c`
- `0x180283a34`
- `0x180283d58`
- `0x1802843ac`
- `0x180284404`
- `0x180286f7c`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ee81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ee81`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowLongPtrW` at `0x18008ea67`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowLongPtrW` at `0x18008ea67`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetFocus` at `0x18008e985`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetFocus` at `0x18008e985`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18008ee77`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18008ee77`

## string_xrefs

- `0x18008e915`: `onecore\windows\accessibletech\uiautomationcore\proxies\editproxy.cpp`
- `0x18008e9e8`: `onecore\windows\accessibletech\uiautomationcore\proxies\editproxy.cpp`
- `0x18008ecd8`: `onecore\windows\accessibletech\uiautomationcore\proxies\editproxy.cpp`
- `0x18008ed2b`: `onecore\windows\accessibletech\uiautomationcore\proxies\editproxy.cpp`
- `0x18008ef00`: `onecore\windows\accessibletech\uiautomationcore\proxies\editproxy.cpp`
- `0x18008efcc`: `onecore\windows\accessibletech\uiautomationcore\proxies\editproxy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EditTextRange::GetBoundingRectangles(EditTextRange *this, struct tagSAFEARRAY **a2)
{
  SAFEARRAY **v2; // r12
  EditTextRange *v4; // r14
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int16 v8; // r8
  HWND Hwnd; // rbx
  int v10; // eax
  __int16 v11; // r8
  __int64 v12; // rdx
  HWND v13; // rax
  unsigned int v14; // r15d
  unsigned int v15; // esi
  unsigned int v16; // eax
  unsigned int v17; // ecx
  HWND v18; // rax
  HWND v19; // rax
  int i; // r13d
  unsigned int v21; // r12d
  unsigned int v22; // ebx
  HWND v23; // rax
  int v24; // eax
  int v25; // r12d
  HWND v26; // rax
  int v27; // eax
  __int64 v28; // rdx
  unsigned int v29; // ecx
  signed int LastError; // eax
  double v31; // xmm6_8
  int v32; // eax
  int v33; // eax
  void *v34; // rcx
  int v35; // ebx
  unsigned int v36; // esi
  int v37; // eax
  __int16 v38; // r8
  _QWORD *v39; // rdi
  int v40; // ebx
  int v41; // eax
  struct EditBuffer *v43; // rbx
  int v44; // [rsp+28h] [rbp-E0h]
  bool v45[8]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v46; // [rsp+50h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-B0h] BYREF
  void *v48; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v49; // [rsp+68h] [rbp-A0h]
  void *Block; // [rsp+70h] [rbp-98h]
  __m256i v51; // [rsp+78h] [rbp-90h] BYREF
  unsigned int pvParam; // [rsp+98h] [rbp-70h] BYREF
  int v53; // [rsp+9Ch] [rbp-6Ch] BYREF
  int v54; // [rsp+A0h] [rbp-68h] BYREF
  bool v55; // [rsp+A8h] [rbp-60h] BYREF
  __int16 v56; // [rsp+A9h] [rbp-5Fh]
  char v57; // [rsp+ABh] [rbp-5Dh]
  int v58; // [rsp+ACh] [rbp-5Ch]
  struct EditBuffer *v59; // [rsp+B0h] [rbp-58h] BYREF
  unsigned int v60; // [rsp+B8h] [rbp-50h] BYREF
  int v61; // [rsp+BCh] [rbp-4Ch] BYREF
  int v62; // [rsp+C0h] [rbp-48h] BYREF
  unsigned int v63; // [rsp+C4h] [rbp-44h]
  struct tagSAFEARRAY **v64; // [rsp+C8h] [rbp-40h] BYREF
  void *v65; // [rsp+D0h] [rbp-38h]
  struct UiaRect v66; // [rsp+D8h] [rbp-30h] BYREF
  struct UiaRect v67; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v68; // [rsp+118h] [rbp+10h] BYREF
  _DWORD v69[24]; // [rsp+128h] [rbp+20h] BYREF
  _DWORD v70[24]; // [rsp+188h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+240h] [rbp+138h]

  v2 = a2;
  v64 = a2;
  *a2 = 0;
  v59 = 0;
  v4 = (EditTextRange *)((char *)this - 16);
  v5 = (*(__int64 (__fastcall **)(_QWORD, struct EditBuffer **))(**((_QWORD **)this + 1) + 40LL))(
         *((_QWORD *)this + 1),
         &v59);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 1663;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\editproxy.cpp",
      (const char *)(unsigned int)v5,
      v44);
    goto LABEL_101;
  }
  v5 = EditTextRange::ValidateEndpoints(v4, v59);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 1664;
    goto LABEL_5;
  }
  if ( *((_DWORD *)this + 6) != 1 && *((_DWORD *)this + 4) >= *((_DWORD *)this + 5) )
  {
    v6 = ArrayToSafeArray<double>(0, 0, v8, v2);
    goto LABEL_101;
  }
  v48 = 0;
  LODWORD(v49) = 0;
  Block = 0;
  v51.m256i_i32[0] = 0;
  memset(&v51.m256i_u64[1], 0, 24);
  if ( *((_DWORD *)this + 6) == 1 )
  {
    Hwnd = EditTextRange::GetHwnd(v4);
    if ( GetFocus() == Hwnd )
    {
      memset(&v66, 0, sizeof(v66));
      if ( EditTextRange::_GetMSAACaretBoundsIntersect(v4, &v66) )
      {
        BasicArrayBuilder<UiaRect>::Add(&v48, &v66);
LABEL_87:
        LODWORD(v64) = 0;
        v65 = 0;
        v32 = BasicArrayBuilder<UiaRect>::Count(&v48);
        v33 = BasicArrayPair<double>::AllocInit(&v64, (unsigned int)(4 * v32));
        v6 = v33;
        if ( v33 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x74B,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\editproxy.cpp",
            (const char *)(unsigned int)v33,
            v44);
          v34 = v65;
          if ( !v65 )
            goto LABEL_96;
          goto LABEL_95;
        }
        v35 = 0;
        v36 = 0;
        v37 = BasicArrayBuilder<UiaRect>::Count(&v48);
        v39 = v65;
        if ( v37 > 0 )
        {
          do
          {
            v39[v35] = *(_QWORD *)BasicArrayBuilder<UiaRect>::operator[](&v48, v36);
            v39[v35 + 1] = *(_QWORD *)(BasicArrayBuilder<UiaRect>::operator[](&v48, v36) + 8);
            v40 = v35 + 2;
            v39[v40] = *(_QWORD *)(BasicArrayBuilder<UiaRect>::operator[](&v48, v36) + 16);
            v39[v40 + 1] = *(_QWORD *)(BasicArrayBuilder<UiaRect>::operator[](&v48, v36++) + 24);
            v35 = v40 + 2;
          }
          while ( (int)v36 < (int)BasicArrayBuilder<UiaRect>::Count(&v48) );
        }
        v41 = ArrayToSafeArray<double>((__int64)v39, (signed int)v64, v38, v2);
        v6 = v41;
        if ( v41 >= 0 )
        {
          if ( v39 )
            operator delete(v39);
          if ( Block && Block != v48 )
            operator delete(Block);
          v51.m256i_i64[1] = (__int64)v48;
          v51.m256i_i32[0] = 0;
          Block = v48;
          v43 = v59;
          if ( v59 )
          {
            EditBuffer::~EditBuffer(v59);
            operator delete(v43);
          }
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x756,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\editproxy.cpp",
          (const char *)(unsigned int)v41,
          v44);
        if ( v39 )
        {
          v34 = v39;
LABEL_95:
          operator delete(v34);
        }
LABEL_96:
        if ( Block )
        {
          if ( Block != v48 )
            operator delete(Block);
        }
        v51.m256i_i32[0] = 0;
        goto LABEL_100;
      }
    }
  }
  v47 = 0;
  v46 = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(**((_QWORD **)this + 1)
                                                                                                + 88LL))(
          *((_QWORD *)this + 1),
          &v47);
  v6 = v10;
  if ( v10 < 0 )
  {
    v12 = 1721;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\editproxy.cpp",
      (const char *)(unsigned int)v10,
      v44);
LABEL_16:
    AutoRelease<EditTextRange *>::~AutoRelease<EditTextRange *>(&v46);
    wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v47);
    goto LABEL_96;
  }
  if ( !v47 )
    goto LABEL_18;
  v10 = (**v47)(v47, &GUID_dc866705_ac34_41d4_a190_2059e0a16491, &v46);
  v6 = v10;
  if ( v10 < 0 )
  {
    v12 = 1728;
    goto LABEL_15;
  }
  v13 = EditTextRange::GetHwnd(v4);
  if ( (GetWindowLongPtrW(v13, -20) & 0x2000) != 0 )
  {
    v14 = *((_DWORD *)this + 4);
    v15 = *(_DWORD *)(v46 + 36);
    if ( *((_DWORD *)this + 5) >= v15 )
      v15 = *((_DWORD *)this + 5);
    if ( v14 >= *(_DWORD *)(v46 + 32) )
      v14 = *(_DWORD *)(v46 + 32);
  }
  else
  {
    v14 = *(_DWORD *)(v46 + 32);
    if ( *((_DWORD *)this + 4) >= v14 )
      v14 = *((_DWORD *)this + 4);
    v15 = *((_DWORD *)this + 5);
    if ( v15 >= *(_DWORD *)(v46 + 36) )
      v15 = *(_DWORD *)(v46 + 36);
  }
  if ( *((_DWORD *)this + 6) != 1 )
  {
    v16 = v15 - 1;
    if ( !v15 )
      v16 = 0;
    v15 = v16;
    if ( v14 > v16 )
    {
LABEL_18:
      v6 = ArrayToSafeArray<double>(0, 0, v11, v2);
      goto LABEL_16;
    }
  }
  v68 = 0;
  (*(void (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 1) + 104LL))(*((_QWORD *)this + 1), &v68);
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 32LL))(*((_QWORD *)this + 1)) )
  {
    if ( *((_DWORD *)this + 6) == 1 )
    {
      memset_0(v70, 0, 0x5Cu);
      v10 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1), v70);
      v6 = v10;
      if ( v10 < 0 )
      {
        v12 = 1836;
        goto LABEL_15;
      }
      v29 = v70[0];
      if ( ((v70[0] & 0x40000000) != 0) != __OFSUB__(v70[0], -v70[0]) )
        v29 = -v70[0];
    }
    else
    {
      v29 = HIDWORD(v68) - DWORD1(v68);
    }
    memset(&v67, 0, sizeof(v67));
    v45[0] = 0;
    *(_OWORD *)&v66.left = v68;
    v10 = EditTextRange::CalculateOneLineRangeRectangle(v4, v14, v15, v59, v29, (struct tagRECT *)&v66, &v67, v45);
    v6 = v10;
    if ( v10 >= 0 )
    {
      if ( v45[0] )
        BasicArrayBuilder<UiaRect>::Add(&v48, &v67);
LABEL_80:
      if ( *((_DWORD *)this + 6) == 1 && (int)BasicArrayBuilder<UiaRect>::Count(&v48) > 0 )
      {
        pvParam = 0;
        if ( !SystemParametersInfoW(0x2006u, 0, &pvParam, 0) )
        {
          LastError = GetLastError();
          v6 = LastError;
          if ( LastError > 0 )
            v6 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_16;
        }
        v31 = (double)(int)pvParam;
        *(double *)(BasicArrayBuilder<UiaRect>::operator[](&v48, 0) + 16) = v31;
      }
      AutoRelease<EditTextRange *>::~AutoRelease<EditTextRange *>(&v46);
      wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v47);
      goto LABEL_87;
    }
    v12 = 1843;
    goto LABEL_15;
  }
  memset_0(v69, 0, 0x5Cu);
  v10 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1), v69);
  v6 = v10;
  if ( v10 < 0 )
  {
    v12 = 1774;
    goto LABEL_15;
  }
  v17 = v69[0];
  if ( ((v69[0] & 0x40000000) != 0) != __OFSUB__(v69[0], -v69[0]) )
    v17 = -v69[0];
  v63 = v17;
  v60 = 0;
  v61 = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, int *))(**((_QWORD **)this + 1) + 112LL))(
          *((_QWORD *)this + 1),
          &v60,
          &v61);
  v6 = v10;
  if ( v10 < 0 )
  {
    v12 = 1780;
    goto LABEL_15;
  }
  v55 = v60 >= 0x80000;
  v56 = 0;
  v57 = 0;
  v58 = v61;
  v53 = 0;
  v18 = EditTextRange::GetHwnd(v4);
  v10 = Edit_LineFromChar_Timeout(v18, v14, (struct UIA_TIMEOUTDATA *)&v55, &v53);
  v6 = v10;
  if ( v10 < 0 )
  {
    v12 = 1787;
    goto LABEL_15;
  }
  v54 = 0;
  v19 = EditTextRange::GetHwnd(v4);
  v10 = Edit_LineFromChar_Timeout(v19, v15, (struct UIA_TIMEOUTDATA *)&v55, &v54);
  v6 = v10;
  if ( v10 < 0 )
  {
    v12 = 1790;
    goto LABEL_15;
  }
  for ( i = v53; ; ++i )
  {
    if ( i > v54 )
    {
      v2 = v64;
      goto LABEL_80;
    }
    v21 = v14;
    v62 = v14;
    v22 = v15;
    pvParam = v15;
    if ( i != v53 )
      break;
LABEL_51:
    if ( i != v54 )
    {
      v26 = EditTextRange::GetHwnd(v4);
      v27 = Edit_LineIndex_Timeout(v26, i + 1, (struct UIA_TIMEOUTDATA *)&v55, (int *)&pvParam);
      v6 = v27;
      if ( v27 < 0 )
      {
        v28 = 1807;
        goto LABEL_63;
      }
      v22 = pvParam - 1;
    }
    memset(&v67, 0, sizeof(v67));
    v45[0] = 0;
    *(_OWORD *)&v66.left = v68;
    v27 = EditTextRange::CalculateOneLineRangeRectangle(v4, v21, v22, v59, v63, (struct tagRECT *)&v66, &v67, v45);
    v6 = v27;
    if ( v27 < 0 )
    {
      v28 = 1813;
LABEL_63:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\editproxy.cpp",
        (const char *)(unsigned int)v27,
        v44);
      AutoRelease<EditTextRange *>::~AutoRelease<EditTextRange *>(&v46);
      wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v47);
      if ( Block && Block != v48 )
        operator delete(Block);
      v51.m256i_i32[0] = 0;
      goto LABEL_100;
    }
    if ( v45[0] )
      BasicArrayBuilder<UiaRect>::Add(&v48, &v67);
  }
  v23 = EditTextRange::GetHwnd(v4);
  v24 = Edit_LineIndex_Timeout(v23, i, (struct UIA_TIMEOUTDATA *)&v55, &v62);
  v25 = v24;
  if ( v24 >= 0 )
  {
    v21 = v62;
    goto LABEL_51;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x70B,
    (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\editproxy.cpp",
    (const char *)(unsigned int)v24,
    v44);
  AutoRelease<EditTextRange *>::~AutoRelease<EditTextRange *>(&v46);
  wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v47);
  if ( Block && Block != v48 )
    operator delete(Block);
  v51.m256i_i32[0] = 0;
  v6 = v25;
LABEL_100:
  Block = v48;
  v51.m256i_i64[1] = (__int64)v48;
LABEL_101:
  AutoDelete<EditBuffer *>::~AutoDelete<EditBuffer *>(&v59);
  return v6;
}

```

## disassembly

```asm
0x18008e890  mov     rax, rsp
0x18008e893  mov     [rax+18h], rbx
0x18008e897  push    rbp
0x18008e898  push    rsi
0x18008e899  push    rdi
0x18008e89a  push    r12
0x18008e89c  push    r13
0x18008e89e  push    r14
0x18008e8a0  push    r15
0x18008e8a2  lea     rbp, [rax-138h]
0x18008e8a9  sub     rsp, 200h
0x18008e8b0  movaps  xmmword ptr [rax-48h], xmm6
0x18008e8b4  mov     rax, cs:__security_cookie
0x18008e8bb  xor     rax, rsp
0x18008e8be  mov     [rbp+130h+var_50], rax
0x18008e8c5  mov     r12, rdx
0x18008e8c8  mov     [rbp+130h+var_170], rdx
0x18008e8cc  mov     rdi, rcx
0x18008e8cf  xor     r13d, r13d
0x18008e8d2  mov     [rdx], r13
0x18008e8d5  mov     [rbp+130h+var_188], r13
0x18008e8d9  lea     r14, [rcx-10h]
0x18008e8dd  mov     rcx, [r14+18h]
0x18008e8e1  mov     rax, [rcx]
0x18008e8e4  lea     rdx, [rbp+130h+var_188]
0x18008e8e8  mov     rax, [rax+28h]
0x18008e8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e8f1  mov     ebx, eax
0x18008e8f3  test    eax, eax
0x18008e8f5  jns     short loc_18008E8FE
0x18008e8f7  mov     edx, 67Fh
0x18008e8fc  jmp     short loc_18008E915
0x18008e8fe  mov     rdx, [rbp+130h+var_188]; struct EditBuffer *
0x18008e902  mov     rcx, r14; this
0x18008e905  call    ?ValidateEndpoints@EditTextRange@@AEAAJPEBVEditBuffer@@@Z; EditTextRange::ValidateEndpoints(EditBuffer const *)
0x18008e90a  mov     ebx, eax
0x18008e90c  test    eax, eax
0x18008e90e  jns     short loc_18008E930
0x18008e910  mov     edx, 680h; void *
0x18008e915  lea     r8, aOnecoreWindows_161; "onecore\\windows\\accessibletech\\uiaut"...
0x18008e91c  mov     r9d, eax; char *
0x18008e91f  mov     rcx, [rbp+138h]; this
0x18008e926  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e92b  jmp     loc_18008F015
0x18008e930  cmp     dword ptr [rdi+18h], 1
0x18008e934  jz      short loc_18008E951
0x18008e936  mov     eax, [rdi+14h]
0x18008e939  cmp     [rdi+10h], eax
0x18008e93c  jb      short loc_18008E951
0x18008e93e  mov     r9, r12
0x18008e941  xor     edx, edx
0x18008e943  xor     ecx, ecx
0x18008e945  call    ??$ArrayToSafeArray@N@@YAJPEBNHGPEAPEAUtagSAFEARRAY@@@Z; ArrayToSafeArray<double>(double const *,int,ushort,tagSAFEARRAY * *)
0x18008e94a  mov     ebx, eax
0x18008e94c  jmp     loc_18008F015
0x18008e951  mov     [rsp+230h+var_1D8], r13
0x18008e956  mov     dword ptr [rsp+230h+var_1D0], r13d
0x18008e95b  mov     [rsp+230h+Block], r13
0x18008e960  mov     dword ptr [rsp+230h+var_1C0], r13d
0x18008e965  xorps   xmm0, xmm0
0x18008e968  movdqu  xmmword ptr [rsp+230h+var_1C0+8], xmm0
0x18008e96e  xor     eax, eax
0x18008e970  mov     [rbp+130h+var_1A8], rax
0x18008e974  cmp     dword ptr [rdi+18h], 1
0x18008e978  jnz     short loc_18008E9BE
0x18008e97a  mov     rcx, r14; this
0x18008e97d  call    ?GetHwnd@EditTextRange@@AEAAPEAUHWND__@@XZ; EditTextRange::GetHwnd(void)
0x18008e982  mov     rbx, rax
0x18008e985  call    cs:__imp_GetFocus
0x18008e98b  cmp     rax, rbx
0x18008e98e  jnz     short loc_18008E9BE
0x18008e990  xorps   xmm0, xmm0
0x18008e993  movups  xmmword ptr [rbp+130h+var_160.left], xmm0
0x18008e997  movups  [rbp+130h+var_150], xmm0
0x18008e99b  lea     rdx, [rbp+130h+var_160]; struct UiaRect *
0x18008e99f  mov     rcx, r14; this
0x18008e9a2  call    ?_GetMSAACaretBoundsIntersect@EditTextRange@@AEAA_NPEAUUiaRect@@@Z; EditTextRange::_GetMSAACaretBoundsIntersect(UiaRect *)
0x18008e9a7  test    al, al
0x18008e9a9  jz      short loc_18008E9BE
0x18008e9ab  lea     rdx, [rbp+130h+var_160]
0x18008e9af  lea     rcx, [rsp+230h+var_1D8]
0x18008e9b4  call    ?Add@?$BasicArrayBuilder@UUiaRect@@@@QEAAJAEBUUiaRect@@@Z; BasicArrayBuilder<UiaRect>::Add(UiaRect const &)
0x18008e9b9  jmp     loc_18008EED0
0x18008e9be  mov     [rsp+230h+var_1E0], r13
0x18008e9c3  mov     [rsp+230h+var_1E8], r13
0x18008e9c8  mov     rcx, [rdi+8]
0x18008e9cc  mov     rax, [rcx]
0x18008e9cf  lea     rdx, [rsp+230h+var_1E0]
0x18008e9d4  mov     rax, [rax+58h]
0x18008e9d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e9dd  mov     ebx, eax
0x18008e9df  test    eax, eax
0x18008e9e1  jns     short loc_18008EA19
0x18008e9e3  mov     edx, 6B9h; void *
0x18008e9e8  lea     r8, aOnecoreWindows_161; "onecore\\windows\\accessibletech\\uiaut"...
0x18008e9ef  mov     r9d, eax; char *
0x18008e9f2  mov     rcx, [rbp+138h]; this
0x18008e9f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e9fe  nop
0x18008e9ff  lea     rcx, [rsp+230h+var_1E8]
0x18008ea04  call    ??1?$AutoRelease@PEAVEditTextRange@@@@QEAA@XZ; AutoRelease<EditTextRange *>::~AutoRelease<EditTextRange *>(void)
0x18008ea09  nop
0x18008ea0a  lea     rcx, [rsp+230h+var_1E0]; void *
0x18008ea0f  call    ??1?$com_ptr_t@UIAccessibleAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(void)
0x18008ea14  jmp     loc_18008EFEB
0x18008ea19  mov     rcx, [rsp+230h+var_1E0]
0x18008ea1e  test    rcx, rcx
0x18008ea21  jnz     short loc_18008EA33
0x18008ea23  mov     r9, r12
0x18008ea26  xor     edx, edx
0x18008ea28  xor     ecx, ecx
0x18008ea2a  call    ??$ArrayToSafeArray@N@@YAJPEBNHGPEAPEAUtagSAFEARRAY@@@Z; ArrayToSafeArray<double>(double const *,int,ushort,tagSAFEARRAY * *)
0x18008ea2f  mov     ebx, eax
0x18008ea31  jmp     short loc_18008E9FF
0x18008ea33  mov     rax, [rcx]
0x18008ea36  lea     r8, [rsp+230h+var_1E8]
0x18008ea3b  lea     rdx, _GUID_dc866705_ac34_41d4_a190_2059e0a16491
0x18008ea42  mov     rax, [rax]
0x18008ea45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ea4a  mov     ebx, eax
0x18008ea4c  test    eax, eax
0x18008ea4e  jns     short loc_18008EA57
0x18008ea50  mov     edx, 6C0h
0x18008ea55  jmp     short loc_18008E9E8
0x18008ea57  mov     rcx, r14; this
0x18008ea5a  call    ?GetHwnd@EditTextRange@@AEAAPEAUHWND__@@XZ; EditTextRange::GetHwnd(void)
0x18008ea5f  mov     rcx, rax; hWnd
0x18008ea62  mov     edx, 0FFFFFFECh; nIndex
0x18008ea67  call    cs:__imp_GetWindowLongPtrW
0x18008ea6d  bt      rax, 0Dh
0x18008ea72  mov     rax, [rsp+230h+var_1E8]
0x18008ea77  jb      short loc_18008EA92
0x18008ea79  mov     r15d, [rax+20h]
0x18008ea7d  cmp     [rdi+10h], r15d
0x18008ea81  cmovnb  r15d, [rdi+10h]
0x18008ea86  mov     esi, [rdi+14h]
0x18008ea89  cmp     esi, [rax+24h]
0x18008ea8c  cmovnb  esi, [rax+24h]
0x18008ea90  jmp     short loc_18008EAA9
0x18008ea92  mov     r15d, [rdi+10h]
0x18008ea96  mov     esi, [rax+24h]
0x18008ea99  cmp     [rdi+14h], esi
0x18008ea9c  cmovnb  esi, [rdi+14h]
0x18008eaa0  cmp     r15d, [rax+20h]
0x18008eaa4  cmovnb  r15d, [rax+20h]
0x18008eaa9  cmp     dword ptr [rdi+18h], 1
0x18008eaad  jz      short loc_18008EAC2
0x18008eaaf  lea     eax, [rsi-1]
0x18008eab2  test    esi, esi
0x18008eab4  cmovz   eax, esi
0x18008eab7  mov     esi, eax
0x18008eab9  cmp     r15d, eax
0x18008eabc  ja      loc_18008EA23
0x18008eac2  xorps   xmm0, xmm0
0x18008eac5  movups  [rbp+130h+var_120], xmm0
0x18008eac9  mov     rcx, [rdi+8]
0x18008eacd  mov     rax, [rcx]
0x18008ead0  lea     rdx, [rbp+130h+var_120]
0x18008ead4  mov     rax, [rax+68h]
0x18008ead8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eadd  mov     rcx, [rdi+8]
0x18008eae1  mov     rax, [rcx]
0x18008eae4  mov     rax, [rax+20h]
0x18008eae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eaed  test    al, al
0x18008eaef  jz      loc_18008ED82
0x18008eaf5  xor     edx, edx; Val
0x18008eaf7  lea     r8d, [rdx+5Ch]; Size
0x18008eafb  lea     rcx, [rbp+130h+var_110]; void *
0x18008eaff  call    memset_0
0x18008eb04  mov     rcx, [rdi+8]
0x18008eb08  mov     rax, [rcx]
0x18008eb0b  lea     rdx, [rbp+130h+var_110]
0x18008eb0f  mov     rax, [rax+50h]
0x18008eb13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eb18  mov     ebx, eax
0x18008eb1a  test    eax, eax
0x18008eb1c  jns     short loc_18008EB28
0x18008eb1e  mov     edx, 6EEh
0x18008eb23  jmp     loc_18008E9E8
0x18008eb28  mov     ecx, [rbp+130h+var_110]
0x18008eb2b  mov     eax, ecx
0x18008eb2d  neg     eax
0x18008eb2f  cmp     ecx, eax
0x18008eb31  cmovl   ecx, eax
0x18008eb34  mov     [rbp+130h+var_174], ecx
0x18008eb37  mov     [rbp+130h+var_180], r13d
0x18008eb3b  mov     [rbp+130h+var_17C], r13d
0x18008eb3f  mov     rcx, [rdi+8]
0x18008eb43  mov     rax, [rcx]
0x18008eb46  lea     r8, [rbp+130h+var_17C]
0x18008eb4a  lea     rdx, [rbp+130h+var_180]
0x18008eb4e  mov     rax, [rax+70h]
0x18008eb52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eb57  mov     ebx, eax
0x18008eb59  test    eax, eax
0x18008eb5b  jns     short loc_18008EB67
0x18008eb5d  mov     edx, 6F4h
0x18008eb62  jmp     loc_18008E9E8
0x18008eb67  cmp     [rbp+130h+var_180], 80000h
0x18008eb6e  setnb   [rbp+130h+var_190]
0x18008eb72  xor     eax, eax
0x18008eb74  mov     [rbp+130h+var_18F], ax
0x18008eb78  mov     [rbp+130h+var_18D], al
0x18008eb7b  mov     eax, [rbp+130h+var_17C]
0x18008eb7e  mov     [rbp+130h+var_18C], eax
0x18008eb81  mov     [rbp+130h+var_19C], r13d
0x18008eb85  mov     rcx, r14; this
0x18008eb88  call    ?GetHwnd@EditTextRange@@AEAAPEAUHWND__@@XZ; EditTextRange::GetHwnd(void)
0x18008eb8d  mov     rcx, rax; HWND
0x18008eb90  lea     r9, [rbp+130h+var_19C]; int *
0x18008eb94  lea     r8, [rbp+130h+var_190]; struct UIA_TIMEOUTDATA *
0x18008eb98  mov     edx, r15d; int
0x18008eb9b  call    ?Edit_LineFromChar_Timeout@@YAJPEAUHWND__@@HAEAUUIA_TIMEOUTDATA@@PEAH@Z; Edit_LineFromChar_Timeout(HWND__ *,int,UIA_TIMEOUTDATA &,int *)
0x18008eba0  mov     ebx, eax
0x18008eba2  test    eax, eax
0x18008eba4  jns     short loc_18008EBB0
0x18008eba6  mov     edx, 6FBh
0x18008ebab  jmp     loc_18008E9E8
0x18008ebb0  mov     [rbp+130h+var_198], r13d
0x18008ebb4  mov     rcx, r14; this
0x18008ebb7  call    ?GetHwnd@EditTextRange@@AEAAPEAUHWND__@@XZ; EditTextRange::GetHwnd(void)
0x18008ebbc  mov     rcx, rax; HWND
0x18008ebbf  lea     r9, [rbp+130h+var_198]; int *
0x18008ebc3  lea     r8, [rbp+130h+var_190]; struct UIA_TIMEOUTDATA *
0x18008ebc7  mov     edx, esi; int
0x18008ebc9  call    ?Edit_LineFromChar_Timeout@@YAJPEAUHWND__@@HAEAUUIA_TIMEOUTDATA@@PEAH@Z; Edit_LineFromChar_Timeout(HWND__ *,int,UIA_TIMEOUTDATA &,int *)
0x18008ebce  mov     ebx, eax
0x18008ebd0  test    eax, eax
0x18008ebd2  jns     short loc_18008EBDE
0x18008ebd4  mov     edx, 6FEh
0x18008ebd9  jmp     loc_18008E9E8
0x18008ebde  mov     r13d, [rbp+130h+var_19C]
0x18008ebe2  cmp     r13d, [rbp+130h+var_198]
0x18008ebe6  jg      loc_18008EE4A
0x18008ebec  mov     r12d, r15d
0x18008ebef  mov     [rbp+130h+var_178], r15d
0x18008ebf3  mov     ebx, esi
0x18008ebf5  mov     [rbp+130h+pvParam], ebx
0x18008ebf8  cmp     r13d, [rbp+130h+var_19C]
0x18008ebfc  jz      short loc_18008EC28
0x18008ebfe  mov     rcx, r14; this
0x18008ec01  call    ?GetHwnd@EditTextRange@@AEAAPEAUHWND__@@XZ; EditTextRange::GetHwnd(void)
0x18008ec06  mov     rcx, rax; HWND
0x18008ec09  lea     r9, [rbp+130h+var_178]; int *
0x18008ec0d  lea     r8, [rbp+130h+var_190]; struct UIA_TIMEOUTDATA *
0x18008ec11  mov     edx, r13d; int
0x18008ec14  call    ?Edit_LineIndex_Timeout@@YAJPEAUHWND__@@HAEAUUIA_TIMEOUTDATA@@PEAH@Z; Edit_LineIndex_Timeout(HWND__ *,int,UIA_TIMEOUTDATA &,int *)
0x18008ec19  mov     r12d, eax
0x18008ec1c  test    eax, eax
0x18008ec1e  js      loc_18008ECCE
0x18008ec24  mov     r12d, [rbp+130h+var_178]
0x18008ec28  cmp     r13d, [rbp+130h+var_198]
0x18008ec2c  jz      short loc_18008EC59
0x18008ec2e  mov     rcx, r14; this
0x18008ec31  call    ?GetHwnd@EditTextRange@@AEAAPEAUHWND__@@XZ; EditTextRange::GetHwnd(void)
0x18008ec36  mov     rcx, rax; HWND
0x18008ec39  lea     r9, [rbp+130h+pvParam]; int *
0x18008ec3d  lea     r8, [rbp+130h+var_190]; struct UIA_TIMEOUTDATA *
0x18008ec41  lea     edx, [r13+1]; int
0x18008ec45  call    ?Edit_LineIndex_Timeout@@YAJPEAUHWND__@@HAEAUUIA_TIMEOUTDATA@@PEAH@Z; Edit_LineIndex_Timeout(HWND__ *,int,UIA_TIMEOUTDATA &,int *)
0x18008ec4a  mov     ebx, eax
0x18008ec4c  test    eax, eax
0x18008ec4e  js      loc_18008ED26
0x18008ec54  mov     ebx, [rbp+130h+pvParam]
0x18008ec57  dec     ebx
0x18008ec59  xorps   xmm0, xmm0
0x18008ec5c  movups  xmmword ptr [rbp+130h+var_140.left], xmm0
0x18008ec60  movups  xmmword ptr [rbp+130h+var_140.width], xmm0
0x18008ec64  mov     [rsp+230h+var_1F0], 0
0x18008ec69  movaps  xmm0, [rbp+130h+var_120]
0x18008ec6d  movdqa  xmmword ptr [rbp+130h+var_160.left], xmm0
0x18008ec72  lea     rax, [rsp+230h+var_1F0]
0x18008ec77  mov     [rsp+230h+var_1F8], rax; bool *
0x18008ec7c  lea     rax, [rbp+130h+var_140]
0x18008ec80  mov     [rsp+230h+var_200], rax; struct UiaRect *
0x18008ec85  lea     rax, [rbp+130h+var_160]
0x18008ec89  mov     [rsp+230h+var_208], rax; struct tagRECT
0x18008ec8e  mov     eax, [rbp+130h+var_174]
0x18008ec91  mov     [rsp+230h+var_210], eax; unsigned int
0x18008ec95  mov     r9, [rbp+130h+var_188]; struct EditBuffer *
0x18008ec99  mov     r8d, ebx; unsigned int
0x18008ec9c  mov     edx, r12d; unsigned int
0x18008ec9f  mov     rcx, r14; this
0x18008eca2  call    ?CalculateOneLineRangeRectangle@EditTextRange@@AEAAJKKPEBVEditBuffer@@IUtagRECT@@PEAUUiaRect@@PEA_N@Z; EditTextRange::CalculateOneLineRangeRectangle(ulong,ulong,EditBuffer const *,uint,tagRECT,UiaRect *,bool *)
0x18008eca7  mov     ebx, eax
0x18008eca9  test    eax, eax
0x18008ecab  js      loc_18008ED7B
0x18008ecb1  cmp     [rsp+230h+var_1F0], 0
0x18008ecb6  jz      short loc_18008ECC6
0x18008ecb8  lea     rdx, [rbp+130h+var_140]
0x18008ecbc  lea     rcx, [rsp+230h+var_1D8]
0x18008ecc1  call    ?Add@?$BasicArrayBuilder@UUiaRect@@@@QEAAJAEBUUiaRect@@@Z; BasicArrayBuilder<UiaRect>::Add(UiaRect const &)
0x18008ecc6  inc     r13d
0x18008ecc9  jmp     loc_18008EBE2
0x18008ecce  mov     rcx, [rbp+138h]; this
0x18008ecd5  mov     r9d, r12d; char *
0x18008ecd8  lea     r8, aOnecoreWindows_161; "onecore\\windows\\accessibletech\\uiaut"...
0x18008ecdf  mov     edx, 70Bh; void *
0x18008ece4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
