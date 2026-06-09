# WaasMedic::CDeferManager::SignalMaintenanceScheduled(void)

- ea: `0x180021190`
- end: `0x180021305`
- name: `?SignalMaintenanceScheduled@CDeferManager@WaasMedic@@QEAAJXZ`
- size: `373`
- prototype: `__int64 __fastcall(WaasMedic::CDeferManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001fe68`

## callees

- `0x18000bbd4`
- `0x180021190`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180021239`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180021239`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800211c0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800211c0`

## string_xrefs

- `0x180021293`: `%systemroot%\System32\usoclient.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaasMedic::CDeferManager::SignalMaintenanceScheduled(WaasMedic::CDeferManager *this)
{
  unsigned int v1; // ebx
  HRESULT v3; // eax
  int v4; // eax
  int dwAuthnLevel; // [rsp+20h] [rbp-28h]
  int dwAuthnLevela; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  IUnknown *pProxy; // [rsp+50h] [rbp+8h] BYREF

  pProxy = 0;
  CoCreateInstance(
    &GUID_9c695035_48d2_4229_8b73_4c70e756e519,
    0,
    4u,
    &GUID_c53f3549_0dbf_429a_8297_c812ba00742d,
    (LPVOID *)&pProxy);
  if ( !pProxy )
  {
    v1 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\engine\\defermanager.cpp",
      (const char *)0x80004003LL,
      dwAuthnLevel);
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    return v1;
  }
  v3 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
  v1 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\engine\\defermanager.cpp",
      (const char *)(unsigned int)v3,
      dwAuthnLevela);
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    return v1;
  }
  v4 = ((__int64 (__fastcall *)(IUnknown *, const wchar_t *, const wchar_t *, const wchar_t *))pProxy->lpVtbl[1].AddRef)(
         pProxy,
         L"Medic",
         L"%systemroot%\\System32\\usoclient.exe",
         L"StartMedic");
  v1 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\engine\\defermanager.cpp",
      (const char *)(unsigned int)v4,
      (int)L"StopMedic");
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    return v1;
  }
  if ( pProxy )
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  return 0;
}

```

## disassembly

```asm
0x180021190  mov     r11, rsp
0x180021193  mov     [r11+8], rcx
0x180021197  push    rbx
0x180021198  sub     rsp, 40h
0x18002119c  mov     qword ptr [r11+8], 0
0x1800211a4  lea     rax, [r11+8]
0x1800211a8  mov     [r11-28h], rax
0x1800211ac  lea     r9, _GUID_c53f3549_0dbf_429a_8297_c812ba00742d; riid
0x1800211b3  xor     edx, edx; pUnkOuter
0x1800211b5  lea     r8d, [rdx+4]; dwClsContext
0x1800211b9  lea     rcx, _GUID_9c695035_48d2_4229_8b73_4c70e756e519; rclsid
0x1800211c0  call    cs:__imp_CoCreateInstance
0x1800211c6  nop
0x1800211c7  mov     rcx, [rsp+48h+pProxy]; pProxy
0x1800211cc  test    rcx, rcx
0x1800211cf  jnz     short loc_18002120E
0x1800211d1  mov     rcx, [rsp+48h]; this
0x1800211d6  mov     ebx, 80004003h
0x1800211db  mov     r9d, ebx; char *
0x1800211de  lea     r8, aOnecoreEnduser_10; "onecore\\enduser\\waasmedic\\lib\\engin"...
0x1800211e5  mov     edx, 0ADh; void *
0x1800211ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800211ef  nop
0x1800211f0  mov     rcx, [rsp+48h+pProxy]
0x1800211f5  test    rcx, rcx
0x1800211f8  jz      short loc_180021207
0x1800211fa  mov     rdx, [rcx]
0x1800211fd  mov     rax, [rdx+10h]
0x180021201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021206  nop
0x180021207  mov     eax, ebx
0x180021209  jmp     loc_1800212FF
0x18002120e  mov     [rsp+48h+dwCapabilities], 0; dwCapabilities
0x180021216  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x18002121f  mov     [rsp+48h+dwImpLevel], 3; dwImpLevel
0x180021227  mov     [rsp+48h+dwAuthnLevel], 0; int
0x18002122f  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180021233  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180021236  mov     r8d, edx; dwAuthzSvc
0x180021239  call    cs:__imp_CoSetProxyBlanket
0x18002123f  mov     ebx, eax
0x180021241  test    eax, eax
0x180021243  jns     short loc_180021278
0x180021245  mov     rcx, [rsp+48h]; this
0x18002124a  mov     r9d, eax; char *
0x18002124d  lea     r8, aOnecoreEnduser_10; "onecore\\enduser\\waasmedic\\lib\\engin"...
0x180021254  mov     edx, 0B6h; void *
0x180021259  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002125e  nop
0x18002125f  mov     rcx, [rsp+48h+pProxy]
0x180021264  test    rcx, rcx
0x180021267  jz      short loc_180021276
0x180021269  mov     rax, [rcx]
0x18002126c  mov     rax, [rax+10h]
0x180021270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021275  nop
0x180021276  jmp     short loc_180021207
0x180021278  mov     rcx, [rsp+48h+pProxy]
0x18002127d  mov     rax, [rcx]
0x180021280  lea     rdx, aStopmedic; "StopMedic"
0x180021287  mov     qword ptr [rsp+48h+dwAuthnLevel], rdx; int
0x18002128c  lea     r9, aStartmedic; "StartMedic"
0x180021293  lea     r8, aSystemrootSyst; "%systemroot%\\System32\\usoclient.exe"
0x18002129a  lea     rdx, aMedic; "Medic"
0x1800212a1  mov     rax, [rax+20h]
0x1800212a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212aa  mov     ebx, eax
0x1800212ac  test    eax, eax
0x1800212ae  jns     short loc_1800212E6
0x1800212b0  mov     rcx, [rsp+48h]; this
0x1800212b5  mov     r9d, eax; char *
0x1800212b8  lea     r8, aOnecoreEnduser_10; "onecore\\enduser\\waasmedic\\lib\\engin"...
0x1800212bf  mov     edx, 0BBh; void *
0x1800212c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800212c9  nop
0x1800212ca  mov     rcx, [rsp+48h+pProxy]
0x1800212cf  test    rcx, rcx
0x1800212d2  jz      short loc_1800212E1
0x1800212d4  mov     rax, [rcx]
0x1800212d7  mov     rax, [rax+10h]
0x1800212db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212e0  nop
0x1800212e1  jmp     loc_180021207
0x1800212e6  mov     rcx, [rsp+48h+pProxy]
0x1800212eb  test    rcx, rcx
0x1800212ee  jz      short loc_1800212FD
0x1800212f0  mov     rax, [rcx]
0x1800212f3  mov     rax, [rax+10h]
0x1800212f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212fc  nop
0x1800212fd  xor     eax, eax
0x1800212ff  add     rsp, 40h
0x180021303  pop     rbx
0x180021304  retn
```
