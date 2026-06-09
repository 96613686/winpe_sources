# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180004430`
- end: `0x1800044dc`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002520`
- `0x180006414`
- `0x180007764`
- `0x180007d70`

## callees

- `0x180003c4c`
- `0x180004430`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800044c5`
- `KERNEL32!SetLastError` at `0x1800044c5`
- `KERNEL32!GetLastError` at `0x180004447`
- `KERNEL32!GetLastError` at `0x180004447`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800044bd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800044bd`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800044a4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800044a4`

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
0x180004430  push    rbx
0x180004432  push    rbp
0x180004433  push    rsi
0x180004434  push    rdi
0x180004435  sub     rsp, 28h
0x180004439  cmp     qword ptr [rcx+18h], 0
0x18000443e  mov     rbx, rcx
0x180004441  jnz     loc_1800044CB
0x180004447  call    cs:__imp_GetLastError
0x18000444d  cmp     qword ptr [rbx+18h], 0
0x180004452  mov     ebp, eax
0x180004454  jz      short loc_18000445A
0x180004456  xor     esi, esi
0x180004458  jmp     short loc_18000449D
0x18000445a  cmp     qword ptr [rbx+10h], 0
0x18000445f  jnz     short loc_18000448C
0x180004461  mov     rcx, [rbx+8]
0x180004465  lea     rdx, [rsp+48h+arg_0]
0x18000446a  mov     [rsp+48h+arg_0], 0
0x180004473  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180004478  test    eax, eax
0x18000447a  js      short loc_18000448C
0x18000447c  cmp     qword ptr [rbx+10h], 0
0x180004481  jnz     short loc_18000448C
0x180004483  mov     rax, [rsp+48h+arg_0]
0x180004488  mov     [rbx+10h], rax
0x18000448c  mov     rax, [rbx+10h]
0x180004490  lea     rcx, [rax+20h]
0x180004494  neg     rax
0x180004497  sbb     rsi, rsi
0x18000449a  and     rsi, rcx
0x18000449d  lea     rdi, [rbx+20h]
0x1800044a1  mov     rcx, rdi; SRWLock
0x1800044a4  call    cs:__imp_AcquireSRWLockExclusive
0x1800044aa  cmp     qword ptr [rbx+18h], 0
0x1800044af  jnz     short loc_1800044B5
0x1800044b1  mov     [rbx+18h], rsi
0x1800044b5  test    rdi, rdi
0x1800044b8  jz      short loc_1800044C3
0x1800044ba  mov     rcx, rdi; SRWLock
0x1800044bd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800044c3  mov     ecx, ebp; dwErrCode
0x1800044c5  call    cs:__imp_SetLastError
0x1800044cb  cmp     qword ptr [rbx+18h], 0
0x1800044d0  setnz   al
0x1800044d3  add     rsp, 28h
0x1800044d7  pop     rdi
0x1800044d8  pop     rsi
0x1800044d9  pop     rbp
0x1800044da  pop     rbx
0x1800044db  retn
```
