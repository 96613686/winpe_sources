# FileExplorerTelemetryDesktop::GetBrowserSessionId(IUnknown *,_GUID *)

- ea: `0x180014c0c`
- end: `0x180014cf1`
- name: `?GetBrowserSessionId@FileExplorerTelemetryDesktop@@SAJPEAUIUnknown@@PEAU_GUID@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(IUnknown *punk, GUID *value)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001399c`

## callees

- `0x180004a10`
- `0x180005480`
- `0x180014c0c`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180014c4e`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180014c85`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180014cae`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180014c4e`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180014c85`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180014cae`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x180014cd1`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x180014cd1`

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
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punka);
    if ( IUnknown_QueryService(punk, &IID_IShellBrowser, &GUID_00000000_0000_0000_c000_000000000046, (void **)&punka) >= 0 )
    {
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppvOut);
      GUID = IUnknown_QueryService(
               punka,
               &GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1,
               &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
               &ppvOut);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punka);
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
0x180014c0c  mov     [rsp-18h+arg_0], rbx
0x180014c11  push    rbp
0x180014c12  push    rsi
0x180014c13  push    rdi
0x180014c14  mov     rbp, rsp
0x180014c17  sub     rsp, 20h
0x180014c1b  mov     rdi, rcx
0x180014c1e  mov     [rbp+ppvOut], 0
0x180014c26  xorps   xmm0, xmm0
0x180014c29  lea     rcx, [rbp+ppvOut]
0x180014c2d  movdqu  xmmword ptr [rdx], xmm0
0x180014c31  mov     rsi, rdx
0x180014c34  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180014c39  lea     r9, [rbp+ppvOut]; ppvOut
0x180014c3d  mov     rcx, rdi; punk
0x180014c40  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180014c47  lea     rdx, _GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1; guidService
0x180014c4e  call    cs:__imp_IUnknown_QueryService
0x180014c54  mov     ebx, eax
0x180014c56  test    eax, eax
0x180014c58  jns     short loc_180014CC3
0x180014c5a  test    rdi, rdi
0x180014c5d  jz      short loc_180014CD9
0x180014c5f  lea     rcx, [rbp+punk]
0x180014c63  mov     [rbp+punk], 0
0x180014c6b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014c70  lea     r9, [rbp+punk]; ppvOut
0x180014c74  mov     rcx, rdi; punk
0x180014c77  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180014c7e  lea     rdx, IID_IShellBrowser; guidService
0x180014c85  call    cs:__imp_IUnknown_QueryService
0x180014c8b  test    eax, eax
0x180014c8d  js      short loc_180014CB6
0x180014c8f  lea     rcx, [rbp+ppvOut]
0x180014c93  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180014c98  mov     rcx, [rbp+punk]; punk
0x180014c9c  lea     r9, [rbp+ppvOut]; ppvOut
0x180014ca0  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180014ca7  lea     rdx, _GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1; guidService
0x180014cae  call    cs:__imp_IUnknown_QueryService
0x180014cb4  mov     ebx, eax
0x180014cb6  lea     rcx, [rbp+punk]
0x180014cba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014cbf  test    ebx, ebx
0x180014cc1  js      short loc_180014CD9
0x180014cc3  mov     rcx, [rbp+ppvOut]; propBag
0x180014cc7  lea     rdx, propName; "BrowserSessionId"
0x180014cce  mov     r8, rsi; value
0x180014cd1  call    cs:__imp_PSPropertyBag_ReadGUID
0x180014cd7  mov     ebx, eax
0x180014cd9  lea     rcx, [rbp+ppvOut]
0x180014cdd  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180014ce2  mov     eax, ebx
0x180014ce4  mov     rbx, [rsp+20h+arg_0]
0x180014ce9  add     rsp, 20h
0x180014ced  pop     rdi
0x180014cee  pop     rsi
0x180014cef  pop     rbp
0x180014cf0  retn
```
