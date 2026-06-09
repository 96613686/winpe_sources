# pplx::details::_CancellationTokenState::~_CancellationTokenState(void)

- ea: `0x18001ac50`
- end: `0x18001acf3`
- name: `??1_CancellationTokenState@details@pplx@@UEAA@XZ`
- size: `163`
- prototype: `void __fastcall(pplx::details::_CancellationTokenState *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b640`

## callees

- `0x180015320`
- `0x18001ac24`
- `0x18001ac50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001acda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001acda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ac6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ac6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ac9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ac9a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001acd0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001acd0`

## pseudocode

```c
void __fastcall pplx::details::_CancellationTokenState::~_CancellationTokenState(
        pplx::details::_CancellationTokenState *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  pplx::details::_RefCounter **v3; // rbx
  pplx::details::_RefCounter *v4; // rcx
  _QWORD v5[7]; // [rsp+20h] [rbp-38h] BYREF

  *(_QWORD *)this = &pplx::details::_CancellationTokenState::`vftable';
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v3 = (pplx::details::_RefCounter **)*((_QWORD *)this + 12);
  v5[0] = v3;
  *((_QWORD *)this + 12) = 0;
  v5[1] = *((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = 0;
  LeaveCriticalSection(v2);
  while ( v3 )
  {
    v4 = *v3;
    _InterlockedExchange((volatile __int32 *)*v3 + 4, 2);
    pplx::details::_RefCounter::_Release(v4);
    v3 = (pplx::details::_RefCounter **)v3[1];
  }
  pplx::details::_CancellationTokenState::TokenRegistrationContainer::~TokenRegistrationContainer((pplx::details::_CancellationTokenState::TokenRegistrationContainer *)v5);
  pplx::details::_CancellationTokenState::TokenRegistrationContainer::~TokenRegistrationContainer((pplx::details::_CancellationTokenState *)((char *)this + 96));
  DeleteCriticalSection(v2);
  CloseHandle(*((HANDLE *)this + 3));
  *(_QWORD *)this = &pplx::details::_RefCounter::`vftable';
}

```

## disassembly

```asm
0x18001ac50  push    rbx
0x18001ac52  push    rbp
0x18001ac53  push    rsi
0x18001ac54  push    rdi
0x18001ac55  sub     rsp, 38h
0x18001ac59  mov     rdi, rcx
0x18001ac5c  lea     rax, ??_7_CancellationTokenState@details@pplx@@6B@; const pplx::details::_CancellationTokenState::`vftable'
0x18001ac63  mov     [rcx], rax
0x18001ac66  lea     rbp, [rcx+20h]
0x18001ac6a  mov     rcx, rbp; lpCriticalSection
0x18001ac6d  call    cs:__imp_EnterCriticalSection
0x18001ac73  lea     rsi, [rdi+60h]
0x18001ac77  mov     rbx, [rsi]
0x18001ac7a  mov     [rsp+58h+var_38], rbx
0x18001ac7f  mov     qword ptr [rsi], 0
0x18001ac86  mov     rax, [rsi+8]
0x18001ac8a  mov     [rsp+58h+var_30], rax
0x18001ac8f  mov     qword ptr [rsi+8], 0
0x18001ac97  mov     rcx, rbp; lpCriticalSection
0x18001ac9a  call    cs:__imp_LeaveCriticalSection
0x18001aca0  jmp     short loc_18001ACB6
0x18001aca2  mov     rcx, [rbx]; this
0x18001aca5  mov     eax, 2
0x18001acaa  xchg    eax, [rcx+10h]
0x18001acad  call    ?_Release@_RefCounter@details@pplx@@QEAAJXZ; pplx::details::_RefCounter::_Release(void)
0x18001acb2  mov     rbx, [rbx+8]
0x18001acb6  test    rbx, rbx
0x18001acb9  jnz     short loc_18001ACA2
0x18001acbb  lea     rcx, [rsp+58h+var_38]; this
0x18001acc0  call    ??1TokenRegistrationContainer@_CancellationTokenState@details@pplx@@QEAA@XZ; pplx::details::_CancellationTokenState::TokenRegistrationContainer::~TokenRegistrationContainer(void)
0x18001acc5  mov     rcx, rsi; this
0x18001acc8  call    ??1TokenRegistrationContainer@_CancellationTokenState@details@pplx@@QEAA@XZ; pplx::details::_CancellationTokenState::TokenRegistrationContainer::~TokenRegistrationContainer(void)
0x18001accd  mov     rcx, rbp; lpCriticalSection
0x18001acd0  call    cs:__imp_DeleteCriticalSection
0x18001acd6  mov     rcx, [rdi+18h]; hObject
0x18001acda  call    cs:__imp_CloseHandle
0x18001ace0  lea     rax, ??_7_RefCounter@details@pplx@@6B@; const pplx::details::_RefCounter::`vftable'
0x18001ace7  mov     [rdi], rax
0x18001acea  add     rsp, 38h
0x18001acee  pop     rdi
0x18001acef  pop     rsi
0x18001acf0  pop     rbp
0x18001acf1  pop     rbx
0x18001acf2  retn
```
