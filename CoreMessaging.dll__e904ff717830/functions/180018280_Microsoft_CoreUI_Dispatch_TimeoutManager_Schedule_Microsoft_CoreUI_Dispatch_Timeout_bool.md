# Microsoft::CoreUI::Dispatch::TimeoutManager::Schedule(Microsoft::CoreUI::Dispatch::Timeout *,bool)

- ea: `0x180018280`
- end: `0x18001837b`
- name: `?Schedule@TimeoutManager@Dispatch@CoreUI@Microsoft@@QEAAXPEAVTimeout@234@_N@Z`
- size: `251`
- prototype: `void(Microsoft::CoreUI::Dispatch::TimeoutManager *__hidden this, struct Microsoft::CoreUI::Dispatch::Timeout *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180017d80`
- `0x1800b6660`

## callees

- `0x180018280`
- `0x18008ae1c`
- `0x18008f584`
- `0x1800a9824`
- `0x1800b6700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180018326`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180018326`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180018303`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180018303`

## pseudocode

```c
void __fastcall Microsoft::CoreUI::Dispatch::TimeoutManager::Schedule(
        const char16_t *this,
        struct Microsoft::CoreUI::Dispatch::Timeout *a2,
        unsigned __int8 a3)
{
  int v5; // edx
  int v6; // eax
  const char16_t *v7; // rcx
  __int64 v8; // rdi
  HANDLE WaitableTimer; // rax
  int v10; // edx
  int v11; // eax
  LARGE_INTEGER DueTime; // [rsp+48h] [rbp+10h] BYREF

  if ( *((_BYTE *)a2 + 96) )
    CFlat::Abandonment::Fail(this);
  if ( *((_BYTE *)a2 + 97) )
  {
    v5 = *((_DWORD *)this + 20);
    v6 = 1;
    v7 = (const char16_t *)(unsigned int)(v5 + 1);
    if ( v5 != -1 )
      v6 = v5 + 1;
    *((_DWORD *)this + 20) = v6;
    *((_BYTE *)a2 + 96) = 1;
    *((_DWORD *)a2 + 16) = v5;
    v8 = *((_QWORD *)a2 + (a3 ^ 1LL) + 10);
    WaitableTimer = (HANDLE)*((_QWORD *)a2 + 7);
    if ( !WaitableTimer )
    {
      WaitableTimer = CreateWaitableTimerExW(0, 0, 1u, 0x1F0003u);
      if ( !WaitableTimer )
        Cn::FailFast::ForWin32();
      *((_QWORD *)a2 + 7) = WaitableTimer;
    }
    if ( v8 < 0 )
      CFlat::Abandonment::Fail(v7);
    DueTime.QuadPart = -v8;
    if ( !SetWaitableTimer(WaitableTimer, &DueTime, 0, 0, 0, 0) )
      Cn::FailFast::ForWin32();
  }
  else
  {
    if ( a3 )
      Microsoft::CoreUI::Dispatch::Timeout::UpdateAbsoluteDueTimeOnRepeat(a2);
    v10 = *((_DWORD *)this + 20);
    v11 = 1;
    if ( v10 != -1 )
      v11 = v10 + 1;
    *((_DWORD *)this + 20) = v11;
    *((_DWORD *)a2 + 16) = v10;
    *((_BYTE *)a2 + 96) = 1;
    Microsoft::CoreUI::Dispatch::TimeoutManager::EnableAbsoluteTimer(
      (Microsoft::CoreUI::Dispatch::TimeoutManager *)(unsigned int)(v10 + 1),
      a2);
  }
}

```

## disassembly

```asm
0x180018280  mov     [rsp+arg_0], rbx
0x180018285  push    rdi
0x180018286  sub     rsp, 30h
0x18001828a  cmp     byte ptr [rdx+60h], 0
0x18001828e  mov     rbx, rdx
0x180018291  mov     rdi, rcx
0x180018294  jz      short loc_18001829C
0x180018296  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18001829c  cmp     byte ptr [rdx+61h], 0
0x1800182a0  jz      loc_180018349
0x1800182a6  mov     edx, [rcx+50h]
0x1800182a9  mov     eax, 1
0x1800182ae  cmp     edx, 0FFFFFFFFh
0x1800182b1  lea     ecx, [rdx+1]; char16_t *
0x1800182b4  cmovnz  eax, ecx
0x1800182b7  mov     [rdi+50h], eax
0x1800182ba  movzx   eax, r8b
0x1800182be  xor     rax, 1
0x1800182c2  mov     byte ptr [rbx+60h], 1
0x1800182c6  mov     [rbx+40h], edx
0x1800182c9  mov     rdi, [rbx+rax*8+50h]
0x1800182ce  mov     rax, [rbx+38h]
0x1800182d2  test    rax, rax
0x1800182d5  jz      short loc_180018318
0x1800182d7  test    rdi, rdi
0x1800182da  js      short loc_180018337
0x1800182dc  neg     rdi
0x1800182df  mov     [rsp+38h+fResume], 0; fResume
0x1800182e7  xor     r9d, r9d; pfnCompletionRoutine
0x1800182ea  mov     qword ptr [rsp+38h+DueTime], rdi
0x1800182ef  xor     r8d, r8d; lPeriod
0x1800182f2  mov     [rsp+38h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x1800182fb  lea     rdx, [rsp+38h+DueTime]; lpDueTime
0x180018300  mov     rcx, rax; hTimer
0x180018303  call    cs:__imp_SetWaitableTimer
0x180018309  test    eax, eax
0x18001830b  jz      short loc_18001833D
0x18001830d  mov     rbx, [rsp+38h+arg_0]
0x180018312  add     rsp, 30h
0x180018316  pop     rdi
0x180018317  retn
0x180018318  xor     edx, edx; lpTimerName
0x18001831a  xor     ecx, ecx; lpTimerAttributes
0x18001831c  mov     r9d, 1F0003h; dwDesiredAccess
0x180018322  lea     r8d, [rdx+1]; dwFlags
0x180018326  call    cs:__imp_CreateWaitableTimerExW
0x18001832c  test    rax, rax
0x18001832f  jnz     short loc_180018343
0x180018331  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
0x180018337  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18001833d  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
0x180018343  mov     [rbx+38h], rax
0x180018347  jmp     short loc_1800182D7
0x180018349  test    r8b, r8b
0x18001834c  jz      short loc_180018356
0x18001834e  mov     rcx, rbx; this
0x180018351  call    ?UpdateAbsoluteDueTimeOnRepeat@Timeout@Dispatch@CoreUI@Microsoft@@QEAAXXZ; Microsoft::CoreUI::Dispatch::Timeout::UpdateAbsoluteDueTimeOnRepeat(void)
0x180018356  mov     edx, [rdi+50h]
0x180018359  mov     eax, 1
0x18001835e  cmp     edx, 0FFFFFFFFh
0x180018361  lea     ecx, [rdx+1]; this
0x180018364  cmovnz  eax, ecx
0x180018367  mov     [rdi+50h], eax
0x18001836a  mov     [rbx+40h], edx
0x18001836d  mov     rdx, rbx; struct Microsoft::CoreUI::Dispatch::Timeout *
0x180018370  mov     byte ptr [rbx+60h], 1
0x180018374  call    ?EnableAbsoluteTimer@TimeoutManager@Dispatch@CoreUI@Microsoft@@AEAAXPEAVTimeout@234@@Z; Microsoft::CoreUI::Dispatch::TimeoutManager::EnableAbsoluteTimer(Microsoft::CoreUI::Dispatch::Timeout *)
0x180018379  jmp     short loc_18001830D
```
