# Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::Initialize(int)

- ea: `0x1800f64c0`
- end: `0x1800f657d`
- name: `?Initialize@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@CAJH@Z`
- size: `189`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800ee140`

## callees

- `0x1800ec618`
- `0x1800f44fc`
- `0x1800f4818`
- `0x1800f64c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800f64d9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800f64d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f6510`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f6510`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f64e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f64f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f64e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f64f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f6504`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f6504`

## string_xrefs

- `0x1800f656b`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::Initialize(
        int a1)
{
  HANDLE Event; // rsi
  const char *v3; // r9
  HANDLE v4; // rdi
  DWORD LastError; // ebp
  unsigned int v6; // r8d
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v3);
  GetLastError();
  v4 = Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseReady;
  if ( Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseReady )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v4) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v6, v7);
    SetLastError(LastError);
  }
  Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseReady = Event;
  Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_runtimeTargetSchemaVersion = 257;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl'::`2'::impl) )
  {
    Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_runtimeTargetSchemaVersion = 258;
    if ( a1 )
      Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_runtimeTargetSchemaVersion = a1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800f64c0  push    rbx
0x1800f64c2  push    rbp
0x1800f64c3  push    rsi
0x1800f64c4  push    rdi
0x1800f64c5  sub     rsp, 28h
0x1800f64c9  xor     edx, edx; lpName
0x1800f64cb  mov     ebx, ecx
0x1800f64cd  xor     ecx, ecx; lpEventAttributes
0x1800f64cf  mov     r9d, 1F0003h; dwDesiredAccess
0x1800f64d5  lea     r8d, [rdx+1]; dwFlags
0x1800f64d9  call    cs:__imp_CreateEventExW
0x1800f64df  mov     rsi, rax
0x1800f64e2  test    rax, rax
0x1800f64e5  jz      short loc_1800F6566
0x1800f64e7  call    cs:__imp_GetLastError
0x1800f64ed  mov     rdi, cs:?m_databaseReady@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A
0x1800f64f4  test    rdi, rdi
0x1800f64f7  jz      short loc_1800F6516
0x1800f64f9  call    cs:__imp_GetLastError
0x1800f64ff  mov     rcx, rdi; hObject
0x1800f6502  mov     ebp, eax
0x1800f6504  call    cs:__imp_CloseHandle
0x1800f650a  test    eax, eax
0x1800f650c  jz      short loc_1800F6556
0x1800f650e  mov     ecx, ebp; dwErrCode
0x1800f6510  call    cs:__imp_SetLastError
0x1800f6516  mov     cs:?m_databaseReady@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A, rsi
0x1800f651d  mov     cs:?m_runtimeTargetSchemaVersion@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@0HA, 101h; int Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_runtimeTargetSchemaVersion
0x1800f6527  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59213523@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59213523@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523> `wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl(void)'::`2'::impl
0x1800f652e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59213523@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(void)
0x1800f6533  test    al, al
0x1800f6535  jz      short loc_1800F654B
0x1800f6537  mov     cs:?m_runtimeTargetSchemaVersion@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@0HA, 102h; int Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_runtimeTargetSchemaVersion
0x1800f6541  test    ebx, ebx
0x1800f6543  jz      short loc_1800F654B
0x1800f6545  mov     cs:?m_runtimeTargetSchemaVersion@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@0HA, ebx; int Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_runtimeTargetSchemaVersion
0x1800f654b  xor     eax, eax
0x1800f654d  add     rsp, 28h
0x1800f6551  pop     rdi
0x1800f6552  pop     rsi
0x1800f6553  pop     rbp
0x1800f6554  pop     rbx
0x1800f6555  retn
0x1800f6556  mov     rcx, [rsp+48h]; this
0x1800f655b  mov     edx, 0A0Bh; void *
0x1800f6560  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800f6566  mov     rcx, [rsp+48h]; this
0x1800f656b  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800f6572  mov     edx, 1CC8h; void *
0x1800f6577  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
