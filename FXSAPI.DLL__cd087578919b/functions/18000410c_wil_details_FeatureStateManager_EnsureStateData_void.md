# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x18000410c`
- end: `0x1800041d1`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `197`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002150`
- `0x180006b54`
- `0x180008724`
- `0x180009060`

## callees

- `0x1800039f4`
- `0x18000410c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800041b3`
- `KERNEL32!SetLastError` at `0x1800041b3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800041a5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800041a5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180004186`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180004186`
- `KERNEL32!GetLastError` at `0x180004123`
- `KERNEL32!GetLastError` at `0x180004123`

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
0x18000410c  push    rbx
0x18000410e  push    rbp
0x18000410f  push    rsi
0x180004110  push    rdi
0x180004111  sub     rsp, 28h
0x180004115  cmp     qword ptr [rcx+18h], 0
0x18000411a  mov     rbx, rcx
0x18000411d  jnz     loc_1800041BF
0x180004123  call    cs:__imp_GetLastError
0x18000412a  nop     dword ptr [rax+rax+00h]
0x18000412f  cmp     qword ptr [rbx+18h], 0
0x180004134  mov     ebp, eax
0x180004136  jz      short loc_18000413C
0x180004138  xor     esi, esi
0x18000413a  jmp     short loc_18000417F
0x18000413c  cmp     qword ptr [rbx+10h], 0
0x180004141  jnz     short loc_18000416E
0x180004143  mov     rcx, [rbx+8]
0x180004147  lea     rdx, [rsp+48h+arg_0]
0x18000414c  mov     [rsp+48h+arg_0], 0
0x180004155  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18000415a  test    eax, eax
0x18000415c  js      short loc_18000416E
0x18000415e  cmp     qword ptr [rbx+10h], 0
0x180004163  jnz     short loc_18000416E
0x180004165  mov     rax, [rsp+48h+arg_0]
0x18000416a  mov     [rbx+10h], rax
0x18000416e  mov     rax, [rbx+10h]
0x180004172  lea     rcx, [rax+20h]
0x180004176  neg     rax
0x180004179  sbb     rsi, rsi
0x18000417c  and     rsi, rcx
0x18000417f  lea     rdi, [rbx+20h]
0x180004183  mov     rcx, rdi; SRWLock
0x180004186  call    cs:__imp_AcquireSRWLockExclusive
0x18000418d  nop     dword ptr [rax+rax+00h]
0x180004192  cmp     qword ptr [rbx+18h], 0
0x180004197  jnz     short loc_18000419D
0x180004199  mov     [rbx+18h], rsi
0x18000419d  test    rdi, rdi
0x1800041a0  jz      short loc_1800041B1
0x1800041a2  mov     rcx, rdi; SRWLock
0x1800041a5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800041ac  nop     dword ptr [rax+rax+00h]
0x1800041b1  mov     ecx, ebp; dwErrCode
0x1800041b3  call    cs:__imp_SetLastError
0x1800041ba  nop     dword ptr [rax+rax+00h]
0x1800041bf  cmp     qword ptr [rbx+18h], 0
0x1800041c4  setnz   al
0x1800041c7  add     rsp, 28h
0x1800041cb  pop     rdi
0x1800041cc  pop     rsi
0x1800041cd  pop     rbp
0x1800041ce  pop     rbx
0x1800041cf  retn
```
