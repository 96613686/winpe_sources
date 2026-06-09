# Common::Deployment::AppHasAttributeForHeadless(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,bool *)

- ea: `0x180045bbc`
- end: `0x180045e48`
- name: `?AppHasAttributeForHeadless@Deployment@Common@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEA_N@Z`
- size: `652`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, __int64), bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180046350`

## callees

- `0x180004920`
- `0x180018248`
- `0x18001a6a0`
- `0x18001ca24`
- `0x18001e284`
- `0x180045bbc`
- `0x180045e50`
- `0x18004b170`
- `0x18004c9d0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180045de4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180045de4`
- `OLEAUT32!__imp_SysFreeString` at `0x180045c98`
- `OLEAUT32!__imp_SysFreeString` at `0x180045d17`
- `OLEAUT32!__imp_SysFreeString` at `0x180045e11`
- `OLEAUT32!__imp_SysFreeString` at `0x180045c98`
- `OLEAUT32!__imp_SysFreeString` at `0x180045d17`
- `OLEAUT32!__imp_SysFreeString` at `0x180045e11`

## string_xrefs

- `0x180045c0f`: `onecore\admin\appmodel\common\headlesspackageutilities.cpp`
- `0x180045c80`: `onecore\admin\appmodel\common\headlesspackageutilities.cpp`
- `0x180045ceb`: `onecore\admin\appmodel\common\headlesspackageutilities.cpp`
- `0x180045d53`: `onecore\admin\appmodel\common\headlesspackageutilities.cpp`
- `0x180045da6`: `onecore\admin\appmodel\common\headlesspackageutilities.cpp`
- `0x180045cf2`: `XPath %ws`

## pseudocode

```c
__int64 __fastcall Common::Deployment::AppHasAttributeForHeadless(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64),
        bool *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v7; // rsi
  __int64 (__fastcall *v8)(__int64, BSTR, _QWORD); // rdi
  OLECHAR *v9; // rbx
  int v10; // edi
  struct IXMLDOMElement *v11; // rdx
  __int64 v12; // rdx
  int AttributeValueStringFromElement; // eax
  int *bIgnoreCase; // [rsp+20h] [rbp-69h]
  int bIgnoreCasea; // [rsp+20h] [rbp-69h]
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-59h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-51h] BYREF
  Common::Xml *v18; // [rsp+40h] [rbp-49h] BYREF
  __int64 v19; // [rsp+48h] [rbp-41h] BYREF
  LPCWCH lpString1[2]; // [rsp+50h] [rbp-39h] BYREF
  int v21; // [rsp+60h] [rbp-29h]
  char v22[16]; // [rsp+70h] [rbp-19h] BYREF
  __int128 v23; // [rsp+80h] [rbp-9h]
  __int128 v24; // [rsp+90h] [rbp+7h]
  _OWORD v25[2]; // [rsp+A0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  if ( !*a1 )
    return 0;
  v19 = 0;
  v4 = Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(a1, (__int64)&v19);
  v5 = v4;
  if ( v4 >= 0 )
  {
    *(_OWORD *)v22 = *(_OWORD *)L"./*[local-name()='VisualElements']";
    v23 = *(_OWORD *)L"l-name()='VisualElements']";
    v24 = *(_OWORD *)L"='VisualElements']";
    v25[0] = *(_OWORD *)L"Elements']";
    *(_QWORD *)((char *)v25 + 14) = *(_QWORD *)L"s']";
    bstrString = 0;
    v6 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoBStrAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoBStrDeallocate(unsigned short *)>::CopyFromString(
           &bstrString,
           v22);
    v5 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecore\\admin\\appmodel\\common\\headlesspackageutilities.cpp",
        (const char *)(unsigned int)v6,
        (int)bIgnoreCase);
      SysFreeString(bstrString);
      goto LABEL_23;
    }
    v7 = v19;
    v16 = 0;
    v8 = *(__int64 (__fastcall **)(__int64, BSTR, _QWORD))(*(_QWORD *)v19 + 296LL);
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v16);
    v9 = bstrString;
    v10 = v8(v7, bstrString, &v16);
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecore\\admin\\appmodel\\common\\headlesspackageutilities.cpp",
        (const char *)(unsigned int)v10,
        (int)"XPath %ws",
        v22);
