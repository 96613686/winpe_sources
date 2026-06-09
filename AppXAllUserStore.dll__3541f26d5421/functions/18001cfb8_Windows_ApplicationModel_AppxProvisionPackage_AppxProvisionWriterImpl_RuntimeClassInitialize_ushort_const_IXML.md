# Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::RuntimeClassInitialize(ushort const *,IXMLDOMDocument2 *)

- ea: `0x18001cfb8`
- end: `0x18001d1a1`
- name: `?RuntimeClassInitialize@AppxProvisionWriterImpl@AppxProvisionPackage@ApplicationModel@Windows@@QEAAJPEBGPEAUIXMLDOMDocument2@@@Z`
- size: `489`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl *__hidden this, const unsigned __int16 *, struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e170`

## callees

- `0x180017f50`
- `0x18001c024`
- `0x18001c8dc`
- `0x18001ca24`
- `0x18001cfb8`
- `0x18001d670`
- `0x18001d810`
- `0x18001e890`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001cff0`
- `OLEAUT32!__imp_SysAllocString` at `0x18001cff0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d003`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d003`

## string_xrefs

- `0x18001cfe9`: `http://schemas.microsoft.com/appx/2013/appxprovisionpackage`
- `0x18001d17d`: `onecore\base\appmodel\appxprovisionpackage\src\appxprovisionwriter.cpp`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::RuntimeClassInitialize(
        Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl *this,
        unsigned __int16 *a2,
        struct IXMLDOMDocument2 *a3)
{
  int Element; // ebx
  __int64 v6; // rdx
  BSTR v7; // rbx
  struct IXMLDOMNode **v9; // rsi
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  bool v11; // [rsp+40h] [rbp+8h] BYREF

