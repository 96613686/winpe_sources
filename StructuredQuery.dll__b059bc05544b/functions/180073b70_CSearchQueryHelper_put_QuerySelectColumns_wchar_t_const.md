# CSearchQueryHelper::put_QuerySelectColumns(wchar_t const *)

- ea: `0x180073b70`
- end: `0x180073bdb`
- name: `?put_QuerySelectColumns@CSearchQueryHelper@@UEAAJPEB_W@Z`
- size: `107`
- prototype: `int(CSearchQueryHelper *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180015a40`
- `0x18005c9f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180073b8b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180073b8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180073bca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180073bca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180073b91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180073b91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073bb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073bb3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSearchQueryHelper::put_QuerySelectColumns(RTL_SRWLOCK *this, const wchar_t *a2)
{
  RTL_SRWLOCK *v4; // rbp
  const wchar_t *v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // ebx

  v4 = this + 2;
  AcquireSRWLockExclusive(this + 2);
  LODWORD(v4[1].Ptr) = GetCurrentThreadId();
  v5 = L"System.ItemUrl";
  if ( !(unsigned int)CSearchQueryHelper::_IsEmptyString(a2) )
    v5 = a2;
  CoTaskMemFree(this[7].Ptr);
  v8 = _AllocString<CTCoAllocPolicy>(v7, v6, (const size_t *)v5, &this[7].Ptr);
  ReleaseSRWLockExclusive(v4);
  return v8;
}

```

## disassembly

```asm
0x180073b70  push    rbx
0x180073b72  push    rbp
0x180073b73  push    rsi
0x180073b74  push    rdi
0x180073b75  sub     rsp, 28h
0x180073b79  mov     rbx, rdx
0x180073b7c  mov     rsi, rcx
0x180073b7f  lea     rbp, [rcx+10h]
0x180073b83  mov     [rsp+48h+arg_0], rbp
0x180073b88  mov     rcx, rbp; SRWLock
0x180073b8b  call    cs:__imp_AcquireSRWLockExclusive
0x180073b91  call    cs:__imp_GetCurrentThreadId
0x180073b97  mov     [rbp+8], eax
0x180073b9a  mov     rcx, rbx; wchar_t *
0x180073b9d  call    ?_IsEmptyString@CSearchQueryHelper@@CAHPEB_W@Z; CSearchQueryHelper::_IsEmptyString(wchar_t const *)
0x180073ba2  lea     rdi, aSystemItemurl; "System.ItemUrl"
0x180073ba9  test    eax, eax
0x180073bab  cmovz   rdi, rbx
0x180073baf  mov     rcx, [rsi+38h]; pv
0x180073bb3  call    cs:__imp_CoTaskMemFree
0x180073bb9  lea     r9, [rsi+38h]
0x180073bbd  mov     r8, rdi
0x180073bc0  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEB_WPEAPEA_W@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,wchar_t const *,wchar_t * *)
0x180073bc5  mov     ebx, eax
0x180073bc7  mov     rcx, rbp; SRWLock
0x180073bca  call    cs:__imp_ReleaseSRWLockExclusive
0x180073bd0  mov     eax, ebx
0x180073bd2  add     rsp, 28h
0x180073bd6  pop     rdi
0x180073bd7  pop     rsi
0x180073bd8  pop     rbp
0x180073bd9  pop     rbx
0x180073bda  retn
```
