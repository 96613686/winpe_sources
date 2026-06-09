# TextLogQueueLogFileBackup

- ea: `0x14000dbc0`
- end: `0x14000dc5d`
- name: `TextLogQueueLogFileBackup`
- size: `157`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000ebf4`

## callees

- `0x14000d530`
- `0x14000dbc0`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dc0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dc0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000dc2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000dc2a`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14000dc05`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14000dc05`

## pseudocode

```c
__int64 __fastcall TextLogQueueLogFileBackup(unsigned __int16 *lpExistingFileName)
{
  unsigned int v2; // edi
  DWORD LastError; // ebx
  WCHAR NewFileName[264]; // [rsp+30h] [rbp-228h] BYREF

  v2 = 0;
  LastError = 0;
  if ( !(unsigned int)TextLogGenerateBackupLogFileName(lpExistingFileName, NewFileName)
    || !MoveFileExW(lpExistingFileName, NewFileName, 5u) )
  {
    LastError = GetLastError();
  }
  SetLastError(LastError);
  LOBYTE(v2) = LastError == 0;
  return v2;
}

```

## disassembly

```asm
0x14000dbc0  mov     [rsp+arg_8], rbx
0x14000dbc5  mov     [rsp+arg_10], rsi
0x14000dbca  push    rdi
0x14000dbcb  sub     rsp, 250h
0x14000dbd2  mov     rax, cs:__security_cookie
0x14000dbd9  xor     rax, rsp
0x14000dbdc  mov     [rsp+258h+var_18], rax
0x14000dbe4  mov     rsi, rcx
0x14000dbe7  xor     edi, edi
0x14000dbe9  mov     ebx, edi
0x14000dbeb  lea     rdx, [rsp+258h+NewFileName]; pszDest
0x14000dbf0  call    TextLogGenerateBackupLogFileName
0x14000dbf5  test    eax, eax
0x14000dbf7  jz      short loc_14000DC0F
0x14000dbf9  lea     r8d, [rdi+5]; dwFlags
0x14000dbfd  lea     rdx, [rsp+258h+NewFileName]; lpNewFileName
0x14000dc02  mov     rcx, rsi; lpExistingFileName
0x14000dc05  call    cs:__imp_MoveFileExW
0x14000dc0b  test    eax, eax
0x14000dc0d  jnz     short loc_14000DC1B
0x14000dc0f  call    cs:__imp_GetLastError
0x14000dc15  mov     [rsp+258h+var_238], eax
0x14000dc19  mov     ebx, eax
0x14000dc1b  jmp     short loc_14000DC28
0x14000dc1d  mov     ebx, 54Fh
0x14000dc22  mov     [rsp+258h+var_238], ebx
0x14000dc26  xor     edi, edi
0x14000dc28  mov     ecx, ebx; dwErrCode
0x14000dc2a  call    cs:__imp_SetLastError
0x14000dc30  test    ebx, ebx
0x14000dc32  setz    dil
0x14000dc36  mov     eax, edi
0x14000dc38  mov     rcx, [rsp+258h+var_18]
0x14000dc40  xor     rcx, rsp; StackCookie
0x14000dc43  call    __security_check_cookie
0x14000dc48  lea     r11, [rsp+258h+var_8]
0x14000dc50  mov     rbx, [r11+18h]
0x14000dc54  mov     rsi, [r11+20h]
0x14000dc58  mov     rsp, r11
0x14000dc5b  pop     rdi
0x14000dc5c  retn
```
