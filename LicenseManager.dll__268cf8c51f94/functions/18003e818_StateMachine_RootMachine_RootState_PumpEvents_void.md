# StateMachine<RootMachine,RootState>::PumpEvents(void)

- ea: `0x18003e818`
- end: `0x18003e9af`
- name: `?PumpEvents@?$StateMachine@VRootMachine@@VRootState@@@@AEAAXXZ`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003e7e0`

## callees

- `0x180013b50`
- `0x180014170`
- `0x18001bcb8`
- `0x18003e818`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e82f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e92f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e82f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e92f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e8a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e98c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e8a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e98c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e885`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e885`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003e9a8`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003e9a8`

## string_xrefs

- `0x18003e843`: `This had better be the only queue thread`
- `0x18003e84f`: `_queueThread == 0`

## pseudocode

```c
void __fastcall StateMachine<RootMachine,RootState>::PumpEvents(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  __int64 *v3; // r14
  __int64 v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rax
  int v7; // edx
  int v8; // ecx
  __int64 v9; // rcx

  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
  if ( *(_DWORD *)(a1 + 96) )
    LogMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\statemachine.h",
      0xA2u,
      "StateMachine<class RootMachine,class RootState>::PumpEvents",
      (wchar_t *)L"Assert (%s): %s",
      L"_queueThread == 0",
      L"This had better be the only queue thread");
  *(_DWORD *)(a1 + 96) = GetCurrentThreadId();
  v3 = *(__int64 **)(*(_QWORD *)(a1 + 24) + 8 * (*(_QWORD *)(a1 + 40) & (*(_QWORD *)(a1 + 32) - 1LL)));
  if ( v2 )
    LeaveCriticalSection(v2);
  while ( v3 )
  {
    if ( (Microsoft_Windows_StoreEnableBits & 8) != 0 )
    {
      v4 = (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
      v5 = *v3;
      v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      McTemplateU0pqzsz_EtwEventWriteTransfer(v8, v7, 0, *(_DWORD *)(a1 + 96), v6, v5, v4);
    }
    v9 = v3[8];
    if ( !v9 )
    {
      std::_Xbad_function_call();
      JUMPOUT(0x18003E9AELL);
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 16LL))(v9, (a1 - 24) & -(__int64)(a1 != 0));
    EnterCriticalSection(v2);
    std::_Func_class<void,RootMachine &>::~_Func_class<void,RootMachine &>(*(_QWORD *)(*(_QWORD *)(a1 + 24)
                                                                                     + 8
                                                                                     * (*(_QWORD *)(a1 + 40)
                                                                                      & (*(_QWORD *)(a1 + 32) - 1LL))) + 8LL);
    if ( (*(_QWORD *)(a1 + 48))-- == 1 )
    {
      *(_QWORD *)(a1 + 40) = 0;
      *(_DWORD *)(a1 + 96) = 0;
      v3 = 0;
    }
    else
    {
      v3 = *(__int64 **)(*(_QWORD *)(a1 + 24) + 8 * (++*(_QWORD *)(a1 + 40) & (*(_QWORD *)(a1 + 32) - 1LL)));
    }
    if ( v2 )
      LeaveCriticalSection(v2);
  }
}

