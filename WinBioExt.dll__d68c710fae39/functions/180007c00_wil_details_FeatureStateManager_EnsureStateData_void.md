# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180007c00`
- end: `0x180007cac`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007140`
- `0x180008534`
- `0x18000937c`
- `0x1800096a0`

## callees

- `0x180007824`
- `0x180007c00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007c8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007c8d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007c74`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007c74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007c95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007c95`

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
0x180007c00  push    rbx
0x180007c02  push    rbp
0x180007c03  push    rsi
0x180007c04  push    rdi
0x180007c05  sub     rsp, 28h
0x180007c09  cmp     qword ptr [rcx+18h], 0
0x180007c0e  mov     rbx, rcx
0x180007c11  jnz     loc_180007C9B
0x180007c17  call    cs:__imp_GetLastError
0x180007c1d  cmp     qword ptr [rbx+18h], 0
0x180007c22  mov     ebp, eax
0x180007c24  jz      short loc_180007C2A
0x180007c26  xor     esi, esi
0x180007c28  jmp     short loc_180007C6D
0x180007c2a  cmp     qword ptr [rbx+10h], 0
0x180007c2f  jnz     short loc_180007C5C
0x180007c31  mov     rcx, [rbx+8]
0x180007c35  lea     rdx, [rsp+48h+arg_0]
0x180007c3a  mov     [rsp+48h+arg_0], 0
0x180007c43  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180007c48  test    eax, eax
0x180007c4a  js      short loc_180007C5C
0x180007c4c  cmp     qword ptr [rbx+10h], 0
0x180007c51  jnz     short loc_180007C5C
0x180007c53  mov     rax, [rsp+48h+arg_0]
0x180007c58  mov     [rbx+10h], rax
0x180007c5c  mov     rax, [rbx+10h]
0x180007c60  lea     rcx, [rax+20h]
0x180007c64  neg     rax
0x180007c67  sbb     rsi, rsi
0x180007c6a  and     rsi, rcx
0x180007c6d  lea     rdi, [rbx+20h]
0x180007c71  mov     rcx, rdi; SRWLock
0x180007c74  call    cs:__imp_AcquireSRWLockExclusive
0x180007c7a  cmp     qword ptr [rbx+18h], 0
0x180007c7f  jnz     short loc_180007C85
0x180007c81  mov     [rbx+18h], rsi
0x180007c85  test    rdi, rdi
0x180007c88  jz      short loc_180007C93
0x180007c8a  mov     rcx, rdi; SRWLock
0x180007c8d  call    cs:__imp_ReleaseSRWLockExclusive
0x180007c93  mov     ecx, ebp; dwErrCode
0x180007c95  call    cs:__imp_SetLastError
0x180007c9b  cmp     qword ptr [rbx+18h], 0
0x180007ca0  setnz   al
0x180007ca3  add     rsp, 28h
0x180007ca7  pop     rdi
0x180007ca8  pop     rsi
0x180007ca9  pop     rbp
0x180007caa  pop     rbx
0x180007cab  retn
```
