# wWinMain

- ea: `0x140005cb8`
- end: `0x140005d42`
- name: `wWinMain`
- size: `138`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x140007330`

## callees

- `0x140003624`
- `0x140005930`
- `0x1400059bc`
- `0x140005a88`
- `0x140005c7c`
- `0x140005cb8`

## import_xrefs

- `ntdll!_wcsicmp` at `0x140005ceb`
- `ntdll!_wcsicmp` at `0x140005cff`
- `ntdll!_wcsicmp` at `0x140005ceb`
- `ntdll!_wcsicmp` at `0x140005cff`
- `ntdll!_wcsnicmp` at `0x140005d20`
- `ntdll!_wcsnicmp` at `0x140005d20`

## string_xrefs

- `0x140005ce1`: `/install`
- `0x140005cf5`: `/uninstall`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  unsigned int v5; // eax
  __int64 v6; // rcx
  unsigned int v8; // eax

  if ( (unsigned int)Feature_Servicing_GameInputSvcRedirectionGuard__private_IsEnabledDeviceUsageNoInline(
                       hInstance,
                       hPrevInstance,
                       lpCmdLine,
                       nShowCmd) )
  {
    v5 = EnableRedirectionGuard();
    if ( (unsigned __int8)wWinMain_::_1_::_lambda_1_::operator()(v6, v5) )
      return 1;
  }
  if ( _wcsicmp(lpCmdLine, L"/install") && _wcsicmp(lpCmdLine, L"/uninstall") )
  {
    if ( _wcsnicmp(lpCmdLine, L"Global\\GameInputSession", 0x17u) )
      v8 = RunService();
    else
      v8 = RunInstance(lpCmdLine);
  }
  else
  {
    v8 = -2147467263;
  }
  return v8 >> 31;
}

```

## disassembly

```asm
0x140005cb8  push    rbx
0x140005cba  sub     rsp, 20h
0x140005cbe  mov     rbx, r8
0x140005cc1  call    Feature_Servicing_GameInputSvcRedirectionGuard__private_IsEnabledDeviceUsageNoInline
0x140005cc6  test    eax, eax
0x140005cc8  jz      short loc_140005CE1
0x140005cca  call    EnableRedirectionGuard
0x140005ccf  mov     edx, eax
0x140005cd1  call    _wWinMain____1____lambda_1___operator__
0x140005cd6  test    al, al
0x140005cd8  jz      short loc_140005CE1
0x140005cda  mov     eax, 1
0x140005cdf  jmp     short loc_140005D3C
0x140005ce1  lea     rdx, aInstall; "/install"
0x140005ce8  mov     rcx, rbx; String1
0x140005ceb  call    cs:__imp__wcsicmp
0x140005cf1  test    eax, eax
0x140005cf3  jz      short loc_140005D09
0x140005cf5  lea     rdx, aUninstall; "/uninstall"
0x140005cfc  mov     rcx, rbx; String1
0x140005cff  call    cs:__imp__wcsicmp
0x140005d05  test    eax, eax
0x140005d07  jnz     short loc_140005D10
0x140005d09  mov     eax, 80004001h
0x140005d0e  jmp     short loc_140005D39
0x140005d10  mov     r8d, 17h; MaxCount
0x140005d16  lea     rdx, aGlobalGameinpu; "Global\\GameInputSession"
0x140005d1d  mov     rcx, rbx; String1
0x140005d20  call    cs:__imp__wcsnicmp
0x140005d26  test    eax, eax
0x140005d28  jnz     short loc_140005D34
0x140005d2a  mov     rcx, rbx; unsigned __int16 *
0x140005d2d  call    RunInstance
0x140005d32  jmp     short loc_140005D39
0x140005d34  call    ?RunService@@YAJXZ; RunService(void)
0x140005d39  shr     eax, 1Fh
0x140005d3c  add     rsp, 20h
0x140005d40  pop     rbx
0x140005d41  retn
```
