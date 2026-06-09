# __std_fs_remove

- ea: `0x180007670`
- end: `0x1800079b2`
- name: `__std_fs_remove`
- size: `834`
- prototype: `HANDLE __fastcall(__int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18005aeb8`
- `0x18005c580`
- `0x18006a914`
- `0x18006ad88`

## callees

- `0x180004ca0`
- `0x1800067d0`
- `0x18000753c`
- `0x180007670`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800078cf`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180007977`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800078cf`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180007977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000774a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007798`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007829`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007876`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007902`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000791d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000796d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000774a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007798`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007829`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007876`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007902`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000791d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000796d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800076d9`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180007855`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800078a9`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800076d9`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180007855`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800078a9`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800077fc`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800077fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x180007670  mov     [rsp-18h+arg_8], rbx
0x180007675  mov     [rsp-18h+arg_10], rsi
0x18000767a  push    rbp
0x18000767b  push    rdi
0x18000767c  push    r15
0x18000767e  mov     rbp, rsp
0x180007681  sub     rsp, 60h
0x180007685  mov     rax, cs:__security_cookie
0x18000768c  xor     rax, rsp
0x18000768f  mov     [rbp+var_8], rax
0x180007693  mov     rdi, rcx
0x180007696  mov     rdx, rcx
0x180007699  lea     rcx, [rbp+hFile]
0x18000769d  mov     r9d, 2200000h
0x1800076a3  mov     r8d, 10180h
0x1800076a9  call    __std_fs_open_handle
0x1800076ae  mov     ebx, eax
0x1800076b0  mov     r15d, 5
0x1800076b6  test    eax, eax
0x1800076b8  jnz     short loc_180007711
0x1800076ba  mov     sil, 1
0x1800076bd  mov     rbx, [rbp+hFile]
0x1800076c1  lea     r8, [rbp+FileInformation]; lpFileInformation
0x1800076c5  mov     r9d, 4; dwBufferSize
0x1800076cb  mov     dword ptr [rbp+FileInformation], 13h
0x1800076d2  mov     rcx, rbx; hFile
0x1800076d5  lea     edx, [r9+11h]; FileInformationClass
0x1800076d9  call    cs:__imp_SetFileInformationByHandle
0x1800076df  test    eax, eax
0x1800076e1  jz      loc_180007770
0x1800076e7  xor     edi, edi
0x1800076e9  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800076ed  jz      short loc_180007700
0x1800076ef  mov     rcx, rbx; hObject
0x1800076f2  call    cs:__imp_CloseHandle
0x1800076f8  test    eax, eax
0x1800076fa  jz      loc_180007977
0x180007700  mov     byte ptr [rbp+FileInformation], 1
0x180007704  mov     word ptr [rbp+FileInformation+1], di
0x180007708  mov     byte ptr [rbp+FileInformation+3], dil
0x18000770c  mov     dword ptr [rbp+FileInformation+4], edi
0x18000770f  jmp     short loc_180007767
0x180007711  cmp     eax, r15d
0x180007714  jnz     loc_180007939
0x18000771a  mov     r9d, 2200000h
0x180007720  lea     rcx, [rbp+hFile]
0x180007724  mov     r8d, 10000h
0x18000772a  mov     rdx, rdi
0x18000772d  xor     sil, sil
0x180007730  call    __std_fs_open_handle
0x180007735  mov     ebx, eax
0x180007737  test    eax, eax
0x180007739  jz      short loc_1800076BD
0x18000773b  mov     rcx, [rbp+hFile]; hObject
0x18000773f  xor     dil, dil
0x180007742  xor     esi, esi
0x180007744  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180007748  jz      short loc_180007758
0x18000774a  call    cs:__imp_CloseHandle
0x180007750  test    eax, eax
0x180007752  jz      loc_180007977
0x180007758  mov     byte ptr [rbp+FileInformation], dil
0x18000775c  mov     word ptr [rbp+FileInformation+1], si
0x180007760  mov     byte ptr [rbp+FileInformation+3], sil
0x180007764  mov     dword ptr [rbp+FileInformation+4], ebx
0x180007767  mov     rax, [rbp+FileInformation]
0x18000776b  jmp     loc_180007991
0x180007770  call    cs:__imp_GetLastError
0x180007776  mov     ecx, eax
0x180007778  mov     edi, eax
0x18000777a  sub     ecx, 1
0x18000777d  jz      short loc_1800077B8
0x18000777f  sub     ecx, 31h ; '1'
0x180007782  jz      short loc_1800077B8
0x180007784  cmp     ecx, 25h ; '%'
0x180007787  jz      short loc_1800077B8
0x180007789  xor     sil, sil
0x18000778c  xor     r15d, r15d
0x18000778f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180007793  jz      short loc_1800077A6
0x180007795  mov     rcx, rbx; hObject
0x180007798  call    cs:__imp_CloseHandle
0x18000779e  test    eax, eax
0x1800077a0  jz      loc_180007977
0x1800077a6  mov     byte ptr [rbp+FileInformation], sil
0x1800077aa  mov     word ptr [rbp+FileInformation+1], r15w
0x1800077af  mov     byte ptr [rbp+FileInformation+3], r15b
0x1800077b3  jmp     loc_18000770C
0x1800077b8  mov     rcx, rbx; hFile
0x1800077bb  call    _anonymous_namespace____Set_delete_flag
0x1800077c0  mov     edi, eax
0x1800077c2  test    eax, eax
0x1800077c4  jz      loc_1800076E7
0x1800077ca  cmp     eax, r15d
0x1800077cd  jnz     loc_18000790E
0x1800077d3  test    sil, sil
0x1800077d6  jz      loc_18000790E
0x1800077dc  xor     eax, eax
0x1800077de  lea     r8, [rbp+var_30]; lpFileInformation
0x1800077e2  xorps   xmm0, xmm0
0x1800077e5  mov     [rbp+var_10], rax
0x1800077e9  xor     edx, edx; FileInformationClass
0x1800077eb  mov     rcx, rbx; hFile
0x1800077ee  movups  [rbp+var_30], xmm0
0x1800077f2  lea     edi, [rax+28h]
0x1800077f5  mov     r9d, edi; dwBufferSize
0x1800077f8  movups  [rbp+var_20], xmm0
0x1800077fc  call    cs:__imp_GetFileInformationByHandleEx
0x180007802  test    eax, eax
0x180007804  jnz     short loc_18000783C
0x180007806  xor     eax, eax
0x180007808  mov     byte ptr [rbp+hFile], 0
0x18000780c  mov     word ptr [rbp+hFile+1], ax
0x180007810  mov     byte ptr [rbp+hFile+3], al
0x180007813  call    cs:__imp_GetLastError
0x180007819  mov     dword ptr [rbp+hFile+4], eax
0x18000781c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180007820  jz      loc_18000798D
0x180007826  mov     rcx, rbx; hObject
0x180007829  call    cs:__imp_CloseHandle
0x18000782f  test    eax, eax
0x180007831  jz      loc_1800078CF
0x180007837  jmp     loc_18000798D
0x18000783c  mov     eax, dword ptr [rbp+var_10]
0x18000783f  test    al, 1
0x180007841  jz      short loc_1800078B7
0x180007843  xor     eax, 1
0x180007846  lea     r8, [rbp+var_30]; lpFileInformation
0x18000784a  mov     r9d, edi; dwBufferSize
0x18000784d  mov     dword ptr [rbp+var_10], eax
0x180007850  xor     edx, edx; FileInformationClass
0x180007852  mov     rcx, rbx; hFile
0x180007855  call    cs:__imp_SetFileInformationByHandle
0x18000785b  test    eax, eax
0x18000785d  jz      short loc_180007806
0x18000785f  mov     rcx, rbx; hFile
0x180007862  call    _anonymous_namespace____Set_delete_flag
0x180007867  test    eax, eax
0x180007869  jnz     short loc_180007894
0x18000786b  xor     edi, edi
0x18000786d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180007871  jz      short loc_180007880
0x180007873  mov     rcx, rbx; hObject
0x180007876  call    cs:__imp_CloseHandle
0x18000787c  test    eax, eax
0x18000787e  jz      short loc_1800078CF
0x180007880  mov     byte ptr [rbp+hFile], 1
0x180007884  mov     word ptr [rbp+hFile+1], di
0x180007888  mov     byte ptr [rbp+hFile+3], dil
0x18000788c  mov     dword ptr [rbp+hFile+4], edi
0x18000788f  jmp     loc_18000798D
0x180007894  cmp     eax, r15d
0x180007897  jnz     short loc_1800078DF
0x180007899  or      dword ptr [rbp+var_10], 1
0x18000789d  lea     r8, [rbp+var_30]; lpFileInformation
0x1800078a1  mov     r9d, edi; dwBufferSize
0x1800078a4  xor     edx, edx; FileInformationClass
0x1800078a6  mov     rcx, rbx; hFile
0x1800078a9  call    cs:__imp_SetFileInformationByHandle
0x1800078af  test    eax, eax
0x1800078b1  jz      loc_180007806
0x1800078b7  xor     dil, dil
0x1800078ba  xor     esi, esi
0x1800078bc  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800078c0  jz      short loc_1800078D6
0x1800078c2  mov     rcx, rbx; hObject
0x1800078c5  call    cs:__imp_CloseHandle
0x1800078cb  test    eax, eax
0x1800078cd  jnz     short loc_1800078D6
0x1800078cf  call    cs:__imp_abort
0x1800078d6  mov     dword ptr [rbp+hFile+4], r15d
0x1800078da  jmp     loc_180007981
0x1800078df  xor     eax, eax
0x1800078e1  mov     byte ptr [rbp+hFile], 0
0x1800078e5  mov     word ptr [rbp+hFile+1], ax
0x1800078e9  mov     byte ptr [rbp+hFile+3], al
0x1800078ec  call    cs:__imp_GetLastError
0x1800078f2  mov     dword ptr [rbp+hFile+4], eax
0x1800078f5  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800078f9  jz      loc_18000798D
0x1800078ff  mov     rcx, rbx; hObject
0x180007902  call    cs:__imp_CloseHandle
0x180007908  test    eax, eax
0x18000790a  jz      short loc_180007977
0x18000790c  jmp     short loc_18000798D
0x18000790e  xor     sil, sil
0x180007911  xor     r15d, r15d
0x180007914  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180007918  jz      short loc_180007927
0x18000791a  mov     rcx, rbx; hObject
0x18000791d  call    cs:__imp_CloseHandle
0x180007923  test    eax, eax
0x180007925  jz      short loc_180007977
0x180007927  mov     byte ptr [rbp+hFile], sil
0x18000792b  mov     word ptr [rbp+hFile+1], r15w
0x180007930  mov     byte ptr [rbp+hFile+3], r15b
0x180007934  jmp     loc_18000788C
0x180007939  xor     dil, dil
0x18000793c  xor     esi, esi
0x18000793e  sub     eax, 2
0x180007941  jz      short loc_180007961
0x180007943  sub     eax, 1
0x180007946  jz      short loc_180007961
0x180007948  sub     eax, 32h ; '2'
0x18000794b  jz      short loc_180007961
0x18000794d  sub     eax, 0Bh
0x180007950  jz      short loc_180007961
0x180007952  sub     eax, 3Bh ; ';'
0x180007955  jz      short loc_180007961
0x180007957  sub     eax, 26h ; '&'
0x18000795a  jz      short loc_180007961
0x18000795c  cmp     eax, 6Ah ; 'j'
0x18000795f  jnz     short loc_180007963
0x180007961  xor     ebx, ebx
0x180007963  mov     rcx, [rbp+hFile]; hObject
0x180007967  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000796b  jz      short loc_18000797E
0x18000796d  call    cs:__imp_CloseHandle
0x180007973  test    eax, eax
0x180007975  jnz     short loc_18000797E
0x180007977  call    cs:__imp_abort
0x18000797e  mov     dword ptr [rbp+hFile+4], ebx
0x180007981  mov     byte ptr [rbp+hFile], dil
0x180007985  mov     word ptr [rbp+hFile+1], si
0x180007989  mov     byte ptr [rbp+hFile+3], sil
0x18000798d  mov     rax, [rbp+hFile]
0x180007991  mov     rcx, [rbp+var_8]
0x180007995  xor     rcx, rsp; StackCookie
0x180007998  call    __security_check_cookie
0x18000799d  lea     r11, [rsp+60h+var_s0]
0x1800079a2  mov     rbx, [r11+28h]
0x1800079a6  mov     rsi, [r11+30h]
0x1800079aa  mov     rsp, r11
0x1800079ad  pop     r15
0x1800079af  pop     rdi
0x1800079b0  pop     rbp
0x1800079b1  retn
```
