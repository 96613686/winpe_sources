# Wallet::WalletDatabaseESE::LoadDatabase(char const *)

- ea: `0x1800102c0`
- end: `0x1800108fe`
- name: `?LoadDatabase@WalletDatabaseESE@Wallet@@AEAAJPEBD@Z`
- size: `1598`
- prototype: `__int64 __fastcall(Wallet::WalletDatabaseESE *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1800110f0`

## callees

- `0x18000de7c`
- `0x18000f8bc`
- `0x18000fab0`
- `0x18000fe14`
- `0x1800102c0`
- `0x18001108c`
- `0x18001150c`
- `0x18001183c`
- `0x180011924`
- `0x1800124c0`
- `0x1800126c0`
- `0x18001c048`
- `0x180043052`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001089e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001089e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800108a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800108a7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180010336`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180010336`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180010366`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180010366`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180010388`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180010388`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1800103a6`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1800103a6`
- `api-ms-win-core-path-l1-1-0!PathCchStripPrefix` at `0x180010397`
- `api-ms-win-core-path-l1-1-0!PathCchStripPrefix` at `0x180010397`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800103b7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800103b7`

## pseudocode

```c
__int64 __fastcall Wallet::WalletDatabaseESE::LoadDatabase(Wallet::WalletDatabaseESE *this, const char *a2)
{
  int v4; // r15d
  int v5; // ebx
  HANDLE FileW; // rax
  void *v7; // r13
  unsigned int v8; // ebx
  _QWORD *v9; // r12
  int v10; // eax
  Wallet::WalletDatabaseESE *v11; // rcx
  int v12; // r14d
  unsigned int i; // esi
  struct TableDefinition *v14; // rdx
  WalletEncrypter *v15; // rcx
  unsigned int v17; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v18[3]; // [rsp+48h] [rbp-B8h] BYREF
  char v19[272]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR WideCharStr[2]; // [rsp+170h] [rbp+70h] BYREF
  char v21[524]; // [rsp+174h] [rbp+74h] BYREF
  WCHAR szFilePath[264]; // [rsp+380h] [rbp+280h] BYREF

  v4 = 0;
  *(_DWORD *)WideCharStr = 0;
  v5 = -107;
  memset_0(v21, 0, 0x204u);
  if ( !MultiByteToWideChar(0xFDE9u, 0, a2, -1, WideCharStr, 260) )
  {
    v7 = 0;
    GetLastError();
    goto LABEL_47;
  }
  FileW = CreateFileW(WideCharStr, 0, 1u, 0, 3u, 0x2000000u, 0);
  v7 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    GetFinalPathNameByHandleW(FileW, szFilePath, 0x104u, 0);
    PathCchStripPrefix(szFilePath, 0x104u);
    PathCchAddBackslash(szFilePath, 0x104u);
    if ( !lstrcmpW(WideCharStr, szFilePath) )
    {
      if ( (int)StringCchPrintfA(v19, 0x104u, "%swallet.db", a2) < 0 )
      {
        v5 = -1011;
        goto LABEL_47;
      }
      v5 = (***((__int64 (__fastcall ****)(_QWORD, char *, _QWORD))this + 13))(
             *((_QWORD *)this + 13),
             (char *)this + 16,
             0);
      if ( v5 >= 0 )
      {
        v17 = 0;
        memset(v18, 0, sizeof(v18));
        if ( (unsigned int)ATL::CRegKey::Open(
                             (ATL::CRegKey *)v18,
                             HKEY_LOCAL_MACHINE,
                             L"Software\\Microsoft\\Wallet",
                             0x2001Fu) )
          GetLastError();
        else
          ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v18, L"DatabaseCorrupt", &v17);
        v8 = v17;
        ATL::CRegKey::Close((ATL::CRegKey *)v18);
        if ( v8 )
          Wallet::WalletDatabaseESE::HandleDatabaseCorruption(a2);
        v5 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, __int64, __int64, _QWORD))(**((_QWORD **)this + 13)
                                                                                          + 32LL))(
               *((_QWORD *)this + 13),
               (char *)this + 16,
               -1,
               129,
               212,
               0);
        if ( v5 >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, _QWORD, _QWORD, const char *))(**((_QWORD **)this + 13)
                                                                                                + 32LL))(
                 *((_QWORD *)this + 13),
                 (char *)this + 16,
                 -1,
                 0,
                 0,
                 a2);
          if ( v5 >= 0 )
          {
            v5 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, __int64, _QWORD, const char *))(**((_QWORD **)this + 13) + 32LL))(
                   *((_QWORD *)this + 13),
                   (char *)this + 16,
                   -1,
                   1,
                   0,
                   a2);
            if ( v5 >= 0 )
            {
              v5 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, __int64, _QWORD, const char *))(**((_QWORD **)this + 13) + 32LL))(
                     *((_QWORD *)this + 13),
                     (char *)this + 16,
                     -1,
                     2,
                     0,
                     a2);
              if ( v5 >= 0 )
              {
                v5 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, __int64, __int64, _QWORD))(**((_QWORD **)this + 13)
                                                                                                  + 32LL))(
                       *((_QWORD *)this + 13),
                       (char *)this + 16,
                       -1,
                       156,
                       1,
                       0);
                if ( v5 >= 0 )
                {
                  v5 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, __int64, __int64, _QWORD))(**((_QWORD **)this + 13) + 32LL))(
                         *((_QWORD *)this + 13),
                         (char *)this + 16,
                         -1,
                         77,
                         1,
                         0);
                  if ( v5 >= 0 )
                  {
                    v5 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, __int64, __int64, _QWORD))(**((_QWORD **)this + 13) + 32LL))(
                           *((_QWORD *)this + 13),
                           (char *)this + 16,
                           -1,
                           11,
                           128,
                           0);
                    if ( v5 >= 0 )
                    {
                      v5 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, __int64, __int64, _QWORD))(**((_QWORD **)this + 13) + 32LL))(
                             *((_QWORD *)this + 13),
                             (char *)this + 16,
                             -1,
                             18,
                             22,
                             0);
                      if ( v5 >= 0 )
                      {
                        v5 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, __int64, __int64, _QWORD))(**((_QWORD **)this + 13) + 32LL))(
                               *((_QWORD *)this + 13),
                               (char *)this + 16,
                               -1,
                               45,
                               1,
                               0);
                        if ( v5 >= 0 )
                        {
                          v5 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, __int64, __int64, _QWORD))(**((_QWORD **)this + 13) + 32LL))(
                                 *((_QWORD *)this + 13),
                                 (char *)this + 16,
                                 -1,
                                 54,
                                 1,
                                 0);
                          if ( v5 >= 0 )
                          {
                            v5 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 13) + 48LL))(
                                   *((_QWORD *)this + 13),
                                   (char *)this + 16);
                            if ( v5 >= 0 )
                            {
                              v9 = (_QWORD *)((char *)this + 24);
                              v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, _QWORD, _QWORD))(**((_QWORD **)this + 13) + 64LL))(
                                     *((_QWORD *)this + 13),
                                     *((_QWORD *)this + 2),
                                     (char *)this + 24,
                                     0,
                                     0);
                              if ( v5 >= 0 )
                              {
                                v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, __int64))(**((_QWORD **)this + 13)
                                                                                                 + 40LL))(
                                        *((_QWORD *)this + 13),
                                        *v9,
                                        v19,
                                        16);
                                v5 = v10;
                                if ( v10 == -1811 )
                                {
                                  v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, _QWORD, char *, _DWORD))(**((_QWORD **)this + 13) + 80LL))(
                                         *((_QWORD *)this + 13),
                                         *v9,
                                         v19,
                                         0,
                                         (char *)this + 32,
                                         0);
                                  if ( v5 < 0 )
                                    goto LABEL_47;
                                  v12 = 1;
                                  goto LABEL_34;
                                }
                                if ( v10 == 1415 )
                                {
                                  v4 = 1;
                                }
                                else
                                {
                                  if ( v10 == -1413 )
                                  {
                                    v5 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 13) + 32LL))(
                                           *((_QWORD *)this + 13),
                                           (char *)this + 16,
                                           -1,
                                           45,
                                           0,
                                           0);
                                    if ( v5 < 0 )
                                      goto LABEL_47;
                                    v5 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 13) + 32LL))(
                                           *((_QWORD *)this + 13),
                                           (char *)this + 16,
                                           -1,
                                           54,
                                           0,
                                           0);
                                    if ( v5 < 0 )
                                      goto LABEL_47;
                                    v4 = 1;
                                    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, _QWORD))(**((_QWORD **)this + 13) + 40LL))(
                                           *((_QWORD *)this + 13),
                                           *v9,
                                           v19,
                                           0);
                                    if ( v5 < 0 )
                                      goto LABEL_47;
                                  }
                                  if ( v5 < 0 )
                                    goto LABEL_47;
                                }
                                v12 = 0;
                                v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, _QWORD, char *, _DWORD))(**((_QWORD **)this + 13) + 128LL))(
                                       *((_QWORD *)this + 13),
                                       *v9,
                                       v19,
                                       0,
                                       (char *)this + 32,
                                       0);
                                if ( v5 >= 0 )
                                {
LABEL_34:
                                  for ( i = 0; i < 7; ++i )
                                  {
                                    v14 = (struct TableDefinition *)&qword_18006A2D0[7 * (int)i];
                                    if ( *(_DWORD *)v14 != 1 )
                                    {
                                      v5 = Wallet::WalletDatabaseESE::PrepareTable(this, v14);
                                      if ( v5 < 0 )
                                        goto LABEL_47;
                                    }
                                  }
                                  if ( v12 )
                                  {
                                    v5 = Wallet::WalletDatabaseESE::SetDatabaseVersionCurrent(v11);
                                  }
                                  else
                                  {
                                    v5 = Wallet::WalletDatabaseESE::HandleDataMigration(this, v4);
                                    if ( v5 >= 0
                                      && (unsigned int)WalletEncrypter::IsEncryptionKeyExpired(v15)
                                      && (int)Wallet::WalletDatabaseESE::ReEncrypt(
                                                this,
                                                (const struct PropertyMapping *const)qword_18004C770,
                                                0x23Cu,
                                                1,
                                                1,
                                                0) < 0 )
                                    {
                                      v5 = -107;
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_47:
  CloseHandle(v7);
  if ( (int)Wallet::WalletDatabaseESE::JetErrToHR(v5) < 0 )
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 13) + 56LL))(
      *((_QWORD *)this + 13),
      *((_QWORD *)this + 2),
      1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800102c0  mov     [rsp-8+arg_10], rbx
0x1800102c5  push    rbp
0x1800102c6  push    rsi
0x1800102c7  push    rdi
0x1800102c8  push    r12
0x1800102ca  push    r13
0x1800102cc  push    r14
0x1800102ce  push    r15
0x1800102d0  lea     rbp, [rsp-4A0h]
0x1800102d8  sub     rsp, 5A0h
0x1800102df  mov     rax, cs:__security_cookie
0x1800102e6  xor     rax, rsp
0x1800102e9  mov     [rbp+4D0h+var_40], rax
0x1800102f0  mov     r14, rdx
0x1800102f3  mov     rdi, rcx
0x1800102f6  xor     r15d, r15d
0x1800102f9  lea     rcx, [rbp+4D0h+var_45C]; void *
0x1800102fd  xor     edx, edx; Val
0x1800102ff  mov     dword ptr [rbp+4D0h+WideCharStr], r15d
0x180010303  mov     r8d, 204h; Size
0x180010309  mov     ebx, 0FFFFFF95h
0x18001030e  call    memset_0
0x180010313  lea     rax, [rbp+4D0h+WideCharStr]
0x180010317  mov     esi, 104h
0x18001031c  or      r12, 0FFFFFFFFFFFFFFFFh
0x180010320  mov     [rsp+5D0h+cchWideChar], esi; cchWideChar
0x180010324  mov     r9d, r12d; cbMultiByte
0x180010327  mov     [rsp+5D0h+lpWideCharStr], rax; lpWideCharStr
0x18001032c  mov     r8, r14; lpMultiByteStr
0x18001032f  xor     edx, edx; dwFlags
0x180010331  mov     ecx, 0FDE9h; CodePage
0x180010336  call    cs:__imp_MultiByteToWideChar
0x18001033c  test    eax, eax
0x18001033e  jz      loc_18001089B
0x180010344  mov     [rsp+5D0h+hTemplateFile], r15; hTemplateFile
0x180010349  lea     r8d, [rbx+6Ch]; dwShareMode
0x18001034d  mov     [rsp+5D0h+cchWideChar], 2000000h; dwFlagsAndAttributes
0x180010355  lea     rcx, [rbp+4D0h+WideCharStr]; lpFileName
0x180010359  xor     r9d, r9d; lpSecurityAttributes
0x18001035c  mov     dword ptr [rsp+5D0h+lpWideCharStr], 3; dwCreationDisposition
0x180010364  xor     edx, edx; dwDesiredAccess
0x180010366  call    cs:__imp_CreateFileW
0x18001036c  mov     r13, rax
0x18001036f  cmp     rax, r12
0x180010372  jz      loc_1800108A4
0x180010378  xor     r9d, r9d; dwFlags
0x18001037b  lea     rdx, [rbp+4D0h+szFilePath]; lpszFilePath
0x180010382  mov     r8d, esi; cchFilePath
0x180010385  mov     rcx, rax; hFile
0x180010388  call    cs:__imp_GetFinalPathNameByHandleW
0x18001038e  mov     edx, esi; cchPath
0x180010390  lea     rcx, [rbp+4D0h+szFilePath]; pszPath
0x180010397  call    cs:__imp_PathCchStripPrefix
0x18001039d  mov     edx, esi; cchPath
0x18001039f  lea     rcx, [rbp+4D0h+szFilePath]; pszPath
0x1800103a6  call    cs:__imp_PathCchAddBackslash
0x1800103ac  lea     rdx, [rbp+4D0h+szFilePath]; lpString2
0x1800103b3  lea     rcx, [rbp+4D0h+WideCharStr]; lpString1
0x1800103b7  call    cs:__imp_lstrcmpW
0x1800103bd  test    eax, eax
0x1800103bf  jnz     loc_1800108A4
0x1800103c5  mov     r9, r14
0x1800103c8  lea     r8, aSwalletDb; "%swallet.db"
0x1800103cf  mov     edx, esi; unsigned __int64
0x1800103d1  lea     rcx, [rsp+5D0h+var_570]; char *
0x1800103d6  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800103db  test    eax, eax
0x1800103dd  js      loc_180010894
0x1800103e3  mov     rcx, [rdi+68h]
0x1800103e7  lea     rsi, [rdi+10h]
0x1800103eb  xor     r8d, r8d
0x1800103ee  mov     rdx, rsi
0x1800103f1  mov     rax, [rcx]
0x1800103f4  mov     rax, [rax]
0x1800103f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103fc  mov     ebx, eax
0x1800103fe  test    eax, eax
0x180010400  js      loc_1800108A4
0x180010406  mov     r9d, 2001Fh; unsigned int
0x18001040c  mov     [rsp+5D0h+var_590], r15d
0x180010411  lea     r8, ?sc_szWalletRegKey@WalletDatabaseESE@Wallet@@0QBGB; "Software\\Microsoft\\Wallet"
0x180010418  mov     [rsp+5D0h+var_588], r15
0x18001041d  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180010424  mov     [rsp+5D0h+var_580], r15
0x180010429  lea     rcx, [rsp+5D0h+var_588]; this
0x18001042e  mov     [rsp+5D0h+var_578], r15
0x180010433  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180010438  test    eax, eax
0x18001043a  jnz     short loc_180010454
0x18001043c  lea     r8, [rsp+5D0h+var_590]; unsigned int *
0x180010441  lea     rdx, ?sc_szDatabaseCorruptRegValue@WalletDatabaseESE@Wallet@@0QBGB; "DatabaseCorrupt"
0x180010448  lea     rcx, [rsp+5D0h+var_588]; this
0x18001044d  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x180010452  jmp     short loc_18001045A
0x180010454  call    cs:__imp_GetLastError
0x18001045a  mov     ebx, [rsp+5D0h+var_590]
0x18001045e  lea     rcx, [rsp+5D0h+var_588]; this
0x180010463  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180010468  test    ebx, ebx
0x18001046a  jz      short loc_180010474
0x18001046c  mov     rcx, r14; char *
0x18001046f  call    ?HandleDatabaseCorruption@WalletDatabaseESE@Wallet@@CAJPEBD@Z; Wallet::WalletDatabaseESE::HandleDatabaseCorruption(char const *)
0x180010474  mov     rcx, [rdi+68h]
0x180010478  mov     r9d, 81h
0x18001047e  mov     qword ptr [rsp+5D0h+cchWideChar], r15
0x180010483  mov     r8, r12
0x180010486  mov     rdx, rsi
0x180010489  mov     [rsp+5D0h+lpWideCharStr], 0D4h
0x180010492  mov     rax, [rcx]
0x180010495  mov     rax, [rax+20h]
0x180010499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001049e  mov     ebx, eax
0x1800104a0  test    eax, eax
0x1800104a2  js      loc_1800108A4
0x1800104a8  mov     rcx, [rdi+68h]
0x1800104ac  xor     r9d, r9d
0x1800104af  mov     qword ptr [rsp+5D0h+cchWideChar], r14
0x1800104b4  mov     r8, r12
0x1800104b7  mov     rdx, rsi
0x1800104ba  mov     [rsp+5D0h+lpWideCharStr], r15
0x1800104bf  mov     rax, [rcx]
0x1800104c2  mov     rax, [rax+20h]
0x1800104c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104cb  mov     ebx, eax
0x1800104cd  test    eax, eax
0x1800104cf  js      loc_1800108A4
0x1800104d5  mov     rcx, [rdi+68h]
0x1800104d9  mov     r9d, 1
0x1800104df  mov     qword ptr [rsp+5D0h+cchWideChar], r14
0x1800104e4  mov     r8, r12
0x1800104e7  mov     rdx, rsi
0x1800104ea  mov     [rsp+5D0h+lpWideCharStr], r15
0x1800104ef  mov     rax, [rcx]
0x1800104f2  mov     rax, [rax+20h]
0x1800104f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104fb  mov     ebx, eax
0x1800104fd  test    eax, eax
0x1800104ff  js      loc_1800108A4
0x180010505  mov     rcx, [rdi+68h]
0x180010509  mov     r9d, 2
0x18001050f  mov     qword ptr [rsp+5D0h+cchWideChar], r14
0x180010514  mov     r8, r12
0x180010517  mov     rdx, rsi
0x18001051a  mov     [rsp+5D0h+lpWideCharStr], r15
0x18001051f  mov     rax, [rcx]
0x180010522  mov     rax, [rax+20h]
0x180010526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001052b  mov     ebx, eax
0x18001052d  test    eax, eax
0x18001052f  js      loc_1800108A4
0x180010535  mov     rcx, [rdi+68h]
0x180010539  mov     r9d, 9Ch
0x18001053f  mov     qword ptr [rsp+5D0h+cchWideChar], r15
0x180010544  mov     r8, r12
0x180010547  mov     rdx, rsi
0x18001054a  mov     [rsp+5D0h+lpWideCharStr], 1
0x180010553  mov     rax, [rcx]
0x180010556  mov     rax, [rax+20h]
0x18001055a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001055f  mov     ebx, eax
0x180010561  test    eax, eax
0x180010563  js      loc_1800108A4
0x180010569  mov     rcx, [rdi+68h]
0x18001056d  mov     r9d, 4Dh ; 'M'
0x180010573  mov     qword ptr [rsp+5D0h+cchWideChar], r15
0x180010578  mov     r8, r12
0x18001057b  mov     rdx, rsi
0x18001057e  mov     [rsp+5D0h+lpWideCharStr], 1
0x180010587  mov     rax, [rcx]
0x18001058a  mov     rax, [rax+20h]
0x18001058e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010593  mov     ebx, eax
0x180010595  test    eax, eax
0x180010597  js      loc_1800108A4
0x18001059d  mov     rcx, [rdi+68h]
0x1800105a1  mov     r9d, 0Bh
0x1800105a7  mov     qword ptr [rsp+5D0h+cchWideChar], r15
0x1800105ac  mov     r8, r12
0x1800105af  mov     rdx, rsi
0x1800105b2  mov     [rsp+5D0h+lpWideCharStr], 80h
0x1800105bb  mov     rax, [rcx]
0x1800105be  mov     rax, [rax+20h]
0x1800105c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105c7  mov     ebx, eax
0x1800105c9  test    eax, eax
0x1800105cb  js      loc_1800108A4
0x1800105d1  mov     rcx, [rdi+68h]
0x1800105d5  mov     r9d, 12h
0x1800105db  mov     qword ptr [rsp+5D0h+cchWideChar], r15
0x1800105e0  mov     r8, r12
0x1800105e3  mov     rdx, rsi
0x1800105e6  mov     [rsp+5D0h+lpWideCharStr], 16h
0x1800105ef  mov     rax, [rcx]
0x1800105f2  mov     rax, [rax+20h]
0x1800105f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105fb  mov     ebx, eax
0x1800105fd  test    eax, eax
0x1800105ff  js      loc_1800108A4
0x180010605  mov     rcx, [rdi+68h]
0x180010609  mov     r14d, 2Dh ; '-'
0x18001060f  mov     qword ptr [rsp+5D0h+cchWideChar], r15
0x180010614  mov     r9d, r14d
0x180010617  mov     r8, r12
0x18001061a  mov     [rsp+5D0h+lpWideCharStr], 1
0x180010623  mov     rdx, rsi
0x180010626  mov     rax, [rcx]
0x180010629  mov     rax, [rax+20h]
0x18001062d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010632  mov     ebx, eax
0x180010634  test    eax, eax
0x180010636  js      loc_1800108A4
0x18001063c  mov     rcx, [rdi+68h]
0x180010640  lea     r9d, [r14+9]
0x180010644  mov     qword ptr [rsp+5D0h+cchWideChar], r15
0x180010649  mov     r8, r12
0x18001064c  mov     rdx, rsi
0x18001064f  mov     [rsp+5D0h+lpWideCharStr], 1
0x180010658  mov     rax, [rcx]
0x18001065b  mov     rax, [rax+20h]
0x18001065f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010664  mov     ebx, eax
0x180010666  test    eax, eax
0x180010668  js      loc_1800108A4
0x18001066e  mov     rcx, [rdi+68h]
0x180010672  mov     rdx, rsi
0x180010675  mov     rax, [rcx]
0x180010678  mov     rax, [rax+30h]
0x18001067c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010681  mov     ebx, eax
0x180010683  test    eax, eax
0x180010685  js      loc_1800108A4
0x18001068b  mov     rcx, [rdi+68h]
0x18001068f  lea     r12, [rdi+18h]
0x180010693  mov     rdx, [rsi]
0x180010696  xor     r9d, r9d
0x180010699  mov     r8, r12
0x18001069c  mov     [rsp+5D0h+lpWideCharStr], r15
0x1800106a1  mov     rax, [rcx]
0x1800106a4  mov     rax, [rax+40h]
0x1800106a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106ad  mov     ebx, eax
0x1800106af  test    eax, eax
0x1800106b1  js      loc_1800108A4
0x1800106b7  mov     rcx, [rdi+68h]
0x1800106bb  lea     r9d, [r14-1Dh]
0x1800106bf  mov     rdx, [r12]
0x1800106c3  lea     r8, [rsp+5D0h+var_570]
0x1800106c8  mov     rax, [rcx]
0x1800106cb  mov     rax, [rax+28h]
0x1800106cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106d4  mov     ebx, eax
0x1800106d6  cmp     eax, 0FFFFF8EDh
0x1800106db  jnz     short loc_18001071C
0x1800106dd  mov     rcx, [rdi+68h]
0x1800106e1  lea     rdx, [rdi+20h]
0x1800106e5  mov     [rsp+5D0h+cchWideChar], r15d
0x1800106ea  lea     r8, [rsp+5D0h+var_570]
0x1800106ef  mov     [rsp+5D0h+lpWideCharStr], rdx
0x1800106f4  xor     r9d, r9d
0x1800106f7  mov     rdx, [r12]
0x1800106fb  mov     rax, [rcx]
0x1800106fe  mov     rax, [rax+50h]
0x180010702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010707  mov     ebx, eax
0x180010709  test    eax, eax
0x18001070b  js      loc_1800108A4
0x180010711  mov     r14d, 1
0x180010717  jmp     loc_180010804
0x18001071c  cmp     eax, 587h
0x180010721  jnz     short loc_18001072E
0x180010723  mov     r15d, 1
0x180010729  jmp     loc_1800107CA
0x18001072e  cmp     eax, 0FFFFFA7Bh
0x180010733  jnz     loc_1800107C2
0x180010739  mov     rcx, [rdi+68h]
0x18001073d  mov     r9d, r14d
0x180010740  or      r14, 0FFFFFFFFFFFFFFFFh
0x180010744  mov     qword ptr [rsp+5D0h+cchWideChar], r15
0x180010749  mov     r8, r14
0x18001074c  mov     [rsp+5D0h+lpWideCharStr], r15
0x180010751  mov     rdx, rsi
0x180010754  mov     rax, [rcx]
0x180010757  mov     rax, [rax+20h]
0x18001075b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010760  mov     ebx, eax
0x180010762  test    eax, eax
0x180010764  js      loc_1800108A4
0x18001076a  mov     rcx, [rdi+68h]
0x18001076e  lea     r9d, [r14+37h]
0x180010772  mov     qword ptr [rsp+5D0h+cchWideChar], r15
0x180010777  mov     r8, r14
0x18001077a  mov     rdx, rsi
0x18001077d  mov     [rsp+5D0h+lpWideCharStr], r15
0x180010782  mov     rax, [rcx]
0x180010785  mov     rax, [rax+20h]
0x180010789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001078e  mov     ebx, eax
0x180010790  test    eax, eax
0x180010792  js      loc_1800108A4
0x180010798  mov     rcx, [rdi+68h]
  ... truncated ...
```
