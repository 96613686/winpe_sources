# CScheduleMgr::BaseCentralEventAggregateCallback(void *,_CBROKERED_EVENT_ID,void *,void *,ulong)

- ea: `0x18000d550`
- end: `0x18000d634`
- name: `?BaseCentralEventAggregateCallback@CScheduleMgr@@SAXPEAXU_CBROKERED_EVENT_ID@@00K@Z`
- size: `228`
- prototype: `static void __high(void *, struct _CBROKERED_EVENT_ID, void *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000d550`
- `0x180010094`
- `0x180010208`
- `0x180010276`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000d62c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d62c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000d623`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000d623`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000d5d6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000d5d6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000d5bc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000d5bc`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000d5cd`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000d5cd`

## pseudocode

```c
void __fastcall CScheduleMgr::BaseCentralEventAggregateCallback(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const void *a4,
        unsigned int Size)
{
  _QWORD *v9; // rax
  _QWORD *v10; // rdi
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v12; // rbx
  void *v13; // rax
  void *v14; // rcx

  if ( !a3 )
    return;
  v9 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( !v9 )
    return;
  *v9 = a3;
  v9[1] = a1;
  v9[2] = a2;
  *((_DWORD *)v9 + 8) = Size;
  v9[3] = 0;
  if ( !a4 || !Size )
    goto LABEL_4;
  v13 = operator new[](Size, (const struct std::nothrow_t *)&std::nothrow);
  v10[3] = v13;
  if ( v13 )
  {
    memcpy_0(v13, a4, Size);
LABEL_4:
    ThreadpoolWork = CreateThreadpoolWork(BaseCentralEventAggregateCallbackWorker, v10, &ThreadpoolCallBackEnvironment);
    v12 = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      CloseThreadpoolWork(v12);
      return;
    }
  }
  v14 = (void *)v10[3];
  if ( v14 )
    operator delete[](v14);
  operator delete(v10);
}

```

## disassembly

```asm
0x18000d550  test    r8, r8
0x18000d553  jz      locret_18000D5EA
0x18000d559  push    rbx
0x18000d55a  push    rbp
0x18000d55b  push    rsi
0x18000d55c  push    r14
0x18000d55e  sub     rsp, 28h
0x18000d562  mov     rbx, rdx
0x18000d565  mov     [rsp+48h+arg_0], rdi
0x18000d56a  mov     r14, rcx
0x18000d56d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d574  mov     ecx, 28h ; '('; unsigned __int64
0x18000d579  mov     rbp, r9
0x18000d57c  mov     rsi, r8
0x18000d57f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d584  mov     rdi, rax
0x18000d587  test    rax, rax
0x18000d58a  jz      short loc_18000D5DC
0x18000d58c  mov     [rax], rsi
0x18000d58f  mov     [rax+8], r14
0x18000d593  mov     [rax+10h], rbx
0x18000d597  mov     eax, dword ptr [rsp+48h+Size]
0x18000d59b  mov     [rdi+20h], eax
0x18000d59e  mov     qword ptr [rdi+18h], 0
0x18000d5a6  test    rbp, rbp
0x18000d5a9  jnz     short loc_18000D5EB
0x18000d5ab  lea     r8, ?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18000d5b2  mov     rdx, rdi; pv
0x18000d5b5  lea     rcx, ?BaseCentralEventAggregateCallbackWorker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000d5bc  call    cs:__imp_CreateThreadpoolWork
0x18000d5c2  mov     rbx, rax
0x18000d5c5  test    rax, rax
0x18000d5c8  jz      short loc_18000D61A
0x18000d5ca  mov     rcx, rax; pwk
0x18000d5cd  call    cs:__imp_SubmitThreadpoolWork
0x18000d5d3  mov     rcx, rbx; pwk
0x18000d5d6  call    cs:__imp_CloseThreadpoolWork
0x18000d5dc  mov     rdi, [rsp+48h+arg_0]
0x18000d5e1  add     rsp, 28h
0x18000d5e5  pop     r14
0x18000d5e7  pop     rsi
0x18000d5e8  pop     rbp
0x18000d5e9  pop     rbx
0x18000d5ea  retn
0x18000d5eb  test    eax, eax
0x18000d5ed  jz      short loc_18000D5AB
0x18000d5ef  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d5f6  mov     rcx, rax; unsigned __int64
0x18000d5f9  mov     rbx, rax
0x18000d5fc  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000d601  mov     [rdi+18h], rax
0x18000d605  test    rax, rax
0x18000d608  jz      short loc_18000D61A
0x18000d60a  mov     r8, rbx; Size
0x18000d60d  mov     rdx, rbp; Src
0x18000d610  mov     rcx, rax; void *
0x18000d613  call    memcpy_0
0x18000d618  jmp     short loc_18000D5AB
0x18000d61a  mov     rcx, [rdi+18h]
0x18000d61e  test    rcx, rcx
0x18000d621  jz      short loc_18000D629
0x18000d623  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000d629  mov     rcx, rdi
0x18000d62c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000d632  jmp     short loc_18000D5DC
```
