# ContainingPathIsTamperProof(ushort const *)

- ea: `0x408a2f`
- end: `0x408c2f`
- name: `?ContainingPathIsTamperProof@@YGHPBG@Z`
- size: `512`
- prototype: `int __thiscall(unsigned __int16 *this)`
- caller_count: `7`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x40373b`
- `0x403d84`
- `0x403ffd`
- `0x404214`
- `0x4044ae`
- `0x40494e`
- `0x405628`

## callees

- `0x4066fc`
- `0x408704`
- `0x4088b6`
- `0x40895f`
- `0x408a2f`
- `0x40b6d3`
- `0x40b958`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x408c06`
- `KERNEL32!CloseHandle` at `0x408c06`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x408b63`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x408b89`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x408b63`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x408b89`
- `KERNEL32!LocalFree` at `0x408c15`
- `KERNEL32!LocalFree` at `0x408c15`
- `KERNEL32!GetFileAttributesW` at `0x408aad`
- `KERNEL32!GetFileAttributesW` at `0x408af7`
- `KERNEL32!GetFileAttributesW` at `0x408aad`
- `KERNEL32!GetFileAttributesW` at `0x408af7`
- `KERNEL32!CreateFileW` at `0x408b49`
- `KERNEL32!CreateFileW` at `0x408b49`
- `KERNEL32!GetLastError` at `0x408ab5`
- `KERNEL32!GetLastError` at `0x408aff`
- `KERNEL32!GetLastError` at `0x408ab5`
- `KERNEL32!GetLastError` at `0x408aff`
- `ole32!CoTaskMemAlloc` at `0x408b73`
- `ole32!CoTaskMemAlloc` at `0x408b73`
- `ole32!CoTaskMemFree` at `0x408c20`
- `ole32!CoTaskMemFree` at `0x408c20`
- `iertutil!__imp_?IsProtectedModeCOMCaller@@YGJPAH@Z` at `0x408a6a`
- `iertutil!__imp_?IsProtectedModeCOMCaller@@YGJPAH@Z` at `0x408a6a`

## pseudocode

