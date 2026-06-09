# CScheduleMgr::BaseBrokerCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void * const,ulong)

- ea: `0x1800186f0`
- end: `0x1800187e2`
- name: `?BaseBrokerCallback@CScheduleMgr@@SAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXQEAXK@Z`
- size: `242`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, ULONG, struct _WNF_TYPE_ID *, struct _WNF_STATE_NAME, void *const Src, size_t Size)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180010094`
- `0x180010208`
- `0x180010276`
- `0x1800186f0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800187ce`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800187d7`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800187ce`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800187d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800187ae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800187ae`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180018794`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180018794`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800187a5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800187a5`

## pseudocode

```c
__int64 __fastcall CScheduleMgr::BaseBrokerCallback(
        struct _WNF_STATE_NAME a1,
        ULONG a2,
        struct _WNF_TYPE_ID *a3,
        struct _WNF_STATE_NAME a4,
        void *const Src,
        size_t Size)
{
  struct _WNF_STATE_NAME *v9; // rax
  struct _WNF_STATE_NAME *v10; // rdi
  void *v12; // rax
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v14; // rbx
  void *v15; // rcx

  if ( !a2 || !*(_QWORD *)&a4 )
    return 0;
  v9 = (struct _WNF_STATE_NAME *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( !v9 )
    return 3221225473LL;
  *v9 = a1;
  v9[3] = 0;
  v9[1].Data[0] = a2;
  v9[2] = a4;
  v9[4].Data[0] = Size;
  if ( Src && (_DWORD)Size )
  {
    v12 = operator new[]((unsigned int)Size, (const struct std::nothrow_t *)&std::nothrow);
    v10[3] = (struct _WNF_STATE_NAME)v12;
    if ( !v12 )
    {
LABEL_12:
      if ( v10[4].Data[0] )
      {
        v15 = (void *)v10[3];
        if ( v15 )
          operator delete(v15);
      }
      operator delete(v10);
      return 3221225473LL;
    }
    memcpy_0(v12, Src, (unsigned int)Size);
  }
  ThreadpoolWork = CreateThreadpoolWork(BaseBrokerCallbackWorker, v10, &ThreadpoolCallBackEnvironment);
  v14 = ThreadpoolWork;
  if ( !ThreadpoolWork )
    goto LABEL_12;
  SubmitThreadpoolWork(ThreadpoolWork);
  CloseThreadpoolWork(v14);
  return 0;
}

```

## disassembly

```asm
0x1800186f0  push    rbx
0x1800186f2  push    rbp
0x1800186f3  push    rsi
0x1800186f4  push    rdi
0x1800186f5  sub     rsp, 28h
0x1800186f9  mov     rsi, r9
0x1800186fc  mov     ebp, edx
0x1800186fe  mov     rbx, rcx
0x180018701  test    edx, edx
0x180018703  jz      loc_1800187B4
0x180018709  test    r9, r9
0x18001870c  jz      loc_1800187B4
0x180018712  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018719  mov     ecx, 28h ; '('; unsigned __int64
0x18001871e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180018723  mov     rdi, rax
0x180018726  test    rax, rax
0x180018729  jnz     short loc_180018735
0x18001872b  mov     eax, 0C0000001h
0x180018730  jmp     loc_1800187B6
0x180018735  mov     [rax], rbx
0x180018738  mov     rbx, [rsp+48h+Src]
0x18001873d  mov     qword ptr [rax+18h], 0
0x180018745  mov     [rax+8], ebp
0x180018748  mov     [rax+10h], rsi
0x18001874c  mov     eax, dword ptr [rsp+48h+Size]
0x180018750  mov     [rdi+20h], eax
0x180018753  test    rbx, rbx
0x180018756  jz      short loc_180018783
0x180018758  test    eax, eax
0x18001875a  jz      short loc_180018783
0x18001875c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018763  mov     ecx, eax; unsigned __int64
0x180018765  mov     esi, eax
0x180018767  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001876c  mov     [rdi+18h], rax
0x180018770  test    rax, rax
0x180018773  jz      short loc_1800187BF
0x180018775  mov     r8d, esi; Size
0x180018778  mov     rdx, rbx; Src
0x18001877b  mov     rcx, rax; void *
0x18001877e  call    memcpy_0
0x180018783  lea     r8, ?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18001878a  mov     rdx, rdi; pv
0x18001878d  lea     rcx, ?BaseBrokerCallbackWorker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180018794  call    cs:__imp_CreateThreadpoolWork
0x18001879a  mov     rbx, rax
0x18001879d  test    rax, rax
0x1800187a0  jz      short loc_1800187BF
0x1800187a2  mov     rcx, rax; pwk
0x1800187a5  call    cs:__imp_SubmitThreadpoolWork
0x1800187ab  mov     rcx, rbx; pwk
0x1800187ae  call    cs:__imp_CloseThreadpoolWork
0x1800187b4  xor     eax, eax
0x1800187b6  add     rsp, 28h
0x1800187ba  pop     rdi
0x1800187bb  pop     rsi
0x1800187bc  pop     rbp
0x1800187bd  pop     rbx
0x1800187be  retn
0x1800187bf  cmp     dword ptr [rdi+20h], 0
0x1800187c3  jz      short loc_1800187D4
0x1800187c5  mov     rcx, [rdi+18h]
0x1800187c9  test    rcx, rcx
0x1800187cc  jz      short loc_1800187D4
0x1800187ce  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800187d4  mov     rcx, rdi
0x1800187d7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800187dd  jmp     loc_18001872B
```
