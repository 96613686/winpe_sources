# Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::InsertRedirectedRegKeyData(IStream *,IStream * *)

- ea: `0x180115e38`
- end: `0x180116095`
- name: `?InsertRedirectedRegKeyData@PolicyDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAUIStream@@PEAPEAU6@@Z`
- size: `605`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource *__hidden this, struct IStream *, struct IStream **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180115cc0`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x180115e38`
- `0x1801165cc`
- `0x180191010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x180115ea4`
- `XmlLite!CreateXmlWriter` at `0x180115ea4`
- `XmlLite!CreateXmlReader` at `0x180115f72`
- `XmlLite!CreateXmlReader` at `0x180115f72`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180115e5c`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180115e5c`

## string_xrefs

- `0x180115e6f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\policydiagdata.cpp`
- `0x180115ed5`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\policydiagdata.cpp`
- `0x180115f8a`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\policydiagdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::InsertRedirectedRegKeyData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource *this,
        struct IStream *a2,
        struct IStream **a3)
{
  HRESULT StreamOnHGlobal; // eax
  unsigned int v7; // ebx
  HRESULT XmlWriter; // eax
  __int64 v9; // rdx
  HRESULT XmlReader; // eax
  __int64 v11; // rdx
  int v13; // [rsp+20h] [rbp-28h]
  void *ppvObject[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  struct IXmlReader *v16; // [rsp+98h] [rbp+50h] BYREF

  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, a3);
  v7 = StreamOnHGlobal;
  if ( StreamOnHGlobal >= 0 )
  {
    ppvObject[0] = 0;
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(ppvObject);
    XmlWriter = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, ppvObject, 0);
    v7 = XmlWriter;
    if ( XmlWriter >= 0 )
    {
      XmlWriter = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvObject[0] + 24LL))(ppvObject[0], *a3);
      v7 = XmlWriter;
      if ( XmlWriter >= 0 )
      {
        XmlWriter = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject[0] + 40LL))(
                      ppvObject[0],
                      1,
                      1);
        v7 = XmlWriter;
        if ( XmlWriter >= 0 )
        {
          XmlWriter = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvObject[0] + 208LL))(ppvObject[0], 0);
          v7 = XmlWriter;
          if ( XmlWriter >= 0 )
          {
            ppvObject[1] = 0;
            (*(void (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a2 + 40LL))(a2, 0, 0, 0);
            v16 = 0;
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v16);
            XmlReader = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, (void **)&v16, 0);
            v7 = XmlReader;
            if ( XmlReader >= 0 )
            {
              XmlReader = ((__int64 (__fastcall *)(struct IXmlReader *, __int64))v16->lpVtbl->SetProperty)(v16, 4);
              v7 = XmlReader;
              if ( XmlReader >= 0 )
              {
                XmlReader = ((__int64 (__fastcall *)(struct IXmlReader *, __int64, __int64))v16->lpVtbl->SetProperty)(
                              v16,
                              1,
                              1);
                v7 = XmlReader;
                if ( XmlReader >= 0 )
                {
                  XmlReader = ((__int64 (__fastcall *)(struct IXmlReader *, struct IStream *))v16->lpVtbl->SetInput)(
                                v16,
                                a2);
                  v7 = XmlReader;
                  if ( XmlReader >= 0 )
                  {
                    XmlReader = Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::RetrieveRedirectedRegKeyData(
                                  this,
                                  v16,
                                  (struct IXmlWriter *)ppvObject[0]);
                    v7 = XmlReader;
                    if ( XmlReader >= 0 )
                    {
                      XmlReader = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject[0] + 112LL))(ppvObject[0]);
                      v7 = XmlReader;
                      if ( XmlReader >= 0 )
                      {
                        XmlReader = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject[0] + 248LL))(ppvObject[0]);
                        v7 = XmlReader;
                        if ( XmlReader >= 0 )
                        {
                          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v16);
                          v7 = 0;
                          goto LABEL_28;
                        }
                        v11 = 495;
                      }
                      else
                      {
                        v11 = 494;
                      }
                    }
                    else
                    {
                      v11 = 491;
                    }
                  }
                  else
                  {
                    v11 = 488;
                  }
                }
                else
                {
                  v11 = 487;
                }
              }
              else
              {
                v11 = 486;
              }
            }
            else
            {
              v11 = 485;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v11,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\policydiagdata.cpp",
              (const char *)(unsigned int)XmlReader,
              v13);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v16);
LABEL_28:
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(ppvObject);
            return v7;
          }
          v9 = 477;
        }
        else
        {
          v9 = 476;
        }
      }
      else
      {
        v9 = 475;
      }
    }
    else
    {
      v9 = 474;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\policydiagdata.cpp",
      (const char *)(unsigned int)XmlWriter,
      v13);
    goto LABEL_28;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1D6,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\policydiagdata.cpp",
    (const char *)(unsigned int)StreamOnHGlobal,
    v13);
  return v7;
}

```

