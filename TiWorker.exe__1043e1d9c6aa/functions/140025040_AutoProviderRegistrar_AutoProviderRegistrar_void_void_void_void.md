# AutoProviderRegistrar::AutoProviderRegistrar(void (*)(void),void (*)(void))

- ea: `0x140025040`
- end: `0x140025222`
- name: `??0AutoProviderRegistrar@@QEAA@P6AXXZ0@Z`
- size: `482`
- prototype: `AutoProviderRegistrar *__fastcall(AutoProviderRegistrar *__hidden this, void (*)(void), void (*)(void))`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001f50`

## callees

- `0x140002310`
- `0x140002cf8`
- `0x140025040`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x14002510f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x14002512b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140025147`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x14002510f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x14002512b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140025147`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1400250de`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1400250f7`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1400250de`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1400250f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1400250a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1400250a7`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1400251f4`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1400251f4`

## string_xrefs

- `0x1400250f0`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x1400250d7`: `advapi32.dll`
- `0x140025105`: `EventWrite`

## pseudocode

```c
AutoProviderRegistrar *__fastcall AutoProviderRegistrar::AutoProviderRegistrar(
        AutoProviderRegistrar *this,
        void (*a2)(void),
        void (*a3)(void))
{
  int v3; // edi
  HMODULE ModuleHandleW; // rbx
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-148h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-138h] BYREF

  g_ProviderRegistrationMicrosoft_Windows_Deplorch = AutoUnregisterMicrosoft_Windows_Deplorch;
  if ( !Microsoft_Windows_Deplorch_Context )
  {
    memset_0(&VersionInformation, 0, sizeof(VersionInformation));
    if ( McGenTracingSupportInit )
      goto LABEL_18;
    VersionInformation.dwOSVersionInfoSize = 276;
    v3 = 0;
    if ( !GetVersionExW(&VersionInformation) )
      goto LABEL_9;
    McGenPreVista = VersionInformation.dwMajorVersion < 6;
    if ( VersionInformation.dwMajorVersion > 6
      || VersionInformation.dwMajorVersion == 6 && VersionInformation.dwMinorVersion > 1 )
    {
      v3 = 1;
    }
    if ( VersionInformation.dwMajorVersion >= 6 )
    {
LABEL_9:
      ModuleHandleW = GetModuleHandleW(L"advapi32.dll");
      if ( ModuleHandleW || v3 && (ModuleHandleW = GetModuleHandleW(L"api-ms-win-eventing-provider-l1-1-0.dll")) != 0 )
      {
        PfnEventWrite = (__int64)GetProcAddress(ModuleHandleW, "EventWrite");
        if ( PfnEventWrite )
        {
          PfnEventRegister = (__int64 (__fastcall *)(LPCGUID, WMIDPREQUEST, PTRACEHANDLE))GetProcAddress(
                                                                                            ModuleHandleW,
                                                                                            "EventRegister");
          if ( PfnEventRegister )
          {
            PfnEventUnregister = (__int64)GetProcAddress(ModuleHandleW, "EventUnregister");
            if ( PfnEventUnregister )
              goto LABEL_17;
          }
          PfnEventRegister = McGenEventTracingRegister;
        }
      }
      McGenPreVista = 1;
    }
LABEL_17:
    McGenTracingSupportInit = 1;
LABEL_18:
    if ( McGenPreVista )
    {
      Microsoft_Windows_Deplorch_Context = (ULONG64)&Microsoft_Windows_Deplorch_Context;
      TraceGuidReg.Guid = &Microsoft_Windows_Deplorch;
      TraceGuidReg.RegHandle = 0;
      RegisterTraceGuidsW(
        McGenControlCallback,
        &Microsoft_Windows_Deplorch_Context,
        &Microsoft_Windows_Deplorch,
        1u,
        &TraceGuidReg,
        0,
        0,
        &Microsoft_Windows_Deplorch_Context);
    }
    else
    {
      ((void (__fastcall *)(const GUID *, __int64 (__fastcall *)(int, int, int, int, __int64, int, __int64), ULONG64 *, ULONG64 *))PfnEventRegister)(
        &Microsoft_Windows_Deplorch,
        McGenControlCallbackV2,
        &Microsoft_Windows_Deplorch_Context,
        &Microsoft_Windows_Deplorch_Context);
    }
  }
  return (AutoProviderRegistrar *)&g_ProviderRegistrationMicrosoft_Windows_Deplorch;
}

```

## disassembly

