# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x18000a498`
- end: `0x18000a544`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180009470`
- `0x18000d09c`
- `0x18000e040`
- `0x18000e610`

## callees

- `0x180009ed8`
- `0x18000a498`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a525`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a525`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a50c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a50c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a52d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a52d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4af`

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
0x18000a498  push    rbx
0x18000a49a  push    rbp
0x18000a49b  push    rsi
0x18000a49c  push    rdi
0x18000a49d  sub     rsp, 28h
0x18000a4a1  cmp     qword ptr [rcx+18h], 0
0x18000a4a6  mov     rbx, rcx
0x18000a4a9  jnz     loc_18000A533
0x18000a4af  call    cs:__imp_GetLastError
0x18000a4b5  cmp     qword ptr [rbx+18h], 0
0x18000a4ba  mov     ebp, eax
0x18000a4bc  jz      short loc_18000A4C2
0x18000a4be  xor     esi, esi
0x18000a4c0  jmp     short loc_18000A505
0x18000a4c2  cmp     qword ptr [rbx+10h], 0
0x18000a4c7  jnz     short loc_18000A4F4
0x18000a4c9  mov     rcx, [rbx+8]
0x18000a4cd  lea     rdx, [rsp+48h+arg_0]
0x18000a4d2  mov     [rsp+48h+arg_0], 0
0x18000a4db  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18000a4e0  test    eax, eax
0x18000a4e2  js      short loc_18000A4F4
0x18000a4e4  cmp     qword ptr [rbx+10h], 0
0x18000a4e9  jnz     short loc_18000A4F4
0x18000a4eb  mov     rax, [rsp+48h+arg_0]
0x18000a4f0  mov     [rbx+10h], rax
0x18000a4f4  mov     rax, [rbx+10h]
0x18000a4f8  lea     rcx, [rax+20h]
0x18000a4fc  neg     rax
0x18000a4ff  sbb     rsi, rsi
0x18000a502  and     rsi, rcx
0x18000a505  lea     rdi, [rbx+20h]
0x18000a509  mov     rcx, rdi; SRWLock
0x18000a50c  call    cs:__imp_AcquireSRWLockExclusive
0x18000a512  cmp     qword ptr [rbx+18h], 0
0x18000a517  jnz     short loc_18000A51D
0x18000a519  mov     [rbx+18h], rsi
0x18000a51d  test    rdi, rdi
0x18000a520  jz      short loc_18000A52B
0x18000a522  mov     rcx, rdi; SRWLock
0x18000a525  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a52b  mov     ecx, ebp; dwErrCode
0x18000a52d  call    cs:__imp_SetLastError
0x18000a533  cmp     qword ptr [rbx+18h], 0
0x18000a538  setnz   al
0x18000a53b  add     rsp, 28h
0x18000a53f  pop     rdi
0x18000a540  pop     rsi
0x18000a541  pop     rbp
0x18000a542  pop     rbx
0x18000a543  retn
```
