# StateMachine<LeaseMachine,LeaseState>::PumpEvents(void)

- ea: `0x180030a88`
- end: `0x180030c1f`
- name: `?PumpEvents@?$StateMachine@VLeaseMachine@@VLeaseState@@@@AEAAXXZ`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180030a50`

## callees

- `0x180013b50`
- `0x180014170`
- `0x18001bcb8`
- `0x180030a88`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030a9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030b9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030a9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030b9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030b19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030bfc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030b19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030bfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030af5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030af5`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180030c18`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180030c18`

## string_xrefs

- `0x180030ab3`: `This had better be the only queue thread`
- `0x180030abf`: `_queueThread == 0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall StateMachine<LeaseMachine,LeaseState>::PumpEvents(__int64 a1)
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
      "StateMachine<class LeaseMachine,class LeaseState>::PumpEvents",
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
      JUMPOUT(0x180030C1ELL);
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 16LL))(v9, (a1 - 32) & -(__int64)(a1 != 0));
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
0x180030a88  push    rbx
0x180030a8a  push    rbp
0x180030a8b  push    rsi
0x180030a8c  push    rdi
0x180030a8d  push    r14
0x180030a8f  push    r15
0x180030a91  sub     rsp, 58h
0x180030a95  mov     rsi, rcx
0x180030a98  lea     rbp, [rcx+38h]
0x180030a9c  mov     rcx, rbp; lpCriticalSection
0x180030a9f  call    cs:__imp_EnterCriticalSection
0x180030aa5  mov     [rsp+88h+arg_0], rbp
0x180030aad  cmp     dword ptr [rsi+60h], 0
0x180030ab1  jz      short loc_180030AF5
0x180030ab3  lea     rax, aThisHadBetterB; "This had better be the only queue threa"...
0x180030aba  mov     [rsp+88h+var_58], rax
0x180030abf  lea     rax, aQueuethread0; "_queueThread == 0"
0x180030ac6  mov     [rsp+88h+var_60], rax
0x180030acb  lea     rax, aAssertSS; "Assert (%s): %s"
0x180030ad2  mov     [rsp+88h+Format], rax; Format
0x180030ad7  lea     r9, aStatemachineCl_0; "StateMachine<class LeaseMachine,class L"...
0x180030ade  mov     r8d, 0A2h; unsigned int
0x180030ae4  lea     rdx, aOnecoreuapEndu_2; "onecoreuap\\enduser\\winstore\\licensem"...
0x180030aeb  mov     ecx, 1; unsigned int
0x180030af0  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180030af5  call    cs:__imp_GetCurrentThreadId
0x180030afb  mov     [rsi+60h], eax
0x180030afe  mov     rcx, [rsi+20h]
0x180030b02  dec     rcx
0x180030b05  and     rcx, [rsi+28h]
0x180030b09  mov     rax, [rsi+18h]
0x180030b0d  mov     r14, [rax+rcx*8]
0x180030b11  test    rbp, rbp
0x180030b14  jz      short loc_180030B1F
0x180030b16  mov     rcx, rbp; lpCriticalSection
0x180030b19  call    cs:__imp_LeaveCriticalSection
0x180030b1f  test    r14, r14
0x180030b22  jz      loc_180030C0B
0x180030b28  mov     rax, rsi
0x180030b2b  lea     rcx, [rsi-20h]
0x180030b2f  neg     rax
0x180030b32  sbb     r15, r15
0x180030b35  and     r15, rcx
0x180030b38  test    cs:Microsoft_Windows_StoreEnableBits, 8
0x180030b3f  jz      short loc_180030B80
0x180030b41  mov     rcx, [rsi+8]
0x180030b45  mov     rax, [rcx]
0x180030b48  mov     rax, [rax]
0x180030b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b50  mov     rbx, rax
0x180030b53  mov     rdi, [r14]
0x180030b56  mov     rcx, [rsi]
0x180030b59  mov     rax, [rcx+8]
0x180030b5d  mov     rcx, rsi
0x180030b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b65  mov     [rsp+88h+var_58], rbx
0x180030b6a  mov     [rsp+88h+var_60], rdi
0x180030b6f  mov     [rsp+88h+Format], rax
0x180030b74  mov     r9d, [rsi+60h]
0x180030b78  xor     r8d, r8d
0x180030b7b  call    McTemplateU0pqzsz_EtwEventWriteTransfer
0x180030b80  mov     rcx, [r14+40h]
0x180030b84  test    rcx, rcx
0x180030b87  jz      loc_180030C18
0x180030b8d  mov     rax, [rcx]
0x180030b90  mov     rdx, r15
0x180030b93  mov     rax, [rax+10h]
0x180030b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b9c  mov     rcx, rbp; lpCriticalSection
0x180030b9f  call    cs:__imp_EnterCriticalSection
0x180030ba5  nop
0x180030ba6  mov     rcx, [rsi+20h]
0x180030baa  dec     rcx
0x180030bad  and     rcx, [rsi+28h]
0x180030bb1  mov     rax, [rsi+18h]
0x180030bb5  mov     rcx, [rax+rcx*8]
0x180030bb9  add     rcx, 8
0x180030bbd  call    ??1?$_Func_class@XAEAVRootMachine@@@std@@QEAA@XZ; std::_Func_class<void,RootMachine &>::~_Func_class<void,RootMachine &>(void)
0x180030bc2  sub     qword ptr [rsi+30h], 1
0x180030bc7  jnz     short loc_180030BDD
0x180030bc9  mov     qword ptr [rsi+28h], 0
0x180030bd1  mov     dword ptr [rsi+60h], 0
0x180030bd8  xor     r14d, r14d
0x180030bdb  jmp     short loc_180030BF4
0x180030bdd  inc     qword ptr [rsi+28h]
0x180030be1  mov     rcx, [rsi+20h]
0x180030be5  dec     rcx
0x180030be8  and     rcx, [rsi+28h]
0x180030bec  mov     rax, [rsi+18h]
0x180030bf0  mov     r14, [rax+rcx*8]
0x180030bf4  test    rbp, rbp
0x180030bf7  jz      short loc_180030C02
0x180030bf9  mov     rcx, rbp; lpCriticalSection
0x180030bfc  call    cs:__imp_LeaveCriticalSection
0x180030c02  test    r14, r14
0x180030c05  jnz     loc_180030B38
0x180030c0b  add     rsp, 58h
0x180030c0f  pop     r15
0x180030c11  pop     r14
0x180030c13  pop     rdi
0x180030c14  pop     rsi
0x180030c15  pop     rbp
0x180030c16  pop     rbx
0x180030c17  retn
0x180030c18  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
```
