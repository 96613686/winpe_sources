# BACKUP_FILE_SYSTEM_HELPER::DeleteBackupInPath(ushort const *)

- ea: `0x180023d04`
- end: `0x180023daf`
- name: `?DeleteBackupInPath@BACKUP_FILE_SYSTEM_HELPER@@SAJPEBG@Z`
- size: `171`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180023ba8`

## callees

- `0x180023d04`
- `0x180023db8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d84`
- `ktmw32!CommitTransaction` at `0x180023d7a`
- `ktmw32!CommitTransaction` at `0x180023d7a`
- `ktmw32!CreateTransaction` at `0x180023d44`
- `ktmw32!CreateTransaction` at `0x180023d44`
- `ktmw32!RollbackTransaction` at `0x180023d9c`
- `ktmw32!RollbackTransaction` at `0x180023d9c`

## pseudocode

```c
__int64 __fastcall BACKUP_FILE_SYSTEM_HELPER::DeleteBackupInPath(const unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  HANDLE Transaction; // rax
  void *v4; // rdi
  signed int LastError; // eax
  signed int v6; // eax

  if ( a1 )
  {
    Transaction = CreateTransaction(0, 0, 1u, 0, 0, 0, 0);
    v4 = Transaction;
    if ( Transaction == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v2 = BACKUP_FILE_SYSTEM_HELPER::DeleteDirectoryTreeTransacted(a1, Transaction);
      if ( !CommitTransaction(v4) )
      {
        v6 = GetLastError();
        v2 = v6;
        if ( v6 > 0 )
          v2 = (unsigned __int16)v6 | 0x80070000;
        RollbackTransaction(v4);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v2;
}

```

## disassembly

```asm
0x180023d04  mov     [rsp+arg_0], rbx
0x180023d09  push    rdi
0x180023d0a  sub     rsp, 40h
0x180023d0e  mov     rbx, rcx
0x180023d11  test    rcx, rcx
0x180023d14  jnz     short loc_180023D20
0x180023d16  mov     ebx, 80070057h
0x180023d1b  jmp     loc_180023DA2
0x180023d20  xor     r9d, r9d; IsolationLevel
0x180023d23  mov     [rsp+48h+Description], 0; Description
0x180023d2c  mov     [rsp+48h+Timeout], 0; Timeout
0x180023d34  xor     edx, edx; UOW
0x180023d36  xor     ecx, ecx; lpTransactionAttributes
0x180023d38  mov     [rsp+48h+IsolationFlags], 0; IsolationFlags
0x180023d40  lea     r8d, [r9+1]; CreateOptions
0x180023d44  call    cs:__imp_CreateTransaction
0x180023d4a  mov     rdi, rax
0x180023d4d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023d51  jnz     short loc_180023D6A
0x180023d53  call    cs:__imp_GetLastError
0x180023d59  mov     ebx, eax
0x180023d5b  test    eax, eax
0x180023d5d  jle     short loc_180023DA2
0x180023d5f  movzx   ebx, ax
0x180023d62  or      ebx, 80070000h
0x180023d68  jmp     short loc_180023DA2
0x180023d6a  mov     rdx, rdi; void *
0x180023d6d  mov     rcx, rbx; unsigned __int16 *
0x180023d70  call    ?DeleteDirectoryTreeTransacted@BACKUP_FILE_SYSTEM_HELPER@@CAJPEBGPEAX@Z; BACKUP_FILE_SYSTEM_HELPER::DeleteDirectoryTreeTransacted(ushort const *,void *)
0x180023d75  mov     rcx, rdi; TransactionHandle
0x180023d78  mov     ebx, eax
0x180023d7a  call    cs:__imp_CommitTransaction
0x180023d80  test    eax, eax
0x180023d82  jnz     short loc_180023DA2
0x180023d84  call    cs:__imp_GetLastError
0x180023d8a  mov     ebx, eax
0x180023d8c  test    eax, eax
0x180023d8e  jle     short loc_180023D99
0x180023d90  movzx   ebx, ax
0x180023d93  or      ebx, 80070000h
0x180023d99  mov     rcx, rdi; TransactionHandle
0x180023d9c  call    cs:__imp_RollbackTransaction
0x180023da2  mov     eax, ebx
0x180023da4  mov     rbx, [rsp+48h+arg_0]
0x180023da9  add     rsp, 40h
0x180023dad  pop     rdi
0x180023dae  retn
```
