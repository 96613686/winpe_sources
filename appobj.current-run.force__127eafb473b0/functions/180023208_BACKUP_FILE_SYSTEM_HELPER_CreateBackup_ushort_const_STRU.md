# BACKUP_FILE_SYSTEM_HELPER::CreateBackup(ushort const *,STRU *)

- ea: `0x180023208`
- end: `0x18002346b`
- name: `?CreateBackup@BACKUP_FILE_SYSTEM_HELPER@@SAJPEBGPEAVSTRU@@@Z`
- size: `611`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct STRU *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180022a9c`

## callees

- `0x180001ed0`
- `0x180001fb0`
- `0x180002640`
- `0x180022f88`
- `0x180023208`
- `0x180023474`
- `0x180024480`
- `0x180024a98`
- `0x180033bc4`
- `0x180034d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800232b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800232b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023406`
- `api-ms-win-core-kernel32-legacy-l1-1-3!CreateDirectoryTransactedW` at `0x180023358`
- `api-ms-win-core-kernel32-legacy-l1-1-3!CreateDirectoryTransactedW` at `0x180023358`
- `ktmw32!CommitTransaction` at `0x1800233fc`
- `ktmw32!CommitTransaction` at `0x1800233fc`
- `ktmw32!CreateTransaction` at `0x1800232a6`
- `ktmw32!CreateTransaction` at `0x1800232a6`
- `ktmw32!RollbackTransaction` at `0x18002341e`
- `ktmw32!RollbackTransaction` at `0x18002341e`

## pseudocode

```c
__int64 __fastcall BACKUP_FILE_SYSTEM_HELPER::CreateBackup(const unsigned __int16 *a1, struct STRU *this)
{
  HANDLE Transaction; // rax
  void *v5; // r14
  signed int LastError; // eax
  signed int BackupStorageDirectoryTransacted; // ebx
  const unsigned __int16 *v8; // rdi
  __int64 i; // rcx
  __int64 v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rax
  signed int v13; // eax
  _QWORD v15[4]; // [rsp+40h] [rbp-79h] BYREF
  LPCWSTR lpNewDirectory; // [rsp+60h] [rbp-59h]
  int v17; // [rsp+68h] [rbp-51h]
  __int16 v18; // [rsp+6Ch] [rbp-4Dh]
  int v19; // [rsp+70h] [rbp-49h]
  _BYTE v20[32]; // [rsp+78h] [rbp-41h] BYREF
  unsigned __int64 v21; // [rsp+98h] [rbp-21h]
  _BYTE v22[32]; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v23; // [rsp+D0h] [rbp+17h]

  v17 = 32;
  v18 = 256;
  v15[0] = 0;
  lpNewDirectory = (LPCWSTR)v15;
  v19 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v22);
  MULTISZ::MULTISZ((MULTISZ *)v20);
  if ( !a1 || !*a1 || !this || *((_DWORD *)this + 12) )
  {
    BackupStorageDirectoryTransacted = -2147024809;
    goto LABEL_29;
  }
  Transaction = CreateTransaction(0, 0, 1u, 0, 0, 0, 0);
  v5 = Transaction;
  if ( Transaction == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    BackupStorageDirectoryTransacted = LastError;
    if ( LastError > 0 )
      BackupStorageDirectoryTransacted = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_29;
  }
  BackupStorageDirectoryTransacted = BACKUP_FILE_SYSTEM_HELPER::CreateBackupStorageDirectoryTransacted(Transaction);
  if ( (int)(BackupStorageDirectoryTransacted + 0x80000000) >= 0 && BackupStorageDirectoryTransacted != -2147024713 )
    goto LABEL_27;
  BackupStorageDirectoryTransacted = BACKUP_FILE_SYSTEM_HELPER::GetAppcmdBackupStoragePath(this);
  if ( BackupStorageDirectoryTransacted < 0 )
    goto LABEL_27;
  BackupStorageDirectoryTransacted = STRU::Append(this, L"\\");
  if ( BackupStorageDirectoryTransacted < 0 )
    goto LABEL_27;
  BackupStorageDirectoryTransacted = STRU::Append(this, a1);
  if ( BackupStorageDirectoryTransacted < 0 )
    goto LABEL_27;
  BackupStorageDirectoryTransacted = MakePathCanonicalizationProof(
                                       *((const unsigned __int16 **)this + 4),
                                       (struct STRU *)v15);
  if ( BackupStorageDirectoryTransacted < 0 )
    goto LABEL_27;
  if ( !CreateDirectoryTransactedW(0, lpNewDirectory, 0, v5) )
  {
LABEL_25:
    v13 = GetLastError();
    BackupStorageDirectoryTransacted = v13;
    if ( v13 > 0 )
      BackupStorageDirectoryTransacted = (unsigned __int16)v13 | 0x80070000;
    goto LABEL_27;
  }
  BackupStorageDirectoryTransacted = BACKUP_FILE_SYSTEM_HELPER::GetConfigFilePathsListing(
                                       *((_QWORD *)this + 4),
                                       1,
                                       v20,
                                       v22);
  if ( BackupStorageDirectoryTransacted < 0 )
  {
LABEL_27:
    RollbackTransaction(v5);
    goto LABEL_29;
  }
  v8 = (const unsigned __int16 *)(v21 & -(__int64)(*(_WORD *)v21 != 0));
  for ( i = v23; ; i = v10 + 2 + 2 * v12 )
  {
    v10 = i & -(__int64)(*(_WORD *)i != 0);
    if ( !v8 )
      break;
    BackupStorageDirectoryTransacted = BACKUP_FILE_SYSTEM_HELPER::CopyConfigFileTransacted(
                                         (const unsigned __int16 *)(i & -(__int64)(*(_WORD *)i != 0)),
                                         v8,
                                         v5);
    if ( BackupStorageDirectoryTransacted < 0 )
      goto LABEL_27;
    v11 = -1;
    do
      ++v11;
    while ( v8[v11] );
    v8 = (const unsigned __int16 *)((unsigned __int64)&v8[v11 + 1] & -(__int64)(v8[v11 + 1] != 0));
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(v10 + 2 * v12) );
  }
  if ( !CommitTransaction(v5) )
    goto LABEL_25;
