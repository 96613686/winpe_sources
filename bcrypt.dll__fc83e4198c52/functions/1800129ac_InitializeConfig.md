# InitializeConfig

- ea: `0x1800129ac`
- end: `0x180012a13`
- name: `InitializeConfig`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a768`

## callees

- `0x18000b094`
- `0x18000d994`
- `0x18000dd8c`
- `0x1800114c4`
- `0x180011ea8`
- `0x1800129ac`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x1800129e2`
- `ntdll!RtlDllShutdownInProgress` at `0x1800129e2`

## pseudocode

```c
__int64 InitializeConfig()
{
  int v0; // eax
  char TrustedEnvironment; // cl

  v0 = g_TrustedEnvironment;
  if ( g_TrustedEnvironment )
  {
    TrustedEnvironment = g_TrustedEnvironment;
  }
  else
  {
    TrustedEnvironment = GetTrustedEnvironment();
    v0 = g_TrustedEnvironment;
  }
  if ( (TrustedEnvironment & 1) != 0 )
  {
    if ( !v0 )
      LOBYTE(v0) = GetTrustedEnvironment();
    if ( (v0 & 1) != 0 )
      InitializeProcessImageNameUM();
    if ( !RtlDllShutdownInProgress() )
      TlgRegisterAggregateProviderEx();
  }
  else
  {
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180024050);
  }
  return IoStartup();
}

```

## disassembly

```asm
0x1800129ac  sub     rsp, 28h
0x1800129b0  mov     eax, cs:g_TrustedEnvironment
0x1800129b6  test    eax, eax
0x1800129b8  jnz     short loc_1800129C9
0x1800129ba  call    GetTrustedEnvironment
0x1800129bf  mov     ecx, eax
0x1800129c1  mov     eax, cs:g_TrustedEnvironment
0x1800129c7  jmp     short loc_1800129CB
0x1800129c9  mov     ecx, eax
0x1800129cb  test    cl, 1
0x1800129ce  jz      short loc_1800129F9
0x1800129d0  test    eax, eax
0x1800129d2  jnz     short loc_1800129D9
0x1800129d4  call    GetTrustedEnvironment
0x1800129d9  test    al, 1
0x1800129db  jz      short loc_1800129E2
0x1800129dd  call    InitializeProcessImageNameUM
0x1800129e2  call    cs:__imp_RtlDllShutdownInProgress
0x1800129e9  nop     dword ptr [rax+rax+00h]
0x1800129ee  test    al, al
0x1800129f0  jnz     short loc_180012A0A
0x1800129f2  call    TlgRegisterAggregateProviderEx
0x1800129f7  jmp     short loc_180012A0A
0x1800129f9  xor     r8d, r8d
0x1800129fc  lea     rcx, dword_180024050; CallbackContext
0x180012a03  xor     edx, edx
0x180012a05  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180012a0a  add     rsp, 28h
0x180012a0e  jmp     ?IoStartup@@YAJXZ; IoStartup(void)
```
