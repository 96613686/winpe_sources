# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180008084`
- end: `0x180008130`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007180`
- `0x180008ff0`
- `0x18000a358`
- `0x18000a680`

## callees

- `0x180007c8c`
- `0x180008084`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008111`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008111`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800080f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800080f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000809b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000809b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008119`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008119`

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
0x180008084  push    rbx
0x180008086  push    rbp
0x180008087  push    rsi
0x180008088  push    rdi
0x180008089  sub     rsp, 28h
0x18000808d  cmp     qword ptr [rcx+18h], 0
0x180008092  mov     rbx, rcx
0x180008095  jnz     loc_18000811F
0x18000809b  call    cs:__imp_GetLastError
0x1800080a1  cmp     qword ptr [rbx+18h], 0
0x1800080a6  mov     ebp, eax
0x1800080a8  jz      short loc_1800080AE
0x1800080aa  xor     esi, esi
0x1800080ac  jmp     short loc_1800080F1
0x1800080ae  cmp     qword ptr [rbx+10h], 0
0x1800080b3  jnz     short loc_1800080E0
0x1800080b5  mov     rcx, [rbx+8]
0x1800080b9  lea     rdx, [rsp+48h+arg_0]
0x1800080be  mov     [rsp+48h+arg_0], 0
0x1800080c7  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x1800080cc  test    eax, eax
0x1800080ce  js      short loc_1800080E0
0x1800080d0  cmp     qword ptr [rbx+10h], 0
0x1800080d5  jnz     short loc_1800080E0
0x1800080d7  mov     rax, [rsp+48h+arg_0]
0x1800080dc  mov     [rbx+10h], rax
0x1800080e0  mov     rax, [rbx+10h]
0x1800080e4  lea     rcx, [rax+20h]
0x1800080e8  neg     rax
0x1800080eb  sbb     rsi, rsi
0x1800080ee  and     rsi, rcx
0x1800080f1  lea     rdi, [rbx+20h]
0x1800080f5  mov     rcx, rdi; SRWLock
0x1800080f8  call    cs:__imp_AcquireSRWLockExclusive
0x1800080fe  cmp     qword ptr [rbx+18h], 0
0x180008103  jnz     short loc_180008109
0x180008105  mov     [rbx+18h], rsi
0x180008109  test    rdi, rdi
0x18000810c  jz      short loc_180008117
0x18000810e  mov     rcx, rdi; SRWLock
0x180008111  call    cs:__imp_ReleaseSRWLockExclusive
0x180008117  mov     ecx, ebp; dwErrCode
0x180008119  call    cs:__imp_SetLastError
0x18000811f  cmp     qword ptr [rbx+18h], 0
0x180008124  setnz   al
0x180008127  add     rsp, 28h
0x18000812b  pop     rdi
0x18000812c  pop     rsi
0x18000812d  pop     rbp
0x18000812e  pop     rbx
0x18000812f  retn
```
