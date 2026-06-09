# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180004674`
- end: `0x180004720`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002920`
- `0x180006584`
- `0x180007b84`
- `0x1800081a0`

## callees

- `0x180003f94`
- `0x180004674`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004701`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004701`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800046e8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800046e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004709`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000468b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000468b`

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
0x180004674  push    rbx
0x180004676  push    rbp
0x180004677  push    rsi
0x180004678  push    rdi
0x180004679  sub     rsp, 28h
0x18000467d  cmp     qword ptr [rcx+18h], 0
0x180004682  mov     rbx, rcx
0x180004685  jnz     loc_18000470F
0x18000468b  call    cs:__imp_GetLastError
0x180004691  cmp     qword ptr [rbx+18h], 0
0x180004696  mov     ebp, eax
0x180004698  jz      short loc_18000469E
0x18000469a  xor     esi, esi
0x18000469c  jmp     short loc_1800046E1
0x18000469e  cmp     qword ptr [rbx+10h], 0
0x1800046a3  jnz     short loc_1800046D0
0x1800046a5  mov     rcx, [rbx+8]
0x1800046a9  lea     rdx, [rsp+48h+arg_0]
0x1800046ae  mov     [rsp+48h+arg_0], 0
0x1800046b7  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x1800046bc  test    eax, eax
0x1800046be  js      short loc_1800046D0
0x1800046c0  cmp     qword ptr [rbx+10h], 0
0x1800046c5  jnz     short loc_1800046D0
0x1800046c7  mov     rax, [rsp+48h+arg_0]
0x1800046cc  mov     [rbx+10h], rax
0x1800046d0  mov     rax, [rbx+10h]
0x1800046d4  lea     rcx, [rax+20h]
0x1800046d8  neg     rax
0x1800046db  sbb     rsi, rsi
0x1800046de  and     rsi, rcx
0x1800046e1  lea     rdi, [rbx+20h]
0x1800046e5  mov     rcx, rdi; SRWLock
0x1800046e8  call    cs:__imp_AcquireSRWLockExclusive
0x1800046ee  cmp     qword ptr [rbx+18h], 0
0x1800046f3  jnz     short loc_1800046F9
0x1800046f5  mov     [rbx+18h], rsi
0x1800046f9  test    rdi, rdi
0x1800046fc  jz      short loc_180004707
0x1800046fe  mov     rcx, rdi; SRWLock
0x180004701  call    cs:__imp_ReleaseSRWLockExclusive
0x180004707  mov     ecx, ebp; dwErrCode
0x180004709  call    cs:__imp_SetLastError
0x18000470f  cmp     qword ptr [rbx+18h], 0
0x180004714  setnz   al
0x180004717  add     rsp, 28h
0x18000471b  pop     rdi
0x18000471c  pop     rsi
0x18000471d  pop     rbp
0x18000471e  pop     rbx
0x18000471f  retn
```
