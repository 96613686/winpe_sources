# TfsGetDirectorySize

- ea: `0x18002b1e0`
- end: `0x18002b3b5`
- name: `TfsGetDirectorySize`
- size: `469`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, int, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002c94c`

## callees

- `0x18000b43c`
- `0x18000b4f0`
- `0x18000b7dc`
- `0x18002b1e0`
- `0x18002cf62`
- `0x18002cfa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b259`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b2d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b32b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b259`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b2d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b32b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b357`
- `KERNEL32!LocalFree` at `0x18002b2f6`
- `KERNEL32!LocalFree` at `0x18002b380`
- `KERNEL32!LocalFree` at `0x18002b2f6`
- `KERNEL32!LocalFree` at `0x18002b380`
- `KERNEL32!LocalAlloc` at `0x18002b22c`
- `KERNEL32!LocalAlloc` at `0x18002b22c`
- `KERNEL32!FindFirstFileW` at `0x18002b2aa`
- `KERNEL32!FindFirstFileW` at `0x18002b2aa`
- `KERNEL32!FindNextFileW` at `0x18002b321`
- `KERNEL32!FindNextFileW` at `0x18002b321`
- `KERNEL32!FindClose` at `0x18002b389`
- `KERNEL32!FindClose` at `0x18002b389`

## pseudocode

```c
__int64 __fastcall TfsGetDirectorySize(STRSAFE_LPCWSTR pszSrc, int a2, _QWORD *a3)
{
  SIZE_T v6; // rdx
  size_t v7; // rbx
  wchar_t *v8; // rax
  wchar_t *v9; // rdi
  __int64 v10; // rbx
  DWORD LastError; // eax
  HANDLE FirstFileW; // rsi
  __int64 v14; // rbx
  DWORD v15; // eax
  __int64 v16; // rbx
  DWORD v17; // eax
  unsigned int v18; // ebx
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-278h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v6 = (unsigned int)(2 * a2 + 4);
  v7 = v6;
  v8 = (wchar_t *)LocalAlloc(0x40u, v6);
  v9 = v8;
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LastError = GetLastError();
      WPP_SF_d(v10, 24, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, LastError);
    }
    return 0;
  }
  StringCbCopyW(v8, v7, pszSrc);
  StringCbCatW(v9, v7, L"\\*");
  *a3 = 0;
  FirstFileW = FindFirstFileW(v9, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v15 = GetLastError();
      WPP_SF_d(v14, 25, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, v15);
    }
    LocalFree(v9);
    return 0;
  }
  do
    *a3 += __PAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow);
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  if ( GetLastError() == 18 )
  {
    v18 = 1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v17 = GetLastError();
      WPP_SF_d(v16, 26, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, v17);
    }
    v18 = 0;
  }
  LocalFree(v9);
  FindClose(FirstFileW);
  return v18;
}

