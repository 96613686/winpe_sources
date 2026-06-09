# __std_fs_remove

- ea: `0x1800a4ffc`
- end: `0x1800a53b8`
- name: `__std_fs_remove`
- size: `956`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18010cdc4`

## callees

- `0x1800059d0`
- `0x180006964`
- `0x1800a42e8`
- `0x1800a4fac`
- `0x1800a4ffc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800a5065`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800a5219`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800a527d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800a5065`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800a5219`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800a527d`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800a51aa`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800a51aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a51c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a52c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a51c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a52c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a5084`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a50e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a5140`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a51e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a5240`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a529f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a52e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a530d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a5367`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a5084`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a50e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a5140`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a51e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a5240`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a529f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a52e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a530d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a5367`

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
  int v9; // eax
  int v10; // edi
  int v11; // eax
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
        goto LABEL_59;
      HIDWORD(hFile) = v3;
LABEL_56:
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
      goto LABEL_59;
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
LABEL_59:
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
    goto LABEL_59;
  }
  if ( v9 != 5 || !v4 )
  {
    if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
      goto LABEL_59;
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
LABEL_58:
    abort();
  }
  if ( (v21 & 1) == 0 )
  {
LABEL_36:
    if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
      goto LABEL_58;
    HIDWORD(hFile) = 5;
    goto LABEL_56;
  }
  LODWORD(v21) = v21 ^ 1;
  if ( !SetFileInformationByHandle(v5, FileBasicInfo, v20, 0x28u) )
    goto LABEL_24;
  v11 = anonymous_namespace_::_Set_delete_flag(v5);
  if ( !v11 )
  {
    v10 = 0;
    if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
      goto LABEL_58;
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
    goto LABEL_59;
  return hFile;
}

