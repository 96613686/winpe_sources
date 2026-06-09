# DllMain

- ea: `0x18001cac0`
- end: `0x18001cbdb`
- name: `DllMain`
- size: `283`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004584`

## callees

- `0x18000d7fc`
- `0x18001cac0`
- `0x18001ce18`
- `0x1800db304`
- `0x1800e09b0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18001cb89`
- `KERNEL32!FreeLibrary` at `0x18001cb89`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18001cb74`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18001cb74`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18001cbad`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18001cbad`

## string_xrefs

- `0x18001cb20`: `SecurityHealthUdk.dll`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const unsigned __int16 *v4; // r8
  int SystemLibrary; // eax
  _QWORD *v7; // rdi
  TRACEHANDLE v8; // rcx

  if ( fdwReason == 1 )
  {
    qword_180139E00 = 1;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_ShieldProviderWdspCore;
    qword_180139DF8 = 0;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WPP_MAIN_CB = 0;
    WppInitUm(hinstDLL, fdwReason, lpvReserved);
    if ( (int)MpInvokeAutoStartupInitialization() < 0 )
      return 0;
    SystemLibrary = CommonUtil::UtilLoadSystemLibrary(
                      (CommonUtil *)&g_hUdkDll,
                      (HINSTANCE *)L"SecurityHealthUdk.dll",
                      v4);
    if ( SystemLibrary < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_994fa911d54f3e27e05dcb2a0079fd72_Traceguids,
          (unsigned int)SystemLibrary);
      return 0;
    }
    g_hInstance = (unsigned __int16 **)hinstDLL;
    DisableThreadLibraryCalls(hinstDLL);
  }
  else if ( !fdwReason )
  {
    FreeLibrary(g_hUdkDll);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      while ( v7 )
      {
        v8 = v7[1];
        if ( v8 )
        {
          UnregisterTraceGuids(v8);
          v7[1] = 0;
        }
        v7 = (_QWORD *)*v7;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18001cac0  mov     [rsp+arg_0], rbx
0x18001cac5  mov     [rsp+arg_8], rsi
0x18001caca  push    rdi
0x18001cacb  sub     rsp, 20h
0x18001cacf  mov     rdi, rcx
0x18001cad2  cmp     edx, 1
0x18001cad5  jnz     loc_18001CB7C
0x18001cadb  lea     rax, WPP_ThisDir_CTLGUID_ShieldProviderWdspCore
0x18001cae2  mov     cs:qword_180139E00, 1
0x18001caed  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18001caf4  xor     ebx, ebx
0x18001caf6  lea     rax, WPP_MAIN_CB
0x18001cafd  mov     cs:qword_180139DF8, rbx
0x18001cb04  mov     cs:WPP_GLOBAL_Control, rax
0x18001cb0b  mov     cs:WPP_MAIN_CB, rbx
0x18001cb12  call    WppInitUm
0x18001cb17  call    MpInvokeAutoStartupInitialization
0x18001cb1c  test    eax, eax
0x18001cb1e  js      short loc_18001CB66
0x18001cb20  lea     rdx, aSecurityhealth_8; "SecurityHealthUdk.dll"
0x18001cb27  lea     rcx, ?g_hUdkDll@@3PEAUHINSTANCE__@@EA; this
0x18001cb2e  call    ?UtilLoadSystemLibrary@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEBG@Z; CommonUtil::UtilLoadSystemLibrary(HINSTANCE__ * *,ushort const *)
0x18001cb33  test    eax, eax
0x18001cb35  jns     short loc_18001CB6A
0x18001cb37  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb3e  lea     rsi, WPP_GLOBAL_Control
0x18001cb45  cmp     rcx, rsi
0x18001cb48  jz      short loc_18001CB66
0x18001cb4a  test    byte ptr [rcx+1Ch], 1
0x18001cb4e  jz      short loc_18001CB66
0x18001cb50  mov     rcx, [rcx+10h]
0x18001cb54  lea     edx, [rbx+0Ah]
0x18001cb57  mov     r9d, eax
0x18001cb5a  lea     r8, WPP_994fa911d54f3e27e05dcb2a0079fd72_Traceguids
0x18001cb61  call    WPP_SF_d
0x18001cb66  xor     eax, eax
0x18001cb68  jmp     short loc_18001CBCB
0x18001cb6a  mov     rcx, rdi; hLibModule
0x18001cb6d  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hInstance
0x18001cb74  call    cs:__imp_DisableThreadLibraryCalls
0x18001cb7a  jmp     short loc_18001CBC6
0x18001cb7c  xor     ebx, ebx
0x18001cb7e  test    edx, edx
0x18001cb80  jnz     short loc_18001CBC6
0x18001cb82  mov     rcx, cs:?g_hUdkDll@@3PEAUHINSTANCE__@@EA; hLibModule
0x18001cb89  call    cs:__imp_FreeLibrary
0x18001cb8f  mov     rdi, cs:WPP_GLOBAL_Control
0x18001cb96  lea     rsi, WPP_GLOBAL_Control
0x18001cb9d  cmp     rdi, rsi
0x18001cba0  jz      short loc_18001CBC6
0x18001cba2  jmp     short loc_18001CBBA
0x18001cba4  mov     rcx, [rdi+8]; RegistrationHandle
0x18001cba8  test    rcx, rcx
0x18001cbab  jz      short loc_18001CBB7
0x18001cbad  call    cs:__imp_UnregisterTraceGuids
0x18001cbb3  mov     [rdi+8], rbx
0x18001cbb7  mov     rdi, [rdi]
0x18001cbba  test    rdi, rdi
0x18001cbbd  jnz     short loc_18001CBA4
0x18001cbbf  mov     cs:WPP_GLOBAL_Control, rsi
0x18001cbc6  mov     eax, 1
0x18001cbcb  mov     rbx, [rsp+28h+arg_0]
0x18001cbd0  mov     rsi, [rsp+28h+arg_8]
0x18001cbd5  add     rsp, 20h
0x18001cbd9  pop     rdi
0x18001cbda  retn
```