```

## disassembly

```asm
0x18003e818  push    rbx
0x18003e81a  push    rbp
0x18003e81b  push    rsi
0x18003e81c  push    rdi
0x18003e81d  push    r14
0x18003e81f  push    r15
0x18003e821  sub     rsp, 58h
0x18003e825  mov     rsi, rcx
0x18003e828  lea     rbp, [rcx+38h]
0x18003e82c  mov     rcx, rbp; lpCriticalSection
0x18003e82f  call    cs:__imp_EnterCriticalSection
0x18003e835  mov     [rsp+88h+arg_0], rbp
0x18003e83d  cmp     dword ptr [rsi+60h], 0
0x18003e841  jz      short loc_18003E885
0x18003e843  lea     rax, aThisHadBetterB; "This had better be the only queue threa"...
0x18003e84a  mov     [rsp+88h+var_58], rax
0x18003e84f  lea     rax, aQueuethread0; "_queueThread == 0"
0x18003e856  mov     [rsp+88h+var_60], rax
0x18003e85b  lea     rax, aAssertSS; "Assert (%s): %s"
0x18003e862  mov     [rsp+88h+Format], rax; Format
0x18003e867  lea     r9, aStatemachineCl_2; "StateMachine<class RootMachine,class Ro"...
0x18003e86e  mov     r8d, 0A2h; unsigned int
0x18003e874  lea     rdx, aOnecoreuapEndu_2; "onecoreuap\\enduser\\winstore\\licensem"...
0x18003e87b  mov     ecx, 1; unsigned int
0x18003e880  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18003e885  call    cs:__imp_GetCurrentThreadId
0x18003e88b  mov     [rsi+60h], eax
0x18003e88e  mov     rcx, [rsi+20h]
0x18003e892  dec     rcx
0x18003e895  and     rcx, [rsi+28h]
0x18003e899  mov     rax, [rsi+18h]
0x18003e89d  mov     r14, [rax+rcx*8]
0x18003e8a1  test    rbp, rbp
0x18003e8a4  jz      short loc_18003E8AF
0x18003e8a6  mov     rcx, rbp; lpCriticalSection
0x18003e8a9  call    cs:__imp_LeaveCriticalSection
0x18003e8af  test    r14, r14
0x18003e8b2  jz      loc_18003E99B
0x18003e8b8  mov     rax, rsi
0x18003e8bb  lea     rcx, [rsi-18h]
0x18003e8bf  neg     rax
0x18003e8c2  sbb     r15, r15
0x18003e8c5  and     r15, rcx
0x18003e8c8  test    cs:Microsoft_Windows_StoreEnableBits, 8
0x18003e8cf  jz      short loc_18003E910
0x18003e8d1  mov     rcx, [rsi+8]
0x18003e8d5  mov     rax, [rcx]
0x18003e8d8  mov     rax, [rax]
0x18003e8db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e8e0  mov     rbx, rax
0x18003e8e3  mov     rdi, [r14]
0x18003e8e6  mov     rcx, [rsi]
0x18003e8e9  mov     rax, [rcx+8]
0x18003e8ed  mov     rcx, rsi
0x18003e8f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e8f5  mov     [rsp+88h+var_58], rbx
0x18003e8fa  mov     [rsp+88h+var_60], rdi
0x18003e8ff  mov     [rsp+88h+Format], rax
0x18003e904  mov     r9d, [rsi+60h]
0x18003e908  xor     r8d, r8d
0x18003e90b  call    McTemplateU0pqzsz_EtwEventWriteTransfer
0x18003e910  mov     rcx, [r14+40h]
0x18003e914  test    rcx, rcx
0x18003e917  jz      loc_18003E9A8
0x18003e91d  mov     rax, [rcx]
0x18003e920  mov     rdx, r15
0x18003e923  mov     rax, [rax+10h]
0x18003e927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e92c  mov     rcx, rbp; lpCriticalSection
0x18003e92f  call    cs:__imp_EnterCriticalSection
0x18003e935  nop
0x18003e936  mov     rcx, [rsi+20h]
0x18003e93a  dec     rcx
0x18003e93d  and     rcx, [rsi+28h]
0x18003e941  mov     rax, [rsi+18h]
0x18003e945  mov     rcx, [rax+rcx*8]
0x18003e949  add     rcx, 8
0x18003e94d  call    ??1?$_Func_class@XAEAVRootMachine@@@std@@QEAA@XZ; std::_Func_class<void,RootMachine &>::~_Func_class<void,RootMachine &>(void)
0x18003e952  sub     qword ptr [rsi+30h], 1
0x18003e957  jnz     short loc_18003E96D
0x18003e959  mov     qword ptr [rsi+28h], 0
0x18003e961  mov     dword ptr [rsi+60h], 0
0x18003e968  xor     r14d, r14d
0x18003e96b  jmp     short loc_18003E984
0x18003e96d  inc     qword ptr [rsi+28h]
0x18003e971  mov     rcx, [rsi+20h]
0x18003e975  dec     rcx
0x18003e978  and     rcx, [rsi+28h]
0x18003e97c  mov     rax, [rsi+18h]
0x18003e980  mov     r14, [rax+rcx*8]
0x18003e984  test    rbp, rbp
0x18003e987  jz      short loc_18003E992
0x18003e989  mov     rcx, rbp; lpCriticalSection
0x18003e98c  call    cs:__imp_LeaveCriticalSection
0x18003e992  test    r14, r14
0x18003e995  jnz     loc_18003E8C8
0x18003e99b  add     rsp, 58h
0x18003e99f  pop     r15
0x18003e9a1  pop     r14
0x18003e9a3  pop     rdi
0x18003e9a4  pop     rsi
0x18003e9a5  pop     rbp
0x18003e9a6  pop     rbx
0x18003e9a7  retn
0x18003e9a8  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
```
