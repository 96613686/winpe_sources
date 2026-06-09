# NormalizeFeedXml

- ea: `0x1800252e4`
- end: `0x180025474`
- name: `NormalizeFeedXml`
- size: `400`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x180043938`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x1800129ec`
- `0x1800129f8`
- `0x180024f24`
- `0x180025240`
- `0x1800252e4`
- `0x18004ca14`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x18002540e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x18002540e`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800253e1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800253e1`

## pseudocode

```c
__int64 __fastcall NormalizeFeedXml(__int64 a1, HINSTANCE a2, _QWORD *a3)
{
  struct IXMLDOMDocument **v5; // rax
  struct IStream *v6; // r9
  HRESULT XmlDomDocumentFromStream; // ebx
  void **v8; // rax
  const struct _GUID *v9; // rcx
  struct IXMLDOMDocument **v10; // rax
  int v11; // r8d
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rax
  LPSTREAM *v13; // rax
  const unsigned __int16 *v15; // [rsp+20h] [rbp-40h]
  unsigned int v16; // [rsp+28h] [rbp-38h]
  __int64 v17; // [rsp+40h] [rbp-20h] BYREF
  struct IDispatch *v18; // [rsp+48h] [rbp-18h] BYREF
  struct IXMLDOMDocument *v19[2]; // [rsp+50h] [rbp-10h] BYREF
  IStream *pstm; // [rsp+90h] [rbp+30h] BYREF
  __int64 v21; // [rsp+98h] [rbp+38h] BYREF

  *a3 = 0;
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(v19);
  v5 = (struct IXMLDOMDocument **)ATL::CComPtrBase<IXMLDOMDocument>::operator&((__int64)v19);
  XmlDomDocumentFromStream = CreateXmlDomDocumentFromStream(v6, v5);
  if ( XmlDomDocumentFromStream >= 0 )
  {
    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v18);
    v8 = (void **)ATL::CComPtrBase<IXMLDOMDocument>::operator&((__int64)&v18);
    XmlDomDocumentFromStream = COpenSearchNormalizationXsltObject::s_CreateInstance(v9, v8);
    if ( XmlDomDocumentFromStream >= 0 )
    {
      LODWORD(pstm) = 0;
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v17);
      v10 = (struct IXMLDOMDocument **)ATL::CComPtrBase<IXMLDOMDocument>::operator&((__int64)&v17);
      XmlDomDocumentFromStream = NormalizeFeed(v19[0], v18, v11, a2, v15, v16, (enum FEEDS_DOWNLOAD_ERROR *)&pstm, v10);
      if ( XmlDomDocumentFromStream >= 0 )
      {
        ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v21);
        v12 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->((__int64)&v17);
        XmlDomDocumentFromStream = (**v12)(v12, &GUID_00000109_0000_0000_c000_000000000046, &v21);
        if ( XmlDomDocumentFromStream >= 0 )
        {
          ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&pstm);
          v13 = (LPSTREAM *)ATL::CComPtrBase<IXMLDOMDocument>::operator&((__int64)&pstm);
          XmlDomDocumentFromStream = CreateStreamOnHGlobal(0, 1, v13);
          if ( XmlDomDocumentFromStream >= 0 )
          {
            XmlDomDocumentFromStream = (*(__int64 (__fastcall **)(__int64, IStream *, __int64))(*(_QWORD *)v21 + 48LL))(
                                         v21,
                                         pstm,
                                         1);
            if ( XmlDomDocumentFromStream >= 0 )
            {
              XmlDomDocumentFromStream = IStream_Reset(pstm);
              if ( XmlDomDocumentFromStream >= 0 )
                XmlDomDocumentFromStream = (**(__int64 (__fastcall ***)(IStream *, GUID *, _QWORD *))pstm)(
                                             pstm,
                                             &GUID_0000000c_0000_0000_c000_000000000046,
                                             a3);
            }
          }
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&pstm);
        }
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v21);
      }
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v17);
    }
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v18);
  }
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)v19);
  return (unsigned int)XmlDomDocumentFromStream;
}

```

## disassembly

