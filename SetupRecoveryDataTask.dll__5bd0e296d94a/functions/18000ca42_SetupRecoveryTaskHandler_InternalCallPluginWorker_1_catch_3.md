# _SetupRecoveryTaskHandler::InternalCallPluginWorker_::_1_::catch$3

- ea: `0x18000ca42`
- end: `0x18000cae4`
- name: `_SetupRecoveryTaskHandler::InternalCallPluginWorker_::_1_::catch$3`
- size: `162`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x1800040f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca51`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000caca`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000caca`
- `WDSCORE!CurrentIP` at `0x18000ca59`
- `WDSCORE!CurrentIP` at `0x18000ca59`

## string_xrefs

- `0x18000caa7`: `base\diagnosis\srt\setuprecoverydatatask\dll\src\setuprecoverydatatask.cpp`
- `0x18000ca9b`: `SetupRecoveryTaskHandler::InternalCallPluginWorker`
- `0x18000ca70`: `SetupRecoveryTaskHandler::InternalCallPluginWorker: Unhandled exception while executing the plugin. Plugin: [%s], Entry Point: [%s]`

## pseudocode

```c
__int64 __fastcall SetupRecoveryTaskHandler::InternalCallPluginWorker_::_1_::catch_3(__int64 a1, __int64 a2)
{
  DWORD LastError; // edi
  __int64 v4; // rbx
  struct tagLOG_PARTIAL_MSG *v5; // rax

  LastError = GetLastError();
  v4 = CurrentIP();
  v5 = ConstructPartialMsgW(
         0x2000000,
         "SetupRecoveryTaskHandler::InternalCallPluginWorker: Unhandled exception while executing the plugin. Plugin: [%s"
         "], Entry Point: [%s]",
         (const char *)(a2 + 768),
         (const char *)(a2 + 240));
  WdsSetupLogMessageW(
    v5,
    0,
    L"D",
    0,
    292,
    L"base\\diagnosis\\srt\\setuprecoverydatatask\\dll\\src\\setuprecoverydatatask.cpp",
    L"SetupRecoveryTaskHandler::InternalCallPluginWorker",
    v4,
    LastError,
    0,
    0);
  return 0;
}

```

## disassembly

```asm
0x18000ca42  mov     [rsp+arg_8], rdx
0x18000ca47  push    rbx
0x18000ca48  push    rbp
0x18000ca49  push    rdi
0x18000ca4a  sub     rsp, 60h
0x18000ca4e  mov     rbp, rdx
0x18000ca51  call    cs:__imp_GetLastError
0x18000ca57  mov     edi, eax
0x18000ca59  call    cs:__imp_CurrentIP
0x18000ca5f  mov     rbx, rax
0x18000ca62  lea     r9, [rbp+0F0h]
0x18000ca69  lea     r8, [rbp+300h]
0x18000ca70  lea     rdx, aSetuprecoveryt_19; "SetupRecoveryTaskHandler::InternalCallP"...
0x18000ca77  mov     ecx, 2000000h; unsigned int
0x18000ca7c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000ca81  mov     [rsp+78h+var_28], 0
0x18000ca89  mov     [rsp+78h+var_30], 0
0x18000ca92  mov     [rsp+78h+var_38], edi
0x18000ca96  mov     [rsp+78h+var_40], rbx
0x18000ca9b  lea     rcx, aSetuprecoveryt_21; "SetupRecoveryTaskHandler::InternalCallP"...
0x18000caa2  mov     [rsp+78h+var_48], rcx
0x18000caa7  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\setuprecoverydata"...
0x18000caae  mov     [rsp+78h+var_50], rcx
0x18000cab3  mov     [rsp+78h+var_58], 124h
0x18000cabb  xor     r9d, r9d
0x18000cabe  lea     r8, aD; "D"
0x18000cac5  xor     edx, edx
0x18000cac7  mov     rcx, rax
0x18000caca  call    cs:__imp_WdsSetupLogMessageW
0x18000cad0  nop
0x18000cad1  mov     rax, 0
0x18000cadb  add     rsp, 60h
0x18000cadf  pop     rdi
0x18000cae0  pop     rbp
0x18000cae1  pop     rbx
0x18000cae2  retn
```
