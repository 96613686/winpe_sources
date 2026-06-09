# BfspSpacesCopyToPhysicalPartitions

- ea: `0x14000d494`
- end: `0x14000d911`
- name: `BfspSpacesCopyToPhysicalPartitions`
- size: `1149`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, const wchar_t *, const wchar_t *, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task`

## callers

- `0x14000cfc0`

## callees

- `0x140001738`
- `0x140002b7c`
- `0x14000bd28`
- `0x14000c7bc`
- `0x14000d3c4`
- `0x14000d494`
- `0x14000dba4`
- `0x14000e628`
- `0x14000f50c`
- `0x140010194`
- `0x140011a88`
- `0x140011b18`
- `0x140026650`

## import_xrefs

- `msvcrt!wcschr` at `0x14000d6a2`
- `msvcrt!wcschr` at `0x14000d6a2`
- `KERNEL32!SetLastError` at `0x14000d54b`
- `KERNEL32!SetLastError` at `0x14000d6ff`
- `KERNEL32!SetLastError` at `0x14000d7e4`
- `KERNEL32!SetLastError` at `0x14000d7f5`
- `KERNEL32!SetLastError` at `0x14000d54b`
- `KERNEL32!SetLastError` at `0x14000d6ff`
- `KERNEL32!SetLastError` at `0x14000d7e4`
- `KERNEL32!SetLastError` at `0x14000d7f5`
- `KERNEL32!GetLastError` at `0x14000d4eb`
- `KERNEL32!GetLastError` at `0x14000d509`
- `KERNEL32!GetLastError` at `0x14000d6ca`
- `KERNEL32!GetLastError` at `0x14000d72e`
- `KERNEL32!GetLastError` at `0x14000d752`
- `KERNEL32!GetLastError` at `0x14000d798`
- `KERNEL32!GetLastError` at `0x14000d7da`
- `KERNEL32!GetLastError` at `0x14000d7fb`
- `KERNEL32!GetLastError` at `0x14000d893`
- `KERNEL32!GetLastError` at `0x14000d4eb`
- `KERNEL32!GetLastError` at `0x14000d509`
- `KERNEL32!GetLastError` at `0x14000d6ca`
- `KERNEL32!GetLastError` at `0x14000d72e`
- `KERNEL32!GetLastError` at `0x14000d752`
- `KERNEL32!GetLastError` at `0x14000d798`
- `KERNEL32!GetLastError` at `0x14000d7da`
- `KERNEL32!GetLastError` at `0x14000d7fb`
- `KERNEL32!GetLastError` at `0x14000d893`
- `KERNEL32!HeapFree` at `0x14000d520`
- `KERNEL32!HeapFree` at `0x14000d539`
- `KERNEL32!HeapFree` at `0x14000d7cd`
- `KERNEL32!HeapFree` at `0x14000d520`
- `KERNEL32!HeapFree` at `0x14000d539`
- `KERNEL32!HeapFree` at `0x14000d7cd`
- `KERNEL32!GetProcessHeap` at `0x14000d512`
- `KERNEL32!GetProcessHeap` at `0x14000d52b`
- `KERNEL32!GetProcessHeap` at `0x14000d7bf`
- `KERNEL32!GetProcessHeap` at `0x14000d512`
- `KERNEL32!GetProcessHeap` at `0x14000d52b`
- `KERNEL32!GetProcessHeap` at `0x14000d7bf`
- `KERNEL32!GetFileAttributesW` at `0x14000d770`
- `KERNEL32!GetFileAttributesW` at `0x14000d770`
- `KERNEL32!CreateDirectoryW` at `0x14000d6c0`
- `KERNEL32!CreateDirectoryW` at `0x14000d745`
- `KERNEL32!CreateDirectoryW` at `0x14000d6c0`
- `KERNEL32!CreateDirectoryW` at `0x14000d745`

## string_xrefs

- `0x14000d56a`: `ServiceSpaces: %s does not exist`
- `0x14000d80e`: `ServiceSpaces: Failed to create path %s. Last error = %#x`
- `0x14000d8a1`: `ServiceSpaces: Failed to copy %s to %s. Last Error = %#x`
- `0x14000d862`: `ServiceSpaces: Skipping non-Windows %s`
- `0x14000d8b8`: `ServiceSpaces: Skipping %s`
- `0x14000d7a1`: `CreatePath: Unable to get attributes for [%s]; GLE = 0x%x`
- `0x14000d764`: `CreatePath: Unable to create [%s]; GLE = 0x%x`
- `0x14000d739`: `CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x`
- `0x14000d6e5`: `CreatePath: Unable to create intermediate path [%s]; GLE = 0x%x`
- `0x14000d78c`: `CreatePath: Existing path [%s] is not a directory; GLE = 0x%x`

