# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x140004c64`
- end: `0x140004d10`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002c60`
- `0x140007f14`
- `0x140009c08`
- `0x14000a210`

## callees

- `0x140004498`
- `0x140004c64`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140004cf9`
- `KERNEL32!SetLastError` at `0x140004cf9`
- `KERNEL32!GetLastError` at `0x140004c7b`
- `KERNEL32!GetLastError` at `0x140004c7b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140004cf1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140004cf1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140004cd8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140004cd8`

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
0x140004c64  push    rbx
0x140004c66  push    rbp
0x140004c67  push    rsi
0x140004c68  push    rdi
0x140004c69  sub     rsp, 28h
0x140004c6d  cmp     qword ptr [rcx+18h], 0
0x140004c72  mov     rbx, rcx
0x140004c75  jnz     loc_140004CFF
0x140004c7b  call    cs:__imp_GetLastError
0x140004c81  cmp     qword ptr [rbx+18h], 0
0x140004c86  mov     ebp, eax
0x140004c88  jz      short loc_140004C8E
0x140004c8a  xor     esi, esi
0x140004c8c  jmp     short loc_140004CD1
0x140004c8e  cmp     qword ptr [rbx+10h], 0
0x140004c93  jnz     short loc_140004CC0
0x140004c95  mov     rcx, [rbx+8]
0x140004c99  lea     rdx, [rsp+48h+arg_0]
0x140004c9e  mov     [rsp+48h+arg_0], 0
0x140004ca7  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x140004cac  test    eax, eax
0x140004cae  js      short loc_140004CC0
0x140004cb0  cmp     qword ptr [rbx+10h], 0
0x140004cb5  jnz     short loc_140004CC0
0x140004cb7  mov     rax, [rsp+48h+arg_0]
0x140004cbc  mov     [rbx+10h], rax
0x140004cc0  mov     rax, [rbx+10h]
0x140004cc4  lea     rcx, [rax+20h]
0x140004cc8  neg     rax
0x140004ccb  sbb     rsi, rsi
0x140004cce  and     rsi, rcx
0x140004cd1  lea     rdi, [rbx+20h]
0x140004cd5  mov     rcx, rdi; SRWLock
0x140004cd8  call    cs:__imp_AcquireSRWLockExclusive
0x140004cde  cmp     qword ptr [rbx+18h], 0
0x140004ce3  jnz     short loc_140004CE9
0x140004ce5  mov     [rbx+18h], rsi
0x140004ce9  test    rdi, rdi
0x140004cec  jz      short loc_140004CF7
0x140004cee  mov     rcx, rdi; SRWLock
0x140004cf1  call    cs:__imp_ReleaseSRWLockExclusive
0x140004cf7  mov     ecx, ebp; dwErrCode
0x140004cf9  call    cs:__imp_SetLastError
0x140004cff  cmp     qword ptr [rbx+18h], 0
0x140004d04  setnz   al
0x140004d07  add     rsp, 28h
0x140004d0b  pop     rdi
0x140004d0c  pop     rsi
0x140004d0d  pop     rbp
0x140004d0e  pop     rbx
0x140004d0f  retn
```