```

## disassembly

```asm
0x1800a4ffc  mov     [rsp-18h+arg_8], rbx
0x1800a5001  mov     [rsp-18h+arg_10], rsi
0x1800a5006  push    rbp
0x1800a5007  push    rdi
0x1800a5008  push    r15
0x1800a500a  mov     rbp, rsp
0x1800a500d  sub     rsp, 60h
0x1800a5011  mov     rax, cs:__security_cookie
0x1800a5018  xor     rax, rsp
0x1800a501b  mov     [rbp+var_8], rax
0x1800a501f  mov     rdi, rcx
0x1800a5022  mov     rdx, rcx
0x1800a5025  lea     rcx, [rbp+hFile]
0x1800a5029  mov     r9d, 2200000h
0x1800a502f  mov     r8d, 10180h
0x1800a5035  call    __std_fs_open_handle
0x1800a503a  mov     ebx, eax
0x1800a503c  mov     r15d, 5
0x1800a5042  test    eax, eax
0x1800a5044  jnz     short loc_1800A50A9
0x1800a5046  mov     sil, 1
0x1800a5049  mov     rbx, [rbp+hFile]
0x1800a504d  lea     r8, [rbp+FileInformation]; lpFileInformation
0x1800a5051  mov     r9d, 4; dwBufferSize
0x1800a5057  mov     dword ptr [rbp+FileInformation], 13h
0x1800a505e  mov     rcx, rbx; hFile
0x1800a5061  lea     edx, [r9+11h]; FileInformationClass
0x1800a5065  call    cs:__imp_SetFileInformationByHandle
0x1800a506c  nop     dword ptr [rax+rax+00h]
0x1800a5071  test    eax, eax
0x1800a5073  jz      loc_1800A5112
0x1800a5079  xor     edi, edi
0x1800a507b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800a507f  jz      short loc_1800A5098
0x1800a5081  mov     rcx, rbx; hObject
0x1800a5084  call    cs:__imp_CloseHandle
0x1800a508b  nop     dword ptr [rax+rax+00h]
0x1800a5090  test    eax, eax
0x1800a5092  jz      loc_1800A53B2
0x1800a5098  mov     byte ptr [rbp+FileInformation], 1
0x1800a509c  mov     word ptr [rbp+FileInformation+1], di
0x1800a50a0  mov     byte ptr [rbp+FileInformation+3], dil
0x1800a50a4  mov     dword ptr [rbp+FileInformation+4], edi
0x1800a50a7  jmp     short loc_1800A5109
0x1800a50a9  cmp     eax, r15d
0x1800a50ac  jnz     loc_1800A5333
0x1800a50b2  mov     r9d, 2200000h
0x1800a50b8  lea     rcx, [rbp+hFile]
0x1800a50bc  mov     r8d, 10000h
0x1800a50c2  mov     rdx, rdi
0x1800a50c5  xor     sil, sil
0x1800a50c8  call    __std_fs_open_handle
0x1800a50cd  mov     ebx, eax
0x1800a50cf  test    eax, eax
0x1800a50d1  jz      loc_1800A5049
0x1800a50d7  mov     rcx, [rbp+hFile]; hObject
0x1800a50db  xor     dil, dil
0x1800a50de  xor     esi, esi
0x1800a50e0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800a50e4  jz      short loc_1800A50FA
0x1800a50e6  call    cs:__imp_CloseHandle
0x1800a50ed  nop     dword ptr [rax+rax+00h]
0x1800a50f2  test    eax, eax
0x1800a50f4  jz      loc_1800A53B2
0x1800a50fa  mov     byte ptr [rbp+FileInformation], dil
0x1800a50fe  mov     word ptr [rbp+FileInformation+1], si
0x1800a5102  mov     byte ptr [rbp+FileInformation+3], sil
0x1800a5106  mov     dword ptr [rbp+FileInformation+4], ebx
0x1800a5109  mov     rax, [rbp+FileInformation]
0x1800a510d  jmp     loc_1800A538A
0x1800a5112  call    cs:__imp_GetLastError
0x1800a5119  nop     dword ptr [rax+rax+00h]
0x1800a511e  mov     ecx, eax
0x1800a5120  mov     edi, eax
0x1800a5122  sub     ecx, 1
0x1800a5125  jz      short loc_1800A5166
0x1800a5127  sub     ecx, 31h ; '1'
0x1800a512a  jz      short loc_1800A5166
0x1800a512c  cmp     ecx, 25h ; '%'
0x1800a512f  jz      short loc_1800A5166
0x1800a5131  xor     sil, sil
0x1800a5134  xor     r15d, r15d
0x1800a5137  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800a513b  jz      short loc_1800A5154
0x1800a513d  mov     rcx, rbx; hObject
0x1800a5140  call    cs:__imp_CloseHandle
0x1800a5147  nop     dword ptr [rax+rax+00h]
0x1800a514c  test    eax, eax
0x1800a514e  jz      loc_1800A53B2
0x1800a5154  mov     byte ptr [rbp+FileInformation], sil
0x1800a5158  mov     word ptr [rbp+FileInformation+1], r15w
0x1800a515d  mov     byte ptr [rbp+FileInformation+3], r15b
0x1800a5161  jmp     loc_1800A50A4
0x1800a5166  mov     rcx, rbx; hFile
0x1800a5169  call    _anonymous_namespace____Set_delete_flag
0x1800a516e  mov     edi, eax
0x1800a5170  test    eax, eax
0x1800a5172  jz      loc_1800A5079
0x1800a5178  cmp     eax, r15d
0x1800a517b  jnz     loc_1800A52FE
0x1800a5181  test    sil, sil
0x1800a5184  jz      loc_1800A52FE
0x1800a518a  xor     eax, eax
0x1800a518c  lea     r8, [rbp+var_30]; lpFileInformation
0x1800a5190  xorps   xmm0, xmm0
0x1800a5193  mov     [rbp+var_10], rax
0x1800a5197  xor     edx, edx; FileInformationClass
0x1800a5199  mov     rcx, rbx; hFile
0x1800a519c  movups  [rbp+var_30], xmm0
0x1800a51a0  lea     edi, [rax+28h]
0x1800a51a3  mov     r9d, edi; dwBufferSize
0x1800a51a6  movups  [rbp+var_20], xmm0
0x1800a51aa  call    cs:__imp_GetFileInformationByHandleEx
0x1800a51b1  nop     dword ptr [rax+rax+00h]
0x1800a51b6  test    eax, eax
0x1800a51b8  jnz     short loc_1800A51FC
0x1800a51ba  xor     eax, eax
0x1800a51bc  mov     byte ptr [rbp+hFile], 0
0x1800a51c0  mov     word ptr [rbp+hFile+1], ax
0x1800a51c4  mov     byte ptr [rbp+hFile+3], al
0x1800a51c7  call    cs:__imp_GetLastError
0x1800a51ce  nop     dword ptr [rax+rax+00h]
0x1800a51d3  mov     dword ptr [rbp+hFile+4], eax
0x1800a51d6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800a51da  jz      loc_1800A5386
0x1800a51e0  mov     rcx, rbx; hObject
0x1800a51e3  call    cs:__imp_CloseHandle
0x1800a51ea  nop     dword ptr [rax+rax+00h]
0x1800a51ef  test    eax, eax
0x1800a51f1  jz      loc_1800A53AC
0x1800a51f7  jmp     loc_1800A5386
0x1800a51fc  mov     eax, dword ptr [rbp+var_10]
0x1800a51ff  test    al, 1
0x1800a5201  jz      loc_1800A5291
0x1800a5207  xor     eax, 1
0x1800a520a  lea     r8, [rbp+var_30]; lpFileInformation
0x1800a520e  mov     r9d, edi; dwBufferSize
0x1800a5211  mov     dword ptr [rbp+var_10], eax
0x1800a5214  xor     edx, edx; FileInformationClass
0x1800a5216  mov     rcx, rbx; hFile
0x1800a5219  call    cs:__imp_SetFileInformationByHandle
0x1800a5220  nop     dword ptr [rax+rax+00h]
0x1800a5225  test    eax, eax
0x1800a5227  jz      short loc_1800A51BA
0x1800a5229  mov     rcx, rbx; hFile
0x1800a522c  call    _anonymous_namespace____Set_delete_flag
0x1800a5231  test    eax, eax
0x1800a5233  jnz     short loc_1800A5268
0x1800a5235  xor     edi, edi
0x1800a5237  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800a523b  jz      short loc_1800A5254
0x1800a523d  mov     rcx, rbx; hObject
0x1800a5240  call    cs:__imp_CloseHandle
0x1800a5247  nop     dword ptr [rax+rax+00h]
0x1800a524c  test    eax, eax
0x1800a524e  jz      loc_1800A53AC
0x1800a5254  mov     byte ptr [rbp+hFile], 1
0x1800a5258  mov     word ptr [rbp+hFile+1], di
0x1800a525c  mov     byte ptr [rbp+hFile+3], dil
0x1800a5260  mov     dword ptr [rbp+hFile+4], edi
0x1800a5263  jmp     loc_1800A5386
0x1800a5268  cmp     eax, r15d
0x1800a526b  jnz     short loc_1800A52BC
0x1800a526d  or      dword ptr [rbp+var_10], 1
0x1800a5271  lea     r8, [rbp+var_30]; lpFileInformation
0x1800a5275  mov     r9d, edi; dwBufferSize
0x1800a5278  xor     edx, edx; FileInformationClass
0x1800a527a  mov     rcx, rbx; hFile
0x1800a527d  call    cs:__imp_SetFileInformationByHandle
0x1800a5284  nop     dword ptr [rax+rax+00h]
0x1800a5289  test    eax, eax
0x1800a528b  jz      loc_1800A51BA
0x1800a5291  xor     dil, dil
0x1800a5294  xor     esi, esi
0x1800a5296  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800a529a  jz      short loc_1800A52B3
0x1800a529c  mov     rcx, rbx; hObject
0x1800a529f  call    cs:__imp_CloseHandle
0x1800a52a6  nop     dword ptr [rax+rax+00h]
0x1800a52ab  test    eax, eax
0x1800a52ad  jz      loc_1800A53AC
0x1800a52b3  mov     dword ptr [rbp+hFile+4], r15d
0x1800a52b7  jmp     loc_1800A537A
0x1800a52bc  xor     eax, eax
0x1800a52be  mov     byte ptr [rbp+hFile], 0
0x1800a52c2  mov     word ptr [rbp+hFile+1], ax
0x1800a52c6  mov     byte ptr [rbp+hFile+3], al
0x1800a52c9  call    cs:__imp_GetLastError
0x1800a52d0  nop     dword ptr [rax+rax+00h]
0x1800a52d5  mov     dword ptr [rbp+hFile+4], eax
0x1800a52d8  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800a52dc  jz      loc_1800A5386
0x1800a52e2  mov     rcx, rbx; hObject
0x1800a52e5  call    cs:__imp_CloseHandle
0x1800a52ec  nop     dword ptr [rax+rax+00h]
0x1800a52f1  test    eax, eax
0x1800a52f3  jz      loc_1800A53B2
0x1800a52f9  jmp     loc_1800A5386
0x1800a52fe  xor     sil, sil
0x1800a5301  xor     r15d, r15d
0x1800a5304  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800a5308  jz      short loc_1800A5321
0x1800a530a  mov     rcx, rbx; hObject
0x1800a530d  call    cs:__imp_CloseHandle
0x1800a5314  nop     dword ptr [rax+rax+00h]
0x1800a5319  test    eax, eax
0x1800a531b  jz      loc_1800A53B2
0x1800a5321  mov     byte ptr [rbp+hFile], sil
0x1800a5325  mov     word ptr [rbp+hFile+1], r15w
0x1800a532a  mov     byte ptr [rbp+hFile+3], r15b
0x1800a532e  jmp     loc_1800A5260
0x1800a5333  xor     dil, dil
0x1800a5336  xor     esi, esi
0x1800a5338  sub     eax, 2
0x1800a533b  jz      short loc_1800A535B
0x1800a533d  sub     eax, 1
0x1800a5340  jz      short loc_1800A535B
0x1800a5342  sub     eax, 32h ; '2'
0x1800a5345  jz      short loc_1800A535B
0x1800a5347  sub     eax, 0Bh
0x1800a534a  jz      short loc_1800A535B
0x1800a534c  sub     eax, 3Bh ; ';'
0x1800a534f  jz      short loc_1800A535B
0x1800a5351  sub     eax, 26h ; '&'
0x1800a5354  jz      short loc_1800A535B
0x1800a5356  cmp     eax, 6Ah ; 'j'
0x1800a5359  jnz     short loc_1800A535D
0x1800a535b  xor     ebx, ebx
0x1800a535d  mov     rcx, [rbp+hFile]; hObject
0x1800a5361  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800a5365  jz      short loc_1800A5377
0x1800a5367  call    cs:__imp_CloseHandle
0x1800a536e  nop     dword ptr [rax+rax+00h]
0x1800a5373  test    eax, eax
0x1800a5375  jz      short loc_1800A53B2
0x1800a5377  mov     dword ptr [rbp+hFile+4], ebx
0x1800a537a  mov     byte ptr [rbp+hFile], dil
0x1800a537e  mov     word ptr [rbp+hFile+1], si
0x1800a5382  mov     byte ptr [rbp+hFile+3], sil
0x1800a5386  mov     rax, [rbp+hFile]
0x1800a538a  mov     rcx, [rbp+var_8]
0x1800a538e  xor     rcx, rsp; StackCookie
0x1800a5391  call    __security_check_cookie
0x1800a5396  lea     r11, [rsp+60h+var_s0]
0x1800a539b  mov     rbx, [r11+28h]
0x1800a539f  mov     rsi, [r11+30h]
0x1800a53a3  mov     rsp, r11
0x1800a53a6  pop     r15
0x1800a53a8  pop     rdi
0x1800a53a9  pop     rbp
0x1800a53aa  retn
0x1800a53ac  call    abort
0x1800a53b2  call    abort
```
