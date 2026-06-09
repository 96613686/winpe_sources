# _anonymous_namespace_::GetHwndDescendantsWorker

- ea: `0x1800403a8`
- end: `0x180040613`
- name: `_anonymous_namespace_::GetHwndDescendantsWorker`
- size: `619`
- prototype: `__int64 __fastcall(LPARAM lParam, HWND hWndParent)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800402e0`
- `0x18007b4b0`

## callees

- `0x18000d260`
- `0x18001aef0`
- `0x18001bb34`
- `0x18002a514`
- `0x1800403a8`
- `0x180077e8c`
- `0x18007af84`
- `0x18007b4b0`
- `0x18007b65c`
- `0x18007c1a8`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!GetDesktopWindow` at `0x1800403f1`
- `ext-ms-win-ntuser-window-l1-1-0!GetDesktopWindow` at `0x1800403f1`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!EnumChildWindows` at `0x18004046a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!EnumChildWindows` at `0x180040494`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!EnumChildWindows` at `0x18004052f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!EnumChildWindows` at `0x18004046a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!EnumChildWindows` at `0x180040494`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!EnumChildWindows` at `0x18004052f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!EnumWindows` at `0x18004040a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!EnumWindows` at `0x1800404b5`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!EnumWindows` at `0x18004040a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!EnumWindows` at `0x1800404b5`

## string_xrefs

- `0x180040418`: `onecore\windows\accessibletech\common\basichwndutils.cpp`
- `0x1800404c3`: `onecore\windows\accessibletech\common\basichwndutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall anonymous_namespace_::GetHwndDescendantsWorker(_QWORD *lParam, HWND hWndParent)
{
  _QWORD *v4; // rsi
  const char *v5; // r9
  __int128 i; // rdi
  __int64 v7; // rdx
  const char *v8; // r9
  HWND *j; // rdi
  HWND *v10; // r15
  __int64 OwnedDescendants; // rax
  _QWORD *v12; // r14
  _QWORD *k; // rdi
  LPARAM lParama[2]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v16; // [rsp+48h] [rbp-38h]
  __int128 v17; // [rsp+50h] [rbp-30h] BYREF
  __int64 v18; // [rsp+60h] [rbp-20h]
  _BYTE v19[24]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  char v21; // [rsp+B8h] [rbp+38h] BYREF

  *lParam = 0;
  v4 = lParam + 1;
  lParam[1] = 0;
  lParam[2] = 0;
  if ( hWndParent == GetDesktopWindow() )
  {
    if ( !EnumWindows(anonymous_namespace_::GetHwndDescendantsEnumWindowsProc, (LPARAM)lParam) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x572,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
        v5);
    v17 = 0;
    v18 = 0;
    std::vector<HWND__ *>::_Construct_n<HWND__ * * const &,HWND__ * * const &>(
      &v17,
      (__int64)(*v4 - *lParam) >> 3,
      lParam,
      v4);
    for ( i = v17; (_QWORD)i != *((_QWORD *)&i + 1); *(_QWORD *)&i = i + 8 )
      EnumChildWindows(*(HWND *)i, anonymous_namespace_::GetHwndDescendantsEnumWindowsProc, (LPARAM)lParam);
    std::vector<ViewIdInfo>::_Tidy(&v17);
  }
  else
  {
    EnumChildWindows(hWndParent, anonymous_namespace_::GetHwndDescendantsEnumWindowsProc, (LPARAM)lParam);
    *(_OWORD *)lParama = 0;
    v16 = 0;
    if ( !EnumWindows(anonymous_namespace_::GetOwnedWindowsEnumWindowsProc, (LPARAM)lParama) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x58F,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
        v8);
    if ( lParama[0] != lParama[1] )
    {
      anonymous_namespace_::GetOwnedDescendants(&v17, hWndParent, lParam, lParama);
      while ( (_QWORD)v17 != *((_QWORD *)&v17 + 1) )
      {
        std::vector<HWND__ *>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<HWND__ *>>>,0>(
          (_DWORD)lParam,
          (unsigned int)&v21,
          *v4,
          v17,
          *((__int64 *)&v17 + 1));
        v10 = (HWND *)*((_QWORD *)&v17 + 1);
        for ( j = (HWND *)v17; j != v10; ++j )
          EnumChildWindows(*j, anonymous_namespace_::GetHwndDescendantsEnumWindowsProc, (LPARAM)lParam);
        OwnedDescendants = anonymous_namespace_::GetOwnedDescendants(v19, 0, &v17, lParama);
        std::vector<HWND__ *>::operator=(&v17, OwnedDescendants);
        std::vector<ViewIdInfo>::_Tidy(v19);
      }
      std::vector<ViewIdInfo>::_Tidy(&v17);
    }
    LOBYTE(v7) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_XamlWebView2UiaEventSupport>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_XamlWebView2UiaEventSupport>::GetImpl'::`2'::impl,
      v7);
    v17 = 0;
    v18 = 0;
    anonymous_namespace_::GetComponentUiDescendants(hWndParent, &v17);
    v12 = (_QWORD *)*v4;
    for ( k = (_QWORD *)*lParam; k != v12; ++k )
      anonymous_namespace_::GetComponentUiDescendants(*k, &v17);
    std::vector<HWND__ *>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<HWND__ *>>>,0>(
      (_DWORD)lParam,
      (unsigned int)&v21,
      *v4,
      v17,
      *((__int64 *)&v17 + 1));
    std::vector<ViewIdInfo>::_Tidy(&v17);
    if ( lParama[0] )
      std::_Deallocate<16>(lParama[0], (v16 - lParama[0]) & 0xFFFFFFFFFFFFFFF0uLL);
  }
  return lParam;
}

