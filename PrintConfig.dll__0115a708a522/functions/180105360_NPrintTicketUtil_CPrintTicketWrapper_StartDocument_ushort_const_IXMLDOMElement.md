# NPrintTicketUtil::CPrintTicketWrapper::StartDocument(ushort const *,IXMLDOMElement * *)

- ea: `0x180105360`
- end: `0x18010565c`
- name: `?StartDocument@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEBGPEAPEAUIXMLDOMElement@@@Z`
- size: `764`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrintTicketWrapper *this, struct IXMLDOMDocument2 **, struct IXMLDOMElement **)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800f83e0`
- `0x180114e38`
- `0x180115610`
- `0x18012ec80`
- `0x18013cbd8`
- `0x18013d3b0`

## callees

- `0x1800f1bec`
- `0x1800f370c`
- `0x180105360`
- `0x1801cb010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1801053f2`
- `OLEAUT32!__imp_VariantInit` at `0x18010556f`
- `OLEAUT32!__imp_VariantInit` at `0x1801053f2`
- `OLEAUT32!__imp_VariantInit` at `0x18010556f`
- `OLEAUT32!__imp_VariantClear` at `0x18010544f`
- `OLEAUT32!__imp_VariantClear` at `0x1801055d4`
- `OLEAUT32!__imp_VariantClear` at `0x18010544f`
- `OLEAUT32!__imp_VariantClear` at `0x1801055d4`
- `ole32!CoCreateInstance` at `0x1801053b3`
- `ole32!CoCreateInstance` at `0x1801053b3`

## string_xrefs

- `0x1801055fb`: `http://www.w3.org/2001/XMLSchema-instance`
- `0x180105618`: `http://www.w3.org/2001/XMLSchema`
- `0x180105602`: `xmlns:xsi`
- `0x18010561f`: `xmlns:xsd`
- `0x180105486`: `xmlns:psf`
- `0x18010542f`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x18010547f`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::StartDocument(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMDocument2 **a2,
        struct IXMLDOMElement **a3)
{
  __int64 **v5; // rsi
  int DomDocument; // ebx
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
        DomDocument = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, const unsigned __int16 *, struct IXMLDOMElement **))(**v5 + 416))(
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
0x180105360  mov     [rsp-28h+arg_10], r8
0x180105365  push    rbp
0x180105366  push    rbx
0x180105367  push    rsi
0x180105368  push    rdi
0x180105369  push    r14
0x18010536b  mov     rbp, rsp
0x18010536e  sub     rsp, 70h
0x180105372  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x18010537a  mov     r14, rdx
0x18010537d  mov     rdi, rcx
0x180105380  lea     rsi, [rcx+8]
0x180105384  mov     rcx, rsi; ppv
0x180105387  call    ?CreateDomDocument@NPrintTicketUtil@@YAJPEAPEAUIXMLDOMDocument2@@@Z; NPrintTicketUtil::CreateDomDocument(IXMLDOMDocument2 * *)
0x18010538c  mov     ebx, eax
0x18010538e  test    eax, eax
0x180105390  js      loc_18010564E
0x180105396  lea     rax, [rdi+10h]
0x18010539a  mov     [rsp+70h+ppv], rax; ppv
0x18010539f  lea     r9, IID_IMXNamespaceManager; riid
0x1801053a6  xor     edx, edx; pUnkOuter
0x1801053a8  lea     r8d, [rdx+1]; dwClsContext
0x1801053ac  lea     rcx, CLSID_MXNamespaceManager60; rclsid
0x1801053b3  call    cs:__imp_CoCreateInstance
0x1801053ba  nop     dword ptr [rax+rax+00h]
0x1801053bf  mov     ebx, eax
0x1801053c1  test    eax, eax
0x1801053c3  js      loc_18010564E
0x1801053c9  mov     [rbp+arg_18], 0
0x1801053d1  mov     [rbp+arg_0], 0
0x1801053d9  mov     [rbp+arg_10], 0
0x1801053e1  xorps   xmm0, xmm0
0x1801053e4  xor     eax, eax
0x1801053e6  movups  xmmword ptr [rbp+pvarg], xmm0
0x1801053ea  mov     qword ptr [rbp+pvarg+10h], rax
0x1801053ee  lea     rcx, [rbp+pvarg]; pvarg
0x1801053f2  call    cs:__imp_VariantInit
0x1801053f9  nop     dword ptr [rax+rax+00h]
0x1801053fe  mov     eax, 3
0x180105403  mov     word ptr [rbp+pvarg], ax
0x180105407  mov     dword ptr [rbp+pvarg+8], 1
0x18010540e  mov     rcx, [rsi]
0x180105411  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180105415  movaps  [rbp+var_20], xmm0
0x180105419  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18010541e  movsd   [rbp+var_10], xmm1
0x180105423  mov     rax, [rcx]
0x180105426  lea     rdx, [rbp+arg_18]
0x18010542a  mov     [rsp+70h+ppv], rdx
0x18010542f  lea     r9, aHttpSchemasMic_9; "http://schemas.microsoft.com/windows/20"...
0x180105436  mov     r8, r14
0x180105439  lea     rdx, [rbp+var_20]
0x18010543d  mov     rax, [rax+1C0h]
0x180105444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105449  mov     ebx, eax
0x18010544b  lea     rcx, [rbp+pvarg]; pvarg
0x18010544f  call    cs:__imp_VariantClear
0x180105456  nop     dword ptr [rax+rax+00h]
0x18010545b  test    ebx, ebx
0x18010545d  js      short loc_1801054D8
0x18010545f  mov     rcx, [rbp+arg_18]
0x180105463  mov     rax, [rcx]
0x180105466  lea     r8, [rbp+arg_10]
0x18010546a  lea     rdx, IID_IXMLDOMElement
0x180105471  mov     rax, [rax]
0x180105474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105479  mov     ebx, eax
0x18010547b  test    eax, eax
0x18010547d  js      short loc_1801054D8
0x18010547f  lea     r9, aHttpSchemasMic_9; "http://schemas.microsoft.com/windows/20"...
0x180105486  lea     r8, aXmlnsPsf; "xmlns:psf"
0x18010548d  mov     rdx, [rbp+arg_10]; struct IXMLDOMElement *
0x180105491  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x180105496  mov     ebx, eax
0x180105498  test    eax, eax
0x18010549a  js      short loc_1801054D8
0x18010549c  mov     rcx, [rsi]
0x18010549f  mov     rax, [rcx]
0x1801054a2  lea     r8, [rbp+arg_0]
0x1801054a6  mov     rdx, [rbp+arg_18]
0x1801054aa  mov     rax, [rax+0A8h]
0x1801054b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801054b6  mov     ebx, eax
0x1801054b8  test    eax, eax
0x1801054ba  js      short loc_1801054D8
0x1801054bc  mov     rcx, [rbp+arg_0]
0x1801054c0  mov     rax, [rcx]
0x1801054c3  lea     r8, [rdi+18h]
0x1801054c7  lea     rdx, IID_IXMLDOMElement
0x1801054ce  mov     rax, [rax]
0x1801054d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801054d6  mov     ebx, eax
0x1801054d8  mov     rcx, [rbp+arg_10]
0x1801054dc  test    rcx, rcx
0x1801054df  jz      short loc_1801054F5
0x1801054e1  mov     rax, [rcx]
0x1801054e4  mov     rax, [rax+10h]
0x1801054e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801054ed  mov     [rbp+arg_10], 0
0x1801054f5  mov     rcx, [rbp+arg_0]
0x1801054f9  test    rcx, rcx
0x1801054fc  jz      short loc_180105512
0x1801054fe  mov     rax, [rcx]
0x180105501  mov     rax, [rax+10h]
0x180105505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010550a  mov     [rbp+arg_0], 0
0x180105512  mov     rcx, [rbp+arg_18]
0x180105516  test    rcx, rcx
0x180105519  jz      short loc_180105528
0x18010551b  mov     rax, [rcx]
0x18010551e  mov     rax, [rax+10h]
0x180105522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105527  nop
0x180105528  test    ebx, ebx
0x18010552a  js      loc_18010564E
0x180105530  mov     [rbp+arg_10], 0
0x180105538  xorps   xmm0, xmm0
0x18010553b  xor     eax, eax
0x18010553d  movups  xmmword ptr [rbp+pvarg], xmm0
0x180105541  mov     qword ptr [rbp+pvarg+10h], rax
0x180105545  mov     rcx, [rsi]
0x180105548  mov     rax, [rcx]
0x18010554b  lea     r9, [rbp+arg_10]
0x18010554f  lea     r8, aVersion10Encod; "version=\"1.0\" encoding=\"UTF-8\""
0x180105556  lea     rdx, aXml_0; "xml"
0x18010555d  mov     rax, [rax+1A0h]
0x180105564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105569  mov     ebx, eax
0x18010556b  lea     rcx, [rbp+pvarg]; pvarg
0x18010556f  call    cs:__imp_VariantInit
0x180105576  nop     dword ptr [rax+rax+00h]
0x18010557b  test    ebx, ebx
0x18010557d  js      short loc_1801055D0
0x18010557f  mov     rcx, [rsi]
0x180105582  mov     rax, [rcx]
0x180105585  lea     rdx, [rbp+pvarg+8]
0x180105589  mov     rax, [rax+68h]
0x18010558d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105592  mov     ebx, eax
0x180105594  test    eax, eax
0x180105596  js      short loc_1801055D0
0x180105598  mov     eax, 0Dh
0x18010559d  mov     word ptr [rbp+pvarg], ax
0x1801055a1  mov     rcx, [rsi]
0x1801055a4  mov     rax, [rcx]
0x1801055a7  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1801055ab  movaps  [rbp+var_20], xmm0
0x1801055af  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1801055b4  movsd   [rbp+var_10], xmm1
0x1801055b9  xor     r9d, r9d
0x1801055bc  lea     r8, [rbp+var_20]
0x1801055c0  mov     rdx, [rbp+arg_10]
0x1801055c4  mov     rax, [rax+90h]
0x1801055cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801055d0  lea     rcx, [rbp+pvarg]; pvarg
0x1801055d4  call    cs:__imp_VariantClear
0x1801055db  nop     dword ptr [rax+rax+00h]
0x1801055e0  nop
0x1801055e1  mov     rcx, [rbp+arg_10]
0x1801055e5  test    rcx, rcx
0x1801055e8  jz      short loc_1801055F7
0x1801055ea  mov     rax, [rcx]
0x1801055ed  mov     rax, [rax+10h]
0x1801055f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801055f6  nop
0x1801055f7  test    ebx, ebx
0x1801055f9  js      short loc_18010564E
0x1801055fb  lea     r9, aHttpWwwW3Org20_0; "http://www.w3.org/2001/XMLSchema-instan"...
0x180105602  lea     r8, aXmlnsXsi; "xmlns:xsi"
0x180105609  mov     rdx, [rdi+18h]; struct IXMLDOMElement *
0x18010560d  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x180105612  mov     ebx, eax
0x180105614  test    eax, eax
0x180105616  js      short loc_18010564E
0x180105618  lea     r9, aHttpWwwW3Org20; "http://www.w3.org/2001/XMLSchema"
0x18010561f  lea     r8, aXmlnsXsd; "xmlns:xsd"
0x180105626  mov     rdx, [rdi+18h]; struct IXMLDOMElement *
0x18010562a  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x18010562f  mov     ebx, eax
0x180105631  test    eax, eax
0x180105633  js      short loc_18010564E
0x180105635  lea     r9, a1; "1"
0x18010563c  lea     r8, aVersion; "version"
0x180105643  mov     rdx, [rdi+18h]; struct IXMLDOMElement *
0x180105647  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x18010564c  mov     ebx, eax
0x18010564e  mov     eax, ebx
0x180105650  add     rsp, 70h
0x180105654  pop     r14
0x180105656  pop     rdi
0x180105657  pop     rsi
0x180105658  pop     rbx
0x180105659  pop     rbp
0x18010565a  retn
```
