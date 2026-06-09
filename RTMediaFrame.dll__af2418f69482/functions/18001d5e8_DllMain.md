# DllMain

- ea: `0x18001d5e8`
- end: `0x18001d657`
- name: `DllMain`
- size: `111`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026794`

## callees

- `0x1800183b0`
- `0x180018f60`
- `0x18001ada8`
- `0x18001b124`
- `0x18001b2c8`
- `0x18001b508`
- `0x18001b8f8`
- `0x18001b92c`
- `0x18001bcf8`
- `0x18001d4ac`
- `0x18001d5e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001d5f1`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001d5f1`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  Microsoft::WRL::Details *v3; // rax
  struct Microsoft::WRL::Details::ModuleBase *v4; // rdx
  bool v5; // r9

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
    Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
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
    v3 = (Microsoft::WRL::Details *)Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
    Microsoft::WRL::Details::TerminateMap(v3, v4, 0, v5);
  }
  return 1;
}

```

## disassembly

```asm
0x18001d5e8  sub     rsp, 28h
0x18001d5ec  cmp     edx, 1
0x18001d5ef  jnz     short loc_18001D62A
0x18001d5f1  call    cs:__imp_DisableThreadLibraryCalls
0x18001d5f7  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18001d5fc  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18001d601  call    McGenEventRegister_EventRegister
0x18001d606  call    WPP_INIT_CONTROL_ARRAY
0x18001d60b  call    WPP_INIT_GUID_ARRAY
0x18001d610  lea     rcx, WPP_MAIN_CB
0x18001d617  mov     cs:WPP_GLOBAL_Control, rcx
0x18001d61e  call    WppInitUm
0x18001d623  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001d628  jmp     short loc_18001D64D
0x18001d62a  test    edx, edx
0x18001d62c  jnz     short loc_18001D64D
0x18001d62e  call    McGenEventUnregister_EventUnregister
0x18001d633  call    WppCleanupUm
0x18001d638  call    TraceLoggingUnregister_EventUnregister
0x18001d63d  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18001d642  xor     r8d, r8d; unsigned __int16 *
0x18001d645  mov     rcx, rax; this
0x18001d648  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x18001d64d  mov     eax, 1
0x18001d652  add     rsp, 28h
0x18001d656  retn
```