```

## disassembly

```asm
0x1800403a8  mov     [rsp-28h+arg_10], rbx
0x1800403ad  mov     [rsp-28h+arg_0], rcx
0x1800403b2  push    rbp
0x1800403b3  push    rsi
0x1800403b4  push    rdi
0x1800403b5  push    r14
0x1800403b7  push    r15
0x1800403b9  mov     rbp, rsp
0x1800403bc  sub     rsp, 80h
0x1800403c3  mov     r14, rdx
0x1800403c6  mov     rbx, rcx
0x1800403c9  mov     [rbp+var_50], 0
0x1800403d0  mov     qword ptr [rcx], 0
0x1800403d7  lea     rsi, [rcx+8]
0x1800403db  mov     qword ptr [rsi], 0
0x1800403e2  mov     qword ptr [rcx+10h], 0
0x1800403ea  mov     [rbp+var_50], 1
0x1800403f1  call    cs:__imp_GetDesktopWindow
0x1800403f7  cmp     r14, rax
0x1800403fa  jnz     loc_180040487
0x180040400  mov     rdx, rbx; lParam
0x180040403  lea     rcx, _anonymous_namespace___GetHwndDescendantsEnumWindowsProc; lpEnumFunc
0x18004040a  call    cs:__imp_EnumWindows
0x180040410  test    eax, eax
0x180040412  jnz     short loc_18004042A
0x180040414  mov     rcx, [rbp+28h]; this
0x180040418  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x18004041f  mov     edx, 572h; void *
0x180040424  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18004042a  xorps   xmm0, xmm0
0x18004042d  movdqu  [rbp+var_30], xmm0
0x180040432  mov     [rbp+var_20], 0
0x18004043a  mov     rdx, [rsi]
0x18004043d  sub     rdx, [rbx]
0x180040440  sar     rdx, 3
0x180040444  mov     r9, rsi
0x180040447  mov     r8, rbx
0x18004044a  lea     rcx, [rbp+var_30]
0x18004044e  call    ??$_Construct_n@AEBQEAPEAUHWND__@@AEBQEAPEAU1@@?$vector@PEAUHWND__@@V?$allocator@PEAUHWND__@@@std@@@std@@AEAAX_KAEBQEAPEAUHWND__@@1@Z; std::vector<HWND__ *>::_Construct_n<HWND__ * * const &,HWND__ * * const &>(unsigned __int64,HWND__ * * const &,HWND__ * * const &)
0x180040453  mov     rdi, qword ptr [rbp+var_30]
0x180040457  mov     rsi, qword ptr [rbp+var_30+8]
0x18004045b  jmp     short loc_180040474
0x18004045d  mov     r8, rbx; lParam
0x180040460  lea     rdx, _anonymous_namespace___GetHwndDescendantsEnumWindowsProc; lpEnumFunc
0x180040467  mov     rcx, [rdi]; hWndParent
0x18004046a  call    cs:__imp_EnumChildWindows
0x180040470  add     rdi, 8
0x180040474  cmp     rdi, rsi
0x180040477  jnz     short loc_18004045D
0x180040479  lea     rcx, [rbp+var_30]
0x18004047d  call    ?_Tidy@?$vector@UViewIdInfo@@V?$allocator@UViewIdInfo@@@std@@@std@@AEAAXXZ; std::vector<ViewIdInfo>::_Tidy(void)
0x180040482  jmp     loc_1800405F8
0x180040487  mov     r8, rbx; lParam
0x18004048a  lea     rdx, _anonymous_namespace___GetHwndDescendantsEnumWindowsProc; lpEnumFunc
0x180040491  mov     rcx, r14; hWndParent
0x180040494  call    cs:__imp_EnumChildWindows
0x18004049a  xorps   xmm0, xmm0
0x18004049d  movdqu  xmmword ptr [rbp+lParam], xmm0
0x1800404a2  mov     [rbp+var_38], 0
0x1800404aa  lea     rdx, [rbp+lParam]; lParam
0x1800404ae  lea     rcx, _anonymous_namespace___GetOwnedWindowsEnumWindowsProc; lpEnumFunc
0x1800404b5  call    cs:__imp_EnumWindows
0x1800404bb  mov     rcx, [rbp+28h]; this
0x1800404bf  test    eax, eax
0x1800404c1  jnz     short loc_1800404D5
0x1800404c3  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x1800404ca  mov     edx, 58Fh; void *
0x1800404cf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800404d5  mov     rax, [rbp+lParam+8]
0x1800404d9  cmp     [rbp+lParam], rax
0x1800404dd  jz      loc_180040571
0x1800404e3  lea     r9, [rbp+lParam]
0x1800404e7  mov     r8, rbx
0x1800404ea  mov     rdx, r14
0x1800404ed  lea     rcx, [rbp+var_30]
0x1800404f1  call    _anonymous_namespace___GetOwnedDescendants
0x1800404f6  nop
0x1800404f7  mov     rax, qword ptr [rbp+var_30+8]
0x1800404fb  mov     r9, qword ptr [rbp+var_30]
0x1800404ff  cmp     r9, rax
0x180040502  jz      short loc_180040568
0x180040504  mov     [rsp+80h+var_60], rax
0x180040509  mov     r8, [rsi]
0x18004050c  lea     rdx, [rbp+arg_8]
0x180040510  mov     rcx, rbx
0x180040513  call    ??$insert@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAUHWND__@@@std@@@std@@@std@@$0A@@?$vector@PEAUHWND__@@V?$allocator@PEAUHWND__@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAUHWND__@@@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@PEAUHWND__@@@std@@@std@@@1@V21@1@Z; std::vector<HWND__ *>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<HWND__ *>>>,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<HWND__ *>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<HWND__ *>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<HWND__ *>>>)
0x180040518  mov     rdi, qword ptr [rbp+var_30]
0x18004051c  mov     r15, qword ptr [rbp+var_30+8]
0x180040520  jmp     short loc_180040539
0x180040522  mov     r8, rbx; lParam
0x180040525  lea     rdx, _anonymous_namespace___GetHwndDescendantsEnumWindowsProc; lpEnumFunc
0x18004052c  mov     rcx, [rdi]; hWndParent
0x18004052f  call    cs:__imp_EnumChildWindows
0x180040535  add     rdi, 8
0x180040539  cmp     rdi, r15
0x18004053c  jnz     short loc_180040522
0x18004053e  lea     r9, [rbp+lParam]
0x180040542  lea     r8, [rbp+var_30]
0x180040546  xor     edx, edx
0x180040548  lea     rcx, [rbp+var_18]
0x18004054c  call    _anonymous_namespace___GetOwnedDescendants
0x180040551  mov     rdx, rax
0x180040554  lea     rcx, [rbp+var_30]
0x180040558  call    ??4?$vector@PEAUHWND__@@V?$allocator@PEAUHWND__@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<HWND__ *>::operator=(std::vector<HWND__ *> &&)
0x18004055d  lea     rcx, [rbp+var_18]
0x180040561  call    ?_Tidy@?$vector@UViewIdInfo@@V?$allocator@UViewIdInfo@@@std@@@std@@AEAAXXZ; std::vector<ViewIdInfo>::_Tidy(void)
0x180040566  jmp     short loc_1800404F7
0x180040568  lea     rcx, [rbp+var_30]
0x18004056c  call    ?_Tidy@?$vector@UViewIdInfo@@V?$allocator@UViewIdInfo@@@std@@@std@@AEAAXXZ; std::vector<ViewIdInfo>::_Tidy(void)
0x180040571  mov     dl, 1
0x180040573  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_XamlWebView2UiaEventSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_XamlWebView2UiaEventSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_XamlWebView2UiaEventSupport> `wil::Feature<__WilFeatureTraits_Feature_XamlWebView2UiaEventSupport>::GetImpl(void)'::`2'::impl
0x18004057a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_XamlWebView2UiaEventSupport@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_XamlWebView2UiaEventSupport>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004057f  xorps   xmm0, xmm0
0x180040582  movdqu  [rbp+var_30], xmm0
0x180040587  mov     [rbp+var_20], 0
0x18004058f  lea     rdx, [rbp+var_30]
0x180040593  mov     rcx, r14
0x180040596  call    _anonymous_namespace___GetComponentUiDescendants
0x18004059b  mov     r14, [rsi]
0x18004059e  mov     rdi, [rbx]
0x1800405a1  jmp     short loc_1800405B3
0x1800405a3  lea     rdx, [rbp+var_30]
0x1800405a7  mov     rcx, [rdi]
0x1800405aa  call    _anonymous_namespace___GetComponentUiDescendants
0x1800405af  add     rdi, 8
0x1800405b3  cmp     rdi, r14
0x1800405b6  jnz     short loc_1800405A3
0x1800405b8  mov     rax, qword ptr [rbp+var_30+8]
0x1800405bc  mov     [rsp+80h+var_60], rax
0x1800405c1  mov     r9, qword ptr [rbp+var_30]
0x1800405c5  mov     r8, [rsi]
0x1800405c8  lea     rdx, [rbp+arg_8]
0x1800405cc  mov     rcx, rbx
0x1800405cf  call    ??$insert@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAUHWND__@@@std@@@std@@@std@@$0A@@?$vector@PEAUHWND__@@V?$allocator@PEAUHWND__@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAUHWND__@@@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@PEAUHWND__@@@std@@@std@@@1@V21@1@Z; std::vector<HWND__ *>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<HWND__ *>>>,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<HWND__ *>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<HWND__ *>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<HWND__ *>>>)
0x1800405d4  nop
0x1800405d5  lea     rcx, [rbp+var_30]
0x1800405d9  call    ?_Tidy@?$vector@UViewIdInfo@@V?$allocator@UViewIdInfo@@@std@@@std@@AEAAXXZ; std::vector<ViewIdInfo>::_Tidy(void)
0x1800405de  nop
0x1800405df  mov     rcx, [rbp+lParam]
0x1800405e3  test    rcx, rcx
0x1800405e6  jz      short loc_1800405F8
0x1800405e8  mov     rdx, [rbp+var_38]
0x1800405ec  sub     rdx, rcx
0x1800405ef  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800405f3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800405f8  mov     rax, rbx
0x1800405fb  mov     rbx, [rsp+80h+arg_10]
0x180040603  add     rsp, 80h
0x18004060a  pop     r15
0x18004060c  pop     r14
0x18004060e  pop     rdi
0x18004060f  pop     rsi
0x180040610  pop     rbp
0x180040611  retn
```
