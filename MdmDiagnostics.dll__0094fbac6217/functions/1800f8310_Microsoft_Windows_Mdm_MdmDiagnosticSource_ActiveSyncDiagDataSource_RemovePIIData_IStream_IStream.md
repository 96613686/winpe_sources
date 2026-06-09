# Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource::RemovePIIData(IStream *,IStream * *)

- ea: `0x1800f8310`
- end: `0x1800f856d`
- name: `?RemovePIIData@ActiveSyncDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAUIStream@@PEAPEAU6@@Z`
- size: `605`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource *__hidden this, struct IStream *, struct IStream **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f7ff0`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x1800f8310`
- `0x1800f8574`
- `0x180191010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x1800f837c`
- `XmlLite!CreateXmlWriter` at `0x1800f837c`
- `XmlLite!CreateXmlReader` at `0x1800f844a`
- `XmlLite!CreateXmlReader` at `0x1800f844a`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f8334`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f8334`

## string_xrefs

- `0x1800f8347`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\activesyncdiagdata.cpp`
- `0x1800f83ad`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\activesyncdiagdata.cpp`
- `0x1800f8462`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\activesyncdiagdata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource::RemovePIIData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource *this,
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
                    XmlReader = Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource::RetrieveActiveSyncDataWithoutPII(
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
                        v11 = 182;
                      }
                      else
                      {
                        v11 = 181;
                      }
                    }
                    else
                    {
                      v11 = 178;
                    }
                  }
                  else
                  {
                    v11 = 175;
                  }
                }
                else
                {
                  v11 = 174;
                }
              }
              else
              {
                v11 = 173;
              }
            }
            else
            {
              v11 = 172;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v11,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\activesyncdiagdata.cpp",
              (const char *)(unsigned int)XmlReader,
              v13);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v16);
LABEL_28:
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(ppvObject);
            return v7;
          }
          v9 = 164;
        }
        else
        {
          v9 = 163;
        }
      }
      else
      {
        v9 = 162;
      }
    }
    else
    {
      v9 = 161;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\activesyncdiagdata.cpp",
      (const char *)(unsigned int)XmlWriter,
      v13);
    goto LABEL_28;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9D,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\activesyncdiagdata.cpp",
    (const char *)(unsigned int)StreamOnHGlobal,
    v13);
  return v7;
}

