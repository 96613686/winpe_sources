# DebugFlags::InitRegistry(void)

- ea: `0x18004239c`
- end: `0x18004250e`
- name: `?InitRegistry@DebugFlags@@CAXXZ`
- size: `370`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180041fc8`

## callees

- `0x180042204`
- `0x1800422ec`
- `0x18004239c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800423cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800423f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800423cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800423f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800424f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800424f8`

## string_xrefs

- `0x1800423bf`: `Software\Microsoft\COM3\Debug`
- `0x1800423e9`: `Software\Microsoft\COM3\Debug`
- `0x18004243e`: `DebugBreakOnInitComPlus`
- `0x180042455`: `DebugBreakOnLoadComsvcs`
- `0x1800424c8`: `TraceSecurity`
- `0x1800424df`: `TraceSecurityPM`

## pseudocode

```c
void DebugFlags::InitRegistry(void)
{
  const unsigned __int16 *v0; // rdx
  unsigned int *v1; // r8
  HKEY hKey; // [rsp+40h] [rbp+10h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\COM3\\Debug", 0, 0x2001Bu, &hKey)
    || !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\COM3\\Debug", 0, 0x20019u, &hKey) )
  {
    DebugFlags::InitBoolean(hKey, L"AutoAddTraceToContext", &DebugFlags::sm_fAutoAddTraceToContext);
    DebugFlags::InitBoolean(hKey, L"DebugBreakOnFailFast", &DebugFlags::sm_fDebugBreakOnFailFast);
    DebugFlags::InitBoolean(hKey, L"DebugBreakOnInitComPlus", &DebugFlags::sm_fDebugBreakOnInitComPlus);
    DebugFlags::InitBoolean(hKey, L"DebugBreakOnLoadComsvcs", &DebugFlags::sm_fDebugBreakOnLoadComsvcs);
    DebugFlags::InitBoolean(hKey, L"TraceActivityModule", &DebugFlags::sm_fTraceActivityModule);
    DebugFlags::InitBoolean(hKey, L"TraceContextCreation", &DebugFlags::sm_fTraceContextCreation);
    DebugFlags::InitBoolean(hKey, L"TraceInfrastructureCalls", &DebugFlags::sm_fTraceInfrastructureCalls);
    DebugFlags::InitBoolean(hKey, L"TraceSTAPool", &DebugFlags::sm_fTraceSTAPool);
    DebugFlags::InitBoolean(hKey, L"TraceSecurity", &DebugFlags::sm_fTraceSecurity);
    DebugFlags::InitBoolean(hKey, L"TraceSecurityPM", &DebugFlags::sm_fTraceSecurityPM);
    DebugFlags::InitDWORD(hKey, v0, v1);
    RegCloseKey(hKey);
  }
  DebugFlags::sm_registryInitialized = 1;
}

```

## disassembly

```asm
0x18004239c  push    rbp
0x18004239e  mov     rbp, rsp
0x1800423a1  sub     rsp, 30h
0x1800423a5  lea     rax, [rbp+hKey]
0x1800423a9  mov     [rbp+hKey], 0
0x1800423b1  mov     r9d, 2001Bh; samDesired
0x1800423b7  mov     [rsp+30h+phkResult], rax; phkResult
0x1800423bc  xor     r8d, r8d; ulOptions
0x1800423bf  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\COM3\\Debug"
0x1800423c6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800423cd  call    cs:__imp_RegOpenKeyExW
0x1800423d3  test    eax, eax
0x1800423d5  jz      short loc_180042405
0x1800423d7  lea     rax, [rbp+hKey]
0x1800423db  mov     r9d, 20019h; samDesired
0x1800423e1  xor     r8d, r8d; ulOptions
0x1800423e4  mov     [rsp+30h+phkResult], rax; phkResult
0x1800423e9  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\COM3\\Debug"
0x1800423f0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800423f7  call    cs:__imp_RegOpenKeyExW
0x1800423fd  test    eax, eax
0x1800423ff  jnz     loc_1800424FE
0x180042405  mov     rcx, [rbp+hKey]; hKey
0x180042409  lea     r8, ?sm_fAutoAddTraceToContext@DebugFlags@@0HA; int *
0x180042410  lea     rdx, aAutoaddtraceto; "AutoAddTraceToContext"
0x180042417  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18004241c  mov     rcx, [rbp+hKey]; hKey
0x180042420  lea     r8, ?sm_fDebugBreakOnFailFast@DebugFlags@@0HA; int *
0x180042427  lea     rdx, aDebugbreakonfa; "DebugBreakOnFailFast"
0x18004242e  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180042433  mov     rcx, [rbp+hKey]; hKey
0x180042437  lea     r8, ?sm_fDebugBreakOnInitComPlus@DebugFlags@@0HA; int *
0x18004243e  lea     rdx, aDebugbreakonin; "DebugBreakOnInitComPlus"
0x180042445  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18004244a  mov     rcx, [rbp+hKey]; hKey
0x18004244e  lea     r8, ?sm_fDebugBreakOnLoadComsvcs@DebugFlags@@0HA; int *
0x180042455  lea     rdx, aDebugbreakonlo; "DebugBreakOnLoadComsvcs"
0x18004245c  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180042461  mov     rcx, [rbp+hKey]; hKey
0x180042465  lea     r8, ?sm_fTraceActivityModule@DebugFlags@@0HA; int *
0x18004246c  lea     rdx, aTraceactivitym; "TraceActivityModule"
0x180042473  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180042478  mov     rcx, [rbp+hKey]; hKey
0x18004247c  lea     r8, ?sm_fTraceContextCreation@DebugFlags@@0HA; int *
0x180042483  lea     rdx, aTracecontextcr; "TraceContextCreation"
0x18004248a  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18004248f  mov     rcx, [rbp+hKey]; hKey
0x180042493  lea     r8, ?sm_fTraceInfrastructureCalls@DebugFlags@@0HA; int *
0x18004249a  lea     rdx, aTraceinfrastru; "TraceInfrastructureCalls"
0x1800424a1  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x1800424a6  mov     rcx, [rbp+hKey]; hKey
0x1800424aa  lea     r8, ?sm_fTraceSTAPool@DebugFlags@@0HA; int *
0x1800424b1  lea     rdx, aTracestapool; "TraceSTAPool"
0x1800424b8  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x1800424bd  mov     rcx, [rbp+hKey]; hKey
0x1800424c1  lea     r8, ?sm_fTraceSecurity@DebugFlags@@0HA; int *
0x1800424c8  lea     rdx, aTracesecurity; "TraceSecurity"
0x1800424cf  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x1800424d4  mov     rcx, [rbp+hKey]; hKey
0x1800424d8  lea     r8, ?sm_fTraceSecurityPM@DebugFlags@@0HA; int *
0x1800424df  lea     rdx, aTracesecurityp; "TraceSecurityPM"
0x1800424e6  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x1800424eb  mov     rcx, [rbp+hKey]; hKey
0x1800424ef  call    ?InitDWORD@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAK@Z; DebugFlags::InitDWORD(HKEY__ *,ushort const *,ulong *)
0x1800424f4  mov     rcx, [rbp+hKey]; hKey
0x1800424f8  call    cs:__imp_RegCloseKey
0x1800424fe  mov     cs:?sm_registryInitialized@DebugFlags@@0HA, 1; int DebugFlags::sm_registryInitialized
0x180042508  add     rsp, 30h
0x18004250c  pop     rbp
0x18004250d  retn
```
