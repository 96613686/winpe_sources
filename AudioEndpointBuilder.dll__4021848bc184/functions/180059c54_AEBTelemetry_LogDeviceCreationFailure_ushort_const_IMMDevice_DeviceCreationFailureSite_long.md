# AEBTelemetry::LogDeviceCreationFailure(ushort const *,IMMDevice *,DeviceCreationFailureSite,long)

- ea: `0x180059c54`
- end: `0x180059e09`
- name: `?LogDeviceCreationFailure@AEBTelemetry@@SAXPEBGPEAUIMMDevice@@W4DeviceCreationFailureSite@@J@Z`
- size: `437`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004720`
- `0x180009740`

## callees

- `0x180001008`
- `0x180006b0c`
- `0x18000fb60`
- `0x180013a8c`
- `0x18001f374`
- `0x180029c9c`
- `0x180059c54`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180059dd7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180059dd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059de7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059de7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall AEBTelemetry::LogDeviceCreationFailure(const WCHAR *a1, struct IMMDevice *a2, int a3, int a4)
{
  const WCHAR *v8; // rsi
  HRESULT (__stdcall *GetId)(IMMDevice *, LPWSTR *); // rbx
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  struct IMMDevice *v13; // [rsp+50h] [rbp-19h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-11h] BYREF
  PROPVARIANT pvar[2]; // [rsp+60h] [rbp-9h] BYREF
  const WCHAR **v16; // [rsp+70h] [rbp+7h]
  const WCHAR *v17; // [rsp+78h] [rbp+Fh] BYREF
  const WCHAR *v18; // [rsp+80h] [rbp+17h] BYREF
  const WCHAR *v19; // [rsp+88h] [rbp+1Fh] BYREF
  __int64 v20; // [rsp+90h] [rbp+27h] BYREF
  __int64 v21; // [rsp+D8h] [rbp+6Fh] BYREF

  pv = 0;
  *(_OWORD *)pvar = 0;
  v16 = 0;
  v8 = &LocaleName;
  if ( a2 )
  {
    GetId = a2->lpVtbl->GetId;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pv,
      0);
    ((void (__fastcall *)(struct IMMDevice *, LPVOID *))GetId)(a2, &pv);
    v13 = 0;
    v21 = 0;
    if ( (int)AEBTelemetry::GetPnpDevnodeFromMMDevice(a2, &v13) >= 0
      && ((int (__fastcall *)(struct IMMDevice *, _QWORD, __int64 *))v13->lpVtbl->OpenPropertyStore)(v13, 0, &v21) >= 0
      && (*(int (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v21 + 40LL))(
           v21,
           &DEVPKEY_Device_HardwareIds,
           pvar) >= 0
      && LOWORD(pvar[0]) == 4127
      && LODWORD(pvar[1]) )
    {
      v8 = *v16;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v13);
  }
  v10 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v10 > 3u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL, v10) )
  {
    v17 = v8;
    v18 = (const WCHAR *)pv;
    v19 = a1;
    LODWORD(v21) = a3;
    LODWORD(v13) = a4;
    v20 = 16779264;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v11,
      (int)&unk_180078290,
      v11,
      v12,
      (__int64)&v20,
      (__int64)&v13,
      (__int64)&v21,
      &v19,
      &v18,
      &v17);
  }
  PropVariantClear(pvar);
  if ( pv )
    CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x180059c54  mov     [rsp-8+arg_0], rbx
0x180059c59  mov     [rsp-8+arg_10], rsi
0x180059c5e  push    rbp
0x180059c5f  push    rdi
0x180059c60  push    r12
0x180059c62  push    r14
0x180059c64  push    r15
0x180059c66  lea     rbp, [rsp-37h]
0x180059c6b  sub     rsp, 0A0h
0x180059c72  mov     r14d, r9d
0x180059c75  mov     r15d, r8d
0x180059c78  mov     rdi, rdx
0x180059c7b  mov     r12, rcx
0x180059c7e  mov     [rbp+57h+pv], 0
0x180059c86  xorps   xmm0, xmm0
0x180059c89  xor     eax, eax
0x180059c8b  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180059c8f  mov     [rbp+57h+var_50], rax
0x180059c93  lea     rsi, LocaleName
0x180059c9a  test    rdx, rdx
0x180059c9d  jz      loc_180059D48
0x180059ca3  mov     rax, [rdx]
0x180059ca6  mov     rbx, [rax+28h]
0x180059caa  xor     edx, edx
0x180059cac  lea     rcx, [rbp+57h+pv]
0x180059cb0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180059cb5  lea     rdx, [rbp+57h+pv]
0x180059cb9  mov     rcx, rdi
0x180059cbc  mov     rax, rbx
0x180059cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059cc4  mov     [rbp+57h+var_70], 0
0x180059ccc  mov     [rbp+57h+arg_8], 0
0x180059cd4  lea     rdx, [rbp+57h+var_70]; struct IMMDevice **
0x180059cd8  mov     rcx, rdi; struct IMMDevice *
0x180059cdb  call    ?GetPnpDevnodeFromMMDevice@AEBTelemetry@@CAJPEAUIMMDevice@@PEAPEAU2@@Z; AEBTelemetry::GetPnpDevnodeFromMMDevice(IMMDevice *,IMMDevice * *)
0x180059ce0  test    eax, eax
0x180059ce2  js      short loc_180059D35
0x180059ce4  mov     rcx, [rbp+57h+var_70]
0x180059ce8  mov     rax, [rcx]
0x180059ceb  lea     r8, [rbp+57h+arg_8]
0x180059cef  xor     edx, edx
0x180059cf1  mov     rax, [rax+20h]
0x180059cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059cfa  test    eax, eax
0x180059cfc  js      short loc_180059D35
0x180059cfe  mov     rcx, [rbp+57h+arg_8]
0x180059d02  mov     rax, [rcx]
0x180059d05  lea     r8, [rbp+57h+pvar]
0x180059d09  lea     rdx, DEVPKEY_Device_HardwareIds
0x180059d10  mov     rax, [rax+28h]
0x180059d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059d19  test    eax, eax
0x180059d1b  js      short loc_180059D35
0x180059d1d  mov     eax, 101Fh
0x180059d22  cmp     word ptr [rbp+57h+pvar], ax
0x180059d26  jnz     short loc_180059D35
0x180059d28  cmp     dword ptr [rbp+57h+pvar+8], 0
0x180059d2c  jz      short loc_180059D35
0x180059d2e  mov     rax, [rbp+57h+var_50]
0x180059d32  mov     rsi, [rax]
0x180059d35  lea     rcx, [rbp+57h+arg_8]
0x180059d39  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180059d3e  nop
0x180059d3f  lea     rcx, [rbp+57h+var_70]
0x180059d43  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180059d48  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x180059d4d  mov     r8, rax
0x180059d50  mov     ecx, [rax]
0x180059d52  cmp     ecx, 3
0x180059d55  jbe     short loc_180059DD3
0x180059d57  mov     rdx, 400000000000h
0x180059d61  mov     rcx, rax
0x180059d64  call    _tlgKeywordOn
0x180059d69  test    al, al
0x180059d6b  jz      short loc_180059DD3
0x180059d6d  mov     [rbp+57h+var_48], rsi
0x180059d71  mov     rcx, [rbp+57h+pv]
0x180059d75  mov     [rbp+57h+var_40], rcx
0x180059d79  mov     [rbp+57h+var_38], r12
0x180059d7d  mov     dword ptr [rbp+57h+arg_8], r15d
0x180059d81  mov     dword ptr [rbp+57h+var_70], r14d
0x180059d85  mov     [rbp+57h+var_30], 1000800h
0x180059d8d  lea     rax, [rbp+57h+var_48]
0x180059d91  mov     [rsp+0C0h+var_78], rax
0x180059d96  lea     rax, [rbp+57h+var_40]
0x180059d9a  mov     [rsp+0C0h+var_80], rax
0x180059d9f  lea     rax, [rbp+57h+var_38]
0x180059da3  mov     [rsp+0C0h+var_88], rax
0x180059da8  lea     rax, [rbp+57h+arg_8]
0x180059dac  mov     [rsp+0C0h+var_90], rax
0x180059db1  lea     rax, [rbp+57h+var_70]
0x180059db5  mov     [rsp+0C0h+var_98], rax
0x180059dba  lea     rax, [rbp+57h+var_30]
0x180059dbe  mov     [rsp+0C0h+var_A0], rax
0x180059dc3  lea     rdx, unk_180078290
0x180059dca  mov     rcx, r8
0x180059dcd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180059dd2  nop
0x180059dd3  lea     rcx, [rbp+57h+pvar]; pvar
0x180059dd7  call    cs:__imp_PropVariantClear
0x180059ddd  nop
0x180059dde  mov     rcx, [rbp+57h+pv]; pv
0x180059de2  test    rcx, rcx
0x180059de5  jz      short loc_180059DED
0x180059de7  call    cs:__imp_CoTaskMemFree
0x180059ded  lea     r11, [rsp+0C0h+var_20]
0x180059df5  mov     rbx, [r11+30h]
0x180059df9  mov     rsi, [r11+40h]
0x180059dfd  mov     rsp, r11
0x180059e00  pop     r15
0x180059e02  pop     r14
0x180059e04  pop     r12
0x180059e06  pop     rdi
0x180059e07  pop     rbp
0x180059e08  retn
```
