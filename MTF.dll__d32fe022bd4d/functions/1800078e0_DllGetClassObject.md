# DllGetClassObject

- ea: `0x1800078e0`
- end: `0x180007c91`
- name: `DllGetClassObject`
- size: `945`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180006074`
- `0x1800078e0`
- `0x18002f010`

## string_xrefs

- `0x180007c42`: `mincore\textinput\dev\mtf\dll\com.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  void ***v6; // rbx
  void **v7; // rax
  int v8; // eax
  HRESULT v9; // edi
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !ppv )
    return -2147467261;
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_MtfPrimitive.Data1
    && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_MtfPrimitive.Data4 )
  {
    v6 = &ipx::mtf::g_oPrimitiveFactory;
    ((void (__fastcall *)(void ***))ipx::mtf::g_oPrimitiveFactory[1])(&ipx::mtf::g_oPrimitiveFactory);
    v7 = ipx::mtf::g_oPrimitiveFactory;
  }
  else if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_MtfComposite.Data1
         && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_MtfComposite.Data4 )
  {
    v6 = &ipx::mtf::g_oCompositeFactory;
    ((void (__fastcall *)(void ***))ipx::mtf::g_oCompositeFactory[1])(&ipx::mtf::g_oCompositeFactory);
    v7 = ipx::mtf::g_oCompositeFactory;
  }
  else if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_MtfSuggestionList.Data1
         && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_MtfSuggestionList.Data4 )
  {
    v6 = &ipx::mtf::g_oListFactory;
    ((void (__fastcall *)(void ***))ipx::mtf::g_oListFactory[1])(&ipx::mtf::g_oListFactory);
    v7 = ipx::mtf::g_oListFactory;
  }
  else if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_MtfLattice.Data1
         && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_MtfLattice.Data4 )
  {
    v6 = &ipx::mtf::g_oLatticeFactory;
    ((void (__fastcall *)(void ***))ipx::mtf::g_oLatticeFactory[1])(&ipx::mtf::g_oLatticeFactory);
    v7 = ipx::mtf::g_oLatticeFactory;
  }
  else if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_MtfPropertyBag.Data1
         && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_MtfPropertyBag.Data4 )
  {
    v6 = &ipx::mtf::g_oPropertyBagFactory;
    ((void (__fastcall *)(void ***))ipx::mtf::g_oPropertyBagFactory[1])(&ipx::mtf::g_oPropertyBagFactory);
    v7 = ipx::mtf::g_oPropertyBagFactory;
  }
  else if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_MtfSuggestionInputQuery.Data1
         && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_MtfSuggestionInputQuery.Data4
         || *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_MtfSuggestionInputLatticeQuery.Data1
         && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_MtfSuggestionInputLatticeQuery.Data4 )
  {
    v6 = &ipx::mtf::g_oInputQueryFactory;
    ((void (__fastcall *)(void ***))ipx::mtf::g_oInputQueryFactory[1])(&ipx::mtf::g_oInputQueryFactory);
    v7 = ipx::mtf::g_oInputQueryFactory;
  }
  else if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_MtfInputTypeAttributes.Data1
         && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_MtfInputTypeAttributes.Data4 )
  {
    v6 = (void ***)&ipx::mtf::g_oInputTypeAttributesFactory;
    (*(void (__fastcall **)(void *))(ipx::mtf::g_oInputTypeAttributesFactory + 8LL))(&ipx::mtf::g_oInputTypeAttributesFactory);
    v7 = (void **)ipx::mtf::g_oInputTypeAttributesFactory;
  }
  else if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_MtfSuggestionClient.Data1
         && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_MtfSuggestionClient.Data4
         || *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_MtfSuggestionLatticeClient.Data1
         && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_MtfSuggestionLatticeClient.Data4 )
  {
    v6 = &ipx::mtf::g_oSuggestionClientFactory;
    ((void (__fastcall *)(void ***))ipx::mtf::g_oSuggestionClientFactory[1])(&ipx::mtf::g_oSuggestionClientFactory);
    v7 = ipx::mtf::g_oSuggestionClientFactory;
  }
  else if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_MtfDataSourceManager.Data1
         && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_MtfDataSourceManager.Data4 )
  {
    v6 = &ipx::mtf::g_oDataSourceManagerFactory;
    ((void (__fastcall *)(void ***))ipx::mtf::g_oDataSourceManagerFactory[1])(&ipx::mtf::g_oDataSourceManagerFactory);
    v7 = ipx::mtf::g_oDataSourceManagerFactory;
  }
  else if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_MtfSuggestionClientDCOM.Data1
         && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_MtfSuggestionClientDCOM.Data4 )
  {
    v6 = &ipx::mtf::g_oSuggestionClientDCOMFactory;
    ((void (__fastcall *)(void ***))ipx::mtf::g_oSuggestionClientDCOMFactory[1])(&ipx::mtf::g_oSuggestionClientDCOMFactory);
    v7 = ipx::mtf::g_oSuggestionClientDCOMFactory;
  }
  else if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_MtfDataSourceManagerDCOM.Data1
         && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_MtfDataSourceManagerDCOM.Data4 )
  {
    v6 = &ipx::mtf::g_oDataSourceManagerDCOMFactory;
    ((void (__fastcall *)(void ***))ipx::mtf::g_oDataSourceManagerDCOMFactory[1])(&ipx::mtf::g_oDataSourceManagerDCOMFactory);
    v7 = ipx::mtf::g_oDataSourceManagerDCOMFactory;
  }
  else
  {
    if ( *(_QWORD *)&rclsid->Data1 != *(_QWORD *)&CLSID_MtfSuggestionContextProperty.Data1
      || *(_QWORD *)rclsid->Data4 != *(_QWORD *)CLSID_MtfSuggestionContextProperty.Data4 )
    {
      return -2147024809;
    }
    v6 = &ipx::mtf::g_oContextPropertyFactory;
    ((void (__fastcall *)(void ***))ipx::mtf::g_oContextPropertyFactory[1])(&ipx::mtf::g_oContextPropertyFactory);
    v7 = ipx::mtf::g_oContextPropertyFactory;
  }
  v8 = ((__int64 (__fastcall *)(void ***, const IID *const, LPVOID *))*v7)(v6, riid, ppv);
  v9 = v8;
  if ( v8 >= 0 )
  {
    ((void (__fastcall *)(void ***))(*v6)[2])(v6);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\dll\\com.cpp",
      (const char *)(unsigned int)v8,
      v10);
    ((void (__fastcall *)(void ***))(*v6)[2])(v6);
    return v9;
  }
}

