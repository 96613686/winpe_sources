# file_information

- ea: `0x1800f661c`
- end: `0x1800f68ed`
- name: `file_information`
- size: `721`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800f5838`
- `0x1800f5e24`
- `0x1800f6d98`
- `0x1800f7330`

## callees

- `0x1800149c0`
- `0x180014fc0`
- `0x180015810`
- `0x1800ef3f8`
- `0x1800f661c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f66ca`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f679f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f66ca`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f679f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800f682b`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800f682b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800f6692`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800f66be`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800f6692`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800f66be`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800f66f1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800f66f1`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800f67b4`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800f67b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f66a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f66d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6761`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f66a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f66d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6761`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800f6753`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800f6793`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800f6753`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800f6793`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f67bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f67bf`

## pseudocode

```c
__int64 __fastcall file_information(
        __int64 a1,
        const WCHAR *a2,
        struct _BY_HANDLE_FILE_INFORMATION *a3,
        _WORD *a4,
        int a5)
{
  __int64 v7; // rbx
  __int64 v9; // rsi
  HANDLE FirstFileW; // r14
  wchar_t *v11; // rbx
  DWORD LastError; // eax
  int v14; // eax
  __int64 v15; // rcx
  void *v16; // r14
  wchar_t *v17; // rbx
  BOOL FileInformationByHandle; // ebx
  __int16 v19; // ax
  __int16 v20; // ax
  wchar_t *v21; // rax
  __int16 v22; // ax
  __int128 v24; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v25; // [rsp+48h] [rbp-B8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF

  v7 = a1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v9 = -1;
  v24 = 0;
  v25 = 0;
  if ( a5 || a4 )
  {
    FirstFileW = FindFirstFileW(a2, &FindFileData);
    if ( FirstFileW == (HANDLE)-1LL )
    {
      if ( GetLastError() != 123
        || (v11 = _la_win_permissive_name_w(a2),
            FirstFileW = FindFirstFileW(v11, &FindFileData),
            free(v11),
            FirstFileW == (HANDLE)-1LL) )
      {
LABEL_6:
        LastError = GetLastError();
        _la_dosmaperr(LastError);
        return 0xFFFFFFFFLL;
      }
      v7 = a1;
    }
    FindClose(FirstFileW);
  }
  v14 = 0x2000000;
  if ( a5 && (FindFileData.dwFileAttributes & 0x400) != 0 && FindFileData.dwReserved0 == -1610612724 )
    v14 = 35651584;
  v15 = *(_QWORD *)(v7 + 352);
  v24 = 0;
  DWORD2(v24) = v14;
  LODWORD(v24) = 32;
  v25 = 0;
  v16 = (void *)CreateFile2(v15, 0, 0, 3, &v24);
  if ( v16 == (void *)-1LL )
  {
    if ( GetLastError() != 123 )
      goto LABEL_6;
    v17 = _la_win_permissive_name_w(a2);
    v16 = (void *)CreateFile2(v17, 0, 0, 3, &v24);
    free(v17);
    if ( v16 == (void *)-1LL )
      goto LABEL_6;
  }
  FileInformationByHandle = GetFileInformationByHandle(v16, a3);
  CloseHandle(v16);
  if ( !FileInformationByHandle )
    goto LABEL_6;
  if ( a4 )
  {
    v19 = 292;
    *a4 = 292;
    if ( (a3->dwFileAttributes & 1) == 0 )
    {
      v19 = 438;
      *a4 = 438;
    }
    if ( (a3->dwFileAttributes & 0x400) != 0 && FindFileData.dwReserved0 == -1610612724 )
    {
      v20 = v19 | 0xA000;
LABEL_25:
      *a4 = v20;
      return 0;
    }
    if ( (a3->dwFileAttributes & 0x10) != 0 )
    {
      v20 = v19 | 0x4049;
      goto LABEL_25;
    }
    *a4 = v19 | 0x8000;
    v21 = wcsrchr(a2, 0x2Eu);
    if ( !v21 )
      return 0;
    do
      ++v9;
    while ( v21[v9] );
    if ( v9 != 4 )
      return 0;
    if ( v21[1] != 66 )
    {
      if ( v21[1] == 67 )
        goto LABEL_37;
      if ( v21[1] == 69 )
      {
LABEL_35:
        if ( ((v21[2] - 88) & 0xFFDF) != 0 )
          return 0;
        v22 = v21[3] - 69;
LABEL_41:
        if ( (v22 & 0xFFDF) == 0 )
          *a4 |= 0x49u;
        return 0;
      }
      if ( v21[1] != 98 )
      {
        if ( v21[1] != 99 )
        {
          if ( v21[1] != 101 )
            return 0;
          goto LABEL_35;
        }
LABEL_37:
        if ( ((v21[2] - 77) & 0xFFDF) != 0 )
          return 0;
        v22 = v21[3] - 68;
        goto LABEL_41;
      }
    }
    if ( ((v21[2] - 65) & 0xFFDF) != 0 )
      return 0;
    v22 = v21[3] - 84;
    goto LABEL_41;
  }
  return 0;
}

```

