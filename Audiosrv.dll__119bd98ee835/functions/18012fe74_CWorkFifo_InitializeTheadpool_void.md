# CWorkFifo::InitializeTheadpool(void)

- ea: `0x18012fe74`
- end: `0x18012ff30`
- name: `?InitializeTheadpool@CWorkFifo@@AEAAJXZ`
- size: `188`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18012fd9c`

## callees

- `0x1800b4c88`
- `0x18012fe74`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18012fe83`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18012fe83`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18012ff08`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18012ff08`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18012feb3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18012feb3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18012fee4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18012fee4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18012fec9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18012fec9`

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
0x18012fe74  mov     [rsp+arg_0], rbx
0x18012fe79  push    rdi
0x18012fe7a  sub     rsp, 20h
0x18012fe7e  mov     rbx, rcx
0x18012fe81  xor     ecx, ecx; reserved
0x18012fe83  call    cs:__imp_CreateThreadpool
0x18012fe89  mov     [rbx], rax
0x18012fe8c  test    rax, rax
0x18012fe8f  jnz     short loc_18012FEA9
0x18012fe91  mov     edx, 0DCh; void *
0x18012fe96  mov     rcx, [rsp+28h]; this
0x18012fe9b  lea     r8, aAvcoreAudiocor_69; "avcore\\audiocore\\server\\audiosrv\\sp"...
0x18012fea2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18012fea7  jmp     short loc_18012FF25
0x18012fea9  mov     edi, 1
0x18012feae  mov     rcx, rax; ptpp
0x18012feb1  mov     edx, edi; cthrdMic
0x18012feb3  call    cs:__imp_SetThreadpoolThreadMinimum
0x18012feb9  cmp     eax, edi
0x18012febb  jz      short loc_18012FEC4
0x18012febd  mov     edx, 0DFh
0x18012fec2  jmp     short loc_18012FE96
0x18012fec4  mov     rcx, [rbx]; ptpp
0x18012fec7  mov     edx, edi; cthrdMost
0x18012fec9  call    cs:__imp_SetThreadpoolThreadMaximum
0x18012fecf  mov     rax, [rbx]
0x18012fed2  lea     r8, [rbx+18h]; pcbe
0x18012fed6  mov     rdx, rbx; pv
0x18012fed9  mov     [rbx+20h], rax
0x18012fedd  lea     rcx, ?TimerCallback@CWorkFifo@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18012fee4  call    cs:__imp_CreateThreadpoolTimer
0x18012feea  mov     [rbx+8], rax
0x18012feee  test    rax, rax
0x18012fef1  jnz     short loc_18012FEFA
0x18012fef3  mov     edx, 0E6h
0x18012fef8  jmp     short loc_18012FE96
0x18012fefa  lea     r8, [rbx+18h]; pcbe
0x18012fefe  mov     rdx, rbx; pv
0x18012ff01  lea     rcx, ?WorkCallback@CWorkFifo@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18012ff08  call    cs:__imp_CreateThreadpoolWork
0x18012ff0e  cmp     qword ptr [rbx+8], 0
0x18012ff13  mov     [rbx+10h], rax
0x18012ff17  jnz     short loc_18012FF23
0x18012ff19  mov     edx, 0E9h
0x18012ff1e  jmp     loc_18012FE96
0x18012ff23  xor     eax, eax
0x18012ff25  mov     rbx, [rsp+28h+arg_0]
0x18012ff2a  add     rsp, 20h
0x18012ff2e  pop     rdi
0x18012ff2f  retn
```
