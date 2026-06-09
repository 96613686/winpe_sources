# McGenEventTracingRegister

- ea: `0x1400254f0`
- end: `0x1400256d8`
- name: `McGenEventTracingRegister`
- size: `488`
- prototype: `__int64 __fastcall(LPCGUID ControlGuid, WMIDPREQUEST RequestAddress, PTRACEHANDLE RegistrationHandle)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140002310`
- `0x140002cf8`
- `0x1400254f0`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400255c6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400255e2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400255fe`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400255c6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400255e2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400255fe`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x140025595`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1400255ae`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x140025595`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1400255ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x14002555e`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x14002555e`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1400256b2`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1400256b2`

## string_xrefs

- `0x1400255a7`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x14002558e`: `advapi32.dll`
- `0x1400255bc`: `EventWrite`

## pseudocode

```c
ULONG __fastcall McGenEventTracingRegister(
        LPCGUID ControlGuid,
        WMIDPREQUEST RequestAddress,
        PTRACEHANDLE RegistrationHandle,
        _QWORD *a4)
{
  ULONG result; // eax
  int v9; // edi
  HMODULE ModuleHandleW; // rbx
  ULONG (__stdcall *v11)(WMIDPREQUESTCODE, PVOID, ULONG *, PVOID); // rdx
  ULONG (__stdcall *v12)(WMIDPREQUESTCODE, PVOID, ULONG *, PVOID); // rcx
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-178h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-168h] BYREF

  if ( !a4 )
    return 87;
  result = 0;
  if ( *a4 )
    return result;
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  if ( McGenTracingSupportInit )
    goto LABEL_19;
  VersionInformation.dwOSVersionInfoSize = 276;
  v9 = 0;
  if ( !GetVersionExW(&VersionInformation) )
    goto LABEL_10;
  McGenPreVista = VersionInformation.dwMajorVersion < 6;
  if ( VersionInformation.dwMajorVersion > 6
    || VersionInformation.dwMajorVersion == 6 && VersionInformation.dwMinorVersion > 1 )
  {
    v9 = 1;
  }
  if ( VersionInformation.dwMajorVersion >= 6 )
  {
LABEL_10:
    ModuleHandleW = GetModuleHandleW(L"advapi32.dll");
    if ( ModuleHandleW || v9 && (ModuleHandleW = GetModuleHandleW(L"api-ms-win-eventing-provider-l1-1-0.dll")) != 0 )
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
            goto LABEL_18;
        }
        PfnEventRegister = McGenEventTracingRegister;
      }
    }
    McGenPreVista = 1;
  }
LABEL_18:
  McGenTracingSupportInit = 1;
LABEL_19:
  if ( !McGenPreVista )
  {
    v11 = (ULONG (__stdcall *)(WMIDPREQUESTCODE, PVOID, ULONG *, PVOID))McGenControlCallbackV2;
    if ( RequestAddress )
      v11 = RequestAddress;
    return PfnEventRegister(ControlGuid, v11, RegistrationHandle);
  }
  if ( !RegistrationHandle )
    return 87;
  v12 = McGenControlCallback;
  if ( RequestAddress )
    v12 = RequestAddress;
  *a4 = RegistrationHandle;
  TraceGuidReg.Guid = ControlGuid;
  TraceGuidReg.RegHandle = 0;
  return RegisterTraceGuidsW(v12, RegistrationHandle, ControlGuid, 1u, &TraceGuidReg, 0, 0, RegistrationHandle);
}

```

## disassembly

