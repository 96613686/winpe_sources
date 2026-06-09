# COpenSearchRowset::_ParseXmlStream(IStream *,ulong)

- ea: `0x180046a08`
- end: `0x180046b70`
- name: `?_ParseXmlStream@COpenSearchRowset@@AEAAJPEAUIStream@@K@Z`
- size: `360`
- prototype: `__int64 __fastcall(COpenSearchRowset *__hidden this, struct IStream *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180043938`

## callees

- `0x1800054b0`
- `0x180006900`
- `0x1800129f8`
- `0x180021e64`
- `0x18002eff0`
- `0x1800418bc`
- `0x1800453f0`
- `0x180046a08`
- `0x180051010`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x180046b15`
- `SHLWAPI!__imp_StrCmpICW` at `0x180046b15`
- `XmlLite!CreateXmlReader` at `0x180046a6a`
- `XmlLite!CreateXmlReader` at `0x180046a6a`

## pseudocode

```c
__int64 __fastcall COpenSearchRowset::_ParseXmlStream(
        struct IUnknown **this,
        struct IStream *a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v4; // r14d
  void **v7; // rax
  __int64 v8; // rcx
  HRESULT XmlReader; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  HRESULT v12; // eax
  int v14; // [rsp+30h] [rbp-30h] BYREF
  struct IXmlReader *v15; // [rsp+38h] [rbp-28h] BYREF
  LPCWSTR pszStr1[2]; // [rsp+40h] [rbp-20h] BYREF

  v4 = a3;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (__int64)this,
      (__int64)OpenSearch_ParseResultsPage_Start,
      a3,
      a4,
      (__int64)pszStr1);
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v15);
  v7 = (void **)ATL::CComPtrBase<IXMLDOMDocument>::operator&((__int64)&v15);
  XmlReader = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, v7, 0);
  if ( XmlReader >= 0 )
  {
    XmlReader = ((__int64 (__fastcall *)(struct IXmlReader *, struct IStream *))v15->lpVtbl->SetInput)(v15, a2);
    if ( XmlReader >= 0 )
    {
      v14 = 0;
      v12 = ((__int64 (__fastcall *)(struct IXmlReader *, int *))v15->lpVtbl->Read)(v15, &v14);
LABEL_6:
      XmlReader = v12;
      while ( !((unsigned int (__fastcall *)(struct IXmlReader *, int *))v15->lpVtbl->Read)(v15, &v14) && !XmlReader )
      {
        XmlReader = QueryContinueOnSite(this[4]);
        if ( XmlReader >= 0 && v14 == 1 )
        {
          pszStr1[0] = 0;
          XmlReader = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, _QWORD))v15->lpVtbl->GetQualifiedName)(
                        v15,
                        pszStr1,
                        0);
          if ( XmlReader >= 0 && !StrCmpICW(pszStr1[0], L"channel") )
          {
            v12 = COpenSearchRowset::_ParseChannel((COpenSearchRowset *)this, v15, v4);
            goto LABEL_6;
          }
        }
      }
    }
  }
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v8, (__int64)OpenSearch_ParseResultsPage_Stop, v10, v11, (__int64)pszStr1);
  ATL::CComPtr<CPropertyMapTable>::~CComPtr<CPropertyMapTable>();
  return (unsigned int)XmlReader;
}

