# StateRepository::Initialize(void (*)(void),_tlgProvider_t const *,ushort const *,void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(void *,char const *),void (*)(void *,char const *,uint),int,long (*)(StateRepository::Partition,ushort * *),ushort const *,ushort const *,ushort const *,StateRepository::InitializeFlags)

- ea: `0x180016dcc`
- end: `0x180016fc6`
- name: `?Initialize@StateRepository@@YAJP6AXXZPEBU_tlgProvider_t@@PEBGP6AXHPEBD@Z4444P6AXPEAX3@ZP6AX53I@ZHP6AJW4Partition@1@PEAPEAG@Z222W4InitializeFlags@1@@Z`
- size: `506`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bb64`

## callees

- `0x18000a3c0`
- `0x18000c3bc`
- `0x180016dcc`
- `0x180016fcc`
- `0x18001704c`
- `0x180017670`
- `0x180017b34`
- `0x180017f28`
- `0x180017f54`
- `0x180023ba8`
- `0x180024eec`
- `0x18002703c`
- `0x180028408`
- `0x1800292e4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180016e41`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180016e41`

## string_xrefs

- `0x180016e0b`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x180016e6c`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x180016ebe`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x180016f22`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`

## pseudocode

```c
int __fastcall StateRepository::Initialize(__int64 a1, const struct _tlgProvider_t *a2)
{
  unsigned int v3; // eax
  unsigned int v5; // eax
  void *v6; // rdx
  unsigned int v7; // r8d
  int v8; // eax
  __int64 v9; // rdx
  unsigned int v10; // edi
  __int64 v11; // rdx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  StateRepository *v15; // rcx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  unsigned int v19; // [rsp+20h] [rbp-58h]
  int v20; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( _InterlockedIncrement(&dword_18004BDEC) == 1 )
  {
    v3 = McGenEventRegister_EventRegister(
           a1,
           a2,
           &STATEREPOSITORY_ETW_CONTROL_GUID_Context,
           &STATEREPOSITORY_ETW_CONTROL_GUID_Context);
    if ( v3 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xBA,
               (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
               (const char *)v3,
               v19);
    v5 = EventSetInformation(
           STATEREPOSITORY_ETW_CONTROL_GUID_Context,
           2,
           &`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits,
           (unsigned __int16)`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits);
    if ( v5 )
      wil::details::in1diag3::_Log_Win32(retaddr, v6, v7, (const char *)v5, v19);
    v8 = StateRepository::Globals::Initialize();
    v10 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBF,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
        (const char *)(unsigned int)v8,
        2);
      McGenEventUnregister_EventUnregister(&STATEREPOSITORY_ETW_CONTROL_GUID_Context);
      v11 = 195;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
        (const char *)v10,
        v20);
      return v10;
    }
    v12 = StateRepository::Logging::Initialize((__int64)a2, v9);
    v10 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xCA,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
        (const char *)(unsigned int)v12,
        2);
      v13 = StateRepository::Globals::Shutdown(2);
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xCD,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
          (const char *)(unsigned int)v13,
          v20);
      McGenEventUnregister_EventUnregister(&STATEREPOSITORY_ETW_CONTROL_GUID_Context);
      v11 = 207;
      goto LABEL_8;
    }
    qword_18004BDF0 = (__int64)a2;
    v14 = StateRepository::DatabaseCacheSingleton::Initialize(a2);
    v10 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE5,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
        (const char *)(unsigned int)v14,
        2);
      qword_18004BDF0 = 0;
      v16 = StateRepository::ProcessShutdown(2);
      if ( v16 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xE9,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
          (const char *)(unsigned int)v16,
          v20);
      v17 = StateRepository::Logging::Shutdown(2);
      if ( v17 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xEA,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
          (const char *)(unsigned int)v17,
          v20);
      v18 = StateRepository::Globals::Shutdown(2);
      if ( v18 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xEB,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
          (const char *)(unsigned int)v18,
          v20);
      McGenEventUnregister_EventUnregister(&STATEREPOSITORY_ETW_CONTROL_GUID_Context);
      v11 = 237;
      goto LABEL_8;
    }
    StateRepository::LoggerInitialized(v15);
  }
  return 0;
}

```

