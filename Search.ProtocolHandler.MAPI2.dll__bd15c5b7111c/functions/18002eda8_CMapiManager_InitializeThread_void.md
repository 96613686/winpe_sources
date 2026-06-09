# CMapiManager::InitializeThread(void)

- ea: `0x18002eda8`
- end: `0x18002ee3e`
- name: `?InitializeThread@CMapiManager@@QEAAJXZ`
- size: `150`
- prototype: `__int64 __fastcall(CMapiManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f9cc`

## callees

- `0x180004c20`
- `0x18000fd58`
- `0x1800113ac`
- `0x1800113ec`
- `0x18002eda8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002edbe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002edbe`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIInitialize` at `0x18002ede6`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIInitialize` at `0x18002ee15`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIInitialize` at `0x18002ede6`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIInitialize` at `0x18002ee15`

## string_xrefs

- `0x18002edd5`: `   CMapiManager::IntializeThread() MapiInitialize() Calling...`
- `0x18002ee1d`: `   CMapiManager::IntializeThread() MapiInitialize() Completed!`
- `0x18002edf2`: `     CMapiManager::IntializeThread() MapiInitialize() FAILED!, trying again`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMapiManager::InitializeThread(CMapiManager *this)
{
  int v1; // eax
  unsigned int v2; // ebx
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v5; // [rsp+38h] [rbp+10h] BYREF

  v4 = (__int64)this;
  v5 = &CMapiManager::s_csMapiIdleThread;
  EnterCriticalSection(&CMapiManager::s_csMapiIdleThread);
  v4 = 0x900000000LL;
  CLogger::Info(L"   CMapiManager::IntializeThread() MapiInitialize() Calling...");
  v1 = MAPIInitialize(&v4);
  v2 = v1;
  if ( v1 < 0 )
  {
    CLogger::Error((unsigned int)v1, L"     CMapiManager::IntializeThread() MapiInitialize() FAILED!, trying again");
    if ( v2 == -2147221242 )
    {
      HIDWORD(v4) = 1;
      v2 = MAPIInitialize(&v4);
    }
  }
  CLogger::Info(v2, L"   CMapiManager::IntializeThread() MapiInitialize() Completed!");
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v5);
  return v2;
}

```

## disassembly

```asm
0x18002eda8  mov     [rsp+arg_0], rcx
0x18002edad  push    rbx
0x18002edae  sub     rsp, 20h
0x18002edb2  lea     rcx, ?s_csMapiIdleThread@CMapiManager@@0VCriticalSection@@A; lpCriticalSection
0x18002edb9  mov     [rsp+28h+arg_8], rcx
0x18002edbe  call    cs:__imp_EnterCriticalSection
0x18002edc4  nop
0x18002edc5  mov     dword ptr [rsp+28h+arg_0], 0
0x18002edcd  mov     dword ptr [rsp+28h+arg_0+4], 9
0x18002edd5  lea     rcx, aCmapimanagerIn; "   CMapiManager::IntializeThread() Mapi"...
0x18002eddc  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18002ede1  lea     rcx, [rsp+28h+arg_0]
0x18002ede6  call    cs:__imp_MAPIInitialize
0x18002edec  mov     ebx, eax
0x18002edee  test    eax, eax
0x18002edf0  jns     short loc_18002EE1D
0x18002edf2  lea     rdx, aCmapimanagerIn_3; "     CMapiManager::IntializeThread() Ma"...
0x18002edf9  mov     ecx, eax; int
0x18002edfb  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x18002ee00  cmp     ebx, 80040106h
0x18002ee06  jnz     short loc_18002EE1D
0x18002ee08  mov     dword ptr [rsp+28h+arg_0+4], 1
0x18002ee10  lea     rcx, [rsp+28h+arg_0]
0x18002ee15  call    cs:__imp_MAPIInitialize
0x18002ee1b  mov     ebx, eax
0x18002ee1d  lea     rdx, aCmapimanagerIn_0; "   CMapiManager::IntializeThread() Mapi"...
0x18002ee24  mov     ecx, ebx; int
0x18002ee26  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x18002ee2b  nop
0x18002ee2c  lea     rcx, [rsp+28h+arg_8]
0x18002ee31  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002ee36  mov     eax, ebx
0x18002ee38  add     rsp, 20h
0x18002ee3c  pop     rbx
0x18002ee3d  retn
```
