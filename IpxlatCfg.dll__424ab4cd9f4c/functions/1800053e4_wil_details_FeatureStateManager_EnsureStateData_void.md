# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1800053e4`
- end: `0x180005490`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003350`
- `0x180007364`
- `0x180009040`
- `0x180009680`

## callees

- `0x180004d38`
- `0x1800053e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005479`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005458`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005458`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005471`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005471`

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
0x1800053e4  push    rbx
0x1800053e6  push    rbp
0x1800053e7  push    rsi
0x1800053e8  push    rdi
0x1800053e9  sub     rsp, 28h
0x1800053ed  cmp     qword ptr [rcx+18h], 0
0x1800053f2  mov     rbx, rcx
0x1800053f5  jnz     loc_18000547F
0x1800053fb  call    cs:__imp_GetLastError
0x180005401  cmp     qword ptr [rbx+18h], 0
0x180005406  mov     ebp, eax
0x180005408  jz      short loc_18000540E
0x18000540a  xor     esi, esi
0x18000540c  jmp     short loc_180005451
0x18000540e  cmp     qword ptr [rbx+10h], 0
0x180005413  jnz     short loc_180005440
0x180005415  mov     rcx, [rbx+8]
0x180005419  lea     rdx, [rsp+48h+arg_0]
0x18000541e  mov     [rsp+48h+arg_0], 0
0x180005427  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18000542c  test    eax, eax
0x18000542e  js      short loc_180005440
0x180005430  cmp     qword ptr [rbx+10h], 0
0x180005435  jnz     short loc_180005440
0x180005437  mov     rax, [rsp+48h+arg_0]
0x18000543c  mov     [rbx+10h], rax
0x180005440  mov     rax, [rbx+10h]
0x180005444  lea     rcx, [rax+20h]
0x180005448  neg     rax
0x18000544b  sbb     rsi, rsi
0x18000544e  and     rsi, rcx
0x180005451  lea     rdi, [rbx+20h]
0x180005455  mov     rcx, rdi; SRWLock
0x180005458  call    cs:__imp_AcquireSRWLockExclusive
0x18000545e  cmp     qword ptr [rbx+18h], 0
0x180005463  jnz     short loc_180005469
0x180005465  mov     [rbx+18h], rsi
0x180005469  test    rdi, rdi
0x18000546c  jz      short loc_180005477
0x18000546e  mov     rcx, rdi; SRWLock
0x180005471  call    cs:__imp_ReleaseSRWLockExclusive
0x180005477  mov     ecx, ebp; dwErrCode
0x180005479  call    cs:__imp_SetLastError
0x18000547f  cmp     qword ptr [rbx+18h], 0
0x180005484  setnz   al
0x180005487  add     rsp, 28h
0x18000548b  pop     rdi
0x18000548c  pop     rsi
0x18000548d  pop     rbp
0x18000548e  pop     rbx
0x18000548f  retn
```
