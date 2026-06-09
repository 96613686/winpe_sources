# InitFactories(void)

- ea: `0x1400035d0`
- end: `0x1400036c0`
- name: `?InitFactories@@YAJXZ`
- size: `240`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140003ab8`

## callees

- `0x1400035d0`
- `0x140005010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140003637`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140003686`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140003637`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140003686`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140003698`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140003698`
- `WsmSvc!?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z` at `0x1400035de`
- `WsmSvc!?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z` at `0x1400035de`

## pseudocode

```c
__int64 InitFactories(void)
{
  __int64 v0; // rax
  HRESULT v1; // ebx

  v0 = WSManMemory::Alloc(16, 0, 0);
  if ( v0 )
  {
    *(_DWORD *)(v0 + 8) = 0;
    *(_QWORD *)v0 = &CServerClassFactory::`vftable';
    _InterlockedIncrement(&g_ObjectsInProgress);
    g_HostClassFactory = (LPUNKNOWN)v0;
    v1 = CoRegisterClassObject(&CLSID_WSManProvHostWithUserSettings, (LPUNKNOWN)v0, 4u, 0, &g_HostRegisterProfile);
    if ( v1 >= 0 )
    {
      v1 = CoRegisterClassObject(&CLSID_WSManProvHost, g_HostClassFactory, 4u, 0, &g_HostRegisterNoProfile);
      if ( v1 >= 0 )
        return (unsigned int)v1;
      CoRevokeClassObject(g_HostRegisterProfile);
      g_HostRegisterProfile = 0;
    }
    ((void (__fastcall *)(LPUNKNOWN))g_HostClassFactory->lpVtbl->Release)(g_HostClassFactory);
    g_HostClassFactory = 0;
    return (unsigned int)v1;
  }
  g_HostClassFactory = 0;
  return 14;
}

```

## disassembly

```asm
0x1400035d0  push    rbx
0x1400035d2  sub     rsp, 30h
0x1400035d6  xor     edx, edx
0x1400035d8  xor     r8d, r8d
0x1400035db  lea     ecx, [rdx+10h]
0x1400035de  call    cs:__imp_?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1400035e4  mov     [rsp+38h+arg_0], rax
0x1400035e9  test    rax, rax
0x1400035ec  jz      loc_1400036AA
0x1400035f2  lea     rcx, ??_7CServerClassFactory@@6B@; const CServerClassFactory::`vftable'
0x1400035f9  mov     dword ptr [rax+8], 0
0x140003600  mov     [rax], rcx
0x140003603  lock inc cs:?g_ObjectsInProgress@@3JA; long g_ObjectsInProgress
0x14000360a  mov     cs:?g_HostClassFactory@@3PEAUIUnknown@@EA, rax; IUnknown * g_HostClassFactory
0x140003611  test    rax, rax
0x140003614  jz      loc_1400036B5
0x14000361a  xor     r9d, r9d; flags
0x14000361d  lea     rcx, ?g_HostRegisterProfile@@3KA; ulong g_HostRegisterProfile
0x140003624  mov     [rsp+38h+lpdwRegister], rcx; lpdwRegister
0x140003629  mov     rdx, rax; pUnk
0x14000362c  lea     rcx, CLSID_WSManProvHostWithUserSettings; rclsid
0x140003633  lea     r8d, [r9+4]; dwClsContext
0x140003637  call    cs:__imp_CoRegisterClassObject
0x14000363d  mov     ebx, eax
0x14000363f  test    eax, eax
0x140003641  jns     short loc_140003665
0x140003643  mov     rcx, cs:?g_HostClassFactory@@3PEAUIUnknown@@EA; IUnknown * g_HostClassFactory
0x14000364a  mov     rdx, [rcx]
0x14000364d  mov     rax, [rdx+10h]
0x140003651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003656  mov     cs:?g_HostClassFactory@@3PEAUIUnknown@@EA, 0; IUnknown * g_HostClassFactory
0x140003661  mov     eax, ebx
0x140003663  jmp     short loc_1400036BA
0x140003665  mov     rdx, cs:?g_HostClassFactory@@3PEAUIUnknown@@EA; pUnk
0x14000366c  lea     rax, ?g_HostRegisterNoProfile@@3KA; ulong g_HostRegisterNoProfile
0x140003673  xor     r9d, r9d; flags
0x140003676  mov     [rsp+38h+lpdwRegister], rax; lpdwRegister
0x14000367b  lea     rcx, CLSID_WSManProvHost; rclsid
0x140003682  lea     r8d, [r9+4]; dwClsContext
0x140003686  call    cs:__imp_CoRegisterClassObject
0x14000368c  mov     ebx, eax
0x14000368e  test    eax, eax
0x140003690  jns     short loc_140003661
0x140003692  mov     ecx, cs:?g_HostRegisterProfile@@3KA; dwRegister
0x140003698  call    cs:__imp_CoRevokeClassObject
0x14000369e  mov     cs:?g_HostRegisterProfile@@3KA, 0; ulong g_HostRegisterProfile
0x1400036a8  jmp     short loc_140003643
0x1400036aa  mov     cs:?g_HostClassFactory@@3PEAUIUnknown@@EA, 0; IUnknown * g_HostClassFactory
0x1400036b5  mov     eax, 0Eh
0x1400036ba  add     rsp, 30h
0x1400036be  pop     rbx
0x1400036bf  retn
```
