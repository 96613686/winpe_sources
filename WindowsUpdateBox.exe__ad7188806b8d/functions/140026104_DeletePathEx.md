# DeletePathEx

- ea: `0x140026104`
- end: `0x14002650e`
- name: `DeletePathEx`
- size: `1034`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int, __int64, __int64)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation`

## callers

- `0x140005f7c`
- `0x140009aa8`
- `0x14000b674`
- `0x140013894`
- `0x140057a08`

## callees

- `0x1400221fc`
- `0x1400222e8`
- `0x140022594`
- `0x140022960`
- `0x140024510`
- `0x140025f90`
- `0x140026104`
- `0x140028980`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140026321`
- `KERNEL32!HeapFree` at `0x140026341`
- `KERNEL32!HeapFree` at `0x140026361`
- `KERNEL32!HeapFree` at `0x14002646f`
- `KERNEL32!HeapFree` at `0x140026494`
- `KERNEL32!HeapFree` at `0x1400264b9`
- `KERNEL32!HeapFree` at `0x140026321`
- `KERNEL32!HeapFree` at `0x140026341`
- `KERNEL32!HeapFree` at `0x140026361`
- `KERNEL32!HeapFree` at `0x14002646f`
- `KERNEL32!HeapFree` at `0x140026494`
- `KERNEL32!HeapFree` at `0x1400264b9`
- `KERNEL32!GetProcessHeap` at `0x14002630d`
- `KERNEL32!GetProcessHeap` at `0x14002632d`
- `KERNEL32!GetProcessHeap` at `0x14002634d`
- `KERNEL32!GetProcessHeap` at `0x14002645b`
- `KERNEL32!GetProcessHeap` at `0x140026480`
- `KERNEL32!GetProcessHeap` at `0x1400264a5`
- `KERNEL32!GetProcessHeap` at `0x14002630d`
- `KERNEL32!GetProcessHeap` at `0x14002632d`
- `KERNEL32!GetProcessHeap` at `0x14002634d`
- `KERNEL32!GetProcessHeap` at `0x14002645b`
- `KERNEL32!GetProcessHeap` at `0x140026480`
- `KERNEL32!GetProcessHeap` at `0x1400264a5`
- `KERNEL32!GetLastError` at `0x14002624b`
- `KERNEL32!GetLastError` at `0x1400263c2`
- `KERNEL32!GetLastError` at `0x14002624b`
- `KERNEL32!GetLastError` at `0x1400263c2`
- `KERNEL32!Sleep` at `0x140026297`
- `KERNEL32!Sleep` at `0x140026297`
- `KERNEL32!SetLastError` at `0x1400263ae`
- `KERNEL32!SetLastError` at `0x1400264e7`
- `KERNEL32!SetLastError` at `0x1400263ae`
- `KERNEL32!SetLastError` at `0x1400264e7`

## string_xrefs

