# CSyncMgrSynchronize::UpdateAll(void)

- ea: `0x18001afa0`
- end: `0x18001b012`
- name: `?UpdateAll@CSyncMgrSynchronize@@UEAAJXZ`
- size: `114`
- prototype: `__int64 __fastcall(CSyncMgrSynchronize *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18001afa0`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001afcd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001afcd`
- `ole32!CoAllowSetForegroundWindow` at `0x18001afe0`
- `ole32!CoAllowSetForegroundWindow` at `0x18001afe0`

## pseudocode

```c
__int64 __fastcall CSyncMgrSynchronize::UpdateAll(CSyncMgrSynchronize *this)
{
  DWORD v1; // r8d
  unsigned int Instance; // ebx
  IUnknown *pUnk; // [rsp+40h] [rbp+8h] BYREF

  v1 = *((_DWORD *)this + 5);
  pUnk = 0;
  Instance = CoCreateInstance(&CLSID_SyncMgrp, 0, v1, &GUID_fc2fdb45_bb57_44b2_a88a_4bf09b597e12, (LPVOID *)&pUnk);
  if ( !Instance )
  {
    CoAllowSetForegroundWindow(pUnk, 0);
    Instance = ((__int64 (__fastcall *)(IUnknown *))pUnk->lpVtbl[1].Release)(pUnk);
    ((void (__fastcall *)(IUnknown *))pUnk->lpVtbl->Release)(pUnk);
  }
  return Instance;
}

```

## disassembly

```asm
0x18001afa0  push    rbx
0x18001afa2  sub     rsp, 30h
0x18001afa6  mov     r8d, [rcx+14h]; dwClsContext
0x18001afaa  lea     rax, [rsp+38h+pUnk]
0x18001afaf  lea     rcx, CLSID_SyncMgrp; rclsid
0x18001afb6  mov     [rsp+38h+ppv], rax; ppv
0x18001afbb  lea     r9, _GUID_fc2fdb45_bb57_44b2_a88a_4bf09b597e12; riid
0x18001afc2  mov     [rsp+38h+pUnk], 0
0x18001afcb  xor     edx, edx; pUnkOuter
0x18001afcd  call    cs:__imp_CoCreateInstance
0x18001afd3  mov     ebx, eax
0x18001afd5  test    eax, eax
0x18001afd7  jnz     short loc_18001B00A
0x18001afd9  mov     rcx, [rsp+38h+pUnk]; pUnk
0x18001afde  xor     edx, edx; lpvReserved
0x18001afe0  call    cs:__imp_CoAllowSetForegroundWindow
0x18001afe6  mov     rcx, [rsp+38h+pUnk]
0x18001afeb  mov     rax, [rcx]
0x18001afee  mov     rax, [rax+28h]
0x18001aff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aff7  mov     rcx, [rsp+38h+pUnk]
0x18001affc  mov     ebx, eax
0x18001affe  mov     rax, [rcx]
0x18001b001  mov     rax, [rax+10h]
0x18001b005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b00a  mov     eax, ebx
0x18001b00c  add     rsp, 30h
0x18001b010  pop     rbx
0x18001b011  retn
```
