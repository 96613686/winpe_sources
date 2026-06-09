# BasicHwndUtils::GetPropertyValue(HWND__ *,int,UIA_TIMEOUTDATA &,tagVARIANT *)

- ea: `0x1800234f0`
- end: `0x18002381f`
- name: `?GetPropertyValue@BasicHwndUtils@@SAJPEAUHWND__@@HAEAUUIA_TIMEOUTDATA@@PEAUtagVARIANT@@@Z`
- size: `815`
- prototype: `__int64 __fastcall(HWND hwnd, int, struct UIA_TIMEOUTDATA *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180023450`

## callees

- `0x1800109bc`
- `0x180012484`
- `0x1800234f0`
- `0x180023828`
- `0x180023a90`
- `0x180024794`
- `0x180031540`
- `0x180038c40`
- `0x180043180`
- `0x180043680`
- `0x1800441ac`
- `0x18007bd94`
- `0x18007bed4`
- `0x18007bf68`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800237e2`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800237e2`
- `OLEAUT32!__imp_VariantInit` at `0x18002351f`
- `OLEAUT32!__imp_VariantInit` at `0x18002351f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x1800235c7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x1800235c7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x180023643`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x1800237bb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x180023643`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x1800237bb`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x1800237cd`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x1800237cd`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800236c8`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800236c8`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetGUIThreadInfo` at `0x180023706`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetGUIThreadInfo` at `0x180023706`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsChild` at `0x18002371d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsChild` at `0x18002371d`

## string_xrefs

- `0x180023582`: `onecore\windows\accessibletech\common\basichwndutils.cpp`
- `0x18002368a`: `onecore\windows\accessibletech\common\basichwndutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall BasicHwndUtils::GetPropertyValue(
        HWND hwnd,
        unsigned int a2,
        struct UIA_TIMEOUTDATA *a3,
        struct tagVARIANT *a4)
{
  int WinFormsId; // eax
  unsigned int WindowLongW; // eax
  LONGLONG *bstr; // rax
  LONGLONG v12; // rcx
  WCHAR *v13; // rdx
  int WindowTextAsBstr; // eax
  bool v15; // cf
  int v16; // ebx
  int IsWinFormsControl; // eax
  LONGLONG *v18; // rax
  LONGLONG v19; // rcx
  int IsWindowPatternWindow; // eax
  DWORD dwProcessId[4]; // [rsp+20h] [rbp-198h] BYREF
  tagGUITHREADINFO pgui; // [rsp+30h] [rbp-188h] BYREF
  WCHAR ClassName[128]; // [rsp+80h] [rbp-138h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  VariantInit(a4);
  if ( (int *)_std_find_trivial_4(";u", &dword_1800A2DF4, a2) == &dword_1800A2DF4 )
    return 0;
  if ( a2 == 30011 )
  {
    if ( (unsigned int)BasicHwndUtils::IsWinFormsControl(hwnd) )
    {
      WinFormsId = BasicHwndUtils::GetWinFormsId(hwnd, a3, &a4->bstrVal);
      if ( WinFormsId < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x24F,
          (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
          (const char *)(unsigned int)WinFormsId,
          dwProcessId[0]);
      if ( a4->llVal )
        a4->vt = 8;
    }
    if ( !a4->vt && !(unsigned int)BasicHwndUtils::IsTopLevelWindow(hwnd) )
    {
      WindowLongW = GetWindowLongW(hwnd, -12);
      if ( WindowLongW )
      {
        if ( WindowLongW != -1 && (int)StringCchPrintfW((unsigned __int16 *)&pgui, 0x20u, L"%d", WindowLongW) >= 0 )
        {
          bstr = (LONGLONG *)wil::make_bstr(dwProcessId, &pgui);
          v12 = *bstr;
          *bstr = 0;
          a4->llVal = v12;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(dwProcessId);
          a4->vt = 8;
        }
      }
    }
    return 0;
  }
  if ( a2 != 30012 )
  {
    switch ( a2 )
    {
      case 0x7535u:
        WindowTextAsBstr = BasicHwndUtils::GetWindowTextAsBstr(hwnd, a3, &a4->bstrVal);
        if ( WindowTextAsBstr < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x273,
            (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
            (const char *)(unsigned int)WindowTextAsBstr,
            dwProcessId[0]);
        goto LABEL_35;
      case 0x753Au:
        v15 = (unsigned int)BasicHwndUtils::IsWindowReallyEnabled(hwnd) != 0;
        break;
      case 0x7532u:
        dwProcessId[0] = 0;
        GetWindowThreadProcessId(hwnd, dwProcessId);
        a4->vt = 3;
        a4->lVal = dwProcessId[0];
        return 0;
      case 0x7538u:
        v16 = 0;
        memset_0(&pgui, 0, sizeof(pgui));
        pgui.cbSize = 72;
        if ( GetGUIThreadInfo(0, &pgui) && (pgui.hwndFocus == hwnd || IsChild(hwnd, pgui.hwndFocus)) )
          v16 = 1;
        v15 = v16 != 0;
        break;
      case 0x7548u:
        IsWinFormsControl = BasicHwndUtils::IsWinFormsControl(hwnd);
        v13 = L"WinForm";
        if ( !IsWinFormsControl )
          v13 = L"Win32";
        goto LABEL_34;
      case 0x7533u:
        IsWindowPatternWindow = BasicHwndUtils::IsWindowPatternWindow(hwnd);
        a4->vt = 3;
        a4->lVal = 50033 - (IsWindowPatternWindow != 0);
        return 0;
      default:
        if ( a2 != 30174 || !GetClassNameW(hwnd, ClassName, 128) )
          return 0;
        CharLowerW(ClassName);
        v15 = wcsstr(ClassName, L"dialog") != 0;
        break;
    }
    a4->vt = 11;
    a4->iVal = -v15;
    return 0;
  }
  if ( GetClassNameW(hwnd, ClassName, 128) )
  {
    v13 = ClassName;
LABEL_34:
    v18 = (LONGLONG *)wil::make_bstr(dwProcessId, v13);
    v19 = *v18;
    *v18 = 0;
    a4->llVal = v19;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(dwProcessId);
LABEL_35:
    a4->vt = 8;
  }
  return 0;
}

```

## disassembly

```asm
0x1800234f0  push    rbx
0x1800234f2  push    rsi
0x1800234f3  push    rdi
0x1800234f4  push    r14
0x1800234f6  push    r15
0x1800234f8  sub     rsp, 190h
0x1800234ff  mov     rax, cs:__security_cookie
0x180023506  xor     rax, rsp
0x180023509  mov     [rsp+1B8h+var_38], rax
0x180023511  mov     rdi, r9
0x180023514  mov     r15, r8
0x180023517  mov     ebx, edx
0x180023519  mov     r14, rcx
0x18002351c  mov     rcx, r9; pvarg
0x18002351f  call    cs:__imp_VariantInit
0x180023525  mov     r8d, ebx
0x180023528  lea     rsi, dword_1800A2DF4
0x18002352f  mov     rdx, rsi
0x180023532  lea     rcx, ?s_hwndProvidedProperties@BasicHwndUtils@@2V?$array@H$08@std@@B; ";u"
0x180023539  call    __std_find_trivial_4
0x18002353e  cmp     rax, rsi
0x180023541  jnz     short loc_18002354A
0x180023543  xor     eax, eax
0x180023545  jmp     loc_1800237FF
0x18002354a  cmp     ebx, 753Bh
0x180023550  jnz     loc_18002362A
0x180023556  mov     rcx, r14; hWnd
0x180023559  call    ?IsWinFormsControl@BasicHwndUtils@@SAHPEAUHWND__@@@Z; BasicHwndUtils::IsWinFormsControl(HWND__ *)
0x18002355e  xor     ebx, ebx
0x180023560  test    eax, eax
0x180023562  jz      short loc_1800235A3
0x180023564  lea     r8, [rdi+8]; unsigned __int16 **
0x180023568  mov     rdx, r15; struct UIA_TIMEOUTDATA *
0x18002356b  mov     rcx, r14; HWND
0x18002356e  call    ?GetWinFormsId@BasicHwndUtils@@SAJPEAUHWND__@@AEAUUIA_TIMEOUTDATA@@PEAPEAG@Z; BasicHwndUtils::GetWinFormsId(HWND__ *,UIA_TIMEOUTDATA &,ushort * *)
0x180023573  mov     rcx, [rsp+1B8h]; this
0x18002357b  test    eax, eax
0x18002357d  jns     short loc_180023593
0x18002357f  mov     r9d, eax; char *
0x180023582  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x180023589  mov     edx, 24Fh; void *
0x18002358e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023593  cmp     [rdi+8], rbx
0x180023597  jz      short loc_1800235A3
0x180023599  mov     esi, 8
0x18002359e  mov     [rdi], si
0x1800235a1  jmp     short loc_1800235A8
0x1800235a3  mov     esi, 8
0x1800235a8  cmp     [rdi], bx
0x1800235ab  jnz     loc_1800237F7
0x1800235b1  mov     rcx, r14; HWND
0x1800235b4  call    ?IsTopLevelWindow@BasicHwndUtils@@SAHPEAUHWND__@@@Z; BasicHwndUtils::IsTopLevelWindow(HWND__ *)
0x1800235b9  test    eax, eax
0x1800235bb  jnz     loc_1800237F7
0x1800235c1  lea     edx, [rax-0Ch]; nIndex
0x1800235c4  mov     rcx, r14; hWnd
0x1800235c7  call    cs:__imp_GetWindowLongW
0x1800235cd  test    eax, eax
0x1800235cf  jz      loc_1800237F7
0x1800235d5  cmp     eax, 0FFFFFFFFh
0x1800235d8  jz      loc_1800237F7
0x1800235de  mov     r9d, eax
0x1800235e1  lea     r8, aD; "%d"
0x1800235e8  mov     edx, 20h ; ' '; unsigned __int64
0x1800235ed  lea     rcx, [rsp+1B8h+pgui]; unsigned __int16 *
0x1800235f2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800235f7  test    eax, eax
0x1800235f9  js      loc_1800237F7
0x1800235ff  lea     rdx, [rsp+1B8h+pgui]
0x180023604  lea     rcx, [rsp+1B8h+dwProcessId]
0x180023609  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18002360e  mov     rcx, [rax]
0x180023611  mov     [rax], rbx
0x180023614  mov     [rdi+8], rcx
0x180023618  lea     rcx, [rsp+1B8h+dwProcessId]
0x18002361d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180023622  mov     [rdi], si
0x180023625  jmp     loc_1800237F7
0x18002362a  cmp     ebx, 753Ch
0x180023630  jnz     short loc_180023660
0x180023632  mov     r8d, 80h; nMaxCount
0x180023638  lea     rdx, [rsp+1B8h+ClassName]; lpClassName
0x180023640  mov     rcx, r14; hWnd
0x180023643  call    cs:__imp_GetClassNameW
0x180023649  xor     ebx, ebx
0x18002364b  test    eax, eax
0x18002364d  jz      loc_1800237F7
0x180023653  lea     rdx, [rsp+1B8h+ClassName]
0x18002365b  jmp     loc_180023759
0x180023660  cmp     ebx, 7535h
0x180023666  jnz     short loc_18002369B
0x180023668  lea     r8, [rdi+8]; unsigned __int16 **
0x18002366c  mov     rdx, r15; struct UIA_TIMEOUTDATA *
0x18002366f  mov     rcx, r14; HWND
0x180023672  call    ?GetWindowTextAsBstr@BasicHwndUtils@@SAJPEAUHWND__@@AEAUUIA_TIMEOUTDATA@@PEAPEAG@Z; BasicHwndUtils::GetWindowTextAsBstr(HWND__ *,UIA_TIMEOUTDATA &,ushort * *)
0x180023677  mov     rcx, [rsp+1B8h]; this
0x18002367f  test    eax, eax
0x180023681  jns     loc_180023777
0x180023687  mov     r9d, eax; char *
0x18002368a  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x180023691  mov     edx, 273h; void *
0x180023696  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002369b  cmp     ebx, 753Ah
0x1800236a1  jnz     short loc_1800236B2
0x1800236a3  mov     rcx, r14; hwnd
0x1800236a6  call    ?IsWindowReallyEnabled@BasicHwndUtils@@SAHPEAUHWND__@@@Z; BasicHwndUtils::IsWindowReallyEnabled(HWND__ *)
0x1800236ab  neg     eax
0x1800236ad  jmp     loc_1800237EB
0x1800236b2  cmp     ebx, 7532h
0x1800236b8  jnz     short loc_1800236DF
0x1800236ba  xor     ebx, ebx
0x1800236bc  mov     [rsp+1B8h+dwProcessId], ebx
0x1800236c0  lea     rdx, [rsp+1B8h+dwProcessId]; lpdwProcessId
0x1800236c5  mov     rcx, r14; hWnd
0x1800236c8  call    cs:__imp_GetWindowThreadProcessId
0x1800236ce  mov     word ptr [rdi], 3
0x1800236d3  mov     eax, [rsp+1B8h+dwProcessId]
0x1800236d7  mov     [rdi+8], eax
0x1800236da  jmp     loc_1800237F7
0x1800236df  cmp     ebx, 7538h
0x1800236e5  jnz     short loc_180023733
0x1800236e7  xor     ebx, ebx
0x1800236e9  lea     esi, [rbx+48h]
0x1800236ec  mov     r8d, esi; Size
0x1800236ef  xor     edx, edx; Val
0x1800236f1  lea     rcx, [rsp+1B8h+pgui]; void *
0x1800236f6  call    memset_0
0x1800236fb  mov     [rsp+1B8h+pgui.cbSize], esi
0x1800236ff  lea     rdx, [rsp+1B8h+pgui]; pgui
0x180023704  xor     ecx, ecx; idThread
0x180023706  call    cs:__imp_GetGUIThreadInfo
0x18002370c  test    eax, eax
0x18002370e  jz      short loc_18002372C
0x180023710  mov     rdx, [rsp+1B8h+pgui.hwndFocus]; hWnd
0x180023715  cmp     rdx, r14
0x180023718  jz      short loc_180023727
0x18002371a  mov     rcx, r14; hWndParent
0x18002371d  call    cs:__imp_IsChild
0x180023723  test    eax, eax
0x180023725  jz      short loc_18002372C
0x180023727  mov     ebx, 1
0x18002372c  neg     ebx
0x18002372e  jmp     loc_1800237EB
0x180023733  cmp     ebx, 7548h
0x180023739  jnz     short loc_18002377E
0x18002373b  mov     rcx, r14; hWnd
0x18002373e  call    ?IsWinFormsControl@BasicHwndUtils@@SAHPEAUHWND__@@@Z; BasicHwndUtils::IsWinFormsControl(HWND__ *)
0x180023743  lea     rcx, aWin32; "Win32"
0x18002374a  lea     rdx, aWinform; "WinForm"
0x180023751  xor     ebx, ebx
0x180023753  test    eax, eax
0x180023755  cmovz   rdx, rcx
0x180023759  lea     rcx, [rsp+1B8h+dwProcessId]
0x18002375e  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180023763  mov     rcx, [rax]
0x180023766  mov     [rax], rbx
0x180023769  mov     [rdi+8], rcx
0x18002376d  lea     rcx, [rsp+1B8h+dwProcessId]
0x180023772  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180023777  mov     word ptr [rdi], 8
0x18002377c  jmp     short loc_1800237F7
0x18002377e  cmp     ebx, 7533h
0x180023784  jnz     short loc_1800237A2
0x180023786  mov     rcx, r14; HWND
0x180023789  call    ?IsWindowPatternWindow@BasicHwndUtils@@SAHPEAUHWND__@@@Z; BasicHwndUtils::IsWindowPatternWindow(HWND__ *)
0x18002378e  neg     eax
0x180023790  sbb     ecx, ecx
0x180023792  add     ecx, 0C371h
0x180023798  mov     word ptr [rdi], 3
0x18002379d  mov     [rdi+8], ecx
0x1800237a0  jmp     short loc_1800237F7
0x1800237a2  cmp     ebx, 75DEh
0x1800237a8  jnz     short loc_1800237F7
0x1800237aa  mov     r8d, 80h; nMaxCount
0x1800237b0  lea     rdx, [rsp+1B8h+ClassName]; lpClassName
0x1800237b8  mov     rcx, r14; hWnd
0x1800237bb  call    cs:__imp_GetClassNameW
0x1800237c1  test    eax, eax
0x1800237c3  jz      short loc_1800237F7
0x1800237c5  lea     rcx, [rsp+1B8h+ClassName]; lpsz
0x1800237cd  call    cs:__imp_CharLowerW
0x1800237d3  lea     rdx, aDialog; "dialog"
0x1800237da  lea     rcx, [rsp+1B8h+ClassName]; Str
0x1800237e2  call    cs:__imp_wcsstr
0x1800237e8  neg     rax
0x1800237eb  sbb     ax, ax
0x1800237ee  mov     word ptr [rdi], 0Bh
0x1800237f3  mov     [rdi+8], ax
0x1800237f7  xor     eax, eax
0x1800237f9  jmp     short loc_1800237FF
0x1800237fb  mov     eax, [rsp+1B8h+dwProcessId]
0x1800237ff  mov     rcx, [rsp+1B8h+var_38]
0x180023807  xor     rcx, rsp; StackCookie
0x18002380a  call    __security_check_cookie
0x18002380f  add     rsp, 190h
0x180023816  pop     r15
0x180023818  pop     r14
0x18002381a  pop     rdi
0x18002381b  pop     rsi
0x18002381c  pop     rbx
0x18002381d  retn
```
