# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180012c84`
- end: `0x180012d30`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800111c0`
- `0x1800147d4`
- `0x180015afc`
- `0x1800160e0`

## callees

- `0x1800125e0`
- `0x180012c84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012d19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012d19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c9b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012cf8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012cf8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012d11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012d11`

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
0x180012c84  push    rbx
0x180012c86  push    rbp
0x180012c87  push    rsi
0x180012c88  push    rdi
0x180012c89  sub     rsp, 28h
0x180012c8d  cmp     qword ptr [rcx+18h], 0
0x180012c92  mov     rbx, rcx
0x180012c95  jnz     loc_180012D1F
0x180012c9b  call    cs:__imp_GetLastError
0x180012ca1  cmp     qword ptr [rbx+18h], 0
0x180012ca6  mov     ebp, eax
0x180012ca8  jz      short loc_180012CAE
0x180012caa  xor     esi, esi
0x180012cac  jmp     short loc_180012CF1
0x180012cae  cmp     qword ptr [rbx+10h], 0
0x180012cb3  jnz     short loc_180012CE0
0x180012cb5  mov     rcx, [rbx+8]
0x180012cb9  lea     rdx, [rsp+48h+arg_0]
0x180012cbe  mov     [rsp+48h+arg_0], 0
0x180012cc7  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180012ccc  test    eax, eax
0x180012cce  js      short loc_180012CE0
0x180012cd0  cmp     qword ptr [rbx+10h], 0
0x180012cd5  jnz     short loc_180012CE0
0x180012cd7  mov     rax, [rsp+48h+arg_0]
0x180012cdc  mov     [rbx+10h], rax
0x180012ce0  mov     rax, [rbx+10h]
0x180012ce4  lea     rcx, [rax+20h]
0x180012ce8  neg     rax
0x180012ceb  sbb     rsi, rsi
0x180012cee  and     rsi, rcx
0x180012cf1  lea     rdi, [rbx+20h]
0x180012cf5  mov     rcx, rdi; SRWLock
0x180012cf8  call    cs:__imp_AcquireSRWLockExclusive
0x180012cfe  cmp     qword ptr [rbx+18h], 0
0x180012d03  jnz     short loc_180012D09
0x180012d05  mov     [rbx+18h], rsi
0x180012d09  test    rdi, rdi
0x180012d0c  jz      short loc_180012D17
0x180012d0e  mov     rcx, rdi; SRWLock
0x180012d11  call    cs:__imp_ReleaseSRWLockExclusive
0x180012d17  mov     ecx, ebp; dwErrCode
0x180012d19  call    cs:__imp_SetLastError
0x180012d1f  cmp     qword ptr [rbx+18h], 0
0x180012d24  setnz   al
0x180012d27  add     rsp, 28h
0x180012d2b  pop     rdi
0x180012d2c  pop     rsi
0x180012d2d  pop     rbp
0x180012d2e  pop     rbx
0x180012d2f  retn
```
