# CWorkFifo::InitializeTheadpool(void)

- ea: `0x18012fbd8`
- end: `0x18012fc94`
- name: `?InitializeTheadpool@CWorkFifo@@AEAAJXZ`
- size: `188`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18012fb00`

## callees

- `0x1800b6978`
- `0x18012fbd8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18012fbe7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18012fbe7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18012fc6c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18012fc6c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18012fc17`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18012fc17`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18012fc48`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18012fc48`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18012fc2d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18012fc2d`

## pseudocode

```c
__int64 __fastcall CWorkFifo::InitializeTheadpool(char *pv)
{
  struct _TP_POOL *Threadpool; // rax
  const char *v3; // r9
  __int64 v4; // rdx
  PTP_TIMER ThreadpoolTimer; // rax
  PTP_WORK ThreadpoolWork; // rax
  bool v8; // zf
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Threadpool = CreateThreadpool(0);
  *(_QWORD *)pv = Threadpool;
  if ( !Threadpool )
  {
    v4 = 220;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"avcore\\audiocore\\server\\audiosrv\\spatialaudioresourcemanager\\WorkFifo.h",
             v3);
  }
  if ( !SetThreadpoolThreadMinimum(Threadpool, 1u) )
  {
    v4 = 223;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"avcore\\audiocore\\server\\audiosrv\\spatialaudioresourcemanager\\WorkFifo.h",
             v3);
  }
  SetThreadpoolThreadMaximum(*(PTP_POOL *)pv, 1u);
  *((_QWORD *)pv + 4) = *(_QWORD *)pv;
  ThreadpoolTimer = CreateThreadpoolTimer(CWorkFifo::TimerCallback, pv, (PTP_CALLBACK_ENVIRON)(pv + 24));
  *((_QWORD *)pv + 1) = ThreadpoolTimer;
  if ( !ThreadpoolTimer )
  {
    v4 = 230;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"avcore\\audiocore\\server\\audiosrv\\spatialaudioresourcemanager\\WorkFifo.h",
             v3);
  }
  ThreadpoolWork = CreateThreadpoolWork(CWorkFifo::WorkCallback, pv, (PTP_CALLBACK_ENVIRON)(pv + 24));
  v8 = *((_QWORD *)pv + 1) == 0;
  *((_QWORD *)pv + 2) = ThreadpoolWork;
  if ( v8 )
  {
    v4 = 233;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"avcore\\audiocore\\server\\audiosrv\\spatialaudioresourcemanager\\WorkFifo.h",
             v3);
  }
  return 0;
}

```

## disassembly

```asm
0x18012fbd8  mov     [rsp+arg_0], rbx
0x18012fbdd  push    rdi
0x18012fbde  sub     rsp, 20h
0x18012fbe2  mov     rbx, rcx
0x18012fbe5  xor     ecx, ecx; reserved
0x18012fbe7  call    cs:__imp_CreateThreadpool
0x18012fbed  mov     [rbx], rax
0x18012fbf0  test    rax, rax
0x18012fbf3  jnz     short loc_18012FC0D
0x18012fbf5  mov     edx, 0DCh; void *
0x18012fbfa  mov     rcx, [rsp+28h]; this
0x18012fbff  lea     r8, aAvcoreAudiocor_68; "avcore\\audiocore\\server\\audiosrv\\sp"...
0x18012fc06  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18012fc0b  jmp     short loc_18012FC89
0x18012fc0d  mov     edi, 1
0x18012fc12  mov     rcx, rax; ptpp
0x18012fc15  mov     edx, edi; cthrdMic
0x18012fc17  call    cs:__imp_SetThreadpoolThreadMinimum
0x18012fc1d  cmp     eax, edi
0x18012fc1f  jz      short loc_18012FC28
0x18012fc21  mov     edx, 0DFh
0x18012fc26  jmp     short loc_18012FBFA
0x18012fc28  mov     rcx, [rbx]; ptpp
0x18012fc2b  mov     edx, edi; cthrdMost
0x18012fc2d  call    cs:__imp_SetThreadpoolThreadMaximum
0x18012fc33  mov     rax, [rbx]
0x18012fc36  lea     r8, [rbx+18h]; pcbe
0x18012fc3a  mov     rdx, rbx; pv
0x18012fc3d  mov     [rbx+20h], rax
0x18012fc41  lea     rcx, ?TimerCallback@CWorkFifo@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18012fc48  call    cs:__imp_CreateThreadpoolTimer
0x18012fc4e  mov     [rbx+8], rax
0x18012fc52  test    rax, rax
0x18012fc55  jnz     short loc_18012FC5E
0x18012fc57  mov     edx, 0E6h
0x18012fc5c  jmp     short loc_18012FBFA
0x18012fc5e  lea     r8, [rbx+18h]; pcbe
0x18012fc62  mov     rdx, rbx; pv
0x18012fc65  lea     rcx, ?WorkCallback@CWorkFifo@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18012fc6c  call    cs:__imp_CreateThreadpoolWork
0x18012fc72  cmp     qword ptr [rbx+8], 0
0x18012fc77  mov     [rbx+10h], rax
0x18012fc7b  jnz     short loc_18012FC87
0x18012fc7d  mov     edx, 0E9h
0x18012fc82  jmp     loc_18012FBFA
0x18012fc87  xor     eax, eax
0x18012fc89  mov     rbx, [rsp+28h+arg_0]
0x18012fc8e  add     rsp, 20h
0x18012fc92  pop     rdi
0x18012fc93  retn
```
