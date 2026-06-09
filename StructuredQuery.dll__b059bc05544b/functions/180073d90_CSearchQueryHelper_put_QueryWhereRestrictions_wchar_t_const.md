# CSearchQueryHelper::put_QueryWhereRestrictions(wchar_t const *)

- ea: `0x180073d90`
- end: `0x180073df3`
- name: `?put_QueryWhereRestrictions@CSearchQueryHelper@@UEAAJPEB_W@Z`
- size: `99`
- prototype: `int(CSearchQueryHelper *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18005c340`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180073db1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180073db1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180073ddb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180073ddb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180073db7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180073db7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073dc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073dc4`

## pseudocode

```c
__int64 __fastcall CSearchQueryHelper::put_QueryWhereRestrictions(RTL_SRWLOCK *this, const wchar_t *a2)
{
  RTL_SRWLOCK *v3; // rbx
  RTL_SRWLOCK *v4; // rsi

  v3 = this;
  v4 = this + 2;
  AcquireSRWLockExclusive(this + 2);
  LODWORD(v4[1].Ptr) = GetCurrentThreadId();
  CoTaskMemFree(v3[8].Ptr);
  LODWORD(v3) = CSearchQueryHelper::_CoAllocStringOpt(a2, (wchar_t **)&v3[8]);
  ReleaseSRWLockExclusive(v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180073d90  mov     [rsp+arg_8], rbx
0x180073d95  mov     [rsp+arg_10], rsi
0x180073d9a  push    rdi
0x180073d9b  sub     rsp, 20h
0x180073d9f  mov     rdi, rdx
0x180073da2  mov     rbx, rcx
0x180073da5  lea     rsi, [rcx+10h]
0x180073da9  mov     [rsp+28h+arg_0], rsi
0x180073dae  mov     rcx, rsi; SRWLock
0x180073db1  call    cs:__imp_AcquireSRWLockExclusive
0x180073db7  call    cs:__imp_GetCurrentThreadId
0x180073dbd  mov     [rsi+8], eax
0x180073dc0  mov     rcx, [rbx+40h]; pv
0x180073dc4  call    cs:__imp_CoTaskMemFree
0x180073dca  lea     rdx, [rbx+40h]; wchar_t **
0x180073dce  mov     rcx, rdi; wchar_t *
0x180073dd1  call    ?_CoAllocStringOpt@CSearchQueryHelper@@CAJPEB_WPEAPEA_W@Z; CSearchQueryHelper::_CoAllocStringOpt(wchar_t const *,wchar_t * *)
0x180073dd6  mov     ebx, eax
0x180073dd8  mov     rcx, rsi; SRWLock
0x180073ddb  call    cs:__imp_ReleaseSRWLockExclusive
0x180073de1  mov     eax, ebx
0x180073de3  mov     rbx, [rsp+28h+arg_8]
0x180073de8  mov     rsi, [rsp+28h+arg_10]
0x180073ded  add     rsp, 20h
0x180073df1  pop     rdi
0x180073df2  retn
```
