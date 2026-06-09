# StubWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x140004280`
- end: `0x1400043b9`
- name: `?StubWndProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `313`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140004280`
- `0x140004ba0`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1400042f8`
- `KERNEL32!CompareStringOrdinal` at `0x1400042f8`
- `USER32!GetClassNameW` at `0x1400042d4`
- `USER32!GetClassNameW` at `0x1400042d4`
- `USER32!DestroyIcon` at `0x14000436b`
- `USER32!DestroyIcon` at `0x14000436b`
- `USER32!GetWindowLongPtrW` at `0x14000432f`
- `USER32!GetWindowLongPtrW` at `0x140004376`
- `USER32!GetWindowLongPtrW` at `0x14000432f`
- `USER32!GetWindowLongPtrW` at `0x140004376`
- `USER32!SendMessageW` at `0x14000435d`
- `USER32!SendMessageW` at `0x14000435d`
- `USER32!SetWindowLongPtrW` at `0x14000434a`
- `USER32!SetWindowLongPtrW` at `0x14000438c`
- `USER32!SetWindowLongPtrW` at `0x14000434a`
- `USER32!SetWindowLongPtrW` at `0x14000438c`
- `USER32!GetWindow` at `0x1400042bd`
- `USER32!GetWindow` at `0x140004309`
- `USER32!GetWindow` at `0x14000431a`
- `USER32!GetWindow` at `0x1400042bd`
- `USER32!GetWindow` at `0x140004309`
- `USER32!GetWindow` at `0x14000431a`
- `USER32!DefWindowProcW` at `0x1400042ad`
- `USER32!DefWindowProcW` at `0x1400042ad`
- `SHLWAPI!__imp_SHFreeShared` at `0x140004397`
- `SHLWAPI!__imp_SHFreeShared` at `0x140004397`

## pseudocode

```c
LRESULT __fastcall StubWndProc(HWND hWnd, UINT a2, WPARAM a3, LPARAM a4)
{
  HWND Window; // rbx
  LONG_PTR v7; // rax
  HICON v8; // rax
  void *WindowLongPtrW; // rbx
  WCHAR ClassName[128]; // [rsp+30h] [rbp-128h] BYREF

  if ( a2 == 2 )
  {
    v8 = (HICON)SendMessageW(hWnd, 0x7Fu, 1u, 0);
    if ( v8 )
      DestroyIcon(v8);
    WindowLongPtrW = (void *)GetWindowLongPtrW(hWnd, 0);
    if ( WindowLongPtrW )
    {
      SetWindowLongPtrW(hWnd, 0, 0);
      SHFreeShared(WindowLongPtrW, 0);
    }
  }
  else
  {
    if ( a2 != 28 )
      return DefWindowProcW(hWnd, a2, a3, a4);
    Window = GetWindow(hWnd, 3u);
    if ( GetClassNameW(Window, ClassName, 128) && CompareStringOrdinal(ClassName, -1, L"IME", -1, 1) == 2 )
      Window = GetWindow(Window, 3u);
    if ( GetWindow(Window, 4u) == hWnd )
    {
      v7 = GetWindowLongPtrW(Window, -20);
      if ( (v7 & 0x40080) == 0 )
        SetWindowLongPtrW(Window, -20, v7 | 0x40000);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140004280  push    rbx
0x140004282  push    rdi
0x140004283  sub     rsp, 148h
0x14000428a  mov     rax, cs:__security_cookie
0x140004291  xor     rax, rsp
0x140004294  mov     [rsp+158h+var_28], rax
0x14000429c  mov     rdi, rcx
0x14000429f  cmp     edx, 2
0x1400042a2  jz      loc_140004352
0x1400042a8  cmp     edx, 1Ch
0x1400042ab  jz      short loc_1400042B8
0x1400042ad  call    cs:__imp_DefWindowProcW
0x1400042b3  jmp     loc_14000439F
0x1400042b8  mov     edx, 3; uCmd
0x1400042bd  call    cs:__imp_GetWindow
0x1400042c3  mov     r8d, 80h; nMaxCount
0x1400042c9  lea     rdx, [rsp+158h+ClassName]; lpClassName
0x1400042ce  mov     rcx, rax; hWnd
0x1400042d1  mov     rbx, rax
0x1400042d4  call    cs:__imp_GetClassNameW
0x1400042da  test    eax, eax
0x1400042dc  jz      short loc_140004312
0x1400042de  or      edx, 0FFFFFFFFh; cchCount1
0x1400042e1  mov     [rsp+158h+bIgnoreCase], 1; bIgnoreCase
0x1400042e9  mov     r9d, edx; cchCount2
0x1400042ec  lea     r8, String2; "IME"
0x1400042f3  lea     rcx, [rsp+158h+ClassName]; lpString1
0x1400042f8  call    cs:__imp_CompareStringOrdinal
0x1400042fe  cmp     eax, 2
0x140004301  jnz     short loc_140004312
0x140004303  lea     edx, [rax+1]; uCmd
0x140004306  mov     rcx, rbx; hWnd
0x140004309  call    cs:__imp_GetWindow
0x14000430f  mov     rbx, rax
0x140004312  mov     edx, 4; uCmd
0x140004317  mov     rcx, rbx; hWnd
0x14000431a  call    cs:__imp_GetWindow
0x140004320  cmp     rax, rdi
0x140004323  jnz     short loc_14000439D
0x140004325  mov     edi, 0FFFFFFECh
0x14000432a  mov     rcx, rbx; hWnd
0x14000432d  mov     edx, edi; nIndex
0x14000432f  call    cs:__imp_GetWindowLongPtrW
0x140004335  test    rax, 40080h
0x14000433b  jnz     short loc_14000439D
0x14000433d  bts     rax, 12h
0x140004342  mov     edx, edi; nIndex
0x140004344  mov     r8, rax; dwNewLong
0x140004347  mov     rcx, rbx; hWnd
0x14000434a  call    cs:__imp_SetWindowLongPtrW
0x140004350  jmp     short loc_14000439D
0x140004352  xor     r9d, r9d; lParam
0x140004355  lea     edx, [r9+7Fh]; Msg
0x140004359  lea     r8d, [r9+1]; wParam
0x14000435d  call    cs:__imp_SendMessageW
0x140004363  test    rax, rax
0x140004366  jz      short loc_140004371
0x140004368  mov     rcx, rax; hIcon
0x14000436b  call    cs:__imp_DestroyIcon
0x140004371  xor     edx, edx; nIndex
0x140004373  mov     rcx, rdi; hWnd
0x140004376  call    cs:__imp_GetWindowLongPtrW
0x14000437c  mov     rbx, rax
0x14000437f  test    rax, rax
0x140004382  jz      short loc_14000439D
0x140004384  xor     r8d, r8d; dwNewLong
0x140004387  xor     edx, edx; nIndex
0x140004389  mov     rcx, rdi; hWnd
0x14000438c  call    cs:__imp_SetWindowLongPtrW
0x140004392  xor     edx, edx; dwProcessId
0x140004394  mov     rcx, rbx; hData
0x140004397  call    cs:__imp_SHFreeShared
0x14000439d  xor     eax, eax
0x14000439f  mov     rcx, [rsp+158h+var_28]
0x1400043a7  xor     rcx, rsp; StackCookie
0x1400043aa  call    __security_check_cookie
0x1400043af  add     rsp, 148h
0x1400043b6  pop     rdi
0x1400043b7  pop     rbx
0x1400043b8  retn
```