```

## disassembly

```asm
0x1800f8310  push    rbp
0x1800f8312  push    rbx
0x1800f8313  push    rsi
0x1800f8314  push    rdi
0x1800f8315  push    r12
0x1800f8317  push    r14
0x1800f8319  mov     rbp, rsp
0x1800f831c  sub     rsp, 48h
0x1800f8320  mov     rdi, r8
0x1800f8323  mov     rsi, rdx
0x1800f8326  mov     r14, rcx
0x1800f8329  mov     r12d, 1
0x1800f832f  mov     edx, r12d; fDeleteOnRelease
0x1800f8332  xor     ecx, ecx; hGlobal
0x1800f8334  call    cs:__imp_CreateStreamOnHGlobal
0x1800f833a  mov     ebx, eax
0x1800f833c  test    eax, eax
0x1800f833e  jns     short loc_1800F835D
0x1800f8340  mov     rcx, [rbp+30h]; this
0x1800f8344  mov     r9d, eax; char *
0x1800f8347  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f834e  mov     edx, 9Dh; void *
0x1800f8353  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f8358  jmp     loc_1800F855E
0x1800f835d  mov     [rbp+ppvObject], 0
0x1800f8365  lea     rcx, [rbp+ppvObject]
0x1800f8369  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f836e  xor     r8d, r8d; pMalloc
0x1800f8371  lea     rdx, [rbp+ppvObject]; ppvObject
0x1800f8375  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x1800f837c  call    cs:__imp_CreateXmlWriter
0x1800f8382  mov     ebx, eax
0x1800f8384  test    eax, eax
0x1800f8386  jns     short loc_1800F838F
0x1800f8388  mov     edx, 0A1h
0x1800f838d  jmp     short loc_1800F83AD
0x1800f838f  mov     rcx, [rbp+ppvObject]
0x1800f8393  mov     rax, [rcx]
0x1800f8396  mov     rdx, [rdi]
0x1800f8399  mov     rax, [rax+18h]
0x1800f839d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f83a2  mov     ebx, eax
0x1800f83a4  test    eax, eax
0x1800f83a6  jns     short loc_1800F83C5
0x1800f83a8  mov     edx, 0A2h; void *
0x1800f83ad  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f83b4  mov     r9d, eax; char *
0x1800f83b7  mov     rcx, [rbp+30h]; this
0x1800f83bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f83c0  jmp     loc_1800F8555
0x1800f83c5  mov     rcx, [rbp+ppvObject]
0x1800f83c9  mov     rax, [rcx]
0x1800f83cc  mov     r8, r12
0x1800f83cf  mov     edx, r12d
0x1800f83d2  mov     rax, [rax+28h]
0x1800f83d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f83db  mov     ebx, eax
0x1800f83dd  test    eax, eax
0x1800f83df  jns     short loc_1800F83E8
0x1800f83e1  mov     edx, 0A3h
0x1800f83e6  jmp     short loc_1800F83AD
0x1800f83e8  mov     rcx, [rbp+ppvObject]
0x1800f83ec  mov     rax, [rcx]
0x1800f83ef  xor     edx, edx
0x1800f83f1  mov     rax, [rax+0D0h]
0x1800f83f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f83fd  mov     ebx, eax
0x1800f83ff  test    eax, eax
0x1800f8401  jns     short loc_1800F840A
0x1800f8403  mov     edx, 0A4h
0x1800f8408  jmp     short loc_1800F83AD
0x1800f840a  mov     [rbp+var_10], 0
0x1800f8412  mov     rax, [rsi]
0x1800f8415  xor     r9d, r9d
0x1800f8418  xor     r8d, r8d
0x1800f841b  mov     rdx, [rbp+var_10]
0x1800f841f  mov     rcx, rsi
0x1800f8422  mov     rax, [rax+28h]
0x1800f8426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f842b  mov     [rbp+arg_18], 0
0x1800f8433  lea     rcx, [rbp+arg_18]
0x1800f8437  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f843c  xor     r8d, r8d; pMalloc
0x1800f843f  lea     rdx, [rbp+arg_18]; ppvObject
0x1800f8443  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800f844a  call    cs:__imp_CreateXmlReader
0x1800f8450  mov     ebx, eax
0x1800f8452  test    eax, eax
0x1800f8454  jns     short loc_1800F847D
0x1800f8456  mov     edx, 0ACh; void *
0x1800f845b  mov     rcx, [rbp+30h]; this
0x1800f845f  mov     r9d, eax; char *
0x1800f8462  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f8469  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f846e  nop
0x1800f846f  lea     rcx, [rbp+arg_18]
0x1800f8473  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f8478  jmp     loc_1800F8555
0x1800f847d  mov     rcx, [rbp+arg_18]
0x1800f8481  mov     rax, [rcx]
0x1800f8484  xor     r8d, r8d
0x1800f8487  lea     edx, [r8+4]
0x1800f848b  mov     rax, [rax+28h]
0x1800f848f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8494  mov     ebx, eax
0x1800f8496  test    eax, eax
0x1800f8498  jns     short loc_1800F84A1
0x1800f849a  mov     edx, 0ADh
0x1800f849f  jmp     short loc_1800F845B
0x1800f84a1  mov     rcx, [rbp+arg_18]
0x1800f84a5  mov     rax, [rcx]
0x1800f84a8  mov     r8, r12
0x1800f84ab  mov     edx, r12d
0x1800f84ae  mov     rax, [rax+28h]
0x1800f84b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f84b7  mov     ebx, eax
0x1800f84b9  test    eax, eax
0x1800f84bb  jns     short loc_1800F84C4
0x1800f84bd  mov     edx, 0AEh
0x1800f84c2  jmp     short loc_1800F845B
0x1800f84c4  mov     rcx, [rbp+arg_18]
0x1800f84c8  mov     rax, [rcx]
0x1800f84cb  mov     rdx, rsi
0x1800f84ce  mov     rax, [rax+18h]
0x1800f84d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f84d7  mov     ebx, eax
0x1800f84d9  test    eax, eax
0x1800f84db  jns     short loc_1800F84E7
0x1800f84dd  mov     edx, 0AFh
0x1800f84e2  jmp     loc_1800F845B
0x1800f84e7  mov     r8, [rbp+ppvObject]; struct IXmlWriter *
0x1800f84eb  mov     rdx, [rbp+arg_18]; struct IXmlReader *
0x1800f84ef  mov     rcx, r14; this
0x1800f84f2  call    ?RetrieveActiveSyncDataWithoutPII@ActiveSyncDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAUIXmlReader@@PEAUIXmlWriter@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource::RetrieveActiveSyncDataWithoutPII(IXmlReader *,IXmlWriter *)
0x1800f84f7  mov     ebx, eax
0x1800f84f9  test    eax, eax
0x1800f84fb  jns     short loc_1800F8507
0x1800f84fd  mov     edx, 0B2h
0x1800f8502  jmp     loc_1800F845B
0x1800f8507  mov     rcx, [rbp+ppvObject]
0x1800f850b  mov     rax, [rcx]
0x1800f850e  mov     rax, [rax+70h]
0x1800f8512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8517  mov     ebx, eax
0x1800f8519  test    eax, eax
0x1800f851b  jns     short loc_1800F8527
0x1800f851d  mov     edx, 0B5h
0x1800f8522  jmp     loc_1800F845B
0x1800f8527  mov     rcx, [rbp+ppvObject]
0x1800f852b  mov     rax, [rcx]
0x1800f852e  mov     rax, [rax+0F8h]
0x1800f8535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f853a  mov     ebx, eax
0x1800f853c  test    eax, eax
0x1800f853e  jns     short loc_1800F854A
0x1800f8540  mov     edx, 0B6h
0x1800f8545  jmp     loc_1800F845B
0x1800f854a  lea     rcx, [rbp+arg_18]
0x1800f854e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f8553  xor     ebx, ebx
0x1800f8555  lea     rcx, [rbp+ppvObject]
0x1800f8559  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f855e  mov     eax, ebx
0x1800f8560  add     rsp, 48h
0x1800f8564  pop     r14
0x1800f8566  pop     r12
0x1800f8568  pop     rdi
0x1800f8569  pop     rsi
0x1800f856a  pop     rbx
0x1800f856b  pop     rbp
0x1800f856c  retn
```