```asm
0x1800252e4  mov     [rsp-18h+arg_0], rbx
0x1800252e9  push    rbp
0x1800252ea  push    rsi
0x1800252eb  push    rdi
0x1800252ec  mov     rbp, rsp
0x1800252ef  sub     rsp, 60h
0x1800252f3  mov     r9, rcx
0x1800252f6  mov     qword ptr [r8], 0
0x1800252fd  lea     rcx, [rbp+var_10]; void *
0x180025301  mov     rdi, r8
0x180025304  mov     rsi, rdx
0x180025307  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18002530c  lea     rcx, [rbp+var_10]
0x180025310  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x180025315  mov     rdx, rax; struct IXMLDOMDocument **
0x180025318  mov     rcx, r9; struct IStream *
0x18002531b  call    ?CreateXmlDomDocumentFromStream@@YAJPEAUIStream@@PEAPEAUIXMLDOMDocument@@@Z; CreateXmlDomDocumentFromStream(IStream *,IXMLDOMDocument * *)
0x180025320  mov     ebx, eax
0x180025322  test    eax, eax
0x180025324  js      loc_180025459
0x18002532a  lea     rcx, [rbp+var_18]; void *
0x18002532e  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180025333  lea     rcx, [rbp+var_18]
0x180025337  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x18002533c  mov     rdx, rax; void **
0x18002533f  call    ?s_CreateInstance@COpenSearchNormalizationXsltObject@@SAJAEBU_GUID@@PEAPEAX@Z; COpenSearchNormalizationXsltObject::s_CreateInstance(_GUID const &,void * *)
0x180025344  mov     ebx, eax
0x180025346  test    eax, eax
0x180025348  js      loc_180025450
0x18002534e  lea     rcx, [rbp+var_20]; void *
0x180025352  mov     dword ptr [rbp+pstm], 0
0x180025359  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18002535e  lea     rcx, [rbp+var_20]
0x180025362  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x180025367  mov     rdx, [rbp+var_18]; struct IDispatch *
0x18002536b  mov     r9, rsi; HINSTANCE
0x18002536e  mov     rcx, [rbp+var_10]; struct IXMLDOMDocument *
0x180025372  mov     [rsp+60h+var_28], rax; struct IXMLDOMDocument **
0x180025377  lea     rax, [rbp+pstm]
0x18002537b  mov     [rsp+60h+var_30], rax; enum FEEDS_DOWNLOAD_ERROR *
0x180025380  call    ?NormalizeFeed@@YAJPEAUIXMLDOMDocument@@PEAUIDispatch@@HPEAUHINSTANCE__@@PEBGKPEAW4FEEDS_DOWNLOAD_ERROR@@PEAPEAU1@@Z; NormalizeFeed(IXMLDOMDocument *,IDispatch *,int,HINSTANCE__ *,ushort const *,ulong,FEEDS_DOWNLOAD_ERROR *,IXMLDOMDocument * *)
0x180025385  mov     ebx, eax
0x180025387  test    eax, eax
0x180025389  js      loc_180025447
0x18002538f  lea     rcx, [rbp+arg_18]; void *
0x180025393  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180025398  lea     rcx, [rbp+var_20]
0x18002539c  call    ??C?$CComPtrBase@UIStartMenuResultSetInternal@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIStartMenuResultSetInternal@@@1@XZ; ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->(void)
0x1800253a1  mov     r9, rax
0x1800253a4  lea     r8, [rbp+arg_18]
0x1800253a8  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x1800253af  mov     rcx, [rax]
0x1800253b2  mov     rax, [rcx]
0x1800253b5  mov     rcx, r9
0x1800253b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253bd  mov     ebx, eax
0x1800253bf  test    eax, eax
0x1800253c1  js      short loc_18002543E
0x1800253c3  lea     rcx, [rbp+pstm]; void *
0x1800253c7  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800253cc  lea     rcx, [rbp+pstm]
0x1800253d0  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x1800253d5  mov     esi, 1
0x1800253da  mov     r8, rax; ppstm
0x1800253dd  mov     edx, esi; fDeleteOnRelease
0x1800253df  xor     ecx, ecx; hGlobal
0x1800253e1  call    cs:__imp_CreateStreamOnHGlobal
0x1800253e7  mov     ebx, eax
0x1800253e9  test    eax, eax
0x1800253eb  js      short loc_180025435
0x1800253ed  mov     rcx, [rbp+arg_18]
0x1800253f1  mov     r8d, esi
0x1800253f4  mov     rdx, [rbp+pstm]
0x1800253f8  mov     rax, [rcx]
0x1800253fb  mov     rax, [rax+30h]
0x1800253ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025404  mov     ebx, eax
0x180025406  test    eax, eax
0x180025408  js      short loc_180025435
0x18002540a  mov     rcx, [rbp+pstm]; pstm
0x18002540e  call    cs:__imp_IStream_Reset
0x180025414  mov     ebx, eax
0x180025416  test    eax, eax
0x180025418  js      short loc_180025435
0x18002541a  mov     rcx, [rbp+pstm]
0x18002541e  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180025425  mov     r8, rdi
0x180025428  mov     rax, [rcx]
0x18002542b  mov     rax, [rax]
0x18002542e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025433  mov     ebx, eax
0x180025435  lea     rcx, [rbp+pstm]
0x180025439  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18002543e  lea     rcx, [rbp+arg_18]
0x180025442  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180025447  lea     rcx, [rbp+var_20]
0x18002544b  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180025450  lea     rcx, [rbp+var_18]
0x180025454  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180025459  lea     rcx, [rbp+var_10]
0x18002545d  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180025462  mov     eax, ebx
0x180025464  mov     rbx, [rsp+60h+arg_0]
0x18002546c  add     rsp, 60h
0x180025470  pop     rdi
0x180025471  pop     rsi
0x180025472  pop     rbp
0x180025473  retn
```
