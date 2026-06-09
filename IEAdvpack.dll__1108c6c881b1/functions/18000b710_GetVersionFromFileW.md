# GetVersionFromFileW

- ea: `0x18000b710`
- end: `0x18000b8da`
- name: `GetVersionFromFileW`
- size: `458`
- prototype: `HRESULT __stdcall(LPCWSTR lpszFilename, LPDWORD pdwMSVer, LPDWORD pdwLSVer, BOOL bVersion)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000a918`
- `0x18000ae68`
- `0x18000b560`

## callees

- `0x1800022bc`
- `0x18000b710`
- `0x18001b980`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000b8a1`
- `KERNEL32!LocalFree` at `0x18000b8a1`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000b7b4`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000b7b4`
- `KERNEL32!GetTempFileNameW` at `0x18000b7d0`
- `KERNEL32!GetTempFileNameW` at `0x18000b7d0`
- `KERNEL32!LocalAlloc` at `0x18000b80c`
- `KERNEL32!LocalAlloc` at `0x18000b80c`
- `KERNEL32!DeleteFileW` at `0x18000b8b1`
- `KERNEL32!DeleteFileW` at `0x18000b8b1`
- `KERNEL32!CopyFileW` at `0x18000b7e1`
- `KERNEL32!CopyFileW` at `0x18000b7e1`
- `VERSION!GetFileVersionInfoSizeW` at `0x18000b777`
- `VERSION!GetFileVersionInfoSizeW` at `0x18000b7f5`
- `VERSION!GetFileVersionInfoSizeW` at `0x18000b777`
- `VERSION!GetFileVersionInfoSizeW` at `0x18000b7f5`
- `VERSION!GetFileVersionInfoW` at `0x18000b82d`
- `VERSION!GetFileVersionInfoW` at `0x18000b82d`
- `VERSION!VerQueryValueW` at `0x18000b850`
- `VERSION!VerQueryValueW` at `0x18000b87c`
- `VERSION!VerQueryValueW` at `0x18000b850`
- `VERSION!VerQueryValueW` at `0x18000b87c`
- `SHLWAPI!PathFileExistsW` at `0x18000b79a`
- `SHLWAPI!PathFileExistsW` at `0x18000b79a`

## pseudocode

```c
HRESULT __stdcall GetVersionFromFileW(LPCWSTR lpszFilename, LPDWORD pdwMSVer, LPDWORD pdwLSVer, BOOL bVersion)
{
  int v4; // r15d
  DWORD FileVersionInfoSizeW; // edi
  HLOCAL v10; // rax
  void *v11; // rbx
  _DWORD *v12; // rcx
  DWORD v13; // eax
  unsigned __int16 *v14; // rcx
  unsigned int puLen; // [rsp+20h] [rbp-E0h] BYREF
  DWORD dwHandle; // [rsp+24h] [rbp-DCh] BYREF
  LPVOID lpBuffer; // [rsp+28h] [rbp-D8h] BYREF
  LPVOID v19; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp+150h] BYREF

  v4 = 0;
  puLen = 0;
  *pdwLSVer = 0;
  *pdwMSVer = 0;
  dwHandle = 0;
  lpBuffer = 0;
  v19 = 0;
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(lpszFilename, &dwHandle);
  StringCchCopyW(pszPath, 0x104u, (size_t *)lpszFilename);
  if ( !FileVersionInfoSizeW )
  {
    if ( !PathFileExistsW(pszPath) )
      return 0;
    GetWindowsDirectoryW(Buffer, 0x104u);
    GetTempFileNameW(Buffer, L"_&_", 0, pszPath);
    CopyFileW(lpszFilename, pszPath, 0);
    v4 = 1;
    FileVersionInfoSizeW = GetFileVersionInfoSizeW(pszPath, &dwHandle);
    if ( !FileVersionInfoSizeW )
    {
LABEL_16:
      DeleteFileW(pszPath);
      return 0;
    }
  }
  v10 = LocalAlloc(0x40u, FileVersionInfoSizeW);
  v11 = v10;
  if ( v10 )
  {
    if ( GetFileVersionInfoW(pszPath, dwHandle, FileVersionInfoSizeW, v10) )
    {
      if ( bVersion )
      {
        if ( !VerQueryValueW(v11, L"\\", &lpBuffer, &puLen) || !puLen )
          goto LABEL_14;
        v12 = lpBuffer;
        *pdwMSVer = *((_DWORD *)lpBuffer + 2);
        v13 = v12[3];
      }
      else
      {
        if ( !VerQueryValueW(v11, L"\\VarFileInfo\\Translation", &v19, &puLen) || !puLen )
          goto LABEL_14;
        v14 = (unsigned __int16 *)v19;
        *pdwMSVer = *(unsigned __int16 *)v19;
        v13 = v14[1];
      }
      *pdwLSVer = v13;
    }
LABEL_14:
    LocalFree(v11);
  }
  if ( v4 )
    goto LABEL_16;
  return 0;
}

