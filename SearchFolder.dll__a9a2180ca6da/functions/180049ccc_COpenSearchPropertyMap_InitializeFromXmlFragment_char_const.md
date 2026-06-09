# COpenSearchPropertyMap::_InitializeFromXmlFragment(char const *)

- ea: `0x180049ccc`
- end: `0x180049dd2`
- name: `?_InitializeFromXmlFragment@COpenSearchPropertyMap@@AEAAJPEBD@Z`
- size: `262`
- prototype: `__int64 __fastcall(OLECHAR *this, const BYTE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180049504`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x1800129f8`
- `0x1800418bc`
- `0x180048c6c`
- `0x180049714`
- `0x180049ccc`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180049cfb`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180049cfb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180049cf0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180049cf0`
- `XmlLite!CreateXmlReader` at `0x180049d38`
- `XmlLite!CreateXmlReader` at `0x180049d38`

## pseudocode

```c
__int64 __fastcall COpenSearchPropertyMap::_InitializeFromXmlFragment(OLECHAR *this, const BYTE *a2)
{
  LPCSTR v4; // rdx
  UINT v5; // eax
  _QWORD *v6; // rax
  __int64 v7; // rdx
  void **v8; // rax
  HRESULT XmlReader; // ebx
  unsigned int v10; // r8d
  BSTR v12; // [rsp+20h] [rbp-30h] BYREF
  __int128 v13; // [rsp+28h] [rbp-28h]
  __int128 v14; // [rsp+38h] [rbp-18h]
  struct IXmlReader *v15; // [rsp+70h] [rbp+20h] BYREF
  __int64 v16; // [rsp+78h] [rbp+28h] BYREF

  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v16);
  v5 = lstrlenA(v4);
  SHCreateMemStream(a2, v5);
  v6 = (_QWORD *)ATL::CComPtrBase<IXMLDOMDocument>::operator&((__int64)&v16);
  *v6 = v7;
  if ( v7 )
  {
    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v15);
    v8 = (void **)ATL::CComPtrBase<IXMLDOMDocument>::operator&((__int64)&v15);
    XmlReader = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, v8, 0);
    if ( XmlReader >= 0 )
    {
      XmlReader = ((__int64 (__fastcall *)(struct IXmlReader *, __int64))v15->lpVtbl->SetInput)(v15, v16);
      if ( XmlReader >= 0 )
      {
        v12 = this;
        v13 = 0;
        v14 = 0;
        (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)this + 8LL))(this);
        XmlReader = LoadElementIter(v15, (const struct tagXML_ELEMENTMAP *)&off_180054490, v10, &v12);
        if ( XmlReader >= 0 )
          XmlReader = 0;
        CXmlReaderPropertyMap::~CXmlReaderPropertyMap(&v12);
      }
    }
    ATL::CComPtr<CPropertyMapTable>::~CComPtr<CPropertyMapTable>();
  }
  else
  {
    XmlReader = -2147024882;
  }
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v16);
  return (unsigned int)XmlReader;
}

```

## disassembly

```asm
0x180049ccc  mov     [rsp-8+arg_0], rbx
0x180049cd1  mov     [rsp-8+arg_8], rdi
0x180049cd6  push    rbp
0x180049cd7  mov     rbp, rsp
0x180049cda  sub     rsp, 50h
0x180049cde  mov     rdi, rcx
0x180049ce1  mov     rbx, rdx
0x180049ce4  lea     rcx, [rbp+arg_18]; void *
0x180049ce8  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180049ced  mov     rcx, rdx; lpString
0x180049cf0  call    cs:__imp_lstrlenA
0x180049cf6  mov     edx, eax; cbInit
0x180049cf8  mov     rcx, rbx; pInit
0x180049cfb  call    cs:__imp_SHCreateMemStream
0x180049d01  lea     rcx, [rbp+arg_18]
0x180049d05  mov     rdx, rax
0x180049d08  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x180049d0d  mov     [rax], rdx
0x180049d10  test    rdx, rdx
0x180049d13  jz      loc_180049DB2
0x180049d19  lea     rcx, [rbp+arg_10]; void *
0x180049d1d  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180049d22  lea     rcx, [rbp+arg_10]
0x180049d26  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x180049d2b  mov     rdx, rax; ppvObject
0x180049d2e  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180049d35  xor     r8d, r8d; pMalloc
0x180049d38  call    cs:__imp_CreateXmlReader
0x180049d3e  mov     ebx, eax
0x180049d40  test    eax, eax
0x180049d42  js      short loc_180049DA7
0x180049d44  mov     rcx, [rbp+arg_10]
0x180049d48  mov     rdx, [rbp+arg_18]
0x180049d4c  mov     rax, [rcx]
0x180049d4f  mov     rax, [rax+18h]
0x180049d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d58  mov     ebx, eax
0x180049d5a  test    eax, eax
0x180049d5c  js      short loc_180049DA7
0x180049d5e  xorps   xmm0, xmm0
0x180049d61  mov     [rbp+var_30], rdi
0x180049d65  xorps   xmm1, xmm1
0x180049d68  mov     rcx, rdi
0x180049d6b  movdqu  [rbp+var_28], xmm0
0x180049d70  movdqu  [rbp+var_18], xmm1
0x180049d75  mov     rax, [rdi]
0x180049d78  mov     rax, [rax+8]
0x180049d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d81  mov     rcx, [rbp+arg_10]; struct IXmlReader *
0x180049d85  lea     r9, [rbp+var_30]; void *
0x180049d89  lea     rdx, off_180054490; struct tagXML_ELEMENTMAP *
0x180049d90  call    ?LoadElementIter@@YAJPEAUIXmlReader@@PEBUtagXML_ELEMENTMAP@@IPEAX@Z; LoadElementIter(IXmlReader *,tagXML_ELEMENTMAP const *,uint,void *)
0x180049d95  mov     ebx, eax
0x180049d97  lea     rcx, [rbp+var_30]; this
0x180049d9b  xor     eax, eax
0x180049d9d  test    ebx, ebx
0x180049d9f  cmovns  ebx, eax
0x180049da2  call    ??1CXmlReaderPropertyMap@@QEAA@XZ; CXmlReaderPropertyMap::~CXmlReaderPropertyMap(void)
0x180049da7  lea     rcx, [rbp+arg_10]
0x180049dab  call    ??1?$CComPtr@VCPropertyMapTable@@@ATL@@QEAA@XZ; ATL::CComPtr<CPropertyMapTable>::~CComPtr<CPropertyMapTable>(void)
0x180049db0  jmp     short loc_180049DB7
0x180049db2  mov     ebx, 8007000Eh
0x180049db7  lea     rcx, [rbp+arg_18]
0x180049dbb  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180049dc0  mov     rdi, [rsp+50h+arg_8]
0x180049dc5  mov     eax, ebx
0x180049dc7  mov     rbx, [rsp+50h+arg_0]
0x180049dcc  add     rsp, 50h
0x180049dd0  pop     rbp
0x180049dd1  retn
```
