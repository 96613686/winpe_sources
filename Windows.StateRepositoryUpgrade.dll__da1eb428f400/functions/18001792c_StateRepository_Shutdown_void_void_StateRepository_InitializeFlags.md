# StateRepository::Shutdown(void (*)(void),StateRepository::InitializeFlags)

- ea: `0x18001792c`
- end: `0x180017a4a`
- name: `?Shutdown@StateRepository@@YAJP6AXXZW4InitializeFlags@1@@Z`
- size: `286`
- prototype: `int __high(void (__high *)(void), enum StateRepository::InitializeFlags)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000b8e8`

## callees

- `0x18000c3bc`
- `0x18001704c`
- `0x18001792c`
- `0x180017f54`
- `0x180024eec`
- `0x180028408`
- `0x18002974c`
- `0x18002f010`

## string_xrefs

- `0x180017969`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x18001799b`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x1800179d2`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x180017a08`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Shutdown(void (*a1)(void), char a2)
{
  int v2; // ebx
  int v5; // eax
  int v6; // edi
  int v7; // eax
  int v8; // edi
  int v9; // edi
  int v10; // eax
  int v11; // ebp
  unsigned int v12; // esi
  __int64 v13; // rcx
  int v14; // eax
  int v15; // edi
  int v17; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = 0;
  if ( _InterlockedExchangeAdd(&dword_18004BDEC, 0xFFFFFFFF) == 1 )
  {
    v5 = StateRepository::DatabaseCacheSingleton::Shutdown();
    v6 = v5;
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x134,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
        (const char *)(unsigned int)v5,
        v17);
    qword_18004BDF0 = 0;
    if ( v6 < 0 )
      v2 = v6;
    v7 = StateRepository::ProcessShutdown(a2);
    v8 = v7;
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x138,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
        (const char *)(unsigned int)v7,
        v17);
    if ( v2 >= 0 )
      v2 = v8;
    v9 = a2 & 2;
    v10 = StateRepository::Logging::Shutdown(v9 != 0 ? 2 : 0);
    v11 = v10;
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x13A,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
        (const char *)(unsigned int)v10,
        v17);
    if ( v2 >= 0 )
      v2 = v11;
    v12 = a2 & 1;
    v13 = v12 | 2;
    if ( !v9 )
      v13 = v12;
    v14 = StateRepository::Globals::Shutdown(v13);
    v15 = v14;
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x13C,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
        (const char *)(unsigned int)v14,
        v17);
    if ( v2 >= 0 )
      v2 = v15;
    a1();
    McGenEventUnregister_EventUnregister(&STATEREPOSITORY_ETW_CONTROL_GUID_Context);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001792c  mov     [rsp+arg_0], rbx
0x180017931  mov     [rsp+arg_8], rbp
0x180017936  push    rsi
0x180017937  push    rdi
0x180017938  push    r14; int
0x18001793a  sub     rsp, 20h
0x18001793e  xor     ebx, ebx
0x180017940  mov     esi, edx
0x180017942  or      eax, 0FFFFFFFFh
0x180017945  mov     r14, rcx
0x180017948  lock xadd cs:dword_18004BDEC, eax
0x180017950  cmp     eax, 1
0x180017953  jnz     loc_180017A35
0x180017959  call    ?Shutdown@DatabaseCacheSingleton@StateRepository@@SAJXZ; StateRepository::DatabaseCacheSingleton::Shutdown(void)
0x18001795e  mov     edi, eax
0x180017960  test    eax, eax
0x180017962  jns     short loc_18001797D
0x180017964  mov     rcx, [rsp+38h]; this
0x180017969  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\staterepositor"...
0x180017970  mov     r9d, eax; char *
0x180017973  mov     edx, 134h; void *
0x180017978  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001797d  mov     cs:qword_18004BDF0, rbx
0x180017984  test    edi, edi
0x180017986  mov     ecx, esi
0x180017988  cmovs   ebx, edi
0x18001798b  call    StateRepository__ProcessShutdown
0x180017990  mov     edi, eax
0x180017992  test    eax, eax
0x180017994  jns     short loc_1800179AF
0x180017996  mov     rcx, [rsp+38h]; this
0x18001799b  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\staterepositor"...
0x1800179a2  mov     r9d, eax; char *
0x1800179a5  mov     edx, 138h; void *
0x1800179aa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800179af  test    ebx, ebx
0x1800179b1  cmovns  ebx, edi
0x1800179b4  mov     edi, esi
0x1800179b6  and     edi, 2
0x1800179b9  mov     eax, edi
0x1800179bb  neg     eax
0x1800179bd  sbb     ecx, ecx
0x1800179bf  and     ecx, 2
0x1800179c2  call    ?Shutdown@Logging@StateRepository@@YAJW4InitializeFlags@12@@Z; StateRepository::Logging::Shutdown(StateRepository::Logging::InitializeFlags)
0x1800179c7  mov     ebp, eax
0x1800179c9  test    eax, eax
0x1800179cb  jns     short loc_1800179E6
0x1800179cd  mov     rcx, [rsp+38h]; this
0x1800179d2  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\staterepositor"...
0x1800179d9  mov     r9d, eax; char *
0x1800179dc  mov     edx, 13Ah; void *
0x1800179e1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800179e6  test    ebx, ebx
0x1800179e8  cmovns  ebx, ebp
0x1800179eb  and     esi, 1
0x1800179ee  mov     ecx, esi
0x1800179f0  or      ecx, 2
0x1800179f3  test    edi, edi
0x1800179f5  cmovz   ecx, esi
0x1800179f8  call    ?Shutdown@Globals@StateRepository@@YAJW4Flags@12@@Z; StateRepository::Globals::Shutdown(StateRepository::Globals::Flags)
0x1800179fd  mov     edi, eax
0x1800179ff  test    eax, eax
0x180017a01  jns     short loc_180017A1C
0x180017a03  mov     rcx, [rsp+38h]; this
0x180017a08  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\staterepositor"...
0x180017a0f  mov     r9d, eax; char *
0x180017a12  mov     edx, 13Ch; void *
0x180017a17  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017a1c  test    ebx, ebx
0x180017a1e  mov     rax, r14
0x180017a21  cmovns  ebx, edi
0x180017a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a29  lea     rcx, STATEREPOSITORY_ETW_CONTROL_GUID_Context
0x180017a30  call    McGenEventUnregister_EventUnregister
0x180017a35  mov     rbp, [rsp+38h+arg_8]
0x180017a3a  mov     eax, ebx
0x180017a3c  mov     rbx, [rsp+38h+arg_0]
0x180017a41  add     rsp, 20h
0x180017a45  pop     r14
0x180017a47  pop     rdi
0x180017a48  pop     rsi
0x180017a49  retn
```
