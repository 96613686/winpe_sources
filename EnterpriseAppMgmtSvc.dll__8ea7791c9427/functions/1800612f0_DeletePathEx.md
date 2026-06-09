# DeletePathEx

- ea: `0x1800612f0`
- end: `0x18006163a`
- name: `DeletePathEx`
- size: `842`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation`

## callers

- `0x18003b3f8`
- `0x1800450bc`

## callees

- `0x18005ed60`
- `0x18005eea8`
- `0x18005f94c`
- `0x18005f9f8`
- `0x18005fa9c`
- `0x1800611b8`
- `0x1800612f0`
- `0x180062864`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061492`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800614a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800614ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800615b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800615ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800615e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061492`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800614a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800614ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800615b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800615ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800615e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800614a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800614b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800614c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800615c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800615dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800615f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800614a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800614b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800614c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800615c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800615dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800615f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061412`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061522`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061412`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061522`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061514`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006161d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061514`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006161d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180061452`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180061452`

## string_xrefs

- `0x18006136b`: `SeBackupPrivilege`
- `0x1800614e2`: `SeBackupPrivilege`
- `0x18006138f`: `SeRestorePrivilege`
- `0x180061503`: `SeRestorePrivilege`
- `0x180061600`: `DeletePath: Cannot delete <null>.`
- `0x180061575`: `DeletePath:   Long path [%s]`
- `0x180061559`: `DeletePath:   Full path [%s]`
- `0x18006152d`: `DeletePath: Failed to get desired paths for [%s] (GLE = 0x%x)`
- `0x180061342`: `DeletePath: [%s] doesn't exist as a directory; nothing to delete.`
- `0x180061473`: `DeletePath: Failed to obliterate [%s] after %u tries; GLE = 0x%x`
- `0x180061435`: `DeletePath: Failed to obliterate [%s] (GLE = 0x%x); retrying...`
- `0x1800613e2`: `DeletePath: Attempting to obliterate [%s] (final path [%s]).`
- `0x180061594`: `DeletePath:   Final path [%s]`

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
0x1800612f0  mov     rax, rsp
0x1800612f3  mov     [rax+8], rbx
0x1800612f7  mov     [rax+20h], r9
0x1800612fb  mov     [rax+18h], r8
0x1800612ff  mov     [rax+10h], edx
0x180061302  push    rbp
0x180061303  push    rsi
0x180061304  push    rdi
0x180061305  push    r12
0x180061307  push    r13
0x180061309  push    r14
0x18006130b  push    r15
0x18006130d  sub     rsp, 30h
0x180061311  mov     dword ptr [rax+10h], 0
0x180061318  mov     rbx, rcx
0x18006131b  mov     dword ptr [rax+20h], 0
0x180061322  test    rcx, rcx
0x180061325  jz      loc_180061600
0x18006132b  xor     eax, eax
0x18006132d  cmp     ax, [rcx]
0x180061330  jz      loc_180061600
0x180061336  call    DirectoryExists
0x18006133b  test    eax, eax
0x18006133d  jnz     short loc_180061364
0x18006133f  mov     r9, rbx
0x180061342  lea     r8, aDeletepathSDoe; "DeletePath: [%s] doesn't exist as a dir"...
0x180061349  mov     edx, 2000000h
0x18006134e  lea     rcx, g_WdsLibLog
0x180061355  call    LibLog
0x18006135a  mov     ecx, 3
0x18006135f  jmp     loc_18006161D
0x180061364  xor     ebp, ebp
0x180061366  lea     r8, [rsp+68h+arg_8]
0x18006136b  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x180061372  xor     esi, esi
0x180061374  lea     edi, [rbp+1]
0x180061377  mov     edx, edi
0x180061379  call    EnablePrivilegeEx
0x18006137e  lea     r8, [rsp+68h+arg_18]
0x180061386  mov     [rsp+68h+arg_10], eax
0x18006138d  mov     edx, edi
0x18006138f  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x180061396  call    EnablePrivilegeEx
0x18006139b  mov     rcx, rbx; lpFileName
0x18006139e  mov     r13d, eax
0x1800613a1  call    FormFullPathName
0x1800613a6  mov     r15, rax
0x1800613a9  test    rax, rax
0x1800613ac  jz      loc_180061522
0x1800613b2  mov     rcx, rax
0x1800613b5  call    FormLongPathName
0x1800613ba  mov     rbp, rax
0x1800613bd  test    rax, rax
0x1800613c0  jz      loc_180061522
0x1800613c6  mov     rcx, rax
0x1800613c9  call    FormFinalPathNameEx
0x1800613ce  mov     rsi, rax
0x1800613d1  test    rax, rax
0x1800613d4  jz      loc_180061522
0x1800613da  mov     r9, rbx
0x1800613dd  mov     [rsp+68h+var_48], rax
0x1800613e2  lea     r8, aDeletepathAtte; "DeletePath: Attempting to obliterate [%"...
0x1800613e9  mov     edx, 4000000h
0x1800613ee  lea     rcx, g_WdsLibLog
0x1800613f5  xor     r14d, r14d
0x1800613f8  xor     edi, edi
0x1800613fa  call    LibLog
0x1800613ff  mov     rcx, rsi
0x180061402  call    DeletePathEngine
0x180061407  mov     r12d, eax
0x18006140a  test    eax, eax
0x18006140c  jnz     loc_180061492
0x180061412  call    cs:__imp_GetLastError
0x180061418  mov     r14d, eax
0x18006141b  cmp     eax, 4C7h
0x180061420  jz      short loc_18006146E
0x180061422  cmp     eax, 800704C7h
0x180061427  jz      short loc_180061469
0x180061429  cmp     edi, 3
0x18006142c  jnb     short loc_180061469
0x18006142e  mov     r9, rsi
0x180061431  mov     dword ptr [rsp+68h+var_48], eax
0x180061435  lea     r8, aDeletepathFail_1; "DeletePath: Failed to obliterate [%s] ("...
0x18006143c  mov     edx, 4000000h
0x180061441  lea     rcx, g_WdsLibLog
0x180061448  call    LibLog
0x18006144d  mov     ecx, 3E8h; dwMilliseconds
0x180061452  call    cs:__imp_Sleep
0x180061458  mov     rcx, rsi
0x18006145b  inc     edi
0x18006145d  call    DeletePathEngine
0x180061462  mov     r12d, eax
0x180061465  test    eax, eax
0x180061467  jz      short loc_180061412
0x180061469  test    r12d, r12d
0x18006146c  jnz     short loc_180061492
0x18006146e  mov     [rsp+68h+var_40], r14d
0x180061473  lea     r8, aDeletepathFail; "DeletePath: Failed to obliterate [%s] a"...
0x18006147a  mov     r9, rbx
0x18006147d  mov     dword ptr [rsp+68h+var_48], edi
0x180061481  mov     edx, 2000000h
0x180061486  lea     rcx, g_WdsLibLog
0x18006148d  call    LibLog
0x180061492  call    cs:__imp_GetProcessHeap
0x180061498  mov     r8, rsi; lpMem
0x18006149b  xor     edx, edx; dwFlags
0x18006149d  mov     rcx, rax; hHeap
0x1800614a0  call    cs:__imp_HeapFree
0x1800614a6  call    cs:__imp_GetProcessHeap
0x1800614ac  mov     r8, rbp; lpMem
0x1800614af  xor     edx, edx; dwFlags
0x1800614b1  mov     rcx, rax; hHeap
0x1800614b4  call    cs:__imp_HeapFree
0x1800614ba  call    cs:__imp_GetProcessHeap
0x1800614c0  mov     r8, r15; lpMem
0x1800614c3  xor     edx, edx; dwFlags
0x1800614c5  mov     rcx, rax; hHeap
0x1800614c8  call    cs:__imp_HeapFree
0x1800614ce  cmp     [rsp+68h+arg_10], 1
0x1800614d6  jnz     short loc_1800614F0
0x1800614d8  cmp     [rsp+68h+arg_8], 0
0x1800614dd  jnz     short loc_1800614F0
0x1800614df  xor     r8d, r8d
0x1800614e2  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x1800614e9  xor     edx, edx
0x1800614eb  call    EnablePrivilegeEx
0x1800614f0  cmp     r13d, 1
0x1800614f4  jnz     short loc_180061511
0x1800614f6  cmp     [rsp+68h+arg_18], 0
0x1800614fe  jnz     short loc_180061511
0x180061500  xor     r8d, r8d
0x180061503  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x18006150a  xor     edx, edx
0x18006150c  call    EnablePrivilegeEx
0x180061511  mov     ecx, r14d; dwErrCode
0x180061514  call    cs:__imp_SetLastError
0x18006151a  mov     eax, r12d
0x18006151d  jmp     loc_180061625
0x180061522  call    cs:__imp_GetLastError
0x180061528  mov     edi, 2000000h
0x18006152d  lea     r8, aDeletepathFail_0; "DeletePath: Failed to get desired paths"...
0x180061534  lea     rcx, g_WdsLibLog
0x18006153b  mov     dword ptr [rsp+68h+var_48], eax
0x18006153f  mov     edx, edi
0x180061541  mov     r9, rbx
0x180061544  mov     r14d, eax
0x180061547  call    LibLog
0x18006154c  lea     rbx, aUnavailable; "<unavailable>"
0x180061553  test    r15, r15
0x180061556  mov     r9, rbx
0x180061559  lea     r8, aDeletepathFull; "DeletePath:   Full path [%s]"
0x180061560  cmovnz  r9, r15
0x180061564  lea     rcx, g_WdsLibLog
0x18006156b  mov     edx, edi
0x18006156d  call    LibLog
0x180061572  test    rbp, rbp
0x180061575  lea     r8, aDeletepathLong; "DeletePath:   Long path [%s]"
0x18006157c  mov     r9, rbx
0x18006157f  lea     rcx, g_WdsLibLog
0x180061586  cmovnz  r9, rbp
0x18006158a  mov     edx, edi
0x18006158c  call    LibLog
0x180061591  test    rsi, rsi
0x180061594  lea     r8, aDeletepathFina; "DeletePath:   Final path [%s]"
0x18006159b  mov     edx, edi
0x18006159d  lea     rcx, g_WdsLibLog
0x1800615a4  cmovnz  rbx, rsi
0x1800615a8  mov     r9, rbx
0x1800615ab  call    LibLog
0x1800615b0  test    rsi, rsi
0x1800615b3  jz      short loc_1800615C9
0x1800615b5  call    cs:__imp_GetProcessHeap
0x1800615bb  mov     r8, rsi; lpMem
0x1800615be  xor     edx, edx; dwFlags
0x1800615c0  mov     rcx, rax; hHeap
0x1800615c3  call    cs:__imp_HeapFree
0x1800615c9  test    rbp, rbp
0x1800615cc  jz      short loc_1800615E2
0x1800615ce  call    cs:__imp_GetProcessHeap
0x1800615d4  mov     r8, rbp; lpMem
0x1800615d7  xor     edx, edx; dwFlags
0x1800615d9  mov     rcx, rax; hHeap
0x1800615dc  call    cs:__imp_HeapFree
0x1800615e2  test    r15, r15
0x1800615e5  jz      short loc_1800615FB
0x1800615e7  call    cs:__imp_GetProcessHeap
0x1800615ed  mov     r8, r15; lpMem
0x1800615f0  xor     edx, edx; dwFlags
0x1800615f2  mov     rcx, rax; hHeap
0x1800615f5  call    cs:__imp_HeapFree
0x1800615fb  mov     ecx, r14d
0x1800615fe  jmp     short loc_18006161D
0x180061600  lea     r8, aDeletepathCann; "DeletePath: Cannot delete <null>."
0x180061607  mov     edx, 2000000h
0x18006160c  lea     rcx, g_WdsLibLog
0x180061613  call    LibLog
0x180061618  mov     ecx, 57h ; 'W'; dwErrCode
0x18006161d  call    cs:__imp_SetLastError
0x180061623  xor     eax, eax
0x180061625  mov     rbx, [rsp+68h+arg_0]
0x18006162a  add     rsp, 30h
0x18006162e  pop     r15
0x180061630  pop     r14
0x180061632  pop     r13
0x180061634  pop     r12
0x180061636  pop     rdi
0x180061637  pop     rsi
0x180061638  pop     rbp
0x180061639  retn
```
