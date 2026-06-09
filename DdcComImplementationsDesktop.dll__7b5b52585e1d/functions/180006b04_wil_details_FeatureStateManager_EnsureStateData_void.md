# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180006b04`
- end: `0x180006bb0`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004cf0`
- `0x180008634`
- `0x18000a054`
- `0x18000a620`

## callees

- `0x180006460`
- `0x180006b04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b99`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b99`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b91`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b91`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006b78`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006b78`

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
0x180006b04  push    rbx
0x180006b06  push    rbp
0x180006b07  push    rsi
0x180006b08  push    rdi
0x180006b09  sub     rsp, 28h
0x180006b0d  cmp     qword ptr [rcx+18h], 0
0x180006b12  mov     rbx, rcx
0x180006b15  jnz     loc_180006B9F
0x180006b1b  call    cs:__imp_GetLastError
0x180006b21  cmp     qword ptr [rbx+18h], 0
0x180006b26  mov     ebp, eax
0x180006b28  jz      short loc_180006B2E
0x180006b2a  xor     esi, esi
0x180006b2c  jmp     short loc_180006B71
0x180006b2e  cmp     qword ptr [rbx+10h], 0
0x180006b33  jnz     short loc_180006B60
0x180006b35  mov     rcx, [rbx+8]
0x180006b39  lea     rdx, [rsp+48h+arg_0]
0x180006b3e  mov     [rsp+48h+arg_0], 0
0x180006b47  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180006b4c  test    eax, eax
0x180006b4e  js      short loc_180006B60
0x180006b50  cmp     qword ptr [rbx+10h], 0
0x180006b55  jnz     short loc_180006B60
0x180006b57  mov     rax, [rsp+48h+arg_0]
0x180006b5c  mov     [rbx+10h], rax
0x180006b60  mov     rax, [rbx+10h]
0x180006b64  lea     rcx, [rax+20h]
0x180006b68  neg     rax
0x180006b6b  sbb     rsi, rsi
0x180006b6e  and     rsi, rcx
0x180006b71  lea     rdi, [rbx+20h]
0x180006b75  mov     rcx, rdi; SRWLock
0x180006b78  call    cs:__imp_AcquireSRWLockExclusive
0x180006b7e  cmp     qword ptr [rbx+18h], 0
0x180006b83  jnz     short loc_180006B89
0x180006b85  mov     [rbx+18h], rsi
0x180006b89  test    rdi, rdi
0x180006b8c  jz      short loc_180006B97
0x180006b8e  mov     rcx, rdi; SRWLock
0x180006b91  call    cs:__imp_ReleaseSRWLockExclusive
0x180006b97  mov     ecx, ebp; dwErrCode
0x180006b99  call    cs:__imp_SetLastError
0x180006b9f  cmp     qword ptr [rbx+18h], 0
0x180006ba4  setnz   al
0x180006ba7  add     rsp, 28h
0x180006bab  pop     rdi
0x180006bac  pop     rsi
0x180006bad  pop     rbp
0x180006bae  pop     rbx
0x180006baf  retn
```