```c
int __thiscall ContainingPathIsTamperProof(unsigned __int16 *this)
{
  int IsNotLowIL; // esi
  WCHAR *v2; // edi
  int v3; // eax
  DWORD FileAttributesW; // ebx
  DWORD LastError; // eax
  WCHAR *v6; // edx
  __int16 v7; // ax
  HANDLE FileW; // eax
  DWORD FinalPathNameByHandleW; // ebx
  WCHAR *v10; // eax
  DWORD v11; // eax
  const WCHAR *v12; // edi
  unsigned int v13; // ebx
  WCHAR *v15; // [esp+0h] [ebp-20h]
  WCHAR *v16; // [esp+0h] [ebp-20h]
  size_t v17; // [esp+4h] [ebp-1Ch]
  LPCWSTR lpFileName; // [esp+Ch] [ebp-14h] BYREF
  HLOCAL hMem; // [esp+10h] [ebp-10h] BYREF
  int v20; // [esp+14h] [ebp-Ch] BYREF
  HANDLE hFile; // [esp+18h] [ebp-8h]
  LPCWSTR v22; // [esp+1Ch] [ebp-4h]

  hFile = 0;
  IsNotLowIL = 1;
  v20 = 0;
  hMem = 0;
  v2 = 0;
  lpFileName = 0;
  if ( !this )
    goto LABEL_6;
  if ( CoAllocString(this, &lpFileName) < 0 )
  {
    v2 = (WCHAR *)lpFileName;
LABEL_6:
    IsNotLowIL = 0;
    goto LABEL_7;
  }
  v3 = IsProtectedModeCOMCaller(&v20);
  v2 = (WCHAR *)lpFileName;
  if ( v3 < 0 )
  {
LABEL_23:
    IsNotLowIL = 0;
    goto LABEL_38;
  }
LABEL_7:
  if ( v20 && (GetCallerSid(&hMem) < 0 || !hMem) )
    goto LABEL_23;
  if ( !IsNotLowIL )
    goto LABEL_38;
  FileAttributesW = GetFileAttributesW(v2);
  LastError = GetLastError();
  if ( FileAttributesW != -1 )
    goto LABEL_45;
  do
  {
    if ( LastError != 2 && LastError != 3 )
      break;
    if ( PathCchIsRoot(v15) )
      break;
    v6 = v2;
    do
      v7 = *v6++;
    while ( v7 != (_WORD)hFile );
    if ( PathCchRemoveFileSpec(v15, v17) < 0 )
      break;
    FileAttributesW = GetFileAttributesW(v2);
    LastError = GetLastError();
  }
  while ( FileAttributesW == -1 );
  if ( FileAttributesW != -1 )
  {
LABEL_45:
    if ( (FileAttributesW & 0x10) == 0 )
    {
      wcslen(v2);
      if ( PathCchRemoveFileSpec(v15, v17) < 0 )
        goto LABEL_23;
    }
  }
  FileW = CreateFileW(v2, 0x20000u, 0, 0, 3u, 0x2000000u, 0);
  hFile = FileW;
  if ( FileW == (HANDLE)-1 )
    goto LABEL_23;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 0);
  if ( FinalPathNameByHandleW
    && (v10 = (WCHAR *)CoTaskMemAlloc(2 * FinalPathNameByHandleW), (v22 = v10) != 0)
    && (v11 = GetFinalPathNameByHandleW(hFile, v10, FinalPathNameByHandleW, 0)) != 0 )
  {
    v12 = v22;
    v13 = v11 + 1;
    do
    {
      if ( v13 < 8 )
        break;
      IsNotLowIL = DirectoryIsNotLowIL(v12);
      if ( IsNotLowIL && v20 )
        IsNotLowIL = DirectoryIsNotWritableBySid(v12);
      if ( PathCchIsRoot(v15) )
        break;
      if ( !IsNotLowIL )
        break;
      IsNotLowIL = PathCchRemoveFileSpec(v16, v17) >= 0;
      v13 = wcslen(v12) + 1;
    }
    while ( IsNotLowIL );
    v2 = (WCHAR *)lpFileName;
  }
  else
  {
    IsNotLowIL = 0;
  }
  CloseHandle(hFile);
LABEL_38:
  if ( hMem )
    LocalFree(hMem);
  if ( v2 )
    CoTaskMemFree(v2);
  return IsNotLowIL;
}

```

## disassembly

