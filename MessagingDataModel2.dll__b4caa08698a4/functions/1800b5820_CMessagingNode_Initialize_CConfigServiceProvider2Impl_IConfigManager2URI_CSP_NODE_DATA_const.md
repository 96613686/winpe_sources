# CMessagingNode::Initialize(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *)

- ea: `0x1800b5820`
- end: `0x1800b5927`
- name: `?Initialize@CMessagingNode@@EEAAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@@Z`
- size: `263`
- prototype: `__int64 __fastcall(CMessagingNode *__hidden this, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180030bd0`
- `0x18004eab0`
- `0x18006b108`
- `0x1800b5820`
- `0x1800b5930`
- `0x1800b99f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b5880`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b5880`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b58e3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b58e3`

## string_xrefs

- `0x1800b58ad`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
__int64 __fastcall CMessagingNode::Initialize(
        LPVOID *this,
        struct CConfigServiceProvider2Impl *a2,
        struct IConfigManager2URI *a3,
        const struct CSP_NODE_DATA *a4)
{
  HRESULT Instance; // ebx
  __int64 v7; // rdi
  __int64 v8; // [rsp+30h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-40h] BYREF
  __int64 v10; // [rsp+50h] [rbp-28h]

  Instance = CCSPNodeImpl::Initialize((CCSPNodeImpl *)this, a2, a3, a4);
  if ( Instance >= 0 )
  {
    v8 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 16);
    Instance = CoCreateInstance(&CLSID_Application, 0, 1u, &GUID_a65ccaeb_6558_4656_ad3d_eccc00d00f0d, this + 16);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
    if ( Instance >= 0 )
    {
      v10 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonValue",
        0x1Cu,
        0x1Bu);
      v7 = v10;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 17);
      Instance = RoGetActivationFactory(v7, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, this + 17);
      if ( Instance >= 0 )
      {
        Instance = MessagingSettings::Initialize((MessagingSettings *)(this + 18), 0xFFFFFFFF, 0);
        if ( Instance >= 0 )
          return 0;
      }
    }
  }
  Log_HREvent_98(Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800b5820  push    rbx
0x1800b5822  push    rbp
0x1800b5823  push    rdi
0x1800b5824  sub     rsp, 60h
0x1800b5828  mov     rbp, rcx
0x1800b582b  call    ?Initialize@CCSPNodeImpl@@UEAAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@@Z; CCSPNodeImpl::Initialize(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *)
0x1800b5830  mov     ebx, eax
0x1800b5832  test    eax, eax
0x1800b5834  jns     short loc_1800B584F
0x1800b5836  mov     r9d, 40h ; '@'
0x1800b583c  mov     edx, 1
0x1800b5841  mov     ecx, ebx; int
0x1800b5843  call    Log_HREvent_98
0x1800b5848  mov     eax, ebx
0x1800b584a  jmp     loc_1800B591F
0x1800b584f  lea     rbx, [rbp+80h]
0x1800b5856  mov     [rsp+78h+var_48], 0
0x1800b585f  mov     rcx, rbx
0x1800b5862  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b5867  xor     edx, edx; pUnkOuter
0x1800b5869  mov     [rsp+78h+ppv], rbx; ppv
0x1800b586e  lea     r9, _GUID_a65ccaeb_6558_4656_ad3d_eccc00d00f0d; riid
0x1800b5875  lea     rcx, CLSID_Application; rclsid
0x1800b587c  lea     r8d, [rdx+1]; dwClsContext
0x1800b5880  call    cs:__imp_CoCreateInstance
0x1800b5886  lea     rcx, [rsp+78h+var_48]
0x1800b588b  mov     ebx, eax
0x1800b588d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b5892  test    ebx, ebx
0x1800b5894  jns     short loc_1800B589E
0x1800b5896  mov     r9d, 42h ; 'B'
0x1800b589c  jmp     short loc_1800B583C
0x1800b589e  mov     r9d, 1Bh; unsigned int
0x1800b58a4  mov     [rsp+78h+var_28], 0
0x1800b58ad  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800b58b4  lea     rcx, [rsp+78h+hstringHeader]; hstringHeader
0x1800b58b9  lea     r8d, [r9+1]; unsigned int
0x1800b58bd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b58c2  mov     rdi, [rsp+78h+var_28]
0x1800b58c7  lea     rbx, [rbp+88h]
0x1800b58ce  mov     rcx, rbx
0x1800b58d1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b58d6  mov     r8, rbx
0x1800b58d9  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1800b58e0  mov     rcx, rdi
0x1800b58e3  call    cs:__imp_RoGetActivationFactory
0x1800b58e9  mov     ebx, eax
0x1800b58eb  test    eax, eax
0x1800b58ed  jns     short loc_1800B58FA
0x1800b58ef  mov     r9d, 44h ; 'D'
0x1800b58f5  jmp     loc_1800B583C
0x1800b58fa  lea     rcx, [rbp+90h]; this
0x1800b5901  xor     r8d, r8d; unsigned __int16 *
0x1800b5904  or      edx, 0FFFFFFFFh; unsigned int
0x1800b5907  call    ?Initialize@MessagingSettings@@QEAAJKPEBG@Z; MessagingSettings::Initialize(ulong,ushort const *)
0x1800b590c  mov     ebx, eax
0x1800b590e  test    eax, eax
0x1800b5910  jns     short loc_1800B591D
0x1800b5912  mov     r9d, 46h ; 'F'
0x1800b5918  jmp     loc_1800B583C
0x1800b591d  xor     eax, eax
0x1800b591f  add     rsp, 60h
0x1800b5923  pop     rdi
0x1800b5924  pop     rbp
0x1800b5925  pop     rbx
0x1800b5926  retn
```
