# IsFreeNetwork(int *)

- ea: `0x18000a68c`
- end: `0x18000a7af`
- name: `?IsFreeNetwork@@YAJPEAH@Z`
- size: `291`
- prototype: `__int64 __fastcall(int *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c034`

## callees

- `0x1800050b8`
- `0x18000a68c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a70d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a70d`

## string_xrefs

- `0x18000a6d5`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcregistrationcontroller.cpp`
- `0x18000a722`: `CHR(CoCreateInstance( CLSID_NetworkListManager, 0, (CLSCTX_INPROC_SERVER| CLSCTX_INPROC_HANDLER| CLSCTX_LOCAL_SERVER| CLSCTX_REMOTE_SERVER), __uuidof(INetworkCostManager), (LPVOID *)pNetworkCostManager.GetAddressOf()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall IsFreeNetwork(int *a1, int a2)
{
  HRESULT v3; // ebx
  int v4; // edx
  int v5; // ecx
  int v6; // edx
  int v7; // ecx
  LPVOID v8; // rcx
  int v10; // [rsp+40h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  ppv = 0;
  v10 = 0;
  if ( a1 )
  {
    *a1 = 0;
    v3 = CoCreateInstance(&CLSID_NetworkListManager, 0, 0x17u, &GUID_dcb00008_570f_4a9b_8d69_199fdba5723b, &ppv);
    if ( v3 >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(LPVOID, int *, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, &v10, 0);
      if ( v3 >= 0 )
      {
        *a1 = v10 & 1;
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v6,
          v3,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
          151,
          "CHR(pNetworkCostManager->GetCost(&dwCost, 0))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v5,
        v4,
        v3,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
        148,
        "CHR(CoCreateInstance( CLSID_NetworkListManager, 0, (CLSCTX_INPROC_SERVER| CLSCTX_INPROC_HANDLER| CLSCTX_LOCAL_SE"
        "RVER| CLSCTX_REMOTE_SERVER), __uuidof(INetworkCostManager), (LPVOID *)pNetworkCostManager.GetAddressOf()))");
    }
  }
  else
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
        139,
        "CPR(pfFreeNetwork)");
  }
  v8 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000a68c  mov     [rsp+arg_10], rbx
0x18000a691  push    rdi
0x18000a692  sub     rsp, 30h
0x18000a696  mov     rdi, rcx
0x18000a699  mov     [rsp+38h+arg_8], 0
0x18000a6a2  mov     [rsp+38h+arg_0], 0
0x18000a6aa  test    rcx, rcx
0x18000a6ad  jnz     short loc_18000A6E9
0x18000a6af  mov     ebx, 80070057h
0x18000a6b4  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000a6bb  jz      loc_18000A782
0x18000a6c1  lea     rax, aCprPffreenetwo; "CPR(pfFreeNetwork)"
0x18000a6c8  mov     [rsp+38h+var_10], rax
0x18000a6cd  mov     dword ptr [rsp+38h+ppv], 8Bh
0x18000a6d5  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000a6dc  mov     r8d, ebx
0x18000a6df  call    McTemplateU0dsqs_EventWriteTransfer
0x18000a6e4  jmp     loc_18000A782
0x18000a6e9  mov     dword ptr [rcx], 0
0x18000a6ef  lea     rax, [rsp+38h+arg_8]
0x18000a6f4  mov     [rsp+38h+ppv], rax; ppv
0x18000a6f9  lea     r9, _GUID_dcb00008_570f_4a9b_8d69_199fdba5723b; riid
0x18000a700  xor     edx, edx; pUnkOuter
0x18000a702  lea     r8d, [rdx+17h]; dwClsContext
0x18000a706  lea     rcx, CLSID_NetworkListManager; rclsid
0x18000a70d  call    cs:__imp_CoCreateInstance
0x18000a713  mov     ebx, eax
0x18000a715  test    eax, eax
0x18000a717  jns     short loc_18000A738
0x18000a719  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000a720  jz      short loc_18000A782
0x18000a722  lea     rax, aChrCocreateins_7; "CHR(CoCreateInstance( CLSID_NetworkList"...
0x18000a729  mov     [rsp+38h+var_10], rax
0x18000a72e  mov     dword ptr [rsp+38h+ppv], 94h
0x18000a736  jmp     short loc_18000A6D5
0x18000a738  mov     rcx, [rsp+38h+arg_8]
0x18000a73d  mov     rax, [rcx]
0x18000a740  xor     r8d, r8d
0x18000a743  lea     rdx, [rsp+38h+arg_0]
0x18000a748  mov     rax, [rax+18h]
0x18000a74c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a751  mov     ebx, eax
0x18000a753  test    eax, eax
0x18000a755  jns     short loc_18000A779
0x18000a757  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000a75e  jz      short loc_18000A782
0x18000a760  lea     rax, aChrPnetworkcos; "CHR(pNetworkCostManager->GetCost(&dwCos"...
0x18000a767  mov     [rsp+38h+var_10], rax
0x18000a76c  mov     dword ptr [rsp+38h+ppv], 97h
0x18000a774  jmp     loc_18000A6D5
0x18000a779  mov     eax, [rsp+38h+arg_0]
0x18000a77d  and     eax, 1
0x18000a780  mov     [rdi], eax
0x18000a782  mov     rcx, [rsp+38h+arg_8]
0x18000a787  test    rcx, rcx
0x18000a78a  jz      short loc_18000A7A2
0x18000a78c  mov     [rsp+38h+arg_8], 0
0x18000a795  mov     rax, [rcx]
0x18000a798  mov     rax, [rax+10h]
0x18000a79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7a1  nop
0x18000a7a2  mov     eax, ebx
0x18000a7a4  mov     rbx, [rsp+38h+arg_10]
0x18000a7a9  add     rsp, 30h
0x18000a7ad  pop     rdi
0x18000a7ae  retn
```
