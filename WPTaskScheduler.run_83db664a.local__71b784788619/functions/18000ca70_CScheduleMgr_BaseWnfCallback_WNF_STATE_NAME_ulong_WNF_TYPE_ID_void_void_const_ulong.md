# CScheduleMgr::BaseWnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void * const,ulong)

- ea: `0x18000ca70`
- end: `0x18000cba4`
- name: `?BaseWnfCallback@CScheduleMgr@@SAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXQEAXK@Z`
- size: `308`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, void *const Src, size_t Size)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x18000ca70`
- `0x18000e9c8`
- `0x180010094`
- `0x180010208`
- `0x180010276`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000cb9c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cb9c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000cb93`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000cb93`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000cb3b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000cb3b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000cb21`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000cb21`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000cb32`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000cb32`

## pseudocode

```c
__int64 __fastcall CScheduleMgr::BaseWnfCallback(
        struct _WNF_STATE_NAME a1,
        ULONG a2,
        struct _WNF_TYPE_ID *a3,
        struct _WNF_STATE_NAME a4,
        void *const Src,
        size_t Size)
{
  struct _WNF_STATE_NAME *v9; // rax
  struct _WNF_STATE_NAME *v10; // rdi
  void *v11; // rax
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v13; // rbx
  void *v15; // rcx

  if ( (byte_180030D03 & 2) != 0 )
    McTemplateU0qqq_EventWriteTransfer(a1.Data[0], (unsigned int)WNFEvent, a1.Data[0], a1.Data[1], a2);
  if ( !a2 )
    return 0;
  v9 = (struct _WNF_STATE_NAME *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( v9 )
  {
    *v9 = a1;
    v9[3] = 0;
    v9[1].Data[0] = a2;
    v9[2] = a4;
    v9[4].Data[0] = Size;
    if ( Src )
    {
      if ( (_DWORD)Size )
      {
        v11 = operator new[]((unsigned int)Size, (const struct std::nothrow_t *)&std::nothrow);
        v10[3] = (struct _WNF_STATE_NAME)v11;
        if ( !v11 )
        {
LABEL_14:
          if ( v10[4].Data[0] )
          {
            v15 = (void *)v10[3];
            if ( v15 )
              operator delete[](v15);
          }
          operator delete(v10);
          return 3221225473LL;
        }
        memcpy_0(v11, Src, (unsigned int)Size);
      }
      else
      {
        v9[3] = (struct _WNF_STATE_NAME)Src;
      }
    }
    ThreadpoolWork = CreateThreadpoolWork(BaseWnfCallbackWorker, v10, &ThreadpoolCallBackEnvironment);
    v13 = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      CloseThreadpoolWork(v13);
      return 0;
    }
    goto LABEL_14;
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x18000ca70  mov     [rsp+arg_8], rbx
0x18000ca75  mov     [rsp+arg_10], rbp
0x18000ca7a  push    rsi
0x18000ca7b  sub     rsp, 30h
0x18000ca7f  test    cs:byte_180030D03, 2
0x18000ca86  mov     rbp, r9
0x18000ca89  mov     esi, edx
0x18000ca8b  mov     rbx, rcx
0x18000ca8e  jnz     loc_18000CB65
0x18000ca94  mov     [rsp+38h+arg_0], rdi
0x18000ca99  test    esi, esi
0x18000ca9b  jz      loc_18000CB41
0x18000caa1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000caa8  mov     ecx, 28h ; '('; unsigned __int64
0x18000caad  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000cab2  mov     rdi, rax
0x18000cab5  test    rax, rax
0x18000cab8  jz      loc_18000CB58
0x18000cabe  mov     [rax], rbx
0x18000cac1  mov     rbx, [rsp+38h+Src]
0x18000cac6  mov     qword ptr [rax+18h], 0
0x18000cace  mov     [rax+8], esi
0x18000cad1  mov     [rax+10h], rbp
0x18000cad5  mov     eax, dword ptr [rsp+38h+Size]
0x18000cad9  mov     [rdi+20h], eax
0x18000cadc  test    rbx, rbx
0x18000cadf  jz      short loc_18000CB10
0x18000cae1  test    eax, eax
0x18000cae3  jz      short loc_18000CB5F
0x18000cae5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000caec  mov     ecx, eax; unsigned __int64
0x18000caee  mov     esi, eax
0x18000caf0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000caf5  mov     [rdi+18h], rax
0x18000caf9  test    rax, rax
0x18000cafc  jz      loc_18000CB84
0x18000cb02  mov     r8d, esi; Size
0x18000cb05  mov     rdx, rbx; Src
0x18000cb08  mov     rcx, rax; void *
0x18000cb0b  call    memcpy_0
0x18000cb10  lea     r8, ?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18000cb17  mov     rdx, rdi; pv
0x18000cb1a  lea     rcx, ?BaseWnfCallbackWorker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000cb21  call    cs:__imp_CreateThreadpoolWork
0x18000cb27  mov     rbx, rax
0x18000cb2a  test    rax, rax
0x18000cb2d  jz      short loc_18000CB84
0x18000cb2f  mov     rcx, rax; pwk
0x18000cb32  call    cs:__imp_SubmitThreadpoolWork
0x18000cb38  mov     rcx, rbx; pwk
0x18000cb3b  call    cs:__imp_CloseThreadpoolWork
0x18000cb41  xor     eax, eax
0x18000cb43  mov     rdi, [rsp+38h+arg_0]
0x18000cb48  mov     rbx, [rsp+38h+arg_8]
0x18000cb4d  mov     rbp, [rsp+38h+arg_10]
0x18000cb52  add     rsp, 30h
0x18000cb56  pop     rsi
0x18000cb57  retn
0x18000cb58  mov     eax, 0C0000001h
0x18000cb5d  jmp     short loc_18000CB43
0x18000cb5f  mov     [rdi+18h], rbx
0x18000cb63  jmp     short loc_18000CB10
0x18000cb65  mov     r9, rbx
0x18000cb68  mov     [rsp+38h+var_18], esi
0x18000cb6c  shr     r9, 20h
0x18000cb70  lea     rdx, WNFEvent
0x18000cb77  mov     r8d, ebx
0x18000cb7a  call    McTemplateU0qqq_EventWriteTransfer
0x18000cb7f  jmp     loc_18000CA94
0x18000cb84  cmp     dword ptr [rdi+20h], 0
0x18000cb88  jz      short loc_18000CB99
0x18000cb8a  mov     rcx, [rdi+18h]
0x18000cb8e  test    rcx, rcx
0x18000cb91  jz      short loc_18000CB99
0x18000cb93  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000cb99  mov     rcx, rdi
0x18000cb9c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000cba2  jmp     short loc_18000CB58
```
