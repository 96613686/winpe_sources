# DllMain

- ea: `0x180001ed0`
- end: `0x18000200e`
- name: `DllMain`
- size: `318`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c8f4`

## callees

- `0x180001ed0`
- `0x180005f00`
- `0x180012f88`
- `0x180012fc0`
- `0x180012ff0`
- `0x1800130b4`
- `0x180051a04`
- `0x180051f98`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001f00`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001f00`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001ff9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001ff9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001f86`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001f86`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180001fcc`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180001fcc`
- `USER32!UnregisterClassW` at `0x180001fb9`
- `USER32!UnregisterClassW` at `0x180001fb9`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  INITCOMMONCONTROLSEX picce; // [rsp+48h] [rbp+20h] BYREF

  if ( fdwReason == 1 )
  {
    McGenEventRegister_EtwEventRegister(hinstDLL, fdwReason, lpvReserved);
    g_hmodThisDll = hinstDLL;
    DisableThreadLibraryCalls(hinstDLL);
    WPP_INIT_CONTROL_ARRAY();
    qword_180070CE8 = (__int64)WPP_ThisDir_CTLGUID_ShellPerfTraceProvider;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_ShellTraceProvider;
    qword_180070CF0 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceHomeGroupProvider;
    qword_180070CF8 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceCredUIProvider;
    qword_180070D00 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceImageValidatorProvider;
    qword_180070D08 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceImmersiveColorProvider;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WppInitUm();
    SHFusionInitializeFromModuleID(hinstDLL);
    InitializeCriticalSection(&g_DllCriticalSection);
    picce.dwSize = 8;
    picce.dwICC = 767;
    InitCommonControlsEx(&picce);
  }
  else if ( !fdwReason )
  {
    UnregisterClassW(L"StubWindow32", &_ImageBase);
    if ( g_hActCtx != (HANDLE)-1LL )
    {
      ReleaseActCtx(g_hActCtx);
      g_hActCtx = (HANDLE)-1LL;
    }
    if ( hModule )
      hModule = (HMODULE)-1LL;
    DeleteCriticalSection(&g_DllCriticalSection);
    McGenEventUnregister_EtwEventUnregister();
    WppCleanupUm();
  }
  return 1;
}

```

## disassembly

```asm
0x180001ed0  push    rbx
0x180001ed2  sub     rsp, 20h
0x180001ed6  mov     rbx, rcx
0x180001ed9  cmp     edx, 1
0x180001edc  jz      short loc_180001EF1
0x180001ede  test    edx, edx
0x180001ee0  jz      loc_180001FAB
0x180001ee6  mov     eax, 1
0x180001eeb  add     rsp, 20h
0x180001eef  pop     rbx
0x180001ef0  retn
0x180001ef1  call    McGenEventRegister_EtwEventRegister
0x180001ef6  mov     rcx, rbx; hLibModule
0x180001ef9  mov     cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hmodThisDll
0x180001f00  call    cs:__imp_DisableThreadLibraryCalls
0x180001f06  call    WPP_INIT_CONTROL_ARRAY
0x180001f0b  lea     rax, WPP_ThisDir_CTLGUID_ShellPerfTraceProvider
0x180001f12  mov     cs:qword_180070CE8, rax
0x180001f19  lea     rdx, WPP_ThisDir_CTLGUID_ShellTraceProvider
0x180001f20  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceHomeGroupProvider
0x180001f27  mov     cs:WPP_REGISTRATION_GUIDS, rdx
0x180001f2e  mov     cs:qword_180070CF0, rax
0x180001f35  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceCredUIProvider
0x180001f3c  mov     cs:qword_180070CF8, rax
0x180001f43  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceImageValidatorProvider
0x180001f4a  mov     cs:qword_180070D00, rax
0x180001f51  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceImmersiveColorProvider
0x180001f58  mov     cs:qword_180070D08, rax
0x180001f5f  lea     rax, WPP_MAIN_CB
0x180001f66  mov     cs:WPP_GLOBAL_Control, rax
0x180001f6d  call    WppInitUm
0x180001f72  mov     edx, 7Ch ; '|'
0x180001f77  mov     rcx, rbx; hModule
0x180001f7a  call    SHFusionInitializeFromModuleID
0x180001f7f  lea     rcx, ?g_DllCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001f86  call    cs:__imp_InitializeCriticalSection
0x180001f8c  lea     rcx, [rsp+28h+picce]; picce
0x180001f91  mov     [rsp+28h+picce.dwSize], 8
0x180001f99  mov     [rsp+28h+picce.dwICC], 2FFh
0x180001fa1  call    InitCommonControlsEx
0x180001fa6  jmp     loc_180001EE6
0x180001fab  lea     rdx, __ImageBase; hInstance
0x180001fb2  lea     rcx, ClassName; "StubWindow32"
0x180001fb9  call    cs:__imp_UnregisterClassW
0x180001fbf  mov     rcx, cs:g_hActCtx; hActCtx
0x180001fc6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180001fca  jz      short loc_180001FDD
0x180001fcc  call    cs:__imp_ReleaseActCtx
0x180001fd2  mov     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180001fdd  cmp     cs:hModule, 0
0x180001fe5  jz      short loc_180001FF2
0x180001fe7  mov     cs:hModule, 0FFFFFFFFFFFFFFFFh
0x180001ff2  lea     rcx, ?g_DllCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001ff9  call    cs:__imp_DeleteCriticalSection
0x180001fff  call    McGenEventUnregister_EtwEventUnregister
0x180002004  call    WppCleanupUm
0x180002009  jmp     loc_180001EE6
```
