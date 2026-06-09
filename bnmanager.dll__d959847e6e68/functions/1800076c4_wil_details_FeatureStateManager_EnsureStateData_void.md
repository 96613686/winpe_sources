# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1800076c4`
- end: `0x180007770`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800024b0`
- `0x180009424`
- `0x18000b0cc`
- `0x18000b6a0`

## callees

- `0x180005e7c`
- `0x1800076c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007759`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007759`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007738`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007738`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007751`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007751`

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
0x1800076c4  push    rbx
0x1800076c6  push    rbp
0x1800076c7  push    rsi
0x1800076c8  push    rdi
0x1800076c9  sub     rsp, 28h
0x1800076cd  cmp     qword ptr [rcx+18h], 0
0x1800076d2  mov     rbx, rcx
0x1800076d5  jnz     loc_18000775F
0x1800076db  call    cs:__imp_GetLastError
0x1800076e1  cmp     qword ptr [rbx+18h], 0
0x1800076e6  mov     ebp, eax
0x1800076e8  jz      short loc_1800076EE
0x1800076ea  xor     esi, esi
0x1800076ec  jmp     short loc_180007731
0x1800076ee  cmp     qword ptr [rbx+10h], 0
0x1800076f3  jnz     short loc_180007720
0x1800076f5  mov     rcx, [rbx+8]
0x1800076f9  lea     rdx, [rsp+48h+arg_0]
0x1800076fe  mov     [rsp+48h+arg_0], 0
0x180007707  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18000770c  test    eax, eax
0x18000770e  js      short loc_180007720
0x180007710  cmp     qword ptr [rbx+10h], 0
0x180007715  jnz     short loc_180007720
0x180007717  mov     rax, [rsp+48h+arg_0]
0x18000771c  mov     [rbx+10h], rax
0x180007720  mov     rax, [rbx+10h]
0x180007724  lea     rcx, [rax+20h]
0x180007728  neg     rax
0x18000772b  sbb     rsi, rsi
0x18000772e  and     rsi, rcx
0x180007731  lea     rdi, [rbx+20h]
0x180007735  mov     rcx, rdi; SRWLock
0x180007738  call    cs:__imp_AcquireSRWLockExclusive
0x18000773e  cmp     qword ptr [rbx+18h], 0
0x180007743  jnz     short loc_180007749
0x180007745  mov     [rbx+18h], rsi
0x180007749  test    rdi, rdi
0x18000774c  jz      short loc_180007757
0x18000774e  mov     rcx, rdi; SRWLock
0x180007751  call    cs:__imp_ReleaseSRWLockExclusive
0x180007757  mov     ecx, ebp; dwErrCode
0x180007759  call    cs:__imp_SetLastError
0x18000775f  cmp     qword ptr [rbx+18h], 0
0x180007764  setnz   al
0x180007767  add     rsp, 28h
0x18000776b  pop     rdi
0x18000776c  pop     rsi
0x18000776d  pop     rbp
0x18000776e  pop     rbx
0x18000776f  retn
```
