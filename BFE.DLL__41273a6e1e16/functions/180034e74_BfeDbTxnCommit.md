# BfeDbTxnCommit

- ea: `0x180034e74`
- end: `0x180034ecf`
- name: `BfeDbTxnCommit`
- size: `91`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180034be0`
- `0x1800590dc`
- `0x18006c100`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x180034e74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e9b`
- `ktmw32!CommitTransaction` at `0x180034e81`
- `ktmw32!CommitTransaction` at `0x180034e81`

## string_xrefs

- `0x180034eaa`: `CommitTransaction`
- `0x180034ebe`: `BfeDbTxnCommit`

## pseudocode

```c
__int64 __fastcall BfeDbTxnCommit(void *a1)
{
  __int64 v1; // rbx
  DWORD LastError; // eax
  __int64 v4; // rcx
  __int64 v5; // rax

  v1 = 0;
  if ( a1 )
  {
    if ( !CommitTransaction(a1) )
    {
      LastError = GetLastError();
      v5 = WfpReportSysErrorAsWinError(v4, "CommitTransaction", LastError);
      v1 = v5;
      if ( v5 )
        WfpReportError(v5, "BfeDbTxnCommit");
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180034e74  push    rbx
0x180034e76  sub     rsp, 20h
0x180034e7a  xor     ebx, ebx
0x180034e7c  test    rcx, rcx
0x180034e7f  jz      short loc_180034E91
0x180034e81  call    cs:__imp_CommitTransaction
0x180034e88  nop     dword ptr [rax+rax+00h]
0x180034e8d  test    eax, eax
0x180034e8f  jz      short loc_180034E9B
0x180034e91  mov     rax, rbx
0x180034e94  add     rsp, 20h
0x180034e98  pop     rbx
0x180034e99  retn
0x180034e9b  call    cs:__imp_GetLastError
0x180034ea2  nop     dword ptr [rax+rax+00h]
0x180034ea7  mov     r8d, eax
0x180034eaa  lea     rdx, aCommittransact_0; "CommitTransaction"
0x180034eb1  call    WfpReportSysErrorAsWinError
0x180034eb6  mov     rbx, rax
0x180034eb9  test    rax, rax
0x180034ebc  jz      short loc_180034E91
0x180034ebe  lea     rdx, aBfedbtxncommit; "BfeDbTxnCommit"
0x180034ec5  mov     rcx, rax
0x180034ec8  call    WfpReportError
0x180034ecd  jmp     short loc_180034E91
```
