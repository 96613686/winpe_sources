# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180008d84`
- end: `0x180008e30`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007610`
- `0x18000aab8`
- `0x18000c308`
- `0x18000c740`

## callees

- `0x18000896c`
- `0x180008d84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008e11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008e11`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008df8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008df8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008e19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008e19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d9b`

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
0x180008d84  push    rbx
0x180008d86  push    rbp
0x180008d87  push    rsi
0x180008d88  push    rdi
0x180008d89  sub     rsp, 28h
0x180008d8d  cmp     qword ptr [rcx+18h], 0
0x180008d92  mov     rbx, rcx
0x180008d95  jnz     loc_180008E1F
0x180008d9b  call    cs:__imp_GetLastError
0x180008da1  cmp     qword ptr [rbx+18h], 0
0x180008da6  mov     ebp, eax
0x180008da8  jz      short loc_180008DAE
0x180008daa  xor     esi, esi
0x180008dac  jmp     short loc_180008DF1
0x180008dae  cmp     qword ptr [rbx+10h], 0
0x180008db3  jnz     short loc_180008DE0
0x180008db5  mov     rcx, [rbx+8]
0x180008db9  lea     rdx, [rsp+48h+arg_0]
0x180008dbe  mov     [rsp+48h+arg_0], 0
0x180008dc7  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180008dcc  test    eax, eax
0x180008dce  js      short loc_180008DE0
0x180008dd0  cmp     qword ptr [rbx+10h], 0
0x180008dd5  jnz     short loc_180008DE0
0x180008dd7  mov     rax, [rsp+48h+arg_0]
0x180008ddc  mov     [rbx+10h], rax
0x180008de0  mov     rax, [rbx+10h]
0x180008de4  lea     rcx, [rax+20h]
0x180008de8  neg     rax
0x180008deb  sbb     rsi, rsi
0x180008dee  and     rsi, rcx
0x180008df1  lea     rdi, [rbx+20h]
0x180008df5  mov     rcx, rdi; SRWLock
0x180008df8  call    cs:__imp_AcquireSRWLockExclusive
0x180008dfe  cmp     qword ptr [rbx+18h], 0
0x180008e03  jnz     short loc_180008E09
0x180008e05  mov     [rbx+18h], rsi
0x180008e09  test    rdi, rdi
0x180008e0c  jz      short loc_180008E17
0x180008e0e  mov     rcx, rdi; SRWLock
0x180008e11  call    cs:__imp_ReleaseSRWLockExclusive
0x180008e17  mov     ecx, ebp; dwErrCode
0x180008e19  call    cs:__imp_SetLastError
0x180008e1f  cmp     qword ptr [rbx+18h], 0
0x180008e24  setnz   al
0x180008e27  add     rsp, 28h
0x180008e2b  pop     rdi
0x180008e2c  pop     rsi
0x180008e2d  pop     rbp
0x180008e2e  pop     rbx
0x180008e2f  retn
```
