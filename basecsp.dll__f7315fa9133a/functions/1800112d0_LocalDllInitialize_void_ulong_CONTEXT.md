# LocalDllInitialize(void *,ulong,_CONTEXT *)

- ea: `0x1800112d0`
- end: `0x180011464`
- name: `?LocalDllInitialize@@YAHPEAXKPEAU_CONTEXT@@@Z`
- size: `404`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callees

- `0x1800010b4`
- `0x18000d2b0`
- `0x18001040c`
- `0x1800112d0`
- `0x18001866c`
- `0x1800197b0`
- `0x180019898`
- `0x18002ae50`
- `0x18002b15c`
- `0x18002c40c`
- `0x18002ce30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800113b7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800113b7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011402`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011402`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180011398`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180011398`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800113ed`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800113ed`

## pseudocode

```c
__int64 __fastcall LocalDllInitialize(HINSTANCE a1, __int64 a2, struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE v5; // rcx
  REGHANDLE v6; // rcx
  int v7; // edx
  int v8; // r8d

  v4 = 0;
  if ( (_DWORD)a2 )
  {
    if ( (_DWORD)a2 != 1 )
      return v4;
    SafeAllocaInitialize(a1, a2, a3);
    hThisModule = a1;
    if ( a1 )
    {
      g_hInst = a1;
      if ( !(unsigned int)LoadStrings(a1) )
      {
        dword_18003C730 = 1;
        if ( !InitializeCspState(a1) )
        {
          dword_18003C6B0 = 1;
          qword_18003C280 = 0;
          WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CryptoControlGuid;
          WPP_GLOBAL_Control = &WPP_MAIN_CB;
          WPP_MAIN_CB = 0;
          qword_18003C288 = 1;
          WppInitUm();
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent>::GetImpl'::`2'::impl) )
          {
            TraceLoggingRegisterEx_EventRegister_EventSetInformation();
            InitializeCriticalSection(&stru_18003C2A8);
            dword_18003C488 = 1;
          }
          return 1;
        }
      }
    }
  }
  else
  {
    v5 = g_hWinscard;
    if ( g_hWinscard )
    {
      FreeLibrary(g_hWinscard);
      g_hWinscard = 0;
    }
    WppCleanupUm(v5, a2, a3);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent>::GetImpl'::`2'::impl) )
    {
      v6 = RegHandle;
      dword_18003B0F8 = 0;
      RegHandle = 0;
      EventUnregister(v6);
      if ( dword_18003C488 )
      {
        DeleteCriticalSection(&stru_18003C2A8);
        dword_18003C488 = 0;
      }
    }
    v4 = 1;
  }
  if ( dword_18003C730 )
  {
    UnloadStrings(&g_Strings, 18);
    dword_18003C730 = 0;
  }
  if ( dword_18003C6B0 )
  {
    I_TransactionManagerCleanup((struct _TRANSACTION_MANAGER_STATE *)g_pTransactionManagerState, 1);
    g_pTransactionManagerState = 0;
    DeleteCspState(1u, v7, v8);
    dword_18003C6B0 = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1800112d0  push    rbx
0x1800112d2  push    rbp
0x1800112d3  push    rsi
0x1800112d4  push    rdi
0x1800112d5  sub     rsp, 28h
0x1800112d9  xor     esi, esi
0x1800112db  mov     rdi, rcx
0x1800112de  mov     ebx, esi
0x1800112e0  lea     ebp, [rsi+1]
0x1800112e3  test    edx, edx
0x1800112e5  jz      loc_1800113AB
0x1800112eb  cmp     edx, ebp
0x1800112ed  jnz     loc_180011459
0x1800112f3  call    SafeAllocaInitialize
0x1800112f8  mov     cs:?hThisModule@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * hThisModule
0x1800112ff  test    rdi, rdi
0x180011302  jz      loc_180011410
0x180011308  lea     r8d, [rsi+12h]
0x18001130c  mov     cs:?g_hInst@@3PEAXEA, rdi; void * g_hInst
0x180011313  lea     rdx, ?g_Strings@@3PAU_CSP_STRING@@A; _CSP_STRING near * g_Strings
0x18001131a  mov     rcx, rdi; hInstance
0x18001131d  call    LoadStrings
0x180011322  test    eax, eax
0x180011324  jnz     loc_180011410
0x18001132a  mov     rcx, rdi; HINSTANCE
0x18001132d  mov     cs:dword_18003C730, ebp
0x180011333  call    ?InitializeCspState@@YAKPEAUHINSTANCE__@@@Z; InitializeCspState(HINSTANCE__ *)
0x180011338  test    eax, eax
0x18001133a  jnz     loc_180011410
0x180011340  mov     cs:dword_18003C6B0, ebp
0x180011346  lea     rax, WPP_ThisDir_CTLGUID_CryptoControlGuid
0x18001134d  mov     cs:qword_18003C280, rsi
0x180011354  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18001135b  lea     rax, WPP_MAIN_CB
0x180011362  mov     cs:WPP_GLOBAL_Control, rax
0x180011369  mov     cs:WPP_MAIN_CB, rsi
0x180011370  mov     cs:qword_18003C288, rbp
0x180011377  call    WppInitUm
0x18001137c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent> `wil::Feature<__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent>::GetImpl(void)'::`2'::impl
0x180011383  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent>::__private_IsEnabled(void)
0x180011388  test    al, al
0x18001138a  jz      short loc_1800113A4
0x18001138c  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180011391  lea     rcx, stru_18003C2A8; lpCriticalSection
0x180011398  call    cs:__imp_InitializeCriticalSection
0x18001139e  mov     cs:dword_18003C488, ebp
0x1800113a4  mov     ebx, ebp
0x1800113a6  jmp     loc_180011459
0x1800113ab  mov     rcx, cs:?g_hWinscard@@3PEAUHINSTANCE__@@EA; hLibModule
0x1800113b2  test    rcx, rcx
0x1800113b5  jz      short loc_1800113C4
0x1800113b7  call    cs:__imp_FreeLibrary
0x1800113bd  mov     cs:?g_hWinscard@@3PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * g_hWinscard
0x1800113c4  call    WppCleanupUm
0x1800113c9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent> `wil::Feature<__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent>::GetImpl(void)'::`2'::impl
0x1800113d0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent>::__private_IsEnabled(void)
0x1800113d5  test    al, al
0x1800113d7  jz      short loc_18001140E
0x1800113d9  mov     rcx, cs:RegHandle; RegHandle
0x1800113e0  mov     cs:dword_18003B0F8, esi
0x1800113e6  mov     cs:RegHandle, rsi
0x1800113ed  call    cs:__imp_EventUnregister
0x1800113f3  cmp     cs:dword_18003C488, esi
0x1800113f9  jz      short loc_18001140E
0x1800113fb  lea     rcx, stru_18003C2A8; lpCriticalSection
0x180011402  call    cs:__imp_DeleteCriticalSection
0x180011408  mov     cs:dword_18003C488, esi
0x18001140e  mov     ebx, ebp
0x180011410  cmp     cs:dword_18003C730, esi
0x180011416  jz      short loc_18001142F
0x180011418  mov     edx, 12h
0x18001141d  lea     rcx, ?g_Strings@@3PAU_CSP_STRING@@A; _CSP_STRING near * g_Strings
0x180011424  call    UnloadStrings
0x180011429  mov     cs:dword_18003C730, esi
0x18001142f  cmp     cs:dword_18003C6B0, esi
0x180011435  jz      short loc_180011459
0x180011437  mov     rcx, cs:?g_pTransactionManagerState@@3PEAU_TRANSACTION_MANAGER_STATE@@EA; struct _TRANSACTION_MANAGER_STATE *
0x18001143e  mov     edx, ebp; int
0x180011440  call    ?I_TransactionManagerCleanup@@YAXPEAU_TRANSACTION_MANAGER_STATE@@H@Z; I_TransactionManagerCleanup(_TRANSACTION_MANAGER_STATE *,int)
0x180011445  mov     ecx, ebp; int
0x180011447  mov     cs:?g_pTransactionManagerState@@3PEAU_TRANSACTION_MANAGER_STATE@@EA, rsi; _TRANSACTION_MANAGER_STATE * g_pTransactionManagerState
0x18001144e  call    ?DeleteCspState@@YAKH@Z; DeleteCspState(int)
0x180011453  mov     cs:dword_18003C6B0, esi
0x180011459  mov     eax, ebx
0x18001145b  add     rsp, 28h
0x18001145f  pop     rdi
0x180011460  pop     rsi
0x180011461  pop     rbp
0x180011462  pop     rbx
0x180011463  retn
```