```asm
0x140025040  mov     [rsp+arg_0], rbx
0x140025045  push    rdi
0x140025046  sub     rsp, 180h
0x14002504d  mov     rax, cs:__security_cookie
0x140025054  xor     rax, rsp
0x140025057  mov     [rsp+188h+var_18], rax
0x14002505f  cmp     cs:Microsoft_Windows_Deplorch_Context, 0
0x140025067  lea     rax, AutoUnregisterMicrosoft_Windows_Deplorch
0x14002506e  mov     cs:g_ProviderRegistrationMicrosoft_Windows_Deplorch, rax
0x140025075  jnz     loc_1400251FA
0x14002507b  mov     ebx, 114h
0x140025080  lea     rcx, [rsp+188h+VersionInformation]; void *
0x140025085  mov     r8d, ebx; Size
0x140025088  xor     edx, edx; Val
0x14002508a  call    memset_0
0x14002508f  cmp     cs:McGenTracingSupportInit, 0
0x140025096  jnz     loc_140025175
0x14002509c  lea     rcx, [rsp+188h+VersionInformation]; lpVersionInformation
0x1400250a1  mov     [rsp+188h+VersionInformation.dwOSVersionInfoSize], ebx
0x1400250a5  xor     edi, edi
0x1400250a7  call    cs:__imp_GetVersionExW
0x1400250ad  test    eax, eax
0x1400250af  jz      short loc_1400250D7
0x1400250b1  cmp     [rsp+188h+VersionInformation.dwMajorVersion], 6
0x1400250b6  setb    cl
0x1400250b9  mov     cs:McGenPreVista, cl
0x1400250bf  ja      short loc_1400250CA
0x1400250c1  jnz     short loc_1400250CF
0x1400250c3  cmp     [rsp+188h+VersionInformation.dwMinorVersion], 1
0x1400250c8  jbe     short loc_1400250CF
0x1400250ca  mov     edi, 1
0x1400250cf  test    cl, cl
0x1400250d1  jnz     loc_14002516E
0x1400250d7  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1400250de  call    cs:__imp_GetModuleHandleW
0x1400250e4  mov     rbx, rax
0x1400250e7  test    rax, rax
0x1400250ea  jnz     short loc_140025105
0x1400250ec  test    edi, edi
0x1400250ee  jz      short loc_140025167
0x1400250f0  lea     rcx, ModuleName; "api-ms-win-eventing-provider-l1-1-0.dll"
0x1400250f7  call    cs:__imp_GetModuleHandleW
0x1400250fd  mov     rbx, rax
0x140025100  test    rax, rax
0x140025103  jz      short loc_140025167
0x140025105  lea     rdx, aEventwrite; "EventWrite"
0x14002510c  mov     rcx, rbx; hModule
0x14002510f  call    cs:__imp_GetProcAddress
0x140025115  mov     cs:PfnEventWrite, rax
0x14002511c  test    rax, rax
0x14002511f  jz      short loc_140025167
0x140025121  lea     rdx, aEventregister; "EventRegister"
0x140025128  mov     rcx, rbx; hModule
0x14002512b  call    cs:__imp_GetProcAddress
0x140025131  mov     cs:PfnEventRegister, rax
0x140025138  test    rax, rax
0x14002513b  jz      short loc_140025159
0x14002513d  lea     rdx, aEventunregiste; "EventUnregister"
0x140025144  mov     rcx, rbx; hModule
0x140025147  call    cs:__imp_GetProcAddress
0x14002514d  mov     cs:PfnEventUnregister, rax
0x140025154  test    rax, rax
0x140025157  jnz     short loc_14002516E
0x140025159  lea     rax, McGenEventTracingRegister
0x140025160  mov     cs:PfnEventRegister, rax
0x140025167  mov     cs:McGenPreVista, 1
0x14002516e  mov     cs:McGenTracingSupportInit, 1
0x140025175  cmp     cs:McGenPreVista, 0
0x14002517c  lea     rdx, Microsoft_Windows_Deplorch_Context; RequestContext
0x140025183  jnz     short loc_1400251A7
0x140025185  mov     rax, cs:PfnEventRegister
0x14002518c  lea     rcx, Microsoft_Windows_Deplorch
0x140025193  mov     r9, rdx
0x140025196  mov     r8, rdx
0x140025199  lea     rdx, McGenControlCallbackV2
0x1400251a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400251a5  jmp     short loc_1400251FA
0x1400251a7  mov     [rsp+188h+RegistrationHandle], rdx; RegistrationHandle
0x1400251ac  lea     rax, Microsoft_Windows_Deplorch
0x1400251b3  mov     [rsp+188h+MofResourceName], 0; MofResourceName
0x1400251bc  lea     rcx, [rsp+188h+var_148]
0x1400251c1  mov     [rsp+188h+MofImagePath], 0; MofImagePath
0x1400251ca  mov     r9d, 1; GuidCount
0x1400251d0  mov     [rsp+188h+TraceGuidReg], rcx; TraceGuidReg
0x1400251d5  mov     r8, rax; ControlGuid
0x1400251d8  lea     rcx, McGenControlCallback; RequestAddress
0x1400251df  mov     cs:Microsoft_Windows_Deplorch_Context, rdx
0x1400251e6  mov     [rsp+188h+var_148.Guid], rax
0x1400251eb  mov     [rsp+188h+var_148.RegHandle], 0
0x1400251f4  call    cs:__imp_RegisterTraceGuidsW
0x1400251fa  lea     rax, g_ProviderRegistrationMicrosoft_Windows_Deplorch
0x140025201  mov     rcx, [rsp+188h+var_18]
0x140025209  xor     rcx, rsp; StackCookie
0x14002520c  call    __security_check_cookie
0x140025211  mov     rbx, [rsp+188h+arg_0]
0x140025219  add     rsp, 180h
0x140025220  pop     rdi
0x140025221  retn
```
