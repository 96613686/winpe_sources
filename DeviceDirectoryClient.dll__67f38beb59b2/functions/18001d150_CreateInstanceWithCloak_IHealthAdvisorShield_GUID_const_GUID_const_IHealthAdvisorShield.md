# CreateInstanceWithCloak<IHealthAdvisorShield>(_GUID const &,_GUID const &,IHealthAdvisorShield * *)

- ea: `0x18001d150`
- end: `0x18001d2b2`
- name: `??$CreateInstanceWithCloak@UIHealthAdvisorShield@@@@YAJAEBU_GUID@@0PEAPEAUIHealthAdvisorShield@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(int, int, IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f23c`

## callees

- `0x180004060`
- `0x1800050b8`
- `0x18001d150`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001d25f`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001d25f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d1fa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d1fa`

## string_xrefs

- `0x18001d199`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcprotectionstatehelper.cpp`
- `0x18001d213`: `CHR(CoCreateInstance(rclsid, nullptr, CLSCTX_LOCAL_SERVER, riid, (LPVOID*)pObj.GetAddressOf()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CreateInstanceWithCloak<IHealthAdvisorShield>(int a1, int a2, IUnknown **a3)
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
               &CLSID_HealthAdvisorShield,
               0,
               4u,
               &GUID_18e4f715_debb_4a21_abc9_ff7b6f434703,
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
0x18001d150  mov     r11, rsp
0x18001d153  mov     [r11+8], rbx
0x18001d157  mov     [r11+10h], rdx
0x18001d15b  push    rdi
0x18001d15c  sub     rsp, 40h
0x18001d160  mov     qword ptr [r11+10h], 0
0x18001d168  mov     rdi, r8
0x18001d16b  test    r8, r8
0x18001d16e  jnz     short loc_18001D1AA
0x18001d170  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d177  mov     r8d, 80070057h
0x18001d17d  mov     ebx, r8d
0x18001d180  jz      loc_18001D29B
0x18001d186  lea     rax, aCprPpobj; "CPR(ppObj)"
0x18001d18d  mov     [r11-20h], rax
0x18001d191  mov     dword ptr [rsp+48h+ppv], 1E1h
0x18001d199  lea     r9, aOnecoreuapShel_1; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001d1a0  call    McTemplateU0dsqs_EventWriteTransfer
0x18001d1a5  jmp     loc_18001D29B
0x18001d1aa  cmp     qword ptr [r8], 0
0x18001d1ae  jz      short loc_18001D1DC
0x18001d1b0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d1b7  mov     r8d, 80070057h
0x18001d1bd  mov     ebx, r8d
0x18001d1c0  jz      loc_18001D29B
0x18001d1c6  lea     rax, aCbrPpobjNullpt; "CBR(*ppObj == nullptr)"
0x18001d1cd  mov     qword ptr [rsp+48h+dwImpLevel], rax
0x18001d1d2  mov     dword ptr [rsp+48h+ppv], 1E2h
0x18001d1da  jmp     short loc_18001D199
0x18001d1dc  xor     edx, edx; pUnkOuter
0x18001d1de  lea     rax, [rsp+48h+pProxy]
0x18001d1e3  lea     r9, _GUID_18e4f715_debb_4a21_abc9_ff7b6f434703; riid
0x18001d1ea  mov     [rsp+48h+ppv], rax; ppv
0x18001d1ef  lea     rcx, CLSID_HealthAdvisorShield; rclsid
0x18001d1f6  lea     r8d, [rdx+4]; dwClsContext
0x18001d1fa  call    cs:__imp_CoCreateInstance
0x18001d200  mov     ebx, eax
0x18001d202  test    eax, eax
0x18001d204  jns     short loc_18001D22F
0x18001d206  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d20d  jz      loc_18001D29B
0x18001d213  lea     rax, aChrCocreateins; "CHR(CoCreateInstance(rclsid, nullptr, C"...
0x18001d21a  mov     qword ptr [rsp+48h+dwImpLevel], rax
0x18001d21f  mov     dword ptr [rsp+48h+ppv], 1E4h
0x18001d227  mov     r8d, ebx
0x18001d22a  jmp     loc_18001D199
0x18001d22f  mov     rcx, [rsp+48h+pProxy]; pProxy
0x18001d234  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001d237  mov     [rsp+48h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18001d23f  mov     r8d, edx; dwAuthzSvc
0x18001d242  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x18001d24b  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18001d24f  mov     [rsp+48h+dwImpLevel], 3; dwImpLevel
0x18001d257  mov     dword ptr [rsp+48h+ppv], 0; dwAuthnLevel
0x18001d25f  call    cs:__imp_CoSetProxyBlanket
0x18001d265  mov     ebx, eax
0x18001d267  test    eax, eax
0x18001d269  jns     short loc_18001D28A
0x18001d26b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d272  jz      short loc_18001D29B
0x18001d274  lea     rax, aChrCosetproxyb; "CHR(CoSetProxyBlanket( pObj.Get(), 0xFF"...
0x18001d27b  mov     qword ptr [rsp+48h+dwImpLevel], rax
0x18001d280  mov     dword ptr [rsp+48h+ppv], 1EDh
0x18001d288  jmp     short loc_18001D227
0x18001d28a  mov     rax, [rsp+48h+pProxy]
0x18001d28f  mov     [rdi], rax
0x18001d292  mov     [rsp+48h+pProxy], 0
0x18001d29b  lea     rcx, [rsp+48h+pProxy]
0x18001d2a0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d2a5  mov     eax, ebx
0x18001d2a7  mov     rbx, [rsp+48h+arg_0]
0x18001d2ac  add     rsp, 40h
0x18001d2b0  pop     rdi
0x18001d2b1  retn
```
