# CRegistryChangeListener::_CleanupCB(void)

- ea: `0x1800093b4`
- end: `0x18000945f`
- name: `?_CleanupCB@CRegistryChangeListener@@AEAAXXZ`
- size: `171`
- prototype: `void __fastcall(PTP_WAIT *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009710`

## callees

- `0x180009320`
- `0x1800093b4`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000944c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000944c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800093e5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800093e5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009416`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009416`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800093d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800093d0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800093c6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800093c6`

## pseudocode

```c
void __fastcall CRegistryChangeListener::_CleanupCB(PTP_WAIT *this)
{
  LPVOID v2; // rcx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  WaitForThreadpoolWaitCallbacks(this[5], 1);
  CloseThreadpoolWait(this[5]);
  this[5] = 0;
  if ( CoInitializeEx(0, 6u) >= 0 )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv) >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, *((unsigned int *)this + 12));
      v2 = ppv;
      *((_DWORD *)this + 12) = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v2 + 16LL))(v2);
    }
    CoUninitialize();
  }
  CRegistryChangeListener::Release((CRegistryChangeListener *)this);
}

```

## disassembly

```asm
0x1800093b4  push    rbx
0x1800093b6  sub     rsp, 30h
0x1800093ba  mov     rbx, rcx
0x1800093bd  mov     edx, 1; fCancelPendingCallbacks
0x1800093c2  mov     rcx, [rcx+28h]; pwa
0x1800093c6  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800093cc  mov     rcx, [rbx+28h]; pwa
0x1800093d0  call    cs:__imp_CloseThreadpoolWait
0x1800093d6  mov     edx, 6; dwCoInit
0x1800093db  mov     qword ptr [rbx+28h], 0
0x1800093e3  xor     ecx, ecx; pvReserved
0x1800093e5  call    cs:__imp_CoInitializeEx
0x1800093eb  test    eax, eax
0x1800093ed  js      short loc_180009452
0x1800093ef  xor     edx, edx; pUnkOuter
0x1800093f1  mov     [rsp+38h+arg_0], 0
0x1800093fa  lea     rax, [rsp+38h+arg_0]
0x1800093ff  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180009406  mov     [rsp+38h+ppv], rax; ppv
0x18000940b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180009412  lea     r8d, [rdx+1]; dwClsContext
0x180009416  call    cs:__imp_CoCreateInstance
0x18000941c  test    eax, eax
0x18000941e  js      short loc_18000944C
0x180009420  mov     rcx, [rsp+38h+arg_0]
0x180009425  mov     edx, [rbx+30h]
0x180009428  mov     rax, [rcx]
0x18000942b  mov     rax, [rax+20h]
0x18000942f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009434  mov     rcx, [rsp+38h+arg_0]
0x180009439  mov     dword ptr [rbx+30h], 0
0x180009440  mov     rax, [rcx]
0x180009443  mov     rax, [rax+10h]
0x180009447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000944c  call    cs:__imp_CoUninitialize
0x180009452  mov     rcx, rbx; this
0x180009455  add     rsp, 30h
0x180009459  pop     rbx
0x18000945a  jmp     ?Release@CRegistryChangeListener@@UEAAKXZ; CRegistryChangeListener::Release(void)
```
