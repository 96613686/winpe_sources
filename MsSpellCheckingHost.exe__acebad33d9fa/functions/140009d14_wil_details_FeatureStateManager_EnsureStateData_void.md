# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x140009d14`
- end: `0x140009dc0`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140006cd0`
- `0x14000c364`
- `0x14000dde0`
- `0x14000e420`

## callees

- `0x14000942c`
- `0x140009d14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009d2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009d2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009da9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009da9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009d88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009d88`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009da1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009da1`

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
0x140009d14  push    rbx
0x140009d16  push    rbp
0x140009d17  push    rsi
0x140009d18  push    rdi
0x140009d19  sub     rsp, 28h
0x140009d1d  cmp     qword ptr [rcx+18h], 0
0x140009d22  mov     rbx, rcx
0x140009d25  jnz     loc_140009DAF
0x140009d2b  call    cs:__imp_GetLastError
0x140009d31  cmp     qword ptr [rbx+18h], 0
0x140009d36  mov     ebp, eax
0x140009d38  jz      short loc_140009D3E
0x140009d3a  xor     esi, esi
0x140009d3c  jmp     short loc_140009D81
0x140009d3e  cmp     qword ptr [rbx+10h], 0
0x140009d43  jnz     short loc_140009D70
0x140009d45  mov     rcx, [rbx+8]
0x140009d49  lea     rdx, [rsp+48h+arg_0]
0x140009d4e  mov     [rsp+48h+arg_0], 0
0x140009d57  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x140009d5c  test    eax, eax
0x140009d5e  js      short loc_140009D70
0x140009d60  cmp     qword ptr [rbx+10h], 0
0x140009d65  jnz     short loc_140009D70
0x140009d67  mov     rax, [rsp+48h+arg_0]
0x140009d6c  mov     [rbx+10h], rax
0x140009d70  mov     rax, [rbx+10h]
0x140009d74  lea     rcx, [rax+20h]
0x140009d78  neg     rax
0x140009d7b  sbb     rsi, rsi
0x140009d7e  and     rsi, rcx
0x140009d81  lea     rdi, [rbx+20h]
0x140009d85  mov     rcx, rdi; SRWLock
0x140009d88  call    cs:__imp_AcquireSRWLockExclusive
0x140009d8e  cmp     qword ptr [rbx+18h], 0
0x140009d93  jnz     short loc_140009D99
0x140009d95  mov     [rbx+18h], rsi
0x140009d99  test    rdi, rdi
0x140009d9c  jz      short loc_140009DA7
0x140009d9e  mov     rcx, rdi; SRWLock
0x140009da1  call    cs:__imp_ReleaseSRWLockExclusive
0x140009da7  mov     ecx, ebp; dwErrCode
0x140009da9  call    cs:__imp_SetLastError
0x140009daf  cmp     qword ptr [rbx+18h], 0
0x140009db4  setnz   al
0x140009db7  add     rsp, 28h
0x140009dbb  pop     rdi
0x140009dbc  pop     rsi
0x140009dbd  pop     rbp
0x140009dbe  pop     rbx
0x140009dbf  retn
```