LABEL_9:
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v16);
      SysFreeString(v9);
      v5 = v10;
      goto LABEL_23;
    }
    if ( v16 )
    {
      v18 = 0;
      v10 = Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(&v16, (__int64)&v18);
      if ( v10 < 0 )
      {
        v12 = 85;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecore\\admin\\appmodel\\common\\headlesspackageutilities.cpp",
          (const char *)(unsigned int)v10,
          (int)bIgnoreCase);
LABEL_14:
        Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v18);
        goto LABEL_9;
      }
      if ( !v18 )
      {
        v10 = -2147467261;
        v12 = 86;
        goto LABEL_13;
      }
      v21 = 0;
      LODWORD(bstrString) = 0;
      *(_OWORD *)lpString1 = 0;
      AttributeValueStringFromElement = Common::Xml::GetAttributeValueStringFromElement(
                                          v18,
                                          v11,
                                          (const unsigned __int16 *)lpString1,
                                          (struct Common::StringBuffer *)&bstrString,
                                          bIgnoreCase);
      v10 = AttributeValueStringFromElement;
      if ( AttributeValueStringFromElement < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5E,
          (unsigned int)"onecore\\admin\\appmodel\\common\\headlesspackageutilities.cpp",
          (const char *)(unsigned int)AttributeValueStringFromElement,
          bIgnoreCasea);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpString1);
        goto LABEL_14;
      }
      if ( (_DWORD)bstrString )
        *a2 = CompareStringOrdinal(lpString1[1], -1, L"none", -1, 1) == 2;
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpString1);
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v18);
    }
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v16);
    SysFreeString(v9);
    v5 = 0;
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x48,
    (unsigned int)"onecore\\admin\\appmodel\\common\\headlesspackageutilities.cpp",
    (const char *)(unsigned int)v4,
    (int)bIgnoreCase);
LABEL_23:
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v19);
  return v5;
}

