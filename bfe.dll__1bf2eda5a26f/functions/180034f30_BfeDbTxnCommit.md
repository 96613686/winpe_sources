# BfeDbTxnCommit

- ea: `0x180034f30`
- end: `0x180034f7e`
- name: `BfeDbTxnCommit`
- size: `78`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180034cb0`
- `0x1800573b8`
- `0x180069b1c`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x180034f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034f50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034f50`
- `ktmw32!CommitTransaction` at `0x180034f3d`
- `ktmw32!CommitTransaction` at `0x180034f3d`

## string_xrefs

- `0x180034f59`: `CommitTransaction`
- `0x180034f6d`: `BfeDbTxnCommit`

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
0x180034f30  push    rbx
0x180034f32  sub     rsp, 20h
0x180034f36  xor     ebx, ebx
0x180034f38  test    rcx, rcx
0x180034f3b  jz      short loc_180034F47
0x180034f3d  call    cs:__imp_CommitTransaction
0x180034f43  test    eax, eax
0x180034f45  jz      short loc_180034F50
0x180034f47  mov     rax, rbx
0x180034f4a  add     rsp, 20h
0x180034f4e  pop     rbx
0x180034f4f  retn
0x180034f50  call    cs:__imp_GetLastError
0x180034f56  mov     r8d, eax
0x180034f59  lea     rdx, aCommittransact_0; "CommitTransaction"
0x180034f60  call    WfpReportSysErrorAsWinError
0x180034f65  mov     rbx, rax
0x180034f68  test    rax, rax
0x180034f6b  jz      short loc_180034F47
0x180034f6d  lea     rdx, aBfedbtxncommit; "BfeDbTxnCommit"
0x180034f74  mov     rcx, rax
0x180034f77  call    WfpReportError
0x180034f7c  jmp     short loc_180034F47
```
