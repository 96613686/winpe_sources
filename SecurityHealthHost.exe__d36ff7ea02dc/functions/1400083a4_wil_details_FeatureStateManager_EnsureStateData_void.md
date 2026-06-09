# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1400083a4`
- end: `0x140008450`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400069f0`
- `0x140009680`
- `0x14000b07c`
- `0x14000b650`

## callees

- `0x140007cbc`
- `0x1400083a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400083bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400083bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008439`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008439`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008431`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008431`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008418`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008418`

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
0x1400083a4  push    rbx
0x1400083a6  push    rbp
0x1400083a7  push    rsi
0x1400083a8  push    rdi
0x1400083a9  sub     rsp, 28h
0x1400083ad  cmp     qword ptr [rcx+18h], 0
0x1400083b2  mov     rbx, rcx
0x1400083b5  jnz     loc_14000843F
0x1400083bb  call    cs:__imp_GetLastError
0x1400083c1  cmp     qword ptr [rbx+18h], 0
0x1400083c6  mov     ebp, eax
0x1400083c8  jz      short loc_1400083CE
0x1400083ca  xor     esi, esi
0x1400083cc  jmp     short loc_140008411
0x1400083ce  cmp     qword ptr [rbx+10h], 0
0x1400083d3  jnz     short loc_140008400
0x1400083d5  mov     rcx, [rbx+8]
0x1400083d9  lea     rdx, [rsp+48h+arg_0]
0x1400083de  mov     [rsp+48h+arg_0], 0
0x1400083e7  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x1400083ec  test    eax, eax
0x1400083ee  js      short loc_140008400
0x1400083f0  cmp     qword ptr [rbx+10h], 0
0x1400083f5  jnz     short loc_140008400
0x1400083f7  mov     rax, [rsp+48h+arg_0]
0x1400083fc  mov     [rbx+10h], rax
0x140008400  mov     rax, [rbx+10h]
0x140008404  lea     rcx, [rax+20h]
0x140008408  neg     rax
0x14000840b  sbb     rsi, rsi
0x14000840e  and     rsi, rcx
0x140008411  lea     rdi, [rbx+20h]
0x140008415  mov     rcx, rdi; SRWLock
0x140008418  call    cs:__imp_AcquireSRWLockExclusive
0x14000841e  cmp     qword ptr [rbx+18h], 0
0x140008423  jnz     short loc_140008429
0x140008425  mov     [rbx+18h], rsi
0x140008429  test    rdi, rdi
0x14000842c  jz      short loc_140008437
0x14000842e  mov     rcx, rdi; SRWLock
0x140008431  call    cs:__imp_ReleaseSRWLockExclusive
0x140008437  mov     ecx, ebp; dwErrCode
0x140008439  call    cs:__imp_SetLastError
0x14000843f  cmp     qword ptr [rbx+18h], 0
0x140008444  setnz   al
0x140008447  add     rsp, 28h
0x14000844b  pop     rdi
0x14000844c  pop     rsi
0x14000844d  pop     rbp
0x14000844e  pop     rbx
0x14000844f  retn
```
