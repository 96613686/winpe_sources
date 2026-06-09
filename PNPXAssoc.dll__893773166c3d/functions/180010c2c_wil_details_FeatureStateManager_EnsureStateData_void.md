# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180010c2c`
- end: `0x180010cd8`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180010210`
- `0x180011534`
- `0x1800122f8`
- `0x180012600`

## callees

- `0x18001085c`
- `0x180010c2c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180010cc1`
- `KERNEL32!SetLastError` at `0x180010cc1`
- `KERNEL32!GetLastError` at `0x180010c43`
- `KERNEL32!GetLastError` at `0x180010c43`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180010cb9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180010cb9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180010ca0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180010ca0`

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
0x180010c2c  push    rbx
0x180010c2e  push    rbp
0x180010c2f  push    rsi
0x180010c30  push    rdi
0x180010c31  sub     rsp, 28h
0x180010c35  cmp     qword ptr [rcx+18h], 0
0x180010c3a  mov     rbx, rcx
0x180010c3d  jnz     loc_180010CC7
0x180010c43  call    cs:__imp_GetLastError
0x180010c49  cmp     qword ptr [rbx+18h], 0
0x180010c4e  mov     ebp, eax
0x180010c50  jz      short loc_180010C56
0x180010c52  xor     esi, esi
0x180010c54  jmp     short loc_180010C99
0x180010c56  cmp     qword ptr [rbx+10h], 0
0x180010c5b  jnz     short loc_180010C88
0x180010c5d  mov     rcx, [rbx+8]
0x180010c61  lea     rdx, [rsp+48h+arg_0]
0x180010c66  mov     [rsp+48h+arg_0], 0
0x180010c6f  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180010c74  test    eax, eax
0x180010c76  js      short loc_180010C88
0x180010c78  cmp     qword ptr [rbx+10h], 0
0x180010c7d  jnz     short loc_180010C88
0x180010c7f  mov     rax, [rsp+48h+arg_0]
0x180010c84  mov     [rbx+10h], rax
0x180010c88  mov     rax, [rbx+10h]
0x180010c8c  lea     rcx, [rax+20h]
0x180010c90  neg     rax
0x180010c93  sbb     rsi, rsi
0x180010c96  and     rsi, rcx
0x180010c99  lea     rdi, [rbx+20h]
0x180010c9d  mov     rcx, rdi; SRWLock
0x180010ca0  call    cs:__imp_AcquireSRWLockExclusive
0x180010ca6  cmp     qword ptr [rbx+18h], 0
0x180010cab  jnz     short loc_180010CB1
0x180010cad  mov     [rbx+18h], rsi
0x180010cb1  test    rdi, rdi
0x180010cb4  jz      short loc_180010CBF
0x180010cb6  mov     rcx, rdi; SRWLock
0x180010cb9  call    cs:__imp_ReleaseSRWLockExclusive
0x180010cbf  mov     ecx, ebp; dwErrCode
0x180010cc1  call    cs:__imp_SetLastError
0x180010cc7  cmp     qword ptr [rbx+18h], 0
0x180010ccc  setnz   al
0x180010ccf  add     rsp, 28h
0x180010cd3  pop     rdi
0x180010cd4  pop     rsi
0x180010cd5  pop     rbp
0x180010cd6  pop     rbx
0x180010cd7  retn
```
