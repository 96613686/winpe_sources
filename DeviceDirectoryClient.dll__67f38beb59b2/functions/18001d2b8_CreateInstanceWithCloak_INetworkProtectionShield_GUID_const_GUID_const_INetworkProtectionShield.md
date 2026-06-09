# CreateInstanceWithCloak<INetworkProtectionShield>(_GUID const &,_GUID const &,INetworkProtectionShield * *)

- ea: `0x18001d2b8`
- end: `0x18001d41a`
- name: `??$CreateInstanceWithCloak@UINetworkProtectionShield@@@@YAJAEBU_GUID@@0PEAPEAUINetworkProtectionShield@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(int, int, IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f2e0`

## callees

- `0x180004060`
- `0x1800050b8`
- `0x18001d2b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001d3c7`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001d3c7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d362`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d362`

## string_xrefs

- `0x18001d301`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcprotectionstatehelper.cpp`
- `0x18001d37b`: `CHR(CoCreateInstance(rclsid, nullptr, CLSCTX_LOCAL_SERVER, riid, (LPVOID*)pObj.GetAddressOf()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CreateInstanceWithCloak<INetworkProtectionShield>(int a1, int a2, IUnknown **a3)
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
               &CLSID_NetworkProtectionShield,
               0,
               4u,
               &GUID_43ebf228_2a94_4ba8_8563_4201fe88be6e,
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
0x18001d2b8  mov     r11, rsp
0x18001d2bb  mov     [r11+8], rbx
0x18001d2bf  mov     [r11+10h], rdx
0x18001d2c3  push    rdi
0x18001d2c4  sub     rsp, 40h
0x18001d2c8  mov     qword ptr [r11+10h], 0
0x18001d2d0  mov     rdi, r8
0x18001d2d3  test    r8, r8
0x18001d2d6  jnz     short loc_18001D312
0x18001d2d8  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d2df  mov     r8d, 80070057h
0x18001d2e5  mov     ebx, r8d
0x18001d2e8  jz      loc_18001D403
0x18001d2ee  lea     rax, aCprPpobj; "CPR(ppObj)"
0x18001d2f5  mov     [r11-20h], rax
0x18001d2f9  mov     dword ptr [rsp+48h+ppv], 1E1h
0x18001d301  lea     r9, aOnecoreuapShel_1; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001d308  call    McTemplateU0dsqs_EventWriteTransfer
0x18001d30d  jmp     loc_18001D403
0x18001d312  cmp     qword ptr [r8], 0
0x18001d316  jz      short loc_18001D344
0x18001d318  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d31f  mov     r8d, 80070057h
0x18001d325  mov     ebx, r8d
0x18001d328  jz      loc_18001D403
0x18001d32e  lea     rax, aCbrPpobjNullpt; "CBR(*ppObj == nullptr)"
0x18001d335  mov     qword ptr [rsp+48h+dwImpLevel], rax
0x18001d33a  mov     dword ptr [rsp+48h+ppv], 1E2h
0x18001d342  jmp     short loc_18001D301
0x18001d344  xor     edx, edx; pUnkOuter
0x18001d346  lea     rax, [rsp+48h+pProxy]
0x18001d34b  lea     r9, _GUID_43ebf228_2a94_4ba8_8563_4201fe88be6e; riid
0x18001d352  mov     [rsp+48h+ppv], rax; ppv
0x18001d357  lea     rcx, CLSID_NetworkProtectionShield; rclsid
0x18001d35e  lea     r8d, [rdx+4]; dwClsContext
0x18001d362  call    cs:__imp_CoCreateInstance
0x18001d368  mov     ebx, eax
0x18001d36a  test    eax, eax
0x18001d36c  jns     short loc_18001D397
0x18001d36e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d375  jz      loc_18001D403
0x18001d37b  lea     rax, aChrCocreateins; "CHR(CoCreateInstance(rclsid, nullptr, C"...
0x18001d382  mov     qword ptr [rsp+48h+dwImpLevel], rax
0x18001d387  mov     dword ptr [rsp+48h+ppv], 1E4h
0x18001d38f  mov     r8d, ebx
0x18001d392  jmp     loc_18001D301
0x18001d397  mov     rcx, [rsp+48h+pProxy]; pProxy
0x18001d39c  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001d39f  mov     [rsp+48h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18001d3a7  mov     r8d, edx; dwAuthzSvc
0x18001d3aa  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x18001d3b3  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18001d3b7  mov     [rsp+48h+dwImpLevel], 3; dwImpLevel
0x18001d3bf  mov     dword ptr [rsp+48h+ppv], 0; dwAuthnLevel
0x18001d3c7  call    cs:__imp_CoSetProxyBlanket
0x18001d3cd  mov     ebx, eax
0x18001d3cf  test    eax, eax
0x18001d3d1  jns     short loc_18001D3F2
0x18001d3d3  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d3da  jz      short loc_18001D403
0x18001d3dc  lea     rax, aChrCosetproxyb; "CHR(CoSetProxyBlanket( pObj.Get(), 0xFF"...
0x18001d3e3  mov     qword ptr [rsp+48h+dwImpLevel], rax
0x18001d3e8  mov     dword ptr [rsp+48h+ppv], 1EDh
0x18001d3f0  jmp     short loc_18001D38F
0x18001d3f2  mov     rax, [rsp+48h+pProxy]
0x18001d3f7  mov     [rdi], rax
0x18001d3fa  mov     [rsp+48h+pProxy], 0
0x18001d403  lea     rcx, [rsp+48h+pProxy]
0x18001d408  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d40d  mov     eax, ebx
0x18001d40f  mov     rbx, [rsp+48h+arg_0]
0x18001d414  add     rsp, 40h
0x18001d418  pop     rdi
0x18001d419  retn
```