```

## disassembly

```asm
0x180046a08  push    rbp
0x180046a0a  push    rbx
0x180046a0b  push    rsi
0x180046a0c  push    rdi
0x180046a0d  push    r14
0x180046a0f  mov     rbp, rsp
0x180046a12  sub     rsp, 60h
0x180046a16  mov     rax, cs:__security_cookie
0x180046a1d  xor     rax, rsp
0x180046a20  mov     [rbp+var_10], rax
0x180046a24  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180046a2b  mov     r14d, r8d
0x180046a2e  mov     rsi, rdx
0x180046a31  mov     rdi, rcx
0x180046a34  jz      short loc_180046A4B
0x180046a36  lea     rax, [rbp+pszStr1]
0x180046a3a  lea     rdx, OpenSearch_ParseResultsPage_Start
0x180046a41  mov     [rsp+60h+var_40], rax
0x180046a46  call    McGenEventWrite_EtwEventWriteTransfer
0x180046a4b  lea     rcx, [rbp+var_28]; void *
0x180046a4f  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180046a54  lea     rcx, [rbp+var_28]
0x180046a58  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x180046a5d  mov     rdx, rax; ppvObject
0x180046a60  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180046a67  xor     r8d, r8d; pMalloc
0x180046a6a  call    cs:__imp_CreateXmlReader
0x180046a70  mov     ebx, eax
0x180046a72  test    eax, eax
0x180046a74  js      loc_180046B30
0x180046a7a  mov     rcx, [rbp+var_28]
0x180046a7e  mov     rdx, rsi
0x180046a81  mov     rax, [rcx]
0x180046a84  mov     rax, [rax+18h]
0x180046a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a8d  mov     ebx, eax
0x180046a8f  test    eax, eax
0x180046a91  js      loc_180046B30
0x180046a97  mov     rcx, [rbp+var_28]
0x180046a9b  lea     rdx, [rbp+var_30]
0x180046a9f  mov     [rbp+var_30], 0
0x180046aa6  mov     rax, [rcx]
0x180046aa9  mov     rax, [rax+30h]
0x180046aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ab2  mov     ebx, eax
0x180046ab4  mov     rcx, [rbp+var_28]
0x180046ab8  lea     rdx, [rbp+var_30]
0x180046abc  mov     rax, [rcx]
0x180046abf  mov     rax, [rax+30h]
0x180046ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ac8  test    eax, eax
0x180046aca  jnz     short loc_180046B30
0x180046acc  test    ebx, ebx
0x180046ace  jnz     short loc_180046B30
0x180046ad0  mov     rcx, [rdi+20h]; struct IUnknown *
0x180046ad4  call    ?QueryContinueOnSite@@YAJPEAUIUnknown@@@Z; QueryContinueOnSite(IUnknown *)
0x180046ad9  mov     ebx, eax
0x180046adb  test    eax, eax
0x180046add  js      short loc_180046AB4
0x180046adf  cmp     [rbp+var_30], 1
0x180046ae3  jnz     short loc_180046AB4
0x180046ae5  mov     rcx, [rbp+var_28]
0x180046ae9  lea     rdx, [rbp+pszStr1]
0x180046aed  mov     [rbp+pszStr1], 0
0x180046af5  xor     r8d, r8d
0x180046af8  mov     rax, [rcx]
0x180046afb  mov     rax, [rax+60h]
0x180046aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b04  mov     ebx, eax
0x180046b06  test    eax, eax
0x180046b08  js      short loc_180046AB4
0x180046b0a  mov     rcx, [rbp+pszStr1]; pszStr1
0x180046b0e  lea     rdx, aChannel; "channel"
0x180046b15  call    cs:__imp_StrCmpICW
0x180046b1b  test    eax, eax
0x180046b1d  jnz     short loc_180046AB4
0x180046b1f  mov     rdx, [rbp+var_28]; struct IXmlReader *
0x180046b23  mov     r8d, r14d; unsigned int
0x180046b26  mov     rcx, rdi; this
0x180046b29  call    ?_ParseChannel@COpenSearchRowset@@AEAAJPEAUIXmlReader@@K@Z; COpenSearchRowset::_ParseChannel(IXmlReader *,ulong)
0x180046b2e  jmp     short loc_180046AB2
0x180046b30  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180046b37  jz      short loc_180046B4E
0x180046b39  lea     rax, [rbp+pszStr1]
0x180046b3d  lea     rdx, OpenSearch_ParseResultsPage_Stop
0x180046b44  mov     [rsp+60h+var_40], rax
0x180046b49  call    McGenEventWrite_EtwEventWriteTransfer
0x180046b4e  lea     rcx, [rbp+var_28]
0x180046b52  call    ??1?$CComPtr@VCPropertyMapTable@@@ATL@@QEAA@XZ; ATL::CComPtr<CPropertyMapTable>::~CComPtr<CPropertyMapTable>(void)
0x180046b57  mov     eax, ebx
0x180046b59  mov     rcx, [rbp+var_10]
0x180046b5d  xor     rcx, rsp; StackCookie
0x180046b60  call    __security_check_cookie
0x180046b65  add     rsp, 60h
0x180046b69  pop     r14
0x180046b6b  pop     rdi
0x180046b6c  pop     rsi
0x180046b6d  pop     rbx
0x180046b6e  pop     rbp
0x180046b6f  retn
```
