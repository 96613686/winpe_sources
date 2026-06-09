# BdeCfgInitialize(void)

- ea: `0x1800047d0`
- end: `0x1800048f8`
- name: `?BdeCfgInitialize@@YAJXZ`
- size: `296`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000d930`

## callees

- `0x1800047d0`
- `0x180015010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180004811`
- `ole32!CoCreateInstance` at `0x180004811`
- `ole32!CoTaskMemFree` at `0x1800048e5`
- `ole32!CoTaskMemFree` at `0x1800048e5`

## pseudocode

```c
__int64 BdeCfgInitialize(void)
{
  HRESULT v0; // ebx
  struct IVdsService *v1; // rcx
  LPVOID pv[2]; // [rsp+30h] [rbp-10h] BYREF
  struct IVdsService *v4; // [rsp+50h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp+18h] BYREF

  ppv = 0;
  v4 = 0;
  *(_OWORD *)pv = 0;
  v0 = CoCreateInstance(&CLSID_VdsLoader, 0, 4u, &IID_IVdsServiceLoader, &ppv);
  if ( v0 < 0
    || (v0 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IVdsService **))(*(_QWORD *)ppv + 24LL))(ppv, 0, &v4),
        v0 < 0)
    || (v0 = ((__int64 (__fastcall *)(struct IVdsService *))v4->lpVtbl->WaitForServiceReady)(v4), v0 < 0)
    || (v0 = ((__int64 (__fastcall *)(struct IVdsService *, LPVOID *))v4->lpVtbl->GetProperties)(v4, pv), v0 < 0) )
  {
    v1 = v4;
  }
  else
  {
    if ( ((__int64)pv[1] & 0x20) != 0 )
      v0 = ((__int64 (__fastcall *)(struct IVdsService *))v4->lpVtbl->ClearFlags)(v4);
    v1 = 0;
    g_pService = v4;
    v4 = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v1 = v4;
    ppv = 0;
  }
  if ( v1 )
  {
    ((void (__fastcall *)(struct IVdsService *))v1->lpVtbl->Release)(v1);
    v4 = 0;
  }
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1800047d0  mov     [rsp-8+arg_10], rbx
0x1800047d5  push    rbp
0x1800047d6  mov     rbp, rsp
0x1800047d9  sub     rsp, 40h
0x1800047dd  xor     edx, edx; pUnkOuter
0x1800047df  mov     [rbp+arg_8], 0
0x1800047e7  xorps   xmm0, xmm0
0x1800047ea  mov     [rbp+arg_0], 0
0x1800047f2  lea     rax, [rbp+arg_8]
0x1800047f6  lea     r9, IID_IVdsServiceLoader; riid
0x1800047fd  mov     [rsp+40h+ppv], rax; ppv
0x180004802  lea     r8d, [rdx+4]; dwClsContext
0x180004806  lea     rcx, CLSID_VdsLoader; rclsid
0x18000480d  movups  xmmword ptr [rbp+pv], xmm0
0x180004811  call    cs:__imp_CoCreateInstance
0x180004817  mov     ebx, eax
0x180004819  test    eax, eax
0x18000481b  js      short loc_18000489B
0x18000481d  mov     rcx, [rbp+arg_8]
0x180004821  lea     r8, [rbp+arg_0]
0x180004825  xor     edx, edx
0x180004827  mov     rax, [rcx]
0x18000482a  mov     rax, [rax+18h]
0x18000482e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004833  mov     ebx, eax
0x180004835  test    eax, eax
0x180004837  js      short loc_18000489B
0x180004839  mov     rcx, [rbp+arg_0]
0x18000483d  mov     rax, [rcx]
0x180004840  mov     rax, [rax+20h]
0x180004844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004849  mov     ebx, eax
0x18000484b  test    eax, eax
0x18000484d  js      short loc_18000489B
0x18000484f  mov     rcx, [rbp+arg_0]
0x180004853  lea     rdx, [rbp+pv]
0x180004857  mov     rax, [rcx]
0x18000485a  mov     rax, [rax+28h]
0x18000485e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004863  mov     ebx, eax
0x180004865  test    eax, eax
0x180004867  js      short loc_18000489B
0x180004869  mov     edx, 20h ; ' '
0x18000486e  test    byte ptr [rbp+pv+8], dl
0x180004871  jz      short loc_180004888
0x180004873  mov     rcx, [rbp+arg_0]
0x180004877  mov     rax, [rcx]
0x18000487a  mov     rax, [rax+98h]
0x180004881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004886  mov     ebx, eax
0x180004888  mov     rax, [rbp+arg_0]
0x18000488c  xor     ecx, ecx
0x18000488e  mov     cs:?g_pService@@3PEAUIVdsService@@EA, rax; IVdsService * g_pService
0x180004895  mov     [rbp+arg_0], rcx
0x180004899  jmp     short loc_18000489F
0x18000489b  mov     rcx, [rbp+arg_0]
0x18000489f  mov     rdx, [rbp+arg_8]
0x1800048a3  test    rdx, rdx
0x1800048a6  jz      short loc_1800048C3
0x1800048a8  mov     rax, [rdx]
0x1800048ab  mov     rcx, rdx
0x1800048ae  mov     rax, [rax+10h]
0x1800048b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048b7  mov     rcx, [rbp+arg_0]
0x1800048bb  mov     [rbp+arg_8], 0
0x1800048c3  test    rcx, rcx
0x1800048c6  jz      short loc_1800048DC
0x1800048c8  mov     rax, [rcx]
0x1800048cb  mov     rax, [rax+10h]
0x1800048cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048d4  mov     [rbp+arg_0], 0
0x1800048dc  mov     rcx, [rbp+pv]; pv
0x1800048e0  test    rcx, rcx
0x1800048e3  jz      short loc_1800048EB
0x1800048e5  call    cs:__imp_CoTaskMemFree
0x1800048eb  mov     eax, ebx
0x1800048ed  mov     rbx, [rsp+40h+arg_10]
0x1800048f2  add     rsp, 40h
0x1800048f6  pop     rbp
0x1800048f7  retn
```