  Element = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromString(
              (LPVOID *)this + 2,
              a2);
  if ( Element >= 0 )
  {
    v7 = SysAllocString(L"http://schemas.microsoft.com/appx/2013/appxprovisionpackage");
    if ( *((BSTR *)this + 3) == v7 )
    {
      v7 = (BSTR)*((_QWORD *)this + 3);
    }
    else
    {
      SysFreeString(*((BSTR *)this + 3));
      *((_QWORD *)this + 3) = v7;
    }
    if ( !v7 )
      return 2147942414LL;
    Microsoft::WRL::ComPtr<IXMLDOMDocument2>::operator=((__int64 *)this + 4, (__int64)a3);
    v9 = (struct IXMLDOMNode **)((char *)this + 40);
    v11 = 0;
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease((char *)this + 40);
    Element = Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::GetElement(
                *((struct IXMLDOMNode **)this + 4),
                L"m:AppxProvisionList",
                (struct IXMLDOMElement **)this + 5,
                &v11);
    if ( Element >= 0 )
    {
      if ( !v11 )
      {
        Element = Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateProcessingInstruction(this);
        if ( Element < 0 )
        {
          v6 = 40;
          goto LABEL_25;
        }
        Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease((char *)this + 40);
        Element = Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateChildElement(
                    this,
                    *((struct IXMLDOMNode **)this + 4),
                    L"AppxProvisionList",
                    (struct IXMLDOMElement **)this + 5);
        if ( Element < 0 )
        {
          v6 = 41;
          goto LABEL_25;
        }
      }
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease((char *)this + 48);
      Element = Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::GetElement(
                  *v9,
                  L"m:EndOfLife",
                  (struct IXMLDOMElement **)this + 6,
                  &v11);
      if ( Element >= 0 )
      {
        if ( v11
          || (Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease((char *)this + 48),
              Element = Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateChildElement(
                          this,
                          *v9,
                          L"EndOfLife",
                          (struct IXMLDOMElement **)this + 6),
              Element >= 0) )
        {
          Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease((char *)this + 56);
          Element = Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::GetElement(
                      *v9,
                      L"m:Provisioned",
                      (struct IXMLDOMElement **)this + 7,
                      &v11);
          if ( Element >= 0 )
          {
            if ( v11 )
              return (unsigned int)Element;
            Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease((char *)this + 56);
            Element = Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateChildElement(
                        this,
                        *v9,
                        L"Provisioned",
                        (struct IXMLDOMElement **)this + 7);
            if ( Element >= 0 )
              return (unsigned int)Element;
            v6 = 55;
          }
          else
          {
            v6 = 52;
          }
        }
        else
        {
          v6 = 48;
        }
      }
      else
      {
        v6 = 45;
      }
    }
    else
    {
      v6 = 37;
    }
  }
  else
  {
    v6 = 28;
  }
LABEL_25:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v6,
    (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\appxprovisionwriter.cpp",
    (const char *)(unsigned int)Element);
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x18001cfb8  mov     [rsp+arg_8], rbx
0x18001cfbd  mov     [rsp+arg_10], rbp
0x18001cfc2  push    rsi
0x18001cfc3  push    rdi
0x18001cfc4  push    r14; int
0x18001cfc6  sub     rsp, 20h
0x18001cfca  mov     rdi, rcx
0x18001cfcd  mov     rsi, r8
0x18001cfd0  add     rcx, 10h
0x18001cfd4  call    ?CopyFromString@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromString(ushort const *)
0x18001cfd9  mov     ebx, eax
0x18001cfdb  test    eax, eax
0x18001cfdd  jns     short loc_18001CFE9
0x18001cfdf  mov     edx, 1Ch
0x18001cfe4  jmp     loc_18001D178
0x18001cfe9  lea     rcx, aHttpSchemasMic; "http://schemas.microsoft.com/appx/2013/"...
0x18001cff0  call    cs:__imp_SysAllocString
0x18001cff6  mov     rbx, rax
0x18001cff9  cmp     [rdi+18h], rax
0x18001cffd  jz      short loc_18001D00F
0x18001cfff  mov     rcx, [rdi+18h]; bstrString
0x18001d003  call    cs:__imp_SysFreeString
0x18001d009  mov     [rdi+18h], rbx
0x18001d00d  jmp     short loc_18001D013
0x18001d00f  mov     rbx, [rdi+18h]
0x18001d013  test    rbx, rbx
0x18001d016  jnz     short loc_18001D022
0x18001d018  mov     eax, 8007000Eh
0x18001d01d  jmp     loc_18001D18E
0x18001d022  lea     r14, [rdi+20h]
0x18001d026  mov     rdx, rsi
0x18001d029  mov     rcx, r14
0x18001d02c  call    ??4?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@QEAAAEAV012@PEAUIXMLDOMDocument2@@@Z; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::operator=(IXMLDOMDocument2 *)
0x18001d031  lea     rsi, [rdi+28h]
0x18001d035  mov     [rsp+38h+arg_0], 0
0x18001d03a  mov     rcx, rsi
0x18001d03d  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d042  mov     rcx, [r14]; struct IXMLDOMNode *
0x18001d045  lea     r9, [rsp+38h+arg_0]; bool *
0x18001d04a  mov     r8, rsi; struct IXMLDOMElement **
0x18001d04d  lea     rdx, aMAppxprovision; "m:AppxProvisionList"
0x18001d054  call    ?GetElement@CommonHelpers@AppxProvisionPackage@ApplicationModel@Windows@@SAJPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMElement@@PEA_N@Z; Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::GetElement(IXMLDOMNode *,ushort const *,IXMLDOMElement * *,bool *)
0x18001d059  mov     ebx, eax
0x18001d05b  test    eax, eax
0x18001d05d  jns     short loc_18001D069
0x18001d05f  mov     edx, 25h ; '%'
0x18001d064  jmp     loc_18001D178
0x18001d069  cmp     [rsp+38h+arg_0], 0
0x18001d06e  jnz     short loc_18001D0B5
0x18001d070  mov     rcx, rdi; this
0x18001d073  call    ?CreateProcessingInstruction@AppxProvisionWriterImpl@AppxProvisionPackage@ApplicationModel@Windows@@AEAAJXZ; Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateProcessingInstruction(void)
0x18001d078  mov     ebx, eax
0x18001d07a  test    eax, eax
0x18001d07c  jns     short loc_18001D088
0x18001d07e  mov     edx, 28h ; '('
0x18001d083  jmp     loc_18001D178
0x18001d088  mov     rcx, rsi
0x18001d08b  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d090  mov     rdx, [r14]; struct IXMLDOMNode *
0x18001d093  lea     r8, aAppxprovisionl; "AppxProvisionList"
0x18001d09a  mov     r9, rsi; struct IXMLDOMElement **
0x18001d09d  mov     rcx, rdi; this
0x18001d0a0  call    ?CreateChildElement@AppxProvisionWriterImpl@AppxProvisionPackage@ApplicationModel@Windows@@AEAAJPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMElement@@@Z; Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateChildElement(IXMLDOMNode *,ushort const *,IXMLDOMElement * *)
0x18001d0a5  mov     ebx, eax
0x18001d0a7  test    eax, eax
0x18001d0a9  jns     short loc_18001D0B5
0x18001d0ab  mov     edx, 29h ; ')'
0x18001d0b0  jmp     loc_18001D178
0x18001d0b5  lea     rbp, [rdi+30h]
0x18001d0b9  mov     rcx, rbp
0x18001d0bc  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d0c1  mov     rcx, [rsi]; struct IXMLDOMNode *
0x18001d0c4  lea     r9, [rsp+38h+arg_0]; bool *
0x18001d0c9  mov     r8, rbp; struct IXMLDOMElement **
0x18001d0cc  lea     rdx, aMEndoflife; "m:EndOfLife"
0x18001d0d3  call    ?GetElement@CommonHelpers@AppxProvisionPackage@ApplicationModel@Windows@@SAJPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMElement@@PEA_N@Z; Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::GetElement(IXMLDOMNode *,ushort const *,IXMLDOMElement * *,bool *)
0x18001d0d8  mov     ebx, eax
0x18001d0da  test    eax, eax
0x18001d0dc  jns     short loc_18001D0E8
0x18001d0de  mov     edx, 2Dh ; '-'
0x18001d0e3  jmp     loc_18001D178
0x18001d0e8  cmp     [rsp+38h+arg_0], 0
0x18001d0ed  jnz     short loc_18001D119
0x18001d0ef  mov     rcx, rbp
0x18001d0f2  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d0f7  mov     rdx, [rsi]; struct IXMLDOMNode *
0x18001d0fa  lea     r8, aEndoflife; "EndOfLife"
0x18001d101  mov     r9, rbp; struct IXMLDOMElement **
0x18001d104  mov     rcx, rdi; this
0x18001d107  call    ?CreateChildElement@AppxProvisionWriterImpl@AppxProvisionPackage@ApplicationModel@Windows@@AEAAJPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMElement@@@Z; Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateChildElement(IXMLDOMNode *,ushort const *,IXMLDOMElement * *)
0x18001d10c  mov     ebx, eax
0x18001d10e  test    eax, eax
0x18001d110  jns     short loc_18001D119
0x18001d112  mov     edx, 30h ; '0'
0x18001d117  jmp     short loc_18001D178
0x18001d119  lea     rbp, [rdi+38h]
0x18001d11d  mov     rcx, rbp
0x18001d120  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d125  mov     rcx, [rsi]; struct IXMLDOMNode *
0x18001d128  lea     r9, [rsp+38h+arg_0]; bool *
0x18001d12d  mov     r8, rbp; struct IXMLDOMElement **
0x18001d130  lea     rdx, aMProvisioned; "m:Provisioned"
0x18001d137  call    ?GetElement@CommonHelpers@AppxProvisionPackage@ApplicationModel@Windows@@SAJPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMElement@@PEA_N@Z; Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::GetElement(IXMLDOMNode *,ushort const *,IXMLDOMElement * *,bool *)
0x18001d13c  mov     ebx, eax
0x18001d13e  test    eax, eax
0x18001d140  jns     short loc_18001D149
0x18001d142  mov     edx, 34h ; '4'
0x18001d147  jmp     short loc_18001D178
0x18001d149  cmp     [rsp+38h+arg_0], 0
0x18001d14e  jnz     short loc_18001D18C
0x18001d150  mov     rcx, rbp
0x18001d153  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d158  mov     rdx, [rsi]; struct IXMLDOMNode *
0x18001d15b  lea     r8, aProvisioned; "Provisioned"
0x18001d162  mov     r9, rbp; struct IXMLDOMElement **
0x18001d165  mov     rcx, rdi; this
0x18001d168  call    ?CreateChildElement@AppxProvisionWriterImpl@AppxProvisionPackage@ApplicationModel@Windows@@AEAAJPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMElement@@@Z; Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateChildElement(IXMLDOMNode *,ushort const *,IXMLDOMElement * *)
0x18001d16d  mov     ebx, eax
0x18001d16f  test    eax, eax
0x18001d171  jns     short loc_18001D18C
0x18001d173  mov     edx, 37h ; '7'; void *
0x18001d178  mov     rcx, [rsp+38h]; this
0x18001d17d  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001d184  mov     r9d, ebx; char *
0x18001d187  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d18c  mov     eax, ebx
0x18001d18e  mov     rbx, [rsp+38h+arg_8]
0x18001d193  mov     rbp, [rsp+38h+arg_10]
0x18001d198  add     rsp, 20h
0x18001d19c  pop     r14
0x18001d19e  pop     rdi
0x18001d19f  pop     rsi
0x18001d1a0  retn
```
