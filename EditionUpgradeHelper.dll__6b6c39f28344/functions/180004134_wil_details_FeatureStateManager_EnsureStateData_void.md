# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180004134`
- end: `0x1800041e0`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002630`
- `0x180005c64`
- `0x1800070ac`
- `0x180007640`

## callees

- `0x180003a98`
- `0x180004134`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800041a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800041a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800041c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800041c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000414b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000414b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800041c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800041c9`

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
0x180004134  push    rbx
0x180004136  push    rbp
0x180004137  push    rsi
0x180004138  push    rdi
0x180004139  sub     rsp, 28h
0x18000413d  cmp     qword ptr [rcx+18h], 0
0x180004142  mov     rbx, rcx
0x180004145  jnz     loc_1800041CF
0x18000414b  call    cs:__imp_GetLastError
0x180004151  cmp     qword ptr [rbx+18h], 0
0x180004156  mov     ebp, eax
0x180004158  jz      short loc_18000415E
0x18000415a  xor     esi, esi
0x18000415c  jmp     short loc_1800041A1
0x18000415e  cmp     qword ptr [rbx+10h], 0
0x180004163  jnz     short loc_180004190
0x180004165  mov     rcx, [rbx+8]
0x180004169  lea     rdx, [rsp+48h+arg_0]
0x18000416e  mov     [rsp+48h+arg_0], 0
0x180004177  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18000417c  test    eax, eax
0x18000417e  js      short loc_180004190
0x180004180  cmp     qword ptr [rbx+10h], 0
0x180004185  jnz     short loc_180004190
0x180004187  mov     rax, [rsp+48h+arg_0]
0x18000418c  mov     [rbx+10h], rax
0x180004190  mov     rax, [rbx+10h]
0x180004194  lea     rcx, [rax+20h]
0x180004198  neg     rax
0x18000419b  sbb     rsi, rsi
0x18000419e  and     rsi, rcx
0x1800041a1  lea     rdi, [rbx+20h]
0x1800041a5  mov     rcx, rdi; SRWLock
0x1800041a8  call    cs:__imp_AcquireSRWLockExclusive
0x1800041ae  cmp     qword ptr [rbx+18h], 0
0x1800041b3  jnz     short loc_1800041B9
0x1800041b5  mov     [rbx+18h], rsi
0x1800041b9  test    rdi, rdi
0x1800041bc  jz      short loc_1800041C7
0x1800041be  mov     rcx, rdi; SRWLock
0x1800041c1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800041c7  mov     ecx, ebp; dwErrCode
0x1800041c9  call    cs:__imp_SetLastError
0x1800041cf  cmp     qword ptr [rbx+18h], 0
0x1800041d4  setnz   al
0x1800041d7  add     rsp, 28h
0x1800041db  pop     rdi
0x1800041dc  pop     rsi
0x1800041dd  pop     rbp
0x1800041de  pop     rbx
0x1800041df  retn
```
