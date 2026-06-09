# __std_fs_remove

- ea: `0x140004058`
- end: `0x14000439a`
- name: `__std_fs_remove`
- size: `834`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400265f0`

## callees

- `0x140003968`
- `0x140003ffc`
- `0x140004058`
- `0x140004870`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400042b7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14000435f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400042b7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14000435f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400041fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400042d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400041fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400042d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400040da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004132`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004180`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004211`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000425e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400042ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400042ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004305`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004355`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400040da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004132`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004180`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004211`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000425e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400042ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400042ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004305`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004355`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1400040c1`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x14000423d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140004291`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1400040c1`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x14000423d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140004291`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1400041e4`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1400041e4`

## pseudocode

```c
HANDLE __fastcall _std_fs_remove(__int64 a1)
{
  int v2; // eax
  int v3; // ebx
  char v4; // si
  HANDLE v5; // rbx
  DWORD LastError; // edi
  int v7; // ebx
  DWORD v9; // eax
  DWORD v10; // edi
  DWORD v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  HANDLE hFile; // [rsp+20h] [rbp-40h] BYREF
  __int64 FileInformation; // [rsp+28h] [rbp-38h] BYREF
  _OWORD v20[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v21; // [rsp+50h] [rbp-10h]

  v2 = _std_fs_open_handle(&hFile, a1, 65920, 35651584);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 != 5 )
    {
      v12 = v2 - 2;
      if ( !v12
        || (v13 = v12 - 1) == 0
        || (v14 = v13 - 50) == 0
        || (v15 = v14 - 11) == 0
        || (v16 = v15 - 59) == 0
        || (v17 = v16 - 38) == 0
        || v17 == 106 )
      {
        v3 = 0;
      }
      if ( hFile != (HANDLE)-1LL && !CloseHandle(hFile) )
        goto LABEL_56;
      HIDWORD(hFile) = v3;
LABEL_58:
      LOBYTE(hFile) = 0;
      *(_WORD *)((char *)&hFile + 1) = 0;
      BYTE3(hFile) = 0;
      return hFile;
    }
    v4 = 0;
    v7 = _std_fs_open_handle(&hFile, a1, 0x10000, 35651584);
    if ( v7 )
    {
      if ( hFile == (HANDLE)-1LL || CloseHandle(hFile) )
      {
        LOBYTE(FileInformation) = 0;
        *(_WORD *)((char *)&FileInformation + 1) = 0;
        BYTE3(FileInformation) = 0;
        HIDWORD(FileInformation) = v7;
        return (HANDLE)FileInformation;
      }
      goto LABEL_56;
    }
  }
  else
  {
    v4 = 1;
  }
  v5 = hFile;
  LODWORD(FileInformation) = 19;
  if ( SetFileInformationByHandle(hFile, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
    goto LABEL_4;
  LastError = GetLastError();
  if ( LastError != 1 && LastError != 50 && LastError != 87 )
  {
    if ( v5 == (HANDLE)-1LL || CloseHandle(v5) )
    {
      LOBYTE(FileInformation) = 0;
      *(_WORD *)((char *)&FileInformation + 1) = 0;
      BYTE3(FileInformation) = 0;
      goto LABEL_7;
    }
LABEL_56:
    abort();
  }
  v9 = anonymous_namespace_::_Set_delete_flag(v5);
  v10 = v9;
  if ( !v9 )
  {
LABEL_4:
    LastError = 0;
    if ( v5 == (HANDLE)-1LL || CloseHandle(v5) )
    {
      LOBYTE(FileInformation) = 1;
      *(_WORD *)((char *)&FileInformation + 1) = 0;
      BYTE3(FileInformation) = 0;
LABEL_7:
      HIDWORD(FileInformation) = LastError;
      return (HANDLE)FileInformation;
    }
    goto LABEL_56;
  }
  if ( v9 != 5 || !v4 )
  {
    if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
      goto LABEL_56;
    LOBYTE(hFile) = 0;
    *(_WORD *)((char *)&hFile + 1) = 0;
    BYTE3(hFile) = 0;
LABEL_33:
    HIDWORD(hFile) = v10;
    return hFile;
  }
  v21 = 0;
  memset(v20, 0, sizeof(v20));
  if ( !GetFileInformationByHandleEx(v5, FileBasicInfo, v20, 0x28u) )
  {
LABEL_24:
    LOBYTE(hFile) = 0;
    *(_WORD *)((char *)&hFile + 1) = 0;
    BYTE3(hFile) = 0;
    HIDWORD(hFile) = GetLastError();
    if ( v5 == (HANDLE)-1LL || CloseHandle(v5) )
      return hFile;
LABEL_38:
    abort();
  }
  if ( (v21 & 1) == 0 )
  {
LABEL_36:
    if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
      goto LABEL_38;
    HIDWORD(hFile) = 5;
    goto LABEL_58;
  }
  LODWORD(v21) = v21 ^ 1;
  if ( !SetFileInformationByHandle(v5, FileBasicInfo, v20, 0x28u) )
    goto LABEL_24;
  v11 = anonymous_namespace_::_Set_delete_flag(v5);
  if ( !v11 )
  {
    v10 = 0;
    if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
      goto LABEL_38;
    LOBYTE(hFile) = 1;
    *(_WORD *)((char *)&hFile + 1) = 0;
    BYTE3(hFile) = 0;
    goto LABEL_33;
  }
  if ( v11 == 5 )
  {
    LODWORD(v21) = v21 | 1;
    if ( !SetFileInformationByHandle(v5, FileBasicInfo, v20, 0x28u) )
      goto LABEL_24;
    goto LABEL_36;
  }
  LOBYTE(hFile) = 0;
  *(_WORD *)((char *)&hFile + 1) = 0;
  BYTE3(hFile) = 0;
  HIDWORD(hFile) = GetLastError();
  if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
    goto LABEL_56;
  return hFile;
}

```

## disassembly

```asm
0x140004058  mov     [rsp-18h+arg_8], rbx
0x14000405d  mov     [rsp-18h+arg_10], rsi
0x140004062  push    rbp
0x140004063  push    rdi
0x140004064  push    r15
0x140004066  mov     rbp, rsp
0x140004069  sub     rsp, 60h
0x14000406d  mov     rax, cs:__security_cookie
0x140004074  xor     rax, rsp
0x140004077  mov     [rbp+var_8], rax
0x14000407b  mov     rdi, rcx
0x14000407e  mov     rdx, rcx
0x140004081  lea     rcx, [rbp+hFile]
0x140004085  mov     r9d, 2200000h
0x14000408b  mov     r8d, 10180h
0x140004091  call    __std_fs_open_handle
0x140004096  mov     ebx, eax
0x140004098  mov     r15d, 5
0x14000409e  test    eax, eax
0x1400040a0  jnz     short loc_1400040F9
0x1400040a2  mov     sil, 1
0x1400040a5  mov     rbx, [rbp+hFile]
0x1400040a9  lea     r8, [rbp+FileInformation]; lpFileInformation
0x1400040ad  mov     r9d, 4; dwBufferSize
0x1400040b3  mov     dword ptr [rbp+FileInformation], 13h
0x1400040ba  mov     rcx, rbx; hFile
0x1400040bd  lea     edx, [r9+11h]; FileInformationClass
0x1400040c1  call    cs:__imp_SetFileInformationByHandle
0x1400040c7  test    eax, eax
0x1400040c9  jz      loc_140004158
0x1400040cf  xor     edi, edi
0x1400040d1  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400040d5  jz      short loc_1400040E8
0x1400040d7  mov     rcx, rbx; hObject
0x1400040da  call    cs:__imp_CloseHandle
0x1400040e0  test    eax, eax
0x1400040e2  jz      loc_14000435F
0x1400040e8  mov     byte ptr [rbp+FileInformation], 1
0x1400040ec  mov     word ptr [rbp+FileInformation+1], di
0x1400040f0  mov     byte ptr [rbp+FileInformation+3], dil
0x1400040f4  mov     dword ptr [rbp+FileInformation+4], edi
0x1400040f7  jmp     short loc_14000414F
0x1400040f9  cmp     eax, r15d
0x1400040fc  jnz     loc_140004321
0x140004102  mov     r9d, 2200000h
0x140004108  lea     rcx, [rbp+hFile]
0x14000410c  mov     r8d, 10000h
0x140004112  mov     rdx, rdi
0x140004115  xor     sil, sil
0x140004118  call    __std_fs_open_handle
0x14000411d  mov     ebx, eax
0x14000411f  test    eax, eax
0x140004121  jz      short loc_1400040A5
0x140004123  mov     rcx, [rbp+hFile]; hObject
0x140004127  xor     dil, dil
0x14000412a  xor     esi, esi
0x14000412c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140004130  jz      short loc_140004140
0x140004132  call    cs:__imp_CloseHandle
0x140004138  test    eax, eax
0x14000413a  jz      loc_14000435F
0x140004140  mov     byte ptr [rbp+FileInformation], dil
0x140004144  mov     word ptr [rbp+FileInformation+1], si
0x140004148  mov     byte ptr [rbp+FileInformation+3], sil
0x14000414c  mov     dword ptr [rbp+FileInformation+4], ebx
0x14000414f  mov     rax, [rbp+FileInformation]
0x140004153  jmp     loc_140004379
0x140004158  call    cs:__imp_GetLastError
0x14000415e  mov     ecx, eax
0x140004160  mov     edi, eax
0x140004162  sub     ecx, 1
0x140004165  jz      short loc_1400041A0
0x140004167  sub     ecx, 31h ; '1'
0x14000416a  jz      short loc_1400041A0
0x14000416c  cmp     ecx, 25h ; '%'
0x14000416f  jz      short loc_1400041A0
0x140004171  xor     sil, sil
0x140004174  xor     r15d, r15d
0x140004177  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000417b  jz      short loc_14000418E
0x14000417d  mov     rcx, rbx; hObject
0x140004180  call    cs:__imp_CloseHandle
0x140004186  test    eax, eax
0x140004188  jz      loc_14000435F
0x14000418e  mov     byte ptr [rbp+FileInformation], sil
0x140004192  mov     word ptr [rbp+FileInformation+1], r15w
0x140004197  mov     byte ptr [rbp+FileInformation+3], r15b
0x14000419b  jmp     loc_1400040F4
0x1400041a0  mov     rcx, rbx; hFile
0x1400041a3  call    _anonymous_namespace____Set_delete_flag
0x1400041a8  mov     edi, eax
0x1400041aa  test    eax, eax
0x1400041ac  jz      loc_1400040CF
0x1400041b2  cmp     eax, r15d
0x1400041b5  jnz     loc_1400042F6
0x1400041bb  test    sil, sil
0x1400041be  jz      loc_1400042F6
0x1400041c4  xor     eax, eax
0x1400041c6  lea     r8, [rbp+var_30]; lpFileInformation
0x1400041ca  xorps   xmm0, xmm0
0x1400041cd  mov     [rbp+var_10], rax
0x1400041d1  xor     edx, edx; FileInformationClass
0x1400041d3  mov     rcx, rbx; hFile
0x1400041d6  movups  [rbp+var_30], xmm0
0x1400041da  lea     edi, [rax+28h]
0x1400041dd  mov     r9d, edi; dwBufferSize
0x1400041e0  movups  [rbp+var_20], xmm0
0x1400041e4  call    cs:__imp_GetFileInformationByHandleEx
0x1400041ea  test    eax, eax
0x1400041ec  jnz     short loc_140004224
0x1400041ee  xor     eax, eax
0x1400041f0  mov     byte ptr [rbp+hFile], 0
0x1400041f4  mov     word ptr [rbp+hFile+1], ax
0x1400041f8  mov     byte ptr [rbp+hFile+3], al
0x1400041fb  call    cs:__imp_GetLastError
0x140004201  mov     dword ptr [rbp+hFile+4], eax
0x140004204  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140004208  jz      loc_140004375
0x14000420e  mov     rcx, rbx; hObject
0x140004211  call    cs:__imp_CloseHandle
0x140004217  test    eax, eax
0x140004219  jz      loc_1400042B7
0x14000421f  jmp     loc_140004375
0x140004224  mov     eax, dword ptr [rbp+var_10]
0x140004227  test    al, 1
0x140004229  jz      short loc_14000429F
0x14000422b  xor     eax, 1
0x14000422e  lea     r8, [rbp+var_30]; lpFileInformation
0x140004232  mov     r9d, edi; dwBufferSize
0x140004235  mov     dword ptr [rbp+var_10], eax
0x140004238  xor     edx, edx; FileInformationClass
0x14000423a  mov     rcx, rbx; hFile
0x14000423d  call    cs:__imp_SetFileInformationByHandle
0x140004243  test    eax, eax
0x140004245  jz      short loc_1400041EE
0x140004247  mov     rcx, rbx; hFile
0x14000424a  call    _anonymous_namespace____Set_delete_flag
0x14000424f  test    eax, eax
0x140004251  jnz     short loc_14000427C
0x140004253  xor     edi, edi
0x140004255  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140004259  jz      short loc_140004268
0x14000425b  mov     rcx, rbx; hObject
0x14000425e  call    cs:__imp_CloseHandle
0x140004264  test    eax, eax
0x140004266  jz      short loc_1400042B7
0x140004268  mov     byte ptr [rbp+hFile], 1
0x14000426c  mov     word ptr [rbp+hFile+1], di
0x140004270  mov     byte ptr [rbp+hFile+3], dil
0x140004274  mov     dword ptr [rbp+hFile+4], edi
0x140004277  jmp     loc_140004375
0x14000427c  cmp     eax, r15d
0x14000427f  jnz     short loc_1400042C7
0x140004281  or      dword ptr [rbp+var_10], 1
0x140004285  lea     r8, [rbp+var_30]; lpFileInformation
0x140004289  mov     r9d, edi; dwBufferSize
0x14000428c  xor     edx, edx; FileInformationClass
0x14000428e  mov     rcx, rbx; hFile
0x140004291  call    cs:__imp_SetFileInformationByHandle
0x140004297  test    eax, eax
0x140004299  jz      loc_1400041EE
0x14000429f  xor     dil, dil
0x1400042a2  xor     esi, esi
0x1400042a4  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400042a8  jz      short loc_1400042BE
0x1400042aa  mov     rcx, rbx; hObject
0x1400042ad  call    cs:__imp_CloseHandle
0x1400042b3  test    eax, eax
0x1400042b5  jnz     short loc_1400042BE
0x1400042b7  call    cs:__imp_abort
0x1400042be  mov     dword ptr [rbp+hFile+4], r15d
0x1400042c2  jmp     loc_140004369
0x1400042c7  xor     eax, eax
0x1400042c9  mov     byte ptr [rbp+hFile], 0
0x1400042cd  mov     word ptr [rbp+hFile+1], ax
0x1400042d1  mov     byte ptr [rbp+hFile+3], al
0x1400042d4  call    cs:__imp_GetLastError
0x1400042da  mov     dword ptr [rbp+hFile+4], eax
0x1400042dd  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400042e1  jz      loc_140004375
0x1400042e7  mov     rcx, rbx; hObject
0x1400042ea  call    cs:__imp_CloseHandle
0x1400042f0  test    eax, eax
0x1400042f2  jz      short loc_14000435F
0x1400042f4  jmp     short loc_140004375
0x1400042f6  xor     sil, sil
0x1400042f9  xor     r15d, r15d
0x1400042fc  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140004300  jz      short loc_14000430F
0x140004302  mov     rcx, rbx; hObject
0x140004305  call    cs:__imp_CloseHandle
0x14000430b  test    eax, eax
0x14000430d  jz      short loc_14000435F
0x14000430f  mov     byte ptr [rbp+hFile], sil
0x140004313  mov     word ptr [rbp+hFile+1], r15w
0x140004318  mov     byte ptr [rbp+hFile+3], r15b
0x14000431c  jmp     loc_140004274
0x140004321  xor     dil, dil
0x140004324  xor     esi, esi
0x140004326  sub     eax, 2
0x140004329  jz      short loc_140004349
0x14000432b  sub     eax, 1
0x14000432e  jz      short loc_140004349
0x140004330  sub     eax, 32h ; '2'
0x140004333  jz      short loc_140004349
0x140004335  sub     eax, 0Bh
0x140004338  jz      short loc_140004349
0x14000433a  sub     eax, 3Bh ; ';'
0x14000433d  jz      short loc_140004349
0x14000433f  sub     eax, 26h ; '&'
0x140004342  jz      short loc_140004349
0x140004344  cmp     eax, 6Ah ; 'j'
0x140004347  jnz     short loc_14000434B
0x140004349  xor     ebx, ebx
0x14000434b  mov     rcx, [rbp+hFile]; hObject
0x14000434f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140004353  jz      short loc_140004366
0x140004355  call    cs:__imp_CloseHandle
0x14000435b  test    eax, eax
0x14000435d  jnz     short loc_140004366
0x14000435f  call    cs:__imp_abort
0x140004366  mov     dword ptr [rbp+hFile+4], ebx
0x140004369  mov     byte ptr [rbp+hFile], dil
0x14000436d  mov     word ptr [rbp+hFile+1], si
0x140004371  mov     byte ptr [rbp+hFile+3], sil
0x140004375  mov     rax, [rbp+hFile]
0x140004379  mov     rcx, [rbp+var_8]
0x14000437d  xor     rcx, rsp; StackCookie
0x140004380  call    __security_check_cookie
0x140004385  lea     r11, [rsp+60h+var_s0]
0x14000438a  mov     rbx, [r11+28h]
0x14000438e  mov     rsi, [r11+30h]
0x140004392  mov     rsp, r11
0x140004395  pop     r15
0x140004397  pop     rdi
0x140004398  pop     rbp
0x140004399  retn
```
