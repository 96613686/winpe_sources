# _lambda_80c9c4321fda70fcbf4fd57f8d5fc182_::operator()

- ea: `0x18006c4ac`
- end: `0x18006c650`
- name: `_lambda_80c9c4321fda70fcbf4fd57f8d5fc182_::operator()`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18006c3e0`

## callees

- `0x180024184`
- `0x180043c30`
- `0x18006c4ac`
- `0x18006f064`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006c4fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006c4fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006c4ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006c4ee`
- `UxTheme!GetThemeColor` at `0x18006c58d`
- `UxTheme!GetThemeColor` at `0x18006c58d`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18006c547`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18006c547`
- `ext-ms-win-ntuser-window-l1-1-0!SetPropW` at `0x18006c61c`
- `ext-ms-win-ntuser-window-l1-1-0!SetPropW` at `0x18006c61c`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18006c4e6`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18006c4e6`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x18006c560`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x18006c560`
- `dwmapi!DwmSetWindowAttribute` at `0x18006c5aa`
- `dwmapi!DwmSetWindowAttribute` at `0x18006c5e6`
- `dwmapi!DwmSetWindowAttribute` at `0x18006c5aa`
- `dwmapi!DwmSetWindowAttribute` at `0x18006c5e6`
- `USER32!GetClassNameW` at `0x18006c51a`
- `USER32!GetClassNameW` at `0x18006c51a`

## pseudocode

```c
__int64 __fastcall lambda_80c9c4321fda70fcbf4fd57f8d5fc182_::operator()(__int64 a1, HWND a2, _QWORD *a3)
{
  DWORD WindowThreadProcessId; // edi
  void *v6; // rcx
  HRESULT v7; // eax
  HRESULT v8; // eax
  int pColor; // [rsp+20h] [rbp-838h]
  DWORD dwProcessId; // [rsp+30h] [rbp-828h] BYREF
  COLORREF pvAttribute; // [rsp+34h] [rbp-824h] BYREF
  int v13; // [rsp+38h] [rbp-820h] BYREF
  WCHAR ClassName[1024]; // [rsp+40h] [rbp-818h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+858h] [rbp+0h]

  dwProcessId = 0;
  WindowThreadProcessId = GetWindowThreadProcessId(a2, &dwProcessId);
  if ( dwProcessId != GetCurrentProcessId() )
    return 1;
  if ( WindowThreadProcessId != GetCurrentThreadId() )
    return 1;
  GetClassNameW(a2, ClassName, 1024);
  if ( wcscmp_0(ClassName, L"#32768") || *a3 != SendMessageW(a2, 0x1E1u, 0, 0) )
    return 1;
  if ( !(unsigned int)GetPropW(a2, L"IsZachMenuDWMAttributeSet") )
  {
    v6 = (void *)a3[1];
    pvAttribute = 0;
    if ( GetThemeColor(v6, 10, 0, 3821, &pvAttribute) >= 0 )
    {
      v7 = DwmSetWindowAttribute(a2, 0x22u, &pvAttribute, 4u);
      if ( v7 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x74,
          (unsigned int)"shell\\lib\\immersivecontextmenu\\immersivecontextmenuownerdrawhelper.cpp",
          (const char *)(unsigned int)v7,
          pColor);
    }
    v13 = 3;
    v8 = DwmSetWindowAttribute(a2, 0x21u, &v13, 4u);
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"shell\\lib\\immersivecontextmenu\\immersivecontextmenuownerdrawhelper.cpp",
        (const char *)(unsigned int)v8,
        pColor);
    SetPropW(a2, L"IsZachMenuDWMAttributeSet", HANDLE_FLAG_INHERIT);
  }
  return 0;
}

```

## disassembly

