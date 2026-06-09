# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1800077c8`
- end: `0x180007874`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004710`
- `0x18000cdd4`
- `0x180010758`
- `0x180010e60`

## callees

- `0x1800064ac`
- `0x1800077c8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800077df`
- `KERNEL32!GetLastError` at `0x1800077df`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000783c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000783c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007855`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007855`
- `KERNEL32!SetLastError` at `0x18000785d`
- `KERNEL32!SetLastError` at `0x18000785d`

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
0x1800077c8  push    rbx
0x1800077ca  push    rbp
0x1800077cb  push    rsi
0x1800077cc  push    rdi
0x1800077cd  sub     rsp, 28h
0x1800077d1  cmp     qword ptr [rcx+18h], 0
0x1800077d6  mov     rbx, rcx
0x1800077d9  jnz     loc_180007863
0x1800077df  call    cs:__imp_GetLastError
0x1800077e5  cmp     qword ptr [rbx+18h], 0
0x1800077ea  mov     ebp, eax
0x1800077ec  jz      short loc_1800077F2
0x1800077ee  xor     esi, esi
0x1800077f0  jmp     short loc_180007835
0x1800077f2  cmp     qword ptr [rbx+10h], 0
0x1800077f7  jnz     short loc_180007824
0x1800077f9  mov     rcx, [rbx+8]
0x1800077fd  lea     rdx, [rsp+48h+arg_0]
0x180007802  mov     [rsp+48h+arg_0], 0
0x18000780b  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180007810  test    eax, eax
0x180007812  js      short loc_180007824
0x180007814  cmp     qword ptr [rbx+10h], 0
0x180007819  jnz     short loc_180007824
0x18000781b  mov     rax, [rsp+48h+arg_0]
0x180007820  mov     [rbx+10h], rax
0x180007824  mov     rax, [rbx+10h]
0x180007828  lea     rcx, [rax+20h]
0x18000782c  neg     rax
0x18000782f  sbb     rsi, rsi
0x180007832  and     rsi, rcx
0x180007835  lea     rdi, [rbx+20h]
0x180007839  mov     rcx, rdi; SRWLock
0x18000783c  call    cs:__imp_AcquireSRWLockExclusive
0x180007842  cmp     qword ptr [rbx+18h], 0
0x180007847  jnz     short loc_18000784D
0x180007849  mov     [rbx+18h], rsi
0x18000784d  test    rdi, rdi
0x180007850  jz      short loc_18000785B
0x180007852  mov     rcx, rdi; SRWLock
0x180007855  call    cs:__imp_ReleaseSRWLockExclusive
0x18000785b  mov     ecx, ebp; dwErrCode
0x18000785d  call    cs:__imp_SetLastError
0x180007863  cmp     qword ptr [rbx+18h], 0
0x180007868  setnz   al
0x18000786b  add     rsp, 28h
0x18000786f  pop     rdi
0x180007870  pop     rsi
0x180007871  pop     rbp
0x180007872  pop     rbx
0x180007873  retn
```
