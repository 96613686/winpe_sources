# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1800119d4`
- end: `0x180011a82`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `174`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f890`
- `0x180013804`
- `0x180015074`
- `0x180015630`

## callees

- `0x180011324`
- `0x1800119d4`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011a61`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011a61`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011a48`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011a48`
- `KERNEL32!GetLastError` at `0x1800119eb`
- `KERNEL32!GetLastError` at `0x1800119eb`
- `KERNEL32!SetLastError` at `0x180011a6a`
- `KERNEL32!SetLastError` at `0x180011a6a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall wil::details::FeatureStateManager::EnsureStateData(wil::details::FeatureStateManager *this)
{
  DWORD LastError; // ebp
  __int64 v3; // rsi
  __int64 v5; // [rsp+50h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 3) )
  {
    LastError = GetLastError();
    if ( *((_QWORD *)this + 3) )
    {
      v3 = 0;
    }
    else
    {
      if ( !*((_QWORD *)this + 2) )
      {
        v5 = 0;
        if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
                    *((_QWORD *)this + 1),
                    &v5) >= 0
          && !*((_QWORD *)this + 2) )
        {
          *((_QWORD *)this + 2) = v5;
        }
      }
      v3 = (*((_QWORD *)this + 2) + 32LL) & -(__int64)(*((_QWORD *)this + 2) != 0);
    }
    AcquireSRWLockExclusive((PSRWLOCK)this + 4);
    if ( !*((_QWORD *)this + 3) )
      *((_QWORD *)this + 3) = v3;
    if ( this != (wil::details::FeatureStateManager *)-32LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 4);
    SetLastError(LastError);
  }
  return *((_QWORD *)this + 3) != 0;
}

```

## disassembly

```asm
0x1800119d4  push    rbx
0x1800119d6  push    rbp
0x1800119d7  push    rsi
0x1800119d8  push    rdi
0x1800119d9  sub     rsp, 28h
0x1800119dd  mov     rbx, rcx
0x1800119e0  cmp     qword ptr [rcx+18h], 0
0x1800119e5  jnz     loc_180011A71
0x1800119eb  call    cs:__imp_GetLastError
0x1800119f1  mov     ebp, eax
0x1800119f3  cmp     qword ptr [rbx+18h], 0
0x1800119f8  jz      short loc_1800119FE
0x1800119fa  xor     esi, esi
0x1800119fc  jmp     short loc_180011A41
0x1800119fe  cmp     qword ptr [rbx+10h], 0
0x180011a03  jnz     short loc_180011A30
0x180011a05  mov     [rsp+48h+arg_0], 0
0x180011a0e  lea     rdx, [rsp+48h+arg_0]
0x180011a13  mov     rcx, [rbx+8]
0x180011a17  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180011a1c  test    eax, eax
0x180011a1e  js      short loc_180011A30
0x180011a20  cmp     qword ptr [rbx+10h], 0
0x180011a25  jnz     short loc_180011A30
0x180011a27  mov     rax, [rsp+48h+arg_0]
0x180011a2c  mov     [rbx+10h], rax
0x180011a30  mov     rcx, [rbx+10h]
0x180011a34  lea     rax, [rcx+20h]
0x180011a38  neg     rcx
0x180011a3b  sbb     rsi, rsi
0x180011a3e  and     rsi, rax
0x180011a41  lea     rdi, [rbx+20h]
0x180011a45  mov     rcx, rdi; SRWLock
0x180011a48  call    cs:__imp_AcquireSRWLockExclusive
0x180011a4e  cmp     qword ptr [rbx+18h], 0
0x180011a53  jnz     short loc_180011A59
0x180011a55  mov     [rbx+18h], rsi
0x180011a59  test    rdi, rdi
0x180011a5c  jz      short loc_180011A68
0x180011a5e  mov     rcx, rdi; SRWLock
0x180011a61  call    cs:__imp_ReleaseSRWLockExclusive
0x180011a67  nop
0x180011a68  mov     ecx, ebp; dwErrCode
0x180011a6a  call    cs:__imp_SetLastError
0x180011a70  nop
0x180011a71  cmp     qword ptr [rbx+18h], 0
0x180011a76  setnz   al
0x180011a79  add     rsp, 28h
0x180011a7d  pop     rdi
0x180011a7e  pop     rsi
0x180011a7f  pop     rbp
0x180011a80  pop     rbx
0x180011a81  retn
```
