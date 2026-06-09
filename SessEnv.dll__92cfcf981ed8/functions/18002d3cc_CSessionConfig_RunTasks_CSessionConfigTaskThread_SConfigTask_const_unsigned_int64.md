# CSessionConfig::RunTasks(CSessionConfigTaskThread * *,SConfigTask const *,unsigned __int64)

- ea: `0x18002d3cc`
- end: `0x18002d7b0`
- name: `?RunTasks@CSessionConfig@@AEAAJPEAPEAVCSessionConfigTaskThread@@PEBUSConfigTask@@_K@Z`
- size: `996`
- prototype: `__int64 __fastcall(CSessionConfig *__hidden this, struct CSessionConfigTaskThread **, const struct SConfigTask *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18002c890`

## callees

- `0x180003f30`
- `0x18001a2a4`
- `0x18001a8d0`
- `0x18002d3cc`
- `0x18002db88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d5e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d67b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d5e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d67b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d671`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d671`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002d5c6`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002d5c6`

## string_xrefs

- `0x18002d508`: `CSessionConfig::s_TaskCanRun`
- `0x18002d427`: `CSessionConfig::RunTasks`
- `0x18002d412`: `new EConfigTaskStatus failed: 0x%x in %s`
- `0x18002d46b`: `new prgTaskIndex failed: 0x%x in %s`
- `0x18002d528`: `starting task %u`
- `0x18002d758`: `Task thread failed to start failed: 0x%x in %s`
- `0x18002d772`: `No tasks to run`
- `0x18002d59b`: `Calling WaitForMultipleObjects, %u tasks running, %u tasks finished, %u tasks remaining\n`
- `0x18002d60a`: `completed task %u`
- `0x18002d6d6`: `task %u requires reboot\n`
- `0x18002d734`: `%u percent complete`

## pseudocode

```c
__int64 __fastcall CSessionConfig::RunTasks(
        CSessionConfig *this,
        struct CSessionConfigTaskThread **a2,
        const struct SConfigTask *a3)
{
  _QWORD *v4; // r14
  _DWORD *v5; // r12
  HANDLE *v6; // r15
  const char *v7; // rdx
  __int64 v8; // r8
  signed int v9; // ebx
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // r13
  unsigned __int64 v12; // rbp
  unsigned __int64 i; // rdx
  struct CSessionConfigTaskThread *v14; // rcx
  unsigned __int64 j; // rsi
  unsigned __int64 k; // rax
  unsigned __int64 v17; // rcx
  int v18; // eax
  unsigned __int64 v19; // rbx
  __int64 v20; // rsi
  signed int LastError; // eax
  __int64 v22; // rax
  struct CSessionConfigTaskThread *v23; // rcx
  int v24; // r9d
  int v25; // eax
  signed int v26; // eax
  int v27; // edx
  __int64 v28; // r8
  unsigned __int64 m; // rcx
  __int64 v30; // rax
  __int64 v34; // [rsp+88h] [rbp+20h]

  v4 = 0;
  v5 = operator new(0xCu, (const struct std::nothrow_t *)std::nothrow);
  if ( !v5 )
  {
    v6 = 0;
    v7 = "new EConfigTaskStatus failed: 0x%x in %s";
    goto LABEL_3;
  }
  v6 = (HANDLE *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v6 )
  {
    v7 = "new prgHandles failed: 0x%x in %s";
    goto LABEL_3;
  }
  v4 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  if ( v4 )
  {
    v10 = 0;
    v9 = 0;
    v11 = 0;
    v34 = 0;
    v12 = 0;
    for ( i = 0; i < 3; ++i )
    {
      v14 = a2[i];
      if ( v14 )
        ++v11;
      v5[i] = v14 == 0 ? 2 : 0;
    }
    while ( 1 )
    {
      if ( v10 >= v11 )
        goto LABEL_51;
      for ( j = 0; j < 3; ++j )
      {
        if ( !v5[j] )
        {
          for ( k = 0; k < (unsigned __int64)*(&off_18005E4F0 + 4 * j + 2); ++k )
          {
            v17 = *((_QWORD *)*(&off_18005E4F0 + 4 * j + 3) + k);
            if ( v17 >= 3 )
            {
              _DbgPrintMessage(
                8,
                "prgDependsOn[idx] is out of bounds failed: 0x%x in %s",
                -2147418113,
                "CSessionConfig::s_TaskCanRun");
              goto LABEL_25;
            }
            if ( v5[v17] != 2 )
              goto LABEL_25;
          }
          _DbgPrintMessage(1, "starting task %u", j);
          v18 = CSessionConfigTaskThread::Start((HANDLE *)a2[j]);
          v9 = v18;
          if ( v18 < 0 )
          {
            v8 = (unsigned int)v18;
            v7 = "Task thread failed to start failed: 0x%x in %s";
            goto LABEL_4;
          }
          v5[j] = 1;
          v6[v12] = (HANDLE)*((_QWORD *)a2[j] + 1);
          v4[v12++] = j;
        }
LABEL_25:
        ;
      }
      if ( v12 - 1 > 2 )
      {
        _DbgPrintMessage(1, "No tasks to run");
        goto LABEL_51;
      }
      _DbgPrintMessage(
        1,
        "Calling WaitForMultipleObjects, %u tasks running, %u tasks finished, %u tasks remaining\n",
        v12,
        v34,
        v11 - v34);
      v19 = WaitForMultipleObjects(v12, v6, 0, 0xFFFFFFFF);
      _DbgPrintMessage(1, "WaitForMultipleObjects returned value %u\n", j);
      v20 = (unsigned int)v19;
      if ( v19 >= v12 )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        if ( v9 < 0 )
        {
          v8 = (unsigned int)v9;
          v7 = "WaitForMultipleObjects returned WAIT_ABANDONED, WAIT_TIMEOUT or WAIT_FAILED failed: 0x%x in %s";
          goto LABEL_4;
        }
      }
      _DbgPrintMessage(1, "completed task %u", v4[v20]);
      v22 = v4[v20];
      v9 = 0;
      v23 = a2[v22];
      v24 = *((_DWORD *)v23 + 8);
      if ( v24 < 0 )
        break;
      v27 = *((_DWORD *)v23 + 12);
      v28 = v34 + 1;
      v5[v22] = 2;
      ++v34;
      if ( !*((_DWORD *)this + 403) && v27 )
      {
        _DbgPrintMessage(1, "task %u requires reboot\n", v4[v20]);
        *((_DWORD *)this + 403) = 1;
LABEL_43:
        v28 = v34;
      }
      for ( m = v20 + 1; m < v12; ++m )
      {
        v6[v20] = v6[m];
        v30 = v4[m];
        v4[v20++] = v30;
      }
      v6[--v12] = 0;
      _DbgPrintMessage(1, "%u percent complete", 99 * v28 / v11);
      v10 = v34;
    }
    v25 = *((_DWORD *)this + 402);
    if ( !v25 || v25 == -2147467260 )
      *((_DWORD *)this + 402) = v24;
    _DbgPrintMessage(1, "%u failed , error: 0x%08X\n", v4[v20], v24);
    if ( !SetEvent(*((HANDLE *)this + 199)) )
    {
      v26 = GetLastError();
      v9 = v26;
      if ( v26 > 0 )
        v9 = (unsigned __int16)v26 | 0x80070000;
      if ( v9 < 0 )
      {
        v8 = (unsigned int)v9;
        v7 = "SetEvent failed: 0x%x in %s";
        goto LABEL_4;
      }
    }
    goto LABEL_43;
  }
  v7 = "new prgTaskIndex failed: 0x%x in %s";
