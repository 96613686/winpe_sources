# WpnService::RegisterClassFactoryCallback(tagComCallData *)

- ea: `0x180011ca0`
- end: `0x180011ded`
- name: `?RegisterClassFactoryCallback@WpnService@@SAJPEAUtagComCallData@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(struct tagComCallData *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003190`
- `0x180011ca0`
- `0x180011df4`
- `0x180012140`
- `0x1800202bc`
- `0x18002830c`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180011d8c`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180011d8c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011d30`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011d30`

## string_xrefs

- `0x180011cb9`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\systemservice\dll\wpnservice.cpp`
- `0x180011d44`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\systemservice\dll\wpnservice.cpp`
- `0x180011da0`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\systemservice\dll\wpnservice.cpp`

## pseudocode

```c
__int64 __fastcall WpnService::RegisterClassFactoryCallback(struct tagComCallData *a1)
{
  unsigned int v1; // ebx
  __int64 v2; // rdx
  LPDWORD *pUserDefined; // rdi
  HRESULT Instance; // eax
  HRESULT v6; // eax
  LPUNKNOWN v7; // rcx
  int ppv; // [rsp+20h] [rbp-18h]
  int ppva; // [rsp+20h] [rbp-18h]
  int ppvb; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPUNKNOWN pUnk; // [rsp+40h] [rbp+8h] BYREF
  __int64 v13; // [rsp+48h] [rbp+10h] BYREF

  if ( !a1 )
  {
    v1 = -2147024809;
    v2 = 287;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\systemservice\\dll\\wpnservice.cpp",
      (const char *)v1,
      ppv);
    return v1;
  }
  pUserDefined = (LPDWORD *)a1->pUserDefined;
  v1 = Microsoft::WRL::Details::RegisterObjects<2>(module);
  if ( (v1 & 0x80000000) != 0 )
  {
    v2 = 292;
    goto LABEL_3;
  }
  if ( IsMultiUsersInSessionSku() )
    return 0;
  pUnk = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
  Instance = CoCreateInstance(
               &GUID_48f4ce0c_bc11_4c9b_a165_2097308f9c25,
               0,
               1u,
               &GUID_00000001_0000_0000_c000_000000000046,
               (LPVOID *)&pUnk);
  v1 = Instance;
  if ( Instance >= 0 )
  {
    v13 = (__int64)(pUserDefined[1] + 2);
    ServiceHostTelemetry::RegisterClassObject<unsigned short const *>(&v13);
    v6 = CoRegisterClassObject(&GUID_1fd1b5a7_5c96_4711_a7c3_fff6d21f93d9, pUnk, 4u, 1u, *pUserDefined);
    v1 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x139,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\systemservice\\dll\\wpnservice.cpp",
        (const char *)(unsigned int)v6,
        ppvb);
      v7 = pUnk;
      if ( pUnk )
      {
        pUnk = 0;
        ((void (__fastcall *)(LPUNKNOWN))v7->lpVtbl->Release)(v7);
      }
      return v1;
    }
    v1 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x131,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\systemservice\\dll\\wpnservice.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
  return v1;
}

```

## disassembly

```asm
0x180011ca0  mov     [rsp+arg_10], rbx
0x180011ca5  push    rdi
0x180011ca6  sub     rsp, 30h
0x180011caa  test    rcx, rcx
0x180011cad  jnz     short loc_180011CD2
0x180011caf  mov     ebx, 80070057h
0x180011cb4  mov     edx, 11Fh; void *
0x180011cb9  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180011cc0  mov     r9d, ebx; char *
0x180011cc3  mov     rcx, [rsp+38h]; this
0x180011cc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011ccd  jmp     loc_180011DE0
0x180011cd2  mov     rdi, [rcx+8]
0x180011cd6  mov     rcx, cs:?module@@3AEAVWpnServiceModule@@EA; WpnServiceModule & module
0x180011cdd  call    ??$RegisterObjects@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBG@Z; Microsoft::WRL::Details::RegisterObjects<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x180011ce2  mov     ebx, eax
0x180011ce4  test    eax, eax
0x180011ce6  jns     short loc_180011CEF
0x180011ce8  mov     edx, 124h
0x180011ced  jmp     short loc_180011CB9
0x180011cef  call    ?IsMultiUsersInSessionSku@@YA_NXZ; IsMultiUsersInSessionSku(void)
0x180011cf4  test    al, al
0x180011cf6  jz      short loc_180011CFF
0x180011cf8  xor     eax, eax
0x180011cfa  jmp     loc_180011DE2
0x180011cff  mov     [rsp+38h+pUnk], 0
0x180011d08  lea     rcx, [rsp+38h+pUnk]
0x180011d0d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011d12  lea     rax, [rsp+38h+pUnk]
0x180011d17  mov     qword ptr [rsp+38h+ppv], rax; int
0x180011d1c  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180011d23  xor     edx, edx; pUnkOuter
0x180011d25  lea     r8d, [rdx+1]; dwClsContext
0x180011d29  lea     rcx, _GUID_48f4ce0c_bc11_4c9b_a165_2097308f9c25; rclsid
0x180011d30  call    cs:__imp_CoCreateInstance
0x180011d36  mov     ebx, eax
0x180011d38  test    eax, eax
0x180011d3a  jns     short loc_180011D57
0x180011d3c  mov     rcx, [rsp+38h]; this
0x180011d41  mov     r9d, eax; char *
0x180011d44  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180011d4b  mov     edx, 131h; void *
0x180011d50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011d55  jmp     short loc_180011DD6
0x180011d57  mov     rax, [rdi+8]
0x180011d5b  add     rax, 8
0x180011d5f  mov     [rsp+38h+arg_8], rax
0x180011d64  lea     rcx, [rsp+38h+arg_8]
0x180011d69  call    ??$RegisterClassObject@PEBG@ServiceHostTelemetry@@SAX$$QEAPEBG@Z; ServiceHostTelemetry::RegisterClassObject<ushort const *>(ushort const * &&)
0x180011d6e  mov     rax, [rdi]
0x180011d71  mov     qword ptr [rsp+38h+ppv], rax; int
0x180011d76  mov     r9d, 1; flags
0x180011d7c  lea     r8d, [r9+3]; dwClsContext
0x180011d80  mov     rdx, [rsp+38h+pUnk]; pUnk
0x180011d85  lea     rcx, _GUID_1fd1b5a7_5c96_4711_a7c3_fff6d21f93d9; rclsid
0x180011d8c  call    cs:__imp_CoRegisterClassObject
0x180011d92  mov     ebx, eax
0x180011d94  test    eax, eax
0x180011d96  jns     short loc_180011DD4
0x180011d98  mov     rcx, [rsp+38h]; this
0x180011d9d  mov     r9d, eax; char *
0x180011da0  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180011da7  mov     edx, 139h; void *
0x180011dac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011db1  nop
0x180011db2  mov     rcx, [rsp+38h+pUnk]
0x180011db7  test    rcx, rcx
0x180011dba  jz      short loc_180011DD2
0x180011dbc  mov     [rsp+38h+pUnk], 0
0x180011dc5  mov     rax, [rcx]
0x180011dc8  mov     rax, [rax+10h]
0x180011dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dd1  nop
0x180011dd2  jmp     short loc_180011DE0
0x180011dd4  xor     ebx, ebx
0x180011dd6  lea     rcx, [rsp+38h+pUnk]
0x180011ddb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011de0  mov     eax, ebx
0x180011de2  mov     rbx, [rsp+38h+arg_10]
0x180011de7  add     rsp, 30h
0x180011deb  pop     rdi
0x180011dec  retn
```
