# BfeDbTxnCreate

- ea: `0x180034ed8`
- end: `0x18003503e`
- name: `BfeDbTxnCreate`
- size: `358`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034be0`
- `0x1800590dc`
- `0x18006c100`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x180034ed8`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fe3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fe3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180034f8f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180034f8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008ca9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008ca9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034f7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034f7d`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180034f64`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180034f64`
- `ktmw32!CreateTransaction` at `0x180034f19`
- `ktmw32!CreateTransaction` at `0x180034f19`

## string_xrefs

- `0x180034fef`: `CreateTransaction`
- `0x180035001`: `BfeDbTxnCreate`
- `0x18003502a`: `BfeDbTxnCreate`
- `0x18003501e`: `RegOpenKeyTransactedA`

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
0x180034ed8  mov     r11, rsp
0x180034edb  mov     [r11+10h], rbx
0x180034edf  mov     [r11+18h], rsi
0x180034ee3  push    rdi
0x180034ee4  sub     rsp, 50h
0x180034ee8  mov     rax, cs:__security_cookie
0x180034eef  xor     rax, rsp
0x180034ef2  mov     [rsp+58h+var_10], rax
0x180034ef7  xor     ebx, ebx
0x180034ef9  mov     rsi, rcx
0x180034efc  mov     [r11-28h], rbx
0x180034f00  xor     r9d, r9d; IsolationLevel
0x180034f03  mov     [rcx], rbx
0x180034f06  xor     r8d, r8d; CreateOptions
0x180034f09  mov     [rsp+58h+Timeout], ebx; Timeout
0x180034f0d  xor     ecx, ecx; lpTransactionAttributes
0x180034f0f  xor     edx, edx; UOW
0x180034f11  mov     [rsp+58h+IsolationFlags], ebx; IsolationFlags
0x180034f15  mov     [r11-18h], rbx
0x180034f19  call    cs:__imp_CreateTransaction
0x180034f20  nop     dword ptr [rax+rax+00h]
0x180034f25  mov     rdi, rax
0x180034f28  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034f2c  jz      loc_180034FD2
0x180034f32  test    rax, rax
0x180034f35  jz      loc_180034FFB
0x180034f3b  mov     [rsp+58h+pExtendedParemeter], rbx; pExtendedParemeter
0x180034f40  lea     r9d, [rbx+1]; samDesired
0x180034f44  mov     qword ptr [rsp+58h+Timeout], rax; hTransaction
0x180034f49  lea     rdx, SYSTEM_REG_KEY; "System"
0x180034f50  lea     rax, [rsp+58h+phkResult]
0x180034f55  xor     r8d, r8d; ulOptions
0x180034f58  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034f5f  mov     qword ptr [rsp+58h+IsolationFlags], rax; phkResult
0x180034f64  call    cs:__imp_RegOpenKeyTransactedW
0x180034f6b  nop     dword ptr [rax+rax+00h]
0x180034f70  test    eax, eax
0x180034f72  jnz     loc_18003500A
0x180034f78  mov     rcx, [rsp+58h+phkResult]; hKey
0x180034f7d  call    cs:__imp_RegCloseKey
0x180034f84  nop     dword ptr [rax+rax+00h]
0x180034f89  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x180034f8f  call    cs:__imp_TlsGetValue
0x180034f96  nop     dword ptr [rax+rax+00h]
0x180034f9b  mov     [rax+10h], rdi
0x180034f9f  mov     [rsi], rdi
0x180034fa2  jmp     short loc_180034FB1
0x180034fa4  call    WfpReportSysErrorAsWinError
0x180034fa9  mov     rbx, rax
0x180034fac  test    rax, rax
0x180034faf  jnz     short loc_18003502A
0x180034fb1  mov     rax, rbx
0x180034fb4  mov     rcx, [rsp+58h+var_10]
0x180034fb9  xor     rcx, rsp; StackCookie
0x180034fbc  call    __security_check_cookie
0x180034fc1  mov     rbx, [rsp+58h+arg_8]
0x180034fc6  mov     rsi, [rsp+58h+arg_10]
0x180034fcb  add     rsp, 50h
0x180034fcf  pop     rdi
0x180034fd0  retn
0x180034fd2  call    cs:__imp_GetLastError
0x180034fd9  nop     dword ptr [rax+rax+00h]
0x180034fde  cmp     eax, 32h ; '2'
0x180034fe1  jnz     short loc_180034FB1
0x180034fe3  call    cs:__imp_GetLastError
0x180034fea  nop     dword ptr [rax+rax+00h]
0x180034fef  lea     rdx, aCreatetransact_0; "CreateTransaction"
0x180034ff6  jmp     loc_18008CA94
0x180034ffb  mov     r8d, 1Fh
0x180035001  lea     rdx, aBfedbtxncreate; "BfeDbTxnCreate"
0x180035008  jmp     short loc_180034FA4
0x18003500a  cmp     eax, 1A91h
0x18003500f  jz      loc_18008CA9C
0x180035015  cmp     eax, 78h ; 'x'
0x180035018  jz      loc_18008CA9C
0x18003501e  lea     rdx, aRegopenkeytran_0; "RegOpenKeyTransactedA"
0x180035025  jmp     loc_18008CA94
0x18003502a  lea     rdx, aBfedbtxncreate; "BfeDbTxnCreate"
0x180035031  mov     rcx, rbx
0x180035034  call    WfpReportError
0x180035039  jmp     loc_180034FB1
0x18008ca94  mov     r8d, eax
0x18008ca97  jmp     loc_180034FA4
0x18008ca9c  mov     rcx, rdi; hObject
0x18008ca9f  call    cs:__imp_CloseHandle
0x18008caa6  nop     dword ptr [rax+rax+00h]
0x18008caab  nop
0x18008caac  jmp     loc_180034FB1
```