LABEL_29:
  BUFFER::~BUFFER((BUFFER *)v20);
  BUFFER::~BUFFER((BUFFER *)v22);
  BUFFER::~BUFFER((BUFFER *)v15);
  return (unsigned int)BackupStorageDirectoryTransacted;
}

```

## disassembly

```asm
0x180023208  mov     [rsp-8+arg_10], rbx
0x18002320d  push    rbp
0x18002320e  push    rsi
0x18002320f  push    rdi
0x180023210  push    r14
0x180023212  push    r15
0x180023214  lea     rbp, [rsp-37h]
0x180023219  sub     rsp, 0F0h
0x180023220  mov     rax, cs:__security_cookie
0x180023227  xor     rax, rsp
0x18002322a  mov     [rbp+57h+var_28], rax
0x18002322e  mov     rsi, rcx
0x180023231  mov     [rbp+57h+var_A8], 20h ; ' '
0x180023238  xor     r15d, r15d
0x18002323b  mov     [rbp+57h+var_A4], 100h
0x180023241  lea     rax, [rbp+57h+var_D0]
0x180023245  mov     [rbp+57h+var_D0], r15
0x180023249  lea     rcx, [rbp+57h+var_60]; this
0x18002324d  mov     [rbp+57h+lpNewDirectory], rax
0x180023251  mov     [rbp+57h+var_A0], r15d
0x180023255  mov     rdi, rdx
0x180023258  call    ??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18002325d  lea     rcx, [rbp+57h+var_98]; this
0x180023261  call    ??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180023266  test    rsi, rsi
0x180023269  jz      loc_180023426
0x18002326f  cmp     [rsi], r15w
0x180023273  jz      loc_180023426
0x180023279  test    rdi, rdi
0x18002327c  jz      loc_180023426
0x180023282  cmp     [rdi+30h], r15d
0x180023286  jnz     loc_180023426
0x18002328c  mov     [rsp+110h+Description], r15; Description
0x180023291  lea     r8d, [r15+1]; CreateOptions
0x180023295  mov     [rsp+110h+Timeout], r15d; Timeout
0x18002329a  xor     r9d, r9d; IsolationLevel
0x18002329d  xor     edx, edx; UOW
0x18002329f  mov     [rsp+110h+IsolationFlags], r15d; IsolationFlags
0x1800232a4  xor     ecx, ecx; lpTransactionAttributes
0x1800232a6  call    cs:__imp_CreateTransaction
0x1800232ac  mov     r14, rax
0x1800232af  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800232b3  jnz     short loc_1800232D3
0x1800232b5  call    cs:__imp_GetLastError
0x1800232bb  mov     ebx, eax
0x1800232bd  test    eax, eax
0x1800232bf  jle     loc_18002342B
0x1800232c5  movzx   ebx, ax
0x1800232c8  or      ebx, 80070000h
0x1800232ce  jmp     loc_18002342B
0x1800232d3  mov     rcx, r14; hTransaction
0x1800232d6  call    ?CreateBackupStorageDirectoryTransacted@BACKUP_FILE_SYSTEM_HELPER@@CAJPEAX@Z; BACKUP_FILE_SYSTEM_HELPER::CreateBackupStorageDirectoryTransacted(void *)
0x1800232db  mov     ebx, eax
0x1800232dd  mov     eax, 80000000h
0x1800232e2  lea     ecx, [rbx+rax]
0x1800232e5  test    eax, ecx
0x1800232e7  jnz     short loc_1800232F5
0x1800232e9  cmp     ebx, 800700B7h
0x1800232ef  jnz     loc_18002341B
0x1800232f5  mov     rcx, rdi; this
0x1800232f8  call    ?GetAppcmdBackupStoragePath@BACKUP_FILE_SYSTEM_HELPER@@CAJPEAVSTRU@@@Z; BACKUP_FILE_SYSTEM_HELPER::GetAppcmdBackupStoragePath(STRU *)
0x1800232fd  mov     ebx, eax
0x1800232ff  test    eax, eax
0x180023301  js      loc_18002341B
0x180023307  lea     rdx, asc_180039420; "\\"
0x18002330e  mov     rcx, rdi; this
0x180023311  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180023316  mov     ebx, eax
0x180023318  test    eax, eax
0x18002331a  js      loc_18002341B
0x180023320  mov     rdx, rsi; unsigned __int16 *
0x180023323  mov     rcx, rdi; this
0x180023326  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002332b  mov     ebx, eax
0x18002332d  test    eax, eax
0x18002332f  js      loc_18002341B
0x180023335  mov     rcx, [rdi+20h]; unsigned __int16 *
0x180023339  lea     rdx, [rbp+57h+var_D0]; this
0x18002333d  call    ?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x180023342  mov     ebx, eax
0x180023344  test    eax, eax
0x180023346  js      loc_18002341B
0x18002334c  mov     rdx, [rbp+57h+lpNewDirectory]; lpNewDirectory
0x180023350  mov     r9, r14; hTransaction
0x180023353  xor     r8d, r8d; lpSecurityAttributes
0x180023356  xor     ecx, ecx; lpTemplateDirectory
0x180023358  call    cs:__imp_CreateDirectoryTransactedW
0x18002335e  test    eax, eax
0x180023360  jz      loc_180023406
0x180023366  mov     rcx, [rdi+20h]
0x18002336a  lea     r9, [rbp+57h+var_60]
0x18002336e  lea     r8, [rbp+57h+var_98]
0x180023372  mov     edx, 1
0x180023377  call    ?GetConfigFilePathsListing@BACKUP_FILE_SYSTEM_HELPER@@CAJPEBGW4ConfigFilePathListingMode@1@PEAVMULTISZ@@2@Z; BACKUP_FILE_SYSTEM_HELPER::GetConfigFilePathsListing(ushort const *,BACKUP_FILE_SYSTEM_HELPER::ConfigFilePathListingMode,MULTISZ *,MULTISZ *)
0x18002337c  mov     ebx, eax
0x18002337e  test    eax, eax
0x180023380  js      loc_18002341B
0x180023386  mov     rcx, [rbp+57h+var_78]
0x18002338a  movzx   eax, word ptr [rcx]
0x18002338d  neg     ax
0x180023390  sbb     rdi, rdi
0x180023393  and     rdi, rcx
0x180023396  mov     rcx, [rbp+57h+var_40]
0x18002339a  movzx   eax, word ptr [rcx]
0x18002339d  neg     ax
0x1800233a0  sbb     rsi, rsi
0x1800233a3  and     rsi, rcx
0x1800233a6  test    rdi, rdi
0x1800233a9  jz      short loc_1800233F9
0x1800233ab  mov     r8, r14; void *
0x1800233ae  mov     rdx, rdi; unsigned __int16 *
0x1800233b1  mov     rcx, rsi; unsigned __int16 *
0x1800233b4  call    ?CopyConfigFileTransacted@BACKUP_FILE_SYSTEM_HELPER@@CAJPEBG0PEAX@Z; BACKUP_FILE_SYSTEM_HELPER::CopyConfigFileTransacted(ushort const *,ushort const *,void *)
0x1800233b9  mov     ebx, eax
0x1800233bb  test    eax, eax
0x1800233bd  js      short loc_18002341B
0x1800233bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800233c3  inc     rax
0x1800233c6  cmp     [rdi+rax*2], r15w
0x1800233cb  jnz     short loc_1800233C3
0x1800233cd  lea     rcx, [rdi+2]
0x1800233d1  lea     rcx, [rcx+rax*2]
0x1800233d5  movzx   eax, word ptr [rcx]
0x1800233d8  neg     ax
0x1800233db  sbb     rdi, rdi
0x1800233de  and     rdi, rcx
0x1800233e1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800233e5  inc     rax
0x1800233e8  cmp     [rsi+rax*2], r15w
0x1800233ed  jnz     short loc_1800233E5
0x1800233ef  lea     rcx, [rsi+2]
0x1800233f3  lea     rcx, [rcx+rax*2]
0x1800233f7  jmp     short loc_18002339A
0x1800233f9  mov     rcx, r14; TransactionHandle
0x1800233fc  call    cs:__imp_CommitTransaction
0x180023402  test    eax, eax
0x180023404  jnz     short loc_18002342B
0x180023406  call    cs:__imp_GetLastError
0x18002340c  mov     ebx, eax
0x18002340e  test    eax, eax
0x180023410  jle     short loc_18002341B
0x180023412  movzx   ebx, ax
0x180023415  or      ebx, 80070000h
0x18002341b  mov     rcx, r14; TransactionHandle
0x18002341e  call    cs:__imp_RollbackTransaction
0x180023424  jmp     short loc_18002342B
0x180023426  mov     ebx, 80070057h
0x18002342b  lea     rcx, [rbp+57h+var_98]; this
0x18002342f  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180023434  lea     rcx, [rbp+57h+var_60]; this
0x180023438  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002343d  lea     rcx, [rbp+57h+var_D0]; this
0x180023441  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180023446  mov     eax, ebx
0x180023448  mov     rcx, [rbp+57h+var_28]
0x18002344c  xor     rcx, rsp; StackCookie
0x18002344f  call    __security_check_cookie
0x180023454  mov     rbx, [rsp+110h+arg_10]
0x18002345c  add     rsp, 0F0h
0x180023463  pop     r15
0x180023465  pop     r14
0x180023467  pop     rdi
0x180023468  pop     rsi
0x180023469  pop     rbp
0x18002346a  retn
```
