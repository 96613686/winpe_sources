# wWinMain

- ea: `0x14000215c`
- end: `0x1400023d3`
- name: `wWinMain`
- size: `631`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140005380`

## callees

- `0x14000215c`
- `0x140002e6c`
- `0x140002f10`
- `0x140002fbc`
- `0x1400031e0`
- `0x140003350`
- `0x140003480`
- `0x140004254`
- `0x1400047a4`
- `0x1400066e4`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_set_error_mode` at `0x140002176`
- `api-ms-win-crt-runtime-l1-1-0!_set_error_mode` at `0x140002176`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerSetFlags` at `0x140002247`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerSetFlags` at `0x140002247`
- `api-ms-win-core-windowserrorreporting-l1-1-3!WerSetMaxProcessHoldMilliseconds` at `0x140002264`
- `api-ms-win-core-windowserrorreporting-l1-1-3!WerSetMaxProcessHoldMilliseconds` at `0x140002264`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x140002290`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x140002290`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400021ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000227e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400021ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000227e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002202`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000229a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002202`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000229a`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14000223c`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14000223c`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x14000218f`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x14000218f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140002181`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140002181`
- `ntdll!NtSetInformationProcess` at `0x1400021ab`
- `ntdll!NtSetInformationProcess` at `0x1400021de`
- `ntdll!NtSetInformationProcess` at `0x1400021ab`
- `ntdll!NtSetInformationProcess` at `0x1400021de`
- `dxgi!DXGIDeclareAdapterRemovalSupport` at `0x1400022cf`
- `dxgi!DXGIDeclareAdapterRemovalSupport` at `0x1400022cf`
- `ext-ms-win-imm-l1-1-0!ImmDisableIME` at `0x1400021f8`
- `ext-ms-win-imm-l1-1-0!ImmDisableIME` at `0x1400021f8`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  HANDLE CurrentProcess; // rax
  __int64 v6; // rdx
  signed int LastError; // eax
  signed int v8; // ebx
  HRESULT v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  HRESULT v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rdx
  CDwmAppHost *v15; // rcx
  CDwmAppHost *v16; // rcx
  CDwmAppHost *v17; // rcx
  int v18; // r9d
  unsigned int v20; // [rsp+20h] [rbp-28h]
  int ProcessInformation; // [rsp+30h] [rbp-18h] BYREF
  _DWORD v22[4]; // [rsp+38h] [rbp-10h] BYREF

  ProcessInformation = 1;
  _set_error_mode(1);
  ModifyTokenPrivileges();
  CurrentProcess = GetCurrentProcess();
  SetPriorityClass(CurrentProcess, 0x80u);
  NtSetInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessCycleTime|ProcessUserModeIOPL, &ProcessInformation, 4u);
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DwmHandleTracing>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DwmHandleTracing>::GetImpl'::`2'::impl,
    v6);
  v22[0] = 0;
  v22[1] = 0x2000;
  NtSetInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessHandleTracing, v22, 8u);
  if ( (unsigned __int8)IsImmDisableIMEPresent() )
  {
    SetLastError(0);
    if ( !ImmDisableIME(0xFFFFFFFF) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      v20 = 151;
      if ( v8 >= 0 )
        v8 = -2003304445;
      goto LABEL_31;
    }
  }
  SetErrorMode(0xC001u);
  v9 = WerSetFlags(0x20u);
  v8 = 0;
  if ( v9 != -2147467263 )
    v8 = v9;
  if ( v8 < 0 )
  {
    v20 = 167;
    goto LABEL_31;
  }
  v10 = WerSetMaxProcessHoldMilliseconds(5000);
  v8 = 0;
  if ( v10 != -2147467263 )
    v8 = v10;
  if ( v8 < 0 )
  {
    v20 = 171;
LABEL_31:
    v18 = v8;
    goto LABEL_32;
  }
  SetLastError(0);
  if ( !HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0) )
  {
    v11 = GetLastError();
    v8 = v11;
    if ( v11 > 0 )
      v8 = (unsigned __int16)v11 | 0x80070000;
    v20 = 181;
    if ( v8 >= 0 )
      v8 = -2003304445;
    goto LABEL_31;
  }
  v12 = DXGIDeclareAdapterRemovalSupport();
  v8 = v12;
  if ( v12 < 0 )
  {
    v20 = 184;
    goto LABEL_25;
  }
  McGenEventRegister_EtwEventRegister(
    Microsoft_Windows_Dwm_Dwm_Provider,
    v13,
    &Microsoft_Windows_Dwm_Dwm_Provider_Context,
    &Microsoft_Windows_Dwm_Dwm_Provider_Context);
  McGenEventRegister_EtwEventRegister(
    WERSVC_TRIGGER_PROVIDER_GUID,
    v14,
    WERSVC_TRIGGER_PROVIDER_GUID_Context,
    WERSVC_TRIGGER_PROVIDER_GUID_Context);
  v12 = CheckForDwmGroupSid();
  v8 = v12;
  if ( v12 < 0 )
  {
    v20 = 190;
    goto LABEL_25;
  }
  v12 = CDwmAppHost::Initialize(v15, hInstance);
  v8 = v12;
  if ( v12 < 0 )
  {
    v20 = 192;
    goto LABEL_25;
  }
  v12 = CDwmAppHost::Run(v16);
  v8 = v12;
  if ( v12 < 0 )
  {
    v20 = 194;
LABEL_25:
    v18 = v12;
LABEL_32:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1400120A8, 5u, v18, v20, 0);
  }
  CDwmAppHost::Shutdown(v17, v8);
  return v8;
}