```asm
0x18006c4ac  mov     [rsp+arg_0], rbx
0x18006c4b1  mov     [rsp+arg_18], rsi
0x18006c4b6  push    rdi
0x18006c4b7  sub     rsp, 850h
0x18006c4be  mov     rax, cs:__security_cookie
0x18006c4c5  xor     rax, rsp
0x18006c4c8  mov     [rsp+858h+var_18], rax
0x18006c4d0  mov     rbx, rdx
0x18006c4d3  mov     [rsp+858h+dwProcessId], 0
0x18006c4db  mov     rcx, rbx; hWnd
0x18006c4de  lea     rdx, [rsp+858h+dwProcessId]; lpdwProcessId
0x18006c4e3  mov     rsi, r8
0x18006c4e6  call    cs:__imp_GetWindowThreadProcessId
0x18006c4ec  mov     edi, eax
0x18006c4ee  call    cs:__imp_GetCurrentProcessId
0x18006c4f4  cmp     [rsp+858h+dwProcessId], eax
0x18006c4f8  jnz     loc_18006C626
0x18006c4fe  call    cs:__imp_GetCurrentThreadId
0x18006c504  cmp     edi, eax
0x18006c506  jnz     loc_18006C626
0x18006c50c  mov     r8d, 400h; nMaxCount
0x18006c512  lea     rdx, [rsp+858h+ClassName]; lpClassName
0x18006c517  mov     rcx, rbx; hWnd
0x18006c51a  call    cs:__imp_GetClassNameW
0x18006c520  lea     rdx, a32768; "#32768"
0x18006c527  lea     rcx, [rsp+858h+ClassName]; String1
0x18006c52c  call    wcscmp_0
0x18006c531  test    eax, eax
0x18006c533  jnz     loc_18006C626
0x18006c539  xor     r9d, r9d; lParam
0x18006c53c  xor     r8d, r8d; wParam
0x18006c53f  mov     edx, 1E1h; Msg
0x18006c544  mov     rcx, rbx; hWnd
0x18006c547  call    cs:__imp_SendMessageW
0x18006c54d  cmp     [rsi], rax
0x18006c550  jnz     loc_18006C626
0x18006c556  lea     rdx, aIszachmenudwma; "IsZachMenuDWMAttributeSet"
0x18006c55d  mov     rcx, rbx; hWnd
0x18006c560  call    cs:__imp_GetPropW
0x18006c566  test    eax, eax
0x18006c568  jnz     loc_18006C622
0x18006c56e  mov     rcx, [rsi+8]; hTheme
0x18006c572  xor     r8d, r8d; iStateId
0x18006c575  mov     [rsp+858h+pvAttribute], eax
0x18006c579  mov     r9d, 0EEDh; iPropId
0x18006c57f  lea     rax, [rsp+858h+pvAttribute]
0x18006c584  mov     qword ptr [rsp+858h+pColor], rax; int
0x18006c589  lea     edx, [r8+0Ah]; iPartId
0x18006c58d  call    cs:__imp_GetThemeColor
0x18006c593  mov     edi, 4
0x18006c598  test    eax, eax
0x18006c59a  js      short loc_18006C5CE
0x18006c59c  mov     r9d, edi; cbAttribute
0x18006c59f  lea     r8, [rsp+858h+pvAttribute]; pvAttribute
0x18006c5a4  lea     edx, [rdi+1Eh]; dwAttribute
0x18006c5a7  mov     rcx, rbx; hwnd
0x18006c5aa  call    cs:__imp_DwmSetWindowAttribute
0x18006c5b0  test    eax, eax
0x18006c5b2  jns     short loc_18006C5CE
0x18006c5b4  mov     rcx, [rsp+858h]; this
0x18006c5bc  lea     r8, aShellLibImmers; "shell\\lib\\immersivecontextmenu\\immer"...
0x18006c5c3  mov     r9d, eax; char *
0x18006c5c6  lea     edx, [rdi+70h]; void *
0x18006c5c9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006c5ce  mov     r9d, edi; cbAttribute
0x18006c5d1  mov     [rsp+858h+var_820], 3
0x18006c5d9  lea     r8, [rsp+858h+var_820]; pvAttribute
0x18006c5de  mov     edx, 21h ; '!'; dwAttribute
0x18006c5e3  mov     rcx, rbx; hwnd
0x18006c5e6  call    cs:__imp_DwmSetWindowAttribute
0x18006c5ec  test    eax, eax
0x18006c5ee  jns     short loc_18006C60C
0x18006c5f0  mov     rcx, [rsp+858h]; this
0x18006c5f8  lea     r8, aShellLibImmers; "shell\\lib\\immersivecontextmenu\\immer"...
0x18006c5ff  mov     r9d, eax; char *
0x18006c602  mov     edx, 78h ; 'x'; void *
0x18006c607  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006c60c  mov     r8d, 1; hData
0x18006c612  lea     rdx, aIszachmenudwma; "IsZachMenuDWMAttributeSet"
0x18006c619  mov     rcx, rbx; hWnd
0x18006c61c  call    cs:__imp_SetPropW
0x18006c622  xor     eax, eax
0x18006c624  jmp     short loc_18006C62B
0x18006c626  mov     eax, 1
0x18006c62b  mov     rcx, [rsp+858h+var_18]
0x18006c633  xor     rcx, rsp; StackCookie
0x18006c636  call    __security_check_cookie
0x18006c63b  lea     r11, [rsp+858h+var_8]
0x18006c643  mov     rbx, [r11+10h]
0x18006c647  mov     rsi, [r11+28h]
0x18006c64b  mov     rsp, r11
0x18006c64e  pop     rdi
0x18006c64f  retn
```
