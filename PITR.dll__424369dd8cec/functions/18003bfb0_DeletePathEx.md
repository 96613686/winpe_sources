# DeletePathEx

- ea: `0x18003bfb0`
- end: `0x18003c2fc`
- name: `DeletePathEx`
- size: `844`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation`

## callers

- `0x1800170f0`

## callees

- `0x18003a8d8`
- `0x18003b6ac`
- `0x18003be78`
- `0x18003bfb0`
- `0x18003cd7c`
- `0x18003ce30`
- `0x18003ced4`
- `0x18003e794`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c154`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c168`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c17c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c277`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c290`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c2a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c154`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c168`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c17c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c277`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c290`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c2a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c162`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c176`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c18a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c285`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c29e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c2b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c162`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c176`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c18a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c285`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c29e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c2b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c1d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c2df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c1d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c2df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c0d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c1e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c0d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c1e4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003c114`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003c114`

## string_xrefs

- `0x18003c02b`: `SeBackupPrivilege`
- `0x18003c1a4`: `SeBackupPrivilege`
- `0x18003c04f`: `SeRestorePrivilege`
- `0x18003c1c5`: `SeRestorePrivilege`
- `0x18003c2c2`: `DeletePath: Cannot delete <null>.`
- `0x18003c002`: `DeletePath: [%s] doesn't exist as a directory; nothing to delete.`
- `0x18003c1ef`: `DeletePath: Failed to get desired paths for [%s] (GLE = 0x%x)`
- `0x18003c21b`: `DeletePath:   Full path [%s]`
- `0x18003c237`: `DeletePath:   Long path [%s]`
- `0x18003c256`: `DeletePath:   Final path [%s]`
- `0x18003c0a4`: `DeletePath: Attempting to obliterate [%s] (final path [%s]).`
- `0x18003c0f7`: `DeletePath: Failed to obliterate [%s] (GLE = 0x%x); retrying...`
- `0x18003c135`: `DeletePath: Failed to obliterate [%s] after %u tries; GLE = 0x%x`

## pseudocode

```c
__int64 __fastcall DeletePathEx(LPCWSTR lpFileName)
{
  DWORD v2; // ecx
  wchar_t *v3; // rbp
  wchar_t *v4; // rsi
  int v5; // r13d
  __int64 v6; // rax
  wchar_t *v7; // r15
  __int64 v8; // rax
  __int64 v9; // rax
  DWORD v10; // r14d
  unsigned int v11; // edi
  unsigned int v12; // r12d
  DWORD v13; // eax
  HANDLE v14; // rax
  HANDLE v15; // rax
  HANDLE v16; // rax
  DWORD LastError; // r14d
  const wchar_t *v19; // rbx
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  HANDLE ProcessHeap; // rax
  HANDLE v23; // rax
  HANDLE v24; // rax
  __int64 v25; // [rsp+20h] [rbp-48h]
  int v26; // [rsp+80h] [rbp+18h]

  if ( !lpFileName || !*lpFileName )
  {
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath: Cannot delete <null>.");
    v2 = 87;
    goto LABEL_34;
  }
  if ( !(unsigned int)DirectoryExists() )
  {
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath: [%s] doesn't exist as a directory; nothing to delete.", lpFileName);
    v2 = 3;
LABEL_34:
    SetLastError(v2);
    return 0;
  }
  v3 = 0;
  v4 = 0;
  v26 = EnablePrivilegeEx(L"SeBackupPrivilege");
  v5 = EnablePrivilegeEx(L"SeRestorePrivilege");
  v6 = FormFullPathName(lpFileName);
  v7 = (wchar_t *)v6;
  if ( !v6
    || (v8 = FormLongPathName(v6), (v3 = (wchar_t *)v8) == 0)
    || (v9 = FormFinalPathNameEx(v8, 1), (v4 = (wchar_t *)v9) == 0) )
  {
    LastError = GetLastError();
    LibLog(
      &g_WdsLibLog,
      0x2000000,
      L"DeletePath: Failed to get desired paths for [%s] (GLE = 0x%x)",
      lpFileName,
      LastError);
    v19 = L"<unavailable>";
    v20 = L"<unavailable>";
    if ( v7 )
      v20 = v7;
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath:   Full path [%s]", v20);
    v21 = L"<unavailable>";
    if ( v3 )
      v21 = v3;
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath:   Long path [%s]", v21);
    if ( v4 )
      v19 = v4;
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath:   Final path [%s]", v19);
    if ( v4 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    if ( v3 )
    {
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v3);
    }
    if ( v7 )
    {
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v7);
    }
    v2 = LastError;
    goto LABEL_34;
  }
  v10 = 0;
  v11 = 0;
  LibLog(&g_WdsLibLog, 0x4000000, L"DeletePath: Attempting to obliterate [%s] (final path [%s]).", lpFileName, v9);
  v12 = DeletePathEngine(v4);
  if ( !v12 )
  {
    while ( 1 )
    {
      v13 = GetLastError();
      v10 = v13;
      if ( v13 == 1223 )
        break;
      if ( v13 != -2147023673 && v11 < 3 )
      {
        LODWORD(v25) = v13;
        LibLog(&g_WdsLibLog, 0x4000000, L"DeletePath: Failed to obliterate [%s] (GLE = 0x%x); retrying...", v4, v25);
        Sleep(0x3E8u);
        ++v11;
        v12 = DeletePathEngine(v4);
        if ( !v12 )
          continue;
      }
      if ( v12 )
        goto LABEL_15;
      break;
    }
    LODWORD(v25) = v11;
    LibLog(
      &g_WdsLibLog,
      0x2000000,
      L"DeletePath: Failed to obliterate [%s] after %u tries; GLE = 0x%x",
      lpFileName,
      v25,
      v10);
  }
LABEL_15:
  v14 = GetProcessHeap();
  HeapFree(v14, 0, v4);
  v15 = GetProcessHeap();
  HeapFree(v15, 0, v3);
  v16 = GetProcessHeap();
  HeapFree(v16, 0, v7);
  if ( v26 == 1 )
    EnablePrivilegeEx(L"SeBackupPrivilege");
  if ( v5 == 1 )
    EnablePrivilegeEx(L"SeRestorePrivilege");
  SetLastError(v10);
  return v12;
}

```

