# InitializeService(ulong,ushort * * const)

- ea: `0x18000c694`
- end: `0x18000c836`
- name: `?InitializeService@@YAJKQEAPEAG@Z`
- size: `418`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 **const, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c8e0`

## callees

- `0x180003a60`
- `0x18000becc`
- `0x18000c694`
- `0x18000cf90`
- `0x180017648`
- `0x180051420`
- `0x180051628`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c721`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c721`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c809`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c809`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000c6db`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000c73c`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000c6db`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000c73c`
- `ntdll!RtlPublishWnfStateData` at `0x18000c7cf`
- `ntdll!RtlPublishWnfStateData` at `0x18000c7cf`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18000c6fe`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18000c6fe`

## string_xrefs

- `0x18000c6ec`: `OSDATA\System\Services\SmsRouter\State`
- `0x18000c6f7`: `SYSTEM\CurrentControlSet\Services\SmsRouter\State`
- `0x18000c745`: `SmsRouter: Failed to get global registry handle (StateSeparation = %d)`
- `0x18000c758`: `InitializeService`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall InitializeService(__int64 a1, unsigned __int16 **const a2, __int64 a3)
{
  char IsStateSeparationEnabled; // al
  const WCHAR *v4; // rdx
  LSTATUS v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  signed int v8; // ebx
  HKEY v9; // rcx
  unsigned __int8 v10; // al
  unsigned int v11; // edx
  struct SmsRouterRpcInterface *v12; // rcx
  void **v13; // r8
  int v14; // eax
  LSTATUS v15; // eax
  int v16; // ecx
  bool v17; // zf
  __int64 result; // rax
  BYTE Data[8]; // [rsp+30h] [rbp-30h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v22[16]; // [rsp+48h] [rbp-18h] BYREF

  phkResult = 0;
  if ( (Microsoft_Windows_CoreSystem_SmsRouterEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, "d", a3, 1, v22);
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1, a2);
  v4 = L"OSDATA\\System\\Services\\SmsRouter\\State";
  if ( !IsStateSeparationEnabled )
    v4 = L"SYSTEM\\CurrentControlSet\\Services\\SmsRouter\\State";
  v5 = RegCreateKeyW(HKEY_LOCAL_MACHINE, v4, &phkResult);
  v8 = v5;
  if ( !v5 )
  {
    v9 = g_SmsRouterKey;
    g_SmsRouterKey = phkResult;
    if ( v9 )
      RegCloseKey(v9);
    phkResult = 0;
LABEL_12:
    v8 = CSmsServiceManager::Startup();
    if ( v8 >= 0 )
    {
      v14 = RegisterRPCInterfaceGroup(v12, v11, v13);
      v8 = v14;
      if ( v14 >= 0 )
      {
        LogSmsRouterInfo("RegisterSmsRouterRPCInterface", 0x42u, "RegisterRPCInterfaceGroup succeeded.");
        *(_DWORD *)Data = 1;
        RtlPublishWnfStateData(WNF_SMSR_READY, 0, Data, 4, 0);
      }
      else
      {
        LogSmsRouterError("RegisterSmsRouterRPCInterface", 0x3Eu, v14, "RegisterRPCInterfaceGroup failed.");
      }
    }
    goto LABEL_16;
  }
  if ( v5 > 0 )
    v8 = (unsigned __int16)v5 | 0x80070000;
  v10 = RtlIsStateSeparationEnabled(v7, v6);
  LogSmsRouterError(
    "InitializeService",
    0x90u,
    v8,
    "SmsRouter: Failed to get global registry handle (StateSeparation = %d)",
    v10);
  if ( v8 >= 0 )
    goto LABEL_12;
LABEL_16:
  *(_DWORD *)Data = 0;
  cbData = 4;
  v15 = RegQueryValueExW(g_SmsRouterKey, L"LogPduData", 0, 0, Data, &cbData);
  v16 = 0;
  v17 = v15 == 0;
  result = (unsigned int)v8;
  if ( v17 )
    v16 = *(_DWORD *)Data;
  g_fLogPduData = v16;
  return result;
}

```

## disassembly