- `0x1400264ca`: `DeletePath: Cannot delete <null>.`
- `0x14002616c`: `DeletePath: [%s] doesn't exist as a directory; nothing to delete.`
- `0x14002619b`: `SeBackupPrivilege`
- `0x14002637e`: `SeBackupPrivilege`
- `0x1400261b3`: `SeRestorePrivilege`
- `0x14002639d`: `SeRestorePrivilege`
- `0x1400263d3`: `DeletePath: Failed to get desired paths for [%s] (GLE = 0x%x)`
- `0x1400263ff`: `DeletePath:   Full path [%s]`
- `0x14002641b`: `DeletePath:   Long path [%s]`
- `0x14002643a`: `DeletePath:   Final path [%s]`
- `0x14002620e`: `DeletePath: Attempting to obliterate [%s] (final path [%s]).`
- `0x140026278`: `DeletePath: Failed to obliterate [%s] (GLE = 0x%x); retrying...`
- `0x1400262ee`: `DeletePath: Failed to obliterate [%s] after %u tries; GLE = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeletePathEx(LPCWSTR lpFileName, int a2, __int64 a3, __int64 a4)
{
  wchar_t *v7; // rsi
  wchar_t *v8; // rbp
  DWORD v9; // r14d
  unsigned int v10; // edi
  DWORD v11; // ecx
  __int64 v12; // rax
  wchar_t *v13; // r15
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int v16; // r13d
  unsigned int v17; // r12d
  DWORD v18; // eax
  int v19; // eax
  HANDLE v20; // rax
  HANDLE v21; // rax
  HANDLE v22; // rax
  DWORD LastError; // r14d
  const wchar_t *v25; // rbx
  const wchar_t *v26; // r9
  const wchar_t *v27; // r9
  HANDLE ProcessHeap; // rax
  HANDLE v29; // rax
  HANDLE v30; // rax
  __int64 v31; // [rsp+20h] [rbp-58h]
  int v32; // [rsp+38h] [rbp-40h]
  int v33; // [rsp+3Ch] [rbp-3Ch]
  DWORD dwMilliseconds; // [rsp+80h] [rbp+8h]

  dwMilliseconds = 1000;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( !lpFileName || !*lpFileName )
  {
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath: Cannot delete <null>.");
    v11 = 87;
    goto LABEL_36;
  }
  if ( !(unsigned int)DirectoryExists(lpFileName) )
  {
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath: [%s] doesn't exist as a directory; nothing to delete.", lpFileName);
    v11 = 3;
LABEL_36:
    SetLastError(v11);
    return 0;
  }
  v32 = EnablePrivilegeEx(L"SeBackupPrivilege");
  v33 = EnablePrivilegeEx(L"SeRestorePrivilege");
  v12 = FormFullPathName(lpFileName, 0);
  v13 = (wchar_t *)v12;
  if ( !v12
    || (v14 = FormLongPathName(v12), (v7 = (wchar_t *)v14) == 0)
    || (v15 = FormFinalPathNameEx(v14, 1), (v8 = (wchar_t *)v15) == 0) )
  {
    LastError = GetLastError();
    LibLog(
      &g_WdsLibLog,
      0x2000000,
      L"DeletePath: Failed to get desired paths for [%s] (GLE = 0x%x)",
      lpFileName,
      LastError);
    v25 = L"<unavailable>";
    v26 = L"<unavailable>";
    if ( v13 )
      v26 = v13;
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath:   Full path [%s]", v26);
    v27 = L"<unavailable>";
    if ( v7 )
      v27 = v7;
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath:   Long path [%s]", v27);
    if ( v8 )
      v25 = v8;
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath:   Final path [%s]", v25);
    if ( v8 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v8);
    }
    if ( v7 )
    {
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v7);
    }
    if ( v13 )
    {
      v30 = GetProcessHeap();
      HeapFree(v30, 0, v13);
    }
    v11 = LastError;
    goto LABEL_36;
  }
  LibLog(&g_WdsLibLog, 0x4000000, L"DeletePath: Attempting to obliterate [%s] (final path [%s]).", lpFileName, v15);
  v16 = a2 | 0x20;
  v17 = DeletePathEngine(v8, v16, a3, a4);
  if ( !v17 )
  {
    while ( 1 )
    {
      v18 = GetLastError();
      v9 = v18;
      if ( v18 == 1223 )
        break;
      if ( v18 != -2147023673 && v10 < 3 )
      {
        LODWORD(v31) = v18;
        LibLog(&g_WdsLibLog, 0x4000000, L"DeletePath: Failed to obliterate [%s] (GLE = 0x%x); retrying...", v8, v31);
        Sleep(dwMilliseconds);
        ++v10;
        v17 = DeletePathEngine(v8, v16, a3, a4);
        v19 = 2 * dwMilliseconds;
        if ( (v16 & 2) == 0 )
          v19 = dwMilliseconds;
        dwMilliseconds = v19;
        if ( !v17 )
          continue;
      }
      if ( v17 )
        goto LABEL_17;
      break;
    }
    LODWORD(v31) = v10;
    LibLog(
      &g_WdsLibLog,
      0x2000000,
      L"DeletePath: Failed to obliterate [%s] after %u tries; GLE = 0x%x",
      lpFileName,
      v31,
      v9);
  }
LABEL_17:
  v20 = GetProcessHeap();
  HeapFree(v20, 0, v8);
  v21 = GetProcessHeap();
  HeapFree(v21, 0, v7);
  v22 = GetProcessHeap();
  HeapFree(v22, 0, v13);
  if ( v32 == 1 )
    EnablePrivilegeEx(L"SeBackupPrivilege");
  if ( v33 == 1 )
    EnablePrivilegeEx(L"SeRestorePrivilege");
  SetLastError(v9);
  return v17;
}

```