```asm
0x408a2f  mov     edi, edi
0x408a31  push    ebp
0x408a32  mov     ebp, esp
0x408a34  and     esp, 0FFFFFFF8h
0x408a37  sub     esp, 14h
0x408a3a  push    ebx
0x408a3b  xor     ebx, ebx
0x408a3d  push    esi; unsigned __int16 **
0x408a3e  xor     esi, esi
0x408a40  mov     [esp+1Ch+hFile], ebx
0x408a44  push    edi; unsigned __int16 *
0x408a45  inc     esi
0x408a46  mov     [esp+20h+var_C], ebx
0x408a4a  mov     [esp+20h+hMem], ebx
0x408a4e  mov     edi, ebx
0x408a50  mov     [esp+20h+lpFileName], edi
0x408a54  test    ecx, ecx
0x408a56  jz      short loc_408A81
0x408a58  lea     edx, [esp+20h+lpFileName]
0x408a5c  call    ?CoAllocString@@YGJPBGPAPAG@Z; CoAllocString(ushort const *,ushort * *)
0x408a61  test    eax, eax
0x408a63  js      short loc_408A7D
0x408a65  lea     eax, [esp+20h+var_C]
0x408a69  push    eax
0x408a6a  call    ds:__imp_?IsProtectedModeCOMCaller@@YGJPAH@Z; IsProtectedModeCOMCaller(int *)
0x408a70  mov     edi, [esp+20h+lpFileName]
0x408a74  test    eax, eax
0x408a76  jns     short loc_408A83
0x408a78  jmp     loc_408B58
0x408a7d  mov     edi, [esp+20h+lpFileName]
0x408a81  mov     esi, ebx
0x408a83  cmp     [esp+20h+var_C], ebx
0x408a87  jz      short loc_408AA4
0x408a89  lea     ecx, [esp+20h+hMem]
0x408a8d  call    GetCallerSid
0x408a92  test    eax, eax
0x408a94  js      loc_408B58
0x408a9a  cmp     [esp+20h+hMem], ebx
0x408a9e  jz      loc_408B58
0x408aa4  test    esi, esi
0x408aa6  jz      loc_408C0C
0x408aac  push    edi; lpFileName
0x408aad  call    ds:__imp__GetFileAttributesW@4; GetFileAttributesW(x)
0x408ab3  mov     ebx, eax
0x408ab5  call    ds:__imp__GetLastError@0; GetLastError()
0x408abb  cmp     ebx, 0FFFFFFFFh
0x408abe  jnz     short loc_408B0F
0x408ac0  cmp     eax, 2
0x408ac3  jz      short loc_408ACA
0x408ac5  cmp     eax, 3
0x408ac8  jnz     short loc_408B0A
0x408aca  mov     ecx, edi
0x408acc  call    _PathCchIsRoot@4; PathCchIsRoot(x)
0x408ad1  test    eax, eax
0x408ad3  jnz     short loc_408B0A
0x408ad5  mov     edx, edi
0x408ad7  lea     ecx, [edx+2]
0x408ada  mov     ax, [edx]
0x408add  add     edx, 2
0x408ae0  cmp     ax, word ptr [esp+20h+hFile]
0x408ae5  jnz     short loc_408ADA
0x408ae7  sub     edx, ecx
0x408ae9  mov     ecx, edi
0x408aeb  sar     edx, 1
0x408aed  call    _PathCchRemoveFileSpec@8; PathCchRemoveFileSpec(x,x)
0x408af2  test    eax, eax
0x408af4  js      short loc_408B0A
0x408af6  push    edi; lpFileName
0x408af7  call    ds:__imp__GetFileAttributesW@4; GetFileAttributesW(x)
0x408afd  mov     ebx, eax
0x408aff  call    ds:__imp__GetLastError@0; GetLastError()
0x408b05  cmp     ebx, 0FFFFFFFFh
0x408b08  jz      short loc_408AC0
0x408b0a  cmp     ebx, 0FFFFFFFFh
0x408b0d  jz      short loc_408B37
0x408b0f  test    bl, 10h
0x408b12  jnz     short loc_408B37
0x408b14  mov     edx, edi
0x408b16  xor     ebx, ebx
0x408b18  lea     ecx, [edx+2]
0x408b1b  mov     ax, [edx]
0x408b1e  add     edx, 2
0x408b21  cmp     ax, bx
0x408b24  jnz     short loc_408B1B
0x408b26  sub     edx, ecx
0x408b28  mov     ecx, edi
0x408b2a  sar     edx, 1
0x408b2c  call    _PathCchRemoveFileSpec@8; PathCchRemoveFileSpec(x,x)
0x408b31  test    eax, eax
0x408b33  jns     short loc_408B39
0x408b35  jmp     short loc_408B58
0x408b37  xor     ebx, ebx
0x408b39  push    ebx; hTemplateFile
0x408b3a  push    2000000h; dwFlagsAndAttributes
0x408b3f  push    3; dwCreationDisposition
0x408b41  push    ebx; lpSecurityAttributes
0x408b42  push    ebx; dwShareMode
0x408b43  push    20000h; dwDesiredAccess
0x408b48  push    edi; lpFileName
0x408b49  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x408b4f  mov     [esp+20h+hFile], eax
0x408b53  cmp     eax, 0FFFFFFFFh
0x408b56  jnz     short loc_408B5F
0x408b58  mov     esi, ebx
0x408b5a  jmp     loc_408C0C
0x408b5f  push    ebx; dwFlags
0x408b60  push    ebx; cchFilePath
0x408b61  push    ebx; lpszFilePath
0x408b62  push    eax; hFile
0x408b63  call    ds:__imp__GetFinalPathNameByHandleW@16; GetFinalPathNameByHandleW(x,x,x,x)
0x408b69  mov     ebx, eax
0x408b6b  test    ebx, ebx
0x408b6d  jz      short loc_408B95
0x408b6f  lea     eax, [ebx+ebx]
0x408b72  push    eax; cb
0x408b73  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x408b79  mov     [esp+20h+var_4], eax
0x408b7d  test    eax, eax
0x408b7f  jz      short loc_408B95
0x408b81  push    0; dwFlags
0x408b83  push    ebx; cchFilePath
0x408b84  push    eax; lpszFilePath
0x408b85  push    [esp+2Ch+hFile]; hFile
0x408b89  call    ds:__imp__GetFinalPathNameByHandleW@16; GetFinalPathNameByHandleW(x,x,x,x)
0x408b8f  mov     ebx, eax
0x408b91  test    ebx, ebx
0x408b93  jnz     short loc_408B99
0x408b95  xor     esi, esi
0x408b97  jmp     short loc_408C02
0x408b99  mov     edi, [esp+20h+var_4]
0x408b9d  inc     ebx
0x408b9e  cmp     ebx, 8
0x408ba1  jb      short loc_408BFE
0x408ba3  mov     ecx, edi; lpFileName
0x408ba5  call    DirectoryIsNotLowIL
0x408baa  mov     esi, eax
0x408bac  test    esi, esi
0x408bae  jz      short loc_408BC4
0x408bb0  cmp     [esp+20h+var_C], 0
0x408bb5  jz      short loc_408BC4
0x408bb7  mov     edx, [esp+20h+hMem]
0x408bbb  mov     ecx, edi; lpFileName
0x408bbd  call    DirectoryIsNotWritableBySid
0x408bc2  mov     esi, eax
0x408bc4  mov     ecx, edi
0x408bc6  call    _PathCchIsRoot@4; PathCchIsRoot(x)
0x408bcb  test    eax, eax
0x408bcd  jnz     short loc_408BFE
0x408bcf  test    esi, esi
0x408bd1  jz      short loc_408BFE
0x408bd3  mov     edx, ebx
0x408bd5  mov     ecx, edi
0x408bd7  call    _PathCchRemoveFileSpec@8; PathCchRemoveFileSpec(x,x)
0x408bdc  mov     esi, eax
0x408bde  mov     ebx, edi
0x408be0  not     esi
0x408be2  shr     esi, 1Fh
0x408be5  xor     edx, edx
0x408be7  lea     ecx, [ebx+2]
0x408bea  mov     ax, [ebx]
0x408bed  add     ebx, 2
0x408bf0  cmp     ax, dx
0x408bf3  jnz     short loc_408BEA
0x408bf5  sub     ebx, ecx
0x408bf7  sar     ebx, 1
0x408bf9  inc     ebx
0x408bfa  test    esi, esi
0x408bfc  jnz     short loc_408B9E
0x408bfe  mov     edi, [esp+20h+lpFileName]
0x408c02  push    [esp+20h+hFile]; hObject
0x408c06  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x408c0c  mov     eax, [esp+20h+hMem]
0x408c10  test    eax, eax
0x408c12  jz      short loc_408C1B
0x408c14  push    eax; hMem
0x408c15  call    ds:__imp__LocalFree@4; LocalFree(x)
0x408c1b  test    edi, edi
0x408c1d  jz      short loc_408C26
0x408c1f  push    edi; pv
0x408c20  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x408c26  pop     edi
0x408c27  mov     eax, esi
0x408c29  pop     esi
0x408c2a  pop     ebx
0x408c2b  mov     esp, ebp
0x408c2d  pop     ebp
0x408c2e  retn
```