```asm
0x18000c694  mov     [rsp-8+arg_0], rbx
0x18000c699  push    rbp
0x18000c69a  mov     rbp, rsp
0x18000c69d  sub     rsp, 60h
0x18000c6a1  mov     rax, cs:__security_cookie
0x18000c6a8  xor     rax, rsp
0x18000c6ab  mov     [rbp+var_8], rax
0x18000c6af  test    cs:Microsoft_Windows_CoreSystem_SmsRouterEnableBits, 1
0x18000c6b6  mov     [rbp+phkResult], 0
0x18000c6be  jz      short loc_18000C6DB
0x18000c6c0  lea     rax, [rbp+var_18]
0x18000c6c4  mov     r9d, 1
0x18000c6ca  lea     rdx, SmsRouter_Start; "d"
0x18000c6d1  mov     [rsp+60h+lpData], rax
0x18000c6d6  call    McGenEventWrite_EventWriteTransfer
0x18000c6db  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000c6e1  lea     r8, [rbp+phkResult]; phkResult
0x18000c6e5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c6ec  lea     rdx, aOsdataSystemSe; "OSDATA\\System\\Services\\SmsRouter\\St"...
0x18000c6f3  test    al, al
0x18000c6f5  jnz     short loc_18000C6FE
0x18000c6f7  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Sm"...
0x18000c6fe  call    cs:__imp_RegCreateKeyW
0x18000c704  mov     ebx, eax
0x18000c706  test    eax, eax
0x18000c708  jnz     short loc_18000C731
0x18000c70a  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hKey
0x18000c711  mov     rax, [rbp+phkResult]
0x18000c715  mov     cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A, rax; Windows::Sms::Common::__AutoHandle<HKEY__ *,Windows::Sms::Common::RegkeyDeleter> g_SmsRouterKey
0x18000c71c  test    rcx, rcx
0x18000c71f  jz      short loc_18000C727
0x18000c721  call    cs:__imp_RegCloseKey
0x18000c727  mov     [rbp+phkResult], 0
0x18000c72f  jmp     short loc_18000C768
0x18000c731  jle     short loc_18000C73C
0x18000c733  movzx   ebx, bx
0x18000c736  or      ebx, 80070000h
0x18000c73c  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000c742  movzx   eax, al
0x18000c745  lea     r9, aSmsrouterFaile; "SmsRouter: Failed to get global registr"...
0x18000c74c  mov     r8d, ebx; int
0x18000c74f  mov     dword ptr [rsp+60h+lpData], eax
0x18000c753  mov     edx, 90h; unsigned int
0x18000c758  lea     rcx, aInitializeserv; "InitializeService"
0x18000c75f  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18000c764  test    ebx, ebx
0x18000c766  js      short loc_18000C7D5
0x18000c768  call    ?Startup@CSmsServiceManager@@SAJXZ; CSmsServiceManager::Startup(void)
0x18000c76d  mov     ebx, eax
0x18000c76f  test    eax, eax
0x18000c771  js      short loc_18000C7D5
0x18000c773  call    ?RegisterRPCInterfaceGroup@@YAJQEAUSmsRouterRpcInterface@@KPEAPEAX@Z; RegisterRPCInterfaceGroup(SmsRouterRpcInterface * const,ulong,void * *)
0x18000c778  lea     rcx, aRegistersmsrou; "RegisterSmsRouterRPCInterface"
0x18000c77f  mov     ebx, eax
0x18000c781  test    eax, eax
0x18000c783  jns     short loc_18000C79B
0x18000c785  lea     r9, aRegisterrpcint; "RegisterRPCInterfaceGroup failed."
0x18000c78c  mov     r8d, eax; int
0x18000c78f  mov     edx, 3Eh ; '>'; unsigned int
0x18000c794  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18000c799  jmp     short loc_18000C7D5
0x18000c79b  lea     r8, aRegisterrpcint_0; "RegisterRPCInterfaceGroup succeeded."
0x18000c7a2  mov     edx, 42h ; 'B'; unsigned int
0x18000c7a7  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18000c7ac  mov     rcx, cs:WNF_SMSR_READY
0x18000c7b3  lea     r8, [rbp+Data]
0x18000c7b7  mov     r9d, 4
0x18000c7bd  mov     dword ptr [rbp+Data], 1
0x18000c7c4  xor     edx, edx
0x18000c7c6  mov     [rsp+60h+lpData], 0
0x18000c7cf  call    cs:__imp_RtlPublishWnfStateData
0x18000c7d5  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hKey
0x18000c7dc  lea     rax, [rbp+cbData]
0x18000c7e0  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18000c7e5  lea     rdx, aLogpdudata; "LogPduData"
0x18000c7ec  lea     rax, [rbp+Data]
0x18000c7f0  mov     dword ptr [rbp+Data], 0
0x18000c7f7  xor     r9d, r9d; lpType
0x18000c7fa  mov     [rsp+60h+lpData], rax; lpData
0x18000c7ff  xor     r8d, r8d; lpReserved
0x18000c802  mov     [rbp+cbData], 4
0x18000c809  call    cs:__imp_RegQueryValueExW
0x18000c80f  xor     ecx, ecx
0x18000c811  test    eax, eax
0x18000c813  mov     eax, ebx
0x18000c815  cmovz   ecx, dword ptr [rbp+Data]
0x18000c819  mov     cs:?g_fLogPduData@@3HA, ecx; int g_fLogPduData
0x18000c81f  mov     rcx, [rbp+var_8]
0x18000c823  xor     rcx, rsp; StackCookie
0x18000c826  call    __security_check_cookie
0x18000c82b  mov     rbx, [rsp+60h+arg_0]
0x18000c830  add     rsp, 60h
0x18000c834  pop     rbp
0x18000c835  retn
```
