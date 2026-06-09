# DeletePathEx

- ea: `0x1800666b4`
- end: `0x180066a65`
- name: `DeletePathEx`
- size: `945`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation`

## callers

- `0x18003ead0`
- `0x180048fe8`

## callees

- `0x180063c48`
- `0x180063df0`
- `0x1800649a4`
- `0x180064a7c`
- `0x180064b54`
- `0x18006655c`
- `0x1800666b4`
- `0x180067e80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066862`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066882`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800668a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800669b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800669da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800669ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066862`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066882`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800668a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800669b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800669da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800669ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066876`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066896`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800668b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800669c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800669ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066a13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066876`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066896`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800668b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800669c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800669ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066a13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800667d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006691c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800667d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006691c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066908`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066a41`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066908`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066a41`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006681c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006681c`

## string_xrefs

- `0x18006672f`: `SeBackupPrivilege`
- `0x1800668d6`: `SeBackupPrivilege`
- `0x180066753`: `SeRestorePrivilege`
- `0x1800668f7`: `SeRestorePrivilege`
- `0x18006692d`: `DeletePath: Failed to get desired paths for [%s] (GLE = 0x%x)`
- `0x180066706`: `DeletePath: [%s] doesn't exist as a directory; nothing to delete.`
- `0x180066a24`: `DeletePath: Cannot delete <null>.`
- `0x1800667a6`: `DeletePath: Attempting to obliterate [%s] (final path [%s]).`
- `0x180066994`: `DeletePath:   Final path [%s]`
- `0x180066975`: `DeletePath:   Long path [%s]`
- `0x180066959`: `DeletePath:   Full path [%s]`
- `0x180066843`: `DeletePath: Failed to obliterate [%s] after %u tries; GLE = 0x%x`
- `0x1800667ff`: `DeletePath: Failed to obliterate [%s] (GLE = 0x%x); retrying...`

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
0x1800666b4  mov     rax, rsp
0x1800666b7  mov     [rax+8], rbx
0x1800666bb  mov     [rax+20h], r9
0x1800666bf  mov     [rax+18h], r8
0x1800666c3  mov     [rax+10h], edx
0x1800666c6  push    rbp
0x1800666c7  push    rsi
0x1800666c8  push    rdi
0x1800666c9  push    r12
0x1800666cb  push    r13
0x1800666cd  push    r14
0x1800666cf  push    r15
0x1800666d1  sub     rsp, 30h
0x1800666d5  mov     dword ptr [rax+10h], 0
0x1800666dc  mov     rbx, rcx
0x1800666df  mov     dword ptr [rax+20h], 0
0x1800666e6  test    rcx, rcx
0x1800666e9  jz      loc_180066A24
0x1800666ef  xor     eax, eax
0x1800666f1  cmp     ax, [rcx]
0x1800666f4  jz      loc_180066A24
0x1800666fa  call    DirectoryExists
0x1800666ff  test    eax, eax
0x180066701  jnz     short loc_180066728
0x180066703  mov     r9, rbx
0x180066706  lea     r8, aDeletepathSDoe; "DeletePath: [%s] doesn't exist as a dir"...
0x18006670d  mov     edx, 2000000h
0x180066712  lea     rcx, g_WdsLibLog
0x180066719  call    LibLog
0x18006671e  mov     ecx, 3
0x180066723  jmp     loc_180066A41
0x180066728  xor     ebp, ebp
0x18006672a  lea     r8, [rsp+68h+arg_8]
0x18006672f  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x180066736  xor     esi, esi
0x180066738  lea     edi, [rbp+1]
0x18006673b  mov     edx, edi
0x18006673d  call    EnablePrivilegeEx
0x180066742  lea     r8, [rsp+68h+arg_18]
0x18006674a  mov     [rsp+68h+arg_10], eax
0x180066751  mov     edx, edi
0x180066753  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x18006675a  call    EnablePrivilegeEx
0x18006675f  mov     rcx, rbx; lpFileName
0x180066762  mov     r13d, eax
0x180066765  call    FormFullPathName
0x18006676a  mov     r15, rax
0x18006676d  test    rax, rax
0x180066770  jz      loc_18006691C
0x180066776  mov     rcx, rax
0x180066779  call    FormLongPathName
0x18006677e  mov     rbp, rax
0x180066781  test    rax, rax
0x180066784  jz      loc_18006691C
0x18006678a  mov     rcx, rax
0x18006678d  call    FormFinalPathNameEx
0x180066792  mov     rsi, rax
0x180066795  test    rax, rax
0x180066798  jz      loc_18006691C
0x18006679e  mov     r9, rbx
0x1800667a1  mov     [rsp+68h+var_48], rax
0x1800667a6  lea     r8, aDeletepathAtte; "DeletePath: Attempting to obliterate [%"...
0x1800667ad  mov     edx, 4000000h
0x1800667b2  lea     rcx, g_WdsLibLog
0x1800667b9  xor     r14d, r14d
0x1800667bc  xor     edi, edi
0x1800667be  call    LibLog
0x1800667c3  mov     rcx, rsi
0x1800667c6  call    DeletePathEngine
0x1800667cb  mov     r12d, eax
0x1800667ce  test    eax, eax
0x1800667d0  jnz     loc_180066862
0x1800667d6  call    cs:__imp_GetLastError
0x1800667dd  nop     dword ptr [rax+rax+00h]
0x1800667e2  mov     r14d, eax
0x1800667e5  cmp     eax, 4C7h
0x1800667ea  jz      short loc_18006683E
0x1800667ec  cmp     eax, 800704C7h
0x1800667f1  jz      short loc_180066839
0x1800667f3  cmp     edi, 3
0x1800667f6  jnb     short loc_180066839
0x1800667f8  mov     r9, rsi
0x1800667fb  mov     dword ptr [rsp+68h+var_48], eax
0x1800667ff  lea     r8, aDeletepathFail_1; "DeletePath: Failed to obliterate [%s] ("...
0x180066806  mov     edx, 4000000h
0x18006680b  lea     rcx, g_WdsLibLog
0x180066812  call    LibLog
0x180066817  mov     ecx, 3E8h; dwMilliseconds
0x18006681c  call    cs:__imp_Sleep
0x180066823  nop     dword ptr [rax+rax+00h]
0x180066828  mov     rcx, rsi
0x18006682b  inc     edi
0x18006682d  call    DeletePathEngine
0x180066832  mov     r12d, eax
0x180066835  test    eax, eax
0x180066837  jz      short loc_1800667D6
0x180066839  test    r12d, r12d
0x18006683c  jnz     short loc_180066862
0x18006683e  mov     [rsp+68h+var_40], r14d
0x180066843  lea     r8, aDeletepathFail; "DeletePath: Failed to obliterate [%s] a"...
0x18006684a  mov     r9, rbx
0x18006684d  mov     dword ptr [rsp+68h+var_48], edi
0x180066851  mov     edx, 2000000h
0x180066856  lea     rcx, g_WdsLibLog
0x18006685d  call    LibLog
0x180066862  call    cs:__imp_GetProcessHeap
0x180066869  nop     dword ptr [rax+rax+00h]
0x18006686e  mov     r8, rsi; lpMem
0x180066871  xor     edx, edx; dwFlags
0x180066873  mov     rcx, rax; hHeap
0x180066876  call    cs:__imp_HeapFree
0x18006687d  nop     dword ptr [rax+rax+00h]
0x180066882  call    cs:__imp_GetProcessHeap
0x180066889  nop     dword ptr [rax+rax+00h]
0x18006688e  mov     r8, rbp; lpMem
0x180066891  xor     edx, edx; dwFlags
0x180066893  mov     rcx, rax; hHeap
0x180066896  call    cs:__imp_HeapFree
0x18006689d  nop     dword ptr [rax+rax+00h]
0x1800668a2  call    cs:__imp_GetProcessHeap
0x1800668a9  nop     dword ptr [rax+rax+00h]
0x1800668ae  mov     r8, r15; lpMem
0x1800668b1  xor     edx, edx; dwFlags
0x1800668b3  mov     rcx, rax; hHeap
0x1800668b6  call    cs:__imp_HeapFree
0x1800668bd  nop     dword ptr [rax+rax+00h]
0x1800668c2  cmp     [rsp+68h+arg_10], 1
0x1800668ca  jnz     short loc_1800668E4
0x1800668cc  cmp     [rsp+68h+arg_8], 0
0x1800668d1  jnz     short loc_1800668E4
0x1800668d3  xor     r8d, r8d
0x1800668d6  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x1800668dd  xor     edx, edx
0x1800668df  call    EnablePrivilegeEx
0x1800668e4  cmp     r13d, 1
0x1800668e8  jnz     short loc_180066905
0x1800668ea  cmp     [rsp+68h+arg_18], 0
0x1800668f2  jnz     short loc_180066905
0x1800668f4  xor     r8d, r8d
0x1800668f7  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x1800668fe  xor     edx, edx
0x180066900  call    EnablePrivilegeEx
0x180066905  mov     ecx, r14d; dwErrCode
0x180066908  call    cs:__imp_SetLastError
0x18006690f  nop     dword ptr [rax+rax+00h]
0x180066914  mov     eax, r12d
0x180066917  jmp     loc_180066A4F
0x18006691c  call    cs:__imp_GetLastError
0x180066923  nop     dword ptr [rax+rax+00h]
0x180066928  mov     edi, 2000000h
0x18006692d  lea     r8, aDeletepathFail_0; "DeletePath: Failed to get desired paths"...
0x180066934  lea     rcx, g_WdsLibLog
0x18006693b  mov     dword ptr [rsp+68h+var_48], eax
0x18006693f  mov     edx, edi
0x180066941  mov     r9, rbx
0x180066944  mov     r14d, eax
0x180066947  call    LibLog
0x18006694c  lea     rbx, aUnavailable; "<unavailable>"
0x180066953  test    r15, r15
0x180066956  mov     r9, rbx
0x180066959  lea     r8, aDeletepathFull; "DeletePath:   Full path [%s]"
0x180066960  cmovnz  r9, r15
0x180066964  lea     rcx, g_WdsLibLog
0x18006696b  mov     edx, edi
0x18006696d  call    LibLog
0x180066972  test    rbp, rbp
0x180066975  lea     r8, aDeletepathLong; "DeletePath:   Long path [%s]"
0x18006697c  mov     r9, rbx
0x18006697f  lea     rcx, g_WdsLibLog
0x180066986  cmovnz  r9, rbp
0x18006698a  mov     edx, edi
0x18006698c  call    LibLog
0x180066991  test    rsi, rsi
0x180066994  lea     r8, aDeletepathFina; "DeletePath:   Final path [%s]"
0x18006699b  mov     edx, edi
0x18006699d  lea     rcx, g_WdsLibLog
0x1800669a4  cmovnz  rbx, rsi
0x1800669a8  mov     r9, rbx
0x1800669ab  call    LibLog
0x1800669b0  test    rsi, rsi
0x1800669b3  jz      short loc_1800669D5
0x1800669b5  call    cs:__imp_GetProcessHeap
0x1800669bc  nop     dword ptr [rax+rax+00h]
0x1800669c1  mov     r8, rsi; lpMem
0x1800669c4  xor     edx, edx; dwFlags
0x1800669c6  mov     rcx, rax; hHeap
0x1800669c9  call    cs:__imp_HeapFree
0x1800669d0  nop     dword ptr [rax+rax+00h]
0x1800669d5  test    rbp, rbp
0x1800669d8  jz      short loc_1800669FA
0x1800669da  call    cs:__imp_GetProcessHeap
0x1800669e1  nop     dword ptr [rax+rax+00h]
0x1800669e6  mov     r8, rbp; lpMem
0x1800669e9  xor     edx, edx; dwFlags
0x1800669eb  mov     rcx, rax; hHeap
0x1800669ee  call    cs:__imp_HeapFree
0x1800669f5  nop     dword ptr [rax+rax+00h]
0x1800669fa  test    r15, r15
0x1800669fd  jz      short loc_180066A1F
0x1800669ff  call    cs:__imp_GetProcessHeap
0x180066a06  nop     dword ptr [rax+rax+00h]
0x180066a0b  mov     r8, r15; lpMem
0x180066a0e  xor     edx, edx; dwFlags
0x180066a10  mov     rcx, rax; hHeap
0x180066a13  call    cs:__imp_HeapFree
0x180066a1a  nop     dword ptr [rax+rax+00h]
0x180066a1f  mov     ecx, r14d
0x180066a22  jmp     short loc_180066A41
0x180066a24  lea     r8, aDeletepathCann; "DeletePath: Cannot delete <null>."
0x180066a2b  mov     edx, 2000000h
0x180066a30  lea     rcx, g_WdsLibLog
0x180066a37  call    LibLog
0x180066a3c  mov     ecx, 57h ; 'W'; dwErrCode
0x180066a41  call    cs:__imp_SetLastError
0x180066a48  nop     dword ptr [rax+rax+00h]
0x180066a4d  xor     eax, eax
0x180066a4f  mov     rbx, [rsp+68h+arg_0]
0x180066a54  add     rsp, 30h
0x180066a58  pop     r15
0x180066a5a  pop     r14
0x180066a5c  pop     r13
0x180066a5e  pop     r12
0x180066a60  pop     rdi
0x180066a61  pop     rsi
0x180066a62  pop     rbp
0x180066a63  retn
```
