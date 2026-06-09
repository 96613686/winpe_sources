# LeaseMachine::Invalid::EnterState(LeaseMachine &)

- ea: `0x18001a540`
- end: `0x18001a6b6`
- name: `?EnterState@Invalid@LeaseMachine@@UEBAXAEAV2@@Z`
- size: `374`
- prototype: `void __fastcall(LeaseMachine::Invalid *__hidden this, struct LeaseMachine *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180004738`
- `0x180013b50`
- `0x18001a540`
- `0x18001a794`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a592`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a5d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a592`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a5d0`

## string_xrefs

- `0x18001a59f`: `GetCurrentThreadId() == _queueThread`
- `0x18001a689`: `GetCurrentThreadId() == _queueThread`
- `0x18001a644`: `StateMachine<class LeaseMachine,class LeaseState>::AssertQueueThread`
- `0x18001a682`: `StateMachine<class LeaseMachine,class LeaseState>::AssertQueueThread`

## pseudocode

```c
void __fastcall LeaseMachine::Invalid::EnterState(LeaseMachine::Invalid *this, struct LeaseMachine *a2)
{
  _QWORD *v2; // rdi
  __int64 v3; // rcx
  unsigned int v5; // esi
  char *v6; // r15
  char *v7; // rbp
  _QWORD *v8; // r14
  int v9; // ebx
  int v10; // [rsp+78h] [rbp+10h] BYREF
  int v11; // [rsp+80h] [rbp+18h] BYREF

  v2 = (_QWORD *)((char *)a2 + 208);
  v3 = *((_QWORD *)a2 + 26);
  v10 = 0;
  if ( !v3
    || (v11 = 0,
        (*(void (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v3 + 48LL))(v3, &v11, &v10),
        v5 = v10,
        v10 >= 0) )
  {
    v5 = 0;
  }
  v6 = (char *)a2 + 32;
  if ( GetCurrentThreadId() != *((_DWORD *)a2 + 32) )
    LogMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\statemachine.h",
      0x49u,
      "StateMachine<class LeaseMachine,class LeaseState>::AssertQueueThread",
      (wchar_t *)L"Assert (%s): %s",
      L"GetCurrentThreadId() == _queueThread",
      L"Failed");
  v7 = (char *)a2 + 176;
  if ( *v2 )
  {
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v2);
    v8 = (_QWORD *)((char *)a2 + 136);
    (*(void (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)a2 + 17) + 48LL))(
      *((_QWORD *)a2 + 17),
      (char *)a2 + 176,
      v5);
  }
  else
  {
    v8 = (_QWORD *)((char *)a2 + 136);
  }
  v9 = *((_DWORD *)a2 + 32);
  if ( GetCurrentThreadId() != v9 )
    LogMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\statemachine.h",
      0x49u,
      "StateMachine<class LeaseMachine,class LeaseState>::AssertQueueThread",
      (wchar_t *)L"Assert (%s): %s",
      L"GetCurrentThreadId() == _queueThread",
      L"Failed");
  StateMachine<LeaseMachine,LeaseState>::AssertQueueThread(v6);
  (*(void (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v8 + 24LL))(*v8, v7);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v8);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v2);
}

