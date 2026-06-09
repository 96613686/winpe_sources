# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180004624`
- end: `0x1800046d0`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800026e0`
- `0x180006414`
- `0x180008200`
- `0x180008780`

## callees

- `0x180003e1c`
- `0x180004624`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000463b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000463b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800046b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800046b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800046b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800046b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004698`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004698`

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
0x180004624  push    rbx
0x180004626  push    rbp
0x180004627  push    rsi
0x180004628  push    rdi
0x180004629  sub     rsp, 28h
0x18000462d  cmp     qword ptr [rcx+18h], 0
0x180004632  mov     rbx, rcx
0x180004635  jnz     loc_1800046BF
0x18000463b  call    cs:__imp_GetLastError
0x180004641  cmp     qword ptr [rbx+18h], 0
0x180004646  mov     ebp, eax
0x180004648  jz      short loc_18000464E
0x18000464a  xor     esi, esi
0x18000464c  jmp     short loc_180004691
0x18000464e  cmp     qword ptr [rbx+10h], 0
0x180004653  jnz     short loc_180004680
0x180004655  mov     rcx, [rbx+8]
0x180004659  lea     rdx, [rsp+48h+arg_0]
0x18000465e  mov     [rsp+48h+arg_0], 0
0x180004667  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18000466c  test    eax, eax
0x18000466e  js      short loc_180004680
0x180004670  cmp     qword ptr [rbx+10h], 0
0x180004675  jnz     short loc_180004680
0x180004677  mov     rax, [rsp+48h+arg_0]
0x18000467c  mov     [rbx+10h], rax
0x180004680  mov     rax, [rbx+10h]
0x180004684  lea     rcx, [rax+20h]
0x180004688  neg     rax
0x18000468b  sbb     rsi, rsi
0x18000468e  and     rsi, rcx
0x180004691  lea     rdi, [rbx+20h]
0x180004695  mov     rcx, rdi; SRWLock
0x180004698  call    cs:__imp_AcquireSRWLockExclusive
0x18000469e  cmp     qword ptr [rbx+18h], 0
0x1800046a3  jnz     short loc_1800046A9
0x1800046a5  mov     [rbx+18h], rsi
0x1800046a9  test    rdi, rdi
0x1800046ac  jz      short loc_1800046B7
0x1800046ae  mov     rcx, rdi; SRWLock
0x1800046b1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800046b7  mov     ecx, ebp; dwErrCode
0x1800046b9  call    cs:__imp_SetLastError
0x1800046bf  cmp     qword ptr [rbx+18h], 0
0x1800046c4  setnz   al
0x1800046c7  add     rsp, 28h
0x1800046cb  pop     rdi
0x1800046cc  pop     rsi
0x1800046cd  pop     rbp
0x1800046ce  pop     rbx
0x1800046cf  retn
```
