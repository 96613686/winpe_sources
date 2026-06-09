# DataStoreReader::LoadRecentResultsFromFile(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,WinSATData &,IXMLDOMDocument2 * *)

- ea: `0x180004c60`
- end: `0x180005074`
- name: `?LoadRecentResultsFromFile@DataStoreReader@@KAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAUWinSATData@@PEAPEAUIXMLDOMDocument2@@@Z`
- size: `1044`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180003970`

## callees

- `0x180004c60`
- `0x180005080`
- `0x180006494`
- `0x180006584`
- `0x18000e490`
- `0x180012aa8`
- `0x180012b18`
- `0x180013e69`
- `0x180015f4c`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180004def`
- `OLEAUT32!__imp_SysAllocString` at `0x180004def`
- `OLEAUT32!__imp_VariantInit` at `0x180004dbd`
- `OLEAUT32!__imp_VariantInit` at `0x180004dbd`
- `OLEAUT32!__imp_VariantClear` at `0x180004dd6`
- `OLEAUT32!__imp_VariantClear` at `0x180004e9c`
- `OLEAUT32!__imp_VariantClear` at `0x180004f1c`
- `OLEAUT32!__imp_VariantClear` at `0x180004f95`
- `OLEAUT32!__imp_VariantClear` at `0x180004fed`
- `OLEAUT32!__imp_VariantClear` at `0x180004dd6`
- `OLEAUT32!__imp_VariantClear` at `0x180004e9c`
- `OLEAUT32!__imp_VariantClear` at `0x180004f1c`
- `OLEAUT32!__imp_VariantClear` at `0x180004f95`
- `OLEAUT32!__imp_VariantClear` at `0x180004fed`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004d6b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004d6b`

## string_xrefs

- `0x180004e88`: `base\winsat\mlib\mxmldom.cpp`
- `0x180004f08`: `base\winsat\mlib\mxmldom.cpp`
- `0x180004f81`: `base\winsat\mlib\mxmldom.cpp`
- `0x180004e67`: `cannot create an IXMLDOMDocument2 document`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall DataStoreReader::LoadRecentResultsFromFile(__int64 a1, void *a2, struct IXMLDOMDocument2 **a3)
{
  struct IXMLDOMDocument2 *v6; // rbx
  int v7; // r15d
  const OLECHAR *v8; // r12
  __int64 v9; // rax
  int v10; // eax
  int v11; // eax
  int ResultsFromXmlDoc; // esi
  struct IXMLDOMDocument2 *v14; // rcx
  struct IXMLDOMDocument2 *v15; // [rsp+40h] [rbp-98h] BYREF
  __int64 v16; // [rsp+48h] [rbp-90h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-88h] BYREF
  VARIANTARG v18; // [rsp+70h] [rbp-68h] BYREF
  __int16 v19; // [rsp+E0h] [rbp+8h] BYREF
  void *v20; // [rsp+E8h] [rbp+10h]
  struct IXMLDOMDocument2 **v21; // [rsp+F0h] [rbp+18h]
  LPVOID ppv; // [rsp+F8h] [rbp+20h] BYREF

  v21 = a3;
  v20 = a2;
  v16 = -2;
  v15 = 0;
  if ( !a1 || !a2 )
    return 2147942487LL;
  memset_0(a2, 0, 0x1A0u);
  ppv = 0;
  v19 = 0;
  if ( dword_1800506A4 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800506A4);
    if ( dword_1800506A4 == -1 )
    {
      byte_1800506A3 = 0;
      Init_thread_footer(&dword_1800506A4);
    }
  }
  v6 = 0;
  v15 = 0;
  if ( !mlib::XmlDOM::fInitialized )
  {
    mlib::XmlDOM::clsIDDocument = 0;
    mlib::XmlDOM::clsIDSchema = 0;
    if ( !mlib::XmlDOM::CheckMSXMLVersion() )
    {
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      v7 = -2147467259;
      goto LABEL_26;
    }
    mlib::XmlDOM::fInitialized = 1;
  }
  if ( CoCreateInstance(&mlib::XmlDOM::clsIDDocument, 0, 1u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &ppv) < 0 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    v7 = -2147467259;
LABEL_26:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
    return (unsigned int)v7;
  }
  VariantInit(&pvarg);
  v8 = *(const OLECHAR **)(*(_QWORD *)a1 + 24LL);
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(v8);
  if ( !pvarg.llVal && v8 )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  v9 = *(_QWORD *)ppv;
  v18 = pvarg;
  v10 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(v9 + 464))(ppv, &v18, &v19);
  if ( v10 < 0 )
  {
    v7 = mlib::XmlDOM::ReportCOMError_w(
           (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
           230,
           v10,
           0,
           (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
           0,
           (__int64)L"cannot create an IXMLDOMDocument2 document");
    VariantClear(&pvarg);
    if ( !ppv )
      goto LABEL_25;
LABEL_24:
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
LABEL_25:
    if ( v7 < 0 )
      goto LABEL_26;
    goto LABEL_28;
  }
  if ( !v19 )
  {
    v7 = mlib::XmlDOM::ReportCOMError_w(
           (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
           235,
           -2147467259,
           (_DWORD)ppv,
           (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
           0,
           (__int64)L"cannot load document from file '%s'",
           *(_QWORD *)(*(_QWORD *)a1 + 24LL),
           v15,
           v16);
    VariantClear(&pvarg);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    goto LABEL_25;
  }
  v11 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 576LL))(ppv, 0xFFFFFFFFLL);
  if ( v11 < 0 )
  {
    v7 = mlib::XmlDOM::ReportCOMError_w(
           (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
           246,
           v11,
           (_DWORD)ppv,
           (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
           0,
           (__int64)L"cannot set the 'preserve white space' flag");
    VariantClear(&pvarg);
    if ( !ppv )
      goto LABEL_25;
    goto LABEL_24;
  }
  v6 = (struct IXMLDOMDocument2 *)ppv;
  ppv = 0;
  v15 = v6;
  VariantClear(&pvarg);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
LABEL_28:
  ResultsFromXmlDoc = WinSATData::LoadResultsFromXmlDoc((WinSATData *)a2, v6);
  if ( ResultsFromXmlDoc >= 0 && a3 )
  {
    v14 = v6;
    v6 = 0;
    *a3 = v14;
  }
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v6->lpVtbl->Release)(v6);
  return (unsigned int)ResultsFromXmlDoc;
}

```

