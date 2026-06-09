# Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::~AppxProvisionWriterImpl(void)

- ea: `0x180048a50`
- end: `0x180048aa8`
- name: `??1AppxProvisionWriterImpl@AppxProvisionPackage@ApplicationModel@Windows@@UEAA@XZ`
- size: `88`
- prototype: `void __fastcall(Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180048ab0`

## callees

- `0x18001ca24`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048a95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048a95`
- `OLEAUT32!__imp_SysFreeString` at `0x180048a8b`
- `OLEAUT32!__imp_SysFreeString` at `0x180048a8b`

## pseudocode

```c
void __fastcall Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::~AppxProvisionWriterImpl(
        Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl *this)
{
  *(_QWORD *)this = &Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::`vftable';
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease((char *)this + 56);
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease((char *)this + 48);
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease((char *)this + 40);
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease((char *)this + 32);
  SysFreeString(*((BSTR *)this + 3));
  CoTaskMemFree(*((LPVOID *)this + 2));
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180048a50  push    rbx
0x180048a52  sub     rsp, 20h
0x180048a56  lea     rax, ??_7AppxProvisionWriterImpl@AppxProvisionPackage@ApplicationModel@Windows@@6B@; const Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::`vftable'
0x180048a5d  mov     rbx, rcx
0x180048a60  mov     [rcx], rax
0x180048a63  add     rcx, 38h ; '8'
0x180048a67  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180048a6c  lea     rcx, [rbx+30h]
0x180048a70  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180048a75  lea     rcx, [rbx+28h]
0x180048a79  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180048a7e  lea     rcx, [rbx+20h]
0x180048a82  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180048a87  mov     rcx, [rbx+18h]; bstrString
0x180048a8b  call    cs:__imp_SysFreeString
0x180048a91  mov     rcx, [rbx+10h]; pv
0x180048a95  call    cs:__imp_CoTaskMemFree
0x180048a9b  mov     dword ptr [rbx+0Ch], 0C0000001h
0x180048aa2  add     rsp, 20h
0x180048aa6  pop     rbx
0x180048aa7  retn
```
