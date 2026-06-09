# FrameWindow::UpdateWindowPos(void)

- ea: `0x1800298b4`
- end: `0x1800299bf`
- name: `?UpdateWindowPos@FrameWindow@@AEAAXXZ`
- size: `267`
- prototype: `void __fastcall(FrameWindow *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180020dcc`
- `0x1800240e4`
- `0x1800257e0`

## callees

- `0x180001800`
- `0x180022204`
- `0x1800298b4`
- `0x18002f988`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180029993`
- `ADVAPI32!RegCloseKey` at `0x180029993`
- `ADVAPI32!RegSetValueExW` at `0x180029985`
- `ADVAPI32!RegSetValueExW` at `0x180029985`
- `USER32!GetWindowPlacement` at `0x1800298f7`
- `USER32!GetWindowPlacement` at `0x1800298f7`

## pseudocode

```c
void __fastcall FrameWindow::UpdateWindowPos(FrameWindow *this, struct ATL::CRegKey *a2)
{
  HWND v3; // rcx
  bool v4; // zf
  HKEY v5; // rcx
  HKEY v6; // rdi
  WINDOWPLACEMENT wndpl; // [rsp+30h] [rbp-40h] BYREF

  if ( !*((_BYTE *)this + 435) )
  {
    v3 = (HWND)*((_QWORD *)this + 1);
    memset(&wndpl, 0, sizeof(wndpl));
    if ( GetWindowPlacement(v3, &wndpl) )
    {
      if ( wndpl.showCmd != 2 )
      {
        v4 = wndpl.showCmd == 3;
        *(RECT *)((char *)this + 116) = wndpl.rcNormalPosition;
        *((_DWORD *)this + 33) = !v4;
      }
    }
  }
  *((_BYTE *)this + 136) = *((_BYTE *)this + 435);
  if ( this != (FrameWindow *)-116LL )
  {
    memset(&wndpl, 0, 24);
    if ( F12::CreateOrOpenF12RegRoot((HKEY *)&wndpl, a2) )
    {
      v5 = *(HKEY *)&wndpl.length;
      if ( *(_QWORD *)&wndpl.length )
        goto LABEL_11;
    }
    else
    {
      v6 = *(HKEY *)&wndpl.length;
      RegSetValueExW(*(HKEY *)&wndpl.length, L"windowpos", 0, 3u, (const BYTE *)this + 116, 0x18u);
      if ( v6 )
      {
        v5 = v6;
LABEL_11:
        RegCloseKey(v5);
      }
    }
  }
  FrameWindow::DismissPopupWindow(this);
}

```

## disassembly

```asm
0x1800298b4  mov     [rsp-8+arg_8], rbx
0x1800298b9  mov     [rsp-8+arg_10], rdi
0x1800298be  push    rbp
0x1800298bf  mov     rbp, rsp
0x1800298c2  sub     rsp, 70h
0x1800298c6  mov     rax, cs:__security_cookie
0x1800298cd  xor     rax, rsp
0x1800298d0  mov     [rbp+var_10], rax
0x1800298d4  cmp     byte ptr [rcx+1B3h], 0
0x1800298db  mov     rbx, rcx
0x1800298de  jnz     short loc_18002991F
0x1800298e0  mov     rcx, [rcx+8]; hWnd
0x1800298e4  lea     rdx, [rbp+wndpl]; lpwndpl
0x1800298e8  xorps   xmm0, xmm0
0x1800298eb  movups  xmmword ptr [rbp+wndpl.ptMinPosition.y], xmm0
0x1800298ef  movups  xmmword ptr [rbp+wndpl.rcNormalPosition.left], xmm0
0x1800298f3  movups  xmmword ptr [rbp+wndpl.length], xmm0
0x1800298f7  call    cs:__imp_GetWindowPlacement
0x1800298fd  test    eax, eax
0x1800298ff  jz      short loc_18002991F
0x180029901  cmp     [rbp+wndpl.showCmd], 2
0x180029905  jz      short loc_18002991F
0x180029907  movups  xmm0, xmmword ptr [rbp+wndpl.rcNormalPosition.left]
0x18002990b  xor     eax, eax
0x18002990d  cmp     [rbp+wndpl.showCmd], 3
0x180029911  movdqu  xmmword ptr [rbx+74h], xmm0
0x180029916  setnz   al
0x180029919  mov     [rbx+84h], eax
0x18002991f  mov     al, [rbx+1B3h]
0x180029925  lea     rdi, [rbx+74h]
0x180029929  mov     [rdi+14h], al
0x18002992c  test    rdi, rdi
0x18002992f  jz      short loc_180029999
0x180029931  lea     rcx, [rbp+wndpl]; this
0x180029935  mov     qword ptr [rbp+wndpl.length], 0
0x18002993d  mov     qword ptr [rbp+wndpl.showCmd], 0
0x180029945  mov     qword ptr [rbp+wndpl.ptMinPosition.y], 0
0x18002994d  call    ?CreateOrOpenF12RegRoot@F12@@YAJAEAVCRegKey@ATL@@@Z; F12::CreateOrOpenF12RegRoot(ATL::CRegKey &)
0x180029952  test    eax, eax
0x180029954  jz      short loc_180029961
0x180029956  mov     rcx, qword ptr [rbp+wndpl.length]
0x18002995a  test    rcx, rcx
0x18002995d  jz      short loc_180029999
0x18002995f  jmp     short loc_180029993
0x180029961  mov     [rsp+70h+cbData], 18h; cbData
0x180029969  lea     rdx, aWindowpos; "windowpos"
0x180029970  mov     [rsp+70h+lpData], rdi; lpData
0x180029975  mov     r9d, 3; dwType
0x18002997b  mov     rdi, qword ptr [rbp+wndpl.length]
0x18002997f  xor     r8d, r8d; Reserved
0x180029982  mov     rcx, rdi; hKey
0x180029985  call    cs:__imp_RegSetValueExW
0x18002998b  test    rdi, rdi
0x18002998e  jz      short loc_180029999
0x180029990  mov     rcx, rdi; hKey
0x180029993  call    cs:__imp_RegCloseKey
0x180029999  mov     rcx, rbx; this
0x18002999c  call    ?DismissPopupWindow@FrameWindow@@AEAAXXZ; FrameWindow::DismissPopupWindow(void)
0x1800299a1  mov     rcx, [rbp+var_10]
0x1800299a5  xor     rcx, rsp; StackCookie
0x1800299a8  call    __security_check_cookie
0x1800299ad  lea     r11, [rsp+70h+var_s0]
0x1800299b2  mov     rbx, [r11+18h]
0x1800299b6  mov     rdi, [r11+20h]
0x1800299ba  mov     rsp, r11
0x1800299bd  pop     rbp
0x1800299be  retn
```
