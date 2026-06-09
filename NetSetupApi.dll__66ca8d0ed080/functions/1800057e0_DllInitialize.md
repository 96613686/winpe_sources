# DllInitialize

- ea: `0x1800057e0`
- end: `0x18000583e`
- name: `DllInitialize`
- size: `94`
- prototype: `BOOL __fastcall(HMODULE)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800054ac`

## callees

- `0x1800010b8`
- `0x180005844`
- `0x1800058e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!DisableThreadLibraryCalls` at `0x180005837`

## pseudocode

```c
BOOL __fastcall DllInitialize(HMODULE a1)
{
  qword_180025A48 = 1;
  qword_180025A40 = 0;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_NETSETUP;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  WPP_MAIN_CB = 0;
  WppInitUm();
  McGenEventRegister_EventRegister();
  TraceLoggingRegister_EventRegister_EventSetInformation();
  return DisableThreadLibraryCalls(a1);
}

```

## disassembly

```asm
0x1800057e0  push    rbx
0x1800057e2  sub     rsp, 20h
0x1800057e6  mov     rbx, rcx
0x1800057e9  xor     ecx, ecx
0x1800057eb  mov     cs:qword_180025A48, 1
0x1800057f6  lea     rax, WPP_ThisDir_CTLGUID_NETSETUP
0x1800057fd  mov     cs:qword_180025A40, rcx
0x180005804  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000580b  lea     rax, WPP_MAIN_CB
0x180005812  mov     cs:WPP_GLOBAL_Control, rax
0x180005819  mov     cs:WPP_MAIN_CB, rcx
0x180005820  call    WppInitUm
0x180005825  call    McGenEventRegister_EventRegister
0x18000582a  call    TraceLoggingRegister_EventRegister_EventSetInformation
0x18000582f  mov     rcx, rbx
0x180005832  add     rsp, 20h
0x180005836  pop     rbx
0x180005837  jmp     cs:__imp_DisableThreadLibraryCalls
```
