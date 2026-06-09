# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180004634`
- end: `0x1800046e0`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002790`
- `0x180006164`
- `0x180007b84`
- `0x180008150`

## callees

- `0x180003f9c`
- `0x180004634`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800046a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800046a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800046c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800046c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000464b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000464b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800046c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800046c9`

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
0x180004634  push    rbx
0x180004636  push    rbp
0x180004637  push    rsi
0x180004638  push    rdi
0x180004639  sub     rsp, 28h
0x18000463d  cmp     qword ptr [rcx+18h], 0
0x180004642  mov     rbx, rcx
0x180004645  jnz     loc_1800046CF
0x18000464b  call    cs:__imp_GetLastError
0x180004651  cmp     qword ptr [rbx+18h], 0
0x180004656  mov     ebp, eax
0x180004658  jz      short loc_18000465E
0x18000465a  xor     esi, esi
0x18000465c  jmp     short loc_1800046A1
0x18000465e  cmp     qword ptr [rbx+10h], 0
0x180004663  jnz     short loc_180004690
0x180004665  mov     rcx, [rbx+8]
0x180004669  lea     rdx, [rsp+48h+arg_0]
0x18000466e  mov     [rsp+48h+arg_0], 0
0x180004677  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18000467c  test    eax, eax
0x18000467e  js      short loc_180004690
0x180004680  cmp     qword ptr [rbx+10h], 0
0x180004685  jnz     short loc_180004690
0x180004687  mov     rax, [rsp+48h+arg_0]
0x18000468c  mov     [rbx+10h], rax
0x180004690  mov     rax, [rbx+10h]
0x180004694  lea     rcx, [rax+20h]
0x180004698  neg     rax
0x18000469b  sbb     rsi, rsi
0x18000469e  and     rsi, rcx
0x1800046a1  lea     rdi, [rbx+20h]
0x1800046a5  mov     rcx, rdi; SRWLock
0x1800046a8  call    cs:__imp_AcquireSRWLockExclusive
0x1800046ae  cmp     qword ptr [rbx+18h], 0
0x1800046b3  jnz     short loc_1800046B9
0x1800046b5  mov     [rbx+18h], rsi
0x1800046b9  test    rdi, rdi
0x1800046bc  jz      short loc_1800046C7
0x1800046be  mov     rcx, rdi; SRWLock
0x1800046c1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800046c7  mov     ecx, ebp; dwErrCode
0x1800046c9  call    cs:__imp_SetLastError
0x1800046cf  cmp     qword ptr [rbx+18h], 0
0x1800046d4  setnz   al
0x1800046d7  add     rsp, 28h
0x1800046db  pop     rdi
0x1800046dc  pop     rsi
0x1800046dd  pop     rbp
0x1800046de  pop     rbx
0x1800046df  retn
```