## disassembly

```asm
0x1800f661c  push    rbp
0x1800f661e  push    rbx
0x1800f661f  push    rsi
0x1800f6620  push    rdi
0x1800f6621  push    r12
0x1800f6623  push    r14
0x1800f6625  push    r15
0x1800f6627  lea     rbp, [rsp-1C0h]
0x1800f662f  sub     rsp, 2C0h
0x1800f6636  mov     rax, cs:__security_cookie
0x1800f663d  xor     rax, rsp
0x1800f6640  mov     [rbp+1F0h+var_40], rax
0x1800f6647  mov     r12, r8
0x1800f664a  mov     [rsp+2F0h+var_2C0], rcx
0x1800f664f  mov     r15, rdx
0x1800f6652  mov     rbx, rcx
0x1800f6655  xor     edx, edx; Val
0x1800f6657  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x1800f665c  mov     r8d, 250h; Size
0x1800f6662  mov     rdi, r9
0x1800f6665  call    memset_0
0x1800f666a  xorps   xmm0, xmm0
0x1800f666d  xor     eax, eax
0x1800f666f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800f6673  movups  [rsp+2F0h+var_2B8], xmm0
0x1800f6678  movups  [rsp+2F0h+var_2A8], xmm0
0x1800f667d  cmp     [rbp+1F0h+arg_20], eax
0x1800f6683  jnz     short loc_1800F668A
0x1800f6685  test    rdi, rdi
0x1800f6688  jz      short loc_1800F66F7
0x1800f668a  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x1800f668f  mov     rcx, r15; lpFileName
0x1800f6692  call    cs:__imp_FindFirstFileW
0x1800f6698  mov     r14, rax
0x1800f669b  cmp     rax, rsi
0x1800f669e  jnz     short loc_1800F66EE
0x1800f66a0  call    cs:__imp_GetLastError
0x1800f66a6  cmp     eax, 7Bh ; '{'
0x1800f66a9  jnz     short loc_1800F66D5
0x1800f66ab  mov     rcx, r15; lpFileName
0x1800f66ae  call    __la_win_permissive_name_w
0x1800f66b3  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x1800f66b8  mov     rcx, rax; lpFileName
0x1800f66bb  mov     rbx, rax
0x1800f66be  call    cs:__imp_FindFirstFileW
0x1800f66c4  mov     rcx, rbx; Block
0x1800f66c7  mov     r14, rax
0x1800f66ca  call    cs:__imp_free
0x1800f66d0  cmp     r14, rsi
0x1800f66d3  jnz     short loc_1800F66E9
0x1800f66d5  call    cs:__imp_GetLastError
0x1800f66db  mov     ecx, eax
0x1800f66dd  call    __la_dosmaperr
0x1800f66e2  mov     eax, esi
0x1800f66e4  jmp     loc_1800F68CC
0x1800f66e9  mov     rbx, [rsp+2F0h+var_2C0]
0x1800f66ee  mov     rcx, r14; hFindFile
0x1800f66f1  call    cs:__imp_FindClose
0x1800f66f7  cmp     [rbp+1F0h+arg_20], 0
0x1800f66fe  mov     eax, 2000000h
0x1800f6703  jz      short loc_1800F671E
0x1800f6705  test    [rsp+2F0h+FindFileData.dwFileAttributes], 400h
0x1800f670d  jz      short loc_1800F671E
0x1800f670f  cmp     [rbp+1F0h+FindFileData.dwReserved0], 0A000000Ch
0x1800f6716  mov     ecx, 2200000h
0x1800f671b  cmovz   eax, ecx
0x1800f671e  mov     rcx, [rbx+160h]
0x1800f6725  xorps   xmm0, xmm0
0x1800f6728  movups  [rsp+2F0h+var_2B8], xmm0
0x1800f672d  mov     dword ptr [rsp+2F0h+var_2B8+8], eax
0x1800f6731  mov     r9d, 3
0x1800f6737  lea     rax, [rsp+2F0h+var_2B8]
0x1800f673c  mov     dword ptr [rsp+2F0h+var_2B8], 20h ; ' '
0x1800f6744  xor     r8d, r8d
0x1800f6747  mov     [rsp+2F0h+var_2D0], rax
0x1800f674c  xor     edx, edx
0x1800f674e  movups  [rsp+2F0h+var_2A8], xmm0
0x1800f6753  call    cs:__imp_CreateFile2
0x1800f6759  mov     r14, rax
0x1800f675c  cmp     rax, rsi
0x1800f675f  jnz     short loc_1800F67AE
0x1800f6761  call    cs:__imp_GetLastError
0x1800f6767  cmp     eax, 7Bh ; '{'
0x1800f676a  jnz     loc_1800F66D5
0x1800f6770  mov     rcx, r15; lpFileName
0x1800f6773  call    __la_win_permissive_name_w
0x1800f6778  mov     rbx, rax
0x1800f677b  mov     r9d, 3
0x1800f6781  lea     rax, [rsp+2F0h+var_2B8]
0x1800f6786  mov     rcx, rbx
0x1800f6789  xor     r8d, r8d
0x1800f678c  mov     [rsp+2F0h+var_2D0], rax
0x1800f6791  xor     edx, edx
0x1800f6793  call    cs:__imp_CreateFile2
0x1800f6799  mov     rcx, rbx; Block
0x1800f679c  mov     r14, rax
0x1800f679f  call    cs:__imp_free
0x1800f67a5  cmp     r14, rsi
0x1800f67a8  jz      loc_1800F66D5
0x1800f67ae  mov     rdx, r12; lpFileInformation
0x1800f67b1  mov     rcx, r14; hFile
0x1800f67b4  call    cs:__imp_GetFileInformationByHandle
0x1800f67ba  mov     rcx, r14; hObject
0x1800f67bd  mov     ebx, eax
0x1800f67bf  call    cs:__imp_CloseHandle
0x1800f67c5  xor     r14d, r14d
0x1800f67c8  test    ebx, ebx
0x1800f67ca  jz      loc_1800F66D5
0x1800f67d0  test    rdi, rdi
0x1800f67d3  jz      loc_1800F68CA
0x1800f67d9  mov     eax, 124h
0x1800f67de  mov     [rdi], ax
0x1800f67e1  test    byte ptr [r12], 1
0x1800f67e6  jnz     short loc_1800F67F0
0x1800f67e8  mov     eax, 1B6h
0x1800f67ed  mov     [rdi], ax
0x1800f67f0  test    dword ptr [r12], 400h
0x1800f67f8  jz      short loc_1800F6809
0x1800f67fa  cmp     [rbp+1F0h+FindFileData.dwReserved0], 0A000000Ch
0x1800f6801  jnz     short loc_1800F6809
0x1800f6803  or      ax, 0A000h
0x1800f6807  jmp     short loc_1800F6814
0x1800f6809  test    byte ptr [r12], 10h
0x1800f680e  jz      short loc_1800F681C
0x1800f6810  or      ax, 4049h
0x1800f6814  mov     [rdi], ax
0x1800f6817  jmp     loc_1800F68CA
0x1800f681c  or      ax, 8000h
0x1800f6820  mov     edx, 2Eh ; '.'; Ch
0x1800f6825  mov     rcx, r15; Str
0x1800f6828  mov     [rdi], ax
0x1800f682b  call    cs:__imp_wcsrchr
0x1800f6831  mov     rdx, rax
0x1800f6834  test    rax, rax
0x1800f6837  jz      loc_1800F68CA
0x1800f683d  inc     rsi
0x1800f6840  cmp     [rax+rsi*2], r14w
0x1800f6845  jnz     short loc_1800F683D
0x1800f6847  cmp     rsi, 4
0x1800f684b  jnz     short loc_1800F68CA
0x1800f684d  movzx   ecx, word ptr [rax+2]
0x1800f6851  sub     ecx, 42h ; 'B'
0x1800f6854  jz      short loc_1800F68A7
0x1800f6856  sub     ecx, 1
0x1800f6859  jz      short loc_1800F688B
0x1800f685b  sub     ecx, 2
0x1800f685e  jz      short loc_1800F686F
0x1800f6860  sub     ecx, 1Dh
0x1800f6863  jz      short loc_1800F68A7
0x1800f6865  sub     ecx, 1
0x1800f6868  jz      short loc_1800F688B
0x1800f686a  cmp     ecx, 2
0x1800f686d  jnz     short loc_1800F68CA
0x1800f686f  movzx   eax, word ptr [rax+4]
0x1800f6873  mov     ecx, 0FFDFh
0x1800f6878  sub     ax, 58h ; 'X'
0x1800f687c  test    cx, ax
0x1800f687f  jnz     short loc_1800F68CA
0x1800f6881  movzx   eax, word ptr [rdx+6]
0x1800f6885  sub     ax, 45h ; 'E'
0x1800f6889  jmp     short loc_1800F68C1
0x1800f688b  movzx   eax, word ptr [rax+4]
0x1800f688f  mov     ecx, 0FFDFh
0x1800f6894  sub     ax, 4Dh ; 'M'
0x1800f6898  test    cx, ax
0x1800f689b  jnz     short loc_1800F68CA
0x1800f689d  movzx   eax, word ptr [rdx+6]
0x1800f68a1  sub     ax, 44h ; 'D'
0x1800f68a5  jmp     short loc_1800F68C1
0x1800f68a7  movzx   eax, word ptr [rax+4]
0x1800f68ab  mov     ecx, 0FFDFh
0x1800f68b0  sub     ax, 41h ; 'A'
0x1800f68b4  test    cx, ax
0x1800f68b7  jnz     short loc_1800F68CA
0x1800f68b9  movzx   eax, word ptr [rdx+6]
0x1800f68bd  sub     ax, 54h ; 'T'
0x1800f68c1  test    cx, ax
0x1800f68c4  jnz     short loc_1800F68CA
0x1800f68c6  or      word ptr [rdi], 49h
0x1800f68ca  xor     eax, eax
0x1800f68cc  mov     rcx, [rbp+1F0h+var_40]
0x1800f68d3  xor     rcx, rsp; StackCookie
0x1800f68d6  call    __security_check_cookie
0x1800f68db  add     rsp, 2C0h
0x1800f68e2  pop     r15
0x1800f68e4  pop     r14
0x1800f68e6  pop     r12
0x1800f68e8  pop     rdi
0x1800f68e9  pop     rsi
0x1800f68ea  pop     rbx
0x1800f68eb  pop     rbp
0x1800f68ec  retn
```
