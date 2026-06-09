# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1800059dc`
- end: `0x180005a8b`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `175`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002210`
- `0x180008704`
- `0x18000a11c`
- `0x18000ab20`

## callees

- `0x18000487c`
- `0x1800059dc`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180005a73`
- `KERNEL32!SetLastError` at `0x180005a73`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005a6a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005a6a`
- `KERNEL32!GetLastError` at `0x1800059f3`
- `KERNEL32!GetLastError` at `0x1800059f3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180005a50`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180005a50`

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
0x1800059dc  push    rbx
0x1800059de  push    rbp
0x1800059df  push    rsi
0x1800059e0  push    rdi
0x1800059e1  sub     rsp, 28h
0x1800059e5  mov     rbx, rcx
0x1800059e8  cmp     qword ptr [rcx+18h], 0
0x1800059ed  jnz     loc_180005A7A
0x1800059f3  call    cs:__imp_GetLastError
0x1800059f9  mov     ebp, eax
0x1800059fb  cmp     qword ptr [rbx+18h], 0
0x180005a00  jz      short loc_180005A06
0x180005a02  xor     esi, esi
0x180005a04  jmp     short loc_180005A49
0x180005a06  cmp     qword ptr [rbx+10h], 0
0x180005a0b  jnz     short loc_180005A38
0x180005a0d  mov     [rsp+48h+arg_0], 0
0x180005a16  lea     rdx, [rsp+48h+arg_0]
0x180005a1b  mov     rcx, [rbx+8]
0x180005a1f  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180005a24  test    eax, eax
0x180005a26  js      short loc_180005A38
0x180005a28  cmp     qword ptr [rbx+10h], 0
0x180005a2d  jnz     short loc_180005A38
0x180005a2f  mov     rax, [rsp+48h+arg_0]
0x180005a34  mov     [rbx+10h], rax
0x180005a38  mov     rcx, [rbx+10h]
0x180005a3c  lea     rax, [rcx+20h]
0x180005a40  neg     rcx
0x180005a43  sbb     rsi, rsi
0x180005a46  and     rsi, rax
0x180005a49  lea     rdi, [rbx+20h]
0x180005a4d  mov     rcx, rdi; SRWLock
0x180005a50  call    cs:__imp_AcquireSRWLockExclusive
0x180005a56  nop
0x180005a57  cmp     qword ptr [rbx+18h], 0
0x180005a5c  jnz     short loc_180005A62
0x180005a5e  mov     [rbx+18h], rsi
0x180005a62  test    rdi, rdi
0x180005a65  jz      short loc_180005A71
0x180005a67  mov     rcx, rdi; SRWLock
0x180005a6a  call    cs:__imp_ReleaseSRWLockExclusive
0x180005a70  nop
0x180005a71  mov     ecx, ebp; dwErrCode
0x180005a73  call    cs:__imp_SetLastError
0x180005a79  nop
0x180005a7a  cmp     qword ptr [rbx+18h], 0
0x180005a7f  setnz   al
0x180005a82  add     rsp, 28h
0x180005a86  pop     rdi
0x180005a87  pop     rsi
0x180005a88  pop     rbp
0x180005a89  pop     rbx
0x180005a8a  retn
```