## pseudocode

```c
__int64 __fastcall BfspSpacesCopyToPhysicalPartitions(
        __int64 a1,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        __int64 a5)
{
  __int64 v5; // r15
  DWORD LastError; // r14d
  wchar_t *v9; // r13
  wchar_t *v10; // rax
  wchar_t *v11; // rsi
  HANDLE v12; // rax
  HANDLE v13; // rax
  int v15; // r12d
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  unsigned int v18; // edi
  unsigned int v19; // ebx
  __int64 v20; // rcx
  DWORD v21; // ebx
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // r12
  __int64 v24; // rax
  WCHAR *v25; // rdi
  int v26; // r15d
  const wchar_t *v27; // rcx
  wchar_t *v28; // rax
  DWORD v29; // eax
  DWORD v30; // eax
  wchar_t *v31; // r9
  const wchar_t *v32; // r8
  DWORD FileAttributesW; // eax
  HANDLE ProcessHeap; // rax
  DWORD v35; // eax
  int FirmwareType; // eax
  __int64 v37; // [rsp+20h] [rbp-E0h]
  wchar_t *v38; // [rsp+30h] [rbp-D0h]
  unsigned int v39; // [rsp+38h] [rbp-C8h]
  int v40; // [rsp+3Ch] [rbp-C4h]
  int v41; // [rsp+40h] [rbp-C0h]
  wchar_t pszSrc[264]; // [rsp+60h] [rbp-A0h] BYREF

  v5 = a5;
  LastError = 0;
  v9 = BfspEnvExpandString(a1, a3);
  if ( !v9 )
  {
    LastError = GetLastError();
    goto LABEL_7;
  }
  v10 = BfspEnvExpandString(a1, a2);
  v11 = v10;
  if ( !v10 )
  {
    LastError = GetLastError();
    goto LABEL_5;
  }
  if ( (unsigned int)BfspFileExists(v10) )
  {
    v15 = 0;
    v40 = 0;
    v16 = -1;
    do
      ++v16;
    while ( v9[v16] );
    v39 = 0;
    v17 = v16 - 1;
    v18 = 0;
    if ( v16 )
    {
      while ( v9[v17] != 92 )
      {
        ++v18;
        --v17;
        v39 = v18;
        if ( v18 >= v16 )
          goto LABEL_18;
      }
      v15 = 1;
      v40 = 1;
    }
LABEL_18:
    v19 = 0;
    v41 = 0;
    if ( !*(_DWORD *)(a5 + 8) )
      goto LABEL_5;
    while ( 1 )
    {
      LODWORD(v37) = *(_DWORD *)(v5 + 12LL * v19 + 20);
      StringCchPrintfW(
        pszSrc,
        0x104u,
        L"\\\\?\\Harddisk%uPartition%u\\%s",
        *(unsigned int *)(v5 + 12LL * v19 + 16),
        v37,
        v9,
        v38);
      if ( !v15 )
        goto LABEL_51;
      v20 = -1;
      v21 = 0;
      do
        ++v20;
      while ( pszSrc[v20] );
      v22 = v20 + ~(unsigned __int64)v18;
      v23 = v22;
      if ( 2 * v22 >= 0x208 )
        _report_rangecheckfailure();
      pszSrc[v22] = 0;
      v38 = 0;
      if ( pszSrc[0] )
      {
        v24 = PrepareUnicodePathEx(pszSrc);
        v25 = (WCHAR *)v24;
        if ( v24 )
        {
          v26 = 1;
          v27 = (const wchar_t *)v24;
          while ( 1 )
          {
            v28 = wcschr(v27, 0x5Cu);
            v38 = v28;
            if ( !v28 )
              break;
            *v28 = 0;
            if ( !CreateDirectoryW(v25, 0) )
            {
              v29 = GetLastError();
              v21 = v29;
              if ( v29 == 5 || v29 == 183 )
              {
                v21 = 0;
              }
              else
              {
                LODWORD(v37) = v29;
                LibLog(
                  &g_WdsLibLog,
                  50331648,
                  L"CreatePath: Unable to create intermediate path [%s]; GLE = 0x%x",
                  v25,
                  v37);
                SetLastError(v21);
                v26 = 0;
              }
            }
            *v38 = 92;
            v27 = ++v38;
            if ( v26 != 1 )
            {
              v30 = GetLastError();
              v31 = pszSrc;
              v32 = L"CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x";
              goto LABEL_42;
            }
          }
          if ( CreateDirectoryW(v25, 0) )
            goto LABEL_44;
          v30 = GetLastError();
          v21 = v30;
          if ( v30 != 183 )
          {
            v31 = v25;
            v32 = L"CreatePath: Unable to create [%s]; GLE = 0x%x";
            goto LABEL_43;
          }
          FileAttributesW = GetFileAttributesW(v25);
          if ( FileAttributesW == -1 )
          {
            v30 = GetLastError();
            v31 = v25;
            v32 = L"CreatePath: Unable to get attributes for [%s]; GLE = 0x%x";
LABEL_42:
            v21 = v30;
LABEL_43:
            LODWORD(v37) = v30;
            LibLog(&g_WdsLibLog, 50331648, v32, v31, v37);
            goto LABEL_44;
          }
          if ( (FileAttributesW & 0x10) != 0 )
          {
            v21 = 0;
          }
          else
          {
            LODWORD(v37) = 183;
            LibLog(&g_WdsLibLog, 50331648, L"CreatePath: Existing path [%s] is not a directory; GLE = 0x%x", v25, v37);
          }
LABEL_44:
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v25);
          v5 = a5;
        }
        else
        {
          v21 = GetLastError();
        }
        SetLastError(v21);
        if ( !v21 )
          goto LABEL_50;
      }
      else
      {
        SetLastError(0x57u);
      }
      v35 = GetLastError();
      BfspLogMessage(3, L"ServiceSpaces: Failed to create path %s. Last error = %#x", pszSrc, v35);
LABEL_50:
      v19 = v41;
      v18 = v39;
      pszSrc[v23] = 92;
      v15 = v40;
LABEL_51:
      if ( a4
        && (unsigned int)BfspFileExists(pszSrc)
        && (FirmwareType = BfspGetFirmwareType(), !(unsigned int)BfspIsWindowsBinary((__int64)pszSrc, a4, FirmwareType)) )
      {
        BfspLogMessage(3, L"ServiceSpaces: Skipping non-Windows %s", pszSrc);
      }
      else if ( (unsigned int)BfspShouldFileBeCopied(v11) )
      {
        if ( !(unsigned int)BfspCopyFile(v11, pszSrc) )
        {
          LODWORD(v37) = GetLastError();
          BfspLogMessage(3, L"ServiceSpaces: Failed to copy %s to %s. Last Error = %#x", v11, pszSrc, v37);
        }
      }
      else
      {
        BfspLogMessage(3, L"ServiceSpaces: Skipping %s", pszSrc);
      }
      v41 = ++v19;
      if ( v19 >= *(_DWORD *)(v5 + 8) )
        goto LABEL_5;
    }
  }
  BfspLogMessage(4, L"ServiceSpaces: %s does not exist", v11);
  LastError = 2;
LABEL_5:
  v12 = GetProcessHeap();
  HeapFree(v12, 0, v9);
  if ( v11 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v11);
  }
LABEL_7:
  if ( !LastError )
    return 1;
  SetLastError(LastError);
  return 0;
}

```

