# StateMachine<KeyMachine,KeyState>::PumpEvents(void)

- ea: `0x18003cae8`
- end: `0x18003cc7f`
- name: `?PumpEvents@?$StateMachine@VKeyMachine@@VKeyState@@@@AEAAXXZ`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003cab0`

## callees

- `0x180013b50`
- `0x180014170`
- `0x18001bcb8`
- `0x18003cae8`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003caff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cbff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003caff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cbff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cb79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cc5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cb79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cc5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003cb55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003cb55`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003cc78`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003cc78`

## string_xrefs

- `0x18003cb13`: `This had better be the only queue thread`
- `0x18003cb1f`: `_queueThread == 0`

## pseudocode

```c
void __fastcall StateMachine<KeyMachine,KeyState>::PumpEvents(__int64 a1)
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
      "StateMachine<class KeyMachine,class KeyState>::PumpEvents",
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
      JUMPOUT(0x18003CC7ELL);
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
0x18003cae8  push    rbx
0x18003caea  push    rbp
0x18003caeb  push    rsi
0x18003caec  push    rdi
0x18003caed  push    r14
0x18003caef  push    r15
0x18003caf1  sub     rsp, 58h
0x18003caf5  mov     rsi, rcx
0x18003caf8  lea     rbp, [rcx+38h]
0x18003cafc  mov     rcx, rbp; lpCriticalSection
0x18003caff  call    cs:__imp_EnterCriticalSection
0x18003cb05  mov     [rsp+88h+arg_0], rbp
0x18003cb0d  cmp     dword ptr [rsi+60h], 0
0x18003cb11  jz      short loc_18003CB55
0x18003cb13  lea     rax, aThisHadBetterB; "This had better be the only queue threa"...
0x18003cb1a  mov     [rsp+88h+var_58], rax
0x18003cb1f  lea     rax, aQueuethread0; "_queueThread == 0"
0x18003cb26  mov     [rsp+88h+var_60], rax
0x18003cb2b  lea     rax, aAssertSS; "Assert (%s): %s"
0x18003cb32  mov     [rsp+88h+Format], rax; Format
0x18003cb37  lea     r9, aStatemachineCl; "StateMachine<class KeyMachine,class Key"...
0x18003cb3e  mov     r8d, 0A2h; unsigned int
0x18003cb44  lea     rdx, aOnecoreuapEndu_2; "onecoreuap\\enduser\\winstore\\licensem"...
0x18003cb4b  mov     ecx, 1; unsigned int
0x18003cb50  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18003cb55  call    cs:__imp_GetCurrentThreadId
0x18003cb5b  mov     [rsi+60h], eax
0x18003cb5e  mov     rcx, [rsi+20h]
0x18003cb62  dec     rcx
0x18003cb65  and     rcx, [rsi+28h]
0x18003cb69  mov     rax, [rsi+18h]
0x18003cb6d  mov     r14, [rax+rcx*8]
0x18003cb71  test    rbp, rbp
0x18003cb74  jz      short loc_18003CB7F
0x18003cb76  mov     rcx, rbp; lpCriticalSection
0x18003cb79  call    cs:__imp_LeaveCriticalSection
0x18003cb7f  test    r14, r14
0x18003cb82  jz      loc_18003CC6B
0x18003cb88  mov     rax, rsi
0x18003cb8b  lea     rcx, [rsi-20h]
0x18003cb8f  neg     rax
0x18003cb92  sbb     r15, r15
0x18003cb95  and     r15, rcx
0x18003cb98  test    cs:Microsoft_Windows_StoreEnableBits, 8
0x18003cb9f  jz      short loc_18003CBE0
0x18003cba1  mov     rcx, [rsi+8]
0x18003cba5  mov     rax, [rcx]
0x18003cba8  mov     rax, [rax]
0x18003cbab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbb0  mov     rbx, rax
0x18003cbb3  mov     rdi, [r14]
0x18003cbb6  mov     rcx, [rsi]
0x18003cbb9  mov     rax, [rcx+8]
0x18003cbbd  mov     rcx, rsi
0x18003cbc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbc5  mov     [rsp+88h+var_58], rbx
0x18003cbca  mov     [rsp+88h+var_60], rdi
0x18003cbcf  mov     [rsp+88h+Format], rax
0x18003cbd4  mov     r9d, [rsi+60h]
0x18003cbd8  xor     r8d, r8d
0x18003cbdb  call    McTemplateU0pqzsz_EtwEventWriteTransfer
0x18003cbe0  mov     rcx, [r14+40h]
0x18003cbe4  test    rcx, rcx
0x18003cbe7  jz      loc_18003CC78
0x18003cbed  mov     rax, [rcx]
0x18003cbf0  mov     rdx, r15
0x18003cbf3  mov     rax, [rax+10h]
0x18003cbf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbfc  mov     rcx, rbp; lpCriticalSection
0x18003cbff  call    cs:__imp_EnterCriticalSection
0x18003cc05  nop
0x18003cc06  mov     rcx, [rsi+20h]
0x18003cc0a  dec     rcx
0x18003cc0d  and     rcx, [rsi+28h]
0x18003cc11  mov     rax, [rsi+18h]
0x18003cc15  mov     rcx, [rax+rcx*8]
0x18003cc19  add     rcx, 8
0x18003cc1d  call    ??1?$_Func_class@XAEAVRootMachine@@@std@@QEAA@XZ; std::_Func_class<void,RootMachine &>::~_Func_class<void,RootMachine &>(void)
0x18003cc22  sub     qword ptr [rsi+30h], 1
0x18003cc27  jnz     short loc_18003CC3D
0x18003cc29  mov     qword ptr [rsi+28h], 0
0x18003cc31  mov     dword ptr [rsi+60h], 0
0x18003cc38  xor     r14d, r14d
0x18003cc3b  jmp     short loc_18003CC54
0x18003cc3d  inc     qword ptr [rsi+28h]
0x18003cc41  mov     rcx, [rsi+20h]
0x18003cc45  dec     rcx
0x18003cc48  and     rcx, [rsi+28h]
0x18003cc4c  mov     rax, [rsi+18h]
0x18003cc50  mov     r14, [rax+rcx*8]
0x18003cc54  test    rbp, rbp
0x18003cc57  jz      short loc_18003CC62
0x18003cc59  mov     rcx, rbp; lpCriticalSection
0x18003cc5c  call    cs:__imp_LeaveCriticalSection
0x18003cc62  test    r14, r14
0x18003cc65  jnz     loc_18003CB98
0x18003cc6b  add     rsp, 58h
0x18003cc6f  pop     r15
0x18003cc71  pop     r14
0x18003cc73  pop     rdi
0x18003cc74  pop     rsi
0x18003cc75  pop     rbp
0x18003cc76  pop     rbx
0x18003cc77  retn
0x18003cc78  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
```
