# Print::Driver::CPrinterExtensionServer::AttemptDemoteToNormalUserIfElevated(ATL::CAccessToken &)

- ea: `0x18007e25c`
- end: `0x18007e3be`
- name: `?AttemptDemoteToNormalUserIfElevated@CPrinterExtensionServer@Driver@Print@@AEAAXAEAVCAccessToken@ATL@@@Z`
- size: `354`
- prototype: `void __fastcall(Print::Driver::CPrinterExtensionServer *__hidden this, struct ATL::CAccessToken *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007e580`

## callees

- `0x180018f58`
- `0x18007e25c`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007e33e`
- `KERNEL32!GetLastError` at `0x18007e383`
- `KERNEL32!GetLastError` at `0x18007e33e`
- `KERNEL32!GetLastError` at `0x18007e383`
- `ADVAPI32!GetTokenInformation` at `0x18007e298`
- `ADVAPI32!GetTokenInformation` at `0x18007e298`
- `ADVAPI32!SaferCreateLevel` at `0x18007e2d8`
- `ADVAPI32!SaferCreateLevel` at `0x18007e2d8`
- `ADVAPI32!SaferComputeTokenFromLevel` at `0x18007e30c`
- `ADVAPI32!SaferComputeTokenFromLevel` at `0x18007e30c`
- `ADVAPI32!SaferCloseLevel` at `0x18007e35d`
- `ADVAPI32!SaferCloseLevel` at `0x18007e35d`

## string_xrefs

- `0x18007e375`: `Print::Driver::CPrinterExtensionServer::AttemptDemoteToNormalUserIfElevated`
- `0x18007e3a8`: `Print::Driver::CPrinterExtensionServer::AttemptDemoteToNormalUserIfElevated`
- `0x18007e3a1`: `Caller is elevated unable to alter token for Printer Extension. Auto-launch debuggers and gflags will likely fail because Admin group is removed by caller. Error was 0x%x.`
- `0x18007e36e`: `Caller is elevated token altered to normal user for Printer Extension.`

## pseudocode

```c
void __fastcall Print::Driver::CPrinterExtensionServer::AttemptDemoteToNormalUserIfElevated(
        Print::Driver::CPrinterExtensionServer *this,
        struct ATL::CAccessToken *a2)
{
  char v3; // di
  void *v4; // rdx
  __int64 v5; // rax
  unsigned int v6; // ebx
  signed int LastError; // eax
  signed int v8; // eax
  int TokenInformation; // [rsp+60h] [rbp+28h] BYREF
  int TokenInformation_4; // [rsp+64h] [rbp+2Ch]
  DWORD ReturnLength; // [rsp+68h] [rbp+30h] BYREF
  SAFER_LEVEL_HANDLE pLevelHandle; // [rsp+70h] [rbp+38h] BYREF
  HANDLE OutAccessToken; // [rsp+78h] [rbp+40h] BYREF

  TokenInformation_4 = HIDWORD(this);
  TokenInformation = 0;
  ReturnLength = 0;
  if ( !GetTokenInformation(*((HANDLE *)a2 + 1), TokenElevationType, &TokenInformation, 4u, &ReturnLength)
    || TokenInformation == 2 )
  {
    v3 = 1;
    pLevelHandle = 0;
    if ( SaferCreateLevel(2u, 0x20000u, 1u, &pLevelHandle, 0) )
    {
      v4 = (void *)*((_QWORD *)a2 + 1);
      OutAccessToken = 0;
      if ( SaferComputeTokenFromLevel(pLevelHandle, v4, &OutAccessToken, 0, 0) )
      {
        v5 = *(_QWORD *)a2;
        v6 = 0;
        *((_QWORD *)a2 + 1) = 0;
        (*(void (__fastcall **)(struct ATL::CAccessToken *))(v5 + 8))(a2);
        *((_QWORD *)a2 + 1) = OutAccessToken;
      }
      else
      {
        v3 = 0;
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
      }
      SaferCloseLevel(pLevelHandle);
      if ( v3 )
      {
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "Print::Driver::CPrinterExtensionServer::AttemptDemoteToNormalUserIfElevated",
          L"Caller is elevated token altered to normal user for Printer Extension.");
        return;
      }
    }
    else
    {
      v8 = GetLastError();
      v6 = v8;
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
    }
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "Print::Driver::CPrinterExtensionServer::AttemptDemoteToNormalUserIfElevated",
      L"Caller is elevated unable to alter token for Printer Extension. Auto-launch debuggers and gflags will likely fail "
       "because Admin group is removed by caller. Error was 0x%x.",
      v6);
  }
}

