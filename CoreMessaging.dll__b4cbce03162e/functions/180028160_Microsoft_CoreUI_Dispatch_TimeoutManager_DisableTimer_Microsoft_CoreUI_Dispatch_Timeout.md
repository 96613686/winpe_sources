# Microsoft::CoreUI::Dispatch::TimeoutManager::DisableTimer(Microsoft::CoreUI::Dispatch::Timeout *)

- ea: `0x180028160`
- end: `0x180028210`
- name: `?DisableTimer@TimeoutManager@Dispatch@CoreUI@Microsoft@@AEAAXPEAVTimeout@234@@Z`
- size: `176`
- prototype: `void __fastcall(Microsoft::CoreUI::Dispatch::TimeoutManager *__hidden this, struct Microsoft::CoreUI::Dispatch::Timeout *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180027eac`
- `0x180027f50`

## callees

- `0x180028160`
- `0x18008f584`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x1800281f0`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x1800281f0`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1800281c9`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1800281c9`

## pseudocode

```c
void __fastcall Microsoft::CoreUI::Dispatch::TimeoutManager::DisableTimer(
        Microsoft::CoreUI::Dispatch::TimeoutManager *this,
        struct Microsoft::CoreUI::Dispatch::Timeout *a2)
{
  HANDLE WaitableTimer; // rax
  char v4; // si
  BOOL fResume; // edi
  LARGE_INTEGER DueTime; // [rsp+40h] [rbp+8h] BYREF

  DueTime.QuadPart = (LONGLONG)this;
  WaitableTimer = (HANDLE)*((_QWORD *)a2 + 7);
  v4 = *((_BYTE *)a2 + 97);
  fResume = 1;
  if ( !WaitableTimer )
  {
    WaitableTimer = CreateWaitableTimerExW(0, 0, 1u, 0x1F0003u);
    if ( !WaitableTimer )
      Cn::FailFast::ForWin32();
    *((_QWORD *)a2 + 7) = WaitableTimer;
  }
  DueTime.QuadPart = 0x7FFFFFFFFFFFFFFFLL;
  if ( v4 )
  {
    fResume = 0;
    DueTime.QuadPart = 0x8000000000000001uLL;
  }
  if ( !SetWaitableTimer(WaitableTimer, &DueTime, 0, 0, 0, fResume) )
    Cn::FailFast::ForWin32();
}

```

## disassembly

```asm
0x180028160  mov     [rsp+arg_8], rbx
0x180028165  mov     [rsp+arg_10], rsi
0x18002816a  mov     qword ptr [rsp+DueTime], rcx
0x18002816f  push    rdi
0x180028170  sub     rsp, 30h
0x180028174  mov     rax, [rdx+38h]
0x180028178  mov     rbx, rdx
0x18002817b  mov     sil, [rdx+61h]
0x18002817f  mov     edi, 1
0x180028184  test    rax, rax
0x180028187  jz      short loc_1800281E3
0x180028189  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180028193  mov     qword ptr [rsp+38h+DueTime], rcx
0x180028198  test    sil, sil
0x18002819b  jz      short loc_1800281AE
0x18002819d  mov     rcx, 8000000000000001h
0x1800281a7  xor     edi, edi
0x1800281a9  mov     qword ptr [rsp+38h+DueTime], rcx
0x1800281ae  mov     [rsp+38h+fResume], edi; fResume
0x1800281b2  lea     rdx, [rsp+38h+DueTime]; lpDueTime
0x1800281b7  xor     r9d, r9d; pfnCompletionRoutine
0x1800281ba  mov     [rsp+38h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x1800281c3  xor     r8d, r8d; lPeriod
0x1800281c6  mov     rcx, rax; hTimer
0x1800281c9  call    cs:__imp_SetWaitableTimer
0x1800281cf  test    eax, eax
0x1800281d1  jz      short loc_180028201
0x1800281d3  mov     rbx, [rsp+38h+arg_8]
0x1800281d8  mov     rsi, [rsp+38h+arg_10]
0x1800281dd  add     rsp, 30h
0x1800281e1  pop     rdi
0x1800281e2  retn
0x1800281e3  mov     r9d, 1F0003h; dwDesiredAccess
0x1800281e9  mov     r8d, edi; dwFlags
0x1800281ec  xor     edx, edx; lpTimerName
0x1800281ee  xor     ecx, ecx; lpTimerAttributes
0x1800281f0  call    cs:__imp_CreateWaitableTimerExW
0x1800281f6  test    rax, rax
0x1800281f9  jnz     short loc_180028207
0x1800281fb  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
0x180028201  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
0x180028207  mov     [rbx+38h], rax
0x18002820b  jmp     loc_180028189
```
