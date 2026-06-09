# FrameWindow::Initialize(int,HWND__ *)

- ea: `0x180022c00`
- end: `0x180022f3c`
- name: `?Initialize@FrameWindow@@QEAAJHPEAUHWND__@@@Z`
- size: `828`
- prototype: `__int64 __fastcall(FrameWindow *__hidden this, int nCmdShow, HWND)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180016710`

## callees

- `0x180001800`
- `0x180005e44`
- `0x180020fc0`
- `0x180022c00`
- `0x180028228`
- `0x1800303ac`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180022cc7`
- `ADVAPI32!RegCloseKey` at `0x180022ce2`
- `ADVAPI32!RegCloseKey` at `0x180022dbf`
- `ADVAPI32!RegCloseKey` at `0x180022dd6`
- `ADVAPI32!RegCloseKey` at `0x180022cc7`
- `ADVAPI32!RegCloseKey` at `0x180022ce2`
- `ADVAPI32!RegCloseKey` at `0x180022dbf`
- `ADVAPI32!RegCloseKey` at `0x180022dd6`
- `ADVAPI32!RegOpenKeyExW` at `0x180022c65`
- `ADVAPI32!RegOpenKeyExW` at `0x180022d31`
- `ADVAPI32!RegOpenKeyExW` at `0x180022c65`
- `ADVAPI32!RegOpenKeyExW` at `0x180022d31`
- `ADVAPI32!RegQueryValueExW` at `0x180022caa`
- `ADVAPI32!RegQueryValueExW` at `0x180022d85`
- `ADVAPI32!RegQueryValueExW` at `0x180022caa`
- `ADVAPI32!RegQueryValueExW` at `0x180022d85`
- `USER32!SetWindowPos` at `0x180022ee2`
- `USER32!SetWindowPos` at `0x180022ee2`
- `USER32!ShowWindow` at `0x180022eb8`
- `USER32!ShowWindow` at `0x180022eb8`
- `USER32!SetRect` at `0x180022df5`
- `USER32!SetRect` at `0x180022df5`
- `USER32!UpdateWindow` at `0x180022ef0`
- `USER32!UpdateWindow` at `0x180022ef0`
- `USER32!LoadStringW` at `0x180022e33`
- `USER32!LoadStringW` at `0x180022e33`
- `USER32!LoadMenuW` at `0x180022e47`
- `USER32!LoadMenuW` at `0x180022e47`
- `USER32!LoadAcceleratorsW` at `0x180022e79`
- `USER32!LoadAcceleratorsW` at `0x180022e79`

## pseudocode

```c
int __fastcall FrameWindow::Initialize(FrameWindow *this, int nCmdShow, LPARAM a3)
{
  HKEY v6; // rbx
  int v7; // esi
  HKEY v8; // rsi
  const struct F12::tagFramePlacementState *v9; // rdx
  __int64 v10; // xmm1_8
  _DWORD *v11; // rsi
  HMENU MenuW; // rax
  __int64 v13; // rdx
  HACCEL AcceleratorsW; // rax
  bool v15; // zf
  int result; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v23[16]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h]
  WCHAR Buffer[256]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\F12", 0, 0x20019u, &hKey) )
  {
    v6 = hKey;
    *(_DWORD *)Data = 0;
    Type = 0;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"showconsole", 0, &Type, Data, &cbData) || Type != 4 )
    {
      if ( v6 )
        RegCloseKey(v6);
    }
    else
    {
      v7 = *(_DWORD *)Data;
      if ( v6 )
        RegCloseKey(v6);
      *((_BYTE *)this + 432) = v7 != 0;
    }
  }
  *((_BYTE *)this + 435) = a3 != 0;
  if ( this == (FrameWindow *)-116LL )
    goto LABEL_19;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\F12", 0, 0x20019u, &hKey) )
    goto LABEL_19;
  v8 = hKey;
  cbData = 24;
  v24 = 0;
  *(_DWORD *)Data = 0;
  *(_OWORD *)v23 = 0;
  if ( RegQueryValueExW(hKey, L"windowpos", 0, (LPDWORD)Data, v23, &cbData)
    || *(_DWORD *)Data != 3
    || (unsigned int)F12::ValidateWindowPositions((F12 *)v23, v9) )
  {
    if ( v8 )
      RegCloseKey(v8);
LABEL_19:
    SetRect((LPRECT)((char *)this + 116), 100, 100, 1024, 800);
    v11 = (_DWORD *)((char *)this + 132);
    *((_DWORD *)this + 33) = 1;
    goto LABEL_20;
  }
  v10 = v24;
  *(_OWORD *)((char *)this + 116) = *(_OWORD *)v23;
  *(_QWORD *)((char *)this + 132) = v10;
  if ( v8 )
    RegCloseKey(v8);
  v11 = (_DWORD *)((char *)this + 132);
