# DllMain

- ea: `0x1800166dc`
- end: `0x1800167c5`
- name: `DllMain`
- size: `233`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180027614`

## callees

- `0x1800166dc`
- `0x1800167cc`
- `0x180016870`
- `0x1800168fc`
- `0x1800169f0`
- `0x1800173d0`
- `0x180017460`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001670e`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001670e`
- `ntdll!EtwEventRegister` at `0x180016705`
- `ntdll!EtwEventRegister` at `0x180016705`
- `ntdll!EtwEventUnregister` at `0x1800167b6`
- `ntdll!EtwEventUnregister` at `0x1800167b6`
- `fwbase!FwCriticalSectionDestroy` at `0x180016795`
- `fwbase!FwCriticalSectionDestroy` at `0x180016795`
- `fwbase!FwCriticalSectionCreate` at `0x180016761`
- `fwbase!FwCriticalSectionCreate` at `0x180016761`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 *v4; // rdx
  ATL::CComModule *v5; // rcx
  HINSTANCE v6; // r8
  const struct _GUID *v7; // r9
  BOOL result; // eax
  ATL::CComModule *v9; // rcx

  if ( fdwReason == 1 )
  {
    EtwEventRegister(MS_MPS_CLNT_Provider, 0, 0, &g_Provider);
    DisableThreadLibraryCalls(hinstDLL);
    qword_180097FE8 = 1;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_FirewallAPI;
    qword_180097FE0 = 0;
    WPP_GLOBAL_Control = (FwPolicy2 *)&WPP_MAIN_CB;
    WPP_MAIN_CB = 0;
    WppInitUm();
    ATL::CComModule::Init(v5, v4, v6, v7);
    TlgRegisterAggregateProviderEx();
    result = (int)FwCriticalSectionCreate(g_FwPortKeywordLock) >= 0;
    if ( !result )
      return result;
    hProxyDll = hinstDLL;
  }
  else if ( !fdwReason )
  {
    FwCriticalSectionDestroy(g_FwPortKeywordLock, fdwReason, lpvReserved);
    TlgUnregisterAggregateProvider();
    ATL::CComModule::Term(v9);
    WppCleanupUm();
    if ( g_Provider )
    {
      EtwEventUnregister();
      g_Provider = 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800166dc  mov     [rsp+arg_0], rbx
0x1800166e1  push    rdi
0x1800166e2  sub     rsp, 20h
0x1800166e6  mov     rdi, rcx
0x1800166e9  cmp     edx, 1
0x1800166ec  jnz     loc_180016788
0x1800166f2  lea     r9, g_Provider
0x1800166f9  xor     r8d, r8d
0x1800166fc  xor     edx, edx
0x1800166fe  lea     rcx, MS_MPS_CLNT_Provider
0x180016705  call    cs:__imp_EtwEventRegister
0x18001670b  mov     rcx, rdi; hLibModule
0x18001670e  call    cs:__imp_DisableThreadLibraryCalls
0x180016714  lea     rax, WPP_ThisDir_CTLGUID_FirewallAPI
0x18001671b  mov     cs:qword_180097FE8, 1
0x180016726  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18001672d  xor     ebx, ebx
0x18001672f  lea     rax, WPP_MAIN_CB
0x180016736  mov     cs:qword_180097FE0, rbx
0x18001673d  mov     cs:WPP_GLOBAL_Control, rax
0x180016744  mov     cs:WPP_MAIN_CB, rbx
0x18001674b  call    WppInitUm
0x180016750  call    ?Init@CComModule@ATL@@QEAAJPEAU_ATL_OBJMAP_ENTRY30@2@PEAUHINSTANCE__@@PEBU_GUID@@@Z; ATL::CComModule::Init(ATL::_ATL_OBJMAP_ENTRY30 *,HINSTANCE__ *,_GUID const *)
0x180016755  call    TlgRegisterAggregateProviderEx
0x18001675a  lea     rcx, g_FwPortKeywordLock
0x180016761  call    cs:__imp_FwCriticalSectionCreate
0x180016767  not     eax
0x180016769  shr     eax, 1Fh
0x18001676c  cmp     eax, 1
0x18001676f  jnz     short loc_18001677D
0x180016771  mov     cs:hProxyDll, rdi
0x180016778  mov     eax, 1
0x18001677d  mov     rbx, [rsp+28h+arg_0]
0x180016782  add     rsp, 20h
0x180016786  pop     rdi
0x180016787  retn
0x180016788  xor     ebx, ebx
0x18001678a  test    edx, edx
0x18001678c  jnz     short loc_180016778
0x18001678e  lea     rcx, g_FwPortKeywordLock
0x180016795  call    cs:__imp_FwCriticalSectionDestroy
0x18001679b  call    TlgUnregisterAggregateProvider
0x1800167a0  call    ?Term@CComModule@ATL@@QEAAXXZ; ATL::CComModule::Term(void)
0x1800167a5  call    WppCleanupUm
0x1800167aa  mov     rcx, cs:g_Provider
0x1800167b1  test    rcx, rcx
0x1800167b4  jz      short loc_180016778
0x1800167b6  call    cs:__imp_EtwEventUnregister
0x1800167bc  mov     cs:g_Provider, rbx
0x1800167c3  jmp     short loc_180016778
```
