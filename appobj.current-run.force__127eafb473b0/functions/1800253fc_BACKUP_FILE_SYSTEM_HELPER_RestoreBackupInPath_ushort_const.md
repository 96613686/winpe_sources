# BACKUP_FILE_SYSTEM_HELPER::RestoreBackupInPath(ushort const *)

- ea: `0x1800253fc`
- end: `0x18002559e`
- name: `?RestoreBackupInPath@BACKUP_FILE_SYSTEM_HELPER@@SAJPEBG@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180025170`

## callees

- `0x180001ed0`
- `0x180001fb0`
- `0x180022f88`
- `0x180024a98`
- `0x1800253fc`
- `0x180034d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025542`
- `ktmw32!CommitTransaction` at `0x180025538`
- `ktmw32!CommitTransaction` at `0x180025538`
- `ktmw32!CreateTransaction` at `0x180025466`
- `ktmw32!CreateTransaction` at `0x180025466`
- `ktmw32!RollbackTransaction` at `0x18002555a`
- `ktmw32!RollbackTransaction` at `0x18002555a`

## pseudocode

```c
__int64 __fastcall BACKUP_FILE_SYSTEM_HELPER::RestoreBackupInPath(const unsigned __int16 *a1)
{
  signed int ConfigFilePathsListing; // ebx
  HANDLE Transaction; // rbp
  signed int LastError; // eax
  const unsigned __int16 *v5; // rdi
  const unsigned __int16 *v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rax
  signed int v9; // eax
  _BYTE v11[32]; // [rsp+40h] [rbp-98h] BYREF
  unsigned __int64 v12; // [rsp+60h] [rbp-78h]
  _BYTE v13[32]; // [rsp+78h] [rbp-60h] BYREF
  unsigned __int64 v14; // [rsp+98h] [rbp-40h]

  MULTISZ::MULTISZ((MULTISZ *)v13);
  MULTISZ::MULTISZ((MULTISZ *)v11);
  if ( !a1 )
  {
    ConfigFilePathsListing = -2147024809;
    goto LABEL_19;
  }
  Transaction = CreateTransaction(0, 0, 1u, 0, 0, 0, 0);
  if ( Transaction == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    ConfigFilePathsListing = LastError;
    if ( LastError > 0 )
      ConfigFilePathsListing = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_19;
  }
  ConfigFilePathsListing = BACKUP_FILE_SYSTEM_HELPER::GetConfigFilePathsListing(a1, 0, v13, v11);
  if ( ConfigFilePathsListing < 0 )
  {
LABEL_18:
    RollbackTransaction(Transaction);
    goto LABEL_19;
  }
  v5 = (const unsigned __int16 *)(v14 & -(__int64)(*(_WORD *)v14 != 0));
  v6 = (const unsigned __int16 *)(v12 & -(__int64)(*(_WORD *)v12 != 0));
  while ( v5 )
  {
    ConfigFilePathsListing = BACKUP_FILE_SYSTEM_HELPER::CopyConfigFileTransacted(v5, v6, Transaction);
    if ( ConfigFilePathsListing < 0 )
      goto LABEL_18;
    v7 = -1;
    do
      ++v7;
    while ( v5[v7] );
    v5 = (const unsigned __int16 *)((unsigned __int64)&v5[v7 + 1] & -(__int64)(v5[v7 + 1] != 0));
    v8 = -1;
    do
      ++v8;
    while ( v6[v8] );
    v6 = (const unsigned __int16 *)((unsigned __int64)&v6[v8 + 1] & -(__int64)(v6[v8 + 1] != 0));
  }
  if ( !CommitTransaction(Transaction) )
  {
    v9 = GetLastError();
    ConfigFilePathsListing = v9;
    if ( v9 > 0 )
      ConfigFilePathsListing = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_18;
  }
LABEL_19:
  BUFFER::~BUFFER((BUFFER *)v11);
  BUFFER::~BUFFER((BUFFER *)v13);
  return (unsigned int)ConfigFilePathsListing;
}

```

## disassembly

