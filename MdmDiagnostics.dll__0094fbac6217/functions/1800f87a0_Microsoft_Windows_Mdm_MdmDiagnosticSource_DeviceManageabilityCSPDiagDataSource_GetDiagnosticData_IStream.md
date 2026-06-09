# Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceManageabilityCSPDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x1800f87a0`
- end: `0x1800f8892`
- name: `?GetDiagnosticData@DeviceManageabilityCSPDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `242`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceManageabilityCSPDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x1800f7f10`
- `0x1800f8680`
- `0x1800f87a0`
- `0x180122018`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800f87d9`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800f8831`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800f87d9`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800f8831`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f87c8`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f87c8`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800f8844`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800f8844`

## string_xrefs

- `0x1800f87df`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="DeviceManageabilityProviderInfo">\n    <Key>\n      <Category>Providers</Category>\n      <Path>HKLM\Software\Microsoft\DeviceManageabilityCSP\Provider</Path>\n      <Key>\n        <Category>Provider</Category>\n        <Path>*</Path>\n        <Representation>ProviderID</Representation>\n        <Value>\n          <Name>*</Name>\n          <ValueRepresentation>*</ValueRepresentation>\n        </Value>\n      </Key>\n    </K`
- `0x1800f87e6`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="OSDataDeviceManageabilityProviderInfo">\n    <Key>\n      <Category>Providers</Category>\n      <Path>HKLM\OSData\Software\Microsoft\DeviceManageabilityCSP\Provider</Path>\n      <Key>\n        <Category>Provider</Category>\n        <Path>*</Path>\n        <Representation>ProviderID</Representation>\n        <Value>\n          <Name>*</Name>\n          <ValueRepresentation>*</ValueRepresentation>\n        </Value>\n      </`
- `0x1800f8823`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\devicemanageabilitycspdiagdata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceManageabilityCSPDiagDataSource::GetDiagnosticData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceManageabilityCSPDiagDataSource *this,
        struct IStream **a2)
{
  HRESULT StreamOnHGlobal; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  char IsStateSeparationEnabled; // al
  const BYTE *v7; // rdi
  const wchar_t *v8; // rdx
  __int64 v9; // rcx
  IStream *v10; // rax
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct IStream *v14; // [rsp+50h] [rbp+18h] BYREF
  unsigned __int64 cbInit; // [rsp+58h] [rbp+20h] BYREF

  v14 = 0;
  cbInit = 0;
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, a2);
  v4 = StreamOnHGlobal;
  if ( StreamOnHGlobal >= 0 )
  {
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
    v7 = (const BYTE *)L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
                        "<DiagData>\n"
                        "  <DataSource name=\"OSDataDeviceManageabilityProviderInfo\">\n"
                        "    <Key>\n"
                        "      <Category>Providers</Category>\n"
                        "      <Path>HKLM\\OSData\\Software\\Microsoft\\DeviceManageabilityCSP\\Provider</Path>\n"
                        "      <Key>\n"
                        "        <Category>Provider</Category>\n"
                        "        <Path>*</Path>\n"
                        "        <Representation>ProviderID</Representation>\n"
                        "        <Value>\n"
                        "          <Name>*</Name>\n"
                        "          <ValueRepresentation>*</ValueRepresentation>\n"
                        "        </Value>\n"
                        "      </Key>\n"
                        "    </Key>\n"
                        "  </DataSource>\n"
                        "</DiagData>";
    v8 = L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
          "<DiagData>\n"
          "  <DataSource name=\"OSDataDeviceManageabilityProviderInfo\">\n"
          "    <Key>\n"
          "      <Category>Providers</Category>\n"
          "      <Path>HKLM\\OSData\\Software\\Microsoft\\DeviceManageabilityCSP\\Provider</Path>\n"
          "      <Key>\n"
          "        <Category>Provider</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>ProviderID</Representation>\n"
          "        <Value>\n"
          "          <Name>*</Name>\n"
          "          <ValueRepresentation>*</ValueRepresentation>\n"
          "        </Value>\n"
          "      </Key>\n"
          "    </Key>\n"
          "  </DataSource>\n"
          "</DiagData>";
    if ( !IsStateSeparationEnabled )
      v8 = (const wchar_t *)L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
                             "<DiagData>\n"
                             "  <DataSource name=\"DeviceManageabilityProviderInfo\">\n"
                             "    <Key>\n"
                             "      <Category>Providers</Category>\n"
                             "      <Path>HKLM\\Software\\Microsoft\\DeviceManageabilityCSP\\Provider</Path>\n"
                             "      <Key>\n"
                             "        <Category>Provider</Category>\n"
                             "        <Path>*</Path>\n"
                             "        <Representation>ProviderID</Representation>\n"
                             "        <Value>\n"
                             "          <Name>*</Name>\n"
                             "          <ValueRepresentation>*</ValueRepresentation>\n"
                             "        </Value>\n"
                             "      </Key>\n"
                             "    </Key>\n"
                             "  </DataSource>\n"
                             "</DiagData>";
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    StreamOnHGlobal = ULongLongMult(v9 + 1, (unsigned __int64)v8, &cbInit);
    v4 = StreamOnHGlobal;
    if ( StreamOnHGlobal >= 0 )
    {
      if ( !(unsigned __int8)RtlIsStateSeparationEnabled() )
        v7 = L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
              "<DiagData>\n"
              "  <DataSource name=\"DeviceManageabilityProviderInfo\">\n"
              "    <Key>\n"
              "      <Category>Providers</Category>\n"
              "      <Path>HKLM\\Software\\Microsoft\\DeviceManageabilityCSP\\Provider</Path>\n"
              "      <Key>\n"
              "        <Category>Provider</Category>\n"
              "        <Path>*</Path>\n"
              "        <Representation>ProviderID</Representation>\n"
              "        <Value>\n"
              "          <Name>*</Name>\n"
              "          <ValueRepresentation>*</ValueRepresentation>\n"
              "        </Value>\n"
              "      </Key>\n"
              "    </Key>\n"
              "  </DataSource>\n"
              "</DiagData>";
      v10 = SHCreateMemStream(v7, cbInit);
      Microsoft::WRL::ComPtr<IStream>::operator=(&v14, v10);
      StreamOnHGlobal = CreateDiagnosticData(v14, *a2);
      v4 = StreamOnHGlobal;
      if ( StreamOnHGlobal >= 0 )
      {
        v4 = 0;
        goto LABEL_15;
      }
      v5 = 55;
    }
    else
    {
      v5 = 50;
    }
  }
  else
  {
    v5 = 49;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\devicemanageabilitycspdiagdata.cpp",
    (const char *)(unsigned int)StreamOnHGlobal,
    v12);
