# CreateInstanceWithCloak<IThreatProtectionShield>(_GUID const &,_GUID const &,IThreatProtectionShield * *)

- ea: `0x18001d420`
- end: `0x18001d582`
- name: `??$CreateInstanceWithCloak@UIThreatProtectionShield@@@@YAJAEBU_GUID@@0PEAPEAUIThreatProtectionShield@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(int, int, IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800204a4`

## callees

- `0x180004060`
- `0x1800050b8`
- `0x18001d420`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001d52f`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001d52f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d4ca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d4ca`

## string_xrefs

- `0x18001d469`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcprotectionstatehelper.cpp`
- `0x18001d4e3`: `CHR(CoCreateInstance(rclsid, nullptr, CLSCTX_LOCAL_SERVER, riid, (LPVOID*)pObj.GetAddressOf()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CreateInstanceWithCloak<IThreatProtectionShield>(int a1, int a2, IUnknown **a3)
{
  int v4; // r8d
  HRESULT Instance; // ebx
  char ppv; // [rsp+20h] [rbp-28h]
  const char *dwImpLevel; // [rsp+28h] [rbp-20h]
  IUnknown *pProxy; // [rsp+58h] [rbp+10h] BYREF

  pProxy = 0;
  if ( !a3 )
  {
    v4 = -2147024809;
    Instance = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      dwImpLevel = "CPR(ppObj)";
      ppv = -31;
LABEL_4:
      McTemplateU0dsqs_EventWriteTransfer(
        a1,
        a2,
        v4,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
        ppv,
        (__int64)dwImpLevel);
      goto LABEL_17;
    }
    goto LABEL_17;
  }
  if ( *a3 )
  {
    Instance = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        a1,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
        226,
        (__int64)"CBR(*ppObj == nullptr)");
    goto LABEL_17;
  }
  Instance = CoCreateInstance(
               &CLSID_ThreatProtectionShield,
               0,
               4u,
               &GUID_92cbb2de_4b91_4e74_8020_49d6e52f5860,
               (LPVOID *)&pProxy);
  if ( Instance < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_17;
    dwImpLevel = "CHR(CoCreateInstance(rclsid, nullptr, CLSCTX_LOCAL_SERVER, riid, (LPVOID*)pObj.GetAddressOf()))";
    ppv = -28;
LABEL_12:
    v4 = Instance;
    goto LABEL_4;
  }
  Instance = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
  if ( Instance >= 0 )
  {
    *a3 = pProxy;
    pProxy = 0;
    goto LABEL_17;
  }
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    dwImpLevel = "CHR(CoSetProxyBlanket( pObj.Get(), 0xFFFFFFFFL, 0xffffffff, ( ( OLECHAR * )( INT_PTR )-1 ), 0, 3, nullp"
                 "tr, EOAC_STATIC_CLOAKING))";
    ppv = -19;
    goto LABEL_12;
  }
LABEL_17:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18001d420  mov     r11, rsp
0x18001d423  mov     [r11+8], rbx
0x18001d427  mov     [r11+10h], rdx
0x18001d42b  push    rdi
0x18001d42c  sub     rsp, 40h
0x18001d430  mov     qword ptr [r11+10h], 0
0x18001d438  mov     rdi, r8
0x18001d43b  test    r8, r8
0x18001d43e  jnz     short loc_18001D47A
0x18001d440  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d447  mov     r8d, 80070057h
0x18001d44d  mov     ebx, r8d
0x18001d450  jz      loc_18001D56B
0x18001d456  lea     rax, aCprPpobj; "CPR(ppObj)"
0x18001d45d  mov     [r11-20h], rax
0x18001d461  mov     dword ptr [rsp+48h+ppv], 1E1h
0x18001d469  lea     r9, aOnecoreuapShel_1; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001d470  call    McTemplateU0dsqs_EventWriteTransfer
0x18001d475  jmp     loc_18001D56B
0x18001d47a  cmp     qword ptr [r8], 0
0x18001d47e  jz      short loc_18001D4AC
0x18001d480  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d487  mov     r8d, 80070057h
0x18001d48d  mov     ebx, r8d
0x18001d490  jz      loc_18001D56B
0x18001d496  lea     rax, aCbrPpobjNullpt; "CBR(*ppObj == nullptr)"
0x18001d49d  mov     qword ptr [rsp+48h+dwImpLevel], rax
0x18001d4a2  mov     dword ptr [rsp+48h+ppv], 1E2h
0x18001d4aa  jmp     short loc_18001D469
0x18001d4ac  xor     edx, edx; pUnkOuter
0x18001d4ae  lea     rax, [rsp+48h+pProxy]
0x18001d4b3  lea     r9, _GUID_92cbb2de_4b91_4e74_8020_49d6e52f5860; riid
0x18001d4ba  mov     [rsp+48h+ppv], rax; ppv
0x18001d4bf  lea     rcx, CLSID_ThreatProtectionShield; rclsid
0x18001d4c6  lea     r8d, [rdx+4]; dwClsContext
0x18001d4ca  call    cs:__imp_CoCreateInstance
0x18001d4d0  mov     ebx, eax
0x18001d4d2  test    eax, eax
0x18001d4d4  jns     short loc_18001D4FF
0x18001d4d6  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d4dd  jz      loc_18001D56B
0x18001d4e3  lea     rax, aChrCocreateins; "CHR(CoCreateInstance(rclsid, nullptr, C"...
0x18001d4ea  mov     qword ptr [rsp+48h+dwImpLevel], rax
0x18001d4ef  mov     dword ptr [rsp+48h+ppv], 1E4h
0x18001d4f7  mov     r8d, ebx
0x18001d4fa  jmp     loc_18001D469
0x18001d4ff  mov     rcx, [rsp+48h+pProxy]; pProxy
0x18001d504  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001d507  mov     [rsp+48h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18001d50f  mov     r8d, edx; dwAuthzSvc
0x18001d512  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x18001d51b  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18001d51f  mov     [rsp+48h+dwImpLevel], 3; dwImpLevel
0x18001d527  mov     dword ptr [rsp+48h+ppv], 0; dwAuthnLevel
0x18001d52f  call    cs:__imp_CoSetProxyBlanket
0x18001d535  mov     ebx, eax
0x18001d537  test    eax, eax
0x18001d539  jns     short loc_18001D55A
0x18001d53b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d542  jz      short loc_18001D56B
0x18001d544  lea     rax, aChrCosetproxyb; "CHR(CoSetProxyBlanket( pObj.Get(), 0xFF"...
0x18001d54b  mov     qword ptr [rsp+48h+dwImpLevel], rax
0x18001d550  mov     dword ptr [rsp+48h+ppv], 1EDh
0x18001d558  jmp     short loc_18001D4F7
0x18001d55a  mov     rax, [rsp+48h+pProxy]
0x18001d55f  mov     [rdi], rax
0x18001d562  mov     [rsp+48h+pProxy], 0
0x18001d56b  lea     rcx, [rsp+48h+pProxy]
0x18001d570  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d575  mov     eax, ebx
0x18001d577  mov     rbx, [rsp+48h+arg_0]
0x18001d57c  add     rsp, 40h
0x18001d580  pop     rdi
0x18001d581  retn
```