```

## disassembly

```asm
0x18007e25c  mov     [rsp-20h+TokenInformation], rcx
0x18007e261  push    rbp
0x18007e262  push    rbx
0x18007e263  push    rsi
0x18007e264  push    rdi
0x18007e265  mov     rbp, rsp
0x18007e268  sub     rsp, 38h
0x18007e26c  mov     rsi, rdx
0x18007e26f  mov     dword ptr [rbp+TokenInformation], 0
0x18007e276  mov     r9d, 4; TokenInformationLength
0x18007e27c  mov     [rbp+arg_8], 0
0x18007e283  lea     rax, [rbp+arg_8]
0x18007e287  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18007e28b  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18007e290  mov     rcx, [rsi+8]; TokenHandle
0x18007e294  lea     edx, [r9+0Eh]; TokenInformationClass
0x18007e298  call    cs:__imp_GetTokenInformation
0x18007e29f  nop     dword ptr [rax+rax+00h]
0x18007e2a4  mov     ecx, 2; dwScopeId
0x18007e2a9  test    eax, eax
0x18007e2ab  jz      short loc_18007E2B6
0x18007e2ad  cmp     dword ptr [rbp+TokenInformation], ecx
0x18007e2b0  jnz     loc_18007E3B4
0x18007e2b6  mov     edi, 1
0x18007e2bb  mov     [rbp+pLevelHandle], 0
0x18007e2c3  mov     r8d, edi; OpenFlags
0x18007e2c6  mov     [rsp+38h+ReturnLength], 0; lpReserved
0x18007e2cf  lea     r9, [rbp+pLevelHandle]; pLevelHandle
0x18007e2d3  mov     edx, 20000h; dwLevelId
0x18007e2d8  call    cs:__imp_SaferCreateLevel
0x18007e2df  nop     dword ptr [rax+rax+00h]
0x18007e2e4  test    eax, eax
0x18007e2e6  jz      loc_18007E383
0x18007e2ec  mov     rdx, [rsi+8]; InAccessToken
0x18007e2f0  lea     r8, [rbp+OutAccessToken]; OutAccessToken
0x18007e2f4  mov     rcx, [rbp+pLevelHandle]; LevelHandle
0x18007e2f8  xor     r9d, r9d; dwFlags
0x18007e2fb  mov     [rbp+OutAccessToken], 0
0x18007e303  mov     [rsp+38h+ReturnLength], 0; lpReserved
0x18007e30c  call    cs:__imp_SaferComputeTokenFromLevel
0x18007e313  nop     dword ptr [rax+rax+00h]
0x18007e318  test    eax, eax
0x18007e31a  jz      short loc_18007E33B
0x18007e31c  mov     rax, [rsi]
0x18007e31f  xor     ebx, ebx
0x18007e321  mov     rcx, rsi
0x18007e324  mov     [rsi+8], rbx
0x18007e328  mov     rax, [rax+8]
0x18007e32c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e331  mov     rax, [rbp+OutAccessToken]
0x18007e335  mov     [rsi+8], rax
0x18007e339  jmp     short loc_18007E359
0x18007e33b  xor     dil, dil
0x18007e33e  call    cs:__imp_GetLastError
0x18007e345  nop     dword ptr [rax+rax+00h]
0x18007e34a  mov     ebx, eax
0x18007e34c  test    eax, eax
0x18007e34e  jle     short loc_18007E359
0x18007e350  movzx   ebx, ax
0x18007e353  or      ebx, 80070000h
0x18007e359  mov     rcx, [rbp+pLevelHandle]; hLevelHandle
0x18007e35d  call    cs:__imp_SaferCloseLevel
0x18007e364  nop     dword ptr [rax+rax+00h]
0x18007e369  test    dil, dil
0x18007e36c  jz      short loc_18007E39E
0x18007e36e  lea     rdx, aCallerIsElevat; "Caller is elevated token altered to nor"...
0x18007e375  lea     rcx, aPrintDriverCpr_6; "Print::Driver::CPrinterExtensionServer:"...
0x18007e37c  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18007e381  jmp     short loc_18007E3B4
0x18007e383  call    cs:__imp_GetLastError
0x18007e38a  nop     dword ptr [rax+rax+00h]
0x18007e38f  mov     ebx, eax
0x18007e391  test    eax, eax
0x18007e393  jle     short loc_18007E39E
0x18007e395  movzx   ebx, ax
0x18007e398  or      ebx, 80070000h
0x18007e39e  mov     r8d, ebx
0x18007e3a1  lea     rdx, aCallerIsElevat_0; "Caller is elevated unable to alter toke"...
0x18007e3a8  lea     rcx, aPrintDriverCpr_6; "Print::Driver::CPrinterExtensionServer:"...
0x18007e3af  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18007e3b4  add     rsp, 38h
0x18007e3b8  pop     rdi
0x18007e3b9  pop     rsi
0x18007e3ba  pop     rbx
0x18007e3bb  pop     rbp
0x18007e3bc  retn
```
