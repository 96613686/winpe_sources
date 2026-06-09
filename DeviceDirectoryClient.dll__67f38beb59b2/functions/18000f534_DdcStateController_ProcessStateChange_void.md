# DdcStateController::ProcessStateChange(void)

- ea: `0x18000f534`
- end: `0x18000f5d5`
- name: `?ProcessStateChange@DdcStateController@@SAJXZ`
- size: `161`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c034`
- `0x18000ca4c`
- `0x18000f35c`

## callees

- `0x1800050b8`
- `0x18000f534`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f55f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f55f`

## string_xrefs

- `0x18000f59d`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcstatecontroller.cpp`
- `0x18000f589`: `CHR(pTaskStateHandler->ProcessStateChange())`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 DdcStateController::ProcessStateChange(void)
{
  int v0; // ebx
  int v1; // edx
  int v2; // ecx
  LPVOID v3; // rcx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  v0 = 0;
  ppv = 0;
  if ( CoCreateInstance(&CLSID_TaskStateHandler, 0, 1u, &IID_ITaskStateHandler, &ppv) >= 0 )
  {
    v0 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 24LL))(ppv);
    if ( v0 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v2,
        v1,
        v0,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcstatecontroller.cpp",
        97,
        "CHR(pTaskStateHandler->ProcessStateChange())");
  }
  v3 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18000f534  push    rbx
0x18000f536  sub     rsp, 30h
0x18000f53a  xor     ebx, ebx
0x18000f53c  mov     [rsp+38h+arg_0], rbx
0x18000f541  lea     rax, [rsp+38h+arg_0]
0x18000f546  mov     [rsp+38h+ppv], rax; ppv
0x18000f54b  lea     r9, IID_ITaskStateHandler; riid
0x18000f552  xor     edx, edx; pUnkOuter
0x18000f554  lea     r8d, [rbx+1]; dwClsContext
0x18000f558  lea     rcx, CLSID_TaskStateHandler; rclsid
0x18000f55f  call    cs:__imp_CoCreateInstance
0x18000f565  test    eax, eax
0x18000f567  js      short loc_18000F5AD
0x18000f569  mov     rcx, [rsp+38h+arg_0]
0x18000f56e  mov     rax, [rcx]
0x18000f571  mov     rax, [rax+18h]
0x18000f575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f57a  mov     ebx, eax
0x18000f57c  test    eax, eax
0x18000f57e  jns     short loc_18000F5AD
0x18000f580  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000f587  jz      short loc_18000F5AD
0x18000f589  lea     rax, aChrPtaskstateh; "CHR(pTaskStateHandler->ProcessStateChan"...
0x18000f590  mov     [rsp+38h+var_10], rax
0x18000f595  mov     dword ptr [rsp+38h+ppv], 61h ; 'a'
0x18000f59d  lea     r9, aOnecoreuapShel; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000f5a4  mov     r8d, ebx
0x18000f5a7  call    McTemplateU0dsqs_EventWriteTransfer
0x18000f5ac  nop
0x18000f5ad  mov     rcx, [rsp+38h+arg_0]
0x18000f5b2  test    rcx, rcx
0x18000f5b5  jz      short loc_18000F5CD
0x18000f5b7  mov     [rsp+38h+arg_0], 0
0x18000f5c0  mov     rax, [rcx]
0x18000f5c3  mov     rax, [rax+10h]
0x18000f5c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5cc  nop
0x18000f5cd  mov     eax, ebx
0x18000f5cf  add     rsp, 30h
0x18000f5d3  pop     rbx
0x18000f5d4  retn
```
