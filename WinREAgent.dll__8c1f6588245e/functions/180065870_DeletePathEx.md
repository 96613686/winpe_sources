# DeletePathEx

- ea: `0x180065870`
- end: `0x180065be2`
- name: `DeletePathEx`
- size: `882`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation`

## callers

- `0x18004c2b0`

## callees

- `0x180065748`
- `0x180065870`
- `0x18006631c`
- `0x180066a88`
- `0x180066eac`
- `0x180066f58`
- `0x180066ffc`
- `0x180068500`

## import_xrefs

- `KERNEL32!Sleep` at `0x1800659e2`
- `KERNEL32!Sleep` at `0x1800659e2`
- `KERNEL32!SetLastError` at `0x180065ab9`
- `KERNEL32!SetLastError` at `0x180065bc2`
- `KERNEL32!SetLastError` at `0x180065ab9`
- `KERNEL32!SetLastError` at `0x180065bc2`
- `KERNEL32!GetLastError` at `0x1800659a0`
- `KERNEL32!GetLastError` at `0x180065ac7`
- `KERNEL32!GetLastError` at `0x1800659a0`
- `KERNEL32!GetLastError` at `0x180065ac7`
- `KERNEL32!HeapFree` at `0x180065a44`
- `KERNEL32!HeapFree` at `0x180065a58`
- `KERNEL32!HeapFree` at `0x180065a6c`
- `KERNEL32!HeapFree` at `0x180065b68`
- `KERNEL32!HeapFree` at `0x180065b81`
- `KERNEL32!HeapFree` at `0x180065b9a`
- `KERNEL32!HeapFree` at `0x180065a44`
- `KERNEL32!HeapFree` at `0x180065a58`
- `KERNEL32!HeapFree` at `0x180065a6c`
- `KERNEL32!HeapFree` at `0x180065b68`
- `KERNEL32!HeapFree` at `0x180065b81`
- `KERNEL32!HeapFree` at `0x180065b9a`
- `KERNEL32!GetProcessHeap` at `0x180065a36`
- `KERNEL32!GetProcessHeap` at `0x180065a4a`
- `KERNEL32!GetProcessHeap` at `0x180065a5e`
- `KERNEL32!GetProcessHeap` at `0x180065b5a`
- `KERNEL32!GetProcessHeap` at `0x180065b73`
- `KERNEL32!GetProcessHeap` at `0x180065b8c`
- `KERNEL32!GetProcessHeap` at `0x180065a36`
- `KERNEL32!GetProcessHeap` at `0x180065a4a`
- `KERNEL32!GetProcessHeap` at `0x180065a5e`
- `KERNEL32!GetProcessHeap` at `0x180065b5a`
- `KERNEL32!GetProcessHeap` at `0x180065b73`
- `KERNEL32!GetProcessHeap` at `0x180065b8c`

## string_xrefs

- `0x180065ba5`: `DeletePath: Cannot delete <null>.`
- `0x1800658ed`: `SeBackupPrivilege`
- `0x180065a86`: `SeBackupPrivilege`
- `0x1800658c1`: `DeletePath: [%s] doesn't exist as a directory; nothing to delete.`
- `0x180065ad2`: `DeletePath: Failed to get desired paths for [%s] (GLE = 0x%x)`
- `0x18006590e`: `SeRestorePrivilege`
- `0x180065aa8`: `SeRestorePrivilege`
- `0x180065b1a`: `DeletePath:   Long path [%s]`
- `0x180065afe`: `DeletePath:   Full path [%s]`
- `0x180065968`: `DeletePath: Attempting to obliterate [%s] (final path [%s]).`
- `0x180065b39`: `DeletePath:   Final path [%s]`
- `0x180065a17`: `DeletePath: Failed to obliterate [%s] after %u tries; GLE = 0x%x`
- `0x1800659c3`: `DeletePath: Failed to obliterate [%s] (GLE = 0x%x); retrying...`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DeletePathEx(LPCWSTR lpFileName, __int64 a2, __int64 a3, __int64 a4)
{
  DWORD v6; // ecx
  wchar_t *v7; // rsi
  wchar_t *v8; // rbp
  __int64 v9; // rax
  wchar_t *v10; // r15
  __int64 v11; // rax
  __int64 v12; // rax
  DWORD v13; // r14d
  unsigned int v14; // edi
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned int v17; // r12d
  DWORD v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  HANDLE v21; // rax
  HANDLE v22; // rax
  HANDLE v23; // rax
  DWORD LastError; // r14d
  const wchar_t *v26; // rbx
  const wchar_t *v27; // r9
  const wchar_t *v28; // r9
  HANDLE ProcessHeap; // rax
  HANDLE v30; // rax
  HANDLE v31; // rax
  __int64 v32; // [rsp+20h] [rbp-58h]
  int v33; // [rsp+30h] [rbp-48h]
  int v34; // [rsp+34h] [rbp-44h]
  DWORD dwMilliseconds; // [rsp+88h] [rbp+10h]

  if ( !lpFileName || !*lpFileName )
  {
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath: Cannot delete <null>.");
    v6 = 87;
    goto LABEL_34;
  }
  if ( !(unsigned int)DirectoryExists() )
  {
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath: [%s] doesn't exist as a directory; nothing to delete.", lpFileName);
    v6 = 3;
LABEL_34:
    SetLastError(v6);
    return 0;
  }
  v7 = 0;
  v8 = 0;
  v33 = EnablePrivilegeEx(L"SeBackupPrivilege");
  v34 = EnablePrivilegeEx(L"SeRestorePrivilege");
  v9 = FormFullPathName(lpFileName);
  v10 = (wchar_t *)v9;
  if ( !v9
    || (v11 = FormLongPathName(v9), (v7 = (wchar_t *)v11) == 0)
    || (v12 = FormFinalPathNameEx(v11), (v8 = (wchar_t *)v12) == 0) )
  {
    LastError = GetLastError();
    LibLog(
      &g_WdsLibLog,
      0x2000000,
      L"DeletePath: Failed to get desired paths for [%s] (GLE = 0x%x)",
      lpFileName,
      LastError);
    v26 = L"<unavailable>";
    v27 = L"<unavailable>";
    if ( v10 )
      v27 = v10;
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath:   Full path [%s]", v27);
    v28 = L"<unavailable>";
    if ( v7 )
      v28 = v7;
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath:   Long path [%s]", v28);
    if ( v8 )
      v26 = v8;
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath:   Final path [%s]", v26);
    if ( v8 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v8);
    }
    if ( v7 )
    {
      v30 = GetProcessHeap();
      HeapFree(v30, 0, v7);
    }
    if ( v10 )
    {
      v31 = GetProcessHeap();
      HeapFree(v31, 0, v10);
    }
    v6 = LastError;
    goto LABEL_34;
  }
  dwMilliseconds = 1000;
  v13 = 0;
  v14 = 0;
  LibLog(&g_WdsLibLog, 0x4000000, L"DeletePath: Attempting to obliterate [%s] (final path [%s]).", lpFileName, v12);
  v17 = DeletePathEngine(v8, v15, v16, a4);
  if ( !v17 )
  {
    while ( 1 )
    {
      v18 = GetLastError();
      v13 = v18;
      if ( v18 == 1223 )
        break;
      if ( v18 != -2147023673 && v14 < 3 )
      {
        LODWORD(v32) = v18;
        LibLog(&g_WdsLibLog, 0x4000000, L"DeletePath: Failed to obliterate [%s] (GLE = 0x%x); retrying...", v8, v32);
        Sleep(dwMilliseconds);
        ++v14;
        v17 = DeletePathEngine(v8, v19, v20, a4);
        dwMilliseconds *= 2;
        if ( !v17 )
          continue;
      }
      if ( v17 )
        goto LABEL_15;
      break;
    }
    LODWORD(v32) = v14;
    LibLog(
      &g_WdsLibLog,
      0x2000000,
      L"DeletePath: Failed to obliterate [%s] after %u tries; GLE = 0x%x",
      lpFileName,
      v32,
      v13);
  }
