# _lambda_7ecbcb1796d2c9576671ee5d3014cd3d_::operator()

- ea: `0x18001fa98`
- end: `0x18001fbab`
- name: `_lambda_7ecbcb1796d2c9576671ee5d3014cd3d_::operator()`
- size: `275`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001e274`

## callees

- `0x1800089e8`
- `0x18001ea38`
- `0x18001ea6c`
- `0x18001eadc`
- `0x18001fa98`
- `0x180020164`
- `0x18002145c`
- `0x180021738`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18001fb45`
- `RPCRT4!NdrDllGetClassObject` at `0x18001fb45`

## pseudocode

```c
__int64 __fastcall lambda_7ecbcb1796d2c9576671ee5d3014cd3d_::operator()(__int64 a1)
{
  const CLSID *pclsid; // rax
  struct ATL::_ATL_COM_MODULE70 *v3; // rcx
  unsigned int v4; // edi
  _QWORD v6[2]; // [rsp+30h] [rbp-20h] BYREF
  _QWORD *v7; // [rsp+40h] [rbp-10h] BYREF
  __int16 v8; // [rsp+48h] [rbp-8h]
  char v9; // [rsp+70h] [rbp+20h] BYREF
  HRESULT ClassObject; // [rsp+78h] [rbp+28h] BYREF
  int v11; // [rsp+80h] [rbp+30h] BYREF
  int v12; // [rsp+84h] [rbp+34h]

  errorlib::scoped_error<hresult_error::tag>::scoped_error<hresult_error::tag>(&v11);
  v9 = 1;
  v6[0] = &v9;
  v6[1] = &v11;
  lambda_a9368a436d9ee036dc3726bcac3c2c08_::operator()(v6);
  v9 = 0;
  v7 = v6;
  v8 = 258;
  if ( !**(_QWORD **)a1 )
  {
    ClassObject = -2147467261;
    errorlib::scoped_error<hresult_error::tag>::receiveAndThrow<long>(&v11, &ClassObject);
  }
  ***(_QWORD ***)a1 = 0;
  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  ClassObject = NdrDllGetClassObject(
                  *(const IID *const *)(a1 + 8),
                  *(const IID *const *)(a1 + 16),
                  **(void ****)a1,
                  (const ProxyFileInfo **)&aProxyFileList,
                  pclsid,
                  &gPFactory);
  errorlib::scoped_error<hresult_error::tag>::receive<long>(&v11, &ClassObject);
  v12 = 3;
  v4 = v11;
  if ( v11 < 0 )
  {
    ClassObject = ATL::AtlComModuleGetClassObject(
                    v3,
                    *(const struct _GUID **)(a1 + 8),
                    *(const struct _GUID **)(a1 + 16),
                    **(void ****)a1);
    errorlib::scoped_error<hresult_error::tag>::receiveAndThrow<long>(&v11, &ClassObject);
    v4 = 0;
  }
  wil::details::ScopeExitFnGuard_std::tr1::reference_wrapper__lambda_a9368a436d9ee036dc3726bcac3c2c08_____::operator()(&v7);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v11);
  return v4;
}

```

## disassembly

```asm
0x18001fa98  push    rbp
0x18001fa9a  push    rbx
0x18001fa9b  push    rdi
0x18001fa9c  mov     rbp, rsp
0x18001fa9f  sub     rsp, 50h
0x18001faa3  mov     rbx, rcx
0x18001faa6  lea     rcx, [rbp+arg_10]
0x18001faaa  call    ??0?$scoped_error@Utag@hresult_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<hresult_error::tag>::scoped_error<hresult_error::tag>(void)
0x18001faaf  nop
0x18001fab0  mov     [rbp+arg_0], 1
0x18001fab4  lea     rax, [rbp+arg_0]
0x18001fab8  mov     [rbp+var_20], rax
0x18001fabc  lea     rax, [rbp+arg_10]
0x18001fac0  mov     [rbp+var_18], rax
0x18001fac4  lea     rcx, [rbp+var_20]
0x18001fac8  call    _lambda_a9368a436d9ee036dc3726bcac3c2c08___operator__
0x18001facd  mov     [rbp+arg_0], 0
0x18001fad1  lea     rax, [rbp+var_20]
0x18001fad5  mov     [rbp+var_10], rax
0x18001fad9  mov     [rbp+var_8], 102h
0x18001fadf  mov     rax, [rbx]
0x18001fae2  cmp     qword ptr [rax], 0
0x18001fae6  jnz     short loc_18001FAFC
0x18001fae8  mov     [rbp+arg_8], 80004003h
0x18001faef  lea     rdx, [rbp+arg_8]
0x18001faf3  lea     rcx, [rbp+arg_10]
0x18001faf7  call    ??$receiveAndThrow@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAX$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receiveAndThrow<long>(long &&)
0x18001fafc  mov     rax, [rbx]
0x18001faff  mov     rcx, [rax]
0x18001fb02  mov     qword ptr [rcx], 0
0x18001fb09  mov     rax, [rbx]
0x18001fb0c  mov     r8, [rax]; ppv
0x18001fb0f  mov     rax, cs:aProxyFileList
0x18001fb16  mov     rcx, [rax+8]
0x18001fb1a  mov     rax, [rcx]
0x18001fb1d  test    rax, rax
0x18001fb20  jz      short loc_18001FB25
0x18001fb22  mov     rax, [rax]
0x18001fb25  lea     rcx, gPFactory
0x18001fb2c  mov     [rsp+50h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x18001fb31  mov     [rsp+50h+pclsid], rax; pclsid
0x18001fb36  lea     r9, aProxyFileList; pProxyFileList
0x18001fb3d  mov     rdx, [rbx+10h]; riid
0x18001fb41  mov     rcx, [rbx+8]; rclsid
0x18001fb45  call    cs:__imp_NdrDllGetClassObject
0x18001fb4b  mov     [rbp+arg_8], eax
0x18001fb4e  lea     rdx, [rbp+arg_8]
0x18001fb52  lea     rcx, [rbp+arg_10]
0x18001fb56  call    ??$receive@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receive<long>(long &&)
0x18001fb5b  mov     [rbp+arg_14], 3
0x18001fb62  mov     edi, [rbp+arg_10]
0x18001fb65  test    edi, edi
0x18001fb67  jns     short loc_18001FB8E
0x18001fb69  mov     r9, [rbx]
0x18001fb6c  mov     r9, [r9]; void **
0x18001fb6f  mov     r8, [rbx+10h]; struct _GUID *
0x18001fb73  mov     rdx, [rbx+8]; struct _GUID *
0x18001fb77  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x18001fb7c  mov     [rbp+arg_8], eax
0x18001fb7f  lea     rdx, [rbp+arg_8]
0x18001fb83  lea     rcx, [rbp+arg_10]
0x18001fb87  call    ??$receiveAndThrow@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAX$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receiveAndThrow<long>(long &&)
0x18001fb8c  xor     edi, edi
0x18001fb8e  lea     rcx, [rbp+var_10]
0x18001fb92  call    wil__details__ScopeExitFnGuard_std__tr1__reference_wrapper__lambda_a9368a436d9ee036dc3726bcac3c2c08_______operator__
0x18001fb97  nop
0x18001fb98  lea     rcx, [rbp+arg_10]
0x18001fb9c  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x18001fba1  mov     eax, edi
0x18001fba3  add     rsp, 50h
0x18001fba7  pop     rdi
0x18001fba8  pop     rbx
0x18001fba9  pop     rbp
0x18001fbaa  retn
```