## disassembly

```asm
0x18003bfb0  mov     rax, rsp
0x18003bfb3  mov     [rax+8], rbx
0x18003bfb7  mov     [rax+20h], r9
0x18003bfbb  mov     [rax+18h], r8
0x18003bfbf  mov     [rax+10h], edx
0x18003bfc2  push    rbp
0x18003bfc3  push    rsi
0x18003bfc4  push    rdi
0x18003bfc5  push    r12
0x18003bfc7  push    r13
0x18003bfc9  push    r14
0x18003bfcb  push    r15
0x18003bfcd  sub     rsp, 30h
0x18003bfd1  mov     dword ptr [rax+10h], 0
0x18003bfd8  mov     rbx, rcx
0x18003bfdb  mov     dword ptr [rax+20h], 0
0x18003bfe2  test    rcx, rcx
0x18003bfe5  jz      loc_18003C2C2
0x18003bfeb  xor     eax, eax
0x18003bfed  cmp     ax, [rcx]
0x18003bff0  jz      loc_18003C2C2
0x18003bff6  call    DirectoryExists
0x18003bffb  test    eax, eax
0x18003bffd  jnz     short loc_18003C024
0x18003bfff  mov     r9, rbx
0x18003c002  lea     r8, aDeletepathSDoe; "DeletePath: [%s] doesn't exist as a dir"...
0x18003c009  mov     edx, 2000000h
0x18003c00e  lea     rcx, g_WdsLibLog
0x18003c015  call    LibLog
0x18003c01a  mov     ecx, 3
0x18003c01f  jmp     loc_18003C2DF
0x18003c024  xor     ebp, ebp
0x18003c026  lea     r8, [rsp+68h+arg_8]
0x18003c02b  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x18003c032  xor     esi, esi
0x18003c034  lea     edi, [rbp+1]
0x18003c037  mov     edx, edi
0x18003c039  call    EnablePrivilegeEx
0x18003c03e  lea     r8, [rsp+68h+arg_18]
0x18003c046  mov     [rsp+68h+arg_10], eax
0x18003c04d  mov     edx, edi
0x18003c04f  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x18003c056  call    EnablePrivilegeEx
0x18003c05b  mov     rcx, rbx; lpFileName
0x18003c05e  mov     r13d, eax
0x18003c061  call    FormFullPathName
0x18003c066  mov     r15, rax
0x18003c069  test    rax, rax
0x18003c06c  jz      loc_18003C1E4
0x18003c072  mov     rcx, rax
0x18003c075  call    FormLongPathName
0x18003c07a  mov     rbp, rax
0x18003c07d  test    rax, rax
0x18003c080  jz      loc_18003C1E4
0x18003c086  mov     edx, edi
0x18003c088  mov     rcx, rax
0x18003c08b  call    FormFinalPathNameEx
0x18003c090  mov     rsi, rax
0x18003c093  test    rax, rax
0x18003c096  jz      loc_18003C1E4
0x18003c09c  mov     r9, rbx
0x18003c09f  mov     [rsp+68h+var_48], rax
0x18003c0a4  lea     r8, aDeletepathAtte; "DeletePath: Attempting to obliterate [%"...
0x18003c0ab  mov     edx, 4000000h
0x18003c0b0  lea     rcx, g_WdsLibLog
0x18003c0b7  xor     r14d, r14d
0x18003c0ba  xor     edi, edi
0x18003c0bc  call    LibLog
0x18003c0c1  mov     rcx, rsi
0x18003c0c4  call    DeletePathEngine
0x18003c0c9  mov     r12d, eax
0x18003c0cc  test    eax, eax
0x18003c0ce  jnz     loc_18003C154
0x18003c0d4  call    cs:__imp_GetLastError
0x18003c0da  mov     r14d, eax
0x18003c0dd  cmp     eax, 4C7h
0x18003c0e2  jz      short loc_18003C130
0x18003c0e4  cmp     eax, 800704C7h
0x18003c0e9  jz      short loc_18003C12B
0x18003c0eb  cmp     edi, 3
0x18003c0ee  jnb     short loc_18003C12B
0x18003c0f0  mov     r9, rsi
0x18003c0f3  mov     dword ptr [rsp+68h+var_48], eax
0x18003c0f7  lea     r8, aDeletepathFail_1; "DeletePath: Failed to obliterate [%s] ("...
0x18003c0fe  mov     edx, 4000000h
0x18003c103  lea     rcx, g_WdsLibLog
0x18003c10a  call    LibLog
0x18003c10f  mov     ecx, 3E8h; dwMilliseconds
0x18003c114  call    cs:__imp_Sleep
0x18003c11a  mov     rcx, rsi
0x18003c11d  inc     edi
0x18003c11f  call    DeletePathEngine
0x18003c124  mov     r12d, eax
0x18003c127  test    eax, eax
0x18003c129  jz      short loc_18003C0D4
0x18003c12b  test    r12d, r12d
0x18003c12e  jnz     short loc_18003C154
0x18003c130  mov     [rsp+68h+var_40], r14d
0x18003c135  lea     r8, aDeletepathFail; "DeletePath: Failed to obliterate [%s] a"...
0x18003c13c  mov     r9, rbx
0x18003c13f  mov     dword ptr [rsp+68h+var_48], edi
0x18003c143  mov     edx, 2000000h
0x18003c148  lea     rcx, g_WdsLibLog
0x18003c14f  call    LibLog
0x18003c154  call    cs:__imp_GetProcessHeap
0x18003c15a  mov     r8, rsi; lpMem
0x18003c15d  xor     edx, edx; dwFlags
0x18003c15f  mov     rcx, rax; hHeap
0x18003c162  call    cs:__imp_HeapFree
0x18003c168  call    cs:__imp_GetProcessHeap
0x18003c16e  mov     r8, rbp; lpMem
0x18003c171  xor     edx, edx; dwFlags
0x18003c173  mov     rcx, rax; hHeap
0x18003c176  call    cs:__imp_HeapFree
0x18003c17c  call    cs:__imp_GetProcessHeap
0x18003c182  mov     r8, r15; lpMem
0x18003c185  xor     edx, edx; dwFlags
0x18003c187  mov     rcx, rax; hHeap
0x18003c18a  call    cs:__imp_HeapFree
0x18003c190  cmp     [rsp+68h+arg_10], 1
0x18003c198  jnz     short loc_18003C1B2
0x18003c19a  cmp     [rsp+68h+arg_8], 0
0x18003c19f  jnz     short loc_18003C1B2
0x18003c1a1  xor     r8d, r8d
0x18003c1a4  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x18003c1ab  xor     edx, edx
0x18003c1ad  call    EnablePrivilegeEx
0x18003c1b2  cmp     r13d, 1
0x18003c1b6  jnz     short loc_18003C1D3
0x18003c1b8  cmp     [rsp+68h+arg_18], 0
0x18003c1c0  jnz     short loc_18003C1D3
0x18003c1c2  xor     r8d, r8d
0x18003c1c5  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x18003c1cc  xor     edx, edx
0x18003c1ce  call    EnablePrivilegeEx
0x18003c1d3  mov     ecx, r14d; dwErrCode
0x18003c1d6  call    cs:__imp_SetLastError
0x18003c1dc  mov     eax, r12d
0x18003c1df  jmp     loc_18003C2E7
0x18003c1e4  call    cs:__imp_GetLastError
0x18003c1ea  mov     edi, 2000000h
0x18003c1ef  lea     r8, aDeletepathFail_0; "DeletePath: Failed to get desired paths"...
0x18003c1f6  lea     rcx, g_WdsLibLog
0x18003c1fd  mov     dword ptr [rsp+68h+var_48], eax
0x18003c201  mov     edx, edi
0x18003c203  mov     r9, rbx
0x18003c206  mov     r14d, eax
0x18003c209  call    LibLog
0x18003c20e  lea     rbx, aUnavailable; "<unavailable>"
0x18003c215  test    r15, r15
0x18003c218  mov     r9, rbx
0x18003c21b  lea     r8, aDeletepathFull; "DeletePath:   Full path [%s]"
0x18003c222  cmovnz  r9, r15
0x18003c226  lea     rcx, g_WdsLibLog
0x18003c22d  mov     edx, edi
0x18003c22f  call    LibLog
0x18003c234  test    rbp, rbp
0x18003c237  lea     r8, aDeletepathLong; "DeletePath:   Long path [%s]"
0x18003c23e  mov     r9, rbx
0x18003c241  lea     rcx, g_WdsLibLog
0x18003c248  cmovnz  r9, rbp
0x18003c24c  mov     edx, edi
0x18003c24e  call    LibLog
0x18003c253  test    rsi, rsi
0x18003c256  lea     r8, aDeletepathFina; "DeletePath:   Final path [%s]"
0x18003c25d  mov     edx, edi
0x18003c25f  lea     rcx, g_WdsLibLog
0x18003c266  cmovnz  rbx, rsi
0x18003c26a  mov     r9, rbx
0x18003c26d  call    LibLog
0x18003c272  test    rsi, rsi
0x18003c275  jz      short loc_18003C28B
0x18003c277  call    cs:__imp_GetProcessHeap
0x18003c27d  mov     r8, rsi; lpMem
0x18003c280  xor     edx, edx; dwFlags
0x18003c282  mov     rcx, rax; hHeap
0x18003c285  call    cs:__imp_HeapFree
0x18003c28b  test    rbp, rbp
0x18003c28e  jz      short loc_18003C2A4
0x18003c290  call    cs:__imp_GetProcessHeap
0x18003c296  mov     r8, rbp; lpMem
0x18003c299  xor     edx, edx; dwFlags
0x18003c29b  mov     rcx, rax; hHeap
0x18003c29e  call    cs:__imp_HeapFree
0x18003c2a4  test    r15, r15
0x18003c2a7  jz      short loc_18003C2BD
0x18003c2a9  call    cs:__imp_GetProcessHeap
0x18003c2af  mov     r8, r15; lpMem
0x18003c2b2  xor     edx, edx; dwFlags
0x18003c2b4  mov     rcx, rax; hHeap
0x18003c2b7  call    cs:__imp_HeapFree
0x18003c2bd  mov     ecx, r14d
0x18003c2c0  jmp     short loc_18003C2DF
0x18003c2c2  lea     r8, aDeletepathCann; "DeletePath: Cannot delete <null>."
0x18003c2c9  mov     edx, 2000000h
0x18003c2ce  lea     rcx, g_WdsLibLog
0x18003c2d5  call    LibLog
0x18003c2da  mov     ecx, 57h ; 'W'; dwErrCode
0x18003c2df  call    cs:__imp_SetLastError
0x18003c2e5  xor     eax, eax
0x18003c2e7  mov     rbx, [rsp+68h+arg_0]
0x18003c2ec  add     rsp, 30h
0x18003c2f0  pop     r15
0x18003c2f2  pop     r14
0x18003c2f4  pop     r13
0x18003c2f6  pop     r12
0x18003c2f8  pop     rdi
0x18003c2f9  pop     rsi
0x18003c2fa  pop     rbp
0x18003c2fb  retn
```
