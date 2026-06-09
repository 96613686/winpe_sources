# CbsFindServicingStackDirectory

- ea: `0x180040bb0`
- end: `0x180040dd2`
- name: `CbsFindServicingStackDirectory`
- size: `546`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18002d2b0`
- `0x180040a2c`
- `0x180040b30`
- `0x180040bb0`
- `0x180097e20`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x180040d5d`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180040d5d`
- `KERNEL32!GetLastError` at `0x180040d6d`
- `KERNEL32!GetLastError` at `0x180040d6d`
- `ADVAPI32!RegOpenKeyExW` at `0x180040c2a`
- `ADVAPI32!RegOpenKeyExW` at `0x180040c2a`
- `ADVAPI32!RegEnumValueW` at `0x180040ccf`
- `ADVAPI32!RegEnumValueW` at `0x180040ccf`
- `ADVAPI32!RegCloseKey` at `0x180040da0`
- `ADVAPI32!RegCloseKey` at `0x180040da0`

## string_xrefs

- `0x180040c1c`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\Version`

## pseudocode

```c
__int64 __fastcall CbsFindServicingStackDirectory(WCHAR *a1, DWORD a2, unsigned int *a3, unsigned int *a4)
{
  signed int LastError; // eax
  unsigned int v7; // ebx
  bool v8; // cc
  int v9; // r15d
  unsigned int v10; // edi
  unsigned int v11; // esi
  DWORD i; // r14d
  unsigned __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nSize; // [rsp+48h] [rbp-B8h]
  LPWSTR lpDst; // [rsp+50h] [rbp-B0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-98h] BYREF
  wchar_t Data[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Src[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR ValueName[264]; // [rsp+490h] [rbp+390h] BYREF

  nSize = a2;
  lpDst = a1;
  hKey = 0;
  memset(Src, 0, 0x208u);
  LastError = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\Version",
                0,
                0x20019u,
                &hKey);
  v7 = LastError;
  v8 = LastError <= 0;
  if ( LastError )
  {
LABEL_2:
    if ( !v8 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_19;
  }
  v9 = 0;
  v10 = 0;
  v11 = 0;
  for ( i = 0; ; ++i )
  {
    cchValueName = 260;
    Type = 0;
    memset(Data, 0, 0x208u);
    cbData = 518;
    v14 = 0;
    LastError = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData);
    v7 = LastError;
    if ( LastError == 259 )
      break;
    v8 = LastError <= 0;
    if ( LastError )
      goto LABEL_2;
    if ( !(unsigned int)FileVersionFromString_0(ValueName, (char *)&v14 + 4, &v14) && __PAIR64__(v10, v11) < v14 )
    {
      v11 = v14;
      v9 = 1;
      v10 = HIDWORD(v14);
      StringCchCopyW(Src, 0x104u, Data);
    }
  }
  if ( !v9 )
  {
    v7 = -2147023728;
    goto LABEL_19;
  }
  if ( !ExpandEnvironmentStringsW(Src, lpDst, nSize) )
  {
    LastError = GetLastError();
    v7 = LastError;
    v8 = LastError <= 0;
    goto LABEL_2;
  }
  v7 = 0;
  if ( a3 )
    *a3 = v10;
  if ( a4 )
    *a4 = v11;
LABEL_19:
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x180040bb0  push    rbp
0x180040bb2  push    rbx
0x180040bb3  push    rsi
0x180040bb4  push    rdi
0x180040bb5  push    r12
0x180040bb7  push    r13
0x180040bb9  push    r14
0x180040bbb  push    r15
0x180040bbd  lea     rbp, [rsp-5B8h]
0x180040bc5  sub     rsp, 6B8h
0x180040bcc  mov     rax, cs:__security_cookie
0x180040bd3  xor     rax, rsp
0x180040bd6  mov     [rbp+5F0h+var_50], rax
0x180040bdd  mov     r13, r8
0x180040be0  mov     [rsp+6F0h+nSize], edx
0x180040be4  mov     [rsp+6F0h+lpDst], rcx
0x180040be9  xor     edx, edx; Val
0x180040beb  mov     r8d, 208h; Size
0x180040bf1  mov     [rsp+6F0h+hKey], 0
0x180040bfa  lea     rcx, [rbp+5F0h+Src]; void *
0x180040c01  mov     r12, r9
0x180040c04  call    memset
0x180040c09  lea     rax, [rsp+6F0h+hKey]
0x180040c0e  mov     r9d, 20019h; samDesired
0x180040c14  xor     r8d, r8d; ulOptions
0x180040c17  mov     [rsp+6F0h+phkResult], rax; phkResult
0x180040c1c  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180040c23  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180040c2a  call    cs:__imp_RegOpenKeyExW
0x180040c31  nop     dword ptr [rax+rax+00h]
0x180040c36  mov     ebx, eax
0x180040c38  test    eax, eax
0x180040c3a  jz      short loc_180040C50
0x180040c3c  jle     loc_180040D96
0x180040c42  movzx   ebx, ax
0x180040c45  or      ebx, 80070000h
0x180040c4b  jmp     loc_180040D96
0x180040c50  xor     r15d, r15d
0x180040c53  xor     edi, edi
0x180040c55  xor     esi, esi
0x180040c57  xor     r14d, r14d
0x180040c5a  xor     edx, edx; Val
0x180040c5c  mov     [rsp+6F0h+cchValueName], 104h
0x180040c64  mov     r8d, 208h; Size
0x180040c6a  mov     [rsp+6F0h+Type], 0
0x180040c72  lea     rcx, [rsp+6F0h+Data]; void *
0x180040c77  call    memset
0x180040c7c  mov     rcx, [rsp+6F0h+hKey]; hKey
0x180040c81  lea     rax, [rsp+6F0h+cbData]
0x180040c86  mov     [rsp+6F0h+lpcbData], rax; lpcbData
0x180040c8b  lea     r9, [rsp+6F0h+cchValueName]; lpcchValueName
0x180040c90  lea     rax, [rsp+6F0h+Data]
0x180040c95  mov     [rsp+6F0h+cbData], 206h
0x180040c9d  mov     [rsp+6F0h+lpData], rax; lpData
0x180040ca2  lea     r8, [rbp+5F0h+ValueName]; lpValueName
0x180040ca9  lea     rax, [rsp+6F0h+Type]
0x180040cae  mov     dword ptr [rsp+6F0h+var_6B0+4], 0
0x180040cb6  mov     [rsp+6F0h+lpType], rax; lpType
0x180040cbb  mov     edx, r14d; dwIndex
0x180040cbe  mov     [rsp+6F0h+phkResult], 0; lpReserved
0x180040cc7  mov     dword ptr [rsp+6F0h+var_6B0], 0
0x180040ccf  call    cs:__imp_RegEnumValueW
0x180040cd6  nop     dword ptr [rax+rax+00h]
0x180040cdb  mov     ebx, eax
0x180040cdd  cmp     eax, 103h
0x180040ce2  jz      short loc_180040D40
0x180040ce4  test    eax, eax
0x180040ce6  jnz     loc_180040C3C
0x180040cec  lea     r8, [rsp+6F0h+var_6B0]
0x180040cf1  lea     rdx, [rsp+6F0h+var_6B0+4]
0x180040cf6  lea     rcx, [rbp+5F0h+ValueName]
0x180040cfd  call    FileVersionFromString_0
0x180040d02  test    eax, eax
0x180040d04  jnz     short loc_180040D38
0x180040d06  mov     eax, dword ptr [rsp+6F0h+var_6B0+4]
0x180040d0a  cmp     edi, eax
0x180040d0c  jb      short loc_180040D16
0x180040d0e  jnz     short loc_180040D38
0x180040d10  cmp     esi, dword ptr [rsp+6F0h+var_6B0]
0x180040d14  jnb     short loc_180040D38
0x180040d16  mov     esi, dword ptr [rsp+6F0h+var_6B0]
0x180040d1a  lea     r8, [rsp+6F0h+Data]; wchar_t *
0x180040d1f  mov     edx, 104h; unsigned __int64
0x180040d24  lea     rcx, [rbp+5F0h+Src]; wchar_t *
0x180040d2b  mov     r15d, 1
0x180040d31  mov     edi, eax
0x180040d33  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180040d38  inc     r14d
0x180040d3b  jmp     loc_180040C5A
0x180040d40  test    r15d, r15d
0x180040d43  jnz     short loc_180040D4C
0x180040d45  mov     ebx, 80070490h
0x180040d4a  jmp     short loc_180040D96
0x180040d4c  mov     r8d, [rsp+6F0h+nSize]; nSize
0x180040d51  lea     rcx, [rbp+5F0h+Src]; lpSrc
0x180040d58  mov     rdx, [rsp+6F0h+lpDst]; lpDst
0x180040d5d  call    cs:__imp_ExpandEnvironmentStringsW
0x180040d64  nop     dword ptr [rax+rax+00h]
0x180040d69  test    eax, eax
0x180040d6b  jnz     short loc_180040D82
0x180040d6d  call    cs:__imp_GetLastError
0x180040d74  nop     dword ptr [rax+rax+00h]
0x180040d79  mov     ebx, eax
0x180040d7b  test    eax, eax
0x180040d7d  jmp     loc_180040C3C
0x180040d82  xor     ebx, ebx
0x180040d84  test    r13, r13
0x180040d87  jz      short loc_180040D8D
0x180040d89  mov     [r13+0], edi
0x180040d8d  test    r12, r12
0x180040d90  jz      short loc_180040D96
0x180040d92  mov     [r12], esi
0x180040d96  mov     rcx, [rsp+6F0h+hKey]; hKey
0x180040d9b  test    rcx, rcx
0x180040d9e  jz      short loc_180040DAC
0x180040da0  call    cs:__imp_RegCloseKey
0x180040da7  nop     dword ptr [rax+rax+00h]
0x180040dac  mov     eax, ebx
0x180040dae  mov     rcx, [rbp+5F0h+var_50]
0x180040db5  xor     rcx, rsp; StackCookie
0x180040db8  call    __security_check_cookie
0x180040dbd  add     rsp, 6B8h
0x180040dc4  pop     r15
0x180040dc6  pop     r14
0x180040dc8  pop     r13
0x180040dca  pop     r12
0x180040dcc  pop     rdi
0x180040dcd  pop     rsi
0x180040dce  pop     rbx
0x180040dcf  pop     rbp
0x180040dd0  retn
```
