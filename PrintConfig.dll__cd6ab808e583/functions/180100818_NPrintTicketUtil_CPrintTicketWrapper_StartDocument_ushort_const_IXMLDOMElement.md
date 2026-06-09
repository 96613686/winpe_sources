# NPrintTicketUtil::CPrintTicketWrapper::StartDocument(ushort const *,IXMLDOMElement * *)

- ea: `0x180100818`
- end: `0x180100af5`
- name: `?StartDocument@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEBGPEAPEAUIXMLDOMElement@@@Z`
- size: `733`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrintTicketWrapper *__hidden this, const unsigned __int16 *, struct IXMLDOMElement **)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800f3900`
- `0x18010fff8`
- `0x180110780`
- `0x180128f80`
- `0x180136a68`
- `0x1801371f0`

## callees

- `0x1800ed328`
- `0x1800eedb8`
- `0x180100818`
- `0x1801c3010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1801008a4`
- `OLEAUT32!__imp_VariantInit` at `0x180100a15`
- `OLEAUT32!__imp_VariantInit` at `0x1801008a4`
- `OLEAUT32!__imp_VariantInit` at `0x180100a15`
- `OLEAUT32!__imp_VariantClear` at `0x1801008fb`
- `OLEAUT32!__imp_VariantClear` at `0x180100a74`
- `OLEAUT32!__imp_VariantClear` at `0x1801008fb`
- `OLEAUT32!__imp_VariantClear` at `0x180100a74`
- `ole32!CoCreateInstance` at `0x18010086b`
- `ole32!CoCreateInstance` at `0x18010086b`

## string_xrefs

- `0x180100a95`: `http://www.w3.org/2001/XMLSchema-instance`
- `0x180100ab2`: `http://www.w3.org/2001/XMLSchema`
- `0x180100ab9`: `xmlns:xsd`
- `0x180100a9c`: `xmlns:xsi`
- `0x1801008db`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x180100925`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x18010092c`: `xmlns:psf`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::StartDocument(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMDocument2 **a2,
        struct IXMLDOMElement **a3)
{
  __int64 **v5; // rsi
  HRESULT DomDocument; // ebx
  __int64 *v7; // rcx
  NPrintTicketUtil::CPrintTicketWrapper *v8; // rcx
  __int64 *v9; // rcx
  __int64 v10; // rax
  struct IXMLDOMElement *v11; // rcx
  NPrintTicketUtil::CPrintTicketWrapper *v12; // rcx
  NPrintTicketUtil::CPrintTicketWrapper *v13; // rcx
  VARIANTARG pvarg; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG v16; // [rsp+50h] [rbp-20h] BYREF
  __int64 v17; // [rsp+A0h] [rbp+30h] BYREF
  struct IXMLDOMElement *v18; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v19; // [rsp+B8h] [rbp+48h] BYREF

