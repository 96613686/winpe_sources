# Appx::Packaging::Manifest::ManifestReaderBase::ValidateSchemaAndInitializeBase(IStream *,Appx::Packaging::IXmlSchemaProvider *,XmlNamespaceAlias *,ulong,bool,ushort const *)

- ea: `0x180009f04`
- end: `0x18000a16e`
- name: `?ValidateSchemaAndInitializeBase@ManifestReaderBase@Manifest@Packaging@Appx@@QEAAJPEAUIStream@@PEAUIXmlSchemaProvider@34@PEAUXmlNamespaceAlias@@K_NPEBG@Z`
- size: `618`
- prototype: `__int64 __fastcall(Appx::Packaging::Manifest::ManifestReaderBase *this, struct IStream *, struct Appx::Packaging::IXmlSchemaProvider *, struct XmlNamespaceAlias *, unsigned int, bool, Appx::Packaging *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800157c8`
- `0x180021440`

## callees

- `0x180005eb8`
- `0x180007a28`
- `0x1800093b4`
- `0x180009eb8`
- `0x180009f04`
- `0x1800133fc`
- `0x18005dbd8`
- `0x180071f50`
- `0x180106010`

## import_xrefs

- `OpcServices!__imp_GetCloneableStream` at `0x180009f45`
- `OpcServices!__imp_GetCloneableStream` at `0x18000a06e`
- `OpcServices!__imp_GetCloneableStream` at `0x180009f45`
- `OpcServices!__imp_GetCloneableStream` at `0x18000a06e`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000a016`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000a016`

## string_xrefs

