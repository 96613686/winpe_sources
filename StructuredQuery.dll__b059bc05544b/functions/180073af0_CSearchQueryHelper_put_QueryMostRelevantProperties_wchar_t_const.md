# CSearchQueryHelper::put_QueryMostRelevantProperties(wchar_t const *)

- ea: `0x180073af0`
- end: `0x180073b6a`
- name: `?put_QueryMostRelevantProperties@CSearchQueryHelper@@UEAAJPEB_W@Z`
- size: `122`
- prototype: `int(CSearchQueryHelper *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18005c340`
- `0x180073af0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180073b11`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180073b11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180073b52`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180073b52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180073b17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180073b17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073b40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073b40`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSearchQueryHelper::put_QueryMostRelevantProperties(RTL_SRWLOCK *this, const wchar_t *a2)
{
  RTL_SRWLOCK *v4; // rsi
  int v5; // ebx
  wchar_t *v7; // [rsp+30h] [rbp+8h] BYREF
  RTL_SRWLOCK *v8; // [rsp+40h] [rbp+18h]

  v4 = this + 2;
  v8 = this + 2;
  AcquireSRWLockExclusive(this + 2);
  LODWORD(v4[1].Ptr) = GetCurrentThreadId();
  v7 = 0;
  v5 = CSearchQueryHelper::_CoAllocStringOpt(a2, &v7);
  if ( v5 >= 0 )
  {
    CoTaskMemFree(this[12].Ptr);
    this[12].Ptr = v7;
  }
  ReleaseSRWLockExclusive(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180073af0  mov     [rsp+arg_8], rbx
0x180073af5  mov     [rsp+arg_18], rsi
0x180073afa  push    rdi
0x180073afb  sub     rsp, 20h
0x180073aff  mov     rbx, rdx
0x180073b02  mov     rdi, rcx
0x180073b05  lea     rsi, [rcx+10h]
0x180073b09  mov     [rsp+28h+arg_10], rsi
0x180073b0e  mov     rcx, rsi; SRWLock
0x180073b11  call    cs:__imp_AcquireSRWLockExclusive
0x180073b17  call    cs:__imp_GetCurrentThreadId
0x180073b1d  mov     [rsi+8], eax
0x180073b20  mov     [rsp+28h+arg_0], 0
0x180073b29  lea     rdx, [rsp+28h+arg_0]; wchar_t **
0x180073b2e  mov     rcx, rbx; wchar_t *
0x180073b31  call    ?_CoAllocStringOpt@CSearchQueryHelper@@CAJPEB_WPEAPEA_W@Z; CSearchQueryHelper::_CoAllocStringOpt(wchar_t const *,wchar_t * *)
0x180073b36  mov     ebx, eax
0x180073b38  test    eax, eax
0x180073b3a  js      short loc_180073B4F
0x180073b3c  mov     rcx, [rdi+60h]; pv
0x180073b40  call    cs:__imp_CoTaskMemFree
0x180073b46  mov     rdx, [rsp+28h+arg_0]
0x180073b4b  mov     [rdi+60h], rdx
0x180073b4f  mov     rcx, rsi; SRWLock
0x180073b52  call    cs:__imp_ReleaseSRWLockExclusive
0x180073b58  mov     eax, ebx
0x180073b5a  mov     rbx, [rsp+28h+arg_8]
0x180073b5f  mov     rsi, [rsp+28h+arg_18]
0x180073b64  add     rsp, 20h
0x180073b68  pop     rdi
0x180073b69  retn
```
