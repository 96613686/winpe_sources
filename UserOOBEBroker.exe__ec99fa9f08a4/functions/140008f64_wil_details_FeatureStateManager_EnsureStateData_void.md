# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x140008f64`
- end: `0x140009010`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140006c70`
- `0x14000b288`
- `0x14000cb5c`
- `0x14000d080`

## callees

- `0x140008710`
- `0x140008f64`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140008ff9`
- `KERNEL32!SetLastError` at `0x140008ff9`
- `KERNEL32!GetLastError` at `0x140008f7b`
- `KERNEL32!GetLastError` at `0x140008f7b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140008fd8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140008fd8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140008ff1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140008ff1`

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
0x140008f64  push    rbx
0x140008f66  push    rbp
0x140008f67  push    rsi
0x140008f68  push    rdi
0x140008f69  sub     rsp, 28h
0x140008f6d  cmp     qword ptr [rcx+18h], 0
0x140008f72  mov     rbx, rcx
0x140008f75  jnz     loc_140008FFF
0x140008f7b  call    cs:__imp_GetLastError
0x140008f81  cmp     qword ptr [rbx+18h], 0
0x140008f86  mov     ebp, eax
0x140008f88  jz      short loc_140008F8E
0x140008f8a  xor     esi, esi
0x140008f8c  jmp     short loc_140008FD1
0x140008f8e  cmp     qword ptr [rbx+10h], 0
0x140008f93  jnz     short loc_140008FC0
0x140008f95  mov     rcx, [rbx+8]
0x140008f99  lea     rdx, [rsp+48h+arg_0]
0x140008f9e  mov     [rsp+48h+arg_0], 0
0x140008fa7  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x140008fac  test    eax, eax
0x140008fae  js      short loc_140008FC0
0x140008fb0  cmp     qword ptr [rbx+10h], 0
0x140008fb5  jnz     short loc_140008FC0
0x140008fb7  mov     rax, [rsp+48h+arg_0]
0x140008fbc  mov     [rbx+10h], rax
0x140008fc0  mov     rax, [rbx+10h]
0x140008fc4  lea     rcx, [rax+20h]
0x140008fc8  neg     rax
0x140008fcb  sbb     rsi, rsi
0x140008fce  and     rsi, rcx
0x140008fd1  lea     rdi, [rbx+20h]
0x140008fd5  mov     rcx, rdi; SRWLock
0x140008fd8  call    cs:__imp_AcquireSRWLockExclusive
0x140008fde  cmp     qword ptr [rbx+18h], 0
0x140008fe3  jnz     short loc_140008FE9
0x140008fe5  mov     [rbx+18h], rsi
0x140008fe9  test    rdi, rdi
0x140008fec  jz      short loc_140008FF7
0x140008fee  mov     rcx, rdi; SRWLock
0x140008ff1  call    cs:__imp_ReleaseSRWLockExclusive
0x140008ff7  mov     ecx, ebp; dwErrCode
0x140008ff9  call    cs:__imp_SetLastError
0x140008fff  cmp     qword ptr [rbx+18h], 0
0x140009004  setnz   al
0x140009007  add     rsp, 28h
0x14000900b  pop     rdi
0x14000900c  pop     rsi
0x14000900d  pop     rbp
0x14000900e  pop     rbx
0x14000900f  retn
```