## disassembly

```asm
0x180004c60  mov     [rsp+arg_10], r8
0x180004c65  mov     [rsp+arg_8], rdx
0x180004c6a  push    rbx
0x180004c6b  push    rsi
0x180004c6c  push    rdi
0x180004c6d  push    r12
0x180004c6f  push    r13
0x180004c71  push    r14
0x180004c73  push    r15
0x180004c75  sub     rsp, 0A0h
0x180004c7c  mov     [rsp+0D8h+var_90], 0FFFFFFFFFFFFFFFEh
0x180004c85  mov     r14, r8
0x180004c88  mov     rsi, rdx
0x180004c8b  mov     r15, rcx
0x180004c8e  xor     edi, edi
0x180004c90  mov     [rsp+0D8h+var_98], rdi
0x180004c95  test    rcx, rcx
0x180004c98  jz      loc_18000505B
0x180004c9e  test    rdx, rdx
0x180004ca1  jz      loc_18000505B
0x180004ca7  xor     edx, edx; Val
0x180004ca9  mov     r8d, 1A0h; Size
0x180004caf  mov     rcx, rsi; void *
0x180004cb2  call    memset_0
0x180004cb7  nop
0x180004cb8  mov     [rsp+0D8h+arg_18], rdi
0x180004cc0  mov     [rsp+0D8h+arg_0], di
0x180004cc8  mov     ecx, cs:_tls_index
0x180004cce  mov     rax, gs:58h
0x180004cd7  mov     edx, 4
0x180004cdc  mov     rax, [rax+rcx*8]
0x180004ce0  mov     eax, [rdx+rax]
0x180004ce3  cmp     cs:dword_1800506A4, eax
0x180004ce9  jle     short loc_180004D13
0x180004ceb  lea     rcx, dword_1800506A4
0x180004cf2  call    _Init_thread_header
0x180004cf7  cmp     cs:dword_1800506A4, 0FFFFFFFFh
0x180004cfe  jnz     short loc_180004D13
0x180004d00  mov     cs:byte_1800506A3, dil
0x180004d07  lea     rcx, dword_1800506A4
0x180004d0e  call    _Init_thread_footer
0x180004d13  mov     rbx, rdi
0x180004d16  mov     [rsp+0D8h+var_98], rbx
0x180004d1b  cmp     cs:?fInitialized@XmlDOM@mlib@@0_NA, bl; bool mlib::XmlDOM::fInitialized
0x180004d21  jnz     short loc_180004D47
0x180004d23  xorps   xmm0, xmm0
0x180004d26  movups  xmmword ptr cs:?clsIDDocument@XmlDOM@mlib@@0U_GUID@@A.Data1, xmm0; _GUID mlib::XmlDOM::clsIDDocument ...
0x180004d2d  xorps   xmm1, xmm1
0x180004d30  movups  xmmword ptr cs:?clsIDSchema@XmlDOM@mlib@@0U_GUID@@A.Data1, xmm1; _GUID mlib::XmlDOM::clsIDSchema ...
0x180004d37  call    ?CheckMSXMLVersion@XmlDOM@mlib@@SA_NXZ; mlib::XmlDOM::CheckMSXMLVersion(void)
0x180004d3c  test    al, al
0x180004d3e  jz      short loc_180004D93
0x180004d40  mov     cs:?fInitialized@XmlDOM@mlib@@0_NA, 1; bool mlib::XmlDOM::fInitialized
0x180004d47  lea     rax, [rsp+0D8h+arg_18]
0x180004d4f  mov     [rsp+0D8h+ppv], rax; ppv
0x180004d54  lea     r13, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x180004d5b  mov     r9, r13; riid
0x180004d5e  xor     edx, edx; pUnkOuter
0x180004d60  lea     r8d, [rdx+1]; dwClsContext
0x180004d64  lea     rcx, ?clsIDDocument@XmlDOM@mlib@@0U_GUID@@A; rclsid
0x180004d6b  call    cs:__imp_CoCreateInstance
0x180004d72  nop     dword ptr [rax+rax+00h]
0x180004d77  test    eax, eax
0x180004d79  jns     short loc_180004DB8
0x180004d7b  lea     rcx, [rsp+0D8h+arg_18]
0x180004d83  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004d88  mov     r15d, 80004005h
0x180004d8e  jmp     loc_180004FC1
0x180004d93  mov     rcx, [rsp+0D8h+arg_18]
0x180004d9b  test    rcx, rcx
0x180004d9e  jz      short loc_180004DAD
0x180004da0  mov     rax, [rcx]
0x180004da3  mov     rax, [rax+10h]
0x180004da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dac  nop
0x180004dad  mov     r15d, 80004005h
0x180004db3  jmp     loc_180004FC1
0x180004db8  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x180004dbd  call    cs:__imp_VariantInit
0x180004dc4  nop     dword ptr [rax+rax+00h]
0x180004dc9  nop
0x180004dca  mov     rax, [r15]
0x180004dcd  mov     r12, [rax+18h]
0x180004dd1  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x180004dd6  call    cs:__imp_VariantClear
0x180004ddd  nop     dword ptr [rax+rax+00h]
0x180004de2  mov     eax, 8
0x180004de7  mov     word ptr [rsp+0D8h+pvarg], ax
0x180004dec  mov     rcx, r12; psz
0x180004def  call    cs:__imp_SysAllocString
0x180004df6  nop     dword ptr [rax+rax+00h]
0x180004dfb  mov     qword ptr [rsp+0D8h+pvarg+8], rax
0x180004e00  test    rax, rax
0x180004e03  jnz     short loc_180004E26
0x180004e05  test    r12, r12
0x180004e08  jz      short loc_180004E26
0x180004e0a  mov     eax, 0Ah
0x180004e0f  mov     word ptr [rsp+0D8h+pvarg], ax
0x180004e14  mov     dword ptr [rsp+0D8h+pvarg+8], 8007000Eh
0x180004e1c  mov     ecx, 8007000Eh; int
0x180004e21  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004e26  mov     rcx, [rsp+0D8h+arg_18]
0x180004e2e  mov     rax, [rcx]
0x180004e31  movups  xmm0, xmmword ptr [rsp+0D8h+pvarg]
0x180004e36  movaps  [rsp+0D8h+var_68], xmm0
0x180004e3b  movsd   xmm1, qword ptr [rsp+0D8h+pvarg+10h]
0x180004e41  movsd   [rsp+0D8h+var_58], xmm1
0x180004e4a  lea     r8, [rsp+0D8h+arg_0]
0x180004e52  lea     rdx, [rsp+0D8h+var_68]
0x180004e57  mov     rax, [rax+1D0h]
0x180004e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e63  test    eax, eax
0x180004e65  jns     short loc_180004EC8
0x180004e67  lea     rcx, aCannotCreateAn; "cannot create an IXMLDOMDocument2 docum"...
0x180004e6e  mov     [rsp+0D8h+var_A8], rcx
0x180004e73  mov     [rsp+0D8h+var_B0], rdi
0x180004e78  mov     [rsp+0D8h+ppv], r13
0x180004e7d  xor     r9d, r9d
0x180004e80  mov     r8d, eax
0x180004e83  mov     edx, 0E6h
0x180004e88  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180004e8f  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180004e94  mov     r15d, eax
0x180004e97  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x180004e9c  call    cs:__imp_VariantClear
0x180004ea3  nop     dword ptr [rax+rax+00h]
0x180004ea8  nop
0x180004ea9  mov     rcx, [rsp+0D8h+arg_18]
0x180004eb1  test    rcx, rcx
0x180004eb4  jz      short loc_180004EC3
0x180004eb6  mov     rax, [rcx]
0x180004eb9  mov     rax, [rax+10h]
0x180004ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ec2  nop
0x180004ec3  jmp     loc_180004FBC
0x180004ec8  cmp     [rsp+0D8h+arg_0], 0
0x180004ed1  jnz     short loc_180004F3B
0x180004ed3  mov     rax, [r15]
0x180004ed6  mov     rcx, [rax+18h]
0x180004eda  mov     [rsp+0D8h+var_A0], rcx
0x180004edf  lea     rax, aCannotLoadDocu; "cannot load document from file '%s'"
0x180004ee6  mov     [rsp+0D8h+var_A8], rax
0x180004eeb  mov     [rsp+0D8h+var_B0], rdi
0x180004ef0  mov     [rsp+0D8h+ppv], r13
0x180004ef5  mov     r9, [rsp+0D8h+arg_18]
0x180004efd  mov     edx, 0EBh
0x180004f02  mov     r8d, 80004005h
0x180004f08  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180004f0f  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180004f14  mov     r15d, eax
0x180004f17  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x180004f1c  call    cs:__imp_VariantClear
0x180004f23  nop     dword ptr [rax+rax+00h]
0x180004f28  nop
0x180004f29  lea     rcx, [rsp+0D8h+arg_18]
0x180004f31  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004f36  jmp     loc_180004FBC
0x180004f3b  mov     rcx, [rsp+0D8h+arg_18]
0x180004f43  mov     rax, [rcx]
0x180004f46  mov     edx, 0FFFFFFFFh
0x180004f4b  mov     rax, [rax+240h]
0x180004f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f57  test    eax, eax
0x180004f59  jns     short loc_180004FD3
0x180004f5b  lea     rcx, aCannotSetThePr; "cannot set the 'preserve white space' f"...
0x180004f62  mov     [rsp+0D8h+var_A8], rcx
0x180004f67  mov     [rsp+0D8h+var_B0], rdi
0x180004f6c  mov     [rsp+0D8h+ppv], r13
0x180004f71  mov     r9, [rsp+0D8h+arg_18]
0x180004f79  mov     r8d, eax
0x180004f7c  mov     edx, 0F6h
0x180004f81  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180004f88  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180004f8d  mov     r15d, eax
0x180004f90  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x180004f95  call    cs:__imp_VariantClear
0x180004f9c  nop     dword ptr [rax+rax+00h]
0x180004fa1  nop
0x180004fa2  mov     rcx, [rsp+0D8h+arg_18]
0x180004faa  test    rcx, rcx
0x180004fad  jz      short loc_180004FBC
0x180004faf  mov     rax, [rcx]
0x180004fb2  mov     rax, [rax+10h]
0x180004fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fbb  nop
0x180004fbc  test    r15d, r15d
0x180004fbf  jns     short loc_180005008
0x180004fc1  lea     rcx, [rsp+0D8h+var_98]
0x180004fc6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004fcb  mov     eax, r15d
0x180004fce  jmp     loc_180005060
0x180004fd3  mov     rbx, [rsp+0D8h+arg_18]
0x180004fdb  mov     [rsp+0D8h+arg_18], rdi
0x180004fe3  mov     [rsp+0D8h+var_98], rbx
0x180004fe8  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x180004fed  call    cs:__imp_VariantClear
0x180004ff4  nop     dword ptr [rax+rax+00h]
0x180004ff9  nop
0x180004ffa  lea     rcx, [rsp+0D8h+arg_18]
0x180005002  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005007  nop
0x180005008  jmp     short loc_180005023
0x18000500a  jmp     short $+2
0x18000500c  mov     rbx, [rsp+0D8h+var_98]
0x180005011  mov     rsi, [rsp+0D8h+arg_8]
0x180005019  mov     r14, [rsp+0D8h+arg_10]
0x180005021  xor     edi, edi
0x180005023  mov     rdx, rbx; struct IXMLDOMDocument2 *
0x180005026  mov     rcx, rsi; this
0x180005029  call    ?LoadResultsFromXmlDoc@WinSATData@@QEAAJPEAUIXMLDOMDocument2@@@Z; WinSATData::LoadResultsFromXmlDoc(IXMLDOMDocument2 *)
0x18000502e  mov     esi, eax
0x180005030  test    eax, eax
0x180005032  js      short loc_180005042
0x180005034  test    r14, r14
0x180005037  jz      short loc_180005042
0x180005039  mov     rcx, rbx
0x18000503c  mov     rbx, rdi
0x18000503f  mov     [r14], rcx
0x180005042  test    rbx, rbx
0x180005045  jz      short loc_180005057
0x180005047  mov     rax, [rbx]
0x18000504a  mov     rcx, rbx
0x18000504d  mov     rax, [rax+10h]
0x180005051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005056  nop
0x180005057  mov     eax, esi
0x180005059  jmp     short loc_180005060
0x18000505b  mov     eax, 80070057h
0x180005060  add     rsp, 0A0h
0x180005067  pop     r15
0x180005069  pop     r14
0x18000506b  pop     r13
0x18000506d  pop     r12
0x18000506f  pop     rdi
0x180005070  pop     rsi
0x180005071  pop     rbx
0x180005072  retn
```
