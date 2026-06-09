# HrBrowsePicture

- ea: `0x180001cb0`
- end: `0x180001f42`
- name: `HrBrowsePicture`
- size: `658`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001cb0`
- `0x180001f50`
- `0x180004640`
- `0x180012cb4`
- `0x180012f8e`
- `0x180012fc0`

## import_xrefs

- `SHLWAPI!SHGetValueW` at `0x180001e16`
- `SHLWAPI!SHGetValueW` at `0x180001e16`
- `SHLWAPI!SHSetValueW` at `0x180001ef9`
- `SHLWAPI!SHSetValueW` at `0x180001ef9`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180001ea8`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180001ea8`
- `SHLWAPI!PathFileExistsW` at `0x180001e30`
- `SHLWAPI!PathFileExistsW` at `0x180001e30`
- `USER32!LoadStringW` at `0x180001d2b`
- `USER32!LoadStringW` at `0x180001d52`
- `USER32!LoadStringW` at `0x180001d2b`
- `USER32!LoadStringW` at `0x180001d52`
- `SHELL32!SHGetSpecialFolderPathW` at `0x180001e47`
- `SHELL32!SHGetSpecialFolderPathW` at `0x180001e5d`
- `SHELL32!SHGetSpecialFolderPathW` at `0x180001e47`
- `SHELL32!SHGetSpecialFolderPathW` at `0x180001e5d`

## string_xrefs

- `0x180001d98`: `Picture Path`
- `0x180001ed8`: `Picture Path`

## pseudocode

```c
__int64 __fastcall HrBrowsePicture(HWND a1, unsigned __int16 *a2, int a3)
{
  unsigned __int64 v3; // r14
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  bool v8; // sf
  __int64 v9; // rax
  DWORD pcbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pdwType[3]; // [rsp+34h] [rbp-CCh] BYREF
  tagOFNW v13; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPath[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR pvData[264]; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int16 v16[264]; // [rsp+500h] [rbp+400h] BYREF
  WCHAR Buffer[512]; // [rsp+710h] [rbp+610h] BYREF
  WCHAR v18[512]; // [rsp+B10h] [rbp+A10h] BYREF

  v3 = a3;
  pvData[0] = 0;
  v18[0] = 0;
  Buffer[0] = 0;
  v16[0] = 0;
  pszPath[0] = 0;
  v6 = -2147467259;
  if ( LoadStringW(g_hInst, 0x7D4u, Buffer, 512) && LoadStringW(g_hInst, 0x7D5u, v18, 512) )
  {
    ReplaceCharsW(Buffer, 124, 0);
    memset_0(&v13, 0, sizeof(v13));
    v13.hInstance = g_hInst;
    v13.lStructSize = 152;
    v13.lpstrFilter = Buffer;
    v13.hwndOwner = a1;
    v13.lpstrFile = v16;
    v13.nFilterIndex = 5;
    v13.lpstrTitle = v18;
    v13.nMaxFile = 260;
    v13.Flags = 528392;
    pdwType[0] = 0;
    pcbData = 520;
    pszPath[0] = 0;
    v7 = SHGetValueW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Windows Mail",
           L"Picture Path",
           pdwType,
           pszPath,
           &pcbData);
    v8 = v7 < 0;
    if ( v7 > 0 )
      v8 = 1;
    if ( !v8 && PathFileExistsW(pszPath)
      || SHGetSpecialFolderPathW(0, pszPath, 39, 0)
      || SHGetSpecialFolderPathW(0, pszPath, 5, 0) )
    {
      v13.lpstrInitialDir = pszPath;
    }
    else
    {
      v13.lpstrInitialDir = 0;
    }
    if ( GetOpenFileNameW(&v13) )
    {
      if ( (int)StringCchCopyW(pvData, 0x104u, v16) >= 0 && PathRemoveFileSpecW(pvData) )
      {
        v9 = -1;
        do
          ++v9;
        while ( pvData[v9] );
        SHSetValueW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows Mail", L"Picture Path", 1u, pvData, 2 * v9 + 2);
      }
      return (unsigned int)StringCchCopyW(a2, v3, v16);
    }
    else
    {
      return 1;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180001cb0  mov     [rsp-8+arg_18], rbx
0x180001cb5  push    rbp
0x180001cb6  push    rsi
0x180001cb7  push    rdi
0x180001cb8  push    r14
0x180001cba  push    r15
0x180001cbc  lea     rbp, [rsp-0E20h]
0x180001cc4  sub     rsp, 0F20h
0x180001ccb  mov     rax, cs:__security_cookie
0x180001cd2  xor     rax, rsp
0x180001cd5  mov     [rbp+0E40h+var_30], rax
0x180001cdc  xor     r15d, r15d
0x180001cdf  movsxd  r14, r8d
0x180001ce2  mov     rsi, rdx
0x180001ce5  mov     [rbp+0E40h+var_C50], r15w
0x180001ced  mov     rdi, rcx
0x180001cf0  mov     [rbp+0E40h+var_430], r15w
0x180001cf8  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x180001cff  lea     r8, [rbp+0E40h+Buffer]; lpBuffer
0x180001d06  mov     edx, 7D4h; uID
0x180001d0b  mov     [rbp+0E40h+Buffer], r15w
0x180001d13  mov     r9d, 200h; cchBufferMax
0x180001d19  mov     [rbp+0E40h+var_A40], r15w
0x180001d21  mov     [rbp+0E40h+pszPath], r15w
0x180001d26  mov     ebx, 80004005h
0x180001d2b  call    cs:__imp_LoadStringW
0x180001d31  test    eax, eax
0x180001d33  jz      loc_180001F1A
0x180001d39  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x180001d40  lea     r8, [rbp+0E40h+var_430]; lpBuffer
0x180001d47  mov     r9d, 200h; cchBufferMax
0x180001d4d  mov     edx, 7D5h; uID
0x180001d52  call    cs:__imp_LoadStringW
0x180001d58  test    eax, eax
0x180001d5a  jz      loc_180001F1A
0x180001d60  xor     r8d, r8d
0x180001d63  lea     edx, [r15+7Ch]
0x180001d67  lea     rcx, [rbp+0E40h+Buffer]
0x180001d6e  call    ReplaceCharsW
0x180001d73  mov     ebx, 98h
0x180001d78  lea     rcx, [rsp+0F40h+var_F00]; void *
0x180001d7d  mov     r8d, ebx; Size
0x180001d80  xor     edx, edx; Val
0x180001d82  call    memset_0
0x180001d87  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x180001d8e  lea     r9, [rsp+0F40h+pdwType]; pdwType
0x180001d93  mov     [rsp+0F40h+var_F00.hInstance], rax
0x180001d98  lea     r8, c_szwPicturePathValueName; "Picture Path"
0x180001d9f  lea     rax, [rbp+0E40h+Buffer]
0x180001da6  mov     [rsp+0F40h+var_F00.lStructSize], ebx
0x180001daa  mov     [rsp+0F40h+var_F00.lpstrFilter], rax
0x180001daf  lea     ebx, [r15+5]
0x180001db3  lea     rax, [rbp+0E40h+var_A40]
0x180001dba  mov     [rsp+0F40h+var_F00.hwndOwner], rdi
0x180001dbf  mov     [rsp+0F40h+var_F00.lpstrFile], rax
0x180001dc4  lea     rdx, c_szwRegFlat; "Software\\Microsoft\\Windows Mail"
0x180001dcb  lea     rax, [rbp+0E40h+var_430]
0x180001dd2  mov     [rsp+0F40h+var_F00.nFilterIndex], ebx
0x180001dd6  mov     [rbp+0E40h+var_F00.lpstrTitle], rax
0x180001dda  mov     edi, 104h
0x180001ddf  lea     rax, [rsp+0F40h+var_F10]
0x180001de4  mov     [rsp+0F40h+var_F00.nMaxFile], edi
0x180001de8  mov     [rsp+0F40h+pcbData], rax; pcbData
0x180001ded  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180001df4  lea     rax, [rbp+0E40h+pszPath]
0x180001df8  mov     [rbp+0E40h+var_F00.Flags], 81008h
0x180001dff  mov     [rsp+0F40h+pvData], rax; pvData
0x180001e04  mov     [rsp+0F40h+pdwType], r15d
0x180001e09  mov     [rsp+0F40h+var_F10], 208h
0x180001e11  mov     [rbp+0E40h+pszPath], r15w
0x180001e16  call    cs:__imp_SHGetValueW
0x180001e1c  test    eax, eax
0x180001e1e  jle     short loc_180001E2A
0x180001e20  movzx   eax, ax
0x180001e23  or      eax, 80070000h
0x180001e28  test    eax, eax
0x180001e2a  js      short loc_180001E3A
0x180001e2c  lea     rcx, [rbp+0E40h+pszPath]; pszPath
0x180001e30  call    cs:__imp_PathFileExistsW
0x180001e36  test    eax, eax
0x180001e38  jnz     short loc_180001E6D
0x180001e3a  xor     r9d, r9d; fCreate
0x180001e3d  lea     rdx, [rbp+0E40h+pszPath]; pszPath
0x180001e41  xor     ecx, ecx; hwnd
0x180001e43  lea     r8d, [r9+27h]; csidl
0x180001e47  call    cs:__imp_SHGetSpecialFolderPathW
0x180001e4d  test    eax, eax
0x180001e4f  jnz     short loc_180001E6D
0x180001e51  xor     r9d, r9d; fCreate
0x180001e54  lea     rdx, [rbp+0E40h+pszPath]; pszPath
0x180001e58  mov     r8d, ebx; csidl
0x180001e5b  xor     ecx, ecx; hwnd
0x180001e5d  call    cs:__imp_SHGetSpecialFolderPathW
0x180001e63  test    eax, eax
0x180001e65  jnz     short loc_180001E6D
0x180001e67  mov     [rbp+0E40h+var_F00.lpstrInitialDir], r15
0x180001e6b  jmp     short loc_180001E75
0x180001e6d  lea     rax, [rbp+0E40h+pszPath]
0x180001e71  mov     [rbp+0E40h+var_F00.lpstrInitialDir], rax
0x180001e75  lea     rcx, [rsp+0F40h+var_F00]; LPOPENFILENAMEW
0x180001e7a  call    GetOpenFileNameW
0x180001e7f  test    eax, eax
0x180001e81  jz      loc_180001F15
0x180001e87  lea     r8, [rbp+0E40h+var_A40]; unsigned __int16 *
0x180001e8e  mov     rdx, rdi; unsigned __int64
0x180001e91  lea     rcx, [rbp+0E40h+var_C50]; unsigned __int16 *
0x180001e98  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001e9d  test    eax, eax
0x180001e9f  js      short loc_180001EFF
0x180001ea1  lea     rcx, [rbp+0E40h+var_C50]; pszPath
0x180001ea8  call    cs:__imp_PathRemoveFileSpecW
0x180001eae  test    eax, eax
0x180001eb0  jz      short loc_180001EFF
0x180001eb2  lea     r9, [rbp+0E40h+var_C50]
0x180001eb9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001ebd  inc     rax
0x180001ec0  cmp     [r9+rax*2], r15w
0x180001ec5  jnz     short loc_180001EBD
0x180001ec7  lea     eax, ds:2[rax*2]
0x180001ece  mov     r9d, 1; dwType
0x180001ed4  mov     dword ptr [rsp+0F40h+pcbData], eax; cbData
0x180001ed8  lea     r8, c_szwPicturePathValueName; "Picture Path"
0x180001edf  lea     rax, [rbp+0E40h+var_C50]
0x180001ee6  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180001eed  lea     rdx, c_szwRegFlat; "Software\\Microsoft\\Windows Mail"
0x180001ef4  mov     [rsp+0F40h+pvData], rax; pvData
0x180001ef9  call    cs:__imp_SHSetValueW
0x180001eff  mov     rdx, r14; unsigned __int64
0x180001f02  lea     r8, [rbp+0E40h+var_A40]; unsigned __int16 *
0x180001f09  mov     rcx, rsi; unsigned __int16 *
0x180001f0c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001f11  mov     ebx, eax
0x180001f13  jmp     short loc_180001F1A
0x180001f15  mov     ebx, 1
0x180001f1a  mov     eax, ebx
0x180001f1c  mov     rcx, [rbp+0E40h+var_30]
0x180001f23  xor     rcx, rsp; StackCookie
0x180001f26  call    __security_check_cookie
0x180001f2b  mov     rbx, [rsp+0F40h+arg_18]
0x180001f33  add     rsp, 0F20h
0x180001f3a  pop     r15
0x180001f3c  pop     r14
0x180001f3e  pop     rdi
0x180001f3f  pop     rsi
0x180001f40  pop     rbp
0x180001f41  retn
```
