# CNetworkExplorerFolder::s_TurnOnDTSharing(HWND__ *)

- ea: `0x18000d878`
- end: `0x18000d971`
- name: `?s_TurnOnDTSharing@CNetworkExplorerFolder@@SAJPEAUHWND__@@@Z`
- size: `249`
- prototype: `__int64 __fastcall(HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a120`

## callees

- `0x18000d878`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d8ab`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d8ab`
- `ole32!CoAllowSetForegroundWindow` at `0x18000d916`
- `ole32!CoAllowSetForegroundWindow` at `0x18000d916`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::s_TurnOnDTSharing(HWND a1)
{
  HRESULT v2; // ebx
  IUnknown *pUnk; // [rsp+48h] [rbp+10h] BYREF
  LPVOID v5; // [rsp+50h] [rbp+18h] BYREF

  v5 = 0;
  v2 = CoCreateInstance(&CLSID_MultiObjectElevationFactory, 0, 1u, &GUID_6fabda16_031e_47e3_b2a2_2339c05ccb9e, &v5);
  if ( v2 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(LPVOID, HWND, __int64 *))(*(_QWORD *)v5 + 24LL))(v5, a1, qword_1800141D8);
    if ( v2 >= 0 )
    {
      pUnk = 0;
      v2 = (*(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, IUnknown **))(*(_QWORD *)v5 + 40LL))(
             v5,
             &CLSID_DetectionAndSharing,
             &GUID_1fda955c_61ff_11da_978c_0008744faab7,
             &pUnk);
      if ( v2 >= 0 )
      {
        v2 = CoAllowSetForegroundWindow(pUnk, 0);
        if ( v2 >= 0 )
          v2 = ((__int64 (__fastcall *)(IUnknown *, HWND, __int64))pUnk->lpVtbl[1].AddRef)(pUnk, a1, 3);
        ((void (__fastcall *)(IUnknown *))pUnk->lpVtbl->Release)(pUnk);
      }
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000d878  mov     r11, rsp
0x18000d87b  mov     [r11+8], rbx
0x18000d87f  push    rdi
0x18000d880  sub     rsp, 30h
0x18000d884  xor     edx, edx; pUnkOuter
0x18000d886  mov     qword ptr [r11+18h], 0
0x18000d88e  mov     rdi, rcx
0x18000d891  lea     rax, [r11+18h]
0x18000d895  lea     r9, _GUID_6fabda16_031e_47e3_b2a2_2339c05ccb9e; riid
0x18000d89c  mov     [r11-18h], rax
0x18000d8a0  lea     rcx, CLSID_MultiObjectElevationFactory; rclsid
0x18000d8a7  lea     r8d, [rdx+1]; dwClsContext
0x18000d8ab  call    cs:__imp_CoCreateInstance
0x18000d8b1  mov     ebx, eax
0x18000d8b3  test    eax, eax
0x18000d8b5  js      loc_18000D964
0x18000d8bb  mov     rcx, [rsp+38h+arg_10]
0x18000d8c0  lea     r8, qword_1800141D8
0x18000d8c7  mov     rdx, rdi
0x18000d8ca  mov     rax, [rcx]
0x18000d8cd  mov     rax, [rax+18h]
0x18000d8d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8d6  mov     ebx, eax
0x18000d8d8  test    eax, eax
0x18000d8da  js      short loc_18000D953
0x18000d8dc  mov     rcx, [rsp+38h+arg_10]
0x18000d8e1  lea     r9, [rsp+38h+pUnk]
0x18000d8e6  mov     [rsp+38h+pUnk], 0
0x18000d8ef  lea     r8, _GUID_1fda955c_61ff_11da_978c_0008744faab7
0x18000d8f6  lea     rdx, CLSID_DetectionAndSharing
0x18000d8fd  mov     rax, [rcx]
0x18000d900  mov     rax, [rax+28h]
0x18000d904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d909  mov     ebx, eax
0x18000d90b  test    eax, eax
0x18000d90d  js      short loc_18000D953
0x18000d90f  mov     rcx, [rsp+38h+pUnk]; pUnk
0x18000d914  xor     edx, edx; lpvReserved
0x18000d916  call    cs:__imp_CoAllowSetForegroundWindow
0x18000d91c  mov     ebx, eax
0x18000d91e  test    eax, eax
0x18000d920  js      short loc_18000D942
0x18000d922  mov     rcx, [rsp+38h+pUnk]
0x18000d927  mov     r9d, 1
0x18000d92d  mov     rdx, rdi
0x18000d930  mov     rax, [rcx]
0x18000d933  lea     r8d, [r9+2]
0x18000d937  mov     rax, [rax+20h]
0x18000d93b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d940  mov     ebx, eax
0x18000d942  mov     rcx, [rsp+38h+pUnk]
0x18000d947  mov     rax, [rcx]
0x18000d94a  mov     rax, [rax+10h]
0x18000d94e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d953  mov     rcx, [rsp+38h+arg_10]
0x18000d958  mov     rax, [rcx]
0x18000d95b  mov     rax, [rax+10h]
0x18000d95f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d964  mov     eax, ebx
0x18000d966  mov     rbx, [rsp+38h+arg_0]
0x18000d96b  add     rsp, 30h
0x18000d96f  pop     rdi
0x18000d970  retn
```
