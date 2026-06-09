# FileExplorerTelemetryDesktop::GetBrowserSessionId(IUnknown *,_GUID *)

- ea: `0x1800734f8`
- end: `0x1800735dd`
- name: `?GetBrowserSessionId@FileExplorerTelemetryDesktop@@SAJPEAUIUnknown@@PEAU_GUID@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(IUnknown *punk, GUID *value)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800723b0`

## callees

- `0x180004a54`
- `0x1800734f8`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18007353a`
- `SHCORE!IUnknown_QueryService` at `0x180073571`
- `SHCORE!IUnknown_QueryService` at `0x18007359a`
- `SHCORE!IUnknown_QueryService` at `0x18007353a`
- `SHCORE!IUnknown_QueryService` at `0x180073571`
- `SHCORE!IUnknown_QueryService` at `0x18007359a`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1800735bd`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1800735bd`

## pseudocode

```c
__int64 __fastcall FileExplorerTelemetryDesktop::GetBrowserSessionId(IUnknown *punk, GUID *value)
{
  HRESULT GUID; // ebx
  void *ppvOut; // [rsp+48h] [rbp+28h] BYREF
  IUnknown *punka; // [rsp+50h] [rbp+30h] BYREF

  ppvOut = 0;
  *value = 0;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppvOut);
  GUID = IUnknown_QueryService(
           punk,
           &GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1,
           &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
           &ppvOut);
  if ( GUID >= 0 )
    goto LABEL_6;
  if ( punk )
  {
    punka = 0;
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&punka);
    if ( IUnknown_QueryService(punk, &IID_IShellBrowser, &GUID_00000000_0000_0000_c000_000000000046, (void **)&punka) >= 0 )
    {
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppvOut);
      GUID = IUnknown_QueryService(
               punka,
               &GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1,
               &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
               &ppvOut);
    }
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&punka);
    if ( GUID >= 0 )
LABEL_6:
      GUID = PSPropertyBag_ReadGUID((IPropertyBag *)ppvOut, L"BrowserSessionId", value);
  }
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppvOut);
  return (unsigned int)GUID;
}

```

## disassembly

```asm
0x1800734f8  mov     [rsp-18h+arg_0], rbx
0x1800734fd  push    rbp
0x1800734fe  push    rsi
0x1800734ff  push    rdi
0x180073500  mov     rbp, rsp
0x180073503  sub     rsp, 20h
0x180073507  mov     rdi, rcx
0x18007350a  mov     [rbp+ppvOut], 0
0x180073512  xorps   xmm0, xmm0
0x180073515  lea     rcx, [rbp+ppvOut]
0x180073519  movdqu  xmmword ptr [rdx], xmm0
0x18007351d  mov     rsi, rdx
0x180073520  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180073525  lea     r9, [rbp+ppvOut]; ppvOut
0x180073529  mov     rcx, rdi; punk
0x18007352c  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180073533  lea     rdx, _GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1; guidService
0x18007353a  call    cs:__imp_IUnknown_QueryService
0x180073540  mov     ebx, eax
0x180073542  test    eax, eax
0x180073544  jns     short loc_1800735AF
0x180073546  test    rdi, rdi
0x180073549  jz      short loc_1800735C5
0x18007354b  lea     rcx, [rbp+punk]
0x18007354f  mov     [rbp+punk], 0
0x180073557  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18007355c  lea     r9, [rbp+punk]; ppvOut
0x180073560  mov     rcx, rdi; punk
0x180073563  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18007356a  lea     rdx, IID_IShellBrowser; guidService
0x180073571  call    cs:__imp_IUnknown_QueryService
0x180073577  test    eax, eax
0x180073579  js      short loc_1800735A2
0x18007357b  lea     rcx, [rbp+ppvOut]
0x18007357f  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180073584  mov     rcx, [rbp+punk]; punk
0x180073588  lea     r9, [rbp+ppvOut]; ppvOut
0x18007358c  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180073593  lea     rdx, _GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1; guidService
0x18007359a  call    cs:__imp_IUnknown_QueryService
0x1800735a0  mov     ebx, eax
0x1800735a2  lea     rcx, [rbp+punk]
0x1800735a6  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800735ab  test    ebx, ebx
0x1800735ad  js      short loc_1800735C5
0x1800735af  mov     rcx, [rbp+ppvOut]; propBag
0x1800735b3  lea     rdx, propName; "BrowserSessionId"
0x1800735ba  mov     r8, rsi; value
0x1800735bd  call    cs:__imp_PSPropertyBag_ReadGUID
0x1800735c3  mov     ebx, eax
0x1800735c5  lea     rcx, [rbp+ppvOut]
0x1800735c9  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800735ce  mov     eax, ebx
0x1800735d0  mov     rbx, [rsp+20h+arg_0]
0x1800735d5  add     rsp, 20h
0x1800735d9  pop     rdi
0x1800735da  pop     rsi
0x1800735db  pop     rbp
0x1800735dc  retn
```
