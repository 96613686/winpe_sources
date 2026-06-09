# StateRepository::Initialize(void (*)(void),_tlgProvider_t const *,wchar_t const *,void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(void *,char const *),void (*)(void *,char const *,uint),int,long (*)(StateRepository::Partition,wchar_t * *),wchar_t const *,wchar_t const *,wchar_t const *,StateRepository::InitializeFlags)

- ea: `0x18010165c`
- end: `0x1801019b1`
- name: `?Initialize@StateRepository@@YAJP6AXXZPEBU_tlgProvider_t@@PEB_WP6AXHPEBD@Z4444P6AXPEAX3@ZP6AX53I@ZHP6AJW4Partition@1@PEAPEA_W@Z222W4InitializeFlags@1@@Z`
- size: `853`
- prototype: `int(__int64, __int64, __int64, ...)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f6584`

## callees

- `0x1800e4c4c`
- `0x1800eabf4`
- `0x1800f7630`
- `0x18010165c`
- `0x180101d30`
- `0x180101e68`
- `0x180101ebc`
- `0x180102264`
- `0x180102548`
- `0x180102574`
- `0x180102e1c`
- `0x180103e6c`
- `0x180104fbc`
- `0x1801063dc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1801016dd`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1801016dd`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1801018b6`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1801018b6`

## string_xrefs

- `0x1801016a9`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x180101724`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x18010177d`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x1801017da`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x180101918`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x1801018fa`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecachesingleton.cpp`

## pseudocode

```c
int StateRepository::Initialize(__int64 a1, __int64 a2, __int64 a3, ...)
{
  unsigned int v4; // eax
  unsigned int v6; // eax
  void *v7; // rdx
  __int64 v8; // rcx
  void *v9; // r8
  __int64 v10; // r9
  unsigned int v11; // esi
  int v12; // ebp
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // edi
  __int64 v17; // rdx
  unsigned int v18; // ebp
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  _QWORD *v24; // rax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  unsigned int v28; // [rsp+20h] [rbp-48h]
  int v29; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned __int64 UnbiasedTime; // [rsp+88h] [rbp+20h] BYREF
  va_list UnbiasedTimea; // [rsp+88h] [rbp+20h]
  __int64 v33; // [rsp+90h] [rbp+28h]
  __int64 v34; // [rsp+98h] [rbp+30h]
  __int64 v35; // [rsp+A0h] [rbp+38h]
  __int64 v36; // [rsp+A8h] [rbp+40h]
  __int64 v37; // [rsp+B0h] [rbp+48h]
  __int64 v38; // [rsp+B8h] [rbp+50h]
  __int64 v39; // [rsp+C0h] [rbp+58h]
  __int64 v40; // [rsp+C8h] [rbp+60h]
  __int64 v41; // [rsp+D0h] [rbp+68h]
  __int64 v42; // [rsp+D8h] [rbp+70h]
  __int64 v43; // [rsp+E0h] [rbp+78h]
  __int64 v44; // [rsp+E8h] [rbp+80h]
  va_list va1; // [rsp+F0h] [rbp+88h] BYREF

  va_start(va1, a3);
  va_start(UnbiasedTimea, a3);
  UnbiasedTime = va_arg(va1, _QWORD);
  v33 = va_arg(va1, _QWORD);
  v34 = va_arg(va1, _QWORD);
  v35 = va_arg(va1, _QWORD);
  v36 = va_arg(va1, _QWORD);
  v37 = va_arg(va1, _QWORD);
  v38 = va_arg(va1, _QWORD);
  v39 = va_arg(va1, _QWORD);
  v40 = va_arg(va1, _QWORD);
  v41 = va_arg(va1, _QWORD);
  v42 = va_arg(va1, _QWORD);
  v43 = va_arg(va1, _QWORD);
  v44 = va_arg(va1, _QWORD);
  if ( _InterlockedIncrement(&dword_1801403AC) == 1 )
  {
    v4 = McGenEventRegister_EventRegister(
           a1,
           a2,
           &STATEREPOSITORY_ETW_CONTROL_GUID_Context,
           &STATEREPOSITORY_ETW_CONTROL_GUID_Context);
    if ( v4 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xBA,
               (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
               (const char *)v4,
               v28);
    v6 = EventSetInformation(
           STATEREPOSITORY_ETW_CONTROL_GUID_Context,
           2,
           &`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits,
           (unsigned __int16)`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits);
    if ( v6 )
      wil::details::in1diag3::_Log_Win32(retaddr, v7, (unsigned int)v9, (const char *)v6, v28);
    v11 = v44 & 1 | 2;
    v12 = v44 & 2;
    if ( (v44 & 2) == 0 )
      v11 = v44 & 1;
    v13 = StateRepository::Globals::Initialize(v8, (__int64)v7, v9, v10, v11);
    v16 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBF,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
        (const char *)(unsigned int)v13);
      McGenEventUnregister_EventUnregister(&STATEREPOSITORY_ETW_CONTROL_GUID_Context);
      v17 = 195;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
        (const char *)v16,
        v29);
      return v16;
    }
    v18 = v12 != 0 ? 2 : 0;
    v19 = StateRepository::Logging::Initialize(a2, v14, v15);
    v16 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xCA,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
        (const char *)(unsigned int)v19);
      v20 = StateRepository::Globals::Shutdown(v11);
      if ( v20 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xCD,
          (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
          (const char *)(unsigned int)v20);
      McGenEventUnregister_EventUnregister(&STATEREPOSITORY_ETW_CONTROL_GUID_Context);
      v17 = 207;
      goto LABEL_10;
    }
    v21 = StateRepository::ProcessInitialize((unsigned int)v44);
    v16 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xD2,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
        (const char *)(unsigned int)v21);
      v22 = StateRepository::Logging::Shutdown(v18);
      if ( v22 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xD5,
          (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
          (const char *)(unsigned int)v22);
      v23 = StateRepository::Globals::Shutdown(v11);
      if ( v23 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xD6,
          (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
          (const char *)(unsigned int)v23);
      McGenEventUnregister_EventUnregister(&STATEREPOSITORY_ETW_CONTROL_GUID_Context);
      v17 = 216;
      goto LABEL_10;
    }
    qword_1801402E8 = a2;
    v24 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v24 )
    {
      v16 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecachesingleton.cpp",
        (const char *)0x8007000ELL,
        v29);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE5,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
        (const char *)0x8007000ELL);
      qword_1801402E8 = 0;
      v25 = StateRepository::ProcessShutdown((unsigned int)v44);
      if ( v25 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xE9,
          (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
          (const char *)(unsigned int)v25);
      v26 = StateRepository::Logging::Shutdown(v18);
      if ( v26 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xEA,
          (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
          (const char *)(unsigned int)v26);
      v27 = StateRepository::Globals::Shutdown(v11);
      if ( v27 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xEB,
          (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
          (const char *)(unsigned int)v27);
      McGenEventUnregister_EventUnregister(&STATEREPOSITORY_ETW_CONTROL_GUID_Context);
      v17 = 237;
      goto LABEL_10;
    }
    *v24 = 0;
    v24[1] = 0;
    v24[2] = 0;
    *((_BYTE *)v24 + 24) = 1;
    v24[4] = 0;
    v24[5] = 0;
    v24[6] = 0;
    v24[7] = a2;
    StateRepository::DatabaseCacheSingleton::s_cache = (StateRepository::DatabaseCache *)v24;
    UnbiasedTime = 0;
    QueryUnbiasedInterruptTime((PULONGLONG)UnbiasedTimea);
    qword_1801403A0 = a2;
    StateRepository::DatabaseCacheSingleton::s_whenInitialized = UnbiasedTime / 0x2710;
  }
  return 0;
}

