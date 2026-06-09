# MULTI_WORK_QUEUE::SetTimedWorkItem(MULTI_WORK_DISPATCH *,unsigned __int64,ulong,_TP_TIMER * *)

- ea: `0x1800086b8`
- end: `0x180008793`
- name: `?SetTimedWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAVMULTI_WORK_DISPATCH@@_KKPEAPEAU_TP_TIMER@@@Z`
- size: `219`
- prototype: `int(MULTI_WORK_QUEUE *__hidden this, struct MULTI_WORK_DISPATCH *, unsigned __int64, unsigned int, struct _TP_TIMER **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x1800032f0`

## callees

- `0x180001008`
- `0x180001048`
- `0x1800086b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000872e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000872e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008738`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008720`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008720`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000877a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000877a`

## pseudocode

```c
__int64 __fastcall MULTI_WORK_QUEUE::SetTimedWorkItem(
        MULTI_WORK_QUEUE *this,
        struct MULTI_WORK_DISPATCH *a2,
        struct _FILETIME a3,
        unsigned int a4,
        struct _TP_TIMER **a5)
{
  bool v5; // zf
  __int64 v7; // rbp
  unsigned int v9; // ebx
  _QWORD *v10; // rax
  void *v11; // rdi
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v13; // rsi
  signed int LastError; // eax
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+18h] BYREF

  pftDueTime = a3;
  v5 = *((_DWORD *)this + 3) == 0;
  v7 = a4;
  pftDueTime = 0;
  if ( v5 )
  {
    v10 = operator new(0x18u);
    v11 = v10;
    if ( v10 )
    {
      *v10 = this;
      v10[1] = a2;
      v10[2] = 2;
      ThreadpoolTimer = CreateThreadpoolTimer(
                          MultiWorkQueueTimerCallback,
                          v10,
                          (PTP_CALLBACK_ENVIRON)((char *)this + 16));
      v13 = ThreadpoolTimer;
      if ( ThreadpoolTimer )
      {
        v9 = 0;
        pftDueTime = (struct _FILETIME)(-10000 * v7);
        SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, v7, 0);
        *a5 = v13;
      }
      else
      {
        if ( GetLastError() )
        {
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v9 = -2147467259;
        }
        operator delete(v11);
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024726;
  }
  return v9;
}

```

## disassembly

```asm
0x1800086b8  mov     qword ptr [rsp+pftDueTime.dwLowDateTime], r8
0x1800086bd  push    rbx
0x1800086be  push    rbp
0x1800086bf  push    rsi
0x1800086c0  push    rdi
0x1800086c1  sub     rsp, 28h
0x1800086c5  cmp     dword ptr [rcx+0Ch], 0
0x1800086c9  mov     rsi, rdx
0x1800086cc  mov     ebp, r9d
0x1800086cf  mov     rbx, rcx
0x1800086d2  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0
0x1800086db  jz      short loc_1800086E7
0x1800086dd  mov     ebx, 800700AAh
0x1800086e2  jmp     loc_180008788
0x1800086e7  mov     ecx, 18h; Size
0x1800086ec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800086f1  mov     rdi, rax
0x1800086f4  test    rax, rax
0x1800086f7  jnz     short loc_180008703
0x1800086f9  mov     ebx, 8007000Eh
0x1800086fe  jmp     loc_180008788
0x180008703  lea     r8, [rbx+10h]; pcbe
0x180008707  mov     [rax], rbx
0x18000870a  mov     rdx, rdi; pv
0x18000870d  mov     [rax+8], rsi
0x180008711  lea     rcx, ?MultiWorkQueueTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008718  mov     qword ptr [rax+10h], 2
0x180008720  call    cs:__imp_CreateThreadpoolTimer
0x180008726  mov     rsi, rax
0x180008729  test    rax, rax
0x18000872c  jnz     short loc_18000875E
0x18000872e  call    cs:__imp_GetLastError
0x180008734  test    eax, eax
0x180008736  jz      short loc_18000874F
0x180008738  call    cs:__imp_GetLastError
0x18000873e  mov     ebx, eax
0x180008740  test    eax, eax
0x180008742  jle     short loc_180008754
0x180008744  movzx   ebx, ax
0x180008747  or      ebx, 80070000h
0x18000874d  jmp     short loc_180008754
0x18000874f  mov     ebx, 80004005h
0x180008754  mov     rcx, rdi; Block
0x180008757  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000875c  jmp     short loc_180008788
0x18000875e  imul    rdx, rbp, 0FFFFFFFFFFFFD8F0h
0x180008765  xor     ebx, ebx
0x180008767  xor     r9d, r9d; msWindowLength
0x18000876a  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rdx
0x18000876f  mov     r8d, ebp; msPeriod
0x180008772  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180008777  mov     rcx, rsi; pti
0x18000877a  call    cs:__imp_SetThreadpoolTimer
0x180008780  mov     rcx, [rsp+48h+arg_20]
0x180008785  mov     [rcx], rsi
0x180008788  mov     eax, ebx
0x18000878a  add     rsp, 28h
0x18000878e  pop     rdi
0x18000878f  pop     rsi
0x180008790  pop     rbp
0x180008791  pop     rbx
0x180008792  retn
```
