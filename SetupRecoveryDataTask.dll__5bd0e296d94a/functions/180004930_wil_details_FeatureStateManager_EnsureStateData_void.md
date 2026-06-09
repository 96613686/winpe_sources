# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180004930`
- end: `0x1800049dc`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800022d0`
- `0x1800076d4`
- `0x180009618`
- `0x180009c50`

## callees

- `0x180003ce4`
- `0x180004930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800049a4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800049a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800049bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800049bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004947`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004947`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800049c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800049c5`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureStateData(RTL_SRWLOCK *this)
{
  DWORD LastError; // ebp
  __int64 v3; // rsi
  __int64 Ptr; // rcx
  void *v6; // [rsp+20h] [rbp-38h] BYREF

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
0x180004930  push    rbx
0x180004932  push    rbp
0x180004933  push    rsi
0x180004934  push    rdi
0x180004935  sub     rsp, 38h
0x180004939  cmp     qword ptr [rcx+18h], 0
0x18000493e  mov     rbx, rcx
0x180004941  jnz     loc_1800049CB
0x180004947  call    cs:__imp_GetLastError
0x18000494d  cmp     qword ptr [rbx+18h], 0
0x180004952  mov     ebp, eax
0x180004954  jz      short loc_18000495A
0x180004956  xor     esi, esi
0x180004958  jmp     short loc_18000499D
0x18000495a  cmp     qword ptr [rbx+10h], 0
0x18000495f  jnz     short loc_18000498C
0x180004961  mov     rcx, [rbx+8]
0x180004965  lea     rdx, [rsp+58h+var_38]
0x18000496a  mov     [rsp+58h+var_38], 0
0x180004973  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180004978  test    eax, eax
0x18000497a  js      short loc_18000498C
0x18000497c  cmp     qword ptr [rbx+10h], 0
0x180004981  jnz     short loc_18000498C
0x180004983  mov     rax, [rsp+58h+var_38]
0x180004988  mov     [rbx+10h], rax
0x18000498c  mov     rax, [rbx+10h]
0x180004990  lea     rcx, [rax+20h]
0x180004994  neg     rax
0x180004997  sbb     rsi, rsi
0x18000499a  and     rsi, rcx
0x18000499d  lea     rdi, [rbx+20h]
0x1800049a1  mov     rcx, rdi; SRWLock
0x1800049a4  call    cs:__imp_AcquireSRWLockExclusive
0x1800049aa  cmp     qword ptr [rbx+18h], 0
0x1800049af  jnz     short loc_1800049B5
0x1800049b1  mov     [rbx+18h], rsi
0x1800049b5  test    rdi, rdi
0x1800049b8  jz      short loc_1800049C3
0x1800049ba  mov     rcx, rdi; SRWLock
0x1800049bd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800049c3  mov     ecx, ebp; dwErrCode
0x1800049c5  call    cs:__imp_SetLastError
0x1800049cb  cmp     qword ptr [rbx+18h], 0
0x1800049d0  setnz   al
0x1800049d3  add     rsp, 38h
0x1800049d7  pop     rdi
0x1800049d8  pop     rsi
0x1800049d9  pop     rbp
0x1800049da  pop     rbx
0x1800049db  retn
```