- `0x180009fab`: `AppxPackaging.dll`
- `0x18000a0aa`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x18000a0cc`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x18000a106`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x18000a134`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::ManifestReaderBase::ValidateSchemaAndInitializeBase(
        Appx::Packaging::Manifest::ManifestReaderBase *this,
        struct IStream *a2,
        struct Appx::Packaging::IXmlSchemaProvider *a3,
        struct XmlNamespaceAlias *a4,
        unsigned int a5,
        bool a6,
        Appx::Packaging *a7)
{
  HRESULT StreamOnHGlobal; // ebx
  unsigned __int64 v12; // r8
  int v13; // eax
  const unsigned __int16 *v14; // rcx
  Appx::Packaging *v15; // rax
  const unsigned __int16 *v17; // r8
  int CloneableStream; // eax
  LPSTREAM v19; // rcx
  __int64 v20; // rdx
  Appx::Packaging *v21; // rcx
  __int64 v22; // rdx
  LPSTREAM v23; // rcx
  int v24; // [rsp+20h] [rbp-38h]
  Appx::Packaging *v25; // [rsp+40h] [rbp-18h] BYREF
  LPSTREAM ppstm[2]; // [rsp+48h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]

  v25 = 0;
  if ( a6 )
  {
    ppstm[0] = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(ppstm);
    StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, ppstm);
    if ( StreamOnHGlobal < 0 )
    {
      v22 = 60;
    }
    else
    {
      StreamOnHGlobal = Appx::Packaging::CopyStreamAndCalculateDigest(a2, ppstm[0]);
      if ( StreamOnHGlobal < 0 )
      {
        v22 = 62;
      }
      else
      {
        StreamOnHGlobal = Appx::Packaging::VerifyDigest(a7, *((const unsigned __int16 **)this + 4), v17);
        if ( StreamOnHGlobal >= 0 )
        {
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v25);
          CloneableStream = GetCloneableStream(ppstm[0], &v25);
          StreamOnHGlobal = CloneableStream;
          if ( CloneableStream < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x42,
              (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
              (const char *)(unsigned int)CloneableStream,
              v24);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(ppstm);
            goto LABEL_7;
          }
          v19 = ppstm[0];
          if ( ppstm[0] )
          {
            ppstm[0] = 0;
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v19 + 16LL))(v19);
          }
LABEL_3:
          v13 = Appx::Packaging::SetStreamPosition(v25, 0, v12);
          StreamOnHGlobal = v13;
          if ( v13 >= 0 )
          {
            v14 = *(const unsigned __int16 **)this;
            v15 = v25;
            v25 = 0;
            *(_QWORD *)this = v15;
            if ( v14 )
              (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v14 + 16LL))(v14);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease((char *)this + 16);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease((char *)this + 8);
            StreamOnHGlobal = Appx::Packaging::XmlValidationHelper::ValidateXml(
                                *(struct IStream **)this,
                                a3,
                                a4,
                                a5,
                                -2146958844,
                                L"AppxPackaging.dll",
                                (struct IXMLDOMDocument **)this + 1,
                                (struct IXMLDOMDocument **)this + 2);
            if ( StreamOnHGlobal >= 0 )
              goto LABEL_7;
            v20 = 84;
            goto LABEL_17;
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4A,
            (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
            (const char *)(unsigned int)v13,
            v24);
LABEL_7:
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v25);
          return (unsigned int)StreamOnHGlobal;
        }
        v22 = 63;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
      (const char *)(unsigned int)StreamOnHGlobal,
      v24);
    v23 = ppstm[0];
    if ( ppstm[0] )
    {
      ppstm[0] = 0;
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v23 + 16LL))(v23);
    }
    goto LABEL_18;
  }
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v25);
  StreamOnHGlobal = GetCloneableStream(a2, &v25);
  if ( StreamOnHGlobal >= 0 )
    goto LABEL_3;
  v20 = 71;
LABEL_17:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v20,
    (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
    (const char *)(unsigned int)StreamOnHGlobal,
    v24);
LABEL_18:
  v21 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(Appx::Packaging *))(*(_QWORD *)v21 + 16LL))(v21);
  }
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x180009f04  push    rbp
0x180009f06  push    rbx
0x180009f07  push    rsi
0x180009f08  push    rdi
0x180009f09  push    r12
0x180009f0b  push    r13
0x180009f0d  push    r14
0x180009f0f  push    r15
0x180009f11  mov     rbp, rsp
0x180009f14  sub     rsp, 58h
0x180009f18  xor     r13d, r13d
0x180009f1b  mov     r15, r9
0x180009f1e  mov     r12, r8
0x180009f21  mov     r14, rdx
0x180009f24  mov     rsi, rcx
0x180009f27  mov     [rbp+var_18], r13
0x180009f2b  cmp     [rbp+arg_28], r13b
0x180009f2f  jnz     loc_180009FFE
0x180009f35  lea     rcx, [rbp+var_18]
0x180009f39  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180009f3e  lea     rdx, [rbp+var_18]
0x180009f42  mov     rcx, r14
0x180009f45  call    cs:__imp_GetCloneableStream
0x180009f4c  nop     dword ptr [rax+rax+00h]
0x180009f51  mov     ebx, eax
0x180009f53  test    eax, eax
0x180009f55  js      loc_18000A0C3
0x180009f5b  mov     rcx, [rbp+var_18]; this
0x180009f5f  xor     edx, edx; struct IStream *
0x180009f61  call    ?SetStreamPosition@Packaging@Appx@@YAJPEAUIStream@@_K@Z; Appx::Packaging::SetStreamPosition(IStream *,unsigned __int64)
0x180009f66  mov     ebx, eax
0x180009f68  test    eax, eax
0x180009f6a  js      loc_18000A0A6
0x180009f70  mov     rcx, [rsi]
0x180009f73  mov     rax, [rbp+var_18]
0x180009f77  mov     [rbp+var_18], r13
0x180009f7b  mov     [rsi], rax
0x180009f7e  test    rcx, rcx
0x180009f81  jz      short loc_180009F8F
0x180009f83  mov     rax, [rcx]
0x180009f86  mov     rax, [rax+10h]
0x180009f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f8f  lea     rdi, [rsi+10h]
0x180009f93  mov     rcx, rdi
0x180009f96  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180009f9b  lea     rbx, [rsi+8]
0x180009f9f  mov     rcx, rbx
0x180009fa2  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180009fa7  mov     r9d, [rbp+arg_20]; unsigned int
0x180009fab  lea     rax, LibFileName; "AppxPackaging.dll"
0x180009fb2  mov     rcx, [rsi]; struct IStream *
0x180009fb5  mov     r8, r15; struct XmlNamespaceAlias *
0x180009fb8  mov     [rsp+58h+var_20], rdi; struct IXMLDOMDocument **
0x180009fbd  mov     rdx, r12; struct Appx::Packaging::IXmlSchemaProvider *
0x180009fc0  mov     [rsp+58h+var_28], rbx; struct IXMLDOMDocument **
0x180009fc5  mov     [rsp+58h+var_30], rax; unsigned __int16 *
0x180009fca  mov     [rsp+58h+var_38], 80080204h; int
0x180009fd2  call    ?ValidateXml@XmlValidationHelper@Packaging@Appx@@SAJPEAUIStream@@PEAUIXmlSchemaProvider@23@PEAUXmlNamespaceAlias@@KJPEBGPEAPEAUIXMLDOMDocument@@4@Z; Appx::Packaging::XmlValidationHelper::ValidateXml(IStream *,Appx::Packaging::IXmlSchemaProvider *,XmlNamespaceAlias *,ulong,long,ushort const *,IXMLDOMDocument * *,IXMLDOMDocument * *)
0x180009fd7  mov     ebx, eax
0x180009fd9  test    eax, eax
0x180009fdb  js      loc_18000A164
0x180009fe1  lea     rcx, [rbp+var_18]
0x180009fe5  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180009fea  mov     eax, ebx
0x180009fec  add     rsp, 58h
0x180009ff0  pop     r15
0x180009ff2  pop     r14
0x180009ff4  pop     r13
0x180009ff6  pop     r12
0x180009ff8  pop     rdi
0x180009ff9  pop     rsi
0x180009ffa  pop     rbx
0x180009ffb  pop     rbp
0x180009ffc  retn
0x180009ffe  lea     rcx, [rbp+ppstm]
0x18000a002  mov     [rbp+ppstm], r13
0x18000a006  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18000a00b  lea     r8, [rbp+ppstm]; ppstm
0x18000a00f  mov     edx, 1; fDeleteOnRelease
0x18000a014  xor     ecx, ecx; hGlobal
0x18000a016  call    cs:__imp_CreateStreamOnHGlobal
0x18000a01d  nop     dword ptr [rax+rax+00h]
0x18000a022  mov     ebx, eax
0x18000a024  test    eax, eax
0x18000a026  js      loc_18000A15D
0x18000a02c  mov     rdx, [rbp+ppstm]
0x18000a030  lea     r8, [rsi+20h]
0x18000a034  mov     rcx, r14
0x18000a037  call    ?CopyStreamAndCalculateDigest@Packaging@Appx@@YAJPEAUIStream@@0AEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Z; Appx::Packaging::CopyStreamAndCalculateDigest(IStream *,IStream *,Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> &)
0x18000a03c  mov     ebx, eax
0x18000a03e  test    eax, eax
0x18000a040  js      loc_18000A0FD
0x18000a046  mov     rdx, [rsi+20h]; unsigned __int16 *
0x18000a04a  mov     rcx, [rbp+arg_30]; this
0x18000a04e  call    ?VerifyDigest@Packaging@Appx@@YAJPEBG0@Z; Appx::Packaging::VerifyDigest(ushort const *,ushort const *)
0x18000a053  mov     ebx, eax
0x18000a055  test    eax, eax
0x18000a057  js      loc_18000A156
0x18000a05d  lea     rcx, [rbp+var_18]
0x18000a061  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18000a066  mov     rcx, [rbp+ppstm]
0x18000a06a  lea     rdx, [rbp+var_18]
0x18000a06e  call    cs:__imp_GetCloneableStream
0x18000a075  nop     dword ptr [rax+rax+00h]
0x18000a07a  mov     ebx, eax
0x18000a07c  test    eax, eax
0x18000a07e  js      loc_18000A130
0x18000a084  mov     rcx, [rbp+ppstm]
0x18000a088  test    rcx, rcx
0x18000a08b  jz      loc_180009F5B
0x18000a091  mov     [rbp+ppstm], r13
0x18000a095  mov     rax, [rcx]
0x18000a098  mov     rax, [rax+10h]
0x18000a09c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0a1  jmp     loc_180009F5B
0x18000a0a6  mov     rcx, [rbp+40h]; this
0x18000a0aa  lea     r8, aOnecorePrintsc_124; "onecore\\printscan\\appxpackaging\\mani"...
0x18000a0b1  mov     r9d, ebx; char *
0x18000a0b4  mov     edx, 4Ah ; 'J'; void *
0x18000a0b9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a0be  jmp     loc_180009FE1
0x18000a0c3  mov     edx, 47h ; 'G'; void *
0x18000a0c8  mov     rcx, [rbp+40h]; this
0x18000a0cc  lea     r8, aOnecorePrintsc_124; "onecore\\printscan\\appxpackaging\\mani"...
0x18000a0d3  mov     r9d, ebx; char *
0x18000a0d6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a0db  mov     rcx, [rbp+var_18]
0x18000a0df  test    rcx, rcx
0x18000a0e2  jz      loc_180009FEA
0x18000a0e8  mov     [rbp+var_18], r13
0x18000a0ec  mov     rax, [rcx]
0x18000a0ef  mov     rax, [rax+10h]
0x18000a0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0f8  jmp     loc_180009FEA
0x18000a0fd  mov     edx, 3Eh ; '>'; void *
0x18000a102  mov     rcx, [rbp+40h]; this
0x18000a106  lea     r8, aOnecorePrintsc_124; "onecore\\printscan\\appxpackaging\\mani"...
0x18000a10d  mov     r9d, ebx; char *
0x18000a110  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a115  mov     rcx, [rbp+ppstm]
0x18000a119  test    rcx, rcx
0x18000a11c  jz      short loc_18000A0DB
0x18000a11e  mov     [rbp+ppstm], r13
0x18000a122  mov     rax, [rcx]
0x18000a125  mov     rax, [rax+10h]
0x18000a129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a12e  jmp     short loc_18000A0DB
0x18000a130  mov     rcx, [rbp+40h]; this
0x18000a134  lea     r8, aOnecorePrintsc_124; "onecore\\printscan\\appxpackaging\\mani"...
0x18000a13b  mov     r9d, ebx; char *
0x18000a13e  mov     edx, 42h ; 'B'; void *
0x18000a143  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a148  lea     rcx, [rbp+ppstm]
0x18000a14c  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18000a151  jmp     loc_180009FE1
0x18000a156  mov     edx, 3Fh ; '?'
0x18000a15b  jmp     short loc_18000A102
0x18000a15d  mov     edx, 3Ch ; '<'
0x18000a162  jmp     short loc_18000A102
0x18000a164  mov     edx, 54h ; 'T'
0x18000a169  jmp     loc_18000A0C8
```
