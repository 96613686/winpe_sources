# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x140009a38`
- end: `0x140009ae4`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140007e60`
- `0x14000b064`
- `0x14000c580`
- `0x14000d7a0`

## callees

- `0x14000936c`
- `0x140009a38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009a4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009a4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009acd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009acd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009aac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009aac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009ac5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009ac5`

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
0x140009a38  push    rbx
0x140009a3a  push    rbp
0x140009a3b  push    rsi
0x140009a3c  push    rdi
0x140009a3d  sub     rsp, 28h
0x140009a41  cmp     qword ptr [rcx+18h], 0
0x140009a46  mov     rbx, rcx
0x140009a49  jnz     loc_140009AD3
0x140009a4f  call    cs:__imp_GetLastError
0x140009a55  cmp     qword ptr [rbx+18h], 0
0x140009a5a  mov     ebp, eax
0x140009a5c  jz      short loc_140009A62
0x140009a5e  xor     esi, esi
0x140009a60  jmp     short loc_140009AA5
0x140009a62  cmp     qword ptr [rbx+10h], 0
0x140009a67  jnz     short loc_140009A94
0x140009a69  mov     rcx, [rbx+8]
0x140009a6d  lea     rdx, [rsp+48h+arg_0]
0x140009a72  mov     [rsp+48h+arg_0], 0
0x140009a7b  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x140009a80  test    eax, eax
0x140009a82  js      short loc_140009A94
0x140009a84  cmp     qword ptr [rbx+10h], 0
0x140009a89  jnz     short loc_140009A94
0x140009a8b  mov     rax, [rsp+48h+arg_0]
0x140009a90  mov     [rbx+10h], rax
0x140009a94  mov     rax, [rbx+10h]
0x140009a98  lea     rcx, [rax+20h]
0x140009a9c  neg     rax
0x140009a9f  sbb     rsi, rsi
0x140009aa2  and     rsi, rcx
0x140009aa5  lea     rdi, [rbx+20h]
0x140009aa9  mov     rcx, rdi; SRWLock
0x140009aac  call    cs:__imp_AcquireSRWLockExclusive
0x140009ab2  cmp     qword ptr [rbx+18h], 0
0x140009ab7  jnz     short loc_140009ABD
0x140009ab9  mov     [rbx+18h], rsi
0x140009abd  test    rdi, rdi
0x140009ac0  jz      short loc_140009ACB
0x140009ac2  mov     rcx, rdi; SRWLock
0x140009ac5  call    cs:__imp_ReleaseSRWLockExclusive
0x140009acb  mov     ecx, ebp; dwErrCode
0x140009acd  call    cs:__imp_SetLastError
0x140009ad3  cmp     qword ptr [rbx+18h], 0
0x140009ad8  setnz   al
0x140009adb  add     rsp, 28h
0x140009adf  pop     rdi
0x140009ae0  pop     rsi
0x140009ae1  pop     rbp
0x140009ae2  pop     rbx
0x140009ae3  retn
```