  v18 = (struct IXMLDOMElement *)a3;
  v5 = (__int64 **)((char *)this + 8);
  DomDocument = NPrintTicketUtil::CreateDomDocument((LPVOID *)this + 1, a2);
  if ( DomDocument >= 0 )
  {
    DomDocument = CoCreateInstance(&CLSID_MXNamespaceManager60, 0, 1u, &IID_IMXNamespaceManager, (LPVOID *)this + 2);
    if ( DomDocument >= 0 )
    {
      v19 = 0;
      v17 = 0;
      v18 = 0;
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      pvarg.vt = 3;
      pvarg.lVal = 1;
      v7 = *v5;
      v16 = pvarg;
      DomDocument = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, struct IXMLDOMDocument2 **, const unsigned __int16 *, __int64 *))(*v7 + 448))(
                      v7,
                      &v16,
                      a2,
                      L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
                      &v19);
      VariantClear(&pvarg);
      if ( DomDocument >= 0 )
      {
        DomDocument = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IXMLDOMElement **))v19)(
                        v19,
                        &IID_IXMLDOMElement,
                        &v18);
        if ( DomDocument >= 0 )
        {
          DomDocument = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(
                          v8,
                          v18,
                          L"xmlns:psf",
                          L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework");
          if ( DomDocument >= 0 )
          {
            DomDocument = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(**v5 + 168))(*v5, v19, &v17);
            if ( DomDocument >= 0 )
              DomDocument = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))v17)(
                              v17,
                              &IID_IXMLDOMElement,
                              (char *)this + 24);
          }
        }
      }
      if ( v18 )
      {
        ((void (__fastcall *)(struct IXMLDOMElement *))v18->lpVtbl->Release)(v18);
        v18 = 0;
      }
      if ( v17 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        v17 = 0;
      }
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      if ( DomDocument >= 0 )
      {
        v18 = 0;
        memset(&pvarg, 0, sizeof(pvarg));
        DomDocument = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, const OLECHAR *, struct IXMLDOMElement **))(**v5 + 416))(
                        *v5,
                        L"xml",
                        L"version=\"1.0\" encoding=\"UTF-8\"",
                        &v18);
        VariantInit(&pvarg);
        if ( DomDocument >= 0 )
        {
          DomDocument = (*(__int64 (__fastcall **)(__int64 *, CY *))(**v5 + 104))(*v5, &pvarg.cyVal);
          if ( DomDocument >= 0 )
          {
            pvarg.vt = 13;
            v9 = *v5;
            v10 = **v5;
            v16 = pvarg;
            (*(void (__fastcall **)(__int64 *, struct IXMLDOMElement *, VARIANTARG *, _QWORD))(v10 + 144))(
              v9,
              v18,
              &v16,
              0);
          }
        }
        VariantClear(&pvarg);
        v11 = v18;
        if ( v18 )
          ((void (__fastcall *)(struct IXMLDOMElement *))v18->lpVtbl->Release)(v18);
        if ( DomDocument >= 0 )
        {
          DomDocument = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(
                          (NPrintTicketUtil::CPrintTicketWrapper *)v11,
                          *((struct IXMLDOMElement **)this + 3),
                          L"xmlns:xsi",
                          L"http://www.w3.org/2001/XMLSchema-instance");
          if ( DomDocument >= 0 )
          {
            DomDocument = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(
                            v12,
                            *((struct IXMLDOMElement **)this + 3),
                            L"xmlns:xsd",
                            L"http://www.w3.org/2001/XMLSchema");
            if ( DomDocument >= 0 )
              return (unsigned int)NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(
                                     v13,
                                     *((struct IXMLDOMElement **)this + 3),
                                     L"version",
                                     L"1");
          }
        }
      }
    }
  }
  return (unsigned int)DomDocument;
}

