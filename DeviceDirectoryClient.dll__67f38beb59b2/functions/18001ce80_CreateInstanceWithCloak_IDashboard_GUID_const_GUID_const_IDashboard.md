# CreateInstanceWithCloak<IDashboard>(_GUID const &,_GUID const &,IDashboard * *)

- ea: `0x18001ce80`
- end: `0x18001cfe2`
- name: `??$CreateInstanceWithCloak@UIDashboard@@@@YAJAEBU_GUID@@0PEAPEAUIDashboard@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(int, int, IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020068`

## callees

- `0x180004060`
- `0x1800050b8`
- `0x18001ce80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001cf8f`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001cf8f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001cf2a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001cf2a`

## string_xrefs

- `0x18001cec9`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcprotectionstatehelper.cpp`
- `0x18001cf43`: `CHR(CoCreateInstance(rclsid, nullptr, CLSCTX_LOCAL_SERVER, riid, (LPVOID*)pObj.GetAddressOf()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CreateInstanceWithCloak<IDashboard>(int a1, int a2, IUnknown **a3)
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
  Instance = CoCreateInstance(&CLSID_Dashboard, 0, 4u, &GUID_d71bece8_17b8_4636_832c_d010d4f847f7, (LPVOID *)&pProxy);
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
0x18001ce80  mov     r11, rsp
0x18001ce83  mov     [r11+8], rbx
0x18001ce87  mov     [r11+10h], rdx
0x18001ce8b  push    rdi
0x18001ce8c  sub     rsp, 40h
0x18001ce90  mov     qword ptr [r11+10h], 0
0x18001ce98  mov     rdi, r8
0x18001ce9b  test    r8, r8
0x18001ce9e  jnz     short loc_18001CEDA
0x18001cea0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001cea7  mov     r8d, 80070057h
0x18001cead  mov     ebx, r8d
0x18001ceb0  jz      loc_18001CFCB
0x18001ceb6  lea     rax, aCprPpobj; "CPR(ppObj)"
0x18001cebd  mov     [r11-20h], rax
0x18001cec1  mov     dword ptr [rsp+48h+ppv], 1E1h
0x18001cec9  lea     r9, aOnecoreuapShel_1; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001ced0  call    McTemplateU0dsqs_EventWriteTransfer
0x18001ced5  jmp     loc_18001CFCB
0x18001ceda  cmp     qword ptr [r8], 0
0x18001cede  jz      short loc_18001CF0C
0x18001cee0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001cee7  mov     r8d, 80070057h
0x18001ceed  mov     ebx, r8d
0x18001cef0  jz      loc_18001CFCB
0x18001cef6  lea     rax, aCbrPpobjNullpt; "CBR(*ppObj == nullptr)"
0x18001cefd  mov     qword ptr [rsp+48h+dwImpLevel], rax
0x18001cf02  mov     dword ptr [rsp+48h+ppv], 1E2h
0x18001cf0a  jmp     short loc_18001CEC9
0x18001cf0c  xor     edx, edx; pUnkOuter
0x18001cf0e  lea     rax, [rsp+48h+pProxy]
0x18001cf13  lea     r9, _GUID_d71bece8_17b8_4636_832c_d010d4f847f7; riid
0x18001cf1a  mov     [rsp+48h+ppv], rax; ppv
0x18001cf1f  lea     rcx, CLSID_Dashboard; rclsid
0x18001cf26  lea     r8d, [rdx+4]; dwClsContext
0x18001cf2a  call    cs:__imp_CoCreateInstance
0x18001cf30  mov     ebx, eax
0x18001cf32  test    eax, eax
0x18001cf34  jns     short loc_18001CF5F
0x18001cf36  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001cf3d  jz      loc_18001CFCB
0x18001cf43  lea     rax, aChrCocreateins; "CHR(CoCreateInstance(rclsid, nullptr, C"...
0x18001cf4a  mov     qword ptr [rsp+48h+dwImpLevel], rax
0x18001cf4f  mov     dword ptr [rsp+48h+ppv], 1E4h
0x18001cf57  mov     r8d, ebx
0x18001cf5a  jmp     loc_18001CEC9
0x18001cf5f  mov     rcx, [rsp+48h+pProxy]; pProxy
0x18001cf64  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001cf67  mov     [rsp+48h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18001cf6f  mov     r8d, edx; dwAuthzSvc
0x18001cf72  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x18001cf7b  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18001cf7f  mov     [rsp+48h+dwImpLevel], 3; dwImpLevel
0x18001cf87  mov     dword ptr [rsp+48h+ppv], 0; dwAuthnLevel
0x18001cf8f  call    cs:__imp_CoSetProxyBlanket
0x18001cf95  mov     ebx, eax
0x18001cf97  test    eax, eax
0x18001cf99  jns     short loc_18001CFBA
0x18001cf9b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001cfa2  jz      short loc_18001CFCB
0x18001cfa4  lea     rax, aChrCosetproxyb; "CHR(CoSetProxyBlanket( pObj.Get(), 0xFF"...
0x18001cfab  mov     qword ptr [rsp+48h+dwImpLevel], rax
0x18001cfb0  mov     dword ptr [rsp+48h+ppv], 1EDh
0x18001cfb8  jmp     short loc_18001CF57
0x18001cfba  mov     rax, [rsp+48h+pProxy]
0x18001cfbf  mov     [rdi], rax
0x18001cfc2  mov     [rsp+48h+pProxy], 0
0x18001cfcb  lea     rcx, [rsp+48h+pProxy]
0x18001cfd0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001cfd5  mov     eax, ebx
0x18001cfd7  mov     rbx, [rsp+48h+arg_0]
0x18001cfdc  add     rsp, 40h
0x18001cfe0  pop     rdi
0x18001cfe1  retn
```