LABEL_20:
  *((_BYTE *)this + 136) = *((_BYTE *)this + 435);
  Buffer[0] = 0;
  LoadStringW(hInstance, uID, Buffer, 256);
  MenuW = LoadMenuW(hInstance, (LPCWSTR)(unsigned __int16)uID);
  if ( WTL::CFrameWindowImpl<FrameWindow,ATL::CWindow,ATL::CWinTraits<0,262144>>::Create(
         (__int64)this,
         v13,
         (int *)this + 29,
         Buffer,
         (__int64)phkResult,
         (__int64)lpcbData,
         MenuW) )
  {
    AcceleratorsW = LoadAcceleratorsW(hInstance, (LPCWSTR)(unsigned __int16)uID);
    v15 = *((_BYTE *)this + 435) == 0;
    *((_QWORD *)this + 12) = AcceleratorsW;
    if ( !v15 )
    {
      result = FrameWindow::ReparentWindowForDocking(this, a3, 1174405120);
      if ( result )
        goto LABEL_29;
    }
    if ( !*v11 && !*((_BYTE *)this + 435) )
      nCmdShow = 3;
    ShowWindow(*((HWND *)this + 1), nCmdShow);
    if ( SetWindowPos(*((HWND *)this + 1), 0, 0, 0, 0, 0, 0x213u) )
    {
      if ( UpdateWindow(*((HWND *)this + 1)) )
        return 0;
    }
  }
  result = ATL::AtlHresultFromLastError();
  if ( !result )
    return 0;
LABEL_29:
  if ( result >= 0 )
    return -2147467259;
  return result;
}