```asm
0x1400254f0  push    rbx
0x1400254f2  push    rbp
0x1400254f3  push    rsi
0x1400254f4  push    rdi
0x1400254f5  push    r14
0x1400254f7  push    r15
0x1400254f9  sub     rsp, 188h
0x140025500  mov     rax, cs:__security_cookie
0x140025507  xor     rax, rsp
0x14002550a  mov     [rsp+1B8h+var_48], rax
0x140025512  mov     r14, r9
0x140025515  mov     rsi, r8
0x140025518  mov     rbp, rdx
0x14002551b  mov     r15, rcx
0x14002551e  test    r9, r9
0x140025521  jz      loc_14002565F
0x140025527  xor     eax, eax
0x140025529  cmp     [r9], rax
0x14002552c  jnz     loc_1400256B8
0x140025532  mov     ebx, 114h
0x140025537  lea     rcx, [rsp+1B8h+VersionInformation]; void *
0x14002553c  mov     r8d, ebx; Size
0x14002553f  xor     edx, edx; Val
0x140025541  call    memset_0
0x140025546  cmp     cs:McGenTracingSupportInit, 0
0x14002554d  jnz     loc_14002562C
0x140025553  lea     rcx, [rsp+1B8h+VersionInformation]; lpVersionInformation
0x140025558  mov     [rsp+1B8h+VersionInformation.dwOSVersionInfoSize], ebx
0x14002555c  xor     edi, edi
0x14002555e  call    cs:__imp_GetVersionExW
0x140025564  test    eax, eax
0x140025566  jz      short loc_14002558E
0x140025568  cmp     [rsp+1B8h+VersionInformation.dwMajorVersion], 6
0x14002556d  setb    cl
0x140025570  mov     cs:McGenPreVista, cl
0x140025576  ja      short loc_140025581
0x140025578  jnz     short loc_140025586
0x14002557a  cmp     [rsp+1B8h+VersionInformation.dwMinorVersion], 1
0x14002557f  jbe     short loc_140025586
0x140025581  mov     edi, 1
0x140025586  test    cl, cl
0x140025588  jnz     loc_140025625
0x14002558e  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x140025595  call    cs:__imp_GetModuleHandleW
0x14002559b  mov     rbx, rax
0x14002559e  test    rax, rax
0x1400255a1  jnz     short loc_1400255BC
0x1400255a3  test    edi, edi
0x1400255a5  jz      short loc_14002561E
0x1400255a7  lea     rcx, ModuleName; "api-ms-win-eventing-provider-l1-1-0.dll"
0x1400255ae  call    cs:__imp_GetModuleHandleW
0x1400255b4  mov     rbx, rax
0x1400255b7  test    rax, rax
0x1400255ba  jz      short loc_14002561E
0x1400255bc  lea     rdx, aEventwrite; "EventWrite"
0x1400255c3  mov     rcx, rbx; hModule
0x1400255c6  call    cs:__imp_GetProcAddress
0x1400255cc  mov     cs:PfnEventWrite, rax
0x1400255d3  test    rax, rax
0x1400255d6  jz      short loc_14002561E
0x1400255d8  lea     rdx, aEventregister; "EventRegister"
0x1400255df  mov     rcx, rbx; hModule
0x1400255e2  call    cs:__imp_GetProcAddress
0x1400255e8  mov     cs:PfnEventRegister, rax
0x1400255ef  test    rax, rax
0x1400255f2  jz      short loc_140025610
0x1400255f4  lea     rdx, aEventunregiste; "EventUnregister"
0x1400255fb  mov     rcx, rbx; hModule
0x1400255fe  call    cs:__imp_GetProcAddress
0x140025604  mov     cs:PfnEventUnregister, rax
0x14002560b  test    rax, rax
0x14002560e  jnz     short loc_140025625
0x140025610  lea     rax, McGenEventTracingRegister
0x140025617  mov     cs:PfnEventRegister, rax
0x14002561e  mov     cs:McGenPreVista, 1
0x140025625  mov     cs:McGenTracingSupportInit, 1
0x14002562c  cmp     cs:McGenPreVista, 0
0x140025633  jnz     short loc_14002565A
0x140025635  mov     rax, cs:PfnEventRegister
0x14002563c  lea     rdx, McGenControlCallbackV2
0x140025643  test    rbp, rbp
0x140025646  mov     r9, r14
0x140025649  mov     r8, rsi
0x14002564c  mov     rcx, r15
0x14002564f  cmovnz  rdx, rbp
0x140025653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025658  jmp     short loc_1400256B8
0x14002565a  test    rsi, rsi
0x14002565d  jnz     short loc_140025666
0x14002565f  mov     eax, 57h ; 'W'
0x140025664  jmp     short loc_1400256B8
0x140025666  mov     [rsp+1B8h+RegistrationHandle], rsi; RegistrationHandle
0x14002566b  lea     rax, [rsp+1B8h+var_178]
0x140025670  test    rbp, rbp
0x140025673  mov     [rsp+1B8h+MofResourceName], 0; MofResourceName
0x14002567c  lea     rcx, McGenControlCallback
0x140025683  mov     [rsp+1B8h+MofImagePath], 0; MofImagePath
0x14002568c  cmovnz  rcx, rbp; RequestAddress
0x140025690  mov     [r14], rsi
0x140025693  mov     r9d, 1; GuidCount
0x140025699  mov     [rsp+1B8h+var_178.Guid], r15
0x14002569e  mov     r8, r15; ControlGuid
0x1400256a1  mov     [rsp+1B8h+var_178.RegHandle], 0
0x1400256aa  mov     rdx, rsi; RequestContext
0x1400256ad  mov     [rsp+1B8h+TraceGuidReg], rax; TraceGuidReg
0x1400256b2  call    cs:__imp_RegisterTraceGuidsW
0x1400256b8  mov     rcx, [rsp+1B8h+var_48]
0x1400256c0  xor     rcx, rsp; StackCookie
0x1400256c3  call    __security_check_cookie
0x1400256c8  add     rsp, 188h
0x1400256cf  pop     r15
0x1400256d1  pop     r14
0x1400256d3  pop     rdi
0x1400256d4  pop     rsi
0x1400256d5  pop     rbp
0x1400256d6  pop     rbx
0x1400256d7  retn
```
