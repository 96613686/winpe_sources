# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x140006bf8`
- end: `0x140006ca4`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140005860`
- `0x140010314`
- `0x1400115a8`
- `0x140011920`

## callees

- `0x1400063bc`
- `0x140006bf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006c85`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006c85`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006c6c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006c6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006c8d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006c8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006c0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006c0f`

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
0x140006bf8  push    rbx
0x140006bfa  push    rbp
0x140006bfb  push    rsi
0x140006bfc  push    rdi
0x140006bfd  sub     rsp, 28h
0x140006c01  cmp     qword ptr [rcx+18h], 0
0x140006c06  mov     rbx, rcx
0x140006c09  jnz     loc_140006C93
0x140006c0f  call    cs:__imp_GetLastError
0x140006c15  cmp     qword ptr [rbx+18h], 0
0x140006c1a  mov     ebp, eax
0x140006c1c  jz      short loc_140006C22
0x140006c1e  xor     esi, esi
0x140006c20  jmp     short loc_140006C65
0x140006c22  cmp     qword ptr [rbx+10h], 0
0x140006c27  jnz     short loc_140006C54
0x140006c29  mov     rcx, [rbx+8]
0x140006c2d  lea     rdx, [rsp+48h+arg_0]
0x140006c32  mov     [rsp+48h+arg_0], 0
0x140006c3b  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x140006c40  test    eax, eax
0x140006c42  js      short loc_140006C54
0x140006c44  cmp     qword ptr [rbx+10h], 0
0x140006c49  jnz     short loc_140006C54
0x140006c4b  mov     rax, [rsp+48h+arg_0]
0x140006c50  mov     [rbx+10h], rax
0x140006c54  mov     rax, [rbx+10h]
0x140006c58  lea     rcx, [rax+20h]
0x140006c5c  neg     rax
0x140006c5f  sbb     rsi, rsi
0x140006c62  and     rsi, rcx
0x140006c65  lea     rdi, [rbx+20h]
0x140006c69  mov     rcx, rdi; SRWLock
0x140006c6c  call    cs:__imp_AcquireSRWLockExclusive
0x140006c72  cmp     qword ptr [rbx+18h], 0
0x140006c77  jnz     short loc_140006C7D
0x140006c79  mov     [rbx+18h], rsi
0x140006c7d  test    rdi, rdi
0x140006c80  jz      short loc_140006C8B
0x140006c82  mov     rcx, rdi; SRWLock
0x140006c85  call    cs:__imp_ReleaseSRWLockExclusive
0x140006c8b  mov     ecx, ebp; dwErrCode
0x140006c8d  call    cs:__imp_SetLastError
0x140006c93  cmp     qword ptr [rbx+18h], 0
0x140006c98  setnz   al
0x140006c9b  add     rsp, 28h
0x140006c9f  pop     rdi
0x140006ca0  pop     rsi
0x140006ca1  pop     rbp
0x140006ca2  pop     rbx
0x140006ca3  retn
```
