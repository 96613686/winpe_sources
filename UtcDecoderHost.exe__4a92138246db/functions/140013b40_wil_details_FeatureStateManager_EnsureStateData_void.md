# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x140013b40`
- end: `0x140013bec`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140012310`
- `0x140014a90`
- `0x140015b90`
- `0x140015eb0`

## callees

- `0x14001373c`
- `0x140013b40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140013bb4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140013bb4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140013bcd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140013bcd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140013bd5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140013bd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013b57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013b57`

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
0x140013b40  push    rbx
0x140013b42  push    rbp
0x140013b43  push    rsi
0x140013b44  push    rdi
0x140013b45  sub     rsp, 28h
0x140013b49  cmp     qword ptr [rcx+18h], 0
0x140013b4e  mov     rbx, rcx
0x140013b51  jnz     loc_140013BDB
0x140013b57  call    cs:__imp_GetLastError
0x140013b5d  cmp     qword ptr [rbx+18h], 0
0x140013b62  mov     ebp, eax
0x140013b64  jz      short loc_140013B6A
0x140013b66  xor     esi, esi
0x140013b68  jmp     short loc_140013BAD
0x140013b6a  cmp     qword ptr [rbx+10h], 0
0x140013b6f  jnz     short loc_140013B9C
0x140013b71  mov     rcx, [rbx+8]
0x140013b75  lea     rdx, [rsp+48h+arg_0]
0x140013b7a  mov     [rsp+48h+arg_0], 0
0x140013b83  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x140013b88  test    eax, eax
0x140013b8a  js      short loc_140013B9C
0x140013b8c  cmp     qword ptr [rbx+10h], 0
0x140013b91  jnz     short loc_140013B9C
0x140013b93  mov     rax, [rsp+48h+arg_0]
0x140013b98  mov     [rbx+10h], rax
0x140013b9c  mov     rax, [rbx+10h]
0x140013ba0  lea     rcx, [rax+20h]
0x140013ba4  neg     rax
0x140013ba7  sbb     rsi, rsi
0x140013baa  and     rsi, rcx
0x140013bad  lea     rdi, [rbx+20h]
0x140013bb1  mov     rcx, rdi; SRWLock
0x140013bb4  call    cs:__imp_AcquireSRWLockExclusive
0x140013bba  cmp     qword ptr [rbx+18h], 0
0x140013bbf  jnz     short loc_140013BC5
0x140013bc1  mov     [rbx+18h], rsi
0x140013bc5  test    rdi, rdi
0x140013bc8  jz      short loc_140013BD3
0x140013bca  mov     rcx, rdi; SRWLock
0x140013bcd  call    cs:__imp_ReleaseSRWLockExclusive
0x140013bd3  mov     ecx, ebp; dwErrCode
0x140013bd5  call    cs:__imp_SetLastError
0x140013bdb  cmp     qword ptr [rbx+18h], 0
0x140013be0  setnz   al
0x140013be3  add     rsp, 28h
0x140013be7  pop     rdi
0x140013be8  pop     rsi
0x140013be9  pop     rbp
0x140013bea  pop     rbx
0x140013beb  retn
```
