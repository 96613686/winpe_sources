# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180003c64`
- end: `0x180003d10`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001fc0`
- `0x180005b74`
- `0x18000712c`
- `0x180007710`

## callees

- `0x1800035c0`
- `0x180003c64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003cf1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003cf1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003cd8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003cd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003cf9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003cf9`

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
0x180003c64  push    rbx
0x180003c66  push    rbp
0x180003c67  push    rsi
0x180003c68  push    rdi
0x180003c69  sub     rsp, 28h
0x180003c6d  cmp     qword ptr [rcx+18h], 0
0x180003c72  mov     rbx, rcx
0x180003c75  jnz     loc_180003CFF
0x180003c7b  call    cs:__imp_GetLastError
0x180003c81  cmp     qword ptr [rbx+18h], 0
0x180003c86  mov     ebp, eax
0x180003c88  jz      short loc_180003C8E
0x180003c8a  xor     esi, esi
0x180003c8c  jmp     short loc_180003CD1
0x180003c8e  cmp     qword ptr [rbx+10h], 0
0x180003c93  jnz     short loc_180003CC0
0x180003c95  mov     rcx, [rbx+8]
0x180003c99  lea     rdx, [rsp+48h+arg_0]
0x180003c9e  mov     [rsp+48h+arg_0], 0
0x180003ca7  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180003cac  test    eax, eax
0x180003cae  js      short loc_180003CC0
0x180003cb0  cmp     qword ptr [rbx+10h], 0
0x180003cb5  jnz     short loc_180003CC0
0x180003cb7  mov     rax, [rsp+48h+arg_0]
0x180003cbc  mov     [rbx+10h], rax
0x180003cc0  mov     rax, [rbx+10h]
0x180003cc4  lea     rcx, [rax+20h]
0x180003cc8  neg     rax
0x180003ccb  sbb     rsi, rsi
0x180003cce  and     rsi, rcx
0x180003cd1  lea     rdi, [rbx+20h]
0x180003cd5  mov     rcx, rdi; SRWLock
0x180003cd8  call    cs:__imp_AcquireSRWLockExclusive
0x180003cde  cmp     qword ptr [rbx+18h], 0
0x180003ce3  jnz     short loc_180003CE9
0x180003ce5  mov     [rbx+18h], rsi
0x180003ce9  test    rdi, rdi
0x180003cec  jz      short loc_180003CF7
0x180003cee  mov     rcx, rdi; SRWLock
0x180003cf1  call    cs:__imp_ReleaseSRWLockExclusive
0x180003cf7  mov     ecx, ebp; dwErrCode
0x180003cf9  call    cs:__imp_SetLastError
0x180003cff  cmp     qword ptr [rbx+18h], 0
0x180003d04  setnz   al
0x180003d07  add     rsp, 28h
0x180003d0b  pop     rdi
0x180003d0c  pop     rsi
0x180003d0d  pop     rbp
0x180003d0e  pop     rbx
0x180003d0f  retn
```
