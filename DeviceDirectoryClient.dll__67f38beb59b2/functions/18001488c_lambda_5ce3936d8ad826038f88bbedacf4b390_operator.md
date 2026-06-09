# _lambda_5ce3936d8ad826038f88bbedacf4b390_::operator()

- ea: `0x18001488c`
- end: `0x180014a53`
- name: `_lambda_5ce3936d8ad826038f88bbedacf4b390_::operator()`
- size: `455`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ad00`

## callees

- `0x180004060`
- `0x1800050b8`
- `0x18001488c`
- `0x180018c8c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800148e1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800148e1`

## string_xrefs

- `0x180014a19`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x180014906`: `CHR(CoCreateInstance( CLSID_DxDiagProvider, nullptr, CLSCTX_INPROC_SERVER, IID_IDxDiagProvider, (LPVOID*) &pDxDiagProvider))`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall lambda_5ce3936d8ad826038f88bbedacf4b390_::operator()(__int64 a1)
{
  HRESULT v2; // eax
  int v3; // edx
  HRESULT *v4; // rcx
  _DWORD *v5; // rax
  int v6; // eax
  int v7; // edx
  _DWORD *v8; // rcx
  int v9; // r8d
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, __int64 *); // rbx
  int v12; // eax
  int v13; // edx
  _DWORD *v14; // rcx
  int v15; // r8d
  int DisplayInfoValues; // eax
  int v17; // edx
  _DWORD *v18; // rcx
  int v19; // r8d
  unsigned int v20; // ebx
  _DWORD v22[2]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v23; // [rsp+38h] [rbp-20h]
  __int64 v24; // [rsp+40h] [rbp-18h]
  LPVOID ppv; // [rsp+80h] [rbp+28h] BYREF
  __int64 v26; // [rsp+88h] [rbp+30h] BYREF
  __int64 v27; // [rsp+90h] [rbp+38h] BYREF
  __int64 v28; // [rsp+98h] [rbp+40h]

  ppv = 0;
  v26 = 0;
  v28 = 0;
  v27 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&ppv);
  v2 = CoCreateInstance(&CLSID_DxDiagProvider, 0, 1u, &IID_IDxDiagProvider, &ppv);
  v4 = *(HRESULT **)(a1 + 8);
  *v4 = v2;
  v5 = *(_DWORD **)(a1 + 8);
  if ( (int)*v5 >= 0 )
  {
    if ( ppv )
    {
      v23 = 0;
      v22[0] = 24;
      v22[1] = 111;
      v24 = 0;
      v6 = (*(__int64 (__fastcall **)(LPVOID, _DWORD *))(*(_QWORD *)ppv + 24LL))(ppv, v22);
      v8 = *(_DWORD **)(a1 + 8);
      *v8 = v6;
      v9 = **(_DWORD **)(a1 + 8);
      if ( v9 >= 0 )
      {
        v10 = ppv;
        v11 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 32LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
        v12 = v11(v10, &v26);
        v14 = *(_DWORD **)(a1 + 8);
        *v14 = v12;
        v15 = **(_DWORD **)(a1 + 8);
        if ( v15 >= 0 )
        {
          DisplayInfoValues = DdcDeviceInfoHelper::GetDisplayInfoValues(v26, *(__int64 **)a1);
          v18 = *(_DWORD **)(a1 + 8);
          *v18 = DisplayInfoValues;
          v19 = **(_DWORD **)(a1 + 8);
          if ( v19 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              (_DWORD)v18,
              v17,
              v19,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
              86,
              "CHR(GetDisplayInfoValues(pDxDiagRoot.Get(), vDisplayInfo))");
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            (_DWORD)v14,
            v13,
            v15,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
            86,
            "CHR(pDxDiagProvider->GetRootContainer( &pDxDiagRoot ))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)v8,
          v7,
          v9,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          86,
          "CHR(pDxDiagProvider->Initialize( &dxDiagInitParam ))");
      }
    }
    else
    {
      *v5 = -2147467259;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          0,
          v3,
          **(_DWORD **)(a1 + 8),
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          86,
          "CBR(pDxDiagProvider != nullptr)");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)v4,
      v3,
      *v5,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      86,
      "CHR(CoCreateInstance( CLSID_DxDiagProvider, nullptr, CLSCTX_INPROC_SERVER, IID_IDxDiagProvider, (LPVOID*) &pDxDiagProvider))");
  }
  v20 = **(_DWORD **)(a1 + 8);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&ppv);
  return v20;
}

