# ThreadpoolManager::ThreadpoolManagerImpl::RequestThreadpoolWork(std::function<long (void)>)

- ea: `0x18007457c`
- end: `0x1800746bc`
- name: `?RequestThreadpoolWork@ThreadpoolManagerImpl@ThreadpoolManager@@QEAAJV?$function@$$A6AJXZ@std@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007450c`

## callees

- `0x180007670`
- `0x18000d60c`
- `0x18000d62c`
- `0x180010064`
- `0x18003fc80`
- `0x18004c3e4`
- `0x18004c5b0`
- `0x18004ce70`
- `0x180073fa0`
- `0x18007457c`
- `0x1800746f8`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180074654`
- `msvcp_win!_Mtx_unlock` at `0x180074654`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18007466b`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18007466b`

## string_xrefs

- `0x1800745b8`: `onecore\ds\security\ngc\utils\common\lib\threadpoolmanager.cpp`
- `0x18007467a`: `onecore\ds\security\ngc\utils\common\lib\threadpoolmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ThreadpoolManager::ThreadpoolManagerImpl::RequestThreadpoolWork(char *pv, __int64 a2)
{
  unsigned int LastError; // ebx
  struct _Mtx_internal_imp_t *v5; // rbp
  __int64 v6; // r15
  __int64 v7; // r14
  __int64 v8; // rax
  __int64 v9; // rcx
  const char *v10; // r9
  int v12; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( *(_DWORD *)pv )
  {
    v5 = (struct _Mtx_internal_imp_t *)(pv + 8);
    std::_Mutex_base::lock((std::_Mutex_base *)(pv + 8));
    if ( *((_QWORD *)pv + 13) <= (unsigned __int64)(*((_QWORD *)pv + 15) + 1LL) )
      std::deque<std::function<long (void)>>::_Growmap(pv + 88);
    *((_QWORD *)pv + 14) &= *((_QWORD *)pv + 13) - 1LL;
    v6 = *((_QWORD *)pv + 14) + *((_QWORD *)pv + 15);
    v7 = std::deque<std::function<long (void)>>::_Getblock(pv + 88, v6);
    if ( !*(_QWORD *)(*((_QWORD *)pv + 12) + 8 * v7) )
      *(_QWORD *)(*((_QWORD *)pv + 12) + 8 * v7) = std::_Allocate<16,std::_Default_allocate_traits>(0x40u);
    v8 = std::_Deque_val<std::_Deque_simple_types<std::future<NgcIsoPregenPool::PregenKey>>>::_Address_subscript(
           pv + 88,
           v6);
    std::_Default_allocator_traits<std::allocator<std::function<long (void)>>>::construct<std::function<long (void)>,std::function<long (void)>>(
      v9,
      v8,
      a2);
    ++*((_QWORD *)pv + 15);
    _Mtx_unlock(v5);
    if ( TrySubmitThreadpoolCallback(
           ThreadpoolManager::ThreadpoolManagerImpl::WorkItemHandler,
           pv,
           *((PTP_CALLBACK_ENVIRON *)pv + 26)) )
    {
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xA0,
                    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\threadpoolmanager.cpp",
                    v10);
    }
  }
  else
  {
    LastError = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\threadpoolmanager.cpp",
      (const char *)0x8007139FLL,
      v12);
  }
  std::_Func_class<long,>::_Tidy(a2);
  return LastError;
}

