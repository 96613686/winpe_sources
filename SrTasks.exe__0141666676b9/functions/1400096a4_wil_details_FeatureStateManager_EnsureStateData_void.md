# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1400096a4`
- end: `0x140009750`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140007be0`
- `0x14000b104`
- `0x14000c350`
- `0x14000c8d0`

## callees

- `0x140009000`
- `0x1400096a4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400096bb`
- `KERNEL32!GetLastError` at `0x1400096bb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140009718`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140009718`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140009731`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140009731`
- `KERNEL32!SetLastError` at `0x140009739`
- `KERNEL32!SetLastError` at `0x140009739`

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
0x1400096a4  push    rbx
0x1400096a6  push    rbp
0x1400096a7  push    rsi
0x1400096a8  push    rdi
0x1400096a9  sub     rsp, 28h
0x1400096ad  cmp     qword ptr [rcx+18h], 0
0x1400096b2  mov     rbx, rcx
0x1400096b5  jnz     loc_14000973F
0x1400096bb  call    cs:__imp_GetLastError
0x1400096c1  cmp     qword ptr [rbx+18h], 0
0x1400096c6  mov     ebp, eax
0x1400096c8  jz      short loc_1400096CE
0x1400096ca  xor     esi, esi
0x1400096cc  jmp     short loc_140009711
0x1400096ce  cmp     qword ptr [rbx+10h], 0
0x1400096d3  jnz     short loc_140009700
0x1400096d5  mov     rcx, [rbx+8]
0x1400096d9  lea     rdx, [rsp+48h+arg_0]
0x1400096de  mov     [rsp+48h+arg_0], 0
0x1400096e7  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x1400096ec  test    eax, eax
0x1400096ee  js      short loc_140009700
0x1400096f0  cmp     qword ptr [rbx+10h], 0
0x1400096f5  jnz     short loc_140009700
0x1400096f7  mov     rax, [rsp+48h+arg_0]
0x1400096fc  mov     [rbx+10h], rax
0x140009700  mov     rax, [rbx+10h]
0x140009704  lea     rcx, [rax+20h]
0x140009708  neg     rax
0x14000970b  sbb     rsi, rsi
0x14000970e  and     rsi, rcx
0x140009711  lea     rdi, [rbx+20h]
0x140009715  mov     rcx, rdi; SRWLock
0x140009718  call    cs:__imp_AcquireSRWLockExclusive
0x14000971e  cmp     qword ptr [rbx+18h], 0
0x140009723  jnz     short loc_140009729
0x140009725  mov     [rbx+18h], rsi
0x140009729  test    rdi, rdi
0x14000972c  jz      short loc_140009737
0x14000972e  mov     rcx, rdi; SRWLock
0x140009731  call    cs:__imp_ReleaseSRWLockExclusive
0x140009737  mov     ecx, ebp; dwErrCode
0x140009739  call    cs:__imp_SetLastError
0x14000973f  cmp     qword ptr [rbx+18h], 0
0x140009744  setnz   al
0x140009747  add     rsp, 28h
0x14000974b  pop     rdi
0x14000974c  pop     rsi
0x14000974d  pop     rbp
0x14000974e  pop     rbx
0x14000974f  retn
```
