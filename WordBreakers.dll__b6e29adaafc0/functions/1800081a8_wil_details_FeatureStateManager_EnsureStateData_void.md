# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1800081a8`
- end: `0x180008254`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800076e0`
- `0x18000983c`
- `0x18000a8e4`
- `0x18000abf0`

## callees

- `0x180007dd8`
- `0x1800081a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000823d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000823d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008235`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008235`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000821c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000821c`

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
0x1800081a8  push    rbx
0x1800081aa  push    rbp
0x1800081ab  push    rsi
0x1800081ac  push    rdi
0x1800081ad  sub     rsp, 28h
0x1800081b1  cmp     qword ptr [rcx+18h], 0
0x1800081b6  mov     rbx, rcx
0x1800081b9  jnz     loc_180008243
0x1800081bf  call    cs:__imp_GetLastError
0x1800081c5  cmp     qword ptr [rbx+18h], 0
0x1800081ca  mov     ebp, eax
0x1800081cc  jz      short loc_1800081D2
0x1800081ce  xor     esi, esi
0x1800081d0  jmp     short loc_180008215
0x1800081d2  cmp     qword ptr [rbx+10h], 0
0x1800081d7  jnz     short loc_180008204
0x1800081d9  mov     rcx, [rbx+8]
0x1800081dd  lea     rdx, [rsp+48h+arg_0]
0x1800081e2  mov     [rsp+48h+arg_0], 0
0x1800081eb  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x1800081f0  test    eax, eax
0x1800081f2  js      short loc_180008204
0x1800081f4  cmp     qword ptr [rbx+10h], 0
0x1800081f9  jnz     short loc_180008204
0x1800081fb  mov     rax, [rsp+48h+arg_0]
0x180008200  mov     [rbx+10h], rax
0x180008204  mov     rax, [rbx+10h]
0x180008208  lea     rcx, [rax+20h]
0x18000820c  neg     rax
0x18000820f  sbb     rsi, rsi
0x180008212  and     rsi, rcx
0x180008215  lea     rdi, [rbx+20h]
0x180008219  mov     rcx, rdi; SRWLock
0x18000821c  call    cs:__imp_AcquireSRWLockExclusive
0x180008222  cmp     qword ptr [rbx+18h], 0
0x180008227  jnz     short loc_18000822D
0x180008229  mov     [rbx+18h], rsi
0x18000822d  test    rdi, rdi
0x180008230  jz      short loc_18000823B
0x180008232  mov     rcx, rdi; SRWLock
0x180008235  call    cs:__imp_ReleaseSRWLockExclusive
0x18000823b  mov     ecx, ebp; dwErrCode
0x18000823d  call    cs:__imp_SetLastError
0x180008243  cmp     qword ptr [rbx+18h], 0
0x180008248  setnz   al
0x18000824b  add     rsp, 28h
0x18000824f  pop     rdi
0x180008250  pop     rsi
0x180008251  pop     rbp
0x180008252  pop     rbx
0x180008253  retn
```
