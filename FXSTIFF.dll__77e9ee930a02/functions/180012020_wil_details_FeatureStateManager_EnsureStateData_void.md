# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180012020`
- end: `0x1800120e7`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `199`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800100a0`
- `0x180014024`
- `0x180015ae4`
- `0x1800161a0`

## callees

- `0x180011a14`
- `0x180012020`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800120b9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800120b9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001209a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001209a`
- `KERNEL32!GetLastError` at `0x180012037`
- `KERNEL32!GetLastError` at `0x180012037`
- `KERNEL32!SetLastError` at `0x1800120c8`
- `KERNEL32!SetLastError` at `0x1800120c8`

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
0x180012020  push    rbx
0x180012022  push    rbp
0x180012023  push    rsi
0x180012024  push    rdi
0x180012025  sub     rsp, 28h
0x180012029  mov     rbx, rcx
0x18001202c  cmp     qword ptr [rcx+18h], 0
0x180012031  jnz     loc_1800120D5
0x180012037  call    cs:__imp_GetLastError
0x18001203e  nop     dword ptr [rax+rax+00h]
0x180012043  mov     ebp, eax
0x180012045  cmp     qword ptr [rbx+18h], 0
0x18001204a  jz      short loc_180012050
0x18001204c  xor     esi, esi
0x18001204e  jmp     short loc_180012093
0x180012050  cmp     qword ptr [rbx+10h], 0
0x180012055  jnz     short loc_180012082
0x180012057  mov     [rsp+48h+arg_0], 0
0x180012060  lea     rdx, [rsp+48h+arg_0]
0x180012065  mov     rcx, [rbx+8]
0x180012069  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18001206e  test    eax, eax
0x180012070  js      short loc_180012082
0x180012072  cmp     qword ptr [rbx+10h], 0
0x180012077  jnz     short loc_180012082
0x180012079  mov     rax, [rsp+48h+arg_0]
0x18001207e  mov     [rbx+10h], rax
0x180012082  mov     rcx, [rbx+10h]
0x180012086  lea     rax, [rcx+20h]
0x18001208a  neg     rcx
0x18001208d  sbb     rsi, rsi
0x180012090  and     rsi, rax
0x180012093  lea     rdi, [rbx+20h]
0x180012097  mov     rcx, rdi; SRWLock
0x18001209a  call    cs:__imp_AcquireSRWLockExclusive
0x1800120a1  nop     dword ptr [rax+rax+00h]
0x1800120a6  cmp     qword ptr [rbx+18h], 0
0x1800120ab  jnz     short loc_1800120B1
0x1800120ad  mov     [rbx+18h], rsi
0x1800120b1  test    rdi, rdi
0x1800120b4  jz      short loc_1800120C6
0x1800120b6  mov     rcx, rdi; SRWLock
0x1800120b9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800120c0  nop     dword ptr [rax+rax+00h]
0x1800120c5  nop
0x1800120c6  mov     ecx, ebp; dwErrCode
0x1800120c8  call    cs:__imp_SetLastError
0x1800120cf  nop     dword ptr [rax+rax+00h]
0x1800120d4  nop
0x1800120d5  cmp     qword ptr [rbx+18h], 0
0x1800120da  setnz   al
0x1800120dd  add     rsp, 28h
0x1800120e1  pop     rdi
0x1800120e2  pop     rsi
0x1800120e3  pop     rbp
0x1800120e4  pop     rbx
0x1800120e5  retn
```