```

## disassembly

```asm
0x18000b710  push    rbp
0x18000b712  push    rbx
0x18000b713  push    rsi
0x18000b714  push    rdi
0x18000b715  push    r12
0x18000b717  push    r14
0x18000b719  push    r15
0x18000b71b  lea     rbp, [rsp-370h]
0x18000b723  sub     rsp, 470h
0x18000b72a  mov     rax, cs:__security_cookie
0x18000b731  xor     rax, rsp
0x18000b734  mov     [rbp+3A0h+var_40], rax
0x18000b73b  xor     r15d, r15d
0x18000b73e  mov     [rsp+4A0h+puLen], 0
0x18000b746  mov     [r8], r15d
0x18000b749  mov     rsi, rdx
0x18000b74c  mov     [rdx], r15d
0x18000b74f  mov     r12d, r9d
0x18000b752  lea     rdx, [rsp+4A0h+dwHandle]; lpdwHandle
0x18000b757  mov     [rsp+4A0h+dwHandle], 0
0x18000b75f  mov     r14, r8
0x18000b762  mov     [rsp+4A0h+lpBuffer], 0
0x18000b76b  mov     rbx, rcx
0x18000b76e  mov     [rsp+4A0h+var_470], 0
0x18000b777  call    cs:__imp_GetFileVersionInfoSizeW
0x18000b77d  mov     r8, rbx; unsigned __int16 *
0x18000b780  lea     rcx, [rsp+4A0h+pszPath]; unsigned __int16 *
0x18000b785  mov     edx, 104h; unsigned __int64
0x18000b78a  mov     edi, eax
0x18000b78c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b791  test    edi, edi
0x18000b793  jnz     short loc_18000B805
0x18000b795  lea     rcx, [rsp+4A0h+pszPath]; pszPath
0x18000b79a  call    cs:__imp_PathFileExistsW
0x18000b7a0  test    eax, eax
0x18000b7a2  jz      loc_18000B8B7
0x18000b7a8  mov     edx, 104h; uSize
0x18000b7ad  lea     rcx, [rbp+3A0h+Buffer]; lpBuffer
0x18000b7b4  call    cs:__imp_GetWindowsDirectoryW
0x18000b7ba  lea     r9, [rsp+4A0h+pszPath]; lpTempFileName
0x18000b7bf  xor     r8d, r8d; uUnique
0x18000b7c2  lea     rdx, asc_18001F100; "_&_"
0x18000b7c9  lea     rcx, [rbp+3A0h+Buffer]; lpPathName
0x18000b7d0  call    cs:__imp_GetTempFileNameW
0x18000b7d6  xor     r8d, r8d; bFailIfExists
0x18000b7d9  lea     rdx, [rsp+4A0h+pszPath]; lpNewFileName
0x18000b7de  mov     rcx, rbx; lpExistingFileName
0x18000b7e1  call    cs:__imp_CopyFileW
0x18000b7e7  lea     rdx, [rsp+4A0h+dwHandle]; lpdwHandle
0x18000b7ec  lea     rcx, [rsp+4A0h+pszPath]; lptstrFilename
0x18000b7f1  lea     r15d, [rdi+1]
0x18000b7f5  call    cs:__imp_GetFileVersionInfoSizeW
0x18000b7fb  mov     edi, eax
0x18000b7fd  test    eax, eax
0x18000b7ff  jz      loc_18000B8AC
0x18000b805  mov     edx, edi; uBytes
0x18000b807  mov     ecx, 40h ; '@'; uFlags
0x18000b80c  call    cs:__imp_LocalAlloc
0x18000b812  mov     rbx, rax
0x18000b815  test    rax, rax
0x18000b818  jz      loc_18000B8A7
0x18000b81e  mov     edx, [rsp+4A0h+dwHandle]; dwHandle
0x18000b822  lea     rcx, [rsp+4A0h+pszPath]; lptstrFilename
0x18000b827  mov     r9, rax; lpData
0x18000b82a  mov     r8d, edi; dwLen
0x18000b82d  call    cs:__imp_GetFileVersionInfoW
0x18000b833  test    eax, eax
0x18000b835  jz      short loc_18000B89E
0x18000b837  lea     r9, [rsp+4A0h+puLen]; puLen
0x18000b83c  mov     rcx, rbx; pBlock
0x18000b83f  test    r12d, r12d
0x18000b842  jz      short loc_18000B870
0x18000b844  lea     r8, [rsp+4A0h+lpBuffer]; lplpBuffer
0x18000b849  lea     rdx, SubBlock; "\\"
0x18000b850  call    cs:__imp_VerQueryValueW
0x18000b856  test    eax, eax
0x18000b858  jz      short loc_18000B89E
0x18000b85a  cmp     [rsp+4A0h+puLen], 0
0x18000b85f  jz      short loc_18000B89E
0x18000b861  mov     rcx, [rsp+4A0h+lpBuffer]
0x18000b866  mov     eax, [rcx+8]
0x18000b869  mov     [rsi], eax
0x18000b86b  mov     eax, [rcx+0Ch]
0x18000b86e  jmp     short loc_18000B89B
0x18000b870  lea     r8, [rsp+4A0h+var_470]; lplpBuffer
0x18000b875  lea     rdx, aVarfileinfoTra; "\\VarFileInfo\\Translation"
0x18000b87c  call    cs:__imp_VerQueryValueW
0x18000b882  test    eax, eax
0x18000b884  jz      short loc_18000B89E
0x18000b886  cmp     [rsp+4A0h+puLen], 0
0x18000b88b  jz      short loc_18000B89E
0x18000b88d  mov     rcx, [rsp+4A0h+var_470]
0x18000b892  movzx   eax, word ptr [rcx]
0x18000b895  mov     [rsi], eax
0x18000b897  movzx   eax, word ptr [rcx+2]
0x18000b89b  mov     [r14], eax
0x18000b89e  mov     rcx, rbx; hMem
0x18000b8a1  call    cs:__imp_LocalFree
0x18000b8a7  test    r15d, r15d
0x18000b8aa  jz      short loc_18000B8B7
0x18000b8ac  lea     rcx, [rsp+4A0h+pszPath]; lpFileName
0x18000b8b1  call    cs:__imp_DeleteFileW
0x18000b8b7  xor     eax, eax
0x18000b8b9  mov     rcx, [rbp+3A0h+var_40]
0x18000b8c0  xor     rcx, rsp; StackCookie
0x18000b8c3  call    __security_check_cookie
0x18000b8c8  add     rsp, 470h
0x18000b8cf  pop     r15
0x18000b8d1  pop     r14
0x18000b8d3  pop     r12
0x18000b8d5  pop     rdi
0x18000b8d6  pop     rsi
0x18000b8d7  pop     rbx
0x18000b8d8  pop     rbp
0x18000b8d9  retn
```