## disassembly

```asm
0x14000d494  push    rbp
0x14000d496  push    rbx
0x14000d497  push    rsi
0x14000d498  push    rdi
0x14000d499  push    r12
0x14000d49b  push    r13
0x14000d49d  push    r14
0x14000d49f  push    r15
0x14000d4a1  lea     rbp, [rsp-188h]
0x14000d4a9  sub     rsp, 288h
0x14000d4b0  mov     rax, cs:__security_cookie
0x14000d4b7  xor     rax, rsp
0x14000d4ba  mov     [rbp+1C0h+var_50], rax
0x14000d4c1  mov     r15, [rbp+1C0h+arg_20]
0x14000d4c8  mov     rdi, rdx
0x14000d4cb  mov     rdx, r8
0x14000d4ce  mov     [rsp+2C0h+var_270], r15
0x14000d4d3  mov     [rsp+2C0h+var_278], r9
0x14000d4d8  mov     rbx, rcx
0x14000d4db  call    BfspEnvExpandString
0x14000d4e0  xor     r14d, r14d
0x14000d4e3  mov     r13, rax
0x14000d4e6  test    rax, rax
0x14000d4e9  jnz     short loc_14000D4F6
0x14000d4eb  call    cs:__imp_GetLastError
0x14000d4f1  mov     r14d, eax
0x14000d4f4  jmp     short loc_14000D53F
0x14000d4f6  mov     rdx, rdi
0x14000d4f9  mov     rcx, rbx
0x14000d4fc  call    BfspEnvExpandString
0x14000d501  mov     rsi, rax
0x14000d504  test    rax, rax
0x14000d507  jnz     short loc_14000D558
0x14000d509  call    cs:__imp_GetLastError
0x14000d50f  mov     r14d, eax
0x14000d512  call    cs:__imp_GetProcessHeap
0x14000d518  mov     r8, r13; lpMem
0x14000d51b  xor     edx, edx; dwFlags
0x14000d51d  mov     rcx, rax; hHeap
0x14000d520  call    cs:__imp_HeapFree
0x14000d526  test    rsi, rsi
0x14000d529  jz      short loc_14000D53F
0x14000d52b  call    cs:__imp_GetProcessHeap
0x14000d531  mov     r8, rsi; lpMem
0x14000d534  xor     edx, edx; dwFlags
0x14000d536  mov     rcx, rax; hHeap
0x14000d539  call    cs:__imp_HeapFree
0x14000d53f  test    r14d, r14d
0x14000d542  jz      loc_14000D8E3
0x14000d548  mov     ecx, r14d; dwErrCode
0x14000d54b  call    cs:__imp_SetLastError
0x14000d551  xor     eax, eax
0x14000d553  jmp     loc_14000D8E8
0x14000d558  mov     rcx, rsi
0x14000d55b  call    BfspFileExists
0x14000d560  xor     r8d, r8d
0x14000d563  test    eax, eax
0x14000d565  jnz     short loc_14000D581
0x14000d567  mov     r8, rsi
0x14000d56a  lea     rdx, aServicespacesS_1; "ServiceSpaces: %s does not exist"
0x14000d571  lea     ecx, [rax+4]
0x14000d574  call    BfspLogMessage
0x14000d579  mov     r14d, 2
0x14000d57f  jmp     short loc_14000D512
0x14000d581  mov     r12d, r8d
0x14000d584  mov     [rsp+2C0h+var_284], r8d
0x14000d589  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000d58d  inc     rcx
0x14000d590  cmp     [r13+rcx*2+0], r8w
0x14000d596  jnz     short loc_14000D58D
0x14000d598  mov     [rsp+2C0h+var_288], r8d
0x14000d59d  lea     rdx, [rcx-1]
0x14000d5a1  mov     edi, r8d
0x14000d5a4  mov     eax, 5Ch ; '\'
0x14000d5a9  test    rcx, rcx
0x14000d5ac  jz      short loc_14000D5D8
0x14000d5ae  cmp     [r13+rdx*2+0], ax
0x14000d5b4  jz      short loc_14000D5CD
0x14000d5b6  inc     edi
0x14000d5b8  dec     rdx
0x14000d5bb  mov     eax, edi
0x14000d5bd  cmp     rax, rcx
0x14000d5c0  mov     [rsp+2C0h+var_288], edi
0x14000d5c4  mov     eax, 5Ch ; '\'
0x14000d5c9  jb      short loc_14000D5AE
0x14000d5cb  jmp     short loc_14000D5D8
0x14000d5cd  mov     r12d, 1
0x14000d5d3  mov     [rsp+2C0h+var_284], r12d
0x14000d5d8  mov     ebx, r8d
0x14000d5db  mov     [rsp+2C0h+var_280], ebx
0x14000d5df  cmp     [r15+8], r8d
0x14000d5e3  jbe     loc_14000D512
0x14000d5e9  mov     eax, ebx
0x14000d5eb  lea     r8, aHarddiskUparti; "\\\\?\\Harddisk%uPartition%u\\%s"
0x14000d5f2  mov     [rsp+2C0h+var_298], r13
0x14000d5f7  lea     rcx, [rsp+2C0h+pszSrc]; unsigned __int16 *
0x14000d5fc  mov     edx, 104h; unsigned __int64
0x14000d601  lea     r9, [rax+rax*2]
0x14000d605  mov     eax, [r15+r9*4+14h]
0x14000d60a  mov     r9d, [r15+r9*4+10h]
0x14000d60f  mov     dword ptr [rsp+2C0h+var_2A0], eax
0x14000d613  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000d618  test    r12d, r12d
0x14000d61b  jz      loc_14000D832
0x14000d621  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000d625  lea     rax, [rsp+2C0h+pszSrc]
0x14000d62a  xor     ebx, ebx
0x14000d62c  inc     rcx
0x14000d62f  cmp     [rax+rcx*2], bx
0x14000d633  jnz     short loc_14000D62C
0x14000d635  mov     eax, edi
0x14000d637  not     rax
0x14000d63a  add     rax, rcx
0x14000d63d  lea     r12, [rax+rax]
0x14000d641  cmp     r12, 208h
0x14000d648  jnb     loc_14000D90B
0x14000d64e  mov     [rsp+r12+2C0h+pszSrc], bx
0x14000d654  mov     [rsp+2C0h+var_290], rbx
0x14000d659  cmp     bx, [rsp+2C0h+pszSrc]
0x14000d65e  jz      loc_14000D7F0
0x14000d664  lea     rdx, [rsp+2C0h+var_290]
0x14000d669  lea     rcx, [rsp+2C0h+pszSrc]; pszSrc
0x14000d66e  call    PrepareUnicodePathEx
0x14000d673  mov     rdi, rax
0x14000d676  test    rax, rax
0x14000d679  jz      loc_14000D7DA
0x14000d67f  mov     rcx, [rsp+2C0h+var_290]
0x14000d684  mov     r15d, 1
0x14000d68a  test    rcx, rcx
0x14000d68d  jz      short loc_14000D695
0x14000d68f  add     rcx, 2
0x14000d693  jmp     short loc_14000D698
0x14000d695  mov     rcx, rdi; Str
0x14000d698  mov     [rsp+2C0h+var_290], rcx
0x14000d69d  mov     edx, 5Ch ; '\'; Ch
0x14000d6a2  call    cs:__imp_wcschr
0x14000d6a8  xor     ecx, ecx
0x14000d6aa  xor     edx, edx; lpSecurityAttributes
0x14000d6ac  mov     [rsp+2C0h+var_290], rax
0x14000d6b1  test    rax, rax
0x14000d6b4  jz      loc_14000D742
0x14000d6ba  mov     [rax], cx
0x14000d6bd  mov     rcx, rdi; lpPathName
0x14000d6c0  call    cs:__imp_CreateDirectoryW
0x14000d6c6  test    eax, eax
0x14000d6c8  jnz     short loc_14000D70C
0x14000d6ca  call    cs:__imp_GetLastError
0x14000d6d0  mov     ebx, eax
0x14000d6d2  cmp     eax, 5
0x14000d6d5  jz      short loc_14000D70A
0x14000d6d7  cmp     eax, 0B7h
0x14000d6dc  jz      short loc_14000D70A
0x14000d6de  mov     r9, rdi
0x14000d6e1  mov     dword ptr [rsp+2C0h+var_2A0], eax
0x14000d6e5  lea     r8, aCreatepathUnab; "CreatePath: Unable to create intermedia"...
0x14000d6ec  mov     edx, 3000000h
0x14000d6f1  lea     rcx, g_WdsLibLog
0x14000d6f8  call    LibLog
0x14000d6fd  mov     ecx, ebx; dwErrCode
0x14000d6ff  call    cs:__imp_SetLastError
0x14000d705  xor     r15d, r15d
0x14000d708  jmp     short loc_14000D70C
0x14000d70a  xor     ebx, ebx
0x14000d70c  mov     rax, [rsp+2C0h+var_290]
0x14000d711  mov     word ptr [rax], 5Ch ; '\'
0x14000d716  mov     rcx, [rsp+2C0h+var_290]
0x14000d71b  add     rcx, 2
0x14000d71f  mov     [rsp+2C0h+var_290], rcx
0x14000d724  cmp     r15d, 1
0x14000d728  jz      loc_14000D69D
0x14000d72e  call    cs:__imp_GetLastError
0x14000d734  lea     r9, [rsp+2C0h+pszSrc]
0x14000d739  lea     r8, aCreatepathUnab_2; "CreatePath: Unable to create parent dir"...
0x14000d740  jmp     short loc_14000D7A8
0x14000d742  mov     rcx, rdi; lpPathName
0x14000d745  call    cs:__imp_CreateDirectoryW
0x14000d74b  xor     r15d, r15d
0x14000d74e  test    eax, eax
0x14000d750  jnz     short loc_14000D7BF
0x14000d752  call    cs:__imp_GetLastError
0x14000d758  mov     ebx, eax
0x14000d75a  cmp     eax, 0B7h
0x14000d75f  jz      short loc_14000D76D
0x14000d761  mov     r9, rdi
0x14000d764  lea     r8, aCreatepathUnab_1; "CreatePath: Unable to create [%s]; GLE "...
0x14000d76b  jmp     short loc_14000D7AA
0x14000d76d  mov     rcx, rdi; lpFileName
0x14000d770  call    cs:__imp_GetFileAttributesW
0x14000d776  cmp     eax, 0FFFFFFFFh
0x14000d779  jz      short loc_14000D798
0x14000d77b  test    al, 10h
0x14000d77d  jz      short loc_14000D784
0x14000d77f  mov     ebx, r15d
0x14000d782  jmp     short loc_14000D7BF
0x14000d784  mov     dword ptr [rsp+2C0h+var_2A0], 0B7h
0x14000d78c  lea     r8, aCreatepathExis; "CreatePath: Existing path [%s] is not a"...
0x14000d793  mov     r9, rdi
0x14000d796  jmp     short loc_14000D7AE
0x14000d798  call    cs:__imp_GetLastError
0x14000d79e  mov     r9, rdi
0x14000d7a1  lea     r8, aCreatepathUnab_0; "CreatePath: Unable to get attributes fo"...
0x14000d7a8  mov     ebx, eax
0x14000d7aa  mov     dword ptr [rsp+2C0h+var_2A0], eax
0x14000d7ae  mov     edx, 3000000h
0x14000d7b3  lea     rcx, g_WdsLibLog
0x14000d7ba  call    LibLog
0x14000d7bf  call    cs:__imp_GetProcessHeap
0x14000d7c5  mov     r8, rdi; lpMem
0x14000d7c8  xor     edx, edx; dwFlags
0x14000d7ca  mov     rcx, rax; hHeap
0x14000d7cd  call    cs:__imp_HeapFree
0x14000d7d3  mov     r15, [rsp+2C0h+var_270]
0x14000d7d8  jmp     short loc_14000D7E2
0x14000d7da  call    cs:__imp_GetLastError
0x14000d7e0  mov     ebx, eax
0x14000d7e2  mov     ecx, ebx; dwErrCode
0x14000d7e4  call    cs:__imp_SetLastError
0x14000d7ea  test    ebx, ebx
0x14000d7ec  jz      short loc_14000D81A
0x14000d7ee  jmp     short loc_14000D7FB
0x14000d7f0  mov     ecx, 57h ; 'W'; dwErrCode
0x14000d7f5  call    cs:__imp_SetLastError
0x14000d7fb  call    cs:__imp_GetLastError
0x14000d801  lea     r8, [rsp+2C0h+pszSrc]
0x14000d806  mov     ecx, 3
0x14000d80b  mov     r9d, eax
0x14000d80e  lea     rdx, aServicespacesF; "ServiceSpaces: Failed to create path %s"...
0x14000d815  call    BfspLogMessage
0x14000d81a  mov     ebx, [rsp+2C0h+var_280]
0x14000d81e  mov     eax, 5Ch ; '\'
0x14000d823  mov     edi, [rsp+2C0h+var_288]
0x14000d827  mov     [rsp+r12+2C0h+pszSrc], ax
0x14000d82d  mov     r12d, [rsp+2C0h+var_284]
0x14000d832  cmp     [rsp+2C0h+var_278], r14
0x14000d837  jz      short loc_14000D86B
0x14000d839  lea     rcx, [rsp+2C0h+pszSrc]
0x14000d83e  call    BfspFileExists
0x14000d843  test    eax, eax
0x14000d845  jz      short loc_14000D86B
0x14000d847  call    BfspGetFirmwareType
0x14000d84c  mov     rdx, [rsp+2C0h+var_278]
0x14000d851  lea     rcx, [rsp+2C0h+pszSrc]
0x14000d856  mov     r8d, eax
0x14000d859  call    BfspIsWindowsBinary
0x14000d85e  test    eax, eax
0x14000d860  jnz     short loc_14000D86B
0x14000d862  lea     rdx, aServicespacesS_0; "ServiceSpaces: Skipping non-Windows %s"
0x14000d869  jmp     short loc_14000D8BF
0x14000d86b  mov     r8d, 1
0x14000d871  lea     rdx, [rsp+2C0h+pszSrc]
0x14000d876  mov     rcx, rsi; Str
0x14000d879  call    BfspShouldFileBeCopied
0x14000d87e  test    eax, eax
0x14000d880  jz      short loc_14000D8B8
0x14000d882  lea     rdx, [rsp+2C0h+pszSrc]; lpFileName
0x14000d887  mov     rcx, rsi; pszSrc
0x14000d88a  call    BfspCopyFile
0x14000d88f  test    eax, eax
0x14000d891  jnz     short loc_14000D8CE
0x14000d893  call    cs:__imp_GetLastError
0x14000d899  lea     r9, [rsp+2C0h+pszSrc]
0x14000d89e  mov     r8, rsi
0x14000d8a1  lea     rdx, aServicespacesF_0; "ServiceSpaces: Failed to copy %s to %s."...
0x14000d8a8  mov     dword ptr [rsp+2C0h+var_2A0], eax
0x14000d8ac  mov     ecx, 3
0x14000d8b1  call    BfspLogMessage
0x14000d8b6  jmp     short loc_14000D8CE
0x14000d8b8  lea     rdx, aServicespacesS; "ServiceSpaces: Skipping %s"
0x14000d8bf  lea     r8, [rsp+2C0h+pszSrc]
0x14000d8c4  mov     ecx, 3
0x14000d8c9  call    BfspLogMessage
0x14000d8ce  inc     ebx
0x14000d8d0  mov     [rsp+2C0h+var_280], ebx
0x14000d8d4  cmp     ebx, [r15+8]
0x14000d8d8  jb      loc_14000D5E9
0x14000d8de  jmp     loc_14000D512
0x14000d8e3  mov     eax, 1
0x14000d8e8  mov     rcx, [rbp+1C0h+var_50]
0x14000d8ef  xor     rcx, rsp; StackCookie
0x14000d8f2  call    __security_check_cookie
0x14000d8f7  add     rsp, 288h
0x14000d8fe  pop     r15
0x14000d900  pop     r14
0x14000d902  pop     r13
0x14000d904  pop     r12
0x14000d906  pop     rdi
0x14000d907  pop     rsi
0x14000d908  pop     rbx
0x14000d909  pop     rbp
0x14000d90a  retn
0x14000d90b  call    __report_rangecheckfailure
```
