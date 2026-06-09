# Print::Driver::CPrinterExtensionServer::AttemptDemoteToNormalUserIfElevated(ATL::CAccessToken &)

- ea: `0x18007b608`
- end: `0x18007b745`
- name: `?AttemptDemoteToNormalUserIfElevated@CPrinterExtensionServer@Driver@Print@@AEAAXAEAVCAccessToken@ATL@@@Z`
- size: `317`
- prototype: `void __fastcall(Print::Driver::CPrinterExtensionServer *__hidden this, struct ATL::CAccessToken *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007b8f4`

## callees

- `0x1800183f8`
- `0x18007b608`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007b6d8`
- `KERNEL32!GetLastError` at `0x18007b711`
- `KERNEL32!GetLastError` at `0x18007b6d8`
- `KERNEL32!GetLastError` at `0x18007b711`
- `ADVAPI32!GetTokenInformation` at `0x18007b644`
- `ADVAPI32!GetTokenInformation` at `0x18007b644`
- `ADVAPI32!SaferCreateLevel` at `0x18007b67e`
- `ADVAPI32!SaferCreateLevel` at `0x18007b67e`
- `ADVAPI32!SaferComputeTokenFromLevel` at `0x18007b6ac`
- `ADVAPI32!SaferComputeTokenFromLevel` at `0x18007b6ac`
- `ADVAPI32!SaferCloseLevel` at `0x18007b6f1`
- `ADVAPI32!SaferCloseLevel` at `0x18007b6f1`

## string_xrefs

- `0x18007b703`: `Print::Driver::CPrinterExtensionServer::AttemptDemoteToNormalUserIfElevated`
- `0x18007b730`: `Print::Driver::CPrinterExtensionServer::AttemptDemoteToNormalUserIfElevated`
- `0x18007b729`: `Caller is elevated unable to alter token for Printer Extension. Auto-launch debuggers and gflags will likely fail because Admin group is removed by caller. Error was 0x%x.`
- `0x18007b6fc`: `Caller is elevated token altered to normal user for Printer Extension.`

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
0x18007b608  mov     [rsp-20h+TokenInformation], rcx
0x18007b60d  push    rbp
0x18007b60e  push    rbx
0x18007b60f  push    rsi
0x18007b610  push    rdi
0x18007b611  mov     rbp, rsp
0x18007b614  sub     rsp, 38h
0x18007b618  mov     rsi, rdx
0x18007b61b  mov     dword ptr [rbp+TokenInformation], 0
0x18007b622  mov     r9d, 4; TokenInformationLength
0x18007b628  mov     [rbp+arg_8], 0
0x18007b62f  lea     rax, [rbp+arg_8]
0x18007b633  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18007b637  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18007b63c  mov     rcx, [rsi+8]; TokenHandle
0x18007b640  lea     edx, [r9+0Eh]; TokenInformationClass
0x18007b644  call    cs:__imp_GetTokenInformation
0x18007b64a  mov     ecx, 2; dwScopeId
0x18007b64f  test    eax, eax
0x18007b651  jz      short loc_18007B65C
0x18007b653  cmp     dword ptr [rbp+TokenInformation], ecx
0x18007b656  jnz     loc_18007B73C
0x18007b65c  mov     edi, 1
0x18007b661  mov     [rbp+pLevelHandle], 0
0x18007b669  mov     r8d, edi; OpenFlags
0x18007b66c  mov     [rsp+38h+ReturnLength], 0; lpReserved
0x18007b675  lea     r9, [rbp+pLevelHandle]; pLevelHandle
0x18007b679  mov     edx, 20000h; dwLevelId
0x18007b67e  call    cs:__imp_SaferCreateLevel
0x18007b684  test    eax, eax
0x18007b686  jz      loc_18007B711
0x18007b68c  mov     rdx, [rsi+8]; InAccessToken
0x18007b690  lea     r8, [rbp+OutAccessToken]; OutAccessToken
0x18007b694  mov     rcx, [rbp+pLevelHandle]; LevelHandle
0x18007b698  xor     r9d, r9d; dwFlags
0x18007b69b  mov     [rbp+OutAccessToken], 0
0x18007b6a3  mov     [rsp+38h+ReturnLength], 0; lpReserved
0x18007b6ac  call    cs:__imp_SaferComputeTokenFromLevel
0x18007b6b2  test    eax, eax
0x18007b6b4  jz      short loc_18007B6D5
0x18007b6b6  mov     rax, [rsi]
0x18007b6b9  xor     ebx, ebx
0x18007b6bb  mov     rcx, rsi
0x18007b6be  mov     [rsi+8], rbx
0x18007b6c2  mov     rax, [rax+8]
0x18007b6c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b6cb  mov     rax, [rbp+OutAccessToken]
0x18007b6cf  mov     [rsi+8], rax
0x18007b6d3  jmp     short loc_18007B6ED
0x18007b6d5  xor     dil, dil
0x18007b6d8  call    cs:__imp_GetLastError
0x18007b6de  mov     ebx, eax
0x18007b6e0  test    eax, eax
0x18007b6e2  jle     short loc_18007B6ED
0x18007b6e4  movzx   ebx, ax
0x18007b6e7  or      ebx, 80070000h
0x18007b6ed  mov     rcx, [rbp+pLevelHandle]; hLevelHandle
0x18007b6f1  call    cs:__imp_SaferCloseLevel
0x18007b6f7  test    dil, dil
0x18007b6fa  jz      short loc_18007B726
0x18007b6fc  lea     rdx, aCallerIsElevat; "Caller is elevated token altered to nor"...
0x18007b703  lea     rcx, aPrintDriverCpr_6; "Print::Driver::CPrinterExtensionServer:"...
0x18007b70a  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18007b70f  jmp     short loc_18007B73C
0x18007b711  call    cs:__imp_GetLastError
0x18007b717  mov     ebx, eax
0x18007b719  test    eax, eax
0x18007b71b  jle     short loc_18007B726
0x18007b71d  movzx   ebx, ax
0x18007b720  or      ebx, 80070000h
0x18007b726  mov     r8d, ebx
0x18007b729  lea     rdx, aCallerIsElevat_0; "Caller is elevated unable to alter toke"...
0x18007b730  lea     rcx, aPrintDriverCpr_6; "Print::Driver::CPrinterExtensionServer:"...
0x18007b737  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18007b73c  add     rsp, 38h
0x18007b740  pop     rdi
0x18007b741  pop     rsi
0x18007b742  pop     rbx
0x18007b743  pop     rbp
0x18007b744  retn
```