LABEL_15:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v14);
  return v4;
}

```

## disassembly

```asm
0x1800f87a0  mov     rax, rsp
0x1800f87a3  mov     [rax+8], rbx
0x1800f87a7  mov     [rax+10h], rbp
0x1800f87ab  push    rsi
0x1800f87ac  push    rdi
0x1800f87ad  push    r14; int
0x1800f87af  sub     rsp, 20h
0x1800f87b3  mov     rsi, rdx
0x1800f87b6  xor     ebp, ebp
0x1800f87b8  mov     [rax+18h], rbp
0x1800f87bc  mov     [rax+20h], rbp
0x1800f87c0  mov     r8, rdx; ppstm
0x1800f87c3  lea     edx, [rbp+1]; fDeleteOnRelease
0x1800f87c6  xor     ecx, ecx; hGlobal
0x1800f87c8  call    cs:__imp_CreateStreamOnHGlobal
0x1800f87ce  mov     ebx, eax
0x1800f87d0  test    eax, eax
0x1800f87d2  jns     short loc_1800F87D9
0x1800f87d4  lea     edx, [rbp+31h]
0x1800f87d7  jmp     short loc_1800F881B
0x1800f87d9  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800f87df  lea     r14, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x1800f87e6  lea     rdi, aXmlVersion10En_20; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x1800f87ed  mov     rdx, rdi
0x1800f87f0  test    al, al
0x1800f87f2  cmovz   rdx, r14; unsigned __int64
0x1800f87f6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800f87fa  inc     rcx
0x1800f87fd  cmp     [rdx+rcx*2], bp
0x1800f8801  jnz     short loc_1800F87FA
0x1800f8803  inc     rcx; unsigned __int64
0x1800f8806  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x1800f880b  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800f8810  mov     ebx, eax
0x1800f8812  test    eax, eax
0x1800f8814  jns     short loc_1800F8831
0x1800f8816  mov     edx, 32h ; '2'; void *
0x1800f881b  mov     rcx, [rsp+38h]; this
0x1800f8820  mov     r9d, eax; char *
0x1800f8823  lea     r8, aOnecoreuapAdmi_24; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f882a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f882f  jmp     short loc_1800F8873
0x1800f8831  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800f8837  test    al, al
0x1800f8839  cmovz   rdi, r14
0x1800f883d  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x1800f8841  mov     rcx, rdi; pInit
0x1800f8844  call    cs:__imp_SHCreateMemStream
0x1800f884a  mov     rdx, rax
0x1800f884d  lea     rcx, [rsp+38h+arg_10]
0x1800f8852  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x1800f8857  mov     rdx, [rsi]; struct IStream *
0x1800f885a  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x1800f885f  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x1800f8864  mov     ebx, eax
0x1800f8866  test    eax, eax
0x1800f8868  jns     short loc_1800F8871
0x1800f886a  mov     edx, 37h ; '7'
0x1800f886f  jmp     short loc_1800F881B
0x1800f8871  mov     ebx, ebp
0x1800f8873  lea     rcx, [rsp+38h+arg_10]
0x1800f8878  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f887d  mov     eax, ebx
0x1800f887f  mov     rbx, [rsp+38h+arg_0]
0x1800f8884  mov     rbp, [rsp+38h+arg_8]
0x1800f8889  add     rsp, 20h
0x1800f888d  pop     r14
0x1800f888f  pop     rdi
0x1800f8890  pop     rsi
0x1800f8891  retn
```
