# Microsoft::Windows::Mdm::MdmDiagnosticSource::SystemInfoDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180117f70`
- end: `0x1801180c4`
- name: `?GetDiagnosticData@SystemInfoDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::SystemInfoDiagDataSource *__hidden this, LPSTREAM *ppstm)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x180117f70`
- `0x1801180cc`
- `0x180191010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x180117fcf`
- `XmlLite!CreateXmlWriter` at `0x180117fcf`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180117f8a`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180117f8a`

## string_xrefs

- `0x180117fa0`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\systeminfodiagdata.cpp`
- `0x180117fe5`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\systeminfodiagdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::SystemInfoDiagDataSource::GetDiagnosticData(
        void **this,
        LPSTREAM *ppstm)
{
  HRESULT StreamOnHGlobal; // ebx
  __int64 v5; // rdx
  _QWORD *v7; // rbx
  HRESULT XmlWriter; // edi
  __int64 v9; // rdx
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, ppstm);
  if ( StreamOnHGlobal < 0 )
  {
    v5 = 114;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\systeminfodiagdata.cpp",
      (const char *)(unsigned int)StreamOnHGlobal,
      v10);
    return (unsigned int)StreamOnHGlobal;
  }
  v7 = this + 1;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(this + 1);
  XmlWriter = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, this + 1, 0);
  if ( XmlWriter < 0 )
  {
    v9 = 115;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\systeminfodiagdata.cpp",
      (const char *)(unsigned int)XmlWriter,
      v10);
    return (unsigned int)XmlWriter;
  }
  XmlWriter = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v7 + 24LL))(*v7, *ppstm);
  if ( XmlWriter < 0 )
  {
    v9 = 116;
    goto LABEL_6;
  }
  XmlWriter = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v7 + 40LL))(*v7, 1, 1);
  if ( XmlWriter < 0 )
  {
    v9 = 117;
    goto LABEL_6;
  }
  XmlWriter = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v7 + 208LL))(*v7, 0);
  if ( XmlWriter < 0 )
  {
    v9 = 118;
    goto LABEL_6;
  }
  XmlWriter = Microsoft::Windows::Mdm::MdmDiagnosticSource::SystemInfoDiagDataSource::GetSystemInformationData((Microsoft::Windows::Mdm::MdmDiagnosticSource::SystemInfoDiagDataSource *)this);
  if ( XmlWriter < 0 )
  {
    v9 = 120;
    goto LABEL_6;
  }
  XmlWriter = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 112LL))(*v7);
  if ( XmlWriter < 0 )
  {
    v9 = 122;
    goto LABEL_6;
  }
  StreamOnHGlobal = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 248LL))(*v7);
  if ( StreamOnHGlobal < 0 )
  {
    v5 = 123;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180117f70  push    rbx
0x180117f72  push    rsi
0x180117f73  push    rdi
0x180117f74  push    r14
0x180117f76  sub     rsp, 28h
0x180117f7a  mov     r14, rdx
0x180117f7d  mov     rsi, rcx
0x180117f80  mov     r8, rdx; ppstm
0x180117f83  xor     ecx, ecx; hGlobal
0x180117f85  mov     edx, 1; fDeleteOnRelease
0x180117f8a  call    cs:__imp_CreateStreamOnHGlobal
0x180117f90  mov     ebx, eax
0x180117f92  test    eax, eax
0x180117f94  jns     short loc_180117FB6
0x180117f96  mov     edx, 72h ; 'r'; void *
0x180117f9b  mov     rcx, [rsp+48h]; this
0x180117fa0  lea     r8, aOnecoreuapAdmi_35; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180117fa7  mov     r9d, ebx; char *
0x180117faa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117faf  mov     eax, ebx
0x180117fb1  jmp     loc_1801180BA
0x180117fb6  lea     rbx, [rsi+8]
0x180117fba  mov     rcx, rbx
0x180117fbd  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180117fc2  xor     r8d, r8d; pMalloc
0x180117fc5  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180117fcc  mov     rdx, rbx; ppvObject
0x180117fcf  call    cs:__imp_CreateXmlWriter
0x180117fd5  mov     edi, eax
0x180117fd7  test    eax, eax
0x180117fd9  jns     short loc_180117FFB
0x180117fdb  mov     edx, 73h ; 's'; void *
0x180117fe0  mov     rcx, [rsp+48h]; this
0x180117fe5  lea     r8, aOnecoreuapAdmi_35; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180117fec  mov     r9d, edi; char *
0x180117fef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117ff4  mov     eax, edi
0x180117ff6  jmp     loc_1801180BA
0x180117ffb  mov     rcx, [rbx]
0x180117ffe  mov     rdx, [r14]
0x180118001  mov     rax, [rcx]
0x180118004  mov     rax, [rax+18h]
0x180118008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011800d  mov     edi, eax
0x18011800f  test    eax, eax
0x180118011  jns     short loc_18011801A
0x180118013  mov     edx, 74h ; 't'
0x180118018  jmp     short loc_180117FE0
0x18011801a  mov     rcx, [rbx]
0x18011801d  mov     edx, 1
0x180118022  mov     r8d, edx
0x180118025  mov     rax, [rcx]
0x180118028  mov     rax, [rax+28h]
0x18011802c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118031  mov     edi, eax
0x180118033  test    eax, eax
0x180118035  jns     short loc_18011803E
0x180118037  mov     edx, 75h ; 'u'
0x18011803c  jmp     short loc_180117FE0
0x18011803e  mov     rcx, [rbx]
0x180118041  xor     edx, edx
0x180118043  mov     rax, [rcx]
0x180118046  mov     rax, [rax+0D0h]
0x18011804d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118052  mov     edi, eax
0x180118054  test    eax, eax
0x180118056  jns     short loc_18011805F
0x180118058  mov     edx, 76h ; 'v'
0x18011805d  jmp     short loc_180117FE0
0x18011805f  mov     rcx, rsi; this
0x180118062  call    ?GetSystemInformationData@SystemInfoDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SystemInfoDiagDataSource::GetSystemInformationData(void)
0x180118067  mov     edi, eax
0x180118069  test    eax, eax
0x18011806b  jns     short loc_180118077
0x18011806d  mov     edx, 78h ; 'x'
0x180118072  jmp     loc_180117FE0
0x180118077  mov     rcx, [rbx]
0x18011807a  mov     rax, [rcx]
0x18011807d  mov     rax, [rax+70h]
0x180118081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118086  mov     edi, eax
0x180118088  test    eax, eax
0x18011808a  jns     short loc_180118096
0x18011808c  mov     edx, 7Ah ; 'z'
0x180118091  jmp     loc_180117FE0
0x180118096  mov     rcx, [rbx]
0x180118099  mov     rax, [rcx]
0x18011809c  mov     rax, [rax+0F8h]
0x1801180a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801180a8  mov     ebx, eax
0x1801180aa  test    eax, eax
0x1801180ac  jns     short loc_1801180B8
0x1801180ae  mov     edx, 7Bh ; '{'
0x1801180b3  jmp     loc_180117F9B
0x1801180b8  xor     eax, eax
0x1801180ba  add     rsp, 28h
0x1801180be  pop     r14
0x1801180c0  pop     rdi
0x1801180c1  pop     rsi
0x1801180c2  pop     rbx
0x1801180c3  retn
```
