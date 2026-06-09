# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180004254`
- end: `0x180004300`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002360`
- `0x180005dc4`
- `0x180007934`
- `0x180007f20`

## callees

- `0x180003bbc`
- `0x180004254`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800042c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800042c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800042e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800042e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000426b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000426b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042e9`

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
0x180004254  push    rbx
0x180004256  push    rbp
0x180004257  push    rsi
0x180004258  push    rdi
0x180004259  sub     rsp, 28h
0x18000425d  cmp     qword ptr [rcx+18h], 0
0x180004262  mov     rbx, rcx
0x180004265  jnz     loc_1800042EF
0x18000426b  call    cs:__imp_GetLastError
0x180004271  cmp     qword ptr [rbx+18h], 0
0x180004276  mov     ebp, eax
0x180004278  jz      short loc_18000427E
0x18000427a  xor     esi, esi
0x18000427c  jmp     short loc_1800042C1
0x18000427e  cmp     qword ptr [rbx+10h], 0
0x180004283  jnz     short loc_1800042B0
0x180004285  mov     rcx, [rbx+8]
0x180004289  lea     rdx, [rsp+48h+arg_0]
0x18000428e  mov     [rsp+48h+arg_0], 0
0x180004297  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18000429c  test    eax, eax
0x18000429e  js      short loc_1800042B0
0x1800042a0  cmp     qword ptr [rbx+10h], 0
0x1800042a5  jnz     short loc_1800042B0
0x1800042a7  mov     rax, [rsp+48h+arg_0]
0x1800042ac  mov     [rbx+10h], rax
0x1800042b0  mov     rax, [rbx+10h]
0x1800042b4  lea     rcx, [rax+20h]
0x1800042b8  neg     rax
0x1800042bb  sbb     rsi, rsi
0x1800042be  and     rsi, rcx
0x1800042c1  lea     rdi, [rbx+20h]
0x1800042c5  mov     rcx, rdi; SRWLock
0x1800042c8  call    cs:__imp_AcquireSRWLockExclusive
0x1800042ce  cmp     qword ptr [rbx+18h], 0
0x1800042d3  jnz     short loc_1800042D9
0x1800042d5  mov     [rbx+18h], rsi
0x1800042d9  test    rdi, rdi
0x1800042dc  jz      short loc_1800042E7
0x1800042de  mov     rcx, rdi; SRWLock
0x1800042e1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800042e7  mov     ecx, ebp; dwErrCode
0x1800042e9  call    cs:__imp_SetLastError
0x1800042ef  cmp     qword ptr [rbx+18h], 0
0x1800042f4  setnz   al
0x1800042f7  add     rsp, 28h
0x1800042fb  pop     rdi
0x1800042fc  pop     rsi
0x1800042fd  pop     rbp
0x1800042fe  pop     rbx
0x1800042ff  retn
```
