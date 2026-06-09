# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1400091c4`
- end: `0x140009270`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140007840`
- `0x14000a334`
- `0x14000bc8c`
- `0x14000c220`

## callees

- `0x140008ae8`
- `0x1400091c4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400091db`
- `KERNEL32!GetLastError` at `0x1400091db`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009238`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009238`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009251`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009251`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009259`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009259`

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
0x1400091c4  push    rbx
0x1400091c6  push    rbp
0x1400091c7  push    rsi
0x1400091c8  push    rdi
0x1400091c9  sub     rsp, 28h
0x1400091cd  cmp     qword ptr [rcx+18h], 0
0x1400091d2  mov     rbx, rcx
0x1400091d5  jnz     loc_14000925F
0x1400091db  call    cs:__imp_GetLastError
0x1400091e1  cmp     qword ptr [rbx+18h], 0
0x1400091e6  mov     ebp, eax
0x1400091e8  jz      short loc_1400091EE
0x1400091ea  xor     esi, esi
0x1400091ec  jmp     short loc_140009231
0x1400091ee  cmp     qword ptr [rbx+10h], 0
0x1400091f3  jnz     short loc_140009220
0x1400091f5  mov     rcx, [rbx+8]
0x1400091f9  lea     rdx, [rsp+48h+arg_0]
0x1400091fe  mov     [rsp+48h+arg_0], 0
0x140009207  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x14000920c  test    eax, eax
0x14000920e  js      short loc_140009220
0x140009210  cmp     qword ptr [rbx+10h], 0
0x140009215  jnz     short loc_140009220
0x140009217  mov     rax, [rsp+48h+arg_0]
0x14000921c  mov     [rbx+10h], rax
0x140009220  mov     rax, [rbx+10h]
0x140009224  lea     rcx, [rax+20h]
0x140009228  neg     rax
0x14000922b  sbb     rsi, rsi
0x14000922e  and     rsi, rcx
0x140009231  lea     rdi, [rbx+20h]
0x140009235  mov     rcx, rdi; SRWLock
0x140009238  call    cs:__imp_AcquireSRWLockExclusive
0x14000923e  cmp     qword ptr [rbx+18h], 0
0x140009243  jnz     short loc_140009249
0x140009245  mov     [rbx+18h], rsi
0x140009249  test    rdi, rdi
0x14000924c  jz      short loc_140009257
0x14000924e  mov     rcx, rdi; SRWLock
0x140009251  call    cs:__imp_ReleaseSRWLockExclusive
0x140009257  mov     ecx, ebp; dwErrCode
0x140009259  call    cs:__imp_SetLastError
0x14000925f  cmp     qword ptr [rbx+18h], 0
0x140009264  setnz   al
0x140009267  add     rsp, 28h
0x14000926b  pop     rdi
0x14000926c  pop     rsi
0x14000926d  pop     rbp
0x14000926e  pop     rbx
0x14000926f  retn
```
