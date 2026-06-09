# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x140003ac0`
- end: `0x140003b7c`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `188`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003808`
- `0x140003950`
- `0x140007a4c`

## callees

- `0x140001ad0`
- `0x140003ac0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140003b38`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140003b38`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140003b56`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140003b56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ae3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003b5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003b5e`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureStateData(RTL_SRWLOCK *this)
{
  void *v2; // rdi
  DWORD LastError; // ebp
  __int64 Ptr; // rcx
  char *v5; // rax
  char *v6; // rcx
  void *v8; // [rsp+30h] [rbp+8h] BYREF

  if ( !this[3].Ptr )
  {
    v2 = 0;
    LastError = GetLastError();
    if ( !this[3].Ptr )
    {
      if ( !this[2].Ptr )
      {
        Ptr = (__int64)this[1].Ptr;
        v8 = 0;
        if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(Ptr, &v8) >= 0
          && !this[2].Ptr )
        {
          this[2].Ptr = v8;
        }
      }
      v5 = (char *)this[2].Ptr;
      v6 = v5 + 32;
      if ( !v5 )
        v6 = 0;
      v2 = v6;
    }
    AcquireSRWLockExclusive(this + 4);
    if ( !this[3].Ptr )
      this[3].Ptr = v2;
    if ( this != (RTL_SRWLOCK *)-32LL )
      ReleaseSRWLockExclusive(this + 4);
    SetLastError(LastError);
  }
  return this[3].Ptr != 0;
}

```

## disassembly

```asm
0x140003ac0  push    rbx
0x140003ac2  sub     rsp, 20h
0x140003ac6  cmp     qword ptr [rcx+18h], 0
0x140003acb  mov     rbx, rcx
0x140003ace  jnz     loc_140003B6E
0x140003ad4  mov     [rsp+28h+arg_8], rbp
0x140003ad9  mov     [rsp+28h+arg_10], rsi
0x140003ade  mov     [rsp+28h+arg_18], rdi
0x140003ae3  call    cs:__imp_GetLastError
0x140003ae9  xor     edi, edi
0x140003aeb  mov     ebp, eax
0x140003aed  cmp     [rbx+18h], rdi
0x140003af1  jnz     short loc_140003B31
0x140003af3  cmp     [rbx+10h], rdi
0x140003af7  jnz     short loc_140003B1F
0x140003af9  mov     rcx, [rbx+8]
0x140003afd  lea     rdx, [rsp+28h+arg_0]
0x140003b02  mov     [rsp+28h+arg_0], rdi
0x140003b07  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x140003b0c  test    eax, eax
0x140003b0e  js      short loc_140003B1F
0x140003b10  cmp     [rbx+10h], rdi
0x140003b14  jnz     short loc_140003B1F
0x140003b16  mov     rax, [rsp+28h+arg_0]
0x140003b1b  mov     [rbx+10h], rax
0x140003b1f  mov     rax, [rbx+10h]
0x140003b23  test    rax, rax
0x140003b26  lea     rcx, [rax+20h]
0x140003b2a  cmovz   rcx, rdi
0x140003b2e  mov     rdi, rcx
0x140003b31  lea     rsi, [rbx+20h]
0x140003b35  mov     rcx, rsi; SRWLock
0x140003b38  call    cs:__imp_AcquireSRWLockExclusive
0x140003b3e  cmp     qword ptr [rbx+18h], 0
0x140003b43  jnz     short loc_140003B49
0x140003b45  mov     [rbx+18h], rdi
0x140003b49  mov     rdi, [rsp+28h+arg_18]
0x140003b4e  test    rsi, rsi
0x140003b51  jz      short loc_140003B5C
0x140003b53  mov     rcx, rsi; SRWLock
0x140003b56  call    cs:__imp_ReleaseSRWLockExclusive
0x140003b5c  mov     ecx, ebp; dwErrCode
0x140003b5e  call    cs:__imp_SetLastError
0x140003b64  mov     rsi, [rsp+28h+arg_10]
0x140003b69  mov     rbp, [rsp+28h+arg_8]
0x140003b6e  cmp     qword ptr [rbx+18h], 0
0x140003b73  setnz   al
0x140003b76  add     rsp, 20h
0x140003b7a  pop     rbx
0x140003b7b  retn
```
