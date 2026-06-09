# DllMain

- ea: `0x180006ee4`
- end: `0x180006fa0`
- name: `DllMain`
- size: `188`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001984`

## callees

- `0x180001008`
- `0x1800010b8`
- `0x180006ee4`
- `0x1800074b8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180006f43`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180006f43`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180006f73`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180006f73`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  _QWORD *v4; // rbx
  TRACEHANDLE v5; // rcx

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      qword_18002BCE0 = 0;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_ScDeviceEnum;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      WPP_MAIN_CB = 0;
      qword_18002BCE8 = 1;
      WppInitUm(hinstDLL, fdwReason, lpvReserved);
      DisableThreadLibraryCalls(hinstDLL);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation();
    }
  }
  else
  {
    TraceLoggingUnregister_EventUnregister(hinstDLL, fdwReason, lpvReserved);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      while ( v4 )
      {
        v5 = v4[1];
        if ( v5 )
        {
          UnregisterTraceGuids(v5);
          v4[1] = 0;
        }
        v4 = (_QWORD *)*v4;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180006ee4  mov     [rsp+arg_0], rbx
0x180006ee9  push    rsi
0x180006eea  sub     rsp, 20h
0x180006eee  mov     rbx, rcx
0x180006ef1  test    edx, edx
0x180006ef3  jz      short loc_180006F50
0x180006ef5  cmp     edx, 1
0x180006ef8  jnz     loc_180006F90
0x180006efe  lea     rax, WPP_ThisDir_CTLGUID_ScDeviceEnum
0x180006f05  mov     cs:qword_18002BCE0, 0
0x180006f10  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180006f17  lea     rax, WPP_MAIN_CB
0x180006f1e  mov     cs:WPP_GLOBAL_Control, rax
0x180006f25  mov     cs:WPP_MAIN_CB, 0
0x180006f30  mov     cs:qword_18002BCE8, 1
0x180006f3b  call    WppInitUm
0x180006f40  mov     rcx, rbx; hLibModule
0x180006f43  call    cs:__imp_DisableThreadLibraryCalls
0x180006f49  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180006f4e  jmp     short loc_180006F90
0x180006f50  call    TraceLoggingUnregister_EventUnregister
0x180006f55  mov     rbx, cs:WPP_GLOBAL_Control
0x180006f5c  lea     rsi, WPP_GLOBAL_Control
0x180006f63  cmp     rbx, rsi
0x180006f66  jz      short loc_180006F90
0x180006f68  jmp     short loc_180006F84
0x180006f6a  mov     rcx, [rbx+8]; RegistrationHandle
0x180006f6e  test    rcx, rcx
0x180006f71  jz      short loc_180006F81
0x180006f73  call    cs:__imp_UnregisterTraceGuids
0x180006f79  mov     qword ptr [rbx+8], 0
0x180006f81  mov     rbx, [rbx]
0x180006f84  test    rbx, rbx
0x180006f87  jnz     short loc_180006F6A
0x180006f89  mov     cs:WPP_GLOBAL_Control, rsi
0x180006f90  mov     rbx, [rsp+28h+arg_0]
0x180006f95  mov     eax, 1
0x180006f9a  add     rsp, 20h
0x180006f9e  pop     rsi
0x180006f9f  retn
```
