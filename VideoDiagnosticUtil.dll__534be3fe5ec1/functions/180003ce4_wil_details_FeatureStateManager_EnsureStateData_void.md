# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180003ce4`
- end: `0x180003da9`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `197`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002360`
- `0x18000595c`
- `0x180006e2c`
- `0x1800074b0`

## callees

- `0x180003700`
- `0x180003ce4`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180003d5e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180003d5e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180003d7d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180003d7d`
- `KERNEL32!GetLastError` at `0x180003cfb`
- `KERNEL32!GetLastError` at `0x180003cfb`
- `KERNEL32!SetLastError` at `0x180003d8b`
- `KERNEL32!SetLastError` at `0x180003d8b`

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
0x180003ce4  push    rbx
0x180003ce6  push    rbp
0x180003ce7  push    rsi
0x180003ce8  push    rdi
0x180003ce9  sub     rsp, 28h
0x180003ced  cmp     qword ptr [rcx+18h], 0
0x180003cf2  mov     rbx, rcx
0x180003cf5  jnz     loc_180003D97
0x180003cfb  call    cs:__imp_GetLastError
0x180003d02  nop     dword ptr [rax+rax+00h]
0x180003d07  cmp     qword ptr [rbx+18h], 0
0x180003d0c  mov     ebp, eax
0x180003d0e  jz      short loc_180003D14
0x180003d10  xor     esi, esi
0x180003d12  jmp     short loc_180003D57
0x180003d14  cmp     qword ptr [rbx+10h], 0
0x180003d19  jnz     short loc_180003D46
0x180003d1b  mov     rcx, [rbx+8]
0x180003d1f  lea     rdx, [rsp+48h+arg_0]
0x180003d24  mov     [rsp+48h+arg_0], 0
0x180003d2d  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180003d32  test    eax, eax
0x180003d34  js      short loc_180003D46
0x180003d36  cmp     qword ptr [rbx+10h], 0
0x180003d3b  jnz     short loc_180003D46
0x180003d3d  mov     rax, [rsp+48h+arg_0]
0x180003d42  mov     [rbx+10h], rax
0x180003d46  mov     rax, [rbx+10h]
0x180003d4a  lea     rcx, [rax+20h]
0x180003d4e  neg     rax
0x180003d51  sbb     rsi, rsi
0x180003d54  and     rsi, rcx
0x180003d57  lea     rdi, [rbx+20h]
0x180003d5b  mov     rcx, rdi; SRWLock
0x180003d5e  call    cs:__imp_AcquireSRWLockExclusive
0x180003d65  nop     dword ptr [rax+rax+00h]
0x180003d6a  cmp     qword ptr [rbx+18h], 0
0x180003d6f  jnz     short loc_180003D75
0x180003d71  mov     [rbx+18h], rsi
0x180003d75  test    rdi, rdi
0x180003d78  jz      short loc_180003D89
0x180003d7a  mov     rcx, rdi; SRWLock
0x180003d7d  call    cs:__imp_ReleaseSRWLockExclusive
0x180003d84  nop     dword ptr [rax+rax+00h]
0x180003d89  mov     ecx, ebp; dwErrCode
0x180003d8b  call    cs:__imp_SetLastError
0x180003d92  nop     dword ptr [rax+rax+00h]
0x180003d97  cmp     qword ptr [rbx+18h], 0
0x180003d9c  setnz   al
0x180003d9f  add     rsp, 28h
0x180003da3  pop     rdi
0x180003da4  pop     rsi
0x180003da5  pop     rbp
0x180003da6  pop     rbx
0x180003da7  retn
```
