# CreateInstanceWithCloak<IDefenderShield>(_GUID const &,_GUID const &,IDefenderShield * *)

- ea: `0x18001cfe8`
- end: `0x18001d14a`
- name: `??$CreateInstanceWithCloak@UIDefenderShield@@@@YAJAEBU_GUID@@0PEAPEAUIDefenderShield@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(int, int, IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001e8a0`

## callees

- `0x180004060`
- `0x1800050b8`
- `0x18001cfe8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001d0f7`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001d0f7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d092`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d092`

## string_xrefs

- `0x18001d031`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcprotectionstatehelper.cpp`
- `0x18001d0ab`: `CHR(CoCreateInstance(rclsid, nullptr, CLSCTX_LOCAL_SERVER, riid, (LPVOID*)pObj.GetAddressOf()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CreateInstanceWithCloak<IDefenderShield>(int a1, int a2, IUnknown **a3)
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
               &CLSID_DefenderShield,
               0,
               4u,
               &GUID_ff986ead_f547_477f_8f40_2dccad2d76c0,
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
0x18001cfe8  mov     r11, rsp
0x18001cfeb  mov     [r11+8], rbx
0x18001cfef  mov     [r11+10h], rdx
0x18001cff3  push    rdi
0x18001cff4  sub     rsp, 40h
0x18001cff8  mov     qword ptr [r11+10h], 0
0x18001d000  mov     rdi, r8
0x18001d003  test    r8, r8
0x18001d006  jnz     short loc_18001D042
0x18001d008  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d00f  mov     r8d, 80070057h
0x18001d015  mov     ebx, r8d
0x18001d018  jz      loc_18001D133
0x18001d01e  lea     rax, aCprPpobj; "CPR(ppObj)"
0x18001d025  mov     [r11-20h], rax
0x18001d029  mov     dword ptr [rsp+48h+ppv], 1E1h
0x18001d031  lea     r9, aOnecoreuapShel_1; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001d038  call    McTemplateU0dsqs_EventWriteTransfer
0x18001d03d  jmp     loc_18001D133
0x18001d042  cmp     qword ptr [r8], 0
0x18001d046  jz      short loc_18001D074
0x18001d048  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d04f  mov     r8d, 80070057h
0x18001d055  mov     ebx, r8d
0x18001d058  jz      loc_18001D133
0x18001d05e  lea     rax, aCbrPpobjNullpt; "CBR(*ppObj == nullptr)"
0x18001d065  mov     qword ptr [rsp+48h+dwImpLevel], rax
0x18001d06a  mov     dword ptr [rsp+48h+ppv], 1E2h
0x18001d072  jmp     short loc_18001D031
0x18001d074  xor     edx, edx; pUnkOuter
0x18001d076  lea     rax, [rsp+48h+pProxy]
0x18001d07b  lea     r9, _GUID_ff986ead_f547_477f_8f40_2dccad2d76c0; riid
0x18001d082  mov     [rsp+48h+ppv], rax; ppv
0x18001d087  lea     rcx, CLSID_DefenderShield; rclsid
0x18001d08e  lea     r8d, [rdx+4]; dwClsContext
0x18001d092  call    cs:__imp_CoCreateInstance
0x18001d098  mov     ebx, eax
0x18001d09a  test    eax, eax
0x18001d09c  jns     short loc_18001D0C7
0x18001d09e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d0a5  jz      loc_18001D133
0x18001d0ab  lea     rax, aChrCocreateins; "CHR(CoCreateInstance(rclsid, nullptr, C"...
0x18001d0b2  mov     qword ptr [rsp+48h+dwImpLevel], rax
0x18001d0b7  mov     dword ptr [rsp+48h+ppv], 1E4h
0x18001d0bf  mov     r8d, ebx
0x18001d0c2  jmp     loc_18001D031
0x18001d0c7  mov     rcx, [rsp+48h+pProxy]; pProxy
0x18001d0cc  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001d0cf  mov     [rsp+48h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18001d0d7  mov     r8d, edx; dwAuthzSvc
0x18001d0da  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x18001d0e3  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18001d0e7  mov     [rsp+48h+dwImpLevel], 3; dwImpLevel
0x18001d0ef  mov     dword ptr [rsp+48h+ppv], 0; dwAuthnLevel
0x18001d0f7  call    cs:__imp_CoSetProxyBlanket
0x18001d0fd  mov     ebx, eax
0x18001d0ff  test    eax, eax
0x18001d101  jns     short loc_18001D122
0x18001d103  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d10a  jz      short loc_18001D133
0x18001d10c  lea     rax, aChrCosetproxyb; "CHR(CoSetProxyBlanket( pObj.Get(), 0xFF"...
0x18001d113  mov     qword ptr [rsp+48h+dwImpLevel], rax
0x18001d118  mov     dword ptr [rsp+48h+ppv], 1EDh
0x18001d120  jmp     short loc_18001D0BF
0x18001d122  mov     rax, [rsp+48h+pProxy]
0x18001d127  mov     [rdi], rax
0x18001d12a  mov     [rsp+48h+pProxy], 0
0x18001d133  lea     rcx, [rsp+48h+pProxy]
0x18001d138  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d13d  mov     eax, ebx
0x18001d13f  mov     rbx, [rsp+48h+arg_0]
0x18001d144  add     rsp, 40h
0x18001d148  pop     rdi
0x18001d149  retn
```