```

## disassembly

```asm
0x180045bbc  mov     [rsp-8+arg_10], rbx
0x180045bc1  mov     [rsp-8+arg_18], rsi
0x180045bc6  push    rbp
0x180045bc7  push    rdi
0x180045bc8  push    r14
0x180045bca  lea     rbp, [rsp-47h]
0x180045bcf  sub     rsp, 0D0h
0x180045bd6  mov     rax, cs:__security_cookie
0x180045bdd  xor     rax, rsp
0x180045be0  mov     [rbp+57h+var_20], rax
0x180045be4  cmp     qword ptr [rcx], 0
0x180045be8  mov     r14, rdx
0x180045beb  jnz     short loc_180045BF4
0x180045bed  xor     eax, eax
0x180045bef  jmp     loc_180045E24
0x180045bf4  lea     rdx, [rbp+57h+var_98]
0x180045bf8  mov     [rbp+57h+var_98], 0
0x180045c00  call    ??$As@UIXMLDOMElement@@@?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXMLDOMElement@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IXMLDOMElement>>)
0x180045c05  mov     ebx, eax
0x180045c07  test    eax, eax
0x180045c09  jns     short loc_180045C28
0x180045c0b  mov     rcx, [rbp+5Fh]; this
0x180045c0f  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\common\\headl"...
0x180045c16  mov     r9d, eax; char *
0x180045c19  mov     edx, 48h ; 'H'; void *
0x180045c1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045c23  jmp     loc_180045E19
0x180045c28  movaps  xmm0, xmmword ptr cs:aLocalNameVisua; "./*[local-name()='VisualElements']"
0x180045c2f  lea     rdx, [rbp+57h+var_70]
0x180045c33  movaps  xmm1, xmmword ptr cs:aLocalNameVisua+10h; "l-name()='VisualElements']"
0x180045c3a  lea     rcx, [rbp+57h+bstrString]
0x180045c3e  movaps  xmmword ptr [rbp+57h+var_70], xmm0
0x180045c42  movaps  xmm0, xmmword ptr cs:aLocalNameVisua+20h; "='VisualElements']"
0x180045c49  movaps  [rbp+57h+var_60], xmm1
0x180045c4d  movaps  xmm1, xmmword ptr cs:aLocalNameVisua+30h; "Elements']"
0x180045c54  movaps  [rbp+57h+var_50], xmm0
0x180045c58  movsd   xmm0, qword ptr cs:aLocalNameVisua+3Eh; "s']"
0x180045c60  movaps  xmmword ptr [rbp+57h+var_40], xmm1
0x180045c64  movsd   qword ptr [rbp+57h+var_40+0Eh], xmm0
0x180045c69  mov     [rbp+57h+bstrString], 0
0x180045c71  call    ?CopyFromString@?$AutoStringWithAllocator@G$1?AutoBStrAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoBStrDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoBStrAllocateAndCopy(ushort const *,uint),&Common::AutoBStrDeallocate(ushort *)>::CopyFromString(ushort const *)
0x180045c76  mov     ebx, eax
0x180045c78  test    eax, eax
0x180045c7a  jns     short loc_180045CA3
0x180045c7c  mov     rcx, [rbp+5Fh]; this
0x180045c80  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\common\\headl"...
0x180045c87  mov     r9d, eax; char *
0x180045c8a  mov     edx, 4Ch ; 'L'; void *
0x180045c8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045c94  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180045c98  call    cs:__imp_SysFreeString
0x180045c9e  jmp     loc_180045E19
0x180045ca3  mov     rsi, [rbp+57h+var_98]
0x180045ca7  lea     rcx, [rbp+57h+var_B0]
0x180045cab  mov     [rbp+57h+var_B0], 0
0x180045cb3  mov     rax, [rsi]
0x180045cb6  mov     rdi, [rax+128h]
0x180045cbd  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180045cc2  mov     rbx, [rbp+57h+bstrString]
0x180045cc6  lea     r8, [rbp+57h+var_B0]
0x180045cca  mov     rdx, rbx
0x180045ccd  mov     rcx, rsi
0x180045cd0  mov     rax, rdi
0x180045cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045cd8  mov     edi, eax
0x180045cda  test    eax, eax
0x180045cdc  jns     short loc_180045D24
0x180045cde  mov     rcx, [rbp+5Fh]; this
0x180045ce2  lea     rax, [rbp+57h+var_70]
0x180045ce6  mov     [rsp+0E0h+var_B8], rax; char *
0x180045ceb  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\common\\headl"...
0x180045cf2  lea     rax, aXpathWs; "XPath %ws"
0x180045cf9  mov     r9d, edi; char *
0x180045cfc  mov     edx, 51h ; 'Q'; void *
0x180045d01  mov     qword ptr [rsp+0E0h+bIgnoreCase], rax; int
0x180045d06  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180045d0b  lea     rcx, [rbp+57h+var_B0]
0x180045d0f  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180045d14  mov     rcx, rbx; bstrString
0x180045d17  call    cs:__imp_SysFreeString
0x180045d1d  mov     ebx, edi
0x180045d1f  jmp     loc_180045E19
0x180045d24  cmp     [rbp+57h+var_B0], 0
0x180045d29  lea     rcx, [rbp+57h+var_B0]
0x180045d2d  jz      loc_180045E09
0x180045d33  lea     rdx, [rbp+57h+var_A0]
0x180045d37  mov     [rbp+57h+var_A0], 0
0x180045d3f  call    ??$As@UIXMLDOMElement@@@?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXMLDOMElement@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IXMLDOMElement>>)
0x180045d44  mov     edi, eax
0x180045d46  test    eax, eax
0x180045d48  jns     short loc_180045D6D
0x180045d4a  mov     edx, 55h ; 'U'; void *
0x180045d4f  mov     rcx, [rbp+5Fh]; this
0x180045d53  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\common\\headl"...
0x180045d5a  mov     r9d, edi; char *
0x180045d5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045d62  lea     rcx, [rbp+57h+var_A0]
0x180045d66  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180045d6b  jmp     short loc_180045D0B
0x180045d6d  mov     rcx, [rbp+57h+var_A0]; this
0x180045d71  test    rcx, rcx
0x180045d74  jnz     short loc_180045D80
0x180045d76  mov     edi, 80004003h
0x180045d7b  lea     edx, [rcx+56h]
0x180045d7e  jmp     short loc_180045D4F
0x180045d80  xor     eax, eax
0x180045d82  lea     r9, [rbp+57h+bstrString]; struct Common::StringBuffer *
0x180045d86  xorps   xmm0, xmm0
0x180045d89  mov     [rbp+57h+var_80], eax
0x180045d8c  lea     r8, [rbp+57h+lpString1]; unsigned __int16 *
0x180045d90  mov     dword ptr [rbp+57h+bstrString], eax
0x180045d93  movups  xmmword ptr [rbp+57h+lpString1], xmm0
0x180045d97  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x180045d9c  mov     edi, eax
0x180045d9e  test    eax, eax
0x180045da0  jns     short loc_180045DC5
0x180045da2  mov     rcx, [rbp+5Fh]; this
0x180045da6  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\common\\headl"...
0x180045dad  mov     r9d, eax; char *
0x180045db0  mov     edx, 5Eh ; '^'; void *
0x180045db5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045dba  lea     rcx, [rbp+57h+lpString1]; this
0x180045dbe  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180045dc3  jmp     short loc_180045D62
0x180045dc5  cmp     dword ptr [rbp+57h+bstrString], 0
0x180045dc9  jz      short loc_180045DF3
0x180045dcb  mov     rcx, [rbp+57h+lpString1+8]; lpString1
0x180045dcf  lea     r8, ?AppListEntryNone@Attribute@Manifest@Packaging@Appx@@3QBGB; "none"
0x180045dd6  or      edx, 0FFFFFFFFh; cchCount1
0x180045dd9  mov     [rsp+0E0h+bIgnoreCase], 1; bIgnoreCase
0x180045de1  mov     r9d, edx; cchCount2
0x180045de4  call    cs:__imp_CompareStringOrdinal
0x180045dea  cmp     eax, 2
0x180045ded  setz    al
0x180045df0  mov     [r14], al
0x180045df3  lea     rcx, [rbp+57h+lpString1]; this
0x180045df7  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180045dfc  lea     rcx, [rbp+57h+var_A0]
0x180045e00  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180045e05  lea     rcx, [rbp+57h+var_B0]
0x180045e09  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180045e0e  mov     rcx, rbx; bstrString
0x180045e11  call    cs:__imp_SysFreeString
0x180045e17  xor     ebx, ebx
0x180045e19  lea     rcx, [rbp+57h+var_98]
0x180045e1d  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180045e22  mov     eax, ebx
0x180045e24  mov     rcx, [rbp+57h+var_20]
0x180045e28  xor     rcx, rsp; StackCookie
0x180045e2b  call    __security_check_cookie
0x180045e30  lea     r11, [rsp+0E0h+var_10]
0x180045e38  mov     rbx, [r11+30h]
0x180045e3c  mov     rsi, [r11+38h]
0x180045e40  mov     rsp, r11
0x180045e43  pop     r14
0x180045e45  pop     rdi
0x180045e46  pop     rbp
0x180045e47  retn
```
