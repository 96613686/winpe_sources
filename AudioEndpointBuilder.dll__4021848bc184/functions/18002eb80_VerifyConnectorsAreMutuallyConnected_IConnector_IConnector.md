# VerifyConnectorsAreMutuallyConnected(IConnector *,IConnector *)

- ea: `0x18002eb80`
- end: `0x18002ed39`
- name: `?VerifyConnectorsAreMutuallyConnected@@YAJPEAUIConnector@@0@Z`
- size: `441`
- prototype: `__int64 __fastcall(struct IConnector *, struct IConnector *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180052ffc`

## callees

- `0x180006b0c`
- `0x18000fb60`
- `0x180010da8`
- `0x18001f374`
- `0x180022b04`
- `0x180024ca0`
- `0x18002eb80`
- `0x180034c5c`
- `0x180068010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002ecb4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002ecb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ec5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ec73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ece3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ecf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ed09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ed19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ec5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ec73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ece3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ecf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ed09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ed19`

## string_xrefs

- `0x18002ec45`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall VerifyConnectorsAreMutuallyConnected(struct IConnector *a1, struct IConnector *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, LPVOID *); // rbx
  HRESULT (__stdcall *GetConnectorIdConnectedTo)(IConnector *, LPWSTR *); // rbx
  const struct _tlgProvider_t *v9; // rax
  __int64 v11[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  struct IConnector *v13; // [rsp+50h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+30h] BYREF
  LPVOID v15; // [rsp+68h] [rbp+38h] BYREF

  v13 = a1;
  v11[0] = 0;
  v15 = 0;
  pv = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
  }
  v11[0] = 0;
  v3 = wil::com_query_to_nothrow<IPart,IConnector * &>(&v13, (__int64)v11);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 3075;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v3,
      v11[0]);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v15 )
      CoTaskMemFree(v15);
    goto LABEL_28;
  }
  v6 = v11[0];
  v7 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v11[0] + 40LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v15,
    0);
  v3 = v7(v6, &v15);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 3077;
    goto LABEL_9;
  }
  GetConnectorIdConnectedTo = a2->lpVtbl->GetConnectorIdConnectedTo;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v3 = ((__int64 (__fastcall *)(struct IConnector *, LPVOID *))GetConnectorIdConnectedTo)(a2, &pv);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 3080;
    goto LABEL_9;
  }
  if ( (unsigned int)_o__wcsicmp(v15, pv) )
  {
    v9 = AudioEndpointBuilderTelemetryProvider::Provider();
    if ( *(_DWORD *)v9 > 4u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)v9,
        (unsigned __int8 *)byte_1800766C9);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v15 )
      CoTaskMemFree(v15);
    v4 = -2147467259;
  }
  else
  {
    if ( pv )
      CoTaskMemFree(pv);
    if ( v15 )
      CoTaskMemFree(v15);
    v4 = 0;
  }
LABEL_28:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v11);
  return v4;
}

