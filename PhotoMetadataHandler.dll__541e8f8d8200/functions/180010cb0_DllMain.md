# DllMain

- ea: `0x180010cb0`
- end: `0x180010daf`
- name: `DllMain`
- size: `255`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015e94`

## callees

- `0x18000ec78`
- `0x18000ed78`
- `0x18000f3ec`
- `0x18000fa74`
- `0x18000fbd0`
- `0x180010cb0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180010ce0`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180010ce0`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct _GUID *v3; // r9

  if ( fdwReason == 1 )
  {
    hProxyDll = hinstDLL;
    ATL::CComModule::Init(
      (ATL::CComModule *)hinstDLL,
      *(struct ATL::_ATL_OBJMAP_ENTRY30 **)&fdwReason,
      (HINSTANCE)lpvReserved,
      v3);
    DisableThreadLibraryCalls(hinstDLL);
    qword_180098EC0 = 0;
    WPP_MAIN_CB = (__int64)&qword_180098ED8;
    qword_180098ED8 = (__int64)&qword_180098F00;
    WPP_REGISTRATION_GUIDS = (__int64)&WPP_ThisDir_CTLGUID_ShellTraceProvider;
    qword_180098F38 = (__int64)&WPP_ThisDir_CTLGUID_ShellPerfTraceProvider;
    qword_180098F40 = (__int64)&WPP_ThisDir_CTLGUID_ShellTraceHomeGroupProvider;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    qword_180098EC8 = 1;
    qword_180098EE8 = 0;
    qword_180098EF0 = 1;
    qword_180098F10 = 0;
    qword_180098F00 = 0;
    qword_180098F18 = 1;
    WppInitUm();
    DisableStackCapture();
  }
  else if ( !fdwReason )
  {
    ATL::CComModule::Term((ATL::CComModule *)hinstDLL);
    WppCleanupUm();
  }
  g_hInstance = hinstDLL;
  return 1;
}

```

## disassembly

```asm
0x180010cb0  push    rbx
0x180010cb2  sub     rsp, 20h
0x180010cb6  mov     rbx, rcx
0x180010cb9  cmp     edx, 1
0x180010cbc  jnz     short loc_180010CC7
0x180010cbe  mov     cs:hProxyDll, rcx
0x180010cc5  jmp     short loc_180010CD8
0x180010cc7  test    edx, edx
0x180010cc9  jz      loc_180010D93
0x180010ccf  cmp     edx, 1
0x180010cd2  jnz     loc_180010D9D
0x180010cd8  call    ?Init@CComModule@ATL@@QEAAJPEAU_ATL_OBJMAP_ENTRY30@2@PEAUHINSTANCE__@@PEBU_GUID@@@Z; ATL::CComModule::Init(ATL::_ATL_OBJMAP_ENTRY30 *,HINSTANCE__ *,_GUID const *)
0x180010cdd  mov     rcx, rbx; hLibModule
0x180010ce0  call    cs:__imp_DisableThreadLibraryCalls
0x180010ce6  lea     rax, qword_180098ED8
0x180010ced  mov     cs:qword_180098EC0, 0
0x180010cf8  mov     cs:WPP_MAIN_CB, rax
0x180010cff  lea     rax, qword_180098F00
0x180010d06  mov     cs:qword_180098ED8, rax
0x180010d0d  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceProvider
0x180010d14  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180010d1b  lea     rax, WPP_ThisDir_CTLGUID_ShellPerfTraceProvider
0x180010d22  mov     cs:qword_180098F38, rax
0x180010d29  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceHomeGroupProvider
0x180010d30  mov     cs:qword_180098F40, rax
0x180010d37  lea     rax, WPP_MAIN_CB
0x180010d3e  mov     cs:WPP_GLOBAL_Control, rax
0x180010d45  mov     cs:qword_180098EC8, 1
0x180010d50  mov     cs:qword_180098EE8, 0
0x180010d5b  mov     cs:qword_180098EF0, 1
0x180010d66  mov     cs:qword_180098F10, 0
0x180010d71  mov     cs:qword_180098F00, 0
0x180010d7c  mov     cs:qword_180098F18, 1
0x180010d87  call    WppInitUm
0x180010d8c  call    ?DisableStackCapture@@YAXXZ; DisableStackCapture(void)
0x180010d91  jmp     short loc_180010D9D
0x180010d93  call    ?Term@CComModule@ATL@@QEAAXXZ; ATL::CComModule::Term(void)
0x180010d98  call    WppCleanupUm
0x180010d9d  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInstance
0x180010da4  mov     eax, 1
0x180010da9  add     rsp, 20h
0x180010dad  pop     rbx
0x180010dae  retn
```
