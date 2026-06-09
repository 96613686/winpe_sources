# BasicHwndUtils::UIASendMessageTimeout(UIA_TIMEOUTDATA const &,HWND__ *,uint,unsigned __int64,__int64,__int64 *)

- ea: `0x180023d0c`
- end: `0x180023ed1`
- name: `?UIASendMessageTimeout@BasicHwndUtils@@SAJAEBUUIA_TIMEOUTDATA@@PEAUHWND__@@I_K_JPEA_J@Z`
- size: `453`
- prototype: `static int(const struct UIA_TIMEOUTDATA *, HWND, unsigned int, unsigned __int64, __int64, __int64 *)`
- caller_count: `8`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180017600`
- `0x180022fbc`
- `0x180023934`
- `0x180023a90`
- `0x18007b094`
- `0x18007b370`
- `0x18007bb2c`
- `0x18007c4a8`

## callees

- `0x180023d0c`
- `0x180043680`
- `0x18007c01c`
- `0x18007c468`
- `0x18008a028`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023de7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023de7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x180023e4c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x180023e4c`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180023d65`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180023d65`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageTimeoutW` at `0x180023dce`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageTimeoutW` at `0x180023dce`

## string_xrefs

- `0x180023d8b`: `onecore\windows\accessibletech\common\basichwndutils.cpp`
- `0x180023e24`: `onecore\windows\accessibletech\common\basichwndutils.cpp`
- `0x180023e95`: `onecore\windows\accessibletech\common\basichwndutils.cpp`

## pseudocode

```c
__int64 __fastcall BasicHwndUtils::UIASendMessageTimeout(
        const struct UIA_TIMEOUTDATA *a1,
        HWND a2,
        UINT a3,
        WPARAM a4,
        LPARAM lParam,
        __int64 *a6)
{
  UINT v10; // ebx
  UINT fuFlags; // edi
  ULONG_PTR v13; // rbp
  unsigned int v14; // ebx
  signed int LastError; // eax
  signed int v16; // esi
  const char *v17; // rax
  __int64 v18; // rdx
  const char *uTimeout; // [rsp+28h] [rbp-80h]
  const char *uTimeouta; // [rsp+28h] [rbp-80h]
  const char *uTimeoutb; // [rsp+28h] [rbp-80h]
  ULONG_PTR dwResult; // [rsp+40h] [rbp-68h] BYREF
  WCHAR ClassName[16]; // [rsp+48h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  if ( *(_BYTE *)a1 )
  {
    v10 = *((_DWORD *)a1 + 1);
    fuFlags = 34;
    if ( v10 < 0x32 )
      v10 = 20000;
  }
  else
  {
    fuFlags = 1;
    v10 = 10000;
  }
  if ( !IsWindow(a2) )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xEF,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
      (const char *)0x80131505LL,
      (int)"BasicHwndUtils::SendMessageTimeout:  Window doesn't exist anymore. ERROR_TIMEOUT",
      uTimeout);
    return 2148734213LL;
  }
  dwResult = 0;
  if ( SendMessageTimeoutW(a2, a3, a4, lParam, fuFlags, v10, &dwResult) )
  {
    v13 = dwResult;
    v14 = 0;
    goto LABEL_23;
  }
  v13 = 0;
  LastError = GetLastError();
  v16 = LastError;
  if ( LastError )
  {
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    else
      v14 = LastError;
  }
  else
  {
    v14 = -2146233083;
  }
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)0x108,
    (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
    (const char *)v14,
    (int)"BasicHwndUtils::UIASendMessageTimeout:  Call to SendMessageTimeout failed",
    uTimeouta);
  if ( !*(_BYTE *)a1 )
    goto LABEL_23;
  if ( v16 != 5 )
  {
    if ( v16 != 1460 )
      goto LABEL_23;
    v17 = "BasicHwndUtils::SendMessageTimeout, mapped error to UIA timeout from ERROR_TIMEOUT";
    v18 = 286;
LABEL_22:
    v14 = -2146233083;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
      (const char *)0x80131505LL,
      (int)v17,
      uTimeoutb);
    goto LABEL_23;
  }
  if ( GetClassNameW(a2, ClassName, 16) > 0 && !wcscmp_0(ClassName, L"Ghost") )
  {
    v17 = "BasicHwndUtils::UIASendMessageTimeout, mapped error to UIA timeout for Ghost window";
    v18 = 279;
    goto LABEL_22;
  }
LABEL_23:
  if ( a6 )
    *a6 = v13;
  return v14;
}

```

## disassembly