```

## disassembly

```asm
0x180022c00  mov     [rsp-8+arg_10], rbx
0x180022c05  mov     [rsp-8+arg_18], rsi
0x180022c0a  push    rbp
0x180022c0b  push    rdi
0x180022c0c  push    r13
0x180022c0e  push    r14
0x180022c10  push    r15
0x180022c12  lea     rbp, [rsp-180h]
0x180022c1a  sub     rsp, 280h
0x180022c21  mov     rax, cs:__security_cookie
0x180022c28  xor     rax, rsp
0x180022c2b  mov     [rbp+1A0h+var_30], rax
0x180022c32  mov     r15, r8
0x180022c35  mov     [rsp+2A0h+hKey], 0
0x180022c3e  mov     r14d, edx
0x180022c41  lea     rax, [rsp+2A0h+hKey]
0x180022c46  mov     rdi, rcx
0x180022c49  mov     [rsp+2A0h+phkResult], rax; phkResult
0x180022c4e  xor     r8d, r8d; ulOptions
0x180022c51  lea     rdx, SubKey; "Software\\Microsoft\\F12"
0x180022c58  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180022c5f  mov     r9d, 20019h; samDesired
0x180022c65  call    cs:__imp_RegOpenKeyExW
0x180022c6b  test    eax, eax
0x180022c6d  jnz     short loc_180022CE8
0x180022c6f  mov     rbx, [rsp+2A0h+hKey]
0x180022c74  lea     r9, [rsp+2A0h+Type]; lpType
0x180022c79  mov     dword ptr [rsp+2A0h+Data], eax
0x180022c7d  lea     rdx, ValueName; "showconsole"
0x180022c84  mov     [rsp+2A0h+Type], eax
0x180022c88  xor     r8d, r8d; lpReserved
0x180022c8b  lea     rax, [rsp+2A0h+cbData]
0x180022c90  mov     [rsp+2A0h+cbData], 4
0x180022c98  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x180022c9d  mov     rcx, rbx; hKey
0x180022ca0  lea     rax, [rsp+2A0h+Data]
0x180022ca5  mov     [rsp+2A0h+phkResult], rax; lpData
0x180022caa  call    cs:__imp_RegQueryValueExW
0x180022cb0  test    eax, eax
0x180022cb2  jnz     short loc_180022CDA
0x180022cb4  cmp     [rsp+2A0h+Type], 4
0x180022cb9  jnz     short loc_180022CDA
0x180022cbb  mov     esi, dword ptr [rsp+2A0h+Data]
0x180022cbf  test    rbx, rbx
0x180022cc2  jz      short loc_180022CCD
0x180022cc4  mov     rcx, rbx; hKey
0x180022cc7  call    cs:__imp_RegCloseKey
0x180022ccd  test    esi, esi
0x180022ccf  setnz   al
0x180022cd2  mov     [rdi+1B0h], al
0x180022cd8  jmp     short loc_180022CE8
0x180022cda  test    rbx, rbx
0x180022cdd  jz      short loc_180022CE8
0x180022cdf  mov     rcx, rbx; hKey
0x180022ce2  call    cs:__imp_RegCloseKey
0x180022ce8  test    r15, r15
0x180022ceb  lea     rbx, [rdi+74h]
0x180022cef  mov     r13d, 3
0x180022cf5  setnz   al
0x180022cf8  mov     [rdi+1B3h], al
0x180022cfe  test    rbx, rbx
0x180022d01  jz      loc_180022DDC
0x180022d07  lea     rax, [rsp+2A0h+hKey]
0x180022d0c  mov     [rsp+2A0h+hKey], 0
0x180022d15  mov     r9d, 20019h; samDesired
0x180022d1b  mov     [rsp+2A0h+phkResult], rax; phkResult
0x180022d20  xor     r8d, r8d; ulOptions
0x180022d23  lea     rdx, SubKey; "Software\\Microsoft\\F12"
0x180022d2a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180022d31  call    cs:__imp_RegOpenKeyExW
0x180022d37  test    eax, eax
0x180022d39  jnz     loc_180022DDC
0x180022d3f  mov     rsi, [rsp+2A0h+hKey]
0x180022d44  lea     r9, [rsp+2A0h+Data]; lpType
0x180022d49  xor     eax, eax
0x180022d4b  mov     [rsp+2A0h+cbData], 18h
0x180022d53  mov     [rsp+2A0h+var_238], rax
0x180022d58  lea     rdx, aWindowpos; "windowpos"
0x180022d5f  mov     dword ptr [rsp+2A0h+Data], eax
0x180022d63  xorps   xmm0, xmm0
0x180022d66  lea     rax, [rsp+2A0h+cbData]
0x180022d6b  xor     r8d, r8d; lpReserved
0x180022d6e  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x180022d73  mov     rcx, rsi; hKey
0x180022d76  lea     rax, [rsp+2A0h+var_248]
0x180022d7b  mov     [rsp+2A0h+phkResult], rax; lpData
0x180022d80  movups  xmmword ptr [rsp+2A0h+var_248], xmm0
0x180022d85  call    cs:__imp_RegQueryValueExW
0x180022d8b  test    eax, eax
0x180022d8d  jnz     short loc_180022DCE
0x180022d8f  cmp     dword ptr [rsp+2A0h+Data], r13d
0x180022d94  jnz     short loc_180022DCE
0x180022d96  lea     rcx, [rsp+2A0h+var_248]; this
0x180022d9b  call    ?ValidateWindowPositions@F12@@YAJPEBUtagFramePlacementState@1@@Z; F12::ValidateWindowPositions(F12::tagFramePlacementState const *)
0x180022da0  test    eax, eax
0x180022da2  jnz     short loc_180022DCE
0x180022da4  movsd   xmm1, [rsp+2A0h+var_238]
0x180022daa  movups  xmm0, xmmword ptr [rsp+2A0h+var_248]
0x180022daf  movups  xmmword ptr [rbx], xmm0
0x180022db2  movsd   qword ptr [rbx+10h], xmm1
0x180022db7  test    rsi, rsi
0x180022dba  jz      short loc_180022DC5
0x180022dbc  mov     rcx, rsi; hKey
0x180022dbf  call    cs:__imp_RegCloseKey
0x180022dc5  lea     rsi, [rdi+84h]
0x180022dcc  jmp     short loc_180022E08
0x180022dce  test    rsi, rsi
0x180022dd1  jz      short loc_180022DDC
0x180022dd3  mov     rcx, rsi; hKey
0x180022dd6  call    cs:__imp_RegCloseKey
0x180022ddc  mov     edx, 64h ; 'd'; xLeft
0x180022de1  mov     dword ptr [rsp+2A0h+phkResult], 320h; yBottom
0x180022de9  mov     r8d, edx; yTop
0x180022dec  mov     r9d, 400h; xRight
0x180022df2  mov     rcx, rbx; lprc
0x180022df5  call    cs:__imp_SetRect
0x180022dfb  lea     rsi, [rdi+84h]
0x180022e02  mov     dword ptr [rsi], 1
0x180022e08  mov     al, [rdi+1B3h]
0x180022e0e  lea     r8, [rsp+2A0h+Buffer]; lpBuffer
0x180022e13  mov     [rdi+88h], al
0x180022e19  mov     r9d, 100h; cchBufferMax
0x180022e1f  mov     edx, cs:uID; uID
0x180022e25  xor     eax, eax
0x180022e27  mov     rcx, cs:hInstance; hInstance
0x180022e2e  mov     [rsp+2A0h+Buffer], ax
0x180022e33  call    cs:__imp_LoadStringW
0x180022e39  movzx   edx, word ptr cs:uID; lpMenuName
0x180022e40  mov     rcx, cs:hInstance; hInstance
0x180022e47  call    cs:__imp_LoadMenuW
0x180022e4d  lea     r9, [rsp+2A0h+Buffer]
0x180022e52  mov     r8, rbx
0x180022e55  mov     rcx, rdi
0x180022e58  mov     qword ptr [rsp+2A0h+uFlags], rax
0x180022e5d  call    ?Create@?$CFrameWindowImpl@VFrameWindow@@VCWindow@ATL@@V?$CWinTraits@$0A@$0EAAAA@@3@@WTL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@ATL@@PEBGKKPEAUHMENU__@@PEAX@Z; WTL::CFrameWindowImpl<FrameWindow,ATL::CWindow,ATL::CWinTraits<0,262144>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,HMENU__ *,void *)
0x180022e62  test    rax, rax
0x180022e65  jz      loc_180022EFA
0x180022e6b  movzx   edx, word ptr cs:uID; lpTableName
0x180022e72  mov     rcx, cs:hInstance; hInstance
0x180022e79  call    cs:__imp_LoadAcceleratorsW
0x180022e7f  cmp     byte ptr [rdi+1B3h], 0
0x180022e86  mov     [rdi+60h], rax
0x180022e8a  jz      short loc_180022EA1
0x180022e8c  mov     r8d, 46000000h; __int64
0x180022e92  mov     rdx, r15; HWND
0x180022e95  mov     rcx, rdi; this
0x180022e98  call    ?ReparentWindowForDocking@FrameWindow@@AEAAJPEAUHWND__@@_J@Z; FrameWindow::ReparentWindowForDocking(HWND__ *,__int64)
0x180022e9d  test    eax, eax
0x180022e9f  jnz     short loc_180022F03
0x180022ea1  cmp     dword ptr [rsi], 0
0x180022ea4  jnz     short loc_180022EB1
0x180022ea6  cmp     byte ptr [rdi+1B3h], 0
0x180022ead  cmovz   r14d, r13d
0x180022eb1  mov     rcx, [rdi+8]; hWnd
0x180022eb5  mov     edx, r14d; nCmdShow
0x180022eb8  call    cs:__imp_ShowWindow
0x180022ebe  mov     rcx, [rdi+8]; hWnd
0x180022ec2  xor     r9d, r9d; Y
0x180022ec5  mov     [rsp+2A0h+uFlags], 213h; uFlags
0x180022ecd  xor     r8d, r8d; X
0x180022ed0  mov     dword ptr [rsp+2A0h+lpcbData], 0; cy
0x180022ed8  xor     edx, edx; hWndInsertAfter
0x180022eda  mov     dword ptr [rsp+2A0h+phkResult], 0; cx
0x180022ee2  call    cs:__imp_SetWindowPos
0x180022ee8  test    eax, eax
0x180022eea  jz      short loc_180022EFA
0x180022eec  mov     rcx, [rdi+8]; hWnd
0x180022ef0  call    cs:__imp_UpdateWindow
0x180022ef6  test    eax, eax
0x180022ef8  jnz     short loc_180022F0F
0x180022efa  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180022eff  test    eax, eax
0x180022f01  jz      short loc_180022F0F
0x180022f03  test    eax, eax
0x180022f05  mov     ecx, 80004005h
0x180022f0a  cmovns  eax, ecx
0x180022f0d  jmp     short loc_180022F11
0x180022f0f  xor     eax, eax
0x180022f11  mov     rcx, [rbp+1A0h+var_30]
0x180022f18  xor     rcx, rsp; StackCookie
0x180022f1b  call    __security_check_cookie
0x180022f20  lea     r11, [rsp+2A0h+var_20]
0x180022f28  mov     rbx, [r11+40h]
0x180022f2c  mov     rsi, [r11+48h]
0x180022f30  mov     rsp, r11
0x180022f33  pop     r15
0x180022f35  pop     r14
0x180022f37  pop     r13
0x180022f39  pop     rdi
0x180022f3a  pop     rbp
0x180022f3b  retn
```
