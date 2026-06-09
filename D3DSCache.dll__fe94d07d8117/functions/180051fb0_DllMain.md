# DllMain

- ea: `0x180051fb0`
- end: `0x18005201b`
- name: `DllMain`
- size: `107`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180044864`

## callees

- `0x180001434`
- `0x18002de10`
- `0x180032de0`
- `0x180051a60`
- `0x180051fb0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180051fd2`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180051fd2`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v4; // ebx

  v4 = 1;
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      McGenEventRegister_EventRegister();
      CTelemetryHelper::Register((CTelemetryHelper *)&g_TelemetryHelper);
      hInstance = hinstDLL;
      return !ATL::CAtlBaseModule::m_bInitFailed;
    }
  }
  else
  {
    TraceLoggingUnregister_EventUnregister(off_1800C6660, 0, lpvReserved);
    McGenEventUnregister_EventUnregister();
  }
  return v4;
}

```

## disassembly

```asm
0x180051fb0  mov     [rsp+arg_0], rbx
0x180051fb5  push    rdi
0x180051fb6  sub     rsp, 20h
0x180051fba  mov     rdi, rcx
0x180051fbd  mov     eax, edx
0x180051fbf  mov     ebx, 1
0x180051fc4  test    edx, edx
0x180051fc6  jz      short loc_180051FFD
0x180051fc8  cmp     eax, ebx
0x180051fca  jz      short loc_180051FD2
0x180051fcc  cmp     edx, ebx
0x180051fce  jnz     short loc_18005200E
0x180051fd0  jmp     short loc_180051FF0
0x180051fd2  call    cs:__imp_DisableThreadLibraryCalls
0x180051fd8  call    McGenEventRegister_EventRegister
0x180051fdd  lea     rcx, ?g_TelemetryHelper@@3VShaderCacheTelemetryHelper@@A; this
0x180051fe4  call    ?Register@CTelemetryHelper@@UEAAJXZ; CTelemetryHelper::Register(void)
0x180051fe9  mov     cs:hInstance, rdi
0x180051ff0  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x180051ff7  jz      short loc_18005200E
0x180051ff9  xor     ebx, ebx
0x180051ffb  jmp     short loc_18005200E
0x180051ffd  mov     rcx, cs:off_1800C6660
0x180052004  call    TraceLoggingUnregister_EventUnregister
0x180052009  call    McGenEventUnregister_EventUnregister
0x18005200e  mov     eax, ebx
0x180052010  mov     rbx, [rsp+28h+arg_0]
0x180052015  add     rsp, 20h
0x180052019  pop     rdi
0x18005201a  retn
```
