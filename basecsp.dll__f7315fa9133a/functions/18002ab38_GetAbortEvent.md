# GetAbortEvent

- ea: `0x18002ab38`
- end: `0x18002abdf`
- name: `GetAbortEvent`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002af98`

## callees

- `0x18002ab38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ab6c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ab6c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002abb6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002abb6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002ab87`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002ab87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002abca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002abca`

## pseudocode

```c
void __fastcall GetAbortEvent(unsigned int a1, _QWORD *a2, struct _TP_TIMER **a3, _QWORD *a4)
{
  __int64 v5; // rbp
  HANDLE EventW; // rbx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v10; // rdi
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-48h] BYREF

  v5 = a1;
  pftDueTime = 0;
  EventW = CreateEventW(0, 0, 0, L"CancelSCCredUI");
  if ( EventW )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(TimerCallback, (PVOID)L"CancelSCCredUI", 0);
    v10 = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      pftDueTime = (struct _FILETIME)(-10000000 * v5);
      SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
      *a2 = EventW;
      *a3 = v10;
      *a4 = L"CancelSCCredUI";
    }
    else
    {
      CloseHandle(EventW);
    }
  }
}

```

## disassembly

```asm
0x18002ab38  push    rbx
0x18002ab3a  push    rbp
0x18002ab3b  push    rsi
0x18002ab3c  push    rdi
0x18002ab3d  push    r12
0x18002ab3f  push    r14
0x18002ab41  push    r15
0x18002ab43  sub     rsp, 30h
0x18002ab47  mov     rsi, r9
0x18002ab4a  mov     ebp, ecx
0x18002ab4c  mov     r14, r8
0x18002ab4f  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0
0x18002ab58  mov     r15, rdx
0x18002ab5b  lea     r12, pv; "CancelSCCredUI"
0x18002ab62  mov     r9, r12; lpName
0x18002ab65  xor     r8d, r8d; bInitialState
0x18002ab68  xor     edx, edx; bManualReset
0x18002ab6a  xor     ecx, ecx; lpEventAttributes
0x18002ab6c  call    cs:__imp_CreateEventW
0x18002ab72  mov     rbx, rax
0x18002ab75  test    rax, rax
0x18002ab78  jz      short loc_18002ABD0
0x18002ab7a  xor     r8d, r8d; pcbe
0x18002ab7d  lea     rcx, TimerCallback; pfnti
0x18002ab84  mov     rdx, r12; pv
0x18002ab87  call    cs:__imp_CreateThreadpoolTimer
0x18002ab8d  mov     rdi, rax
0x18002ab90  test    rax, rax
0x18002ab93  jz      short loc_18002ABC7
0x18002ab95  imul    rcx, rbp, 0FFFFFFFFFF676980h
0x18002ab9c  xor     r9d, r9d; msWindowLength
0x18002ab9f  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18002aba4  mov     [rsp+68h+pftDueTime.dwLowDateTime], ecx
0x18002aba8  xor     r8d, r8d; msPeriod
0x18002abab  shr     rcx, 20h
0x18002abaf  mov     [rsp+68h+pftDueTime.dwHighDateTime], ecx
0x18002abb3  mov     rcx, rax; pti
0x18002abb6  call    cs:__imp_SetThreadpoolTimer
0x18002abbc  mov     [r15], rbx
0x18002abbf  mov     [r14], rdi
0x18002abc2  mov     [rsi], r12
0x18002abc5  jmp     short loc_18002ABD0
0x18002abc7  mov     rcx, rbx; hObject
0x18002abca  call    cs:__imp_CloseHandle
0x18002abd0  add     rsp, 30h
0x18002abd4  pop     r15
0x18002abd6  pop     r14
0x18002abd8  pop     r12
0x18002abda  pop     rdi
0x18002abdb  pop     rsi
0x18002abdc  pop     rbp
0x18002abdd  pop     rbx
0x18002abde  retn
```
