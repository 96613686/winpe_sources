# TelemetryCorrelationVectorServiceProvider::Increment(IUnknown *)

- ea: `0x180005374`
- end: `0x180005430`
- name: `?Increment@TelemetryCorrelationVectorServiceProvider@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUnknown@@@Z`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001399c`

## callees

- `0x180004a10`
- `0x180004ce0`
- `0x180004d64`
- `0x180005374`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800053c4`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800053c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800053ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800053ef`

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
0x180005374  mov     rax, rsp
0x180005377  mov     [rax+10h], rbx
0x18000537b  mov     [rax+8], rcx
0x18000537f  push    rbp
0x180005380  push    rsi
0x180005381  push    rdi
0x180005382  sub     rsp, 30h
0x180005386  mov     rbx, rdx
0x180005389  mov     rdi, rcx
0x18000538c  mov     dword ptr [rax-28h], 0
0x180005393  mov     qword ptr [rcx], 0
0x18000539a  mov     dword ptr [rax-28h], 1
0x1800053a1  mov     qword ptr [rax+18h], 0
0x1800053a9  lea     rcx, [rax+18h]
0x1800053ad  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800053b2  lea     r9, [rsp+48h+ppvOut]; ppvOut
0x1800053b7  lea     rdx, _GUID_2e228ba3_ea25_4378_97b6_d574faeba356; guidService
0x1800053be  mov     r8, rdx; riid
0x1800053c1  mov     rcx, rbx; punk
0x1800053c4  call    cs:__imp_IUnknown_QueryService
0x1800053ca  test    eax, eax
0x1800053cc  js      short loc_180005415
0x1800053ce  mov     rsi, [rsp+48h+ppvOut]
0x1800053d3  mov     rax, [rsi]
0x1800053d6  mov     rbp, [rax+18h]
0x1800053da  mov     rbx, [rdi]
0x1800053dd  test    rbx, rbx
0x1800053e0  jz      short loc_1800053FF
0x1800053e2  lea     rcx, [rsp+48h+arg_18]; this
0x1800053e7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800053ec  mov     rcx, rbx; pv
0x1800053ef  call    cs:__imp_CoTaskMemFree
0x1800053f5  lea     rcx, [rsp+48h+arg_18]; this
0x1800053fa  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800053ff  mov     qword ptr [rdi], 0
0x180005406  mov     rdx, rdi
0x180005409  mov     rcx, rsi
0x18000540c  mov     rax, rbp
0x18000540f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005414  nop
0x180005415  lea     rcx, [rsp+48h+ppvOut]
0x18000541a  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18000541f  mov     rax, rdi
0x180005422  mov     rbx, [rsp+48h+arg_8]
0x180005427  add     rsp, 30h
0x18000542b  pop     rdi
0x18000542c  pop     rsi
0x18000542d  pop     rbp
0x18000542e  retn
```
