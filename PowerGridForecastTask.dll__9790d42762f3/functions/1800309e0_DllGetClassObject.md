# DllGetClassObject

- ea: `0x1800309e0`
- end: `0x180030a90`
- name: `DllGetClassObject`
- size: `176`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800020c4`
- `0x1800309e0`
- `0x180037010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v5; // ebx
  _DWORD *v6; // rax
  _DWORD *v7; // rdi

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  if ( *(_OWORD *)&CLSID_DeferredChargingTask != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u);
  v7 = v6;
  if ( !v6 )
    return -2147024882;
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<CDeferredChargingTaskHandler,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  return v5;
}

```

## disassembly

```asm
0x1800309e0  mov     [rsp+arg_0], rbx
0x1800309e5  mov     [rsp+arg_8], rsi
0x1800309ea  push    rdi
0x1800309eb  sub     rsp, 20h
0x1800309ef  mov     rbx, r8
0x1800309f2  mov     rsi, rdx
0x1800309f5  test    r8, r8
0x1800309f8  jnz     short loc_180030A01
0x1800309fa  mov     ebx, 80070057h
0x1800309ff  jmp     short loc_180030A7E
0x180030a01  mov     qword ptr [r8], 0
0x180030a08  mov     rax, qword ptr cs:CLSID_DeferredChargingTask.Data1
0x180030a0f  cmp     rax, [rcx]
0x180030a12  jnz     short loc_180030A79
0x180030a14  mov     rax, qword ptr cs:CLSID_DeferredChargingTask.Data4
0x180030a1b  cmp     rax, [rcx+8]
0x180030a1f  jnz     short loc_180030A79
0x180030a21  mov     ecx, 10h; Size
0x180030a26  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030a2b  mov     rdi, rax
0x180030a2e  test    rax, rax
0x180030a31  jz      short loc_180030A72
0x180030a33  lea     rax, ??_7?$CWinTaskClassFactoryT@VCDeferredChargingTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CDeferredChargingTaskHandler,1>::`vftable'
0x180030a3a  mov     [rdi], rax
0x180030a3d  mov     dword ptr [rdi+8], 1
0x180030a44  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180030a4b  mov     rax, [rdi]
0x180030a4e  mov     r8, rbx
0x180030a51  mov     rdx, rsi
0x180030a54  mov     rcx, rdi
0x180030a57  mov     rax, [rax]
0x180030a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a5f  mov     ebx, eax
0x180030a61  mov     rcx, rdi
0x180030a64  mov     rax, [rdi]
0x180030a67  mov     rax, [rax+10h]
0x180030a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a70  jmp     short loc_180030A7E
0x180030a72  mov     ebx, 8007000Eh
0x180030a77  jmp     short loc_180030A7E
0x180030a79  mov     ebx, 80040111h
0x180030a7e  mov     rsi, [rsp+28h+arg_8]
0x180030a83  mov     eax, ebx
0x180030a85  mov     rbx, [rsp+28h+arg_0]
0x180030a8a  add     rsp, 20h
0x180030a8e  pop     rdi
0x180030a8f  retn
```
