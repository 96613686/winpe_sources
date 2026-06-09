# StateWebServer::RunAsService(void)

- ea: `0x140001c90`
- end: `0x140001cd5`
- name: `?RunAsService@StateWebServer@@AEAAJXZ`
- size: `69`
- prototype: `__int64 __fastcall(StateWebServer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x140002950`

## callees

- `0x140001c90`
- `0x140004f2c`

## import_xrefs

- `ADVAPI32!StartServiceCtrlDispatcherW` at `0x140001cbc`
- `ADVAPI32!StartServiceCtrlDispatcherW` at `0x140001cbc`

## pseudocode

```c
__int64 __fastcall StateWebServer::RunAsService(StateWebServer *this)
{
  unsigned int v1; // ebx
  SERVICE_TABLE_ENTRYW v3; // [rsp+20h] [rbp-28h] BYREF
  __int64 v4; // [rsp+30h] [rbp-18h]
  __int64 v5; // [rsp+38h] [rbp-10h]

  v1 = 0;
  v3.lpServiceName = StateWebServer::s_serviceName;
  v4 = 0;
  v3.lpServiceProc = (LPSERVICE_MAIN_FUNCTIONW)StateWebServer::ServiceMain;
  v5 = 0;
  if ( !StartServiceCtrlDispatcherW(&v3) )
    return (unsigned int)GetLastWin32Error();
  return v1;
}

```

## disassembly

```asm
0x140001c90  mov     r11, rsp
0x140001c93  push    rbx
0x140001c94  sub     rsp, 40h
0x140001c98  lea     rax, ?s_serviceName@StateWebServer@@0PAGA; "aspnet_state"
0x140001c9f  xor     ebx, ebx
0x140001ca1  mov     [r11-28h], rax
0x140001ca5  lea     rcx, [r11-28h]; lpServiceStartTable
0x140001ca9  lea     rax, ?ServiceMain@StateWebServer@@CAXKPEAPEAG@Z; StateWebServer::ServiceMain(ulong,ushort * *)
0x140001cb0  mov     [r11-18h], rbx
0x140001cb4  mov     [r11-20h], rax
0x140001cb8  mov     [r11-10h], rbx
0x140001cbc  call    cs:__imp_StartServiceCtrlDispatcherW
0x140001cc2  test    eax, eax
0x140001cc4  jnz     short loc_140001CCD
0x140001cc6  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x140001ccb  mov     ebx, eax
0x140001ccd  mov     eax, ebx
0x140001ccf  add     rsp, 40h
0x140001cd3  pop     rbx
0x140001cd4  retn
```