## disassembly

```asm
0x140026104  mov     rax, rsp
0x140026107  mov     [rax+10h], rbx
0x14002610b  mov     [rax+20h], r9
0x14002610f  mov     [rax+18h], r8
0x140026113  push    rbp
0x140026114  push    rsi
0x140026115  push    rdi
0x140026116  push    r12
0x140026118  push    r13
0x14002611a  push    r14
0x14002611c  push    r15
0x14002611e  sub     rsp, 40h
0x140026122  xor     r15d, r15d
0x140026125  mov     [rsp+78h+dwMilliseconds], 3E8h
0x140026130  mov     [rax-48h], r15d
0x140026134  mov     r12, r9
0x140026137  mov     [rax-44h], r15d
0x14002613b  mov     r13d, edx
0x14002613e  mov     rbx, rcx
0x140026141  mov     esi, r15d
0x140026144  mov     ebp, r15d
0x140026147  mov     r14d, r15d
0x14002614a  mov     edi, r15d
0x14002614d  test    rcx, rcx
0x140026150  jz      loc_1400264CA
0x140026156  cmp     r15w, [rcx]
0x14002615a  jz      loc_1400264CA
0x140026160  call    DirectoryExists
0x140026165  test    eax, eax
0x140026167  jnz     short loc_14002618D
0x140026169  mov     r9, rbx
0x14002616c  lea     r8, aDeletepathSDoe; "DeletePath: [%s] doesn't exist as a dir"...
0x140026173  mov     edx, 2000000h
0x140026178  lea     rcx, g_WdsLibLog
0x14002617f  call    LibLog
0x140026184  lea     ecx, [r15+3]
0x140026188  jmp     loc_1400264E7
0x14002618d  mov     r15d, 1
0x140026193  lea     r8, [rsp+78h+var_48]
0x140026198  mov     edx, r15d
0x14002619b  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x1400261a2  call    EnablePrivilegeEx
0x1400261a7  lea     r8, [rsp+78h+var_44]
0x1400261ac  mov     [rsp+78h+var_40], eax
0x1400261b0  mov     edx, r15d
0x1400261b3  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x1400261ba  call    EnablePrivilegeEx
0x1400261bf  xor     edx, edx; lpFilePart
0x1400261c1  mov     [rsp+78h+var_3C], eax
0x1400261c5  mov     rcx, rbx; lpFileName
0x1400261c8  call    FormFullPathName
0x1400261cd  mov     r15, rax
0x1400261d0  test    rax, rax
0x1400261d3  jz      loc_1400263C2
0x1400261d9  mov     rcx, rax
0x1400261dc  call    FormLongPathName
0x1400261e1  mov     rsi, rax
0x1400261e4  test    rax, rax
0x1400261e7  jz      loc_1400263C2
0x1400261ed  mov     edx, 1
0x1400261f2  mov     rcx, rax
0x1400261f5  call    FormFinalPathNameEx
0x1400261fa  mov     rbp, rax
0x1400261fd  test    rax, rax
0x140026200  jz      loc_1400263C2
0x140026206  mov     r9, rbx
0x140026209  mov     [rsp+78h+var_58], rax
0x14002620e  lea     r8, aDeletepathAtte; "DeletePath: Attempting to obliterate [%"...
0x140026215  mov     edx, 4000000h
0x14002621a  lea     rcx, g_WdsLibLog
0x140026221  call    LibLog
0x140026226  mov     r8, [rsp+78h+arg_10]
0x14002622e  or      r13d, 20h
0x140026232  mov     edx, r13d
0x140026235  mov     r9, r12
0x140026238  mov     rcx, rbp
0x14002623b  call    DeletePathEngine
0x140026240  mov     r12d, eax
0x140026243  test    eax, eax
0x140026245  jnz     loc_14002630D
0x14002624b  call    cs:__imp_GetLastError
0x140026252  nop     dword ptr [rax+rax+00h]
0x140026257  mov     r14d, eax
0x14002625a  cmp     eax, 4C7h
0x14002625f  jz      loc_1400262E9
0x140026265  cmp     eax, 800704C7h
0x14002626a  jz      short loc_1400262E4
0x14002626c  cmp     edi, 3
0x14002626f  jnb     short loc_1400262E4
0x140026271  mov     r9, rbp
0x140026274  mov     dword ptr [rsp+78h+var_58], eax
0x140026278  lea     r8, aDeletepathFail_1; "DeletePath: Failed to obliterate [%s] ("...
0x14002627f  mov     edx, 4000000h
0x140026284  lea     rcx, g_WdsLibLog
0x14002628b  call    LibLog
0x140026290  mov     ecx, [rsp+78h+dwMilliseconds]; dwMilliseconds
0x140026297  call    cs:__imp_Sleep
0x14002629e  nop     dword ptr [rax+rax+00h]
0x1400262a3  mov     r9, [rsp+78h+arg_18]
0x1400262ab  mov     edx, r13d
0x1400262ae  mov     r8, [rsp+78h+arg_10]
0x1400262b6  mov     rcx, rbp
0x1400262b9  inc     edi
0x1400262bb  call    DeletePathEngine
0x1400262c0  mov     ecx, [rsp+78h+dwMilliseconds]
0x1400262c7  mov     r12d, eax
0x1400262ca  test    r13b, 2
0x1400262ce  lea     eax, [rcx+rcx]
0x1400262d1  cmovz   eax, ecx
0x1400262d4  mov     [rsp+78h+dwMilliseconds], eax
0x1400262db  test    r12d, r12d
0x1400262de  jz      loc_14002624B
0x1400262e4  test    r12d, r12d
0x1400262e7  jnz     short loc_14002630D
0x1400262e9  mov     [rsp+78h+var_50], r14d
0x1400262ee  lea     r8, aDeletepathFail; "DeletePath: Failed to obliterate [%s] a"...
0x1400262f5  mov     r9, rbx
0x1400262f8  mov     dword ptr [rsp+78h+var_58], edi
0x1400262fc  mov     edx, 2000000h
0x140026301  lea     rcx, g_WdsLibLog
0x140026308  call    LibLog
0x14002630d  call    cs:__imp_GetProcessHeap
0x140026314  nop     dword ptr [rax+rax+00h]
0x140026319  mov     r8, rbp; lpMem
0x14002631c  xor     edx, edx; dwFlags
0x14002631e  mov     rcx, rax; hHeap
0x140026321  call    cs:__imp_HeapFree
0x140026328  nop     dword ptr [rax+rax+00h]
0x14002632d  call    cs:__imp_GetProcessHeap
0x140026334  nop     dword ptr [rax+rax+00h]
0x140026339  mov     r8, rsi; lpMem
0x14002633c  xor     edx, edx; dwFlags
0x14002633e  mov     rcx, rax; hHeap
0x140026341  call    cs:__imp_HeapFree
0x140026348  nop     dword ptr [rax+rax+00h]
0x14002634d  call    cs:__imp_GetProcessHeap
0x140026354  nop     dword ptr [rax+rax+00h]
0x140026359  mov     r8, r15; lpMem
0x14002635c  xor     edx, edx; dwFlags
0x14002635e  mov     rcx, rax; hHeap
0x140026361  call    cs:__imp_HeapFree
0x140026368  nop     dword ptr [rax+rax+00h]
0x14002636d  cmp     [rsp+78h+var_40], 1
0x140026372  jnz     short loc_14002638C
0x140026374  cmp     [rsp+78h+var_48], 0
0x140026379  jnz     short loc_14002638C
0x14002637b  xor     r8d, r8d
0x14002637e  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x140026385  xor     edx, edx
0x140026387  call    EnablePrivilegeEx
0x14002638c  cmp     [rsp+78h+var_3C], 1
0x140026391  jnz     short loc_1400263AB
0x140026393  cmp     [rsp+78h+var_44], 0
0x140026398  jnz     short loc_1400263AB
0x14002639a  xor     r8d, r8d
0x14002639d  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x1400263a4  xor     edx, edx
0x1400263a6  call    EnablePrivilegeEx
0x1400263ab  mov     ecx, r14d; dwErrCode
0x1400263ae  call    cs:__imp_SetLastError
0x1400263b5  nop     dword ptr [rax+rax+00h]
0x1400263ba  mov     eax, r12d
0x1400263bd  jmp     loc_1400264F5
0x1400263c2  call    cs:__imp_GetLastError
0x1400263c9  nop     dword ptr [rax+rax+00h]
0x1400263ce  mov     edi, 2000000h
0x1400263d3  lea     r8, aDeletepathFail_0; "DeletePath: Failed to get desired paths"...
0x1400263da  lea     rcx, g_WdsLibLog
0x1400263e1  mov     dword ptr [rsp+78h+var_58], eax
0x1400263e5  mov     edx, edi
0x1400263e7  mov     r9, rbx
0x1400263ea  mov     r14d, eax
0x1400263ed  call    LibLog
0x1400263f2  lea     rbx, aUnavailable; "<unavailable>"
0x1400263f9  test    r15, r15
0x1400263fc  mov     r9, rbx
0x1400263ff  lea     r8, aDeletepathFull; "DeletePath:   Full path [%s]"
0x140026406  cmovnz  r9, r15
0x14002640a  lea     rcx, g_WdsLibLog
0x140026411  mov     edx, edi
0x140026413  call    LibLog
0x140026418  test    rsi, rsi
0x14002641b  lea     r8, aDeletepathLong; "DeletePath:   Long path [%s]"
0x140026422  mov     r9, rbx
0x140026425  lea     rcx, g_WdsLibLog
0x14002642c  cmovnz  r9, rsi
0x140026430  mov     edx, edi
0x140026432  call    LibLog
0x140026437  test    rbp, rbp
0x14002643a  lea     r8, aDeletepathFina; "DeletePath:   Final path [%s]"
0x140026441  mov     edx, edi
0x140026443  lea     rcx, g_WdsLibLog
0x14002644a  cmovnz  rbx, rbp
0x14002644e  mov     r9, rbx
0x140026451  call    LibLog
0x140026456  test    rbp, rbp
0x140026459  jz      short loc_14002647B
0x14002645b  call    cs:__imp_GetProcessHeap
0x140026462  nop     dword ptr [rax+rax+00h]
0x140026467  mov     r8, rbp; lpMem
0x14002646a  xor     edx, edx; dwFlags
0x14002646c  mov     rcx, rax; hHeap
0x14002646f  call    cs:__imp_HeapFree
0x140026476  nop     dword ptr [rax+rax+00h]
0x14002647b  test    rsi, rsi
0x14002647e  jz      short loc_1400264A0
0x140026480  call    cs:__imp_GetProcessHeap
0x140026487  nop     dword ptr [rax+rax+00h]
0x14002648c  mov     r8, rsi; lpMem
0x14002648f  xor     edx, edx; dwFlags
0x140026491  mov     rcx, rax; hHeap
0x140026494  call    cs:__imp_HeapFree
0x14002649b  nop     dword ptr [rax+rax+00h]
0x1400264a0  test    r15, r15
0x1400264a3  jz      short loc_1400264C5
0x1400264a5  call    cs:__imp_GetProcessHeap
0x1400264ac  nop     dword ptr [rax+rax+00h]
0x1400264b1  mov     r8, r15; lpMem
0x1400264b4  xor     edx, edx; dwFlags
0x1400264b6  mov     rcx, rax; hHeap
0x1400264b9  call    cs:__imp_HeapFree
0x1400264c0  nop     dword ptr [rax+rax+00h]
0x1400264c5  mov     ecx, r14d
0x1400264c8  jmp     short loc_1400264E7
0x1400264ca  lea     r8, aDeletepathCann; "DeletePath: Cannot delete <null>."
0x1400264d1  mov     edx, 2000000h
0x1400264d6  lea     rcx, g_WdsLibLog
0x1400264dd  call    LibLog
0x1400264e2  mov     ecx, 57h ; 'W'; dwErrCode
0x1400264e7  call    cs:__imp_SetLastError
0x1400264ee  nop     dword ptr [rax+rax+00h]
0x1400264f3  xor     eax, eax
0x1400264f5  mov     rbx, [rsp+78h+arg_8]
0x1400264fd  add     rsp, 40h
0x140026501  pop     r15
0x140026503  pop     r14
0x140026505  pop     r13
0x140026507  pop     r12
0x140026509  pop     rdi
0x14002650a  pop     rsi
0x14002650b  pop     rbp
0x14002650c  retn
```
