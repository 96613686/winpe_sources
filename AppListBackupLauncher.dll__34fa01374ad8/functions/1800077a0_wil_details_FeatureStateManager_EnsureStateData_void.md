# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1800077a0`
- end: `0x18000784c`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003190`
- `0x18000a7c4`
- `0x18000d428`
- `0x18000dae0`

## callees

- `0x180006c4c`
- `0x1800077a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000782d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000782d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007814`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007814`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007835`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007835`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077b7`

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
0x1800077a0  push    rbx
0x1800077a2  push    rbp
0x1800077a3  push    rsi
0x1800077a4  push    rdi
0x1800077a5  sub     rsp, 28h
0x1800077a9  cmp     qword ptr [rcx+18h], 0
0x1800077ae  mov     rbx, rcx
0x1800077b1  jnz     loc_18000783B
0x1800077b7  call    cs:__imp_GetLastError
0x1800077bd  cmp     qword ptr [rbx+18h], 0
0x1800077c2  mov     ebp, eax
0x1800077c4  jz      short loc_1800077CA
0x1800077c6  xor     esi, esi
0x1800077c8  jmp     short loc_18000780D
0x1800077ca  cmp     qword ptr [rbx+10h], 0
0x1800077cf  jnz     short loc_1800077FC
0x1800077d1  mov     rcx, [rbx+8]
0x1800077d5  lea     rdx, [rsp+48h+arg_0]
0x1800077da  mov     [rsp+48h+arg_0], 0
0x1800077e3  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x1800077e8  test    eax, eax
0x1800077ea  js      short loc_1800077FC
0x1800077ec  cmp     qword ptr [rbx+10h], 0
0x1800077f1  jnz     short loc_1800077FC
0x1800077f3  mov     rax, [rsp+48h+arg_0]
0x1800077f8  mov     [rbx+10h], rax
0x1800077fc  mov     rax, [rbx+10h]
0x180007800  lea     rcx, [rax+20h]
0x180007804  neg     rax
0x180007807  sbb     rsi, rsi
0x18000780a  and     rsi, rcx
0x18000780d  lea     rdi, [rbx+20h]
0x180007811  mov     rcx, rdi; SRWLock
0x180007814  call    cs:__imp_AcquireSRWLockExclusive
0x18000781a  cmp     qword ptr [rbx+18h], 0
0x18000781f  jnz     short loc_180007825
0x180007821  mov     [rbx+18h], rsi
0x180007825  test    rdi, rdi
0x180007828  jz      short loc_180007833
0x18000782a  mov     rcx, rdi; SRWLock
0x18000782d  call    cs:__imp_ReleaseSRWLockExclusive
0x180007833  mov     ecx, ebp; dwErrCode
0x180007835  call    cs:__imp_SetLastError
0x18000783b  cmp     qword ptr [rbx+18h], 0
0x180007840  setnz   al
0x180007843  add     rsp, 28h
0x180007847  pop     rdi
0x180007848  pop     rsi
0x180007849  pop     rbp
0x18000784a  pop     rbx
0x18000784b  retn
```