```

## disassembly

```asm
0x18001a540  mov     r11, rsp
0x18001a543  mov     [r11+8], rbx
0x18001a547  push    rbp
0x18001a548  push    rsi
0x18001a549  push    rdi
0x18001a54a  push    r14
0x18001a54c  push    r15
0x18001a54e  sub     rsp, 40h
0x18001a552  xor     r14d, r14d
0x18001a555  lea     rdi, [rdx+0D0h]
0x18001a55c  mov     rcx, [rdi]
0x18001a55f  mov     rbx, rdx
0x18001a562  mov     [r11+10h], r14d
0x18001a566  test    rcx, rcx
0x18001a569  jz      short loc_18001A58B
0x18001a56b  mov     [r11+18h], r14d
0x18001a56f  lea     r8, [r11+10h]
0x18001a573  mov     rax, [rcx]
0x18001a576  lea     rdx, [r11+18h]
0x18001a57a  mov     rax, [rax+30h]
0x18001a57e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a583  mov     esi, [rsp+68h+arg_8]
0x18001a587  test    esi, esi
0x18001a589  js      short loc_18001A58E
0x18001a58b  mov     esi, r14d
0x18001a58e  lea     r15, [rbx+20h]
0x18001a592  call    cs:__imp_GetCurrentThreadId
0x18001a598  lea     rcx, aFailed; "Failed"
0x18001a59f  lea     rdx, aGetcurrentthre; "GetCurrentThreadId() == _queueThread"
0x18001a5a6  lea     r8, aAssertSS; "Assert (%s): %s"
0x18001a5ad  cmp     eax, [r15+60h]
0x18001a5b1  jnz     loc_18001A63F
0x18001a5b7  lea     rbp, [rbx+0B0h]
0x18001a5be  cmp     [rdi], r14
0x18001a5c1  jnz     short loc_18001A619
0x18001a5c3  lea     r14, [rbx+88h]
0x18001a5ca  mov     ebx, [rbx+80h]
0x18001a5d0  call    cs:__imp_GetCurrentThreadId
0x18001a5d6  cmp     eax, ebx
0x18001a5d8  jnz     loc_18001A670
0x18001a5de  mov     rcx, r15
0x18001a5e1  call    ?AssertQueueThread@?$StateMachine@VLeaseMachine@@VLeaseState@@@@IEAAXXZ; StateMachine<LeaseMachine,LeaseState>::AssertQueueThread(void)
0x18001a5e6  mov     rcx, [r14]
0x18001a5e9  mov     rdx, rbp
0x18001a5ec  mov     rax, [rcx]
0x18001a5ef  mov     rax, [rax+18h]
0x18001a5f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5f8  mov     rcx, r14
0x18001a5fb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001a600  mov     rcx, rdi
0x18001a603  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001a608  mov     rbx, [rsp+68h+arg_0]
0x18001a60d  add     rsp, 40h
0x18001a611  pop     r15
0x18001a613  pop     r14
0x18001a615  pop     rdi
0x18001a616  pop     rsi
0x18001a617  pop     rbp
0x18001a618  retn
0x18001a619  mov     rcx, rdi
0x18001a61c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001a621  lea     r14, [rbx+88h]
0x18001a628  mov     r8d, esi
0x18001a62b  mov     rcx, [r14]
0x18001a62e  mov     rdx, rbp
0x18001a631  mov     rax, [rcx]
0x18001a634  mov     rax, [rax+30h]
0x18001a638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a63d  jmp     short loc_18001A5CA
0x18001a63f  mov     [rsp+68h+var_38], rcx
0x18001a644  lea     r9, aStatemachineCl_1; "StateMachine<class LeaseMachine,class L"...
0x18001a64b  mov     [rsp+68h+var_40], rdx
0x18001a650  lea     rdx, aOnecoreuapEndu_2; "onecoreuap\\enduser\\winstore\\licensem"...
0x18001a657  mov     [rsp+68h+Format], r8; Format
0x18001a65c  mov     r8d, 49h ; 'I'; unsigned int
0x18001a662  lea     ecx, [r8-48h]; unsigned int
0x18001a666  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18001a66b  jmp     loc_18001A5B7
0x18001a670  lea     rax, aFailed; "Failed"
0x18001a677  mov     r8d, 49h ; 'I'; unsigned int
0x18001a67d  mov     [rsp+68h+var_38], rax
0x18001a682  lea     r9, aStatemachineCl_1; "StateMachine<class LeaseMachine,class L"...
0x18001a689  lea     rax, aGetcurrentthre; "GetCurrentThreadId() == _queueThread"
0x18001a690  mov     [rsp+68h+var_40], rax
0x18001a695  lea     rdx, aOnecoreuapEndu_2; "onecoreuap\\enduser\\winstore\\licensem"...
0x18001a69c  lea     rax, aAssertSS; "Assert (%s): %s"
0x18001a6a3  lea     ecx, [r8-48h]; unsigned int
0x18001a6a7  mov     [rsp+68h+Format], rax; Format
0x18001a6ac  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18001a6b1  jmp     loc_18001A5DE
```
