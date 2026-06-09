# DeletePathEx

- ea: `0x180225714`
- end: `0x180225ac5`
- name: `DeletePathEx`
- size: `945`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation`

## callers

- `0x1800335c4`
- `0x18003a4b0`

## callees

- `0x18022220c`
- `0x1802222e4`
- `0x1802223bc`
- `0x180222764`
- `0x180223df4`
- `0x1802255bc`
- `0x180225714`
- `0x18022775c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18022587c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18022587c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802258c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802258e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180225902`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180225a15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180225a3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180225a5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802258c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802258e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180225902`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180225a15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180225a3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180225a5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802258d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802258f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180225916`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180225a29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180225a4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180225a73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802258d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802258f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180225916`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180225a29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180225a4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180225a73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180225968`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180225aa1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180225968`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180225aa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180225836`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022597c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180225836`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022597c`

## string_xrefs

- `0x180225766`: `DeletePath: [%s] doesn't exist as a directory; nothing to delete.`
- `0x18022578f`: `SeBackupPrivilege`
- `0x180225936`: `SeBackupPrivilege`
- `0x1802257b3`: `SeRestorePrivilege`
- `0x180225957`: `SeRestorePrivilege`
- `0x18022598d`: `DeletePath: Failed to get desired paths for [%s] (GLE = 0x%x)`
- `0x180225a84`: `DeletePath: Cannot delete <null>.`
- `0x18022585f`: `DeletePath: Failed to obliterate [%s] (GLE = 0x%x); retrying...`
- `0x1802258a3`: `DeletePath: Failed to obliterate [%s] after %u tries; GLE = 0x%x`
- `0x1802259b9`: `DeletePath:   Full path [%s]`
- `0x1802259d5`: `DeletePath:   Long path [%s]`
- `0x1802259f4`: `DeletePath:   Final path [%s]`
- `0x180225806`: `DeletePath: Attempting to obliterate [%s] (final path [%s]).`

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
  if ( !(unsigned int)DirectoryExists(lpFileName) )
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
    || (v9 = FormFinalPathNameEx(v8), (v4 = (wchar_t *)v9) == 0) )
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
0x180225714  mov     rax, rsp
0x180225717  mov     [rax+8], rbx
0x18022571b  mov     [rax+20h], r9
0x18022571f  mov     [rax+18h], r8
0x180225723  mov     [rax+10h], edx
0x180225726  push    rbp
0x180225727  push    rsi
0x180225728  push    rdi
0x180225729  push    r12
0x18022572b  push    r13
0x18022572d  push    r14
0x18022572f  push    r15
0x180225731  sub     rsp, 30h
0x180225735  mov     dword ptr [rax+10h], 0
0x18022573c  mov     rbx, rcx
0x18022573f  mov     dword ptr [rax+20h], 0
0x180225746  test    rcx, rcx
0x180225749  jz      loc_180225A84
0x18022574f  xor     eax, eax
0x180225751  cmp     ax, [rcx]
0x180225754  jz      loc_180225A84
0x18022575a  call    DirectoryExists
0x18022575f  test    eax, eax
0x180225761  jnz     short loc_180225788
0x180225763  mov     r9, rbx
0x180225766  lea     r8, aDeletepathSDoe; "DeletePath: [%s] doesn't exist as a dir"...
0x18022576d  mov     edx, 2000000h
0x180225772  lea     rcx, g_WdsLibLog
0x180225779  call    LibLog
0x18022577e  mov     ecx, 3
0x180225783  jmp     loc_180225AA1
0x180225788  xor     ebp, ebp
0x18022578a  lea     r8, [rsp+68h+arg_8]
0x18022578f  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x180225796  xor     esi, esi
0x180225798  lea     edi, [rbp+1]
0x18022579b  mov     edx, edi
0x18022579d  call    EnablePrivilegeEx
0x1802257a2  lea     r8, [rsp+68h+arg_18]
0x1802257aa  mov     [rsp+68h+arg_10], eax
0x1802257b1  mov     edx, edi
0x1802257b3  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x1802257ba  call    EnablePrivilegeEx
0x1802257bf  mov     rcx, rbx; lpFileName
0x1802257c2  mov     r13d, eax
0x1802257c5  call    FormFullPathName
0x1802257ca  mov     r15, rax
0x1802257cd  test    rax, rax
0x1802257d0  jz      loc_18022597C
0x1802257d6  mov     rcx, rax
0x1802257d9  call    FormLongPathName
0x1802257de  mov     rbp, rax
0x1802257e1  test    rax, rax
0x1802257e4  jz      loc_18022597C
0x1802257ea  mov     rcx, rax
0x1802257ed  call    FormFinalPathNameEx
0x1802257f2  mov     rsi, rax
0x1802257f5  test    rax, rax
0x1802257f8  jz      loc_18022597C
0x1802257fe  mov     r9, rbx
0x180225801  mov     [rsp+68h+var_48], rax
0x180225806  lea     r8, aDeletepathAtte; "DeletePath: Attempting to obliterate [%"...
0x18022580d  mov     edx, 4000000h
0x180225812  lea     rcx, g_WdsLibLog
0x180225819  xor     r14d, r14d
0x18022581c  xor     edi, edi
0x18022581e  call    LibLog
0x180225823  mov     rcx, rsi
0x180225826  call    DeletePathEngine
0x18022582b  mov     r12d, eax
0x18022582e  test    eax, eax
0x180225830  jnz     loc_1802258C2
0x180225836  call    cs:__imp_GetLastError
0x18022583d  nop     dword ptr [rax+rax+00h]
0x180225842  mov     r14d, eax
0x180225845  cmp     eax, 4C7h
0x18022584a  jz      short loc_18022589E
0x18022584c  cmp     eax, 800704C7h
0x180225851  jz      short loc_180225899
0x180225853  cmp     edi, 3
0x180225856  jnb     short loc_180225899
0x180225858  mov     r9, rsi
0x18022585b  mov     dword ptr [rsp+68h+var_48], eax
0x18022585f  lea     r8, aDeletepathFail_1; "DeletePath: Failed to obliterate [%s] ("...
0x180225866  mov     edx, 4000000h
0x18022586b  lea     rcx, g_WdsLibLog
0x180225872  call    LibLog
0x180225877  mov     ecx, 3E8h; dwMilliseconds
0x18022587c  call    cs:__imp_Sleep
0x180225883  nop     dword ptr [rax+rax+00h]
0x180225888  mov     rcx, rsi
0x18022588b  inc     edi
0x18022588d  call    DeletePathEngine
0x180225892  mov     r12d, eax
0x180225895  test    eax, eax
0x180225897  jz      short loc_180225836
0x180225899  test    r12d, r12d
0x18022589c  jnz     short loc_1802258C2
0x18022589e  mov     [rsp+68h+var_40], r14d
0x1802258a3  lea     r8, aDeletepathFail; "DeletePath: Failed to obliterate [%s] a"...
0x1802258aa  mov     r9, rbx
0x1802258ad  mov     dword ptr [rsp+68h+var_48], edi
0x1802258b1  mov     edx, 2000000h
0x1802258b6  lea     rcx, g_WdsLibLog
0x1802258bd  call    LibLog
0x1802258c2  call    cs:__imp_GetProcessHeap
0x1802258c9  nop     dword ptr [rax+rax+00h]
0x1802258ce  mov     r8, rsi; lpMem
0x1802258d1  xor     edx, edx; dwFlags
0x1802258d3  mov     rcx, rax; hHeap
0x1802258d6  call    cs:__imp_HeapFree
0x1802258dd  nop     dword ptr [rax+rax+00h]
0x1802258e2  call    cs:__imp_GetProcessHeap
0x1802258e9  nop     dword ptr [rax+rax+00h]
0x1802258ee  mov     r8, rbp; lpMem
0x1802258f1  xor     edx, edx; dwFlags
0x1802258f3  mov     rcx, rax; hHeap
0x1802258f6  call    cs:__imp_HeapFree
0x1802258fd  nop     dword ptr [rax+rax+00h]
0x180225902  call    cs:__imp_GetProcessHeap
0x180225909  nop     dword ptr [rax+rax+00h]
0x18022590e  mov     r8, r15; lpMem
0x180225911  xor     edx, edx; dwFlags
0x180225913  mov     rcx, rax; hHeap
0x180225916  call    cs:__imp_HeapFree
0x18022591d  nop     dword ptr [rax+rax+00h]
0x180225922  cmp     [rsp+68h+arg_10], 1
0x18022592a  jnz     short loc_180225944
0x18022592c  cmp     [rsp+68h+arg_8], 0
0x180225931  jnz     short loc_180225944
0x180225933  xor     r8d, r8d
0x180225936  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x18022593d  xor     edx, edx
0x18022593f  call    EnablePrivilegeEx
0x180225944  cmp     r13d, 1
0x180225948  jnz     short loc_180225965
0x18022594a  cmp     [rsp+68h+arg_18], 0
0x180225952  jnz     short loc_180225965
0x180225954  xor     r8d, r8d
0x180225957  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x18022595e  xor     edx, edx
0x180225960  call    EnablePrivilegeEx
0x180225965  mov     ecx, r14d; dwErrCode
0x180225968  call    cs:__imp_SetLastError
0x18022596f  nop     dword ptr [rax+rax+00h]
0x180225974  mov     eax, r12d
0x180225977  jmp     loc_180225AAF
0x18022597c  call    cs:__imp_GetLastError
0x180225983  nop     dword ptr [rax+rax+00h]
0x180225988  mov     edi, 2000000h
0x18022598d  lea     r8, aDeletepathFail_0; "DeletePath: Failed to get desired paths"...
0x180225994  lea     rcx, g_WdsLibLog
0x18022599b  mov     dword ptr [rsp+68h+var_48], eax
0x18022599f  mov     edx, edi
0x1802259a1  mov     r9, rbx
0x1802259a4  mov     r14d, eax
0x1802259a7  call    LibLog
0x1802259ac  lea     rbx, aUnavailable; "<unavailable>"
0x1802259b3  test    r15, r15
0x1802259b6  mov     r9, rbx
0x1802259b9  lea     r8, aDeletepathFull; "DeletePath:   Full path [%s]"
0x1802259c0  cmovnz  r9, r15
0x1802259c4  lea     rcx, g_WdsLibLog
0x1802259cb  mov     edx, edi
0x1802259cd  call    LibLog
0x1802259d2  test    rbp, rbp
0x1802259d5  lea     r8, aDeletepathLong; "DeletePath:   Long path [%s]"
0x1802259dc  mov     r9, rbx
0x1802259df  lea     rcx, g_WdsLibLog
0x1802259e6  cmovnz  r9, rbp
0x1802259ea  mov     edx, edi
0x1802259ec  call    LibLog
0x1802259f1  test    rsi, rsi
0x1802259f4  lea     r8, aDeletepathFina; "DeletePath:   Final path [%s]"
0x1802259fb  mov     edx, edi
0x1802259fd  lea     rcx, g_WdsLibLog
0x180225a04  cmovnz  rbx, rsi
0x180225a08  mov     r9, rbx
0x180225a0b  call    LibLog
0x180225a10  test    rsi, rsi
0x180225a13  jz      short loc_180225A35
0x180225a15  call    cs:__imp_GetProcessHeap
0x180225a1c  nop     dword ptr [rax+rax+00h]
0x180225a21  mov     r8, rsi; lpMem
0x180225a24  xor     edx, edx; dwFlags
0x180225a26  mov     rcx, rax; hHeap
0x180225a29  call    cs:__imp_HeapFree
0x180225a30  nop     dword ptr [rax+rax+00h]
0x180225a35  test    rbp, rbp
0x180225a38  jz      short loc_180225A5A
0x180225a3a  call    cs:__imp_GetProcessHeap
0x180225a41  nop     dword ptr [rax+rax+00h]
0x180225a46  mov     r8, rbp; lpMem
0x180225a49  xor     edx, edx; dwFlags
0x180225a4b  mov     rcx, rax; hHeap
0x180225a4e  call    cs:__imp_HeapFree
0x180225a55  nop     dword ptr [rax+rax+00h]
0x180225a5a  test    r15, r15
0x180225a5d  jz      short loc_180225A7F
0x180225a5f  call    cs:__imp_GetProcessHeap
0x180225a66  nop     dword ptr [rax+rax+00h]
0x180225a6b  mov     r8, r15; lpMem
0x180225a6e  xor     edx, edx; dwFlags
0x180225a70  mov     rcx, rax; hHeap
0x180225a73  call    cs:__imp_HeapFree
0x180225a7a  nop     dword ptr [rax+rax+00h]
0x180225a7f  mov     ecx, r14d
0x180225a82  jmp     short loc_180225AA1
0x180225a84  lea     r8, aDeletepathCann; "DeletePath: Cannot delete <null>."
0x180225a8b  mov     edx, 2000000h
0x180225a90  lea     rcx, g_WdsLibLog
0x180225a97  call    LibLog
0x180225a9c  mov     ecx, 57h ; 'W'; dwErrCode
0x180225aa1  call    cs:__imp_SetLastError
0x180225aa8  nop     dword ptr [rax+rax+00h]
0x180225aad  xor     eax, eax
0x180225aaf  mov     rbx, [rsp+68h+arg_0]
0x180225ab4  add     rsp, 30h
0x180225ab8  pop     r15
0x180225aba  pop     r14
0x180225abc  pop     r13
0x180225abe  pop     r12
0x180225ac0  pop     rdi
0x180225ac1  pop     rsi
0x180225ac2  pop     rbp
0x180225ac3  retn
```