LABEL_15:
  v21 = GetProcessHeap();
  HeapFree(v21, 0, v8);
  v22 = GetProcessHeap();
  HeapFree(v22, 0, v7);
  v23 = GetProcessHeap();
  HeapFree(v23, 0, v10);
  if ( v33 == 1 )
    EnablePrivilegeEx(L"SeBackupPrivilege");
  if ( v34 == 1 )
    EnablePrivilegeEx(L"SeRestorePrivilege");
  SetLastError(v13);
  return v17;
}

```

## disassembly

```asm
0x180065870  mov     rax, rsp
0x180065873  mov     [rax+20h], rbx
0x180065877  mov     [rax+18h], r8
0x18006587b  mov     [rax+10h], edx
0x18006587e  push    rbp
0x18006587f  push    rsi
0x180065880  push    rdi
0x180065881  push    r12
0x180065883  push    r13
0x180065885  push    r14
0x180065887  push    r15
0x180065889  sub     rsp, 40h
0x18006588d  mov     dword ptr [rax+18h], 0
0x180065894  mov     r13, r9
0x180065897  mov     dword ptr [rax+8], 0
0x18006589e  mov     rbx, rcx
0x1800658a1  test    rcx, rcx
0x1800658a4  jz      loc_180065BA5
0x1800658aa  xor     eax, eax
0x1800658ac  cmp     ax, [rcx]
0x1800658af  jz      loc_180065BA5
0x1800658b5  call    DirectoryExists
0x1800658ba  test    eax, eax
0x1800658bc  jnz     short loc_1800658E3
0x1800658be  mov     r9, rbx
0x1800658c1  lea     r8, aDeletepathSDoe; "DeletePath: [%s] doesn't exist as a dir"...
0x1800658c8  mov     edx, 2000000h
0x1800658cd  lea     rcx, g_WdsLibLog
0x1800658d4  call    LibLog
0x1800658d9  mov     ecx, 3
0x1800658de  jmp     loc_180065BC2
0x1800658e3  xor     esi, esi
0x1800658e5  lea     r8, [rsp+78h+arg_10]
0x1800658ed  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x1800658f4  xor     ebp, ebp
0x1800658f6  lea     edi, [rsi+1]
0x1800658f9  mov     edx, edi
0x1800658fb  call    EnablePrivilegeEx
0x180065900  lea     r8, [rsp+78h+arg_0]
0x180065908  mov     [rsp+78h+var_48], eax
0x18006590c  mov     edx, edi
0x18006590e  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x180065915  call    EnablePrivilegeEx
0x18006591a  mov     rcx, rbx; lpFileName
0x18006591d  mov     [rsp+78h+var_44], eax
0x180065921  call    FormFullPathName
0x180065926  mov     r15, rax
0x180065929  test    rax, rax
0x18006592c  jz      loc_180065AC7
0x180065932  mov     rcx, rax
0x180065935  call    FormLongPathName
0x18006593a  mov     rsi, rax
0x18006593d  test    rax, rax
0x180065940  jz      loc_180065AC7
0x180065946  mov     rcx, rax
0x180065949  call    FormFinalPathNameEx
0x18006594e  mov     rbp, rax
0x180065951  test    rax, rax
0x180065954  jz      loc_180065AC7
0x18006595a  mov     r9, rbx
0x18006595d  mov     [rsp+78h+dwMilliseconds], 3E8h
0x180065968  lea     r8, aDeletepathAtte; "DeletePath: Attempting to obliterate [%"...
0x18006596f  mov     [rsp+78h+var_58], rax
0x180065974  mov     edx, 4000000h
0x180065979  lea     rcx, g_WdsLibLog
0x180065980  xor     r14d, r14d
0x180065983  xor     edi, edi
0x180065985  call    LibLog
0x18006598a  mov     r9, r13
0x18006598d  mov     rcx, rbp
0x180065990  call    DeletePathEngine
0x180065995  mov     r12d, eax
0x180065998  test    eax, eax
0x18006599a  jnz     loc_180065A36
0x1800659a0  call    cs:__imp_GetLastError
0x1800659a6  mov     r14d, eax
0x1800659a9  cmp     eax, 4C7h
0x1800659ae  jz      short loc_180065A12
0x1800659b0  cmp     eax, 800704C7h
0x1800659b5  jz      short loc_180065A0D
0x1800659b7  cmp     edi, 3
0x1800659ba  jnb     short loc_180065A0D
0x1800659bc  mov     r9, rbp
0x1800659bf  mov     dword ptr [rsp+78h+var_58], eax
0x1800659c3  lea     r8, aDeletepathFail_1; "DeletePath: Failed to obliterate [%s] ("...
0x1800659ca  mov     edx, 4000000h
0x1800659cf  lea     rcx, g_WdsLibLog
0x1800659d6  call    LibLog
0x1800659db  mov     ecx, [rsp+78h+dwMilliseconds]; dwMilliseconds
0x1800659e2  call    cs:__imp_Sleep
0x1800659e8  mov     r9, r13
0x1800659eb  mov     rcx, rbp
0x1800659ee  inc     edi
0x1800659f0  call    DeletePathEngine
0x1800659f5  mov     r12d, eax
0x1800659f8  mov     eax, [rsp+78h+dwMilliseconds]
0x1800659ff  add     eax, eax
0x180065a01  mov     [rsp+78h+dwMilliseconds], eax
0x180065a08  test    r12d, r12d
0x180065a0b  jz      short loc_1800659A0
0x180065a0d  test    r12d, r12d
0x180065a10  jnz     short loc_180065A36
0x180065a12  mov     [rsp+78h+var_50], r14d
0x180065a17  lea     r8, aDeletepathFail; "DeletePath: Failed to obliterate [%s] a"...
0x180065a1e  mov     r9, rbx
0x180065a21  mov     dword ptr [rsp+78h+var_58], edi
0x180065a25  mov     edx, 2000000h
0x180065a2a  lea     rcx, g_WdsLibLog
0x180065a31  call    LibLog
0x180065a36  call    cs:__imp_GetProcessHeap
0x180065a3c  mov     r8, rbp; lpMem
0x180065a3f  xor     edx, edx; dwFlags
0x180065a41  mov     rcx, rax; hHeap
0x180065a44  call    cs:__imp_HeapFree
0x180065a4a  call    cs:__imp_GetProcessHeap
0x180065a50  mov     r8, rsi; lpMem
0x180065a53  xor     edx, edx; dwFlags
0x180065a55  mov     rcx, rax; hHeap
0x180065a58  call    cs:__imp_HeapFree
0x180065a5e  call    cs:__imp_GetProcessHeap
0x180065a64  mov     r8, r15; lpMem
0x180065a67  xor     edx, edx; dwFlags
0x180065a69  mov     rcx, rax; hHeap
0x180065a6c  call    cs:__imp_HeapFree
0x180065a72  cmp     [rsp+78h+var_48], 1
0x180065a77  jnz     short loc_180065A94
0x180065a79  cmp     [rsp+78h+arg_10], 0
0x180065a81  jnz     short loc_180065A94
0x180065a83  xor     r8d, r8d
0x180065a86  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x180065a8d  xor     edx, edx
0x180065a8f  call    EnablePrivilegeEx
0x180065a94  cmp     [rsp+78h+var_44], 1
0x180065a99  jnz     short loc_180065AB6
0x180065a9b  cmp     [rsp+78h+arg_0], 0
0x180065aa3  jnz     short loc_180065AB6
0x180065aa5  xor     r8d, r8d
0x180065aa8  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x180065aaf  xor     edx, edx
0x180065ab1  call    EnablePrivilegeEx
0x180065ab6  mov     ecx, r14d; dwErrCode
0x180065ab9  call    cs:__imp_SetLastError
0x180065abf  mov     eax, r12d
0x180065ac2  jmp     loc_180065BCA
0x180065ac7  call    cs:__imp_GetLastError
0x180065acd  mov     edi, 2000000h
0x180065ad2  lea     r8, aDeletepathFail_0; "DeletePath: Failed to get desired paths"...
0x180065ad9  lea     rcx, g_WdsLibLog
0x180065ae0  mov     dword ptr [rsp+78h+var_58], eax
0x180065ae4  mov     edx, edi
0x180065ae6  mov     r9, rbx
0x180065ae9  mov     r14d, eax
0x180065aec  call    LibLog
0x180065af1  lea     rbx, aUnavailable; "<unavailable>"
0x180065af8  test    r15, r15
0x180065afb  mov     r9, rbx
0x180065afe  lea     r8, aDeletepathFull; "DeletePath:   Full path [%s]"
0x180065b05  cmovnz  r9, r15
0x180065b09  lea     rcx, g_WdsLibLog
0x180065b10  mov     edx, edi
0x180065b12  call    LibLog
0x180065b17  test    rsi, rsi
0x180065b1a  lea     r8, aDeletepathLong; "DeletePath:   Long path [%s]"
0x180065b21  mov     r9, rbx
0x180065b24  lea     rcx, g_WdsLibLog
0x180065b2b  cmovnz  r9, rsi
0x180065b2f  mov     edx, edi
0x180065b31  call    LibLog
0x180065b36  test    rbp, rbp
0x180065b39  lea     r8, aDeletepathFina; "DeletePath:   Final path [%s]"
0x180065b40  mov     edx, edi
0x180065b42  lea     rcx, g_WdsLibLog
0x180065b49  cmovnz  rbx, rbp
0x180065b4d  mov     r9, rbx
0x180065b50  call    LibLog
0x180065b55  test    rbp, rbp
0x180065b58  jz      short loc_180065B6E
0x180065b5a  call    cs:__imp_GetProcessHeap
0x180065b60  mov     r8, rbp; lpMem
0x180065b63  xor     edx, edx; dwFlags
0x180065b65  mov     rcx, rax; hHeap
0x180065b68  call    cs:__imp_HeapFree
0x180065b6e  test    rsi, rsi
0x180065b71  jz      short loc_180065B87
0x180065b73  call    cs:__imp_GetProcessHeap
0x180065b79  mov     r8, rsi; lpMem
0x180065b7c  xor     edx, edx; dwFlags
0x180065b7e  mov     rcx, rax; hHeap
0x180065b81  call    cs:__imp_HeapFree
0x180065b87  test    r15, r15
0x180065b8a  jz      short loc_180065BA0
0x180065b8c  call    cs:__imp_GetProcessHeap
0x180065b92  mov     r8, r15; lpMem
0x180065b95  xor     edx, edx; dwFlags
0x180065b97  mov     rcx, rax; hHeap
0x180065b9a  call    cs:__imp_HeapFree
0x180065ba0  mov     ecx, r14d
0x180065ba3  jmp     short loc_180065BC2
0x180065ba5  lea     r8, aDeletepathCann; "DeletePath: Cannot delete <null>."
0x180065bac  mov     edx, 2000000h
0x180065bb1  lea     rcx, g_WdsLibLog
0x180065bb8  call    LibLog
0x180065bbd  mov     ecx, 57h ; 'W'; dwErrCode
0x180065bc2  call    cs:__imp_SetLastError
0x180065bc8  xor     eax, eax
0x180065bca  mov     rbx, [rsp+78h+arg_18]
0x180065bd2  add     rsp, 40h
0x180065bd6  pop     r15
0x180065bd8  pop     r14
0x180065bda  pop     r13
0x180065bdc  pop     r12
0x180065bde  pop     rdi
0x180065bdf  pop     rsi
0x180065be0  pop     rbp
0x180065be1  retn
```
