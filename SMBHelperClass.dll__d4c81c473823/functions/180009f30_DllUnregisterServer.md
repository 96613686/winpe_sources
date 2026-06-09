# DllUnregisterServer

- ea: `0x180009f30`
- end: `0x180009fb5`
- name: `DllUnregisterServer`
- size: `133`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180008c84`
- `0x180009b74`
- `0x180009f30`
- `0x180012010`

## import_xrefs

- `KERNEL32!SetThreadLocale` at `0x180009f47`
- `KERNEL32!SetThreadLocale` at `0x180009fa2`
- `KERNEL32!SetThreadLocale` at `0x180009f47`
- `KERNEL32!SetThreadLocale` at `0x180009fa2`
- `KERNEL32!GetThreadLocale` at `0x180009f3a`
- `KERNEL32!GetThreadLocale` at `0x180009f3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // edi
  unsigned int v1; // edx
  ATL::CAtlComModule *v2; // rcx
  const struct _GUID *v3; // r8
  HRESULT updated; // ebx
  _QWORD v6[2]; // [rsp+20h] [rbp-28h] BYREF
  __int128 v7; // [rsp+30h] [rbp-18h]

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  if ( !ATL::_pPerfUnRegFunc || (updated = ATL::_pPerfUnRegFunc(), updated >= 0) )
    updated = ATL::CAtlComModule::UnregisterServer(v2, v1, v3);
  if ( updated >= 0 )
  {
    v6[0] = L"APPID";
    v6[1] = L"{71962dd6-5a51-4c62-99aa-65f9ee09ae2c}";
    v7 = 0;
    updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 0, (struct ATL::_ATL_REGMAP_ENTRY *)v6);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x180009f30  mov     [rsp+arg_0], rbx
0x180009f35  push    rdi
0x180009f36  sub     rsp, 40h
0x180009f3a  call    cs:__imp_GetThreadLocale
0x180009f40  mov     edi, eax
0x180009f42  mov     ecx, 800h; Locale
0x180009f47  call    cs:__imp_SetThreadLocale
0x180009f4d  nop
0x180009f4e  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180009f55  test    rax, rax
0x180009f58  jz      short loc_180009F65
0x180009f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f5f  mov     ebx, eax
0x180009f61  test    eax, eax
0x180009f63  js      short loc_180009F6C
0x180009f65  call    ?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlComModule::UnregisterServer(int,_GUID const *)
0x180009f6a  mov     ebx, eax
0x180009f6c  test    ebx, ebx
0x180009f6e  js      short loc_180009FA0
0x180009f70  lea     rax, aAppid; "APPID"
0x180009f77  mov     [rsp+48h+var_28], rax
0x180009f7c  lea     rax, a71962dd65a514c; "{71962dd6-5a51-4c62-99aa-65f9ee09ae2c}"
0x180009f83  mov     [rsp+48h+var_20], rax
0x180009f88  xorps   xmm0, xmm0
0x180009f8b  movdqu  [rsp+48h+var_18], xmm0
0x180009f91  lea     r9, [rsp+48h+var_28]; struct ATL::_ATL_REGMAP_ENTRY *
0x180009f96  xor     r8d, r8d; int
0x180009f99  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180009f9e  mov     ebx, eax
0x180009fa0  mov     ecx, edi; Locale
0x180009fa2  call    cs:__imp_SetThreadLocale
0x180009fa8  mov     eax, ebx
0x180009faa  mov     rbx, [rsp+48h+arg_0]
0x180009faf  add     rsp, 40h
0x180009fb3  pop     rdi
0x180009fb4  retn
```
