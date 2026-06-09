# UseRunOnceEx(void)

- ea: `0x18000ae68`
- end: `0x18000b0c7`
- name: `?UseRunOnceEx@@YAHXZ`
- size: `607`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800079c0`
- `0x180009c14`

## callees

- `0x1800022bc`
- `0x180003180`
- `0x18000ae68`
- `0x18000b710`
- `0x18001a688`
- `0x18001b294`
- `0x18001b94e`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetWindowsDirectoryW` at `0x18000af57`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000af57`
- `KERNEL32!GetSystemDirectoryW` at `0x18000aedc`
- `KERNEL32!GetSystemDirectoryW` at `0x18000aedc`
- `ADVAPI32!RegCreateKeyExW` at `0x18000affe`
- `ADVAPI32!RegCreateKeyExW` at `0x18000affe`
- `ADVAPI32!RegCloseKey` at `0x18000b095`
- `ADVAPI32!RegCloseKey` at `0x18000b09d`
- `ADVAPI32!RegCloseKey` at `0x18000b095`
- `ADVAPI32!RegCloseKey` at `0x18000b09d`
- `ADVAPI32!RegSetValueExW` at `0x18000b084`
- `ADVAPI32!RegSetValueExW` at `0x18000b084`

## string_xrefs

- `0x18000aeeb`: `iernonce.dll`
- `0x18000aef7`: `iernonce.dll`
- `0x18000b00c`: `rundll32.exe `

## pseudocode

```c
__int64 UseRunOnceEx(void)
{
  unsigned int v0; // ebx
  __int64 v1; // rax
  ULONG dwOptions; // [rsp+20h] [rbp-E0h]
  ULONG dwOptionsa; // [rsp+20h] [rbp-E0h]
  DWORD pdwMSVer; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pdwLSVer[2]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition[4]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPathOut; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v9[526]; // [rsp+72h] [rbp-8Eh] BYREF
  WCHAR Buffer; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v11[526]; // [rsp+282h] [rbp+182h] BYREF

  pdwMSVer = 0;
  pdwLSVer[0] = 0;
  Buffer = 0;
  memset_0(v11, 0, 0x206u);
  pszPathOut = 0;
  memset_0(v9, 0, 0x206u);
  dwDisposition[0] = 0;
  GetSystemDirectoryW(&Buffer, 0x104u);
  PathIsUnc2(L"iernonce.dll");
  PathCchCombineEx(&Buffer, 0x104u, &Buffer, L"iernonce.dll", dwOptions);
  GetVersionFromFileW(&Buffer, &pdwMSVer, pdwLSVer, 1);
  if ( pdwMSVer > 0x40047 || (v0 = 0, pdwMSVer == 262215) && pdwLSVer[0] >= 0xDB0000 )
  {
    GetWindowsDirectoryW(&pszPathOut, 0x104u);
    PathIsUnc2(L"explorer.exe");
    PathCchCombineEx(&pszPathOut, 0x104u, &pszPathOut, L"explorer.exe", dwOptionsa);
    GetVersionFromFileW(&pszPathOut, &pdwMSVer, pdwLSVer, 1);
    if ( pdwMSVer < 0x40047 || pdwMSVer == 262215 && pdwLSVer[0] < 0xDB0000 )
    {
      *(_QWORD *)pdwLSVer = 0;
      if ( !RegCreateKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\RunOnce",
              0,
              0,
              0,
              0x20006u,
              0,
              (PHKEY)pdwLSVer,
              dwDisposition) )
      {
        StringCchCopyW(&pszPathOut, 0x104u, (size_t *)L"rundll32.exe ");
        StringCchCatW(&pszPathOut, 260, &Buffer);
        StringCchCatW(&pszPathOut, 260, L",RunOnceExProcess");
        v1 = -1;
        do
          ++v1;
        while ( *(_WORD *)&v9[2 * v1 - 2] );
        if ( RegSetValueExW(*(HKEY *)pdwLSVer, L"RunOnceEx", 0, 1u, (const BYTE *)&pszPathOut, 2 * v1 + 2) )
        {
          v0 = 0;
          RegCloseKey(*(HKEY *)pdwLSVer);
          return v0;
        }
        RegCloseKey(*(HKEY *)pdwLSVer);
      }
    }
    return 1;
  }
  return v0;
}