LABEL_3:
  v8 = 2147942414LL;
  v9 = -2147024882;
LABEL_4:
  _DbgPrintMessage(8, v7, v8, "CSessionConfig::RunTasks");
LABEL_51:
  operator delete(v5);
  operator delete(v6);
  operator delete(v4);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002d3cc  mov     rax, rsp
0x18002d3cf  mov     [rax+18h], rbx
0x18002d3d3  mov     [rax+20h], r9
0x18002d3d7  mov     [rax+10h], rdx
0x18002d3db  mov     [rax+8], rcx
0x18002d3df  push    rbp
0x18002d3e0  push    rsi
0x18002d3e1  push    rdi
0x18002d3e2  push    r12
0x18002d3e4  push    r13
0x18002d3e6  push    r14
0x18002d3e8  push    r15
0x18002d3ea  sub     rsp, 30h
0x18002d3ee  mov     rdi, rdx
0x18002d3f1  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002d3f8  xor     r14d, r14d
0x18002d3fb  mov     rdx, rbx; struct std::nothrow_t *
0x18002d3fe  lea     ecx, [r14+0Ch]; unsigned __int64
0x18002d402  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002d407  mov     r12, rax
0x18002d40a  test    rax, rax
0x18002d40d  jnz     short loc_18002D438
0x18002d40f  xor     r15d, r15d
0x18002d412  lea     rdx, aNewEconfigtask; "new EConfigTaskStatus failed: 0x%x in %"...
0x18002d419  mov     r8d, 8007000Eh
0x18002d41f  mov     ecx, 8; int
0x18002d424  mov     ebx, r8d
0x18002d427  lea     r9, aCsessionconfig_6; "CSessionConfig::RunTasks"
0x18002d42e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d433  jmp     loc_18002D77E
0x18002d438  mov     esi, 18h
0x18002d43d  mov     rdx, rbx; struct std::nothrow_t *
0x18002d440  mov     ecx, esi; unsigned __int64
0x18002d442  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002d447  mov     r15, rax
0x18002d44a  test    rax, rax
0x18002d44d  jnz     short loc_18002D458
0x18002d44f  lea     rdx, aNewPrghandlesF; "new prgHandles failed: 0x%x in %s"
0x18002d456  jmp     short loc_18002D419
0x18002d458  mov     rdx, rbx; struct std::nothrow_t *
0x18002d45b  mov     rcx, rsi; unsigned __int64
0x18002d45e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002d463  mov     r14, rax
0x18002d466  test    rax, rax
0x18002d469  jnz     short loc_18002D474
0x18002d46b  lea     rdx, aNewPrgtaskinde; "new prgTaskIndex failed: 0x%x in %s"
0x18002d472  jmp     short loc_18002D419
0x18002d474  xor     r8d, r8d
0x18002d477  xor     ebx, ebx
0x18002d479  xor     r13d, r13d
0x18002d47c  mov     [rsp+68h+arg_18], r8
0x18002d484  xor     ebp, ebp
0x18002d486  xor     edx, edx
0x18002d488  mov     rcx, [rdi+rdx*8]
0x18002d48c  lea     rax, [r13+1]
0x18002d490  test    rcx, rcx
0x18002d493  cmovnz  r13, rax
0x18002d497  neg     rcx
0x18002d49a  sbb     eax, eax
0x18002d49c  not     eax
0x18002d49e  and     eax, 2
0x18002d4a1  mov     [r12+rdx*4], eax
0x18002d4a5  inc     rdx
0x18002d4a8  cmp     rdx, 3
0x18002d4ac  jb      short loc_18002D488
0x18002d4ae  mov     edi, 8
0x18002d4b3  lea     rcx, off_18005E4F0
0x18002d4ba  cmp     r8, r13
0x18002d4bd  jnb     loc_18002D77E
0x18002d4c3  xor     esi, esi
0x18002d4c5  cmp     rsi, 3
0x18002d4c9  jnb     loc_18002D580
0x18002d4cf  cmp     dword ptr [r12+rsi*4], 0
0x18002d4d4  jnz     loc_18002D578
0x18002d4da  mov     rax, rsi
0x18002d4dd  shl     rax, 5
0x18002d4e1  mov     r8, [rax+rcx+18h]
0x18002d4e6  mov     rdx, [rax+rcx+10h]
0x18002d4eb  xor     eax, eax
0x18002d4ed  cmp     rax, rdx
0x18002d4f0  jnb     short loc_18002D525
0x18002d4f2  mov     rcx, [r8+rax*8]
0x18002d4f6  cmp     rcx, 3
0x18002d4fa  jnb     short loc_18002D508
0x18002d4fc  cmp     dword ptr [r12+rcx*4], 2
0x18002d501  jnz     short loc_18002D571
0x18002d503  inc     rax
0x18002d506  jmp     short loc_18002D4ED
0x18002d508  lea     r9, aCsessionconfig_3; "CSessionConfig::s_TaskCanRun"
0x18002d50f  mov     r8d, 8000FFFFh
0x18002d515  lea     rdx, aPrgdependsonId; "prgDependsOn[idx] is out of bounds fail"...
0x18002d51c  mov     ecx, edi; int
0x18002d51e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d523  jmp     short loc_18002D571
0x18002d525  mov     r8, rsi
0x18002d528  lea     rdx, aStartingTaskU; "starting task %u"
0x18002d52f  mov     ecx, 1; int
0x18002d534  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d539  mov     rax, [rsp+68h+arg_8]
0x18002d53e  mov     rcx, [rax+rsi*8]; this
0x18002d542  call    ?Start@CSessionConfigTaskThread@@QEAAJXZ; CSessionConfigTaskThread::Start(void)
0x18002d547  mov     ebx, eax
0x18002d549  test    eax, eax
0x18002d54b  js      loc_18002D755
0x18002d551  mov     rax, [rsp+68h+arg_8]
0x18002d556  mov     dword ptr [r12+rsi*4], 1
0x18002d55e  mov     rcx, [rax+rsi*8]
0x18002d562  mov     rdx, [rcx+8]
0x18002d566  mov     [r15+rbp*8], rdx
0x18002d56a  mov     [r14+rbp*8], rsi
0x18002d56e  inc     rbp
0x18002d571  lea     rcx, off_18005E4F0
0x18002d578  inc     rsi
0x18002d57b  jmp     loc_18002D4C5
0x18002d580  lea     rax, [rbp-1]
0x18002d584  mov     ecx, 1; int
0x18002d589  cmp     rax, 2
0x18002d58d  ja      loc_18002D772
0x18002d593  mov     r9, [rsp+68h+arg_18]
0x18002d59b  lea     rdx, aCallingWaitfor; "Calling WaitForMultipleObjects, %u task"...
0x18002d5a2  mov     rax, r13
0x18002d5a5  mov     r8, rbp
0x18002d5a8  sub     rax, [rsp+68h+arg_18]
0x18002d5b0  mov     [rsp+68h+var_48], rax
0x18002d5b5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d5ba  mov     ecx, ebp; nCount
0x18002d5bc  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18002d5c0  xor     r8d, r8d; bWaitAll
0x18002d5c3  mov     rdx, r15; lpHandles
0x18002d5c6  call    cs:__imp_WaitForMultipleObjects
0x18002d5cc  mov     r8, rsi
0x18002d5cf  lea     rdx, aWaitformultipl_0; "WaitForMultipleObjects returned value %"...
0x18002d5d6  mov     ecx, 1; int
0x18002d5db  mov     ebx, eax
0x18002d5dd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d5e2  mov     esi, ebx
0x18002d5e4  cmp     rbx, rbp
0x18002d5e7  jb      short loc_18002D606
0x18002d5e9  call    cs:__imp_GetLastError
0x18002d5ef  mov     ebx, eax
0x18002d5f1  test    eax, eax
0x18002d5f3  jle     short loc_18002D5FE
0x18002d5f5  movzx   ebx, ax
0x18002d5f8  or      ebx, 80070000h
0x18002d5fe  test    ebx, ebx
0x18002d600  js      loc_18002D766
0x18002d606  mov     r8, [r14+rsi*8]
0x18002d60a  lea     rdx, aCompletedTaskU; "completed task %u"
0x18002d611  mov     ecx, 1; int
0x18002d616  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d61b  mov     rax, [r14+rsi*8]
0x18002d61f  xor     ebx, ebx
0x18002d621  mov     rcx, [rsp+68h+arg_8]
0x18002d626  mov     rcx, [rcx+rax*8]
0x18002d62a  mov     r9d, [rcx+20h]
0x18002d62e  test    r9d, r9d
0x18002d631  jns     short loc_18002D6A3
0x18002d633  mov     rcx, [rsp+68h+arg_0]
0x18002d638  mov     eax, [rcx+648h]
0x18002d63e  test    eax, eax
0x18002d640  jz      short loc_18002D649
0x18002d642  cmp     eax, 80004004h
0x18002d647  jnz     short loc_18002D650
0x18002d649  mov     [rcx+648h], r9d
0x18002d650  mov     r8, [r14+rsi*8]
0x18002d654  lea     rdx, aUFailedError0x; "%u failed , error: 0x%08X\n"
0x18002d65b  mov     ecx, 1; int
0x18002d660  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d665  mov     rax, [rsp+68h+arg_0]
0x18002d66a  mov     rcx, [rax+638h]; hEvent
0x18002d671  call    cs:__imp_SetEvent
0x18002d677  test    eax, eax
0x18002d679  jnz     short loc_18002D6F6
0x18002d67b  call    cs:__imp_GetLastError
0x18002d681  mov     ebx, eax
0x18002d683  test    eax, eax
0x18002d685  jle     short loc_18002D690
0x18002d687  movzx   ebx, ax
0x18002d68a  or      ebx, 80070000h
0x18002d690  test    ebx, ebx
0x18002d692  jns     short loc_18002D6F6
0x18002d694  mov     r8d, ebx
0x18002d697  lea     rdx, aSeteventFailed; "SetEvent failed: 0x%x in %s"
0x18002d69e  jmp     loc_18002D75F
0x18002d6a3  mov     r8, [rsp+68h+arg_18]
0x18002d6ab  mov     edx, [rcx+30h]
0x18002d6ae  inc     r8
0x18002d6b1  mov     dword ptr [r12+rax*4], 2
0x18002d6b9  mov     rax, [rsp+68h+arg_0]
0x18002d6be  mov     [rsp+68h+arg_18], r8
0x18002d6c6  cmp     [rax+64Ch], ebx
0x18002d6cc  jnz     short loc_18002D6FE
0x18002d6ce  test    edx, edx
0x18002d6d0  jz      short loc_18002D6FE
0x18002d6d2  mov     r8, [r14+rsi*8]
0x18002d6d6  lea     rdx, aTaskURequiresR; "task %u requires reboot\n"
0x18002d6dd  mov     ecx, 1; int
0x18002d6e2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d6e7  mov     rax, [rsp+68h+arg_0]
0x18002d6ec  mov     dword ptr [rax+64Ch], 1
0x18002d6f6  mov     r8, [rsp+68h+arg_18]
0x18002d6fe  lea     rcx, [rsi+1]
0x18002d702  jmp     short loc_18002D71A
0x18002d704  mov     rax, [r15+rcx*8]
0x18002d708  mov     [r15+rsi*8], rax
0x18002d70c  mov     rax, [r14+rcx*8]
0x18002d710  inc     rcx
0x18002d713  mov     [r14+rsi*8], rax
0x18002d717  inc     rsi
0x18002d71a  cmp     rcx, rbp
0x18002d71d  jb      short loc_18002D704
0x18002d71f  imul    rax, r8, 63h ; 'c'
0x18002d723  xor     edx, edx
0x18002d725  mov     qword ptr [r15+rbp*8-8], 0
0x18002d72e  div     r13
0x18002d731  dec     rbp
0x18002d734  lea     rdx, aUPercentComple; "%u percent complete"
0x18002d73b  mov     r8, rax
0x18002d73e  mov     ecx, 1; int
0x18002d743  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d748  mov     r8, [rsp+68h+arg_18]
0x18002d750  jmp     loc_18002D4B3
0x18002d755  mov     r8d, eax
0x18002d758  lea     rdx, aTaskThreadFail; "Task thread failed to start failed: 0x%"...
0x18002d75f  mov     ecx, edi
0x18002d761  jmp     loc_18002D427
0x18002d766  mov     r8d, ebx
0x18002d769  lea     rdx, aWaitformultipl; "WaitForMultipleObjects returned WAIT_AB"...
0x18002d770  jmp     short loc_18002D75F
0x18002d772  lea     rdx, aNoTasksToRun; "No tasks to run"
0x18002d779  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d77e  mov     rcx, r12; Block
0x18002d781  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d786  mov     rcx, r15; Block
0x18002d789  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d78e  mov     rcx, r14; Block
0x18002d791  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d796  mov     eax, ebx
0x18002d798  mov     rbx, [rsp+68h+arg_10]
0x18002d7a0  add     rsp, 30h
0x18002d7a4  pop     r15
0x18002d7a6  pop     r14
0x18002d7a8  pop     r13
0x18002d7aa  pop     r12
0x18002d7ac  pop     rdi
0x18002d7ad  pop     rsi
0x18002d7ae  pop     rbp
0x18002d7af  retn
```
