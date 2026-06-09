# BfeDbTxnCreate

- ea: `0x180034f84`
- end: `0x1800350be`
- name: `BfeDbTxnCreate`
- size: `314`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034cb0`
- `0x1800573b8`
- `0x180069b1c`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x180034f84`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035061`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003506c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035061`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003506c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180035025`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180035025`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089e1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089e1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035019`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035019`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18003500a`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18003500a`
- `ktmw32!CreateTransaction` at `0x180034fc5`
- `ktmw32!CreateTransaction` at `0x180034fc5`

## string_xrefs

- `0x180035072`: `CreateTransaction`
- `0x180035084`: `BfeDbTxnCreate`
- `0x1800350ad`: `BfeDbTxnCreate`
- `0x1800350a1`: `RegOpenKeyTransactedA`

## pseudocode

```c
__int64 __fastcall BfeDbTxnCreate(_QWORD *a1)
{
  __int64 v1; // rbx
  HANDLE Transaction; // rax
  __int64 v4; // rcx
  void *v5; // rdi
  DWORD LastError; // eax
  __int64 v7; // rax
  const char *v9; // rdx
  __int64 v10; // r8
  HKEY phkResult; // [rsp+40h] [rbp-18h] BYREF

  v1 = 0;
  *a1 = 0;
  phkResult = 0;
  Transaction = CreateTransaction(0, 0, 0, 0, 0, 0, 0);
  v5 = Transaction;
  if ( Transaction == (HANDLE)-1LL )
  {
    if ( GetLastError() != 50 )
      return v1;
    LastError = GetLastError();
    v9 = "CreateTransaction";
  }
  else
  {
    if ( !Transaction )
    {
      v10 = 31;
      v9 = "BfeDbTxnCreate";
      goto LABEL_5;
    }
    LastError = RegOpenKeyTransactedW(HKEY_LOCAL_MACHINE, L"System", 0, 1u, &phkResult, Transaction, 0);
    if ( !LastError )
    {
      RegCloseKey(phkResult);
      *((_QWORD *)TlsGetValue(gBfeContextComponent) + 2) = v5;
      *a1 = v5;
      return v1;
    }
    if ( LastError == 6801 || LastError == 120 )
    {
      CloseHandle(v5);
      return v1;
    }
    v9 = "RegOpenKeyTransactedA";
  }
  v10 = LastError;
LABEL_5:
  v7 = WfpReportSysErrorAsWinError(v4, v9, v10);
  v1 = v7;
  if ( v7 )
    WfpReportError(v7, "BfeDbTxnCreate");
  return v1;
}

```

## disassembly

```asm
0x180034f84  mov     r11, rsp
0x180034f87  mov     [r11+10h], rbx
0x180034f8b  mov     [r11+18h], rsi
0x180034f8f  push    rdi
0x180034f90  sub     rsp, 50h
0x180034f94  mov     rax, cs:__security_cookie
0x180034f9b  xor     rax, rsp
0x180034f9e  mov     [rsp+58h+var_10], rax
0x180034fa3  xor     ebx, ebx
0x180034fa5  mov     rsi, rcx
0x180034fa8  mov     [r11-28h], rbx
0x180034fac  xor     r9d, r9d; IsolationLevel
0x180034faf  mov     [rcx], rbx
0x180034fb2  xor     r8d, r8d; CreateOptions
0x180034fb5  mov     [rsp+58h+Timeout], ebx; Timeout
0x180034fb9  xor     ecx, ecx; lpTransactionAttributes
0x180034fbb  xor     edx, edx; UOW
0x180034fbd  mov     [rsp+58h+IsolationFlags], ebx; IsolationFlags
0x180034fc1  mov     [r11-18h], rbx
0x180034fc5  call    cs:__imp_CreateTransaction
0x180034fcb  mov     rdi, rax
0x180034fce  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034fd2  jz      loc_180035061
0x180034fd8  test    rax, rax
0x180034fdb  jz      loc_18003507E
0x180034fe1  mov     [rsp+58h+pExtendedParemeter], rbx; pExtendedParemeter
0x180034fe6  lea     r9d, [rbx+1]; samDesired
0x180034fea  mov     qword ptr [rsp+58h+Timeout], rax; hTransaction
0x180034fef  lea     rdx, SYSTEM_REG_KEY; "System"
0x180034ff6  lea     rax, [rsp+58h+phkResult]
0x180034ffb  xor     r8d, r8d; ulOptions
0x180034ffe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035005  mov     qword ptr [rsp+58h+IsolationFlags], rax; phkResult
0x18003500a  call    cs:__imp_RegOpenKeyTransactedW
0x180035010  test    eax, eax
0x180035012  jnz     short loc_18003508D
0x180035014  mov     rcx, [rsp+58h+phkResult]; hKey
0x180035019  call    cs:__imp_RegCloseKey
0x18003501f  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x180035025  call    cs:__imp_TlsGetValue
0x18003502b  mov     [rax+10h], rdi
0x18003502f  mov     [rsi], rdi
0x180035032  jmp     short loc_180035041
0x180035034  call    WfpReportSysErrorAsWinError
0x180035039  mov     rbx, rax
0x18003503c  test    rax, rax
0x18003503f  jnz     short loc_1800350AD
0x180035041  mov     rax, rbx
0x180035044  mov     rcx, [rsp+58h+var_10]
0x180035049  xor     rcx, rsp; StackCookie
0x18003504c  call    __security_check_cookie
0x180035051  mov     rbx, [rsp+58h+arg_8]
0x180035056  mov     rsi, [rsp+58h+arg_10]
0x18003505b  add     rsp, 50h
0x18003505f  pop     rdi
0x180035060  retn
0x180035061  call    cs:__imp_GetLastError
0x180035067  cmp     eax, 32h ; '2'
0x18003506a  jnz     short loc_180035041
0x18003506c  call    cs:__imp_GetLastError
0x180035072  lea     rdx, aCreatetransact_0; "CreateTransaction"
0x180035079  jmp     loc_180089E12
0x18003507e  mov     r8d, 1Fh
0x180035084  lea     rdx, aBfedbtxncreate; "BfeDbTxnCreate"
0x18003508b  jmp     short loc_180035034
0x18003508d  cmp     eax, 1A91h
0x180035092  jz      loc_180089E1A
0x180035098  cmp     eax, 78h ; 'x'
0x18003509b  jz      loc_180089E1A
0x1800350a1  lea     rdx, aRegopenkeytran_0; "RegOpenKeyTransactedA"
0x1800350a8  jmp     loc_180089E12
0x1800350ad  lea     rdx, aBfedbtxncreate; "BfeDbTxnCreate"
0x1800350b4  mov     rcx, rbx
0x1800350b7  call    WfpReportError
0x1800350bc  jmp     short loc_180035041
0x180089e12  mov     r8d, eax
0x180089e15  jmp     loc_180035034
0x180089e1a  mov     rcx, rdi; hObject
0x180089e1d  call    cs:__imp_CloseHandle
0x180089e23  nop
0x180089e24  jmp     loc_180035041
```