```asm
0x1800253fc  mov     [rsp+arg_8], rbx
0x180025401  mov     [rsp+arg_10], rbp
0x180025406  push    rsi
0x180025407  push    rdi
0x180025408  push    r14
0x18002540a  sub     rsp, 0C0h
0x180025411  mov     rax, cs:__security_cookie
0x180025418  xor     rax, rsp
0x18002541b  mov     [rsp+0D8h+var_28], rax
0x180025423  mov     rbx, rcx
0x180025426  lea     rcx, [rsp+0D8h+var_60]; this
0x18002542b  call    ??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180025430  lea     rcx, [rsp+0D8h+var_98]; this
0x180025435  call    ??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18002543a  xor     r14d, r14d
0x18002543d  test    rbx, rbx
0x180025440  jnz     short loc_18002544C
0x180025442  mov     ebx, 80070057h
0x180025447  jmp     loc_180025560
0x18002544c  xor     r9d, r9d; IsolationLevel
0x18002544f  mov     [rsp+0D8h+Description], r14; Description
0x180025454  mov     [rsp+0D8h+Timeout], r14d; Timeout
0x180025459  xor     edx, edx; UOW
0x18002545b  xor     ecx, ecx; lpTransactionAttributes
0x18002545d  mov     [rsp+0D8h+IsolationFlags], r14d; IsolationFlags
0x180025462  lea     r8d, [r9+1]; CreateOptions
0x180025466  call    cs:__imp_CreateTransaction
0x18002546c  mov     rbp, rax
0x18002546f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025473  jnz     short loc_180025493
0x180025475  call    cs:__imp_GetLastError
0x18002547b  mov     ebx, eax
0x18002547d  test    eax, eax
0x18002547f  jle     loc_180025560
0x180025485  movzx   ebx, ax
0x180025488  or      ebx, 80070000h
0x18002548e  jmp     loc_180025560
0x180025493  lea     r9, [rsp+0D8h+var_98]
0x180025498  xor     edx, edx
0x18002549a  lea     r8, [rsp+0D8h+var_60]
0x18002549f  mov     rcx, rbx
0x1800254a2  call    ?GetConfigFilePathsListing@BACKUP_FILE_SYSTEM_HELPER@@CAJPEBGW4ConfigFilePathListingMode@1@PEAVMULTISZ@@2@Z; BACKUP_FILE_SYSTEM_HELPER::GetConfigFilePathsListing(ushort const *,BACKUP_FILE_SYSTEM_HELPER::ConfigFilePathListingMode,MULTISZ *,MULTISZ *)
0x1800254a7  mov     ebx, eax
0x1800254a9  test    eax, eax
0x1800254ab  js      loc_180025557
0x1800254b1  mov     rdx, [rsp+0D8h+var_40]
0x1800254b9  movzx   ecx, word ptr [rdx]
0x1800254bc  neg     cx
0x1800254bf  sbb     rdi, rdi
0x1800254c2  and     rdi, rdx
0x1800254c5  mov     rdx, [rsp+0D8h+var_78]
0x1800254ca  movzx   ecx, word ptr [rdx]
0x1800254cd  neg     cx
0x1800254d0  sbb     rsi, rsi
0x1800254d3  and     rsi, rdx
0x1800254d6  test    rdi, rdi
0x1800254d9  jz      short loc_180025535
0x1800254db  mov     r8, rbp; void *
0x1800254de  mov     rdx, rsi; unsigned __int16 *
0x1800254e1  mov     rcx, rdi; unsigned __int16 *
0x1800254e4  call    ?CopyConfigFileTransacted@BACKUP_FILE_SYSTEM_HELPER@@CAJPEBG0PEAX@Z; BACKUP_FILE_SYSTEM_HELPER::CopyConfigFileTransacted(ushort const *,ushort const *,void *)
0x1800254e9  mov     ebx, eax
0x1800254eb  test    eax, eax
0x1800254ed  js      short loc_180025557
0x1800254ef  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800254f3  inc     rax
0x1800254f6  cmp     [rdi+rax*2], r14w
0x1800254fb  jnz     short loc_1800254F3
0x1800254fd  lea     rcx, [rdi+2]
0x180025501  lea     rcx, [rcx+rax*2]
0x180025505  movzx   eax, word ptr [rcx]
0x180025508  neg     ax
0x18002550b  sbb     rdi, rdi
0x18002550e  and     rdi, rcx
0x180025511  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025515  inc     rax
0x180025518  cmp     [rsi+rax*2], r14w
0x18002551d  jnz     short loc_180025515
0x18002551f  lea     rcx, [rsi+2]
0x180025523  lea     rcx, [rcx+rax*2]
0x180025527  movzx   eax, word ptr [rcx]
0x18002552a  neg     ax
0x18002552d  sbb     rsi, rsi
0x180025530  and     rsi, rcx
0x180025533  jmp     short loc_1800254D6
0x180025535  mov     rcx, rbp; TransactionHandle
0x180025538  call    cs:__imp_CommitTransaction
0x18002553e  test    eax, eax
0x180025540  jnz     short loc_180025560
0x180025542  call    cs:__imp_GetLastError
0x180025548  mov     ebx, eax
0x18002554a  test    eax, eax
0x18002554c  jle     short loc_180025557
0x18002554e  movzx   ebx, ax
0x180025551  or      ebx, 80070000h
0x180025557  mov     rcx, rbp; TransactionHandle
0x18002555a  call    cs:__imp_RollbackTransaction
0x180025560  lea     rcx, [rsp+0D8h+var_98]; this
0x180025565  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002556a  lea     rcx, [rsp+0D8h+var_60]; this
0x18002556f  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180025574  mov     eax, ebx
0x180025576  mov     rcx, [rsp+0D8h+var_28]
0x18002557e  xor     rcx, rsp; StackCookie
0x180025581  call    __security_check_cookie
0x180025586  lea     r11, [rsp+0D8h+var_18]
0x18002558e  mov     rbx, [r11+28h]
0x180025592  mov     rbp, [r11+30h]
0x180025596  mov     rsp, r11
0x180025599  pop     r14
0x18002559b  pop     rdi
0x18002559c  pop     rsi
0x18002559d  retn
```
