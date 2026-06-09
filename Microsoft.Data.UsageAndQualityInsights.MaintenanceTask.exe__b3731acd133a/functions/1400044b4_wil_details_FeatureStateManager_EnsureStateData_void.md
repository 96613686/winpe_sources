# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1400044b4`
- end: `0x140004560`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002450`
- `0x140006404`
- `0x140007f70`
- `0x1400085b0`

## callees

- `0x140003e1c`
- `0x1400044b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004528`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004528`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004541`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400044cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400044cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004549`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004549`

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
0x1400044b4  push    rbx
0x1400044b6  push    rbp
0x1400044b7  push    rsi
0x1400044b8  push    rdi
0x1400044b9  sub     rsp, 28h
0x1400044bd  cmp     qword ptr [rcx+18h], 0
0x1400044c2  mov     rbx, rcx
0x1400044c5  jnz     loc_14000454F
0x1400044cb  call    cs:__imp_GetLastError
0x1400044d1  cmp     qword ptr [rbx+18h], 0
0x1400044d6  mov     ebp, eax
0x1400044d8  jz      short loc_1400044DE
0x1400044da  xor     esi, esi
0x1400044dc  jmp     short loc_140004521
0x1400044de  cmp     qword ptr [rbx+10h], 0
0x1400044e3  jnz     short loc_140004510
0x1400044e5  mov     rcx, [rbx+8]
0x1400044e9  lea     rdx, [rsp+48h+arg_0]
0x1400044ee  mov     [rsp+48h+arg_0], 0
0x1400044f7  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x1400044fc  test    eax, eax
0x1400044fe  js      short loc_140004510
0x140004500  cmp     qword ptr [rbx+10h], 0
0x140004505  jnz     short loc_140004510
0x140004507  mov     rax, [rsp+48h+arg_0]
0x14000450c  mov     [rbx+10h], rax
0x140004510  mov     rax, [rbx+10h]
0x140004514  lea     rcx, [rax+20h]
0x140004518  neg     rax
0x14000451b  sbb     rsi, rsi
0x14000451e  and     rsi, rcx
0x140004521  lea     rdi, [rbx+20h]
0x140004525  mov     rcx, rdi; SRWLock
0x140004528  call    cs:__imp_AcquireSRWLockExclusive
0x14000452e  cmp     qword ptr [rbx+18h], 0
0x140004533  jnz     short loc_140004539
0x140004535  mov     [rbx+18h], rsi
0x140004539  test    rdi, rdi
0x14000453c  jz      short loc_140004547
0x14000453e  mov     rcx, rdi; SRWLock
0x140004541  call    cs:__imp_ReleaseSRWLockExclusive
0x140004547  mov     ecx, ebp; dwErrCode
0x140004549  call    cs:__imp_SetLastError
0x14000454f  cmp     qword ptr [rbx+18h], 0
0x140004554  setnz   al
0x140004557  add     rsp, 28h
0x14000455b  pop     rdi
0x14000455c  pop     rsi
0x14000455d  pop     rbp
0x14000455e  pop     rbx
0x14000455f  retn
```
