# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x14000645c`
- end: `0x140006508`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140005980`
- `0x140006d90`
- `0x140007bb4`
- `0x140007ee0`

## callees

- `0x140006064`
- `0x14000645c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400064e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400064e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400064d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400064d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006473`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006473`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400064f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400064f1`

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
0x14000645c  push    rbx
0x14000645e  push    rbp
0x14000645f  push    rsi
0x140006460  push    rdi
0x140006461  sub     rsp, 28h
0x140006465  cmp     qword ptr [rcx+18h], 0
0x14000646a  mov     rbx, rcx
0x14000646d  jnz     loc_1400064F7
0x140006473  call    cs:__imp_GetLastError
0x140006479  cmp     qword ptr [rbx+18h], 0
0x14000647e  mov     ebp, eax
0x140006480  jz      short loc_140006486
0x140006482  xor     esi, esi
0x140006484  jmp     short loc_1400064C9
0x140006486  cmp     qword ptr [rbx+10h], 0
0x14000648b  jnz     short loc_1400064B8
0x14000648d  mov     rcx, [rbx+8]
0x140006491  lea     rdx, [rsp+48h+arg_0]
0x140006496  mov     [rsp+48h+arg_0], 0
0x14000649f  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x1400064a4  test    eax, eax
0x1400064a6  js      short loc_1400064B8
0x1400064a8  cmp     qword ptr [rbx+10h], 0
0x1400064ad  jnz     short loc_1400064B8
0x1400064af  mov     rax, [rsp+48h+arg_0]
0x1400064b4  mov     [rbx+10h], rax
0x1400064b8  mov     rax, [rbx+10h]
0x1400064bc  lea     rcx, [rax+20h]
0x1400064c0  neg     rax
0x1400064c3  sbb     rsi, rsi
0x1400064c6  and     rsi, rcx
0x1400064c9  lea     rdi, [rbx+20h]
0x1400064cd  mov     rcx, rdi; SRWLock
0x1400064d0  call    cs:__imp_AcquireSRWLockExclusive
0x1400064d6  cmp     qword ptr [rbx+18h], 0
0x1400064db  jnz     short loc_1400064E1
0x1400064dd  mov     [rbx+18h], rsi
0x1400064e1  test    rdi, rdi
0x1400064e4  jz      short loc_1400064EF
0x1400064e6  mov     rcx, rdi; SRWLock
0x1400064e9  call    cs:__imp_ReleaseSRWLockExclusive
0x1400064ef  mov     ecx, ebp; dwErrCode
0x1400064f1  call    cs:__imp_SetLastError
0x1400064f7  cmp     qword ptr [rbx+18h], 0
0x1400064fc  setnz   al
0x1400064ff  add     rsp, 28h
0x140006503  pop     rdi
0x140006504  pop     rsi
0x140006505  pop     rbp
0x140006506  pop     rbx
0x140006507  retn
```
