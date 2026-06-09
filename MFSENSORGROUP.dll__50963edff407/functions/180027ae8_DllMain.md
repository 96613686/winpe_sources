# DllMain

- ea: `0x180027ae8`
- end: `0x180027b44`
- name: `DllMain`
- size: `92`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180044da4`

## callees

- `0x180027ae8`
- `0x180027b4c`
- `0x180027bd4`
- `0x180027d78`
- `0x180027e38`
- `0x180027e70`
- `0x180027f20`
- `0x180027f4c`
- `0x180027f7c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180027b0d`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180027b0d`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
  {
    g_hModule = hinstDLL;
    DisableThreadLibraryCalls(hinstDLL);
    McGenEventRegister_EventRegister();
    WPP_INIT_CONTROL_ARRAY();
    WPP_INIT_GUID_ARRAY();
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WppInitUm();
    TraceLoggingRegisterEx_EventRegister_EventSetInformation();
  }
  else if ( !fdwReason )
  {
    McGenEventUnregister_EventUnregister(hinstDLL, fdwReason, lpvReserved);
    WppCleanupUm();
    TraceLoggingUnregister_EventUnregister();
  }
  return 1;
}

```

## disassembly

```asm
0x180027ae8  sub     rsp, 28h
0x180027aec  cmp     edx, 1
0x180027aef  jz      short loc_180027B06
0x180027af1  test    edx, edx
0x180027af3  jnz     short loc_180027B3A
0x180027af5  call    McGenEventUnregister_EventUnregister
0x180027afa  call    WppCleanupUm
0x180027aff  call    TraceLoggingUnregister_EventUnregister
0x180027b04  jmp     short loc_180027B3A
0x180027b06  mov     cs:?g_hModule@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hModule
0x180027b0d  call    cs:__imp_DisableThreadLibraryCalls
0x180027b13  call    McGenEventRegister_EventRegister
0x180027b18  call    WPP_INIT_CONTROL_ARRAY
0x180027b1d  call    WPP_INIT_GUID_ARRAY
0x180027b22  lea     rcx, WPP_MAIN_CB
0x180027b29  mov     cs:WPP_GLOBAL_Control, rcx
0x180027b30  call    WppInitUm
0x180027b35  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180027b3a  mov     eax, 1
0x180027b3f  add     rsp, 28h
0x180027b43  retn
```
