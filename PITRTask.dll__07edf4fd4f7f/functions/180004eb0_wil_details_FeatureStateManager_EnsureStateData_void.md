# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180004eb0`
- end: `0x180004f5c`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800024e0`
- `0x1800077c4`
- `0x1800098f0`
- `0x180009f30`

## callees

- `0x180004254`
- `0x180004eb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004f3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004f3d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004f24`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004f24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ec7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ec7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004f45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004f45`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureStateData(RTL_SRWLOCK *this)
{
  DWORD LastError; // ebp
  __int64 v3; // rsi
  __int64 Ptr; // rcx
  void *v6; // [rsp+20h] [rbp-38h] BYREF

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
0x180004eb0  push    rbx
0x180004eb2  push    rbp
0x180004eb3  push    rsi
0x180004eb4  push    rdi
0x180004eb5  sub     rsp, 38h
0x180004eb9  cmp     qword ptr [rcx+18h], 0
0x180004ebe  mov     rbx, rcx
0x180004ec1  jnz     loc_180004F4B
0x180004ec7  call    cs:__imp_GetLastError
0x180004ecd  cmp     qword ptr [rbx+18h], 0
0x180004ed2  mov     ebp, eax
0x180004ed4  jz      short loc_180004EDA
0x180004ed6  xor     esi, esi
0x180004ed8  jmp     short loc_180004F1D
0x180004eda  cmp     qword ptr [rbx+10h], 0
0x180004edf  jnz     short loc_180004F0C
0x180004ee1  mov     rcx, [rbx+8]
0x180004ee5  lea     rdx, [rsp+58h+var_38]
0x180004eea  mov     [rsp+58h+var_38], 0
0x180004ef3  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180004ef8  test    eax, eax
0x180004efa  js      short loc_180004F0C
0x180004efc  cmp     qword ptr [rbx+10h], 0
0x180004f01  jnz     short loc_180004F0C
0x180004f03  mov     rax, [rsp+58h+var_38]
0x180004f08  mov     [rbx+10h], rax
0x180004f0c  mov     rax, [rbx+10h]
0x180004f10  lea     rcx, [rax+20h]
0x180004f14  neg     rax
0x180004f17  sbb     rsi, rsi
0x180004f1a  and     rsi, rcx
0x180004f1d  lea     rdi, [rbx+20h]
0x180004f21  mov     rcx, rdi; SRWLock
0x180004f24  call    cs:__imp_AcquireSRWLockExclusive
0x180004f2a  cmp     qword ptr [rbx+18h], 0
0x180004f2f  jnz     short loc_180004F35
0x180004f31  mov     [rbx+18h], rsi
0x180004f35  test    rdi, rdi
0x180004f38  jz      short loc_180004F43
0x180004f3a  mov     rcx, rdi; SRWLock
0x180004f3d  call    cs:__imp_ReleaseSRWLockExclusive
0x180004f43  mov     ecx, ebp; dwErrCode
0x180004f45  call    cs:__imp_SetLastError
0x180004f4b  cmp     qword ptr [rbx+18h], 0
0x180004f50  setnz   al
0x180004f53  add     rsp, 38h
0x180004f57  pop     rdi
0x180004f58  pop     rsi
0x180004f59  pop     rbp
0x180004f5a  pop     rbx
0x180004f5b  retn
```
