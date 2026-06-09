# __std_fs_remove

- ea: `0x140058e38`
- end: `0x1400590c8`
- name: `__std_fs_remove`
- size: `656`
- prototype: ``
- caller_count: `9`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140118d5c`
- `0x140118f6c`
- `0x140187c64`
- `0x14018b190`
- `0x14018b628`
- `0x14018d4b4`
- `0x1401901cc`
- `0x140345384`
- `0x140355128`

## callees

- `0x140058804`
- `0x140058884`
- `0x140058e38`
- `0x140378e10`
- `0x140379070`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058fbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058fbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059072`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140058f0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140058fd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140058f0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140058fd1`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140058ea2`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140059001`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x14005903e`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140058ea2`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140059001`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x14005903e`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x140058fa4`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x140058fa4`

## pseudocode

```c
__int64 __fastcall _std_fs_remove(__int64 a1)
{
  char v2; // di
  int v3; // ecx
  HANDLE v4; // rbx
  HANDLE v5; // rcx
  int v6; // eax
  DWORD LastError; // eax
  int v9; // eax
  __int64 v10; // [rsp+20h] [rbp-50h]
  HANDLE hFile; // [rsp+28h] [rbp-48h] BYREF
  int FileInformation; // [rsp+30h] [rbp-40h] BYREF
  _OWORD v13[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v14; // [rsp+58h] [rbp-18h]

  v2 = 0;
  v3 = _std_fs_open_handle(&hFile, a1, 65920, 35651584);
  if ( !v3 )
  {
    v2 = 1;
    goto LABEL_3;
  }
  if ( v3 != 5 )
  {
    LOBYTE(v10) = 0;
    *(_WORD *)((char *)&v10 + 1) = 0;
    BYTE3(v10) = 0;
    if ( v3 == 2 || v3 == 3 || v3 == 53 || v3 == 64 || v3 == 123 || v3 == 267 )
      v3 = 0;
    HIDWORD(v10) = v3;
LABEL_10:
    v5 = hFile;
    if ( hFile == (HANDLE)-1LL )
      return v10;
LABEL_11:
    if ( !CloseHandle(v5) )
      abort();
    return v10;
  }
  v6 = _std_fs_open_handle(&hFile, a1, 0x10000, 35651584);
  if ( v6 )
  {
    LOBYTE(v10) = 0;
    *(_WORD *)((char *)&v10 + 1) = 0;
    BYTE3(v10) = 0;
    HIDWORD(v10) = v6;
    goto LABEL_10;
  }
LABEL_3:
  v4 = hFile;
  FileInformation = 19;
  if ( SetFileInformationByHandle(hFile, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
  {
LABEL_4:
    v10 = 1;
LABEL_5:
    if ( v4 == (HANDLE)-1LL )
      return v10;
    v5 = v4;
    goto LABEL_11;
  }
  LastError = GetLastError();
  if ( LastError != 1 && LastError != 50 && LastError != 87 )
    goto LABEL_16;
  LastError = anonymous_namespace_::_Set_delete_flag(v4);
  if ( !LastError )
    goto LABEL_4;
  if ( LastError != 5 || !v2 )
  {
LABEL_16:
    LOBYTE(v10) = 0;
    *(_WORD *)((char *)&v10 + 1) = 0;
    BYTE3(v10) = 0;
    goto LABEL_17;
  }
  v14 = 0;
  memset(v13, 0, sizeof(v13));
  if ( GetFileInformationByHandleEx(v4, FileBasicInfo, v13, 0x28u) )
  {
    if ( (v14 & 1) == 0 )
    {
      LOBYTE(v10) = 0;
      goto LABEL_33;
    }
    LODWORD(v14) = v14 ^ 1;
    if ( !SetFileInformationByHandle(v4, FileBasicInfo, v13, 0x28u) )
      goto LABEL_22;
    v9 = anonymous_namespace_::_Set_delete_flag(v4);
    if ( !v9 )
    {
      v10 = 1;
      goto LABEL_24;
    }
    if ( v9 == 5 )
    {
      LODWORD(v14) = v14 | 1;
      LOBYTE(v10) = 0;
      if ( !SetFileInformationByHandle(v4, FileBasicInfo, v13, 0x28u) )
        goto LABEL_23;
LABEL_33:
      HIDWORD(v10) = 5;
      *(_WORD *)((char *)&v10 + 1) = 0;
      BYTE3(v10) = 0;
      goto LABEL_24;
    }
    LOBYTE(v10) = 0;
    *(_WORD *)((char *)&v10 + 1) = 0;
    BYTE3(v10) = 0;
    LastError = GetLastError();
LABEL_17:
    HIDWORD(v10) = LastError;
    goto LABEL_5;
  }
LABEL_22:
  LOBYTE(v10) = 0;
LABEL_23:
  *(_WORD *)((char *)&v10 + 1) = 0;
  BYTE3(v10) = 0;
  HIDWORD(v10) = GetLastError();
LABEL_24:
  if ( v4 != (HANDLE)-1LL && !CloseHandle(v4) )
    abort();
  return v10;
}

```

## disassembly

```asm
0x140058e38  mov     [rsp-8+arg_8], rbx
0x140058e3d  mov     [rsp-8+arg_10], rsi
0x140058e42  mov     [rsp-8+arg_18], rdi
0x140058e47  push    rbp
0x140058e48  mov     rbp, rsp
0x140058e4b  sub     rsp, 70h
0x140058e4f  mov     rax, cs:__security_cookie
0x140058e56  xor     rax, rsp
0x140058e59  mov     [rbp+var_10], rax
0x140058e5d  mov     rbx, rcx
0x140058e60  mov     rdx, rcx
0x140058e63  xor     esi, esi
0x140058e65  lea     rcx, [rbp+hFile]
0x140058e69  mov     r9d, 2200000h
0x140058e6f  mov     r8d, 10180h
0x140058e75  mov     dil, sil
0x140058e78  call    __std_fs_open_handle
0x140058e7d  mov     ecx, eax
0x140058e7f  test    eax, eax
0x140058e81  jnz     short loc_140058ECB
0x140058e83  mov     dil, 1
0x140058e86  mov     rbx, [rbp+hFile]
0x140058e8a  lea     r8, [rbp+FileInformation]; lpFileInformation
0x140058e8e  mov     r9d, 4; dwBufferSize
0x140058e94  mov     [rbp+FileInformation], 13h
0x140058e9b  mov     rcx, rbx; hFile
0x140058e9e  lea     edx, [r9+11h]; FileInformationClass
0x140058ea2  call    cs:__imp_SetFileInformationByHandle
0x140058ea8  test    eax, eax
0x140058eaa  jz      loc_140058F3E
0x140058eb0  xor     eax, eax
0x140058eb2  mov     byte ptr [rbp+var_50], 1
0x140058eb6  mov     word ptr [rbp+var_50+1], ax
0x140058eba  mov     byte ptr [rbp+var_50+3], al
0x140058ebd  mov     dword ptr [rbp+var_50+4], esi
0x140058ec0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140058ec4  jz      short loc_140058F18
0x140058ec6  mov     rcx, rbx
0x140058ec9  jmp     short loc_140058F0A
0x140058ecb  cmp     ecx, 5
0x140058ece  jnz     loc_140059083
0x140058ed4  mov     r9d, 2200000h
0x140058eda  lea     rcx, [rbp+hFile]
0x140058ede  mov     r8d, 10000h
0x140058ee4  mov     rdx, rbx
0x140058ee7  call    __std_fs_open_handle
0x140058eec  test    eax, eax
0x140058eee  jz      short loc_140058E86
0x140058ef0  xor     ecx, ecx
0x140058ef2  mov     byte ptr [rbp+var_50], sil
0x140058ef6  mov     word ptr [rbp+var_50+1], cx
0x140058efa  mov     byte ptr [rbp+var_50+3], cl
0x140058efd  mov     dword ptr [rbp+var_50+4], eax
0x140058f00  mov     rcx, [rbp+hFile]; hObject
0x140058f04  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140058f08  jz      short loc_140058F18
0x140058f0a  call    cs:__imp_CloseHandle
0x140058f10  test    eax, eax
0x140058f12  jz      loc_1400590BC
0x140058f18  mov     rax, [rbp+var_50]
0x140058f1c  mov     rcx, [rbp+var_10]
0x140058f20  xor     rcx, rsp; StackCookie
0x140058f23  call    __security_check_cookie
0x140058f28  lea     r11, [rsp+70h+var_s0]
0x140058f2d  mov     rbx, [r11+18h]
0x140058f31  mov     rsi, [r11+20h]
0x140058f35  mov     rdi, [r11+28h]
0x140058f39  mov     rsp, r11
0x140058f3c  pop     rbp
0x140058f3d  retn
0x140058f3e  call    cs:__imp_GetLastError
0x140058f44  mov     ecx, eax
0x140058f46  sub     ecx, 1
0x140058f49  jz      short loc_140058F6A
0x140058f4b  sub     ecx, 31h ; '1'
0x140058f4e  jz      short loc_140058F6A
0x140058f50  cmp     ecx, 25h ; '%'
0x140058f53  jz      short loc_140058F6A
0x140058f55  xor     ecx, ecx
0x140058f57  mov     byte ptr [rbp+var_50], sil
0x140058f5b  mov     word ptr [rbp+var_50+1], cx
0x140058f5f  mov     byte ptr [rbp+var_50+3], cl
0x140058f62  mov     dword ptr [rbp+var_50+4], eax
0x140058f65  jmp     loc_140058EC0
0x140058f6a  mov     rcx, rbx; hFile
0x140058f6d  call    _anonymous_namespace____Set_delete_flag
0x140058f72  test    eax, eax
0x140058f74  jz      loc_140058EB0
0x140058f7a  cmp     eax, 5
0x140058f7d  jnz     short loc_140058F55
0x140058f7f  test    dil, dil
0x140058f82  jz      short loc_140058F55
0x140058f84  xor     eax, eax
0x140058f86  lea     r8, [rbp+var_38]; lpFileInformation
0x140058f8a  xorps   xmm0, xmm0
0x140058f8d  mov     [rbp+var_18], rax
0x140058f91  xor     edx, edx; FileInformationClass
0x140058f93  mov     rcx, rbx; hFile
0x140058f96  movups  [rbp+var_38], xmm0
0x140058f9a  lea     edi, [rax+28h]
0x140058f9d  mov     r9d, edi; dwBufferSize
0x140058fa0  movups  [rbp+var_28], xmm0
0x140058fa4  call    cs:__imp_GetFileInformationByHandleEx
0x140058faa  test    eax, eax
0x140058fac  jnz     short loc_140058FE4
0x140058fae  mov     byte ptr [rbp+var_50], sil
0x140058fb2  xor     eax, eax
0x140058fb4  mov     word ptr [rbp+var_50+1], ax
0x140058fb8  mov     byte ptr [rbp+var_50+3], al
0x140058fbb  call    cs:__imp_GetLastError
0x140058fc1  mov     dword ptr [rbp+var_50+4], eax
0x140058fc4  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140058fc8  jz      loc_140058F18
0x140058fce  mov     rcx, rbx; hObject
0x140058fd1  call    cs:__imp_CloseHandle
0x140058fd7  test    eax, eax
0x140058fd9  jz      loc_1400590C2
0x140058fdf  jmp     loc_140058F18
0x140058fe4  mov     eax, dword ptr [rbp+var_18]
0x140058fe7  test    al, 1
0x140058fe9  jz      loc_14005907D
0x140058fef  xor     eax, 1
0x140058ff2  lea     r8, [rbp+var_38]; lpFileInformation
0x140058ff6  mov     r9d, edi; dwBufferSize
0x140058ff9  mov     dword ptr [rbp+var_18], eax
0x140058ffc  xor     edx, edx; FileInformationClass
0x140058ffe  mov     rcx, rbx; hFile
0x140059001  call    cs:__imp_SetFileInformationByHandle
0x140059007  test    eax, eax
0x140059009  jz      short loc_140058FAE
0x14005900b  mov     rcx, rbx; hFile
0x14005900e  call    _anonymous_namespace____Set_delete_flag
0x140059013  test    eax, eax
0x140059015  jnz     short loc_140059029
0x140059017  xor     eax, eax
0x140059019  mov     byte ptr [rbp+var_50], 1
0x14005901d  mov     word ptr [rbp+var_50+1], ax
0x140059021  mov     byte ptr [rbp+var_50+3], al
0x140059024  mov     dword ptr [rbp+var_50+4], esi
0x140059027  jmp     short loc_140058FC4
0x140059029  cmp     eax, 5
0x14005902c  jnz     short loc_140059065
0x14005902e  or      dword ptr [rbp+var_18], 1
0x140059032  lea     r8, [rbp+var_38]; lpFileInformation
0x140059036  mov     r9d, edi; dwBufferSize
0x140059039  xor     edx, edx; FileInformationClass
0x14005903b  mov     rcx, rbx; hFile
0x14005903e  call    cs:__imp_SetFileInformationByHandle
0x140059044  mov     byte ptr [rbp+var_50], sil
0x140059048  test    eax, eax
0x14005904a  jz      loc_140058FB2
0x140059050  xor     eax, eax
0x140059052  mov     dword ptr [rbp+var_50+4], 5
0x140059059  mov     word ptr [rbp+var_50+1], ax
0x14005905d  mov     byte ptr [rbp+var_50+3], al
0x140059060  jmp     loc_140058FC4
0x140059065  xor     eax, eax
0x140059067  mov     byte ptr [rbp+var_50], sil
0x14005906b  mov     word ptr [rbp+var_50+1], ax
0x14005906f  mov     byte ptr [rbp+var_50+3], al
0x140059072  call    cs:__imp_GetLastError
0x140059078  jmp     loc_140058F62
0x14005907d  mov     byte ptr [rbp+var_50], sil
0x140059081  jmp     short loc_140059050
0x140059083  xor     eax, eax
0x140059085  mov     byte ptr [rbp+var_50], sil
0x140059089  mov     word ptr [rbp+var_50+1], ax
0x14005908d  mov     byte ptr [rbp+var_50+3], al
0x140059090  mov     eax, ecx
0x140059092  sub     eax, 2
0x140059095  jz      short loc_1400590B2
0x140059097  sub     eax, 1
0x14005909a  jz      short loc_1400590B2
0x14005909c  sub     eax, 32h ; '2'
0x14005909f  jz      short loc_1400590B2
0x1400590a1  sub     eax, 0Bh
0x1400590a4  jz      short loc_1400590B2
0x1400590a6  sub     eax, 3Bh ; ';'
0x1400590a9  jz      short loc_1400590B2
0x1400590ab  cmp     eax, 90h
0x1400590b0  jnz     short loc_1400590B4
0x1400590b2  mov     ecx, esi
0x1400590b4  mov     dword ptr [rbp+var_50+4], ecx
0x1400590b7  jmp     loc_140058F00
0x1400590bc  call    abort
0x1400590c2  call    abort
```
