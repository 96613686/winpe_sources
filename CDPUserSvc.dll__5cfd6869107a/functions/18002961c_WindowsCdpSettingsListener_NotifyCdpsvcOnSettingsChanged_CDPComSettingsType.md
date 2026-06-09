# WindowsCdpSettingsListener::NotifyCdpsvcOnSettingsChanged(CDPComSettingsType)

- ea: `0x18002961c`
- end: `0x180029701`
- name: `?NotifyCdpsvcOnSettingsChanged@WindowsCdpSettingsListener@@AEAAXW4CDPComSettingsType@@@Z`
- size: `229`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800294d8`
- `0x180029568`
- `0x18002b8b8`
- `0x180059e5c`

## callees

- `0x180003678`
- `0x180004a58`
- `0x180004a98`
- `0x180005028`
- `0x18000c2f4`
- `0x18002961c`
- `0x18002c570`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029664`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029664`

## string_xrefs

- `0x180029677`: `Failed to CoCreate CDPComSettingsInterop with hr = 0x%08x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WindowsCdpSettingsListener::NotifyCdpsvcOnSettingsChanged(__int64 a1, unsigned int a2)
{
  int v3; // eax
  HRESULT v5; // [rsp+30h] [rbp-48h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v7[32]; // [rsp+40h] [rbp-38h] BYREF

  ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  v5 = CoCreateInstance(
         &GUID_284cacfe_b6f2_461a_90c3_a7acc8353816,
         0,
         4u,
         &GUID_b80e6a0c_f02b_40fc_ac78_fa69f871f71c,
         &ppv);
  if ( v5 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, a2);
    if ( v3 < 0 )
    {
      cdp::detail::StringFormat(
        v7,
        "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Call to cdpsvc to notify that CDP's settings has chang"
        "ed failed with hr = 0x%08x.\"}",
        v3,
        "..\\windowscdpsettingslistener.cpp",
        336,
        v3);
      shared::LogMessage(1, v7);
      std::string::_Tidy_deallocate(v7);
    }
  }
  else
  {
    Log<long &>(1, "Failed to CoCreate CDPComSettingsInterop with hr = 0x%08x.", (unsigned int)&v5);
  }
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
}

```

## disassembly

```asm
0x18002961c  push    rbx
0x18002961e  sub     rsp, 70h
0x180029622  mov     rax, cs:__security_cookie
0x180029629  xor     rax, rsp
0x18002962c  mov     [rsp+78h+var_18], rax
0x180029631  mov     ebx, edx
0x180029633  mov     [rsp+78h+var_40], 0
0x18002963c  lea     rcx, [rsp+78h+var_40]
0x180029641  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029646  lea     rax, [rsp+78h+var_40]
0x18002964b  mov     [rsp+78h+ppv], rax; ppv
0x180029650  lea     r9, _GUID_b80e6a0c_f02b_40fc_ac78_fa69f871f71c; riid
0x180029657  xor     edx, edx; pUnkOuter
0x180029659  lea     r8d, [rdx+4]; dwClsContext
0x18002965d  lea     rcx, _GUID_284cacfe_b6f2_461a_90c3_a7acc8353816; rclsid
0x180029664  call    cs:__imp_CoCreateInstance
0x18002966a  mov     [rsp+78h+var_48], eax
0x18002966e  test    eax, eax
0x180029670  jns     short loc_18002968A
0x180029672  lea     r8, [rsp+78h+var_48]
0x180029677  lea     rdx, aFailedToCocrea; "Failed to CoCreate CDPComSettingsIntero"...
0x18002967e  mov     ecx, 1
0x180029683  call    ??$Log@AEAJ@@YAXW4CDPLogLevel@@PEBDAEAJ@Z; Log<long &>(CDPLogLevel,char const *,long &)
0x180029688  jmp     short loc_1800296E4
0x18002968a  mov     rcx, [rsp+78h+var_40]
0x18002968f  mov     rax, [rcx]
0x180029692  mov     edx, ebx
0x180029694  mov     rax, [rax+20h]
0x180029698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002969d  test    eax, eax
0x18002969f  jns     short loc_1800296E4
0x1800296a1  mov     [rsp+78h+var_50], eax
0x1800296a5  mov     dword ptr [rsp+78h+ppv], 150h
0x1800296ad  lea     r9, aWindowscdpsett_2; "..\\windowscdpsettingslistener.cpp"
0x1800296b4  mov     r8d, eax
0x1800296b7  lea     rdx, aHr0x08xFileSLi_13; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800296be  lea     rcx, [rsp+78h+var_38]
0x1800296c3  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x1800296c8  nop
0x1800296c9  lea     rdx, [rsp+78h+var_38]
0x1800296ce  mov     ecx, 1
0x1800296d3  call    ?LogMessage@shared@@YAXW4CDPLogLevel@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; shared::LogMessage(CDPLogLevel,std::string &)
0x1800296d8  nop
0x1800296d9  lea     rcx, [rsp+78h+var_38]
0x1800296de  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800296e3  nop
0x1800296e4  lea     rcx, [rsp+78h+var_40]
0x1800296e9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800296ee  mov     rcx, [rsp+78h+var_18]
0x1800296f3  xor     rcx, rsp; StackCookie
0x1800296f6  call    __security_check_cookie
0x1800296fb  add     rsp, 70h
0x1800296ff  pop     rbx
0x180029700  retn
```