## disassembly

```asm
0x180115e38  push    rbp
0x180115e3a  push    rbx
0x180115e3b  push    rsi
0x180115e3c  push    rdi
0x180115e3d  push    r12
0x180115e3f  push    r14
0x180115e41  mov     rbp, rsp
0x180115e44  sub     rsp, 48h
0x180115e48  mov     rdi, r8
0x180115e4b  mov     rsi, rdx
0x180115e4e  mov     r14, rcx
0x180115e51  mov     r12d, 1
0x180115e57  mov     edx, r12d; fDeleteOnRelease
0x180115e5a  xor     ecx, ecx; hGlobal
0x180115e5c  call    cs:__imp_CreateStreamOnHGlobal
0x180115e62  mov     ebx, eax
0x180115e64  test    eax, eax
0x180115e66  jns     short loc_180115E85
0x180115e68  mov     rcx, [rbp+30h]; this
0x180115e6c  mov     r9d, eax; char *
0x180115e6f  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180115e76  mov     edx, 1D6h; void *
0x180115e7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180115e80  jmp     loc_180116086
0x180115e85  mov     [rbp+ppvObject], 0
0x180115e8d  lea     rcx, [rbp+ppvObject]
0x180115e91  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180115e96  xor     r8d, r8d; pMalloc
0x180115e99  lea     rdx, [rbp+ppvObject]; ppvObject
0x180115e9d  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180115ea4  call    cs:__imp_CreateXmlWriter
0x180115eaa  mov     ebx, eax
0x180115eac  test    eax, eax
0x180115eae  jns     short loc_180115EB7
0x180115eb0  mov     edx, 1DAh
0x180115eb5  jmp     short loc_180115ED5
0x180115eb7  mov     rcx, [rbp+ppvObject]
0x180115ebb  mov     rax, [rcx]
0x180115ebe  mov     rdx, [rdi]
0x180115ec1  mov     rax, [rax+18h]
0x180115ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115eca  mov     ebx, eax
0x180115ecc  test    eax, eax
0x180115ece  jns     short loc_180115EED
0x180115ed0  mov     edx, 1DBh; void *
0x180115ed5  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180115edc  mov     r9d, eax; char *
0x180115edf  mov     rcx, [rbp+30h]; this
0x180115ee3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180115ee8  jmp     loc_18011607D
0x180115eed  mov     rcx, [rbp+ppvObject]
0x180115ef1  mov     rax, [rcx]
0x180115ef4  mov     r8, r12
0x180115ef7  mov     edx, r12d
0x180115efa  mov     rax, [rax+28h]
0x180115efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115f03  mov     ebx, eax
0x180115f05  test    eax, eax
0x180115f07  jns     short loc_180115F10
0x180115f09  mov     edx, 1DCh
0x180115f0e  jmp     short loc_180115ED5
0x180115f10  mov     rcx, [rbp+ppvObject]
0x180115f14  mov     rax, [rcx]
0x180115f17  xor     edx, edx
0x180115f19  mov     rax, [rax+0D0h]
0x180115f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115f25  mov     ebx, eax
0x180115f27  test    eax, eax
0x180115f29  jns     short loc_180115F32
0x180115f2b  mov     edx, 1DDh
0x180115f30  jmp     short loc_180115ED5
0x180115f32  mov     [rbp+var_10], 0
0x180115f3a  mov     rax, [rsi]
0x180115f3d  xor     r9d, r9d
0x180115f40  xor     r8d, r8d
0x180115f43  mov     rdx, [rbp+var_10]
0x180115f47  mov     rcx, rsi
0x180115f4a  mov     rax, [rax+28h]
0x180115f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115f53  mov     [rbp+arg_18], 0
0x180115f5b  lea     rcx, [rbp+arg_18]
0x180115f5f  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180115f64  xor     r8d, r8d; pMalloc
0x180115f67  lea     rdx, [rbp+arg_18]; ppvObject
0x180115f6b  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180115f72  call    cs:__imp_CreateXmlReader
0x180115f78  mov     ebx, eax
0x180115f7a  test    eax, eax
0x180115f7c  jns     short loc_180115FA5
0x180115f7e  mov     edx, 1E5h; void *
0x180115f83  mov     rcx, [rbp+30h]; this
0x180115f87  mov     r9d, eax; char *
0x180115f8a  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180115f91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180115f96  nop
0x180115f97  lea     rcx, [rbp+arg_18]
0x180115f9b  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180115fa0  jmp     loc_18011607D
0x180115fa5  mov     rcx, [rbp+arg_18]
0x180115fa9  mov     rax, [rcx]
0x180115fac  xor     r8d, r8d
0x180115faf  lea     edx, [r8+4]
0x180115fb3  mov     rax, [rax+28h]
0x180115fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115fbc  mov     ebx, eax
0x180115fbe  test    eax, eax
0x180115fc0  jns     short loc_180115FC9
0x180115fc2  mov     edx, 1E6h
0x180115fc7  jmp     short loc_180115F83
0x180115fc9  mov     rcx, [rbp+arg_18]
0x180115fcd  mov     rax, [rcx]
0x180115fd0  mov     r8, r12
0x180115fd3  mov     edx, r12d
0x180115fd6  mov     rax, [rax+28h]
0x180115fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115fdf  mov     ebx, eax
0x180115fe1  test    eax, eax
0x180115fe3  jns     short loc_180115FEC
0x180115fe5  mov     edx, 1E7h
0x180115fea  jmp     short loc_180115F83
0x180115fec  mov     rcx, [rbp+arg_18]
0x180115ff0  mov     rax, [rcx]
0x180115ff3  mov     rdx, rsi
0x180115ff6  mov     rax, [rax+18h]
0x180115ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115fff  mov     ebx, eax
0x180116001  test    eax, eax
0x180116003  jns     short loc_18011600F
0x180116005  mov     edx, 1E8h
0x18011600a  jmp     loc_180115F83
0x18011600f  mov     r8, [rbp+ppvObject]; struct IXmlWriter *
0x180116013  mov     rdx, [rbp+arg_18]; struct IXmlReader *
0x180116017  mov     rcx, r14; this
0x18011601a  call    ?RetrieveRedirectedRegKeyData@PolicyDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAUIXmlReader@@PEAUIXmlWriter@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::RetrieveRedirectedRegKeyData(IXmlReader *,IXmlWriter *)
0x18011601f  mov     ebx, eax
0x180116021  test    eax, eax
0x180116023  jns     short loc_18011602F
0x180116025  mov     edx, 1EBh
0x18011602a  jmp     loc_180115F83
0x18011602f  mov     rcx, [rbp+ppvObject]
0x180116033  mov     rax, [rcx]
0x180116036  mov     rax, [rax+70h]
0x18011603a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011603f  mov     ebx, eax
0x180116041  test    eax, eax
0x180116043  jns     short loc_18011604F
0x180116045  mov     edx, 1EEh
0x18011604a  jmp     loc_180115F83
0x18011604f  mov     rcx, [rbp+ppvObject]
0x180116053  mov     rax, [rcx]
0x180116056  mov     rax, [rax+0F8h]
0x18011605d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116062  mov     ebx, eax
0x180116064  test    eax, eax
0x180116066  jns     short loc_180116072
0x180116068  mov     edx, 1EFh
0x18011606d  jmp     loc_180115F83
0x180116072  lea     rcx, [rbp+arg_18]
0x180116076  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18011607b  xor     ebx, ebx
0x18011607d  lea     rcx, [rbp+ppvObject]
0x180116081  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180116086  mov     eax, ebx
0x180116088  add     rsp, 48h
0x18011608c  pop     r14
0x18011608e  pop     r12
0x180116090  pop     rdi
0x180116091  pop     rsi
0x180116092  pop     rbx
0x180116093  pop     rbp
0x180116094  retn
```
