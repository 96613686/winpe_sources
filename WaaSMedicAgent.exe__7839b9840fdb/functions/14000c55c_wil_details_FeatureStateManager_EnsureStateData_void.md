# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x14000c55c`
- end: `0x14000c608`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b8f0`
- `0x14000d514`
- `0x14000e2d4`
- `0x14000e600`

## callees

- `0x14000c164`
- `0x14000c55c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000c5e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000c5e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000c5d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000c5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c573`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c5f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c5f1`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureStateData(RTL_SRWLOCK *this)
{
  DWORD LastError; // ebp
  __int64 v3; // rsi
  __int64 Ptr; // rcx
  void *v6; // [rsp+50h] [rbp+8h] BYREF

  if ( !this[3].Ptr )
  {
    LastError = GetLastError();
    if ( this[3].Ptr )
    {
      v3 = 0;
    }
    else
    {
      if ( !this[2].Ptr )
      {
        Ptr = (__int64)this[1].Ptr;
        v6 = 0;
        if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(Ptr, &v6) >= 0
          && !this[2].Ptr )
        {
          this[2].Ptr = v6;
        }
      }
      v3 = ((__int64)this[2].Ptr + 32) & -(__int64)(this[2].Ptr != 0);
    }
    AcquireSRWLockExclusive(this + 4);
    if ( !this[3].Ptr )
      this[3].Ptr = (PVOID)v3;
    if ( this != (RTL_SRWLOCK *)-32LL )
      ReleaseSRWLockExclusive(this + 4);
    SetLastError(LastError);
  }
  return this[3].Ptr != 0;
}

```

## disassembly

```asm
0x14000c55c  push    rbx
0x14000c55e  push    rbp
0x14000c55f  push    rsi
0x14000c560  push    rdi
0x14000c561  sub     rsp, 28h
0x14000c565  cmp     qword ptr [rcx+18h], 0
0x14000c56a  mov     rbx, rcx
0x14000c56d  jnz     loc_14000C5F7
0x14000c573  call    cs:__imp_GetLastError
0x14000c579  cmp     qword ptr [rbx+18h], 0
0x14000c57e  mov     ebp, eax
0x14000c580  jz      short loc_14000C586
0x14000c582  xor     esi, esi
0x14000c584  jmp     short loc_14000C5C9
0x14000c586  cmp     qword ptr [rbx+10h], 0
0x14000c58b  jnz     short loc_14000C5B8
0x14000c58d  mov     rcx, [rbx+8]
0x14000c591  lea     rdx, [rsp+48h+arg_0]
0x14000c596  mov     [rsp+48h+arg_0], 0
0x14000c59f  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x14000c5a4  test    eax, eax
0x14000c5a6  js      short loc_14000C5B8
0x14000c5a8  cmp     qword ptr [rbx+10h], 0
0x14000c5ad  jnz     short loc_14000C5B8
0x14000c5af  mov     rax, [rsp+48h+arg_0]
0x14000c5b4  mov     [rbx+10h], rax
0x14000c5b8  mov     rax, [rbx+10h]
0x14000c5bc  lea     rcx, [rax+20h]
0x14000c5c0  neg     rax
0x14000c5c3  sbb     rsi, rsi
0x14000c5c6  and     rsi, rcx
0x14000c5c9  lea     rdi, [rbx+20h]
0x14000c5cd  mov     rcx, rdi; SRWLock
0x14000c5d0  call    cs:__imp_AcquireSRWLockExclusive
0x14000c5d6  cmp     qword ptr [rbx+18h], 0
0x14000c5db  jnz     short loc_14000C5E1
0x14000c5dd  mov     [rbx+18h], rsi
0x14000c5e1  test    rdi, rdi
0x14000c5e4  jz      short loc_14000C5EF
0x14000c5e6  mov     rcx, rdi; SRWLock
0x14000c5e9  call    cs:__imp_ReleaseSRWLockExclusive
0x14000c5ef  mov     ecx, ebp; dwErrCode
0x14000c5f1  call    cs:__imp_SetLastError
0x14000c5f7  cmp     qword ptr [rbx+18h], 0
0x14000c5fc  setnz   al
0x14000c5ff  add     rsp, 28h
0x14000c603  pop     rdi
0x14000c604  pop     rsi
0x14000c605  pop     rbp
0x14000c606  pop     rbx
0x14000c607  retn
```
