# DllMain

- ea: `0x18002ac10`
- end: `0x18002ad25`
- name: `DllMain`
- size: `277`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x1800176cc`
- `0x180017794`
- `0x1800188d0`
- `0x180018a14`
- `0x180018d70`
- `0x180019094`
- `0x18002ac10`
- `0x18002ad2c`
- `0x180039ac8`

## import_xrefs

- `ntdll!LdrFindEntryForAddress` at `0x18002ac8b`
- `ntdll!LdrFindEntryForAddress` at `0x18002ac8b`
- `ntdll!RtlInitializeCriticalSection` at `0x18002ac98`
- `ntdll!RtlInitializeCriticalSection` at `0x18002ac98`
- `ntdll!RtlDeleteCriticalSection` at `0x18002ad08`
- `ntdll!RtlDeleteCriticalSection` at `0x18002ad08`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18002aca1`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18002aca1`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DllMainCRTStartupForGS2(hinstDLL, fdwReason, lpReserved);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1800803E0);
      AslLogCreate(&g_ApphelpDebugLog, (__int64)"ApphelpDebug", 0x400u);
      g_AslLogPfnVPrintf = (__int64)ApphelpDebugVPrintf;
      AslLogPublishToPeb(g_ApphelpDebugLog);
      AslTelemetryCreate(&g_ApphelpTelemetry, "Apphelp");
      LdrFindEntryForAddress(hinstDLL, &g_DataTableEntry);
      RtlInitializeCriticalSection(&g_EngineLock);
      DisableThreadLibraryCalls(hinstDLL);
    }
  }
  else
  {
    if ( !lpReserved )
    {
      AslTelemetryDelete(g_ApphelpTelemetry);
      g_ApphelpTelemetry = 0;
      AslLogDelete(g_ApphelpDebugLog);
      g_ApphelpDebugLog = 0;
    }
    if ( !g_ProcessDying )
    {
      if ( g_StateLog )
        AslLogDelete(g_StateLog);
      g_StateLog = 0;
      RtlDeleteCriticalSection(&g_EngineLock);
    }
    TraceLoggingUnregister_EventUnregister(&dword_1800803E0);
  }
  return 1;
}

```

## disassembly

```asm
0x18002ac10  push    rbx
0x18002ac12  sub     rsp, 20h
0x18002ac16  mov     rbx, rcx
0x18002ac19  test    edx, edx
0x18002ac1b  jz      loc_18002ACA9
0x18002ac21  cmp     edx, 1
0x18002ac24  jnz     loc_18002AD1A
0x18002ac2a  call    _DllMainCRTStartupForGS2
0x18002ac2f  lea     rcx, dword_1800803E0; CallbackContext
0x18002ac36  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18002ac3b  mov     r8d, 400h
0x18002ac41  lea     rdx, aApphelpdebug; "ApphelpDebug"
0x18002ac48  lea     rcx, g_ApphelpDebugLog
0x18002ac4f  call    AslLogCreate
0x18002ac54  mov     rcx, cs:g_ApphelpDebugLog
0x18002ac5b  lea     rax, ApphelpDebugVPrintf
0x18002ac62  mov     cs:g_AslLogPfnVPrintf, rax
0x18002ac69  call    AslLogPublishToPeb
0x18002ac6e  lea     rdx, aApphelp_0; "Apphelp"
0x18002ac75  lea     rcx, g_ApphelpTelemetry
0x18002ac7c  call    AslTelemetryCreate
0x18002ac81  lea     rdx, g_DataTableEntry; Module
0x18002ac88  mov     rcx, rbx; Address
0x18002ac8b  call    cs:__imp_LdrFindEntryForAddress
0x18002ac91  lea     rcx, g_EngineLock; CriticalSection
0x18002ac98  call    cs:__imp_RtlInitializeCriticalSection
0x18002ac9e  mov     rcx, rbx; hLibModule
0x18002aca1  call    cs:__imp_DisableThreadLibraryCalls
0x18002aca7  jmp     short loc_18002AD1A
0x18002aca9  test    r8, r8
0x18002acac  jnz     short loc_18002ACDC
0x18002acae  mov     rcx, cs:g_ApphelpTelemetry
0x18002acb5  call    AslTelemetryDelete
0x18002acba  mov     rcx, cs:g_ApphelpDebugLog
0x18002acc1  mov     cs:g_ApphelpTelemetry, 0
0x18002accc  call    AslLogDelete
0x18002acd1  mov     cs:g_ApphelpDebugLog, 0
0x18002acdc  cmp     cs:g_ProcessDying, 0
0x18002ace3  jnz     short loc_18002AD0E
0x18002ace5  mov     rcx, cs:g_StateLog
0x18002acec  test    rcx, rcx
0x18002acef  jz      short loc_18002ACF6
0x18002acf1  call    AslLogDelete
0x18002acf6  lea     rcx, g_EngineLock; CriticalSection
0x18002acfd  mov     cs:g_StateLog, 0
0x18002ad08  call    cs:__imp_RtlDeleteCriticalSection
0x18002ad0e  lea     rcx, dword_1800803E0
0x18002ad15  call    TraceLoggingUnregister_EventUnregister
0x18002ad1a  mov     eax, 1
0x18002ad1f  add     rsp, 20h
0x18002ad23  pop     rbx
0x18002ad24  retn
```
