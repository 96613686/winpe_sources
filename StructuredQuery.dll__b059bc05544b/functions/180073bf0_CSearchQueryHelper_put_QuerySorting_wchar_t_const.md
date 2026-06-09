# CSearchQueryHelper::put_QuerySorting(wchar_t const *)

- ea: `0x180073bf0`
- end: `0x180073c53`
- name: `?put_QuerySorting@CSearchQueryHelper@@UEAAJPEB_W@Z`
- size: `99`
- prototype: `int(CSearchQueryHelper *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18005c340`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180073c11`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180073c11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180073c3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180073c3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180073c17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180073c17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073c24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073c24`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSearchQueryHelper::put_QuerySorting(RTL_SRWLOCK *this, const wchar_t *a2)
{
  RTL_SRWLOCK *v3; // rbx
  RTL_SRWLOCK *v4; // rsi

  v3 = this;
  v4 = this + 2;
  AcquireSRWLockExclusive(this + 2);
  LODWORD(v4[1].Ptr) = GetCurrentThreadId();
  CoTaskMemFree(v3[9].Ptr);
  LODWORD(v3) = CSearchQueryHelper::_CoAllocStringOpt(a2, (wchar_t **)&v3[9]);
  ReleaseSRWLockExclusive(v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180073bf0  mov     [rsp+arg_8], rbx
0x180073bf5  mov     [rsp+arg_10], rsi
0x180073bfa  push    rdi
0x180073bfb  sub     rsp, 20h
0x180073bff  mov     rdi, rdx
0x180073c02  mov     rbx, rcx
0x180073c05  lea     rsi, [rcx+10h]
0x180073c09  mov     [rsp+28h+arg_0], rsi
0x180073c0e  mov     rcx, rsi; SRWLock
0x180073c11  call    cs:__imp_AcquireSRWLockExclusive
0x180073c17  call    cs:__imp_GetCurrentThreadId
0x180073c1d  mov     [rsi+8], eax
0x180073c20  mov     rcx, [rbx+48h]; pv
0x180073c24  call    cs:__imp_CoTaskMemFree
0x180073c2a  lea     rdx, [rbx+48h]; wchar_t **
0x180073c2e  mov     rcx, rdi; wchar_t *
0x180073c31  call    ?_CoAllocStringOpt@CSearchQueryHelper@@CAJPEB_WPEAPEA_W@Z; CSearchQueryHelper::_CoAllocStringOpt(wchar_t const *,wchar_t * *)
0x180073c36  mov     ebx, eax
0x180073c38  mov     rcx, rsi; SRWLock
0x180073c3b  call    cs:__imp_ReleaseSRWLockExclusive
0x180073c41  mov     eax, ebx
0x180073c43  mov     rbx, [rsp+28h+arg_8]
0x180073c48  mov     rsi, [rsp+28h+arg_10]
0x180073c4d  add     rsp, 20h
0x180073c51  pop     rdi
0x180073c52  retn
```
