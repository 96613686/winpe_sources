# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180004544`
- end: `0x1800045f0`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002420`
- `0x180006804`
- `0x1800085f0`
- `0x180008c30`

## callees

- `0x180003eac`
- `0x180004544`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000455b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000455b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800045d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800045d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800045d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800045d1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800045b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800045b8`

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
0x180004544  push    rbx
0x180004546  push    rbp
0x180004547  push    rsi
0x180004548  push    rdi
0x180004549  sub     rsp, 28h
0x18000454d  cmp     qword ptr [rcx+18h], 0
0x180004552  mov     rbx, rcx
0x180004555  jnz     loc_1800045DF
0x18000455b  call    cs:__imp_GetLastError
0x180004561  cmp     qword ptr [rbx+18h], 0
0x180004566  mov     ebp, eax
0x180004568  jz      short loc_18000456E
0x18000456a  xor     esi, esi
0x18000456c  jmp     short loc_1800045B1
0x18000456e  cmp     qword ptr [rbx+10h], 0
0x180004573  jnz     short loc_1800045A0
0x180004575  mov     rcx, [rbx+8]
0x180004579  lea     rdx, [rsp+48h+arg_0]
0x18000457e  mov     [rsp+48h+arg_0], 0
0x180004587  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18000458c  test    eax, eax
0x18000458e  js      short loc_1800045A0
0x180004590  cmp     qword ptr [rbx+10h], 0
0x180004595  jnz     short loc_1800045A0
0x180004597  mov     rax, [rsp+48h+arg_0]
0x18000459c  mov     [rbx+10h], rax
0x1800045a0  mov     rax, [rbx+10h]
0x1800045a4  lea     rcx, [rax+20h]
0x1800045a8  neg     rax
0x1800045ab  sbb     rsi, rsi
0x1800045ae  and     rsi, rcx
0x1800045b1  lea     rdi, [rbx+20h]
0x1800045b5  mov     rcx, rdi; SRWLock
0x1800045b8  call    cs:__imp_AcquireSRWLockExclusive
0x1800045be  cmp     qword ptr [rbx+18h], 0
0x1800045c3  jnz     short loc_1800045C9
0x1800045c5  mov     [rbx+18h], rsi
0x1800045c9  test    rdi, rdi
0x1800045cc  jz      short loc_1800045D7
0x1800045ce  mov     rcx, rdi; SRWLock
0x1800045d1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800045d7  mov     ecx, ebp; dwErrCode
0x1800045d9  call    cs:__imp_SetLastError
0x1800045df  cmp     qword ptr [rbx+18h], 0
0x1800045e4  setnz   al
0x1800045e7  add     rsp, 28h
0x1800045eb  pop     rdi
0x1800045ec  pop     rsi
0x1800045ed  pop     rbp
0x1800045ee  pop     rbx
0x1800045ef  retn
```
