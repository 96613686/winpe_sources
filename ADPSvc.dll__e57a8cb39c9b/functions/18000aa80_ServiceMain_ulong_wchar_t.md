# ServiceMain(ulong,wchar_t * *)

- ea: `0x18000aa80`
- end: `0x18000aba7`
- name: `?ServiceMain@@YAXKPEAPEA_W@Z`
- size: `295`
- prototype: `void __fastcall(__int64, wchar_t **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800033bc`
- `0x18000aa80`
- `0x18000f148`
- `0x1800118cc`
- `0x1800249b0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000aad7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000aad7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000aae6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000aae6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000aacf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000aacf`

## string_xrefs

- `0x18000aaf3`: `Service starting.`
- `0x18000ab8b`: `Created database manager.`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, wchar_t **a2)
{
  volatile signed __int32 *v2; // rbx
  _DWORD *v3; // [rsp+40h] [rbp-18h]
  int v4; // [rsp+70h] [rbp+18h] BYREF
  DWORD v5; // [rsp+78h] [rbp+20h] BYREF

  v4 = 0;
  v5 = 4;
  RegGetValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\ADPSvc", L"ADPSvcWaitOnAttach", 0x20000010u, 0, &v4, &v5);
  while ( v4 && !IsDebuggerPresent() )
    Sleep(0x1F4u);
  ADPTraceLoggingProvider::TraceLoggingInfo("Service starting.");
  v3 = operator new(0x58u);
  *(_OWORD *)v3 = 0;
  v3[2] = 1;
  v3[3] = 1;
  *(_QWORD *)v3 = &std::_Ref_count_obj2<DatabaseManager>::`vftable';
  DatabaseManager::DatabaseManager((DatabaseManager *)(v3 + 4), 0);
  ADPService::g_databaseManager = (__int64)(v3 + 4);
  v2 = (volatile signed __int32 *)qword_18010F9B0;
  qword_18010F9B0 = (__int64)v3;
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( !_InterlockedDecrement(v2 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  ADPTraceLoggingProvider::TraceLoggingInfo("Created database manager.");
  wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::main();
}

```

## disassembly

```asm
0x18000aa80  mov     r11, rsp
0x18000aa83  mov     [r11+8], rbx
0x18000aa87  push    rdi
0x18000aa88  sub     rsp, 50h
0x18000aa8c  mov     [rsp+58h+arg_10], 0
0x18000aa94  mov     [rsp+58h+arg_18], 4
0x18000aa9c  lea     rax, [r11+20h]
0x18000aaa0  mov     [r11-28h], rax
0x18000aaa4  lea     rax, [r11+18h]
0x18000aaa8  mov     [r11-30h], rax
0x18000aaac  mov     qword ptr [r11-38h], 0
0x18000aab4  mov     r9d, 20000010h; dwFlags
0x18000aaba  lea     r8, Value; "ADPSvcWaitOnAttach"
0x18000aac1  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\ADPSvc"
0x18000aac8  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000aacf  call    cs:__imp_RegGetValueW
0x18000aad5  jmp     short loc_18000AAEC
0x18000aad7  call    cs:__imp_IsDebuggerPresent
0x18000aadd  test    eax, eax
0x18000aadf  jnz     short loc_18000AAF3
0x18000aae1  mov     ecx, 1F4h; dwMilliseconds
0x18000aae6  call    cs:__imp_Sleep
0x18000aaec  cmp     [rsp+58h+arg_10], 0
0x18000aaf1  jnz     short loc_18000AAD7
0x18000aaf3  lea     rcx, aServiceStartin; "Service starting."
0x18000aafa  call    ?TraceLoggingInfo@ADPTraceLoggingProvider@@SAXPEBDZZ; ADPTraceLoggingProvider::TraceLoggingInfo(char const *,...)
0x18000aaff  mov     ecx, 58h ; 'X'; Size
0x18000ab04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ab09  mov     rdi, rax
0x18000ab0c  mov     [rsp+58h+var_18], rax
0x18000ab11  xorps   xmm0, xmm0
0x18000ab14  movups  xmmword ptr [rax], xmm0
0x18000ab17  mov     eax, 1
0x18000ab1c  mov     [rdi+8], eax
0x18000ab1f  mov     [rdi+0Ch], eax
0x18000ab22  lea     rax, ??_7?$_Ref_count_obj2@VDatabaseManager@@@std@@6B@; const std::_Ref_count_obj2<DatabaseManager>::`vftable'
0x18000ab29  mov     [rdi], rax
0x18000ab2c  lea     rbx, [rdi+10h]
0x18000ab30  xor     edx, edx; bool
0x18000ab32  mov     rcx, rbx; this
0x18000ab35  call    ??0DatabaseManager@@QEAA@_N@Z; DatabaseManager::DatabaseManager(bool)
0x18000ab3a  nop
0x18000ab3b  mov     cs:?g_databaseManager@ADPService@@3V?$shared_ptr@VDatabaseManager@@@std@@A, rbx; std::shared_ptr<DatabaseManager> ADPService::g_databaseManager
0x18000ab42  mov     rbx, cs:qword_18010F9B0
0x18000ab49  mov     cs:qword_18010F9B0, rdi
0x18000ab50  test    rbx, rbx
0x18000ab53  jz      short loc_18000AB8B
0x18000ab55  or      edi, 0FFFFFFFFh
0x18000ab58  mov     eax, edi
0x18000ab5a  lock xadd [rbx+8], eax
0x18000ab5f  add     eax, edi
0x18000ab61  jnz     short loc_18000AB8B
0x18000ab63  mov     rax, [rbx]
0x18000ab66  mov     rcx, rbx
0x18000ab69  mov     rax, [rax]
0x18000ab6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab71  mov     eax, edi
0x18000ab73  lock xadd [rbx+0Ch], eax
0x18000ab78  add     eax, edi
0x18000ab7a  jnz     short loc_18000AB8B
0x18000ab7c  mov     rax, [rbx]
0x18000ab7f  mov     rcx, rbx
0x18000ab82  mov     rax, [rax+8]
0x18000ab86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab8b  lea     rcx, aCreatedDatabas; "Created database manager."
0x18000ab92  call    ?TraceLoggingInfo@ADPTraceLoggingProvider@@SAXPEBDZZ; ADPTraceLoggingProvider::TraceLoggingInfo(char const *,...)
0x18000ab97  call    ?main@?$svchost_service@UAdpServiceTraits@ADPService@@UAggregatedDataPlatform@3Internal@Windows@winrt@@@wil@@QEAAXXZ; wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::main(void)
0x18000ab9c  mov     rbx, [rsp+58h+arg_0]
0x18000aba1  add     rsp, 50h
0x18000aba5  pop     rdi
0x18000aba6  retn
```