```

## disassembly

```asm
0x180100818  mov     [rsp-28h+arg_10], r8
0x18010081d  push    rbp
0x18010081e  push    rbx
0x18010081f  push    rsi
0x180100820  push    rdi
0x180100821  push    r14
0x180100823  mov     rbp, rsp
0x180100826  sub     rsp, 70h
0x18010082a  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x180100832  mov     r14, rdx
0x180100835  mov     rdi, rcx
0x180100838  lea     rsi, [rcx+8]
0x18010083c  mov     rcx, rsi; ppv
0x18010083f  call    ?CreateDomDocument@NPrintTicketUtil@@YAJPEAPEAUIXMLDOMDocument2@@@Z; NPrintTicketUtil::CreateDomDocument(IXMLDOMDocument2 * *)
0x180100844  mov     ebx, eax
0x180100846  test    eax, eax
0x180100848  js      loc_180100AE8
0x18010084e  lea     rax, [rdi+10h]
0x180100852  mov     [rsp+70h+ppv], rax; ppv
0x180100857  lea     r9, IID_IMXNamespaceManager; riid
0x18010085e  xor     edx, edx; pUnkOuter
0x180100860  lea     r8d, [rdx+1]; dwClsContext
0x180100864  lea     rcx, CLSID_MXNamespaceManager60; rclsid
0x18010086b  call    cs:__imp_CoCreateInstance
0x180100871  mov     ebx, eax
0x180100873  test    eax, eax
0x180100875  js      loc_180100AE8
0x18010087b  mov     [rbp+arg_18], 0
0x180100883  mov     [rbp+arg_0], 0
0x18010088b  mov     [rbp+arg_10], 0
0x180100893  xorps   xmm0, xmm0
0x180100896  xor     eax, eax
0x180100898  movups  xmmword ptr [rbp+pvarg], xmm0
0x18010089c  mov     qword ptr [rbp+pvarg+10h], rax
0x1801008a0  lea     rcx, [rbp+pvarg]; pvarg
0x1801008a4  call    cs:__imp_VariantInit
0x1801008aa  mov     eax, 3
0x1801008af  mov     word ptr [rbp+pvarg], ax
0x1801008b3  mov     dword ptr [rbp+pvarg+8], 1
0x1801008ba  mov     rcx, [rsi]
0x1801008bd  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1801008c1  movaps  [rbp+var_20], xmm0
0x1801008c5  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1801008ca  movsd   [rbp+var_10], xmm1
0x1801008cf  mov     rax, [rcx]
0x1801008d2  lea     rdx, [rbp+arg_18]
0x1801008d6  mov     [rsp+70h+ppv], rdx
0x1801008db  lea     r9, aHttpSchemasMic_9; "http://schemas.microsoft.com/windows/20"...
0x1801008e2  mov     r8, r14
0x1801008e5  lea     rdx, [rbp+var_20]
0x1801008e9  mov     rax, [rax+1C0h]
0x1801008f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801008f5  mov     ebx, eax
0x1801008f7  lea     rcx, [rbp+pvarg]; pvarg
0x1801008fb  call    cs:__imp_VariantClear
0x180100901  test    ebx, ebx
0x180100903  js      short loc_18010097E
0x180100905  mov     rcx, [rbp+arg_18]
0x180100909  mov     rax, [rcx]
0x18010090c  lea     r8, [rbp+arg_10]
0x180100910  lea     rdx, IID_IXMLDOMElement
0x180100917  mov     rax, [rax]
0x18010091a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010091f  mov     ebx, eax
0x180100921  test    eax, eax
0x180100923  js      short loc_18010097E
0x180100925  lea     r9, aHttpSchemasMic_9; "http://schemas.microsoft.com/windows/20"...
0x18010092c  lea     r8, aXmlnsPsf; "xmlns:psf"
0x180100933  mov     rdx, [rbp+arg_10]; struct IXMLDOMElement *
0x180100937  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x18010093c  mov     ebx, eax
0x18010093e  test    eax, eax
0x180100940  js      short loc_18010097E
0x180100942  mov     rcx, [rsi]
0x180100945  mov     rax, [rcx]
0x180100948  lea     r8, [rbp+arg_0]
0x18010094c  mov     rdx, [rbp+arg_18]
0x180100950  mov     rax, [rax+0A8h]
0x180100957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010095c  mov     ebx, eax
0x18010095e  test    eax, eax
0x180100960  js      short loc_18010097E
0x180100962  mov     rcx, [rbp+arg_0]
0x180100966  mov     rax, [rcx]
0x180100969  lea     r8, [rdi+18h]
0x18010096d  lea     rdx, IID_IXMLDOMElement
0x180100974  mov     rax, [rax]
0x180100977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010097c  mov     ebx, eax
0x18010097e  mov     rcx, [rbp+arg_10]
0x180100982  test    rcx, rcx
0x180100985  jz      short loc_18010099B
0x180100987  mov     rax, [rcx]
0x18010098a  mov     rax, [rax+10h]
0x18010098e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100993  mov     [rbp+arg_10], 0
0x18010099b  mov     rcx, [rbp+arg_0]
0x18010099f  test    rcx, rcx
0x1801009a2  jz      short loc_1801009B8
0x1801009a4  mov     rax, [rcx]
0x1801009a7  mov     rax, [rax+10h]
0x1801009ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801009b0  mov     [rbp+arg_0], 0
0x1801009b8  mov     rcx, [rbp+arg_18]
0x1801009bc  test    rcx, rcx
0x1801009bf  jz      short loc_1801009CE
0x1801009c1  mov     rax, [rcx]
0x1801009c4  mov     rax, [rax+10h]
0x1801009c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801009cd  nop
0x1801009ce  test    ebx, ebx
0x1801009d0  js      loc_180100AE8
0x1801009d6  mov     [rbp+arg_10], 0
0x1801009de  xorps   xmm0, xmm0
0x1801009e1  xor     eax, eax
0x1801009e3  movups  xmmword ptr [rbp+pvarg], xmm0
0x1801009e7  mov     qword ptr [rbp+pvarg+10h], rax
0x1801009eb  mov     rcx, [rsi]
0x1801009ee  mov     rax, [rcx]
0x1801009f1  lea     r9, [rbp+arg_10]
0x1801009f5  lea     r8, aVersion10Encod; "version=\"1.0\" encoding=\"UTF-8\""
0x1801009fc  lea     rdx, aXml_0; "xml"
0x180100a03  mov     rax, [rax+1A0h]
0x180100a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100a0f  mov     ebx, eax
0x180100a11  lea     rcx, [rbp+pvarg]; pvarg
0x180100a15  call    cs:__imp_VariantInit
0x180100a1b  test    ebx, ebx
0x180100a1d  js      short loc_180100A70
0x180100a1f  mov     rcx, [rsi]
0x180100a22  mov     rax, [rcx]
0x180100a25  lea     rdx, [rbp+pvarg+8]
0x180100a29  mov     rax, [rax+68h]
0x180100a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100a32  mov     ebx, eax
0x180100a34  test    eax, eax
0x180100a36  js      short loc_180100A70
0x180100a38  mov     eax, 0Dh
0x180100a3d  mov     word ptr [rbp+pvarg], ax
0x180100a41  mov     rcx, [rsi]
0x180100a44  mov     rax, [rcx]
0x180100a47  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180100a4b  movaps  [rbp+var_20], xmm0
0x180100a4f  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180100a54  movsd   [rbp+var_10], xmm1
0x180100a59  xor     r9d, r9d
0x180100a5c  lea     r8, [rbp+var_20]
0x180100a60  mov     rdx, [rbp+arg_10]
0x180100a64  mov     rax, [rax+90h]
0x180100a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100a70  lea     rcx, [rbp+pvarg]; pvarg
0x180100a74  call    cs:__imp_VariantClear
0x180100a7a  nop
0x180100a7b  mov     rcx, [rbp+arg_10]
0x180100a7f  test    rcx, rcx
0x180100a82  jz      short loc_180100A91
0x180100a84  mov     rax, [rcx]
0x180100a87  mov     rax, [rax+10h]
0x180100a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100a90  nop
0x180100a91  test    ebx, ebx
0x180100a93  js      short loc_180100AE8
0x180100a95  lea     r9, aHttpWwwW3Org20_0; "http://www.w3.org/2001/XMLSchema-instan"...
0x180100a9c  lea     r8, aXmlnsXsi; "xmlns:xsi"
0x180100aa3  mov     rdx, [rdi+18h]; struct IXMLDOMElement *
0x180100aa7  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x180100aac  mov     ebx, eax
0x180100aae  test    eax, eax
0x180100ab0  js      short loc_180100AE8
0x180100ab2  lea     r9, aHttpWwwW3Org20; "http://www.w3.org/2001/XMLSchema"
0x180100ab9  lea     r8, aXmlnsXsd; "xmlns:xsd"
0x180100ac0  mov     rdx, [rdi+18h]; struct IXMLDOMElement *
0x180100ac4  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x180100ac9  mov     ebx, eax
0x180100acb  test    eax, eax
0x180100acd  js      short loc_180100AE8
0x180100acf  lea     r9, a1; "1"
0x180100ad6  lea     r8, aVersion; "version"
0x180100add  mov     rdx, [rdi+18h]; struct IXMLDOMElement *
0x180100ae1  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x180100ae6  mov     ebx, eax
0x180100ae8  mov     eax, ebx
0x180100aea  add     rsp, 70h
0x180100aee  pop     r14
0x180100af0  pop     rdi
0x180100af1  pop     rsi
0x180100af2  pop     rbx
0x180100af3  pop     rbp
0x180100af4  retn
```
