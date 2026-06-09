# TelemetryCorrelationVectorServiceProvider::Increment(IUnknown *)

- ea: `0x180074980`
- end: `0x180074a3c`
- name: `?Increment@TelemetryCorrelationVectorServiceProvider@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUnknown@@@Z`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800723b0`

## callees

- `0x180004a54`
- `0x18001bc08`
- `0x18001bcb0`
- `0x180074980`
- `0x180089010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x1800749d0`
- `SHCORE!IUnknown_QueryService` at `0x1800749d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800749fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800749fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void **__fastcall TelemetryCorrelationVectorServiceProvider::Increment(void **a1, IUnknown *a2)
{
  void *v4; // rsi
  void (__fastcall *v5)(void *, void **); // rbp
  void *v6; // rbx
  void *ppvOut; // [rsp+60h] [rbp+18h] BYREF
  char v9; // [rsp+68h] [rbp+20h] BYREF

  *a1 = 0;
  ppvOut = 0;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppvOut);
  if ( IUnknown_QueryService(
         a2,
         &GUID_2e228ba3_ea25_4378_97b6_d574faeba356,
         &GUID_2e228ba3_ea25_4378_97b6_d574faeba356,
         &ppvOut) >= 0 )
  {
    v4 = ppvOut;
    v5 = *(void (__fastcall **)(void *, void **))(*(_QWORD *)ppvOut + 24LL);
    v6 = *a1;
    if ( *a1 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v9);
      CoTaskMemFree(v6);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v9);
    }
    *a1 = 0;
    v5(v4, a1);
  }
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppvOut);
  return a1;
}

```

## disassembly

```asm
0x180074980  mov     rax, rsp
0x180074983  mov     [rax+10h], rbx
0x180074987  mov     [rax+8], rcx
0x18007498b  push    rbp
0x18007498c  push    rsi
0x18007498d  push    rdi
0x18007498e  sub     rsp, 30h
0x180074992  mov     rbx, rdx
0x180074995  mov     rdi, rcx
0x180074998  mov     dword ptr [rax-28h], 0
0x18007499f  mov     qword ptr [rcx], 0
0x1800749a6  mov     dword ptr [rax-28h], 1
0x1800749ad  mov     qword ptr [rax+18h], 0
0x1800749b5  lea     rcx, [rax+18h]
0x1800749b9  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800749be  lea     r9, [rsp+48h+ppvOut]; ppvOut
0x1800749c3  lea     rdx, _GUID_2e228ba3_ea25_4378_97b6_d574faeba356; guidService
0x1800749ca  mov     r8, rdx; riid
0x1800749cd  mov     rcx, rbx; punk
0x1800749d0  call    cs:__imp_IUnknown_QueryService
0x1800749d6  test    eax, eax
0x1800749d8  js      short loc_180074A21
0x1800749da  mov     rsi, [rsp+48h+ppvOut]
0x1800749df  mov     rax, [rsi]
0x1800749e2  mov     rbp, [rax+18h]
0x1800749e6  mov     rbx, [rdi]
0x1800749e9  test    rbx, rbx
0x1800749ec  jz      short loc_180074A0B
0x1800749ee  lea     rcx, [rsp+48h+arg_18]; this
0x1800749f3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800749f8  mov     rcx, rbx; pv
0x1800749fb  call    cs:__imp_CoTaskMemFree
0x180074a01  lea     rcx, [rsp+48h+arg_18]; this
0x180074a06  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180074a0b  mov     qword ptr [rdi], 0
0x180074a12  mov     rdx, rdi
0x180074a15  mov     rcx, rsi
0x180074a18  mov     rax, rbp
0x180074a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074a20  nop
0x180074a21  lea     rcx, [rsp+48h+ppvOut]
0x180074a26  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180074a2b  mov     rax, rdi
0x180074a2e  mov     rbx, [rsp+48h+arg_8]
0x180074a33  add     rsp, 30h
0x180074a37  pop     rdi
0x180074a38  pop     rsi
0x180074a39  pop     rbp
0x180074a3a  retn
```