```

## disassembly

```asm
0x18001488c  push    rbp
0x18001488e  push    rbx
0x18001488f  push    rsi
0x180014890  push    rdi
0x180014891  mov     rbp, rsp
0x180014894  sub     rsp, 58h
0x180014898  mov     rsi, rcx
0x18001489b  mov     [rbp+arg_0], 0
0x1800148a3  mov     [rbp+arg_8], 0
0x1800148ab  mov     [rbp+arg_18], 0
0x1800148b3  mov     [rbp+arg_10], 0
0x1800148bb  lea     rcx, [rbp+arg_0]
0x1800148bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800148c4  lea     rax, [rbp+arg_0]
0x1800148c8  mov     [rsp+58h+ppv], rax; ppv
0x1800148cd  lea     r9, IID_IDxDiagProvider; riid
0x1800148d4  xor     edx, edx; pUnkOuter
0x1800148d6  lea     r8d, [rdx+1]; dwClsContext
0x1800148da  lea     rcx, CLSID_DxDiagProvider; rclsid
0x1800148e1  call    cs:__imp_CoCreateInstance
0x1800148e7  mov     rcx, [rsi+8]
0x1800148eb  mov     [rcx], eax
0x1800148ed  mov     rax, [rsi+8]
0x1800148f1  mov     r8d, [rax]
0x1800148f4  test    r8d, r8d
0x1800148f7  jns     short loc_180014912
0x1800148f9  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180014900  jz      loc_180014A25
0x180014906  lea     rax, aChrCocreateins_5; "CHR(CoCreateInstance( CLSID_DxDiagProvi"...
0x18001490d  jmp     loc_180014A0C
0x180014912  mov     rcx, [rbp+arg_0]
0x180014916  test    rcx, rcx
0x180014919  jnz     short loc_180014941
0x18001491b  mov     dword ptr [rax], 80004005h
0x180014921  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180014928  jz      loc_180014A25
0x18001492e  mov     r8, [rsi+8]
0x180014932  lea     rax, aCbrPdxdiagprov; "CBR(pDxDiagProvider != nullptr)"
0x180014939  mov     r8d, [r8]
0x18001493c  jmp     loc_180014A0C
0x180014941  mov     [rbp+var_20], 0
0x180014949  mov     [rbp+var_28], 18h
0x180014950  mov     [rbp+var_24], 6Fh ; 'o'
0x180014957  mov     [rbp+var_18], 0
0x18001495f  mov     rax, [rcx]
0x180014962  lea     rdx, [rbp+var_28]
0x180014966  mov     rax, [rax+18h]
0x18001496a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001496f  mov     rcx, [rsi+8]
0x180014973  mov     [rcx], eax
0x180014975  mov     rax, [rsi+8]
0x180014979  mov     r8d, [rax]
0x18001497c  test    r8d, r8d
0x18001497f  jns     short loc_180014997
0x180014981  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180014988  jz      loc_180014A25
0x18001498e  lea     rax, aChrPdxdiagprov_0; "CHR(pDxDiagProvider->Initialize( &dxDia"...
0x180014995  jmp     short loc_180014A0C
0x180014997  mov     rdi, [rbp+arg_0]
0x18001499b  mov     rax, [rdi]
0x18001499e  mov     rbx, [rax+20h]
0x1800149a2  lea     rcx, [rbp+arg_8]
0x1800149a6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800149ab  lea     rdx, [rbp+arg_8]
0x1800149af  mov     rcx, rdi
0x1800149b2  mov     rax, rbx
0x1800149b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149ba  mov     rcx, [rsi+8]
0x1800149be  mov     [rcx], eax
0x1800149c0  mov     rax, [rsi+8]
0x1800149c4  mov     r8d, [rax]
0x1800149c7  test    r8d, r8d
0x1800149ca  jns     short loc_1800149DE
0x1800149cc  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800149d3  jz      short loc_180014A25
0x1800149d5  lea     rax, aChrPdxdiagprov; "CHR(pDxDiagProvider->GetRootContainer( "...
0x1800149dc  jmp     short loc_180014A0C
0x1800149de  mov     rdx, [rsi]
0x1800149e1  mov     rcx, [rbp+arg_8]
0x1800149e5  call    ?GetDisplayInfoValues@DdcDeviceInfoHelper@@CAJPEAUIDxDiagContainer@@AEAV?$vector@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@@2@@std@@@Z; DdcDeviceInfoHelper::GetDisplayInfoValues(IDxDiagContainer *,std::vector<std::unique_ptr<DisplayInfo>> &)
0x1800149ea  mov     rcx, [rsi+8]
0x1800149ee  mov     [rcx], eax
0x1800149f0  mov     rax, [rsi+8]
0x1800149f4  mov     r8d, [rax]
0x1800149f7  test    r8d, r8d
0x1800149fa  jns     short loc_180014A25
0x1800149fc  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180014a03  jz      short loc_180014A25
0x180014a05  lea     rax, aChrGetdisplayi; "CHR(GetDisplayInfoValues(pDxDiagRoot.Ge"...
0x180014a0c  mov     [rsp+58h+var_30], rax
0x180014a11  mov     dword ptr [rsp+58h+ppv], 756h
0x180014a19  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180014a20  call    McTemplateU0dsqs_EventWriteTransfer
0x180014a25  mov     rax, [rsi+8]
0x180014a29  mov     ebx, [rax]
0x180014a2b  lea     rcx, [rbp+arg_10]
0x180014a2f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014a34  nop
0x180014a35  lea     rcx, [rbp+arg_8]
0x180014a39  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014a3e  nop
0x180014a3f  lea     rcx, [rbp+arg_0]
0x180014a43  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014a48  mov     eax, ebx
0x180014a4a  add     rsp, 58h
0x180014a4e  pop     rdi
0x180014a4f  pop     rsi
0x180014a50  pop     rbx
0x180014a51  pop     rbp
0x180014a52  retn
```
