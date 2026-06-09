# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1800063b4`
- end: `0x180006460`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800048f0`
- `0x180007ec4`
- `0x18000924c`
- `0x1800097c0`

## callees

- `0x180005d10`
- `0x1800063b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006441`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006441`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006428`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006428`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006449`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063cb`

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
0x1800063b4  push    rbx
0x1800063b6  push    rbp
0x1800063b7  push    rsi
0x1800063b8  push    rdi
0x1800063b9  sub     rsp, 28h
0x1800063bd  cmp     qword ptr [rcx+18h], 0
0x1800063c2  mov     rbx, rcx
0x1800063c5  jnz     loc_18000644F
0x1800063cb  call    cs:__imp_GetLastError
0x1800063d1  cmp     qword ptr [rbx+18h], 0
0x1800063d6  mov     ebp, eax
0x1800063d8  jz      short loc_1800063DE
0x1800063da  xor     esi, esi
0x1800063dc  jmp     short loc_180006421
0x1800063de  cmp     qword ptr [rbx+10h], 0
0x1800063e3  jnz     short loc_180006410
0x1800063e5  mov     rcx, [rbx+8]
0x1800063e9  lea     rdx, [rsp+48h+arg_0]
0x1800063ee  mov     [rsp+48h+arg_0], 0
0x1800063f7  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x1800063fc  test    eax, eax
0x1800063fe  js      short loc_180006410
0x180006400  cmp     qword ptr [rbx+10h], 0
0x180006405  jnz     short loc_180006410
0x180006407  mov     rax, [rsp+48h+arg_0]
0x18000640c  mov     [rbx+10h], rax
0x180006410  mov     rax, [rbx+10h]
0x180006414  lea     rcx, [rax+20h]
0x180006418  neg     rax
0x18000641b  sbb     rsi, rsi
0x18000641e  and     rsi, rcx
0x180006421  lea     rdi, [rbx+20h]
0x180006425  mov     rcx, rdi; SRWLock
0x180006428  call    cs:__imp_AcquireSRWLockExclusive
0x18000642e  cmp     qword ptr [rbx+18h], 0
0x180006433  jnz     short loc_180006439
0x180006435  mov     [rbx+18h], rsi
0x180006439  test    rdi, rdi
0x18000643c  jz      short loc_180006447
0x18000643e  mov     rcx, rdi; SRWLock
0x180006441  call    cs:__imp_ReleaseSRWLockExclusive
0x180006447  mov     ecx, ebp; dwErrCode
0x180006449  call    cs:__imp_SetLastError
0x18000644f  cmp     qword ptr [rbx+18h], 0
0x180006454  setnz   al
0x180006457  add     rsp, 28h
0x18000645b  pop     rdi
0x18000645c  pop     rsi
0x18000645d  pop     rbp
0x18000645e  pop     rbx
0x18000645f  retn
```