```

## disassembly

```asm
0x18002b1e0  mov     [rsp+arg_18], rbx
0x18002b1e5  push    rsi
0x18002b1e6  push    rdi
0x18002b1e7  push    r14
0x18002b1e9  sub     rsp, 290h
0x18002b1f0  mov     rax, cs:__security_cookie
0x18002b1f7  xor     rax, rsp
0x18002b1fa  mov     [rsp+2A8h+var_28], rax
0x18002b202  mov     r14, r8
0x18002b205  mov     ebx, edx
0x18002b207  mov     rsi, rcx
0x18002b20a  xor     edx, edx; Val
0x18002b20c  mov     r8d, 250h; Size
0x18002b212  lea     rcx, [rsp+2A8h+FindFileData]; void *
0x18002b217  call    memset_0
0x18002b21c  lea     eax, ds:4[rbx*2]
0x18002b223  mov     ecx, 40h ; '@'; uFlags
0x18002b228  mov     edx, eax; uBytes
0x18002b22a  mov     ebx, eax
0x18002b22c  call    cs:__imp_LocalAlloc
0x18002b232  mov     rdi, rax
0x18002b235  test    rax, rax
0x18002b238  jnz     short loc_18002B27B
0x18002b23a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b241  lea     rax, WPP_GLOBAL_Control
0x18002b248  cmp     rcx, rax
0x18002b24b  jz      short loc_18002B274
0x18002b24d  lea     ebx, [rdi+1]
0x18002b250  test    [rcx+1Ch], bl
0x18002b253  jz      short loc_18002B274
0x18002b255  mov     rbx, [rcx+10h]
0x18002b259  call    cs:__imp_GetLastError
0x18002b25f  lea     edx, [rdi+18h]
0x18002b262  mov     rcx, rbx
0x18002b265  mov     r9d, eax
0x18002b268  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002b26f  call    WPP_SF_d
0x18002b274  xor     eax, eax
0x18002b276  jmp     loc_18002B391
0x18002b27b  mov     r8, rsi; pszSrc
0x18002b27e  mov     rdx, rbx; cbDest
0x18002b281  mov     rcx, rdi; pszDest
0x18002b284  call    StringCbCopyW
0x18002b289  lea     r8, asc_18003225C; "\\*"
0x18002b290  mov     rdx, rbx; cbDest
0x18002b293  mov     rcx, rdi; pszDest
0x18002b296  call    StringCbCatW
0x18002b29b  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x18002b2a0  mov     qword ptr [r14], 0
0x18002b2a7  mov     rcx, rdi; lpFileName
0x18002b2aa  call    cs:__imp_FindFirstFileW
0x18002b2b0  mov     rsi, rax
0x18002b2b3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b2b7  jnz     short loc_18002B301
0x18002b2b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b2c0  lea     rax, WPP_GLOBAL_Control
0x18002b2c7  cmp     rcx, rax
0x18002b2ca  jz      short loc_18002B2F3
0x18002b2cc  lea     ebx, [rsi+2]
0x18002b2cf  test    [rcx+1Ch], bl
0x18002b2d2  jz      short loc_18002B2F3
0x18002b2d4  mov     rbx, [rcx+10h]
0x18002b2d8  call    cs:__imp_GetLastError
0x18002b2de  lea     edx, [rsi+1Ah]
0x18002b2e1  mov     rcx, rbx
0x18002b2e4  mov     r9d, eax
0x18002b2e7  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002b2ee  call    WPP_SF_d
0x18002b2f3  mov     rcx, rdi; hMem
0x18002b2f6  call    cs:__imp_LocalFree
0x18002b2fc  jmp     loc_18002B274
0x18002b301  mov     eax, [rsp+2A8h+FindFileData.nFileSizeHigh]
0x18002b305  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x18002b30a  mov     dword ptr [rsp+2A8h+var_288+4], eax
0x18002b30e  mov     rcx, rsi; hFindFile
0x18002b311  mov     eax, [rsp+2A8h+FindFileData.nFileSizeLow]
0x18002b315  mov     dword ptr [rsp+2A8h+var_288], eax
0x18002b319  mov     rax, [rsp+2A8h+var_288]
0x18002b31e  add     [r14], rax
0x18002b321  call    cs:__imp_FindNextFileW
0x18002b327  test    eax, eax
0x18002b329  jnz     short loc_18002B301
0x18002b32b  call    cs:__imp_GetLastError
0x18002b331  cmp     eax, 12h
0x18002b334  jz      short loc_18002B378
0x18002b336  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b33d  lea     rax, WPP_GLOBAL_Control
0x18002b344  cmp     rcx, rax
0x18002b347  jz      short loc_18002B374
0x18002b349  mov     ebx, 1
0x18002b34e  test    [rcx+1Ch], bl
0x18002b351  jz      short loc_18002B374
0x18002b353  mov     rbx, [rcx+10h]
0x18002b357  call    cs:__imp_GetLastError
0x18002b35d  mov     edx, 1Ah
0x18002b362  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002b369  mov     r9d, eax
0x18002b36c  mov     rcx, rbx
0x18002b36f  call    WPP_SF_d
0x18002b374  xor     ebx, ebx
0x18002b376  jmp     short loc_18002B37D
0x18002b378  mov     ebx, 1
0x18002b37d  mov     rcx, rdi; hMem
0x18002b380  call    cs:__imp_LocalFree
0x18002b386  mov     rcx, rsi; hFindFile
0x18002b389  call    cs:__imp_FindClose
0x18002b38f  mov     eax, ebx
0x18002b391  mov     rcx, [rsp+2A8h+var_28]
0x18002b399  xor     rcx, rsp; StackCookie
0x18002b39c  call    __security_check_cookie
0x18002b3a1  mov     rbx, [rsp+2A8h+arg_18]
0x18002b3a9  add     rsp, 290h
0x18002b3b0  pop     r14
0x18002b3b2  pop     rdi
0x18002b3b3  pop     rsi
0x18002b3b4  retn
```