```

## disassembly

```asm
0x18000ae68  push    rbp
0x18000ae6a  push    rbx
0x18000ae6b  push    rsi
0x18000ae6c  push    rdi
0x18000ae6d  push    r14
0x18000ae6f  lea     rbp, [rsp-3A0h]
0x18000ae77  sub     rsp, 4A0h
0x18000ae7e  mov     rax, cs:__security_cookie
0x18000ae85  xor     rax, rsp
0x18000ae88  mov     [rbp+3C0h+var_30], rax
0x18000ae8f  xor     edi, edi
0x18000ae91  lea     rcx, [rbp+3C0h+var_23E]; void *
0x18000ae98  mov     ebx, 206h
0x18000ae9d  mov     [rsp+4C0h+pdwMSVer], edi
0x18000aea1  mov     r8d, ebx; Size
0x18000aea4  mov     [rsp+4C0h+pdwLSVer], edi
0x18000aea8  xor     edx, edx; Val
0x18000aeaa  mov     [rbp+3C0h+Buffer], di
0x18000aeb1  call    memset_0
0x18000aeb6  mov     r8d, ebx; Size
0x18000aeb9  mov     [rsp+4C0h+pszPathOut], di
0x18000aebe  xor     edx, edx; Val
0x18000aec0  lea     rcx, [rsp+4C0h+var_44E]; void *
0x18000aec5  call    memset_0
0x18000aeca  mov     esi, 104h
0x18000aecf  mov     [rsp+4C0h+dwDisposition], edi
0x18000aed3  mov     edx, esi; uSize
0x18000aed5  lea     rcx, [rbp+3C0h+Buffer]; lpBuffer
0x18000aedc  call    cs:__imp_GetSystemDirectoryW
0x18000aee2  lea     r8, IsBackslash
0x18000aee9  xor     edx, edx
0x18000aeeb  lea     rcx, aIernonceDll; "iernonce.dll"
0x18000aef2  call    PathIsUnc2
0x18000aef7  lea     r9, aIernonceDll; "iernonce.dll"
0x18000aefe  mov     edx, esi; cchPathOut
0x18000af00  lea     r8, [rbp+3C0h+Buffer]; pszPathIn
0x18000af07  lea     rcx, [rbp+3C0h+Buffer]; pszPathOut
0x18000af0e  call    PathCchCombineEx
0x18000af13  lea     r9d, [rdi+1]; bVersion
0x18000af17  lea     r8, [rsp+4C0h+pdwLSVer]; pdwLSVer
0x18000af1c  lea     rdx, [rsp+4C0h+pdwMSVer]; pdwMSVer
0x18000af21  lea     rcx, [rbp+3C0h+Buffer]; lpszFilename
0x18000af28  call    GetVersionFromFileW
0x18000af2d  mov     r14d, 40047h
0x18000af33  cmp     [rsp+4C0h+pdwMSVer], r14d
0x18000af38  ja      short loc_18000AF50
0x18000af3a  mov     ebx, edi
0x18000af3c  jnz     loc_18000B0A8
0x18000af42  cmp     [rsp+4C0h+pdwLSVer], 0DB0000h
0x18000af4a  jb      loc_18000B0A8
0x18000af50  mov     edx, esi; uSize
0x18000af52  lea     rcx, [rsp+4C0h+pszPathOut]; lpBuffer
0x18000af57  call    cs:__imp_GetWindowsDirectoryW
0x18000af5d  lea     r8, IsBackslash
0x18000af64  xor     edx, edx
0x18000af66  lea     rcx, aExplorerExe; "explorer.exe"
0x18000af6d  call    PathIsUnc2
0x18000af72  lea     r9, aExplorerExe; "explorer.exe"
0x18000af79  mov     rdx, rsi; cchPathOut
0x18000af7c  lea     r8, [rsp+4C0h+pszPathOut]; pszPathIn
0x18000af81  lea     rcx, [rsp+4C0h+pszPathOut]; pszPathOut
0x18000af86  call    PathCchCombineEx
0x18000af8b  mov     r9d, 1; bVersion
0x18000af91  lea     r8, [rsp+4C0h+pdwLSVer]; pdwLSVer
0x18000af96  lea     rdx, [rsp+4C0h+pdwMSVer]; pdwMSVer
0x18000af9b  lea     rcx, [rsp+4C0h+pszPathOut]; lpszFilename
0x18000afa0  call    GetVersionFromFileW
0x18000afa5  cmp     [rsp+4C0h+pdwMSVer], r14d
0x18000afaa  jb      short loc_18000AFC0
0x18000afac  jnz     loc_18000B0A3
0x18000afb2  cmp     [rsp+4C0h+pdwLSVer], 0DB0000h
0x18000afba  jnb     loc_18000B0A3
0x18000afc0  lea     rax, [rsp+4C0h+dwDisposition]
0x18000afc5  mov     qword ptr [rsp+4C0h+pdwLSVer], rdi
0x18000afca  mov     [rsp+4C0h+lpdwDisposition], rax; lpdwDisposition
0x18000afcf  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000afd6  lea     rax, [rsp+4C0h+pdwLSVer]
0x18000afdb  xor     r9d, r9d; lpClass
0x18000afde  mov     [rsp+4C0h+phkResult], rax; phkResult
0x18000afe3  xor     r8d, r8d; Reserved
0x18000afe6  mov     [rsp+4C0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000afeb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000aff2  mov     [rsp+4C0h+samDesired], 20006h; samDesired
0x18000affa  mov     [rsp+4C0h+dwOptions], edi; dwOptions
0x18000affe  call    cs:__imp_RegCreateKeyExW
0x18000b004  test    eax, eax
0x18000b006  jnz     loc_18000B0A3
0x18000b00c  lea     r8, aRundll32Exe; "rundll32.exe "
0x18000b013  mov     rdx, rsi; unsigned __int64
0x18000b016  lea     rcx, [rsp+4C0h+pszPathOut]; unsigned __int16 *
0x18000b01b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b020  lea     r8, [rbp+3C0h+Buffer]; unsigned __int16 *
0x18000b027  mov     rdx, rsi; unsigned __int64
0x18000b02a  lea     rcx, [rsp+4C0h+pszPathOut]; unsigned __int16 *
0x18000b02f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b034  lea     r8, aRunonceexproce; ",RunOnceExProcess"
0x18000b03b  mov     rdx, rsi; unsigned __int64
0x18000b03e  lea     rcx, [rsp+4C0h+pszPathOut]; unsigned __int16 *
0x18000b043  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b048  lea     rcx, [rsp+4C0h+pszPathOut]
0x18000b04d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b051  inc     rax
0x18000b054  cmp     [rcx+rax*2], di
0x18000b058  jnz     short loc_18000B051
0x18000b05a  mov     rcx, qword ptr [rsp+4C0h+pdwLSVer]; hKey
0x18000b05f  lea     eax, ds:2[rax*2]
0x18000b066  mov     [rsp+4C0h+samDesired], eax; cbData
0x18000b06a  lea     rdx, aRunonceex; "RunOnceEx"
0x18000b071  lea     rax, [rsp+4C0h+pszPathOut]
0x18000b076  mov     r9d, 1; dwType
0x18000b07c  xor     r8d, r8d; Reserved
0x18000b07f  mov     qword ptr [rsp+4C0h+dwOptions], rax; lpData
0x18000b084  call    cs:__imp_RegSetValueExW
0x18000b08a  mov     rcx, qword ptr [rsp+4C0h+pdwLSVer]; hKey
0x18000b08f  test    eax, eax
0x18000b091  jz      short loc_18000B09D
0x18000b093  mov     ebx, edi
0x18000b095  call    cs:__imp_RegCloseKey
0x18000b09b  jmp     short loc_18000B0A8
0x18000b09d  call    cs:__imp_RegCloseKey
0x18000b0a3  mov     ebx, 1
0x18000b0a8  mov     eax, ebx
0x18000b0aa  mov     rcx, [rbp+3C0h+var_30]
0x18000b0b1  xor     rcx, rsp; StackCookie
0x18000b0b4  call    __security_check_cookie
0x18000b0b9  add     rsp, 4A0h
0x18000b0c0  pop     r14
0x18000b0c2  pop     rdi
0x18000b0c3  pop     rsi
0x18000b0c4  pop     rbx
0x18000b0c5  pop     rbp
0x18000b0c6  retn
```
