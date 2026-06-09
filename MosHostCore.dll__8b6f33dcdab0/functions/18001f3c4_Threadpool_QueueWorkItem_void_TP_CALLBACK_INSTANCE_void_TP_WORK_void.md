# Threadpool::QueueWorkItem(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)

- ea: `0x18001f3c4`
- end: `0x18001f401`
- name: `?QueueWorkItem@Threadpool@@AEAAXP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z1@Z`
- size: `61`
- prototype: `void __fastcall(PTP_CALLBACK_ENVIRON pcbe, PTP_WORK_CALLBACK pfnwk, PVOID pv)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180011390`
- `0x180011510`
- `0x18001189c`
- `0x18001ab98`
- `0x18001b3a0`
- `0x18001cc50`

## callees

- `0x18001f3c4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001f3fa`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001f3ec`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001f3ec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001f3d9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001f3d9`

## pseudocode

```c
void __fastcall Threadpool::QueueWorkItem(PTP_CALLBACK_ENVIRON pcbe, PTP_WORK_CALLBACK pfnwk, PVOID pv)
{
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v4; // rbx

  ThreadpoolWork = CreateThreadpoolWork(pfnwk, pv, pcbe);
  v4 = ThreadpoolWork;
  if ( !ThreadpoolWork )
    __int2c();
  SubmitThreadpoolWork(ThreadpoolWork);
  CloseThreadpoolWork(v4);
}

```

## disassembly

```asm
0x18001f3c4  push    rbx
0x18001f3c6  sub     rsp, 20h
0x18001f3ca  mov     rax, r8
0x18001f3cd  mov     r9, rdx
0x18001f3d0  mov     r8, rcx; pcbe
0x18001f3d3  mov     rdx, rax; pv
0x18001f3d6  mov     rcx, r9; pfnwk
0x18001f3d9  call    cs:__imp_CreateThreadpoolWork
0x18001f3df  mov     rbx, rax
0x18001f3e2  test    rax, rax
0x18001f3e5  jnz     short loc_18001F3E9
0x18001f3e7  int     2Ch; Windows NT - assertion failure
0x18001f3e9  mov     rcx, rbx; pwk
0x18001f3ec  call    cs:__imp_SubmitThreadpoolWork
0x18001f3f2  mov     rcx, rbx
0x18001f3f5  add     rsp, 20h
0x18001f3f9  pop     rbx
0x18001f3fa  jmp     cs:__imp_CloseThreadpoolWork
```