```

## disassembly

```asm
0x18002eb80  mov     [rsp-18h+arg_8], rbx
0x18002eb85  mov     [rsp-18h+arg_0], rcx
0x18002eb8a  push    rbp
0x18002eb8b  push    rsi
0x18002eb8c  push    rdi
0x18002eb8d  mov     rbp, rsp
0x18002eb90  sub     rsp, 30h
0x18002eb94  mov     rsi, rdx
0x18002eb97  xor     ecx, ecx
0x18002eb99  mov     [rbp+var_10], rcx
0x18002eb9d  mov     [rbp+arg_18], rcx
0x18002eba1  mov     [rbp+pv], rcx
0x18002eba5  lea     rdx, WPP_GLOBAL_Control
0x18002ebac  mov     rax, cs:WPP_GLOBAL_Control
0x18002ebb3  cmp     rax, rdx
0x18002ebb6  jz      short loc_18002EBDE
0x18002ebb8  test    dword ptr [rax+1Ch], 80000h
0x18002ebbf  jz      short loc_18002EBDE
0x18002ebc1  cmp     byte ptr [rax+19h], 4
0x18002ebc5  jb      short loc_18002EBDE
0x18002ebc7  lea     edx, [rcx+1Dh]
0x18002ebca  lea     r8, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids
0x18002ebd1  mov     rcx, [rax+10h]
0x18002ebd5  call    WPP_SF_
0x18002ebda  mov     rcx, [rbp+var_10]
0x18002ebde  mov     [rbp+var_10], 0
0x18002ebe6  test    rcx, rcx
0x18002ebe9  jz      short loc_18002EBF8
0x18002ebeb  mov     rax, [rcx]
0x18002ebee  mov     rax, [rax+10h]
0x18002ebf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebf7  nop
0x18002ebf8  lea     rdx, [rbp+var_10]
0x18002ebfc  lea     rcx, [rbp+arg_0]
0x18002ec00  call    ??$com_query_to_nothrow@UIPart@@AEAPEAUIConnector@@@wil@@YAJAEAPEAUIConnector@@PEAPEAUIPart@@@Z; wil::com_query_to_nothrow<IPart,IConnector * &>(IConnector * &,IPart * *)
0x18002ec05  mov     ebx, eax
0x18002ec07  test    eax, eax
0x18002ec09  jns     short loc_18002EC12
0x18002ec0b  mov     edx, 0C03h
0x18002ec10  jmp     short loc_18002EC42
0x18002ec12  mov     rdi, [rbp+var_10]
0x18002ec16  mov     rax, [rdi]
0x18002ec19  mov     rbx, [rax+28h]
0x18002ec1d  xor     edx, edx
0x18002ec1f  lea     rcx, [rbp+arg_18]
0x18002ec23  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002ec28  lea     rdx, [rbp+arg_18]
0x18002ec2c  mov     rcx, rdi
0x18002ec2f  mov     rax, rbx
0x18002ec32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec37  mov     ebx, eax
0x18002ec39  test    eax, eax
0x18002ec3b  jns     short loc_18002EC7E
0x18002ec3d  mov     edx, 0C05h; void *
0x18002ec42  mov     r9d, eax; char *
0x18002ec45  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18002ec4c  mov     rcx, [rbp+18h]; this
0x18002ec50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ec55  nop
0x18002ec56  mov     rcx, [rbp+pv]; pv
0x18002ec5a  test    rcx, rcx
0x18002ec5d  jz      short loc_18002EC66
0x18002ec5f  call    cs:__imp_CoTaskMemFree
0x18002ec65  nop
0x18002ec66  mov     rcx, [rbp+arg_18]; pv
0x18002ec6a  test    rcx, rcx
0x18002ec6d  jz      loc_18002ED21
0x18002ec73  call    cs:__imp_CoTaskMemFree
0x18002ec79  jmp     loc_18002ED21
0x18002ec7e  mov     rax, [rsi]
0x18002ec81  mov     rbx, [rax+48h]
0x18002ec85  xor     edx, edx
0x18002ec87  lea     rcx, [rbp+pv]
0x18002ec8b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002ec90  lea     rdx, [rbp+pv]
0x18002ec94  mov     rcx, rsi
0x18002ec97  mov     rax, rbx
0x18002ec9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec9f  mov     ebx, eax
0x18002eca1  test    eax, eax
0x18002eca3  jns     short loc_18002ECAC
0x18002eca5  mov     edx, 0C08h
0x18002ecaa  jmp     short loc_18002EC42
0x18002ecac  mov     rdx, [rbp+pv]
0x18002ecb0  mov     rcx, [rbp+arg_18]
0x18002ecb4  call    cs:__imp__o__wcsicmp
0x18002ecba  test    eax, eax
0x18002ecbc  jz      short loc_18002ED00
0x18002ecbe  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18002ecc3  mov     ecx, [rax]
0x18002ecc5  cmp     ecx, 4
0x18002ecc8  jbe     short loc_18002ECDA
0x18002ecca  lea     rdx, byte_1800766C9
0x18002ecd1  mov     rcx, rax
0x18002ecd4  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18002ecd9  nop
0x18002ecda  mov     rcx, [rbp+pv]; pv
0x18002ecde  test    rcx, rcx
0x18002ece1  jz      short loc_18002ECEA
0x18002ece3  call    cs:__imp_CoTaskMemFree
0x18002ece9  nop
0x18002ecea  mov     rcx, [rbp+arg_18]; pv
0x18002ecee  test    rcx, rcx
0x18002ecf1  jz      short loc_18002ECF9
0x18002ecf3  call    cs:__imp_CoTaskMemFree
0x18002ecf9  mov     ebx, 80004005h
0x18002ecfe  jmp     short loc_18002ED21
0x18002ed00  mov     rcx, [rbp+pv]; pv
0x18002ed04  test    rcx, rcx
0x18002ed07  jz      short loc_18002ED10
0x18002ed09  call    cs:__imp_CoTaskMemFree
0x18002ed0f  nop
0x18002ed10  mov     rcx, [rbp+arg_18]; pv
0x18002ed14  test    rcx, rcx
0x18002ed17  jz      short loc_18002ED1F
0x18002ed19  call    cs:__imp_CoTaskMemFree
0x18002ed1f  xor     ebx, ebx
0x18002ed21  lea     rcx, [rbp+var_10]
0x18002ed25  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002ed2a  mov     eax, ebx
0x18002ed2c  mov     rbx, [rsp+30h+arg_8]
0x18002ed31  add     rsp, 30h
0x18002ed35  pop     rdi
0x18002ed36  pop     rsi
0x18002ed37  pop     rbp
0x18002ed38  retn
```
