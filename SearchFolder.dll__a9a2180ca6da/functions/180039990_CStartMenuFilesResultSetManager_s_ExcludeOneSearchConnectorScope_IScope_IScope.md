# CStartMenuFilesResultSetManager::s_ExcludeOneSearchConnectorScope(IScope *,IScope *)

- ea: `0x180039990`
- end: `0x180039b15`
- name: `?s_ExcludeOneSearchConnectorScope@CStartMenuFilesResultSetManager@@SAJPEAUIScope@@0@Z`
- size: `389`
- prototype: `__int64 __fastcall(struct IScope *, struct IScope *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003435c`

## callees

- `0x180005460`
- `0x1800054b0`
- `0x180005c88`
- `0x18002f49c`
- `0x180039990`
- `0x180051010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180039ac3`
- `OLEAUT32!__imp_SysFreeString` at `0x180039ac3`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x180039a79`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x180039a79`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CStartMenuFilesResultSetManager::s_ExcludeOneSearchConnectorScope(
        struct IScope *a1,
        struct IScope *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r10
  HRESULT v5; // ebx
  LPCWSTR pwzURI; // [rsp+30h] [rbp-20h] BYREF
  __int64 v8; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v9[2]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v10; // [rsp+78h] [rbp+28h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp+30h] BYREF
  IUri *ppURI; // [rsp+88h] [rbp+38h] BYREF

  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(v9);
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, _QWORD *))(*(_QWORD *)v3 + 64LL))(
         v4,
         0,
         &GUID_2c1c7e2e_2d0e_4059_831e_1e6f82335c2e,
         v9);
  if ( v5 >= 0 )
  {
    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v10);
    do
    {
      if ( (*(unsigned int (__fastcall **)(_QWORD, __int64, GUID *, __int64 *, _QWORD))(*(_QWORD *)v9[0] + 24LL))(
             v9[0],
             1,
             &GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0,
             &v10,
             0) )
      {
        break;
      }
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v8);
      v5 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v10 + 120LL))(
             v10,
             &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
             &v8);
      if ( v5 >= 0 )
      {
        pwzURI = 0;
        v5 = (*(__int64 (__fastcall **)(__int64, __int64, LPCWSTR *))(*(_QWORD *)v8 + 40LL))(v8, 2147909632LL, &pwzURI);
        if ( v5 >= 0 )
        {
          ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppURI);
          v5 = CreateUri(pwzURI, 0, 0, &ppURI);
          if ( v5 >= 0 )
          {
            bstrString = 0;
            v5 = ((__int64 (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetSchemeName)(ppURI, &bstrString);
            if ( v5 >= 0 )
              v5 = (*(__int64 (__fastcall **)(struct IScope *, BSTR))(*(_QWORD *)a1 + 88LL))(a1, bstrString);
            SysFreeString(bstrString);
          }
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppURI);
        }
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&pwzURI);
      }
      ATL::CComPtrBase<IPropertyStoreCache>::Release(&v10);
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v8);
    }
    while ( v5 >= 0 );
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v10);
  }
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)v9);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180039990  push    rbp
0x180039992  push    rbx
0x180039993  push    rdi
0x180039994  mov     rbp, rsp
0x180039997  sub     rsp, 50h
0x18003999b  mov     r10, rdx
0x18003999e  mov     rdi, rcx
0x1800399a1  lea     rcx, [rbp+var_10]; void *
0x1800399a5  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800399aa  nop
0x1800399ab  mov     rax, [rdx]
0x1800399ae  lea     r9, [rbp+var_10]
0x1800399b2  lea     r8, _GUID_2c1c7e2e_2d0e_4059_831e_1e6f82335c2e
0x1800399b9  xor     edx, edx
0x1800399bb  mov     rcx, r10
0x1800399be  mov     rax, [rax+40h]
0x1800399c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800399c7  mov     ebx, eax
0x1800399c9  test    eax, eax
0x1800399cb  js      loc_180039B02
0x1800399d1  lea     rcx, [rbp+arg_8]; void *
0x1800399d5  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800399da  nop
0x1800399db  mov     rcx, [rbp+var_10]
0x1800399df  mov     rdx, [rcx]
0x1800399e2  mov     rax, [rdx+18h]
0x1800399e6  mov     [rsp+50h+var_30], 0
0x1800399ef  lea     r9, [rbp+arg_8]
0x1800399f3  lea     r8, _GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0
0x1800399fa  mov     edx, 1
0x1800399ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a04  test    eax, eax
0x180039a06  jnz     loc_180039AF8
0x180039a0c  lea     rcx, [rbp+var_18]; void *
0x180039a10  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180039a15  nop
0x180039a16  mov     rcx, [rbp+arg_8]
0x180039a1a  mov     rax, [rcx]
0x180039a1d  lea     r8, [rbp+var_18]
0x180039a21  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x180039a28  mov     rax, [rax+78h]
0x180039a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a31  mov     ebx, eax
0x180039a33  test    eax, eax
0x180039a35  js      loc_180039ADD
0x180039a3b  mov     [rbp+pwzURI], 0
0x180039a43  mov     rcx, [rbp+var_18]
0x180039a47  mov     rax, [rcx]
0x180039a4a  lea     r8, [rbp+pwzURI]
0x180039a4e  mov     edx, 80068000h
0x180039a53  mov     rax, [rax+28h]
0x180039a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a5c  mov     ebx, eax
0x180039a5e  test    eax, eax
0x180039a60  js      short loc_180039AD4
0x180039a62  lea     rcx, [rbp+ppURI]; void *
0x180039a66  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180039a6b  nop
0x180039a6c  lea     r9, [rbp+ppURI]; ppURI
0x180039a70  xor     r8d, r8d; dwReserved
0x180039a73  xor     edx, edx; dwFlags
0x180039a75  mov     rcx, [rbp+pwzURI]; pwzURI
0x180039a79  call    cs:__imp_CreateUri
0x180039a7f  mov     ebx, eax
0x180039a81  test    eax, eax
0x180039a83  js      short loc_180039ACA
0x180039a85  mov     [rbp+bstrString], 0
0x180039a8d  mov     rcx, [rbp+ppURI]
0x180039a91  mov     rax, [rcx]
0x180039a94  lea     rdx, [rbp+bstrString]
0x180039a98  mov     rax, [rax+98h]
0x180039a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039aa4  mov     ebx, eax
0x180039aa6  test    eax, eax
0x180039aa8  js      short loc_180039ABF
0x180039aaa  mov     rax, [rdi]
0x180039aad  mov     rdx, [rbp+bstrString]
0x180039ab1  mov     rcx, rdi
0x180039ab4  mov     rax, [rax+58h]
0x180039ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039abd  mov     ebx, eax
0x180039abf  mov     rcx, [rbp+bstrString]; bstrString
0x180039ac3  call    cs:__imp_SysFreeString
0x180039ac9  nop
0x180039aca  lea     rcx, [rbp+ppURI]
0x180039ace  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180039ad3  nop
0x180039ad4  lea     rcx, [rbp+pwzURI]; void *
0x180039ad8  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180039add  lea     rcx, [rbp+arg_8]
0x180039ae1  call    ?Release@?$CComPtrBase@UIPropertyStoreCache@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPropertyStoreCache>::Release(void)
0x180039ae6  nop
0x180039ae7  lea     rcx, [rbp+var_18]
0x180039aeb  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180039af0  test    ebx, ebx
0x180039af2  jns     loc_1800399DB
0x180039af8  lea     rcx, [rbp+arg_8]
0x180039afc  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180039b01  nop
0x180039b02  lea     rcx, [rbp+var_10]
0x180039b06  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180039b0b  mov     eax, ebx
0x180039b0d  add     rsp, 50h
0x180039b11  pop     rdi
0x180039b12  pop     rbx
0x180039b13  pop     rbp
0x180039b14  retn
```
