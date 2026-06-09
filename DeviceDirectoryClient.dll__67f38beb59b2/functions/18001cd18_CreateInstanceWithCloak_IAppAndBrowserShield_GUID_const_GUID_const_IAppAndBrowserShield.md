# CreateInstanceWithCloak<IAppAndBrowserShield>(_GUID const &,_GUID const &,IAppAndBrowserShield * *)

- ea: `0x18001cd18`
- end: `0x18001ce7a`
- name: `??$CreateInstanceWithCloak@UIAppAndBrowserShield@@@@YAJAEBU_GUID@@0PEAPEAUIAppAndBrowserShield@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(int, int, IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d588`

## callees

- `0x180004060`
- `0x1800050b8`
- `0x18001cd18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001ce27`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001ce27`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001cdc2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001cdc2`

## string_xrefs

- `0x18001cd61`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcprotectionstatehelper.cpp`
- `0x18001cddb`: `CHR(CoCreateInstance(rclsid, nullptr, CLSCTX_LOCAL_SERVER, riid, (LPVOID*)pObj.GetAddressOf()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CreateInstanceWithCloak<IAppAndBrowserShield>(int a1, int a2, IUnknown **a3)
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
               &CLSID_AppAndBrowserShield,
               0,
               4u,
               &GUID_c21f4dcd_8aa1_4fa9_b115_d31ae2f2244b,
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
0x18001cd18  mov     r11, rsp
0x18001cd1b  mov     [r11+8], rbx
0x18001cd1f  mov     [r11+10h], rdx
0x18001cd23  push    rdi
0x18001cd24  sub     rsp, 40h
0x18001cd28  mov     qword ptr [r11+10h], 0
0x18001cd30  mov     rdi, r8
0x18001cd33  test    r8, r8
0x18001cd36  jnz     short loc_18001CD72
0x18001cd38  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001cd3f  mov     r8d, 80070057h
0x18001cd45  mov     ebx, r8d
0x18001cd48  jz      loc_18001CE63
0x18001cd4e  lea     rax, aCprPpobj; "CPR(ppObj)"
0x18001cd55  mov     [r11-20h], rax
0x18001cd59  mov     dword ptr [rsp+48h+ppv], 1E1h
0x18001cd61  lea     r9, aOnecoreuapShel_1; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001cd68  call    McTemplateU0dsqs_EventWriteTransfer
0x18001cd6d  jmp     loc_18001CE63
0x18001cd72  cmp     qword ptr [r8], 0
0x18001cd76  jz      short loc_18001CDA4
0x18001cd78  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001cd7f  mov     r8d, 80070057h
0x18001cd85  mov     ebx, r8d
0x18001cd88  jz      loc_18001CE63
0x18001cd8e  lea     rax, aCbrPpobjNullpt; "CBR(*ppObj == nullptr)"
0x18001cd95  mov     qword ptr [rsp+48h+dwImpLevel], rax
0x18001cd9a  mov     dword ptr [rsp+48h+ppv], 1E2h
0x18001cda2  jmp     short loc_18001CD61
0x18001cda4  xor     edx, edx; pUnkOuter
0x18001cda6  lea     rax, [rsp+48h+pProxy]
0x18001cdab  lea     r9, _GUID_c21f4dcd_8aa1_4fa9_b115_d31ae2f2244b; riid
0x18001cdb2  mov     [rsp+48h+ppv], rax; ppv
0x18001cdb7  lea     rcx, CLSID_AppAndBrowserShield; rclsid
0x18001cdbe  lea     r8d, [rdx+4]; dwClsContext
0x18001cdc2  call    cs:__imp_CoCreateInstance
0x18001cdc8  mov     ebx, eax
0x18001cdca  test    eax, eax
0x18001cdcc  jns     short loc_18001CDF7
0x18001cdce  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001cdd5  jz      loc_18001CE63
0x18001cddb  lea     rax, aChrCocreateins; "CHR(CoCreateInstance(rclsid, nullptr, C"...
0x18001cde2  mov     qword ptr [rsp+48h+dwImpLevel], rax
0x18001cde7  mov     dword ptr [rsp+48h+ppv], 1E4h
0x18001cdef  mov     r8d, ebx
0x18001cdf2  jmp     loc_18001CD61
0x18001cdf7  mov     rcx, [rsp+48h+pProxy]; pProxy
0x18001cdfc  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001cdff  mov     [rsp+48h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18001ce07  mov     r8d, edx; dwAuthzSvc
0x18001ce0a  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x18001ce13  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18001ce17  mov     [rsp+48h+dwImpLevel], 3; dwImpLevel
0x18001ce1f  mov     dword ptr [rsp+48h+ppv], 0; dwAuthnLevel
0x18001ce27  call    cs:__imp_CoSetProxyBlanket
0x18001ce2d  mov     ebx, eax
0x18001ce2f  test    eax, eax
0x18001ce31  jns     short loc_18001CE52
0x18001ce33  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001ce3a  jz      short loc_18001CE63
0x18001ce3c  lea     rax, aChrCosetproxyb; "CHR(CoSetProxyBlanket( pObj.Get(), 0xFF"...
0x18001ce43  mov     qword ptr [rsp+48h+dwImpLevel], rax
0x18001ce48  mov     dword ptr [rsp+48h+ppv], 1EDh
0x18001ce50  jmp     short loc_18001CDEF
0x18001ce52  mov     rax, [rsp+48h+pProxy]
0x18001ce57  mov     [rdi], rax
0x18001ce5a  mov     [rsp+48h+pProxy], 0
0x18001ce63  lea     rcx, [rsp+48h+pProxy]
0x18001ce68  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ce6d  mov     eax, ebx
0x18001ce6f  mov     rbx, [rsp+48h+arg_0]
0x18001ce74  add     rsp, 40h
0x18001ce78  pop     rdi
0x18001ce79  retn
```
