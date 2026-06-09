# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1800044f4`
- end: `0x1800045a0`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800022c0`
- `0x180006064`
- `0x180007c44`
- `0x180008230`

## callees

- `0x180003e5c`
- `0x1800044f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004568`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004568`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004581`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004581`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000450b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000450b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004589`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004589`

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
0x1800044f4  push    rbx
0x1800044f6  push    rbp
0x1800044f7  push    rsi
0x1800044f8  push    rdi
0x1800044f9  sub     rsp, 28h
0x1800044fd  cmp     qword ptr [rcx+18h], 0
0x180004502  mov     rbx, rcx
0x180004505  jnz     loc_18000458F
0x18000450b  call    cs:__imp_GetLastError
0x180004511  cmp     qword ptr [rbx+18h], 0
0x180004516  mov     ebp, eax
0x180004518  jz      short loc_18000451E
0x18000451a  xor     esi, esi
0x18000451c  jmp     short loc_180004561
0x18000451e  cmp     qword ptr [rbx+10h], 0
0x180004523  jnz     short loc_180004550
0x180004525  mov     rcx, [rbx+8]
0x180004529  lea     rdx, [rsp+48h+arg_0]
0x18000452e  mov     [rsp+48h+arg_0], 0
0x180004537  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18000453c  test    eax, eax
0x18000453e  js      short loc_180004550
0x180004540  cmp     qword ptr [rbx+10h], 0
0x180004545  jnz     short loc_180004550
0x180004547  mov     rax, [rsp+48h+arg_0]
0x18000454c  mov     [rbx+10h], rax
0x180004550  mov     rax, [rbx+10h]
0x180004554  lea     rcx, [rax+20h]
0x180004558  neg     rax
0x18000455b  sbb     rsi, rsi
0x18000455e  and     rsi, rcx
0x180004561  lea     rdi, [rbx+20h]
0x180004565  mov     rcx, rdi; SRWLock
0x180004568  call    cs:__imp_AcquireSRWLockExclusive
0x18000456e  cmp     qword ptr [rbx+18h], 0
0x180004573  jnz     short loc_180004579
0x180004575  mov     [rbx+18h], rsi
0x180004579  test    rdi, rdi
0x18000457c  jz      short loc_180004587
0x18000457e  mov     rcx, rdi; SRWLock
0x180004581  call    cs:__imp_ReleaseSRWLockExclusive
0x180004587  mov     ecx, ebp; dwErrCode
0x180004589  call    cs:__imp_SetLastError
0x18000458f  cmp     qword ptr [rbx+18h], 0
0x180004594  setnz   al
0x180004597  add     rsp, 28h
0x18000459b  pop     rdi
0x18000459c  pop     rsi
0x18000459d  pop     rbp
0x18000459e  pop     rbx
0x18000459f  retn
```