```asm
0x180023d0c  push    rbx
0x180023d0e  push    rbp
0x180023d0f  push    rsi
0x180023d10  push    rdi
0x180023d11  push    r13
0x180023d13  push    r14
0x180023d15  push    r15
0x180023d17  sub     rsp, 70h
0x180023d1b  mov     rax, cs:__security_cookie
0x180023d22  xor     rax, rsp
0x180023d25  mov     [rsp+0A8h+var_40], rax
0x180023d2a  cmp     byte ptr [rcx], 0
0x180023d2d  mov     rbp, r9
0x180023d30  mov     r14, [rsp+0A8h+arg_28]
0x180023d38  mov     esi, r8d
0x180023d3b  mov     r15, rdx
0x180023d3e  mov     r13, rcx
0x180023d41  jz      short loc_180023D58
0x180023d43  mov     ebx, [rcx+4]
0x180023d46  mov     eax, 4E20h
0x180023d4b  cmp     ebx, 32h ; '2'
0x180023d4e  mov     edi, 22h ; '"'
0x180023d53  cmovb   ebx, eax
0x180023d56  jmp     short loc_180023D62
0x180023d58  mov     edi, 1
0x180023d5d  mov     ebx, 2710h
0x180023d62  mov     rcx, r15; hWnd
0x180023d65  call    cs:__imp_IsWindow
0x180023d6b  test    eax, eax
0x180023d6d  jnz     short loc_180023DA3
0x180023d6f  mov     rcx, [rsp+0A8h]; this
0x180023d77  lea     rax, aBasichwndutils_2; "BasicHwndUtils::SendMessageTimeout:  Wi"...
0x180023d7e  mov     edi, 80131505h
0x180023d83  mov     qword ptr [rsp+0A8h+fuFlags], rax; int
0x180023d88  mov     r9d, edi; char *
0x180023d8b  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x180023d92  mov     edx, 0EFh; void *
0x180023d97  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180023d9c  mov     eax, edi
0x180023d9e  jmp     loc_180023EB5
0x180023da3  mov     r9, [rsp+0A8h+lParam]; lParam
0x180023dab  lea     rax, [rsp+0A8h+dwResult]
0x180023db0  mov     [rsp+0A8h+lpdwResult], rax; lpdwResult
0x180023db5  mov     r8, rbp; wParam
0x180023db8  mov     dword ptr [rsp+0A8h+uTimeout], ebx; char *
0x180023dbc  mov     edx, esi; Msg
0x180023dbe  mov     rcx, r15; hWnd
0x180023dc1  mov     [rsp+0A8h+fuFlags], edi; fuFlags
0x180023dc5  mov     [rsp+0A8h+dwResult], 0
0x180023dce  call    cs:__imp_SendMessageTimeoutW
0x180023dd4  test    rax, rax
0x180023dd7  jz      short loc_180023DE5
0x180023dd9  mov     rbp, [rsp+0A8h+dwResult]
0x180023dde  xor     ebx, ebx
0x180023de0  jmp     loc_180023EAB
0x180023de5  xor     ebp, ebp
0x180023de7  call    cs:__imp_GetLastError
0x180023ded  mov     esi, eax
0x180023def  mov     edi, 80131505h
0x180023df4  test    eax, eax
0x180023df6  jz      short loc_180023E0B
0x180023df8  test    eax, eax
0x180023dfa  jg      short loc_180023E00
0x180023dfc  mov     ebx, eax
0x180023dfe  jmp     short loc_180023E0D
0x180023e00  movzx   ebx, si
0x180023e03  or      ebx, 80070000h
0x180023e09  jmp     short loc_180023E0D
0x180023e0b  mov     ebx, edi
0x180023e0d  mov     rcx, [rsp+0A8h]; this
0x180023e15  lea     rax, aBasichwndutils_1; "BasicHwndUtils::UIASendMessageTimeout: "...
0x180023e1c  mov     r9d, ebx; char *
0x180023e1f  mov     qword ptr [rsp+0A8h+fuFlags], rax; int
0x180023e24  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x180023e2b  mov     edx, 108h; void *
0x180023e30  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180023e35  cmp     [r13+0], bpl
0x180023e39  jz      short loc_180023EAB
0x180023e3b  cmp     esi, 5
0x180023e3e  jnz     short loc_180023E79
0x180023e40  lea     r8d, [rsi+0Bh]; nMaxCount
0x180023e44  mov     rcx, r15; hWnd
0x180023e47  lea     rdx, [rsp+0A8h+ClassName]; lpClassName
0x180023e4c  call    cs:__imp_GetClassNameW
0x180023e52  test    eax, eax
0x180023e54  jle     short loc_180023EAB
0x180023e56  lea     rdx, aGhost; "Ghost"
0x180023e5d  lea     rcx, [rsp+0A8h+ClassName]; String1
0x180023e62  call    wcscmp_0
0x180023e67  test    eax, eax
0x180023e69  jnz     short loc_180023EAB
0x180023e6b  lea     rax, aBasichwndutils_0; "BasicHwndUtils::UIASendMessageTimeout, "...
0x180023e72  mov     edx, 117h
0x180023e77  jmp     short loc_180023E8D
0x180023e79  cmp     esi, 5B4h
0x180023e7f  jnz     short loc_180023EAB
0x180023e81  lea     rax, aBasichwndutils; "BasicHwndUtils::SendMessageTimeout, map"...
0x180023e88  mov     edx, 11Eh; void *
0x180023e8d  mov     rcx, [rsp+0A8h]; this
0x180023e95  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x180023e9c  mov     r9d, edi; char *
0x180023e9f  mov     qword ptr [rsp+0A8h+fuFlags], rax; int
0x180023ea4  mov     ebx, edi
0x180023ea6  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180023eab  test    r14, r14
0x180023eae  jz      short loc_180023EB3
0x180023eb0  mov     [r14], rbp
0x180023eb3  mov     eax, ebx
0x180023eb5  mov     rcx, [rsp+0A8h+var_40]
0x180023eba  xor     rcx, rsp; StackCookie
0x180023ebd  call    __security_check_cookie
0x180023ec2  add     rsp, 70h
0x180023ec6  pop     r15
0x180023ec8  pop     r14
0x180023eca  pop     r13
0x180023ecc  pop     rdi
0x180023ecd  pop     rsi
0x180023ece  pop     rbp
0x180023ecf  pop     rbx
0x180023ed0  retn
```
