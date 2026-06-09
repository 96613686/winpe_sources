# CONFIG_HISTORY::SetupAdministrationConfigurationSystem(void)

- ea: `0x180003e70`
- end: `0x18000400e`
- name: `?SetupAdministrationConfigurationSystem@CONFIG_HISTORY@@AEAAJXZ`
- size: `414`
- prototype: `__int64 __fastcall(CONFIG_HISTORY *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002e20`

## callees

- `0x180003e70`
- `0x18000a010`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x180003fc6`
- `iisutil!PuDbgPrintError` at `0x180003fc6`
- `nativerd!CreateNativeConfigurationSystem` at `0x180003e9a`
- `nativerd!CreateNativeConfigurationSystem` at `0x180003e9a`

## string_xrefs

- `0x180003eb3`: `CreateNativeConfigurationSystem failed.\n`
- `0x180003faf`: `CONFIG_HISTORY::SetupAdministrationConfigurationSystem`
- `0x180003fbb`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\config_history.cxx`
- `0x180003f01`: `SetConfigPathMapping failed.\n`

## pseudocode

```c
__int64 __fastcall CONFIG_HISTORY::SetupAdministrationConfigurationSystem(CONFIG_HISTORY *this)
{
  int v2; // ebx
  struct INativeConfigurationSystem *v3; // rcx
  struct INativeConfigurationSystem *v5; // [rsp+58h] [rbp+10h] BYREF
  __int64 v6; // [rsp+60h] [rbp+18h] BYREF

  v5 = 0;
  v6 = 0;
  v2 = CreateNativeConfigurationSystem(L"MACHINE", &v5);
  if ( v2 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, const wchar_t *, _QWORD, __int64))(*(_QWORD *)v5 + 64LL))(
           v5,
           L"MACHINE",
           *(_QWORD *)(*((_QWORD *)this + 5) + 168LL),
           1);
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, CONFIG_HISTORY *))(*(_QWORD *)v5 + 40LL))(
             v5,
             this);
      if ( v2 >= 0 )
      {
        v3 = v5;
        *((_QWORD *)this + 4) = v5;
        v5 = 0;
        v2 = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, const wchar_t *, const wchar_t *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v3 + 24LL))(
               v3,
               L"moduleProviders",
               L"MACHINE",
               &v6,
               0,
               0);
        if ( v2 < 0 && (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\config_history.cxx",
            186,
            "CONFIG_HISTORY::SetupAdministrationConfigurationSystem",
            v2,
            "Failed to get moduleProviders section.\n");
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\config_history.cxx",
          163,
          "CONFIG_HISTORY::SetupAdministrationConfigurationSystem",
          v2,
          "AddChangeListener failed\n");
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\config_history.cxx",
        148,
        "CONFIG_HISTORY::SetupAdministrationConfigurationSystem",
        v2,
        "SetConfigPathMapping failed.\n");
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\config_history.cxx",
      131,
      "CONFIG_HISTORY::SetupAdministrationConfigurationSystem",
      v2,
      "CreateNativeConfigurationSystem failed.\n");
  }
  if ( v5 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v5 + 16LL))(v5);
    v5 = 0;
  }
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180003e70  mov     rax, rsp
0x180003e73  mov     [rax+8], rbx
0x180003e77  push    rdi
0x180003e78  sub     rsp, 40h
0x180003e7c  mov     rdi, rcx
0x180003e7f  mov     qword ptr [rax+10h], 0
0x180003e87  lea     rcx, aMachine; "MACHINE"
0x180003e8e  mov     qword ptr [rax+18h], 0
0x180003e96  lea     rdx, [rax+10h]
0x180003e9a  call    cs:__imp_?CreateNativeConfigurationSystem@@YAJPEBGPEAPEAVINativeConfigurationSystem@@@Z; CreateNativeConfigurationSystem(ushort const *,INativeConfigurationSystem * *)
0x180003ea0  mov     ebx, eax
0x180003ea2  test    eax, eax
0x180003ea4  jns     short loc_180003EC5
0x180003ea6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003ead  jz      loc_180003FCC
0x180003eb3  lea     rax, aCreatenativeco; "CreateNativeConfigurationSystem failed."...
0x180003eba  mov     r8d, 83h
0x180003ec0  jmp     loc_180003FA8
0x180003ec5  mov     rcx, [rsp+48h+arg_8]
0x180003eca  lea     rdx, aMachine; "MACHINE"
0x180003ed1  mov     r8, [rdi+28h]
0x180003ed5  mov     r9d, 1
0x180003edb  mov     rax, [rcx]
0x180003ede  mov     r8, [r8+0A8h]
0x180003ee5  mov     rax, [rax+40h]
0x180003ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eee  mov     ebx, eax
0x180003ef0  test    eax, eax
0x180003ef2  jns     short loc_180003F13
0x180003ef4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003efb  jz      loc_180003FCC
0x180003f01  lea     rax, aSetconfigpathm; "SetConfigPathMapping failed.\n"
0x180003f08  mov     r8d, 94h
0x180003f0e  jmp     loc_180003FA8
0x180003f13  mov     rcx, [rsp+48h+arg_8]
0x180003f18  mov     rdx, rdi
0x180003f1b  mov     rax, [rcx]
0x180003f1e  mov     rax, [rax+28h]
0x180003f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f27  mov     ebx, eax
0x180003f29  test    eax, eax
0x180003f2b  jns     short loc_180003F49
0x180003f2d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003f34  jz      loc_180003FCC
0x180003f3a  lea     rax, aAddchangeliste; "AddChangeListener failed\n"
0x180003f41  mov     r8d, 0A3h
0x180003f47  jmp     short loc_180003FA8
0x180003f49  mov     rcx, [rsp+48h+arg_8]
0x180003f4e  lea     r9, [rsp+48h+arg_10]
0x180003f53  mov     [rdi+20h], rcx
0x180003f57  lea     r8, aMachine; "MACHINE"
0x180003f5e  mov     [rsp+48h+arg_8], 0
0x180003f67  lea     rdx, aModuleprovider; "moduleProviders"
0x180003f6e  mov     [rsp+48h+var_20], 0
0x180003f77  mov     rax, [rcx]
0x180003f7a  mov     [rsp+48h+var_28], 0
0x180003f83  mov     rax, [rax+18h]
0x180003f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f8c  mov     ebx, eax
0x180003f8e  test    eax, eax
0x180003f90  jns     short loc_180003FCC
0x180003f92  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003f99  jz      short loc_180003FCC
0x180003f9b  lea     rax, aFailedToGetMod; "Failed to get moduleProviders section."...
0x180003fa2  mov     r8d, 0BAh
0x180003fa8  mov     rcx, cs:g_pDebug
0x180003faf  lea     r9, aConfigHistoryS_0; "CONFIG_HISTORY::SetupAdministrationConf"...
0x180003fb6  mov     [rsp+48h+var_20], rax
0x180003fbb  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180003fc2  mov     dword ptr [rsp+48h+var_28], ebx
0x180003fc6  call    cs:__imp_PuDbgPrintError
0x180003fcc  mov     rcx, [rsp+48h+arg_8]
0x180003fd1  test    rcx, rcx
0x180003fd4  jz      short loc_180003FEB
0x180003fd6  mov     rax, [rcx]
0x180003fd9  mov     rax, [rax+10h]
0x180003fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fe2  mov     [rsp+48h+arg_8], 0
0x180003feb  mov     rcx, [rsp+48h+arg_10]
0x180003ff0  test    rcx, rcx
0x180003ff3  jz      short loc_180004001
0x180003ff5  mov     rax, [rcx]
0x180003ff8  mov     rax, [rax+10h]
0x180003ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004001  mov     eax, ebx
0x180004003  mov     rbx, [rsp+48h+arg_0]
0x180004008  add     rsp, 40h
0x18000400c  pop     rdi
0x18000400d  retn
```
