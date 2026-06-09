# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x14000492c`
- end: `0x1400049d8`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002370`
- `0x140008634`
- `0x14000a998`
- `0x14000afe0`

## callees

- `0x14000421c`
- `0x14000492c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400049a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400049a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400049b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400049b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400049c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400049c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004943`

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
0x14000492c  push    rbx
0x14000492e  push    rbp
0x14000492f  push    rsi
0x140004930  push    rdi
0x140004931  sub     rsp, 28h
0x140004935  cmp     qword ptr [rcx+18h], 0
0x14000493a  mov     rbx, rcx
0x14000493d  jnz     loc_1400049C7
0x140004943  call    cs:__imp_GetLastError
0x140004949  cmp     qword ptr [rbx+18h], 0
0x14000494e  mov     ebp, eax
0x140004950  jz      short loc_140004956
0x140004952  xor     esi, esi
0x140004954  jmp     short loc_140004999
0x140004956  cmp     qword ptr [rbx+10h], 0
0x14000495b  jnz     short loc_140004988
0x14000495d  mov     rcx, [rbx+8]
0x140004961  lea     rdx, [rsp+48h+arg_0]
0x140004966  mov     [rsp+48h+arg_0], 0
0x14000496f  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x140004974  test    eax, eax
0x140004976  js      short loc_140004988
0x140004978  cmp     qword ptr [rbx+10h], 0
0x14000497d  jnz     short loc_140004988
0x14000497f  mov     rax, [rsp+48h+arg_0]
0x140004984  mov     [rbx+10h], rax
0x140004988  mov     rax, [rbx+10h]
0x14000498c  lea     rcx, [rax+20h]
0x140004990  neg     rax
0x140004993  sbb     rsi, rsi
0x140004996  and     rsi, rcx
0x140004999  lea     rdi, [rbx+20h]
0x14000499d  mov     rcx, rdi; SRWLock
0x1400049a0  call    cs:__imp_AcquireSRWLockExclusive
0x1400049a6  cmp     qword ptr [rbx+18h], 0
0x1400049ab  jnz     short loc_1400049B1
0x1400049ad  mov     [rbx+18h], rsi
0x1400049b1  test    rdi, rdi
0x1400049b4  jz      short loc_1400049BF
0x1400049b6  mov     rcx, rdi; SRWLock
0x1400049b9  call    cs:__imp_ReleaseSRWLockExclusive
0x1400049bf  mov     ecx, ebp; dwErrCode
0x1400049c1  call    cs:__imp_SetLastError
0x1400049c7  cmp     qword ptr [rbx+18h], 0
0x1400049cc  setnz   al
0x1400049cf  add     rsp, 28h
0x1400049d3  pop     rdi
0x1400049d4  pop     rsi
0x1400049d5  pop     rbp
0x1400049d6  pop     rbx
0x1400049d7  retn
```
