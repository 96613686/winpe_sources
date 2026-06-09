# UiaWindowNotifier::OnCreateAutomationConnection(ushort const *,uint,uchar)

- ea: `0x18002e240`
- end: `0x18002e317`
- name: `?OnCreateAutomationConnection@UiaWindowNotifier@@UEAAJPEBGIE@Z`
- size: `215`
- prototype: `int(UiaWindowNotifier *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int8)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180006edc`
- `0x18000af78`
- `0x180024f38`
- `0x18002e240`
- `0x180091010`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18002e2ff`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18002e2ff`
- `ext-ms-win-ntuser-window-l1-1-0!SetPropW` at `0x18002e295`
- `ext-ms-win-ntuser-window-l1-1-0!SetPropW` at `0x18002e295`

## string_xrefs

- `0x18002e266`: `onecore\windows\accessibletech\uiamanager\dll\uiawindownotifier.cpp`
- `0x18002e2a4`: `onecore\windows\accessibletech\uiamanager\dll\uiawindownotifier.cpp`
- `0x18002e2d9`: `onecore\windows\accessibletech\uiamanager\dll\uiawindownotifier.cpp`

## pseudocode

```c
__int64 __fastcall UiaWindowNotifier::OnCreateAutomationConnection(
        UiaWindowNotifier *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        char a4)
{
  HWND v6; // rcx
  const char *v9; // r9
  __int64 v10; // rcx
  int v11; // eax
  int v12; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v6 = (HWND)*((_QWORD *)this + 5);
  if ( !v6 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiawindownotifier.cpp",
      (const char *)0x80004005LL,
      v12);
    return 2147500037LL;
  }
  if ( a4 )
  {
    if ( !SetPropW(v6, L"MS_UIA_BasicViewId", (HANDLE)a3) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x70,
               (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiawindownotifier.cpp",
               v9);
    *((_BYTE *)this + 52) = 1;
  }
  v10 = *((_QWORD *)this + 4);
  if ( v10 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 24LL))(v10, a3);
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7C,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiawindownotifier.cpp",
        (const char *)(unsigned int)v11,
        v12);
  }
  SendMessageW(*((HWND *)this + 5), 0x3Du, (WPARAM)a2, -25);
  return 0;
}

```

## disassembly

```asm
0x18002e240  mov     [rsp+arg_0], rbx
0x18002e245  mov     [rsp+arg_8], rsi
0x18002e24a  push    rdi; int
0x18002e24b  sub     rsp, 20h
0x18002e24f  mov     rbx, rcx
0x18002e252  mov     edi, r8d
0x18002e255  mov     rcx, [rcx+28h]; hWnd
0x18002e259  mov     rsi, rdx
0x18002e25c  test    rcx, rcx
0x18002e25f  jnz     short loc_18002E286
0x18002e261  mov     rcx, [rsp+28h]; this
0x18002e266  lea     r8, aOnecoreWindows_25; "onecore\\windows\\accessibletech\\uiama"...
0x18002e26d  mov     ebx, 80004005h
0x18002e272  mov     edx, 6Bh ; 'k'; void *
0x18002e277  mov     r9d, ebx; char *
0x18002e27a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e27f  mov     eax, ebx
0x18002e281  jmp     loc_18002E307
0x18002e286  test    r9b, r9b
0x18002e289  jz      short loc_18002E2B9
0x18002e28b  mov     r8, rdi; hData
0x18002e28e  lea     rdx, aMsUiaBasicview; "MS_UIA_BasicViewId"
0x18002e295  call    cs:__imp_SetPropW
0x18002e29b  test    eax, eax
0x18002e29d  jnz     short loc_18002E2B5
0x18002e29f  mov     rcx, [rsp+28h]; this
0x18002e2a4  lea     r8, aOnecoreWindows_25; "onecore\\windows\\accessibletech\\uiama"...
0x18002e2ab  lea     edx, [rax+70h]; void *
0x18002e2ae  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002e2b3  jmp     short loc_18002E307
0x18002e2b5  mov     byte ptr [rbx+34h], 1
0x18002e2b9  mov     rcx, [rbx+20h]
0x18002e2bd  test    rcx, rcx
0x18002e2c0  jz      short loc_18002E2ED
0x18002e2c2  mov     rax, [rcx]
0x18002e2c5  mov     edx, edi
0x18002e2c7  mov     rax, [rax+18h]
0x18002e2cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2d0  test    eax, eax
0x18002e2d2  jns     short loc_18002E2ED
0x18002e2d4  mov     rcx, [rsp+28h]; this
0x18002e2d9  lea     r8, aOnecoreWindows_25; "onecore\\windows\\accessibletech\\uiama"...
0x18002e2e0  mov     r9d, eax; char *
0x18002e2e3  mov     edx, 7Ch ; '|'; void *
0x18002e2e8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002e2ed  mov     rcx, [rbx+28h]; hWnd
0x18002e2f1  mov     r9, 0FFFFFFFFFFFFFFE7h; lParam
0x18002e2f8  mov     r8, rsi; wParam
0x18002e2fb  lea     edx, [r9+56h]; Msg
0x18002e2ff  call    cs:__imp_SendMessageW
0x18002e305  xor     eax, eax
0x18002e307  mov     rbx, [rsp+28h+arg_0]
0x18002e30c  mov     rsi, [rsp+28h+arg_8]
0x18002e311  add     rsp, 20h
0x18002e315  pop     rdi
0x18002e316  retn
```
