# CSearchQueryHelper::put_QueryContentProperties(wchar_t const *)

- ea: `0x180073970`
- end: `0x1800739f2`
- name: `?put_QueryContentProperties@CSearchQueryHelper@@UEAAJPEB_W@Z`
- size: `130`
- prototype: `int(CSearchQueryHelper *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180015a40`
- `0x18003ba88`
- `0x18005c9f4`
- `0x180073970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007398b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007398b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800739e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800739e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180073991`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180073991`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800739b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800739b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSearchQueryHelper::put_QueryContentProperties(RTL_SRWLOCK *this, const wchar_t *a2)
{
  RTL_SRWLOCK *v4; // rdi
  const wchar_t *v5; // rsi
  __int64 v6; // rdx
  __int64 v7; // rcx
  CSearchQueryHelper *v8; // rcx
  int v9; // ebx
  struct IQueryParser2 *Ptr; // rdx

  v4 = this + 2;
  AcquireSRWLockExclusive(this + 2);
  LODWORD(v4[1].Ptr) = GetCurrentThreadId();
  v5 = L"System.FullText";
  if ( !(unsigned int)CSearchQueryHelper::_IsEmptyString(a2) )
    v5 = a2;
  CoTaskMemFree(this[6].Ptr);
  v9 = _AllocString<CTCoAllocPolicy>(v7, v6, (const size_t *)v5, &this[6].Ptr);
  if ( v9 >= 0 )
  {
    Ptr = (struct IQueryParser2 *)this[14].Ptr;
    if ( Ptr )
      v9 = CSearchQueryHelper::_InitializeDefaultStringProperty(v8, Ptr, v5);
  }
  ReleaseSRWLockExclusive(v4);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180073970  push    rbx
0x180073972  push    rbp
0x180073973  push    rsi
0x180073974  push    rdi
0x180073975  sub     rsp, 28h
0x180073979  mov     rbx, rdx
0x18007397c  mov     rbp, rcx
0x18007397f  lea     rdi, [rcx+10h]
0x180073983  mov     [rsp+48h+arg_0], rdi
0x180073988  mov     rcx, rdi; SRWLock
0x18007398b  call    cs:__imp_AcquireSRWLockExclusive
0x180073991  call    cs:__imp_GetCurrentThreadId
0x180073997  mov     [rdi+8], eax
0x18007399a  mov     rcx, rbx; wchar_t *
0x18007399d  call    ?_IsEmptyString@CSearchQueryHelper@@CAHPEB_W@Z; CSearchQueryHelper::_IsEmptyString(wchar_t const *)
0x1800739a2  lea     rsi, aSystemFulltext; "System.FullText"
0x1800739a9  test    eax, eax
0x1800739ab  cmovz   rsi, rbx
0x1800739af  mov     rcx, [rbp+30h]; pv
0x1800739b3  call    cs:__imp_CoTaskMemFree
0x1800739b9  lea     r9, [rbp+30h]
0x1800739bd  mov     r8, rsi
0x1800739c0  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEB_WPEAPEA_W@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,wchar_t const *,wchar_t * *)
0x1800739c5  mov     ebx, eax
0x1800739c7  test    eax, eax
0x1800739c9  js      short loc_1800739DE
0x1800739cb  mov     rdx, [rbp+70h]; struct IQueryParser2 *
0x1800739cf  test    rdx, rdx
0x1800739d2  jz      short loc_1800739DE
0x1800739d4  mov     r8, rsi; wchar_t *
0x1800739d7  call    ?_InitializeDefaultStringProperty@CSearchQueryHelper@@AEAAJPEAUIQueryParser2@@PEB_W@Z; CSearchQueryHelper::_InitializeDefaultStringProperty(IQueryParser2 *,wchar_t const *)
0x1800739dc  mov     ebx, eax
0x1800739de  mov     rcx, rdi; SRWLock
0x1800739e1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800739e7  mov     eax, ebx
0x1800739e9  add     rsp, 28h
0x1800739ed  pop     rdi
0x1800739ee  pop     rsi
0x1800739ef  pop     rbp
0x1800739f0  pop     rbx
0x1800739f1  retn
```