## disassembly

```asm
0x180016dcc  push    rbx
0x180016dce  push    rbp
0x180016dcf  push    rsi
0x180016dd0  push    rdi
0x180016dd1  sub     rsp, 58h
0x180016dd5  mov     rbx, rdx
0x180016dd8  mov     eax, 1
0x180016ddd  lock xadd cs:dword_18004BDEC, eax
0x180016de5  inc     eax
0x180016de7  cmp     eax, 1
0x180016dea  jnz     loc_180016FBB
0x180016df0  lea     rbp, STATEREPOSITORY_ETW_CONTROL_GUID_Context
0x180016df7  mov     r9, rbp
0x180016dfa  mov     r8, rbp
0x180016dfd  call    McGenEventRegister_EventRegister
0x180016e02  test    eax, eax
0x180016e04  jz      short loc_180016E24
0x180016e06  mov     rcx, [rsp+78h]; this
0x180016e0b  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\staterepositor"...
0x180016e12  mov     r9d, eax; char *
0x180016e15  mov     edx, 0BAh; void *
0x180016e1a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180016e1f  jmp     loc_180016FBD
0x180016e24  movzx   r9d, cs:?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x180016e2c  lea     r8, ?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x180016e33  mov     rcx, cs:STATEREPOSITORY_ETW_CONTROL_GUID_Context
0x180016e3a  mov     esi, 2
0x180016e3f  mov     edx, esi
0x180016e41  call    cs:__imp_EventSetInformation
0x180016e47  test    eax, eax
0x180016e49  jz      short loc_180016E58
0x180016e4b  mov     rcx, [rsp+78h]; this
0x180016e50  mov     r9d, eax; char *
0x180016e53  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180016e58  mov     [rsp+78h+var_58], esi; int
0x180016e5c  call    ?Initialize@Globals@StateRepository@@YAJP6AJW4Partition@2@PEAPEAG@ZPEBG33W4Flags@12@@Z; StateRepository::Globals::Initialize(long (*)(StateRepository::Partition,ushort * *),ushort const *,ushort const *,ushort const *,StateRepository::Globals::Flags)
0x180016e61  mov     edi, eax
0x180016e63  test    eax, eax
0x180016e65  jns     short loc_180016EA7
0x180016e67  mov     rcx, [rsp+78h]; this
0x180016e6c  lea     rbx, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\staterepositor"...
0x180016e73  mov     r8, rbx; unsigned int
0x180016e76  mov     r9d, eax; char *
0x180016e79  mov     edx, 0BFh; void *
0x180016e7e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016e83  mov     rcx, rbp
0x180016e86  call    McGenEventUnregister_EventUnregister
0x180016e8b  mov     edx, 0C3h; void *
0x180016e90  mov     rcx, [rsp+78h]; this
0x180016e95  mov     r9d, edi; char *
0x180016e98  mov     r8, rbx; unsigned int
0x180016e9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016ea0  mov     eax, edi
0x180016ea2  jmp     loc_180016FBD
0x180016ea7  mov     rcx, rbx
0x180016eaa  mov     [rsp+78h+var_30], esi
0x180016eae  call    ?Initialize@Logging@StateRepository@@YAJPEBU_tlgProvider_t@@PEBGP6AXHPEBD@Z3333P6AXPEAX2@ZP6AX42I@ZW4InitializeFlags@12@@Z; StateRepository::Logging::Initialize(_tlgProvider_t const *,ushort const *,void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(void *,char const *),void (*)(void *,char const *,uint),StateRepository::Logging::InitializeFlags)
0x180016eb3  mov     edi, eax
0x180016eb5  test    eax, eax
0x180016eb7  jns     short loc_180016F04
0x180016eb9  mov     rcx, [rsp+78h]; this
0x180016ebe  lea     rbx, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\staterepositor"...
0x180016ec5  mov     r8, rbx; unsigned int
0x180016ec8  mov     r9d, eax; char *
0x180016ecb  mov     edx, 0CAh; void *
0x180016ed0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016ed5  mov     ecx, esi
0x180016ed7  call    ?Shutdown@Globals@StateRepository@@YAJW4Flags@12@@Z; StateRepository::Globals::Shutdown(StateRepository::Globals::Flags)
0x180016edc  test    eax, eax
0x180016ede  jns     short loc_180016EF5
0x180016ee0  mov     rcx, [rsp+78h]; this
0x180016ee5  mov     r9d, eax; char *
0x180016ee8  mov     r8, rbx; unsigned int
0x180016eeb  mov     edx, 0CDh; void *
0x180016ef0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016ef5  mov     rcx, rbp
0x180016ef8  call    McGenEventUnregister_EventUnregister
0x180016efd  mov     edx, 0CFh
0x180016f02  jmp     short loc_180016E90
0x180016f04  mov     rcx, rbx; struct _tlgProvider_t *
0x180016f07  mov     cs:qword_18004BDF0, rbx
0x180016f0e  call    ?Initialize@DatabaseCacheSingleton@StateRepository@@SAJPEBU_tlgProvider_t@@@Z; StateRepository::DatabaseCacheSingleton::Initialize(_tlgProvider_t const *)
0x180016f13  mov     edi, eax
0x180016f15  test    eax, eax
0x180016f17  jns     loc_180016FB6
0x180016f1d  mov     rcx, [rsp+78h]; this
0x180016f22  lea     rbx, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\staterepositor"...
0x180016f29  mov     r8, rbx; unsigned int
0x180016f2c  mov     r9d, eax; char *
0x180016f2f  mov     edx, 0E5h; void *
0x180016f34  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016f39  mov     ecx, esi
0x180016f3b  mov     cs:qword_18004BDF0, 0
0x180016f46  call    StateRepository__ProcessShutdown
0x180016f4b  test    eax, eax
0x180016f4d  jns     short loc_180016F64
0x180016f4f  mov     rcx, [rsp+78h]; this
0x180016f54  mov     r9d, eax; char *
0x180016f57  mov     r8, rbx; unsigned int
0x180016f5a  mov     edx, 0E9h; void *
0x180016f5f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016f64  mov     ecx, esi
0x180016f66  call    ?Shutdown@Logging@StateRepository@@YAJW4InitializeFlags@12@@Z; StateRepository::Logging::Shutdown(StateRepository::Logging::InitializeFlags)
0x180016f6b  test    eax, eax
0x180016f6d  jns     short loc_180016F84
0x180016f6f  mov     rcx, [rsp+78h]; this
0x180016f74  mov     r9d, eax; char *
0x180016f77  mov     r8, rbx; unsigned int
0x180016f7a  mov     edx, 0EAh; void *
0x180016f7f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016f84  mov     ecx, esi
0x180016f86  call    ?Shutdown@Globals@StateRepository@@YAJW4Flags@12@@Z; StateRepository::Globals::Shutdown(StateRepository::Globals::Flags)
0x180016f8b  test    eax, eax
0x180016f8d  jns     short loc_180016FA4
0x180016f8f  mov     rcx, [rsp+78h]; this
0x180016f94  mov     r9d, eax; char *
0x180016f97  mov     r8, rbx; unsigned int
0x180016f9a  mov     edx, 0EBh; void *
0x180016f9f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016fa4  mov     rcx, rbp
0x180016fa7  call    McGenEventUnregister_EventUnregister
0x180016fac  mov     edx, 0EDh
0x180016fb1  jmp     loc_180016E90
0x180016fb6  call    ?LoggerInitialized@StateRepository@@YAXXZ; StateRepository::LoggerInitialized(void)
0x180016fbb  xor     eax, eax
0x180016fbd  add     rsp, 58h
0x180016fc1  pop     rdi
0x180016fc2  pop     rsi
0x180016fc3  pop     rbp
0x180016fc4  pop     rbx
0x180016fc5  retn
```