```

## disassembly

```asm
0x18007457c  mov     [rsp+arg_10], rbx
0x180074581  push    rbp
0x180074582  push    rsi
0x180074583  push    rdi
0x180074584  push    r14
0x180074586  push    r15
0x180074588  sub     rsp, 40h
0x18007458c  mov     rax, cs:__security_cookie
0x180074593  xor     rax, rsp
0x180074596  mov     [rsp+68h+var_38], rax
0x18007459b  mov     rdi, rdx
0x18007459e  mov     rsi, rcx
0x1800745a1  mov     [rsp+68h+var_40], rdx
0x1800745a6  cmp     dword ptr [rcx], 0
0x1800745a9  jnz     short loc_1800745CE
0x1800745ab  mov     rcx, [rsp+68h]; this
0x1800745b0  mov     ebx, 8007139Fh
0x1800745b5  mov     r9d, ebx; char *
0x1800745b8  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800745bf  mov     edx, 95h; void *
0x1800745c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800745c9  jmp     loc_180074691
0x1800745ce  lea     rbp, [rcx+8]
0x1800745d2  mov     [rsp+68h+var_48], rbp
0x1800745d7  mov     rcx, rbp; this
0x1800745da  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800745df  nop
0x1800745e0  lea     rbx, [rsi+58h]
0x1800745e4  mov     rax, [rbx+20h]
0x1800745e8  inc     rax
0x1800745eb  cmp     [rbx+10h], rax
0x1800745ef  ja      short loc_1800745F9
0x1800745f1  mov     rcx, rbx
0x1800745f4  call    ?_Growmap@?$deque@V?$function@$$A6AJXZ@std@@V?$allocator@V?$function@$$A6AJXZ@std@@@2@@std@@AEAAX_K@Z; std::deque<std::function<long (void)>>::_Growmap(unsigned __int64)
0x1800745f9  mov     rax, [rbx+10h]
0x1800745fd  dec     rax
0x180074600  and     [rbx+18h], rax
0x180074604  mov     r15, [rbx+20h]
0x180074608  add     r15, [rbx+18h]
0x18007460c  mov     rdx, r15
0x18007460f  mov     rcx, rbx
0x180074612  call    ?_Getblock@?$deque@V?$function@$$A6AJXZ@std@@V?$allocator@V?$function@$$A6AJXZ@std@@@2@@std@@AEBA_J_K@Z; std::deque<std::function<long (void)>>::_Getblock(unsigned __int64)
0x180074617  mov     r14, rax
0x18007461a  mov     rcx, [rbx+8]
0x18007461e  cmp     qword ptr [rcx+rax*8], 0
0x180074623  jnz     short loc_180074637
0x180074625  mov     ecx, 40h ; '@'
0x18007462a  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18007462f  mov     rcx, [rbx+8]
0x180074633  mov     [rcx+r14*8], rax
0x180074637  mov     rdx, r15
0x18007463a  mov     rcx, rbx
0x18007463d  call    ?_Address_subscript@?$_Deque_val@U?$_Deque_simple_types@V?$future@UPregenKey@NgcIsoPregenPool@@@std@@@std@@@std@@QEAAPEAV?$future@UPregenKey@NgcIsoPregenPool@@@2@_K@Z; std::_Deque_val<std::_Deque_simple_types<std::future<NgcIsoPregenPool::PregenKey>>>::_Address_subscript(unsigned __int64)
0x180074642  mov     r8, rdi
0x180074645  mov     rdx, rax
0x180074648  call    ??$construct@V?$function@$$A6AJXZ@std@@V12@@?$_Default_allocator_traits@V?$allocator@V?$function@$$A6AJXZ@std@@@std@@@std@@SAXAEAV?$allocator@V?$function@$$A6AJXZ@std@@@1@QEAV?$function@$$A6AJXZ@1@$$QEAV31@@Z; std::_Default_allocator_traits<std::allocator<std::function<long (void)>>>::construct<std::function<long (void)>,std::function<long (void)>>(std::allocator<std::function<long (void)>> &,std::function<long (void)> * const,std::function<long (void)> &&)
0x18007464d  inc     qword ptr [rbx+20h]
0x180074651  mov     rcx, rbp; _Mtx_t
0x180074654  call    cs:__imp__Mtx_unlock
0x18007465a  mov     r8, [rsi+0D0h]; pcbe
0x180074661  mov     rdx, rsi; pv
0x180074664  lea     rcx, ?WorkItemHandler@ThreadpoolManagerImpl@ThreadpoolManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18007466b  call    cs:__imp_TrySubmitThreadpoolCallback
0x180074671  test    eax, eax
0x180074673  jnz     short loc_18007468F
0x180074675  mov     rcx, [rsp+68h]; this
0x18007467a  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180074681  mov     edx, 0A0h; void *
0x180074686  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007468b  mov     ebx, eax
0x18007468d  jmp     short loc_180074691
0x18007468f  xor     ebx, ebx
0x180074691  mov     rcx, rdi
0x180074694  call    ?_Tidy@?$_Func_class@J$$V@std@@IEAAXXZ; std::_Func_class<long,>::_Tidy(void)
0x180074699  mov     eax, ebx
0x18007469b  mov     rcx, [rsp+68h+var_38]
0x1800746a0  xor     rcx, rsp; StackCookie
0x1800746a3  call    __security_check_cookie
0x1800746a8  mov     rbx, [rsp+68h+arg_10]
0x1800746b0  add     rsp, 40h
0x1800746b4  pop     r15
0x1800746b6  pop     r14
0x1800746b8  pop     rdi
0x1800746b9  pop     rsi
0x1800746ba  pop     rbp
0x1800746bb  retn
```
