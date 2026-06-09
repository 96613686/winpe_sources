# DllUnregisterServer

- ea: `0x180001650`
- end: `0x180001795`
- name: `DllUnregisterServer`
- size: `325`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180001650`
- `0x180002610`
- `0x180002de8`
- `0x1800057c0`
- `0x18000e4a0`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x180001664`
- `KERNEL32!GetThreadLocale` at `0x180001664`
- `KERNEL32!SetThreadLocale` at `0x180001671`
- `KERNEL32!SetThreadLocale` at `0x180001738`
- `KERNEL32!SetThreadLocale` at `0x180001671`
- `KERNEL32!SetThreadLocale` at `0x180001738`
- `RPCRT4!NdrDllUnregisterProxy` at `0x18000177a`
- `RPCRT4!NdrDllUnregisterProxy` at `0x18000177a`
- `RPCRT4!NdrDllRegisterProxy` at `0x18000175b`
- `RPCRT4!NdrDllRegisterProxy` at `0x18000175b`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // ebp
  const unsigned __int16 *v1; // rdx
  ATL::CAtlModule *v2; // rcx
  HRESULT updated; // ebx
  GUID **v4; // rdi
  __int64 *v5; // rax
  GUID *v6; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v7; // rax
  HRESULT result; // eax
  _QWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF
  __int128 v10; // [rsp+30h] [rbp-18h]

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  if ( !ATL::_pPerfUnRegFunc || (updated = ATL::_pPerfUnRegFunc(), updated >= 0) )
  {
    v4 = off_180018210;
    v5 = (__int64 *)off_180018218;
    if ( off_180018210 < (GUID **)off_180018218 )
    {
      do
      {
        v6 = *v4;
        if ( *v4 )
        {
          v7 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))&v6[3].Data1)();
          updated = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)&v6->Data1, v7, 0);
          if ( updated < 0 )
            goto LABEL_10;
          updated = (*(__int64 (__fastcall **)(_QWORD))v6->Data4)(0);
          if ( updated < 0 )
            goto LABEL_10;
          v5 = (__int64 *)off_180018218;
        }
        ++v4;
      }
      while ( v4 < (GUID **)v5 );
    }
    updated = ATL::AtlUnRegisterTypeLib(off_180018208, v1);
  }
LABEL_10:
  if ( updated >= 0 )
  {
    v9[0] = L"APPID";
    v9[1] = L"{953E4863-7AD1-4DAE-B2BD-108F1D57967B}";
    v10 = 0;
    updated = ATL::CAtlModule::UpdateRegistryFromResource(v2, 0x65u, 0, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  }
  SetThreadLocale(ThreadLocale);
  if ( updated < 0 )
    return updated;
  result = NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, &IID_IPimcContext2);
  if ( result >= 0 )
    return NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, &IID_IPimcContext2);
  return result;
}

```

## disassembly

```asm
0x180001650  mov     [rsp+arg_0], rbx
0x180001655  mov     [rsp+arg_8], rbp
0x18000165a  mov     [rsp+arg_10], rsi
0x18000165f  push    rdi
0x180001660  sub     rsp, 40h
0x180001664  call    cs:__imp_GetThreadLocale
0x18000166a  mov     ecx, 800h; Locale
0x18000166f  mov     ebp, eax
0x180001671  call    cs:__imp_SetThreadLocale
0x180001677  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x18000167e  test    rax, rax
0x180001681  jz      short loc_18000168F
0x180001683  call    cs:__guard_dispatch_icall_fptr
0x180001689  mov     ebx, eax
0x18000168b  test    eax, eax
0x18000168d  js      short loc_1800016FE
0x18000168f  mov     rdi, cs:off_180018210
0x180001696  xor     ebx, ebx
0x180001698  mov     rax, cs:off_180018218
0x18000169f  cmp     rdi, rax
0x1800016a2  jnb     short loc_1800016F0
0x1800016a4  mov     rsi, [rdi]
0x1800016a7  test    rsi, rsi
0x1800016aa  jz      short loc_1800016E3
0x1800016ac  mov     rax, [rsi+30h]
0x1800016b0  call    cs:__guard_dispatch_icall_fptr
0x1800016b6  mov     rcx, [rsi]; rguid
0x1800016b9  xor     r8d, r8d; int
0x1800016bc  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x1800016bf  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x1800016c4  mov     ebx, eax
0x1800016c6  test    eax, eax
0x1800016c8  js      short loc_1800016FE
0x1800016ca  mov     rax, [rsi+8]
0x1800016ce  xor     ecx, ecx
0x1800016d0  call    cs:__guard_dispatch_icall_fptr
0x1800016d6  mov     ebx, eax
0x1800016d8  test    eax, eax
0x1800016da  js      short loc_1800016FE
0x1800016dc  mov     rax, cs:off_180018218
0x1800016e3  add     rdi, 8
0x1800016e7  cmp     rdi, rax
0x1800016ea  jb      short loc_1800016A4
0x1800016ec  test    ebx, ebx
0x1800016ee  js      short loc_180001736
0x1800016f0  mov     rcx, cs:off_180018208; HINSTANCE
0x1800016f7  call    ?AtlUnRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlUnRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x1800016fc  mov     ebx, eax
0x1800016fe  test    ebx, ebx
0x180001700  js      short loc_180001736
0x180001702  xor     r8d, r8d; int
0x180001705  lea     rax, aAppid; "APPID"
0x18000170c  mov     [rsp+48h+var_28], rax
0x180001711  lea     r9, [rsp+48h+var_28]; struct ATL::_ATL_REGMAP_ENTRY *
0x180001716  lea     rax, a953e48637ad14d; "{953E4863-7AD1-4DAE-B2BD-108F1D57967B}"
0x18000171d  xorps   xmm0, xmm0
0x180001720  mov     [rsp+48h+var_20], rax
0x180001725  lea     edx, [r8+65h]; unsigned int
0x180001729  movdqu  [rsp+48h+var_18], xmm0
0x18000172f  call    ?UpdateRegistryFromResource@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResource(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180001734  mov     ebx, eax
0x180001736  mov     ecx, ebp; Locale
0x180001738  call    cs:__imp_SetThreadLocale
0x18000173e  test    ebx, ebx
0x180001740  jns     short loc_180001746
0x180001742  mov     eax, ebx
0x180001744  jmp     short loc_180001780
0x180001746  mov     rcx, cs:hProxyDll; hDll
0x18000174d  lea     r8, IID_IPimcContext2; pclsid
0x180001754  lea     rdx, aProxyFileList; pProxyFileList
0x18000175b  call    cs:__imp_NdrDllRegisterProxy
0x180001761  test    eax, eax
0x180001763  js      short loc_180001780
0x180001765  mov     rcx, cs:hProxyDll; hDll
0x18000176c  lea     r8, IID_IPimcContext2; pclsid
0x180001773  lea     rdx, aProxyFileList; pProxyFileList
0x18000177a  call    cs:__imp_NdrDllUnregisterProxy
0x180001780  mov     rbx, [rsp+48h+arg_0]
0x180001785  mov     rbp, [rsp+48h+arg_8]
0x18000178a  mov     rsi, [rsp+48h+arg_10]
0x18000178f  add     rsp, 40h
0x180001793  pop     rdi
0x180001794  retn
```