```

## disassembly

```asm
0x14000215c  mov     [rsp+arg_0], rbx
0x140002161  push    rdi
0x140002162  sub     rsp, 40h
0x140002166  mov     rdi, rcx
0x140002169  mov     [rsp+48h+ProcessInformation], 1
0x140002171  mov     ecx, 1; Mode
0x140002176  call    cs:__imp__set_error_mode
0x14000217c  call    ?ModifyTokenPrivileges@@YAJXZ; ModifyTokenPrivileges(void)
0x140002181  call    cs:__imp_GetCurrentProcess
0x140002187  mov     rcx, rax; hProcess
0x14000218a  mov     edx, 80h; dwPriorityClass
0x14000218f  call    cs:__imp_SetPriorityClass
0x140002195  mov     r9d, 4; ProcessInformationLength
0x14000219b  lea     r8, [rsp+48h+ProcessInformation]; ProcessInformation
0x1400021a0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400021a4  mov     rcx, rbx; ProcessHandle
0x1400021a7  lea     edx, [r9+32h]; ProcessInformationClass
0x1400021ab  call    cs:__imp_NtSetInformationProcess
0x1400021b1  mov     dl, 1
0x1400021b3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DwmHandleTracing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DwmHandleTracing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DwmHandleTracing> `wil::Feature<__WilFeatureTraits_Feature_DwmHandleTracing>::GetImpl(void)'::`2'::impl
0x1400021ba  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DwmHandleTracing@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DwmHandleTracing>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1400021bf  lea     r9d, [rbx+9]; ProcessInformationLength
0x1400021c3  mov     [rsp+48h+var_10], 0
0x1400021cb  lea     r8, [rsp+48h+var_10]; ProcessInformation
0x1400021d0  mov     [rsp+48h+var_C], 2000h
0x1400021d8  lea     edx, [rbx+21h]; ProcessInformationClass
0x1400021db  mov     rcx, rbx; ProcessHandle
0x1400021de  call    cs:__imp_NtSetInformationProcess
0x1400021e4  call    IsImmDisableIMEPresent
0x1400021e9  test    al, al
0x1400021eb  jz      short loc_140002237
0x1400021ed  xor     ecx, ecx; dwErrCode
0x1400021ef  call    cs:__imp_SetLastError
0x1400021f5  or      ecx, 0FFFFFFFFh; DWORD
0x1400021f8  call    cs:__imp_ImmDisableIME
0x1400021fe  test    eax, eax
0x140002200  jnz     short loc_140002237
0x140002202  call    cs:__imp_GetLastError
0x140002208  mov     ebx, eax
0x14000220a  test    eax, eax
0x14000220c  jle     short loc_140002217
0x14000220e  movzx   ebx, ax
0x140002211  or      ebx, 80070000h
0x140002217  test    ebx, ebx
0x140002219  mov     [rsp+48h+var_20], 0
0x140002222  mov     eax, 88980003h
0x140002227  mov     [rsp+48h+var_28], 97h
0x14000222f  cmovns  ebx, eax
0x140002232  jmp     loc_1400023A6
0x140002237  mov     ecx, 0C001h; uMode
0x14000223c  call    cs:__imp_SetErrorMode
0x140002242  mov     ecx, 20h ; ' '; dwFlags
0x140002247  call    cs:__imp_WerSetFlags
0x14000224d  xor     ebx, ebx
0x14000224f  cmp     eax, 80004001h
0x140002254  cmovnz  ebx, eax
0x140002257  test    ebx, ebx
0x140002259  js      loc_140002395
0x14000225f  mov     ecx, 1388h
0x140002264  call    cs:__imp_WerSetMaxProcessHoldMilliseconds
0x14000226a  xor     ebx, ebx
0x14000226c  cmp     eax, 80004001h
0x140002271  cmovnz  ebx, eax
0x140002274  test    ebx, ebx
0x140002276  js      loc_140002382
0x14000227c  xor     ecx, ecx; dwErrCode
0x14000227e  call    cs:__imp_SetLastError
0x140002284  xor     r9d, r9d; HeapInformationLength
0x140002287  xor     r8d, r8d; HeapInformation
0x14000228a  xor     ecx, ecx; HeapHandle
0x14000228c  lea     edx, [r9+1]; HeapInformationClass
0x140002290  call    cs:__imp_HeapSetInformation
0x140002296  test    eax, eax
0x140002298  jnz     short loc_1400022CF
0x14000229a  call    cs:__imp_GetLastError
0x1400022a0  mov     ebx, eax
0x1400022a2  test    eax, eax
0x1400022a4  jle     short loc_1400022AF
0x1400022a6  movzx   ebx, ax
0x1400022a9  or      ebx, 80070000h
0x1400022af  test    ebx, ebx
0x1400022b1  mov     [rsp+48h+var_20], 0
0x1400022ba  mov     eax, 88980003h
0x1400022bf  mov     [rsp+48h+var_28], 0B5h
0x1400022c7  cmovns  ebx, eax
0x1400022ca  jmp     loc_1400023A6
0x1400022cf  call    cs:__imp_DXGIDeclareAdapterRemovalSupport
0x1400022d5  mov     ebx, eax
0x1400022d7  test    eax, eax
0x1400022d9  js      loc_14000236F
0x1400022df  lea     r8, Microsoft_Windows_Dwm_Dwm_Provider_Context
0x1400022e6  mov     r9, r8
0x1400022e9  lea     rcx, Microsoft_Windows_Dwm_Dwm_Provider
0x1400022f0  call    McGenEventRegister_EtwEventRegister
0x1400022f5  lea     r8, WERSVC_TRIGGER_PROVIDER_GUID_Context
0x1400022fc  mov     r9, r8
0x1400022ff  lea     rcx, WERSVC_TRIGGER_PROVIDER_GUID
0x140002306  call    McGenEventRegister_EtwEventRegister
0x14000230b  call    ?CheckForDwmGroupSid@@YAJXZ; CheckForDwmGroupSid(void)
0x140002310  mov     ebx, eax
0x140002312  test    eax, eax
0x140002314  js      short loc_14000235C
0x140002316  mov     rdx, rdi; HINSTANCE
0x140002319  call    ?Initialize@CDwmAppHost@@QEAAJPEAUHINSTANCE__@@@Z; CDwmAppHost::Initialize(HINSTANCE__ *)
0x14000231e  mov     ebx, eax
0x140002320  test    eax, eax
0x140002322  js      short loc_140002349
0x140002324  call    ?Run@CDwmAppHost@@QEAAJXZ; CDwmAppHost::Run(void)
0x140002329  mov     ebx, eax
0x14000232b  test    eax, eax
0x14000232d  jns     loc_1400023BF
0x140002333  mov     [rsp+48h+var_20], 0
0x14000233c  mov     [rsp+48h+var_28], 0C2h
0x140002344  mov     r9d, eax
0x140002347  jmp     short loc_1400023A9
0x140002349  mov     [rsp+48h+var_20], 0
0x140002352  mov     [rsp+48h+var_28], 0C0h
0x14000235a  jmp     short loc_140002344
0x14000235c  mov     [rsp+48h+var_20], 0
0x140002365  mov     [rsp+48h+var_28], 0BEh
0x14000236d  jmp     short loc_140002344
0x14000236f  mov     [rsp+48h+var_20], 0
0x140002378  mov     [rsp+48h+var_28], 0B8h
0x140002380  jmp     short loc_140002344
0x140002382  mov     [rsp+48h+var_20], 0
0x14000238b  mov     [rsp+48h+var_28], 0ABh
0x140002393  jmp     short loc_1400023A6
0x140002395  mov     [rsp+48h+var_20], 0; void *
0x14000239e  mov     [rsp+48h+var_28], 0A7h; unsigned int
0x1400023a6  mov     r9d, ebx; int
0x1400023a9  mov     r8d, 5; unsigned int
0x1400023af  lea     rdx, qword_1400120A8; int *
0x1400023b6  lea     ecx, [r8+0Fh]; unsigned int
0x1400023ba  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1400023bf  mov     edx, ebx; int
0x1400023c1  call    ?Shutdown@CDwmAppHost@@QEAAXJ@Z; CDwmAppHost::Shutdown(long)
0x1400023c6  mov     eax, ebx
0x1400023c8  mov     rbx, [rsp+48h+arg_0]
0x1400023cd  add     rsp, 40h
0x1400023d1  pop     rdi
0x1400023d2  retn
```