```

## disassembly

```asm
0x18010165c  mov     [rsp+arg_0], rbx
0x180101661  mov     [rsp+arg_8], rbp
0x180101666  mov     [rsp+UnbiasedTime], r9
0x18010166b  push    rsi
0x18010166c  push    rdi
0x18010166d  push    r12
0x18010166f  sub     rsp, 50h
0x180101673  mov     rbx, rdx
0x180101676  mov     eax, 1
0x18010167b  lock xadd cs:dword_1801403AC, eax
0x180101683  inc     eax
0x180101685  cmp     eax, 1
0x180101688  jnz     loc_1801018E0
0x18010168e  lea     r12, STATEREPOSITORY_ETW_CONTROL_GUID_Context
0x180101695  mov     r9, r12
0x180101698  mov     r8, r12
0x18010169b  call    McGenEventRegister_EventRegister
0x1801016a0  test    eax, eax
0x1801016a2  jz      short loc_1801016C2
0x1801016a4  mov     rcx, [rsp+68h]; this
0x1801016a9  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x1801016b0  mov     r9d, eax; char *
0x1801016b3  mov     edx, 0BAh; void *
0x1801016b8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801016bd  jmp     loc_1801018E2
0x1801016c2  movzx   r9d, cs:?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x1801016ca  lea     r8, ?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x1801016d1  mov     rcx, cs:STATEREPOSITORY_ETW_CONTROL_GUID_Context
0x1801016d8  mov     edx, 2
0x1801016dd  call    cs:__imp_EventSetInformation
0x1801016e3  test    eax, eax
0x1801016e5  jz      short loc_1801016F4
0x1801016e7  mov     rcx, [rsp+68h]; this
0x1801016ec  mov     r9d, eax; char *
0x1801016ef  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1801016f4  mov     eax, dword ptr [rsp+68h+arg_78]
0x1801016fb  mov     ebp, dword ptr [rsp+68h+arg_78]
0x180101702  and     eax, 1
0x180101705  mov     esi, eax
0x180101707  or      esi, 2
0x18010170a  and     ebp, 2
0x18010170d  cmovz   esi, eax
0x180101710  mov     [rsp+68h+var_48], esi; int
0x180101714  call    ?Initialize@Globals@StateRepository@@YAJP6AJW4Partition@2@PEAPEA_W@ZPEB_W33W4Flags@12@@Z; StateRepository::Globals::Initialize(long (*)(StateRepository::Partition,wchar_t * *),wchar_t const *,wchar_t const *,wchar_t const *,StateRepository::Globals::Flags)
0x180101719  mov     edi, eax
0x18010171b  test    eax, eax
0x18010171d  jns     short loc_18010175F
0x18010171f  mov     rcx, [rsp+68h]; this
0x180101724  lea     rbx, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x18010172b  mov     r8, rbx; unsigned int
0x18010172e  mov     r9d, eax; char *
0x180101731  mov     edx, 0BFh; void *
0x180101736  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010173b  mov     rcx, r12
0x18010173e  call    McGenEventUnregister_EventUnregister
0x180101743  mov     edx, 0C3h; void *
0x180101748  mov     rcx, [rsp+68h]; this
0x18010174d  mov     r8, rbx; unsigned int
0x180101750  mov     r9d, edi; char *
0x180101753  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101758  mov     eax, edi
0x18010175a  jmp     loc_1801018E2
0x18010175f  neg     ebp
0x180101761  mov     rcx, rbx
0x180101764  sbb     ebp, ebp
0x180101766  and     ebp, 2
0x180101769  mov     [rsp+68h+var_20], ebp
0x18010176d  call    ?Initialize@Logging@StateRepository@@YAJPEBU_tlgProvider_t@@PEB_WP6AXHPEBD@Z3333P6AXPEAX2@ZP6AX42I@ZW4InitializeFlags@12@@Z; StateRepository::Logging::Initialize(_tlgProvider_t const *,wchar_t const *,void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(void *,char const *),void (*)(void *,char const *,uint),StateRepository::Logging::InitializeFlags)
0x180101772  mov     edi, eax
0x180101774  test    eax, eax
0x180101776  jns     short loc_1801017C3
0x180101778  mov     rcx, [rsp+68h]; this
0x18010177d  lea     rbx, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x180101784  mov     r8, rbx; unsigned int
0x180101787  mov     r9d, eax; char *
0x18010178a  mov     edx, 0CAh; void *
0x18010178f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180101794  mov     ecx, esi
0x180101796  call    ?Shutdown@Globals@StateRepository@@YAJW4Flags@12@@Z; StateRepository::Globals::Shutdown(StateRepository::Globals::Flags)
0x18010179b  test    eax, eax
0x18010179d  jns     short loc_1801017B4
0x18010179f  mov     rcx, [rsp+68h]; this
0x1801017a4  mov     r9d, eax; char *
0x1801017a7  mov     r8, rbx; unsigned int
0x1801017aa  mov     edx, 0CDh; void *
0x1801017af  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801017b4  mov     rcx, r12
0x1801017b7  call    McGenEventUnregister_EventUnregister
0x1801017bc  mov     edx, 0CFh
0x1801017c1  jmp     short loc_180101748
0x1801017c3  mov     ecx, dword ptr [rsp+68h+arg_78]
0x1801017ca  call    StateRepository__ProcessInitialize
0x1801017cf  mov     edi, eax
0x1801017d1  test    eax, eax
0x1801017d3  jns     short loc_180101843
0x1801017d5  mov     rcx, [rsp+68h]; this
0x1801017da  lea     rbx, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x1801017e1  mov     r8, rbx; unsigned int
0x1801017e4  mov     r9d, eax; char *
0x1801017e7  mov     edx, 0D2h; void *
0x1801017ec  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801017f1  mov     ecx, ebp
0x1801017f3  call    ?Shutdown@Logging@StateRepository@@YAJW4InitializeFlags@12@@Z; StateRepository::Logging::Shutdown(StateRepository::Logging::InitializeFlags)
0x1801017f8  test    eax, eax
0x1801017fa  jns     short loc_180101811
0x1801017fc  mov     rcx, [rsp+68h]; this
0x180101801  mov     r9d, eax; char *
0x180101804  mov     r8, rbx; unsigned int
0x180101807  mov     edx, 0D5h; void *
0x18010180c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180101811  mov     ecx, esi
0x180101813  call    ?Shutdown@Globals@StateRepository@@YAJW4Flags@12@@Z; StateRepository::Globals::Shutdown(StateRepository::Globals::Flags)
0x180101818  test    eax, eax
0x18010181a  jns     short loc_180101831
0x18010181c  mov     rcx, [rsp+68h]; this
0x180101821  mov     r9d, eax; char *
0x180101824  mov     r8, rbx; unsigned int
0x180101827  mov     edx, 0D6h; void *
0x18010182c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180101831  mov     rcx, r12
0x180101834  call    McGenEventUnregister_EventUnregister
0x180101839  mov     edx, 0D8h
0x18010183e  jmp     loc_180101748
0x180101843  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18010184a  mov     cs:qword_1801402E8, rbx
0x180101851  mov     ecx, 40h ; '@'; unsigned __int64
0x180101856  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18010185b  test    rax, rax
0x18010185e  jz      loc_1801018F5
0x180101864  lea     rcx, [rsp+68h+UnbiasedTime]; UnbiasedTime
0x18010186c  mov     qword ptr [rax], 0
0x180101873  mov     qword ptr [rax+8], 0
0x18010187b  mov     qword ptr [rax+10h], 0
0x180101883  mov     byte ptr [rax+18h], 1
0x180101887  mov     qword ptr [rax+20h], 0
0x18010188f  mov     qword ptr [rax+28h], 0
0x180101897  mov     qword ptr [rax+30h], 0
0x18010189f  mov     [rax+38h], rbx
0x1801018a3  mov     cs:?s_cache@DatabaseCacheSingleton@StateRepository@@0PEAVDatabaseCache@2@EA, rax; StateRepository::DatabaseCache * StateRepository::DatabaseCacheSingleton::s_cache
0x1801018aa  mov     [rsp+68h+UnbiasedTime], 0
0x1801018b6  call    cs:__imp_QueryUnbiasedInterruptTime
0x1801018bc  mov     rax, 346DC5D63886594Bh
0x1801018c6  mov     cs:qword_1801403A0, rbx
0x1801018cd  mul     [rsp+68h+UnbiasedTime]
0x1801018d5  shr     rdx, 0Bh
0x1801018d9  mov     cs:?s_whenInitialized@DatabaseCacheSingleton@StateRepository@@0_KA, rdx; unsigned __int64 StateRepository::DatabaseCacheSingleton::s_whenInitialized
0x1801018e0  xor     eax, eax
0x1801018e2  mov     rbx, [rsp+68h+arg_0]
0x1801018e7  mov     rbp, [rsp+68h+arg_8]
0x1801018ec  add     rsp, 50h
0x1801018f0  pop     r12
0x1801018f2  pop     rdi
0x1801018f3  pop     rsi
0x1801018f4  retn
0x1801018f5  mov     rcx, [rsp+68h]; this
0x1801018fa  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x180101901  mov     edi, 8007000Eh
0x180101906  mov     edx, 74h ; 't'; void *
0x18010190b  mov     r9d, edi; char *
0x18010190e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101913  mov     rcx, [rsp+68h]; this
0x180101918  lea     rbx, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x18010191f  mov     r8, rbx; unsigned int
0x180101922  mov     r9d, edi; char *
0x180101925  mov     edx, 0E5h; void *
0x18010192a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010192f  mov     ecx, dword ptr [rsp+68h+arg_78]
0x180101936  mov     cs:qword_1801402E8, 0
0x180101941  call    StateRepository__ProcessShutdown
0x180101946  test    eax, eax
0x180101948  jns     short loc_18010195F
0x18010194a  mov     rcx, [rsp+68h]; this
0x18010194f  mov     r9d, eax; char *
0x180101952  mov     r8, rbx; unsigned int
0x180101955  mov     edx, 0E9h; void *
0x18010195a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010195f  mov     ecx, ebp
0x180101961  call    ?Shutdown@Logging@StateRepository@@YAJW4InitializeFlags@12@@Z; StateRepository::Logging::Shutdown(StateRepository::Logging::InitializeFlags)
0x180101966  test    eax, eax
0x180101968  jns     short loc_18010197F
0x18010196a  mov     rcx, [rsp+68h]; this
0x18010196f  mov     r9d, eax; char *
0x180101972  mov     r8, rbx; unsigned int
0x180101975  mov     edx, 0EAh; void *
0x18010197a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010197f  mov     ecx, esi
0x180101981  call    ?Shutdown@Globals@StateRepository@@YAJW4Flags@12@@Z; StateRepository::Globals::Shutdown(StateRepository::Globals::Flags)
0x180101986  test    eax, eax
0x180101988  jns     short loc_18010199F
0x18010198a  mov     rcx, [rsp+68h]; this
0x18010198f  mov     r9d, eax; char *
0x180101992  mov     r8, rbx; unsigned int
0x180101995  mov     edx, 0EBh; void *
0x18010199a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010199f  mov     rcx, r12
0x1801019a2  call    McGenEventUnregister_EventUnregister
0x1801019a7  mov     edx, 0EDh
0x1801019ac  jmp     loc_180101748
```