```

## disassembly

```asm
0x1800078e0  mov     [rsp+arg_0], rbx
0x1800078e5  mov     [rsp+arg_8], rsi
0x1800078ea  push    rdi; int
0x1800078eb  sub     rsp, 20h
0x1800078ef  mov     rdi, r8
0x1800078f2  mov     rsi, rdx
0x1800078f5  test    r8, r8
0x1800078f8  jnz     short loc_180007904
0x1800078fa  mov     eax, 80004003h
0x1800078ff  jmp     loc_180007C81
0x180007904  mov     rax, [rcx]
0x180007907  cmp     rax, qword ptr cs:CLSID_MtfPrimitive.Data1
0x18000790e  jnz     short loc_180007943
0x180007910  mov     rax, [rcx+8]
0x180007914  cmp     rax, qword ptr cs:CLSID_MtfPrimitive.Data4
0x18000791b  jnz     short loc_180007943
0x18000791d  mov     rax, cs:?g_oPrimitiveFactory@mtf@ipx@@3VPrimitiveFactory@12@A; ipx::mtf::PrimitiveFactory ipx::mtf::g_oPrimitiveFactory
0x180007924  lea     rbx, ?g_oPrimitiveFactory@mtf@ipx@@3VPrimitiveFactory@12@A; ipx::mtf::PrimitiveFactory ipx::mtf::g_oPrimitiveFactory
0x18000792b  mov     rcx, rbx
0x18000792e  mov     rax, [rax+8]
0x180007932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007937  mov     rax, cs:?g_oPrimitiveFactory@mtf@ipx@@3VPrimitiveFactory@12@A; ipx::mtf::PrimitiveFactory ipx::mtf::g_oPrimitiveFactory
0x18000793e  jmp     loc_180007C23
0x180007943  mov     rax, [rcx]
0x180007946  cmp     rax, qword ptr cs:CLSID_MtfComposite.Data1
0x18000794d  jnz     short loc_180007982
0x18000794f  mov     rax, [rcx+8]
0x180007953  cmp     rax, qword ptr cs:CLSID_MtfComposite.Data4
0x18000795a  jnz     short loc_180007982
0x18000795c  mov     rax, cs:?g_oCompositeFactory@mtf@ipx@@3VCompositeFactory@12@A; ipx::mtf::CompositeFactory ipx::mtf::g_oCompositeFactory
0x180007963  lea     rbx, ?g_oCompositeFactory@mtf@ipx@@3VCompositeFactory@12@A; ipx::mtf::CompositeFactory ipx::mtf::g_oCompositeFactory
0x18000796a  mov     rcx, rbx
0x18000796d  mov     rax, [rax+8]
0x180007971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007976  mov     rax, cs:?g_oCompositeFactory@mtf@ipx@@3VCompositeFactory@12@A; ipx::mtf::CompositeFactory ipx::mtf::g_oCompositeFactory
0x18000797d  jmp     loc_180007C23
0x180007982  mov     rax, [rcx]
0x180007985  cmp     rax, qword ptr cs:CLSID_MtfSuggestionList.Data1
0x18000798c  jnz     short loc_1800079C1
0x18000798e  mov     rax, [rcx+8]
0x180007992  cmp     rax, qword ptr cs:CLSID_MtfSuggestionList.Data4
0x180007999  jnz     short loc_1800079C1
0x18000799b  mov     rax, cs:?g_oListFactory@mtf@ipx@@3VListFactory@12@A; ipx::mtf::ListFactory ipx::mtf::g_oListFactory
0x1800079a2  lea     rbx, ?g_oListFactory@mtf@ipx@@3VListFactory@12@A; ipx::mtf::ListFactory ipx::mtf::g_oListFactory
0x1800079a9  mov     rcx, rbx
0x1800079ac  mov     rax, [rax+8]
0x1800079b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079b5  mov     rax, cs:?g_oListFactory@mtf@ipx@@3VListFactory@12@A; ipx::mtf::ListFactory ipx::mtf::g_oListFactory
0x1800079bc  jmp     loc_180007C23
0x1800079c1  mov     rax, [rcx]
0x1800079c4  cmp     rax, qword ptr cs:CLSID_MtfLattice.Data1
0x1800079cb  jnz     short loc_180007A00
0x1800079cd  mov     rax, [rcx+8]
0x1800079d1  cmp     rax, qword ptr cs:CLSID_MtfLattice.Data4
0x1800079d8  jnz     short loc_180007A00
0x1800079da  mov     rax, cs:?g_oLatticeFactory@mtf@ipx@@3VLatticeFactory@12@A; ipx::mtf::LatticeFactory ipx::mtf::g_oLatticeFactory
0x1800079e1  lea     rbx, ?g_oLatticeFactory@mtf@ipx@@3VLatticeFactory@12@A; ipx::mtf::LatticeFactory ipx::mtf::g_oLatticeFactory
0x1800079e8  mov     rcx, rbx
0x1800079eb  mov     rax, [rax+8]
0x1800079ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079f4  mov     rax, cs:?g_oLatticeFactory@mtf@ipx@@3VLatticeFactory@12@A; ipx::mtf::LatticeFactory ipx::mtf::g_oLatticeFactory
0x1800079fb  jmp     loc_180007C23
0x180007a00  mov     rax, [rcx]
0x180007a03  cmp     rax, qword ptr cs:CLSID_MtfPropertyBag.Data1
0x180007a0a  jnz     short loc_180007A3F
0x180007a0c  mov     rax, [rcx+8]
0x180007a10  cmp     rax, qword ptr cs:CLSID_MtfPropertyBag.Data4
0x180007a17  jnz     short loc_180007A3F
0x180007a19  mov     rax, cs:?g_oPropertyBagFactory@mtf@ipx@@3VPropertyBagFactory@12@A; ipx::mtf::PropertyBagFactory ipx::mtf::g_oPropertyBagFactory
0x180007a20  lea     rbx, ?g_oPropertyBagFactory@mtf@ipx@@3VPropertyBagFactory@12@A; ipx::mtf::PropertyBagFactory ipx::mtf::g_oPropertyBagFactory
0x180007a27  mov     rcx, rbx
0x180007a2a  mov     rax, [rax+8]
0x180007a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a33  mov     rax, cs:?g_oPropertyBagFactory@mtf@ipx@@3VPropertyBagFactory@12@A; ipx::mtf::PropertyBagFactory ipx::mtf::g_oPropertyBagFactory
0x180007a3a  jmp     loc_180007C23
0x180007a3f  mov     rax, [rcx]
0x180007a42  cmp     rax, qword ptr cs:CLSID_MtfSuggestionInputQuery.Data1
0x180007a49  jnz     short loc_180007A58
0x180007a4b  mov     rax, [rcx+8]
0x180007a4f  cmp     rax, qword ptr cs:CLSID_MtfSuggestionInputQuery.Data4
0x180007a56  jz      short loc_180007A71
0x180007a58  mov     rax, [rcx]
0x180007a5b  cmp     rax, qword ptr cs:CLSID_MtfSuggestionInputLatticeQuery.Data1
0x180007a62  jnz     short loc_180007A97
0x180007a64  mov     rax, [rcx+8]
0x180007a68  cmp     rax, qword ptr cs:CLSID_MtfSuggestionInputLatticeQuery.Data4
0x180007a6f  jnz     short loc_180007A97
0x180007a71  mov     rax, cs:?g_oInputQueryFactory@mtf@ipx@@3VInputQueryFactory@12@A; ipx::mtf::InputQueryFactory ipx::mtf::g_oInputQueryFactory
0x180007a78  lea     rbx, ?g_oInputQueryFactory@mtf@ipx@@3VInputQueryFactory@12@A; ipx::mtf::InputQueryFactory ipx::mtf::g_oInputQueryFactory
0x180007a7f  mov     rcx, rbx
0x180007a82  mov     rax, [rax+8]
0x180007a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a8b  mov     rax, cs:?g_oInputQueryFactory@mtf@ipx@@3VInputQueryFactory@12@A; ipx::mtf::InputQueryFactory ipx::mtf::g_oInputQueryFactory
0x180007a92  jmp     loc_180007C23
0x180007a97  mov     rax, [rcx]
0x180007a9a  cmp     rax, qword ptr cs:CLSID_MtfInputTypeAttributes.Data1
0x180007aa1  jnz     short loc_180007AD6
0x180007aa3  mov     rax, [rcx+8]
0x180007aa7  cmp     rax, qword ptr cs:CLSID_MtfInputTypeAttributes.Data4
0x180007aae  jnz     short loc_180007AD6
0x180007ab0  mov     rax, cs:?g_oInputTypeAttributesFactory@mtf@ipx@@3VInputTypeAttributesFactory@12@A; ipx::mtf::InputTypeAttributesFactory ipx::mtf::g_oInputTypeAttributesFactory
0x180007ab7  lea     rbx, ?g_oInputTypeAttributesFactory@mtf@ipx@@3VInputTypeAttributesFactory@12@A; ipx::mtf::InputTypeAttributesFactory ipx::mtf::g_oInputTypeAttributesFactory
0x180007abe  mov     rcx, rbx
0x180007ac1  mov     rax, [rax+8]
0x180007ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aca  mov     rax, cs:?g_oInputTypeAttributesFactory@mtf@ipx@@3VInputTypeAttributesFactory@12@A; ipx::mtf::InputTypeAttributesFactory ipx::mtf::g_oInputTypeAttributesFactory
0x180007ad1  jmp     loc_180007C23
0x180007ad6  mov     rax, [rcx]
0x180007ad9  cmp     rax, qword ptr cs:CLSID_MtfSuggestionClient.Data1
0x180007ae0  jnz     short loc_180007AEF
0x180007ae2  mov     rax, [rcx+8]
0x180007ae6  cmp     rax, qword ptr cs:CLSID_MtfSuggestionClient.Data4
0x180007aed  jz      short loc_180007B08
0x180007aef  mov     rax, [rcx]
0x180007af2  cmp     rax, qword ptr cs:CLSID_MtfSuggestionLatticeClient.Data1
0x180007af9  jnz     short loc_180007B2E
0x180007afb  mov     rax, [rcx+8]
0x180007aff  cmp     rax, qword ptr cs:CLSID_MtfSuggestionLatticeClient.Data4
0x180007b06  jnz     short loc_180007B2E
0x180007b08  mov     rax, cs:?g_oSuggestionClientFactory@mtf@ipx@@3VSuggestionClientFactory@12@A; ipx::mtf::SuggestionClientFactory ipx::mtf::g_oSuggestionClientFactory
0x180007b0f  lea     rbx, ?g_oSuggestionClientFactory@mtf@ipx@@3VSuggestionClientFactory@12@A; ipx::mtf::SuggestionClientFactory ipx::mtf::g_oSuggestionClientFactory
0x180007b16  mov     rcx, rbx
0x180007b19  mov     rax, [rax+8]
0x180007b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b22  mov     rax, cs:?g_oSuggestionClientFactory@mtf@ipx@@3VSuggestionClientFactory@12@A; ipx::mtf::SuggestionClientFactory ipx::mtf::g_oSuggestionClientFactory
0x180007b29  jmp     loc_180007C23
0x180007b2e  mov     rax, [rcx]
0x180007b31  cmp     rax, qword ptr cs:CLSID_MtfDataSourceManager.Data1
0x180007b38  jnz     short loc_180007B6D
0x180007b3a  mov     rax, [rcx+8]
0x180007b3e  cmp     rax, qword ptr cs:CLSID_MtfDataSourceManager.Data4
0x180007b45  jnz     short loc_180007B6D
0x180007b47  mov     rax, cs:?g_oDataSourceManagerFactory@mtf@ipx@@3VDataSourceManagerFactory@12@A; ipx::mtf::DataSourceManagerFactory ipx::mtf::g_oDataSourceManagerFactory
0x180007b4e  lea     rbx, ?g_oDataSourceManagerFactory@mtf@ipx@@3VDataSourceManagerFactory@12@A; ipx::mtf::DataSourceManagerFactory ipx::mtf::g_oDataSourceManagerFactory
0x180007b55  mov     rcx, rbx
0x180007b58  mov     rax, [rax+8]
0x180007b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b61  mov     rax, cs:?g_oDataSourceManagerFactory@mtf@ipx@@3VDataSourceManagerFactory@12@A; ipx::mtf::DataSourceManagerFactory ipx::mtf::g_oDataSourceManagerFactory
0x180007b68  jmp     loc_180007C23
0x180007b6d  mov     rax, [rcx]
0x180007b70  cmp     rax, qword ptr cs:CLSID_MtfSuggestionClientDCOM.Data1
0x180007b77  jnz     short loc_180007BA9
0x180007b79  mov     rax, [rcx+8]
0x180007b7d  cmp     rax, qword ptr cs:CLSID_MtfSuggestionClientDCOM.Data4
0x180007b84  jnz     short loc_180007BA9
0x180007b86  mov     rax, cs:?g_oSuggestionClientDCOMFactory@mtf@ipx@@3VSuggestionClientDCOMFactory@12@A; ipx::mtf::SuggestionClientDCOMFactory ipx::mtf::g_oSuggestionClientDCOMFactory
0x180007b8d  lea     rbx, ?g_oSuggestionClientDCOMFactory@mtf@ipx@@3VSuggestionClientDCOMFactory@12@A; ipx::mtf::SuggestionClientDCOMFactory ipx::mtf::g_oSuggestionClientDCOMFactory
0x180007b94  mov     rcx, rbx
0x180007b97  mov     rax, [rax+8]
0x180007b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ba0  mov     rax, cs:?g_oSuggestionClientDCOMFactory@mtf@ipx@@3VSuggestionClientDCOMFactory@12@A; ipx::mtf::SuggestionClientDCOMFactory ipx::mtf::g_oSuggestionClientDCOMFactory
0x180007ba7  jmp     short loc_180007C23
0x180007ba9  mov     rax, [rcx]
0x180007bac  cmp     rax, qword ptr cs:CLSID_MtfDataSourceManagerDCOM.Data1
0x180007bb3  jnz     short loc_180007BE5
0x180007bb5  mov     rax, [rcx+8]
0x180007bb9  cmp     rax, qword ptr cs:CLSID_MtfDataSourceManagerDCOM.Data4
0x180007bc0  jnz     short loc_180007BE5
0x180007bc2  mov     rax, cs:?g_oDataSourceManagerDCOMFactory@mtf@ipx@@3VDataSourceManagerDCOMFactory@12@A; ipx::mtf::DataSourceManagerDCOMFactory ipx::mtf::g_oDataSourceManagerDCOMFactory
0x180007bc9  lea     rbx, ?g_oDataSourceManagerDCOMFactory@mtf@ipx@@3VDataSourceManagerDCOMFactory@12@A; ipx::mtf::DataSourceManagerDCOMFactory ipx::mtf::g_oDataSourceManagerDCOMFactory
0x180007bd0  mov     rcx, rbx
0x180007bd3  mov     rax, [rax+8]
0x180007bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bdc  mov     rax, cs:?g_oDataSourceManagerDCOMFactory@mtf@ipx@@3VDataSourceManagerDCOMFactory@12@A; ipx::mtf::DataSourceManagerDCOMFactory ipx::mtf::g_oDataSourceManagerDCOMFactory
0x180007be3  jmp     short loc_180007C23
0x180007be5  mov     rax, [rcx]
0x180007be8  cmp     rax, qword ptr cs:CLSID_MtfSuggestionContextProperty.Data1
0x180007bef  jnz     loc_180007C7C
0x180007bf5  mov     rax, [rcx+8]
0x180007bf9  cmp     rax, qword ptr cs:CLSID_MtfSuggestionContextProperty.Data4
0x180007c00  jnz     short loc_180007C7C
0x180007c02  mov     rax, cs:?g_oContextPropertyFactory@mtf@ipx@@3VContextPropertyFactory@12@A; ipx::mtf::ContextPropertyFactory ipx::mtf::g_oContextPropertyFactory
0x180007c09  lea     rbx, ?g_oContextPropertyFactory@mtf@ipx@@3VContextPropertyFactory@12@A; ipx::mtf::ContextPropertyFactory ipx::mtf::g_oContextPropertyFactory
0x180007c10  mov     rcx, rbx
0x180007c13  mov     rax, [rax+8]
0x180007c17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c1c  mov     rax, cs:?g_oContextPropertyFactory@mtf@ipx@@3VContextPropertyFactory@12@A; ipx::mtf::ContextPropertyFactory ipx::mtf::g_oContextPropertyFactory
0x180007c23  mov     r8, rdi
0x180007c26  mov     rdx, rsi
0x180007c29  mov     rcx, rbx
0x180007c2c  mov     rax, [rax]
0x180007c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c34  mov     edi, eax
0x180007c36  test    eax, eax
0x180007c38  jns     short loc_180007C68
0x180007c3a  mov     rcx, [rsp+28h]; this
0x180007c3f  mov     r9d, eax; char *
0x180007c42  lea     r8, aMincoreTextinp_6; "mincore\\textinput\\dev\\mtf\\dll\\com."...
0x180007c49  mov     edx, 53h ; 'S'; void *
0x180007c4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c53  nop
0x180007c54  mov     rcx, [rbx]
0x180007c57  mov     rax, [rcx+10h]
0x180007c5b  mov     rcx, rbx
0x180007c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c63  nop
0x180007c64  mov     eax, edi
0x180007c66  jmp     short loc_180007C81
0x180007c68  mov     rax, [rbx]
0x180007c6b  mov     rcx, rbx
0x180007c6e  mov     rax, [rax+10h]
0x180007c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c77  nop
0x180007c78  xor     eax, eax
0x180007c7a  jmp     short loc_180007C81
0x180007c7c  mov     eax, 80070057h
0x180007c81  mov     rbx, [rsp+28h+arg_0]
0x180007c86  mov     rsi, [rsp+28h+arg_8]
0x180007c8b  add     rsp, 20h
0x180007c8f  pop     rdi
0x180007c90  retn
```
