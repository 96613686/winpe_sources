# mlib::XmlDOM::SelectXmlReturnFirstNodeCreateIfNotExists(IXMLDOMDocument2 *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMNode * *)

- ea: `0x1400563ec`
- end: `0x14005675b`
- name: `?SelectXmlReturnFirstNodeCreateIfNotExists@XmlDOM@mlib@@SAJPEAUIXMLDOMDocument2@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEAPEAUIXMLDOMNode@@@Z`
- size: `879`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x140055094`

## callees

- `0x140001abc`
- `0x140005f10`
- `0x14000712c`
- `0x14000a8d8`
- `0x1400143a0`
- `0x140016954`
- `0x140016d04`
- `0x14001e318`
- `0x140053e14`
- `0x140054228`
- `0x1400557f4`
- `0x140055bf0`
- `0x1400563ec`
- `0x140056bc8`
- `0x14011a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400565cf`
- `OLEAUT32!__imp_SysFreeString` at `0x140056697`
- `OLEAUT32!__imp_SysFreeString` at `0x1400565cf`
- `OLEAUT32!__imp_SysFreeString` at `0x140056697`

## string_xrefs

- `0x1400564d3`: `base\winsat\mlib\mxmldom.cpp`
- `0x140056649`: `base\winsat\mlib\mxmldom.cpp`
- `0x140056687`: `base\winsat\mlib\mxmldom.cpp`
- `0x1400566cf`: `base\winsat\mlib\mxmldom.cpp`
- `0x140056477`: `cannot get the IXMLDOMNode intrface for a node`
- `0x140056621`: `cannot create an element for a node`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall mlib::XmlDOM::SelectXmlReturnFirstNodeCreateIfNotExists(__int64 a1, __int64 a2, _QWORD *a3)
{
  int DocRootNode; // ebx
  int v7; // eax
  int v8; // eax
  __int64 v9; // rcx
  void *v10; // rsi
  _QWORD **i; // rbx
  __int64 v12; // rax
  __int64 v13; // rdx
  int v14; // r8d
  int v15; // eax
  __int64 v16; // r8
  __int64 v17; // rdx
  OLECHAR *v18; // rdi
  int v19; // eax
  int v20; // eax
  int v21; // eax
  OLECHAR *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v26; // [rsp+40h] [rbp-29h] BYREF
  __int64 v27; // [rsp+48h] [rbp-21h] BYREF
  __int64 v28; // [rsp+50h] [rbp-19h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-11h] BYREF
  void *Block[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v31; // [rsp+70h] [rbp+7h]
  BSTR bstrString; // [rsp+78h] [rbp+Fh] BYREF
  _BYTE v33[64]; // [rsp+80h] [rbp+17h] BYREF

  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v33);
  v29 = 0;
  v27 = 0;
  *(_OWORD *)Block = 0;
  v31 = 0;
  *a3 = 0;
  DocRootNode = mlib::XmlDOM::GetDocRootNode(a1, &v29, 0);
  if ( DocRootNode >= 0 )
  {
    if ( !v29 )
    {
      DocRootNode = -2147467259;
      goto LABEL_32;
    }
    v7 = (**v29)(v29, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60, &v27);
    if ( v7 < 0 )
    {
      v8 = mlib::XmlDOM::ReportCOMError_w(
             (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
             1210,
             v7,
             (_DWORD)v29,
             (__int64)&GUID_2933bf86_7b36_11d2_b20e_00c04f983e60,
             0,
             (__int64)L"cannot get the IXMLDOMNode intrface for a node");
LABEL_8:
      DocRootNode = v8;
      goto LABEL_32;
    }
    if ( !v27 )
    {
      v8 = mlib::XmlDOM::ReportCOMError_w(
             (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
             1215,
             -2147467259,
             0,
             (__int64)qword_1401C3B08,
             0,
             (__int64)L"cannot get the root node");
      goto LABEL_8;
    }
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::split_on(
      a2,
      Block);
    v10 = Block[0];
    for ( i = (_QWORD **)Block[0]; i != Block[1]; ++i )
    {
      v12 = mlib::m_traits<unsigned short>::CStrlen(&qword_14012B318, 0x10000);
      if ( (unsigned int)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::comparei_str(
                           i,
                           v13,
                           **i,
                           &qword_14012B318,
                           v12) )
      {
        v26 = 0;
        v15 = mlib::XmlDOM::SelectSingleNode(v27, (*i)[3], v14, (unsigned int)&v26, (__int64)v33);
        v16 = (unsigned int)v15;
        if ( v15 < 0 )
        {
          DocRootNode = mlib::XmlDOM::ReportCOMError_w(
                          (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                          1233,
                          v15,
                          v27,
                          (__int64)&GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
                          0,
                          (__int64)L"cannot get the root node");
          goto LABEL_27;
        }
        v17 = v26;
        if ( !v26 )
        {
          v28 = 0;
          bstrString = 0;
          ATL::CComBSTR::operator=(&bstrString, (*i)[3]);
          v18 = bstrString;
          if ( !bstrString )
          {
            DocRootNode = mlib::XmlDOM::ReportCOMError_w(
                            (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                            1245,
                            -2147024882,
                            0,
                            (__int64)qword_1401C3B08,
                            0,
                            (__int64)L"cannot allocate memory for a string");
            v22 = 0;
            goto LABEL_25;
          }
          v19 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)a1 + 376LL))(a1, bstrString, &v28);
          if ( v19 < 0 )
          {
            v21 = mlib::XmlDOM::ReportCOMError_w(
                    (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                    1252,
                    v19,
                    a1,
                    (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                    0,
                    (__int64)L"cannot create an element for a node");
LABEL_23:
            DocRootNode = v21;
            v22 = v18;
LABEL_25:
            SysFreeString(v22);
            ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v28);
LABEL_27:
            ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v26);
            if ( v10 )
            {
              std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const,std::allocator<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const>>::_Destroy(
                v23,
                v10,
                Block[1]);
              operator delete(v10);
            }
            goto LABEL_32;
          }
          v20 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v27 + 168LL))(v27, v28, &v26);
          if ( v20 < 0 )
          {
            v21 = mlib::XmlDOM::ReportCOMError_w(
                    (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                    1262,
                    v20,
                    v27,
                    (__int64)&GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
                    0,
                    (__int64)L"cannot append node as a child to another node");
            goto LABEL_23;
          }
          SysFreeString(v18);
          ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v28);
          v17 = v26;
        }
        v26 = 0;
        ATL::CComPtrBase<IXMLDOMNode>::Attach(&v27, v17, v16);
        ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v26);
      }
    }
    v24 = v27;
    v27 = 0;
    *a3 = v24;
    if ( v10 )
    {
      std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const,std::allocator<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const>>::_Destroy(
        v9,
        v10,
        Block[1]);
      operator delete(v10);
    }
    DocRootNode = 0;
  }
LABEL_32:
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v27);
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v29);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v33);
  return (unsigned int)DocRootNode;
}

```

## disassembly

```asm
0x1400563ec  push    rbp
0x1400563ee  push    rbx
0x1400563ef  push    rsi
0x1400563f0  push    rdi
0x1400563f1  push    r12
0x1400563f3  push    r13
0x1400563f5  push    r15
0x1400563f7  lea     rbp, [rsp-27h]
0x1400563fc  sub     rsp, 90h
0x140056403  mov     r12, r8
0x140056406  mov     rdi, rdx
0x140056409  mov     r15, rcx
0x14005640c  lea     rcx, [rbp+57h+var_40]
0x140056410  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x140056415  nop
0x140056416  xor     r13d, r13d
0x140056419  mov     [rbp+57h+var_68], r13
0x14005641d  mov     [rbp+57h+var_78], r13
0x140056421  xorps   xmm0, xmm0
0x140056424  movdqu  xmmword ptr [rbp+57h+Block], xmm0
0x140056429  mov     [rbp+57h+var_50], r13
0x14005642d  mov     [r12], r13
0x140056431  xor     r8d, r8d
0x140056434  lea     rdx, [rbp+57h+var_68]
0x140056438  mov     rcx, r15
0x14005643b  call    ?GetDocRootNode@XmlDOM@mlib@@SAJPEAUIXMLDOMDocument2@@AEAPEAUIXMLDOMElement@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::XmlDOM::GetDocRootNode(IXMLDOMDocument2 *,IXMLDOMElement * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140056440  mov     ebx, eax
0x140056442  test    eax, eax
0x140056444  js      loc_1400564E1
0x14005644a  mov     rcx, [rbp+57h+var_68]
0x14005644e  test    rcx, rcx
0x140056451  jnz     short loc_14005645D
0x140056453  mov     ebx, 80004005h
0x140056458  jmp     loc_1400564E1
0x14005645d  mov     rax, [rcx]
0x140056460  lea     r8, [rbp+57h+var_78]
0x140056464  lea     rdx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x14005646b  mov     rax, [rax]
0x14005646e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056473  test    eax, eax
0x140056475  jns     short loc_1400564A2
0x140056477  lea     rcx, aCannotGetTheIx_0; "cannot get the IXMLDOMNode intrface for"...
0x14005647e  mov     [rsp+0C0h+var_90], rcx
0x140056483  mov     [rsp+0C0h+var_98], r13
0x140056488  lea     rcx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x14005648f  mov     [rsp+0C0h+var_A0], rcx
0x140056494  mov     r9, [rbp+57h+var_68]
0x140056498  mov     r8d, eax
0x14005649b  mov     edx, 4BAh
0x1400564a0  jmp     short loc_1400564D3
0x1400564a2  cmp     [rbp+57h+var_78], r13
0x1400564a6  jnz     short loc_1400564E6
0x1400564a8  lea     rax, aCannotGetTheRo_0; "cannot get the root node"
0x1400564af  mov     [rsp+0C0h+var_90], rax
0x1400564b4  mov     [rsp+0C0h+var_98], r13
0x1400564b9  lea     rax, qword_1401C3B08
0x1400564c0  mov     [rsp+0C0h+var_A0], rax
0x1400564c5  xor     r9d, r9d
0x1400564c8  mov     edx, 4BFh
0x1400564cd  mov     r8d, 80004005h
0x1400564d3  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x1400564da  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x1400564df  mov     ebx, eax
0x1400564e1  jmp     loc_14005672A
0x1400564e6  lea     rdx, [rbp+57h+Block]
0x1400564ea  mov     rcx, rdi
0x1400564ed  call    ?split_on@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBAIAEAV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@G@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::split_on(std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> &,ushort)
0x1400564f2  mov     rsi, [rbp+57h+Block]
0x1400564f6  mov     rbx, rsi
0x1400564f9  cmp     rbx, [rbp+57h+Block+8]
0x1400564fd  jz      loc_140056702
0x140056503  mov     edx, 10000h
0x140056508  lea     rcx, qword_14012B318
0x14005650f  call    ?CStrlen@?$m_traits@G@mlib@@SA_KPEBG_K@Z; mlib::m_traits<ushort>::CStrlen(ushort const *,unsigned __int64)
0x140056514  mov     r8, [rbx]
0x140056517  mov     [rsp+0C0h+var_A0], rax
0x14005651c  lea     r9, qword_14012B318
0x140056523  mov     r8, [r8]
0x140056526  mov     rcx, rbx
0x140056529  call    ?comparei_str@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEBAH_K0PEBG0@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::comparei_str(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x14005652e  test    eax, eax
0x140056530  jz      loc_1400565FA
0x140056536  mov     [rbp+57h+var_80], r13
0x14005653a  mov     rdx, [rbx]
0x14005653d  lea     rax, [rbp+57h+var_40]
0x140056541  mov     [rsp+0C0h+var_A0], rax
0x140056546  lea     r9, [rbp+57h+var_80]
0x14005654a  mov     rdx, [rdx+18h]
0x14005654e  mov     rcx, [rbp+57h+var_78]
0x140056552  call    ?SelectSingleNode@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@PEBG1AEAPEAU3@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::XmlDOM::SelectSingleNode(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140056557  mov     r8d, eax
0x14005655a  test    eax, eax
0x14005655c  js      loc_1400566A9
0x140056562  mov     rdx, [rbp+57h+var_80]
0x140056566  test    rdx, rdx
0x140056569  jnz     short loc_1400565E3
0x14005656b  mov     [rbp+57h+var_70], r13
0x14005656f  mov     [rbp+57h+bstrString], r13
0x140056573  mov     rdx, [rbx]
0x140056576  mov     rdx, [rdx+18h]
0x14005657a  lea     rcx, [rbp+57h+bstrString]
0x14005657e  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x140056583  mov     rdi, [rbp+57h+bstrString]
0x140056587  test    rdi, rdi
0x14005658a  jz      loc_14005665C
0x140056590  mov     rax, [r15]
0x140056593  lea     r8, [rbp+57h+var_70]
0x140056597  mov     rdx, rdi
0x14005659a  mov     rcx, r15
0x14005659d  mov     rax, [rax+178h]
0x1400565a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400565a9  test    eax, eax
0x1400565ab  js      short loc_140056621
0x1400565ad  mov     rcx, [rbp+57h+var_78]
0x1400565b1  mov     rax, [rcx]
0x1400565b4  lea     r8, [rbp+57h+var_80]
0x1400565b8  mov     rdx, [rbp+57h+var_70]
0x1400565bc  mov     rax, [rax+0A8h]
0x1400565c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400565c8  test    eax, eax
0x1400565ca  js      short loc_140056603
0x1400565cc  mov     rcx, rdi; bstrString
0x1400565cf  call    cs:__imp_SysFreeString
0x1400565d5  nop
0x1400565d6  lea     rcx, [rbp+57h+var_70]
0x1400565da  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x1400565df  mov     rdx, [rbp+57h+var_80]
0x1400565e3  mov     [rbp+57h+var_80], r13
0x1400565e7  lea     rcx, [rbp+57h+var_78]
0x1400565eb  call    ?Attach@?$CComPtrBase@UIXMLDOMNode@@@ATL@@QEAAXPEAUIXMLDOMNode@@@Z; ATL::CComPtrBase<IXMLDOMNode>::Attach(IXMLDOMNode *)
0x1400565f0  nop
0x1400565f1  lea     rcx, [rbp+57h+var_80]
0x1400565f5  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x1400565fa  add     rbx, 8
0x1400565fe  jmp     loc_1400564F9
0x140056603  lea     rcx, aCannotAppendNo; "cannot append node as a child to anothe"...
0x14005660a  mov     [rsp+0C0h+var_90], rcx
0x14005660f  lea     rcx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x140056616  mov     r9, [rbp+57h+var_78]
0x14005661a  mov     edx, 4EEh
0x14005661f  jmp     short loc_14005663C
0x140056621  lea     rcx, aCannotCreateAn_1; "cannot create an element for a node"
0x140056628  mov     [rsp+0C0h+var_90], rcx
0x14005662d  lea     rcx, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x140056634  mov     r9, r15
0x140056637  mov     edx, 4E4h
0x14005663c  mov     [rsp+0C0h+var_98], r13
0x140056641  mov     r8d, eax
0x140056644  mov     [rsp+0C0h+var_A0], rcx
0x140056649  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140056650  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140056655  mov     ebx, eax
0x140056657  mov     rcx, rdi
0x14005665a  jmp     short loc_140056697
0x14005665c  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x140056663  mov     [rsp+0C0h+var_90], rax
0x140056668  mov     [rsp+0C0h+var_98], r13
0x14005666d  lea     rax, qword_1401C3B08
0x140056674  mov     [rsp+0C0h+var_A0], rax
0x140056679  xor     r9d, r9d
0x14005667c  mov     edx, 4DDh
0x140056681  mov     r8d, 8007000Eh
0x140056687  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x14005668e  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140056693  mov     ebx, eax
0x140056695  xor     ecx, ecx; bstrString
0x140056697  call    cs:__imp_SysFreeString
0x14005669d  nop
0x14005669e  lea     rcx, [rbp+57h+var_70]
0x1400566a2  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x1400566a7  jmp     short loc_1400566DD
0x1400566a9  lea     rax, aCannotGetTheRo_0; "cannot get the root node"
0x1400566b0  mov     [rsp+0C0h+var_90], rax
0x1400566b5  mov     [rsp+0C0h+var_98], r13
0x1400566ba  lea     rcx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x1400566c1  mov     [rsp+0C0h+var_A0], rcx
0x1400566c6  mov     r9, [rbp+57h+var_78]
0x1400566ca  mov     edx, 4D1h
0x1400566cf  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x1400566d6  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x1400566db  mov     ebx, eax
0x1400566dd  lea     rcx, [rbp+57h+var_80]
0x1400566e1  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x1400566e6  nop
0x1400566e7  test    rsi, rsi
0x1400566ea  jz      short loc_14005672A
0x1400566ec  mov     r8, [rbp+57h+Block+8]
0x1400566f0  mov     rdx, rsi
0x1400566f3  call    ?_Destroy@?$vector@$$CBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@$$CBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const,std::allocator<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x1400566f8  mov     rcx, rsi; Block
0x1400566fb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140056700  jmp     short loc_14005672A
0x140056702  mov     rax, [rbp+57h+var_78]
0x140056706  mov     [rbp+57h+var_78], r13
0x14005670a  mov     [r12], rax
0x14005670e  test    rsi, rsi
0x140056711  jz      short loc_140056727
0x140056713  mov     r8, [rbp+57h+Block+8]
0x140056717  mov     rdx, rsi
0x14005671a  call    ?_Destroy@?$vector@$$CBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@$$CBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const,std::allocator<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14005671f  mov     rcx, rsi; Block
0x140056722  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140056727  mov     ebx, r13d
0x14005672a  lea     rcx, [rbp+57h+var_78]
0x14005672e  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140056733  nop
0x140056734  lea     rcx, [rbp+57h+var_68]
0x140056738  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x14005673d  nop
0x14005673e  lea     rcx, [rbp+57h+var_40]
0x140056742  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140056747  mov     eax, ebx
0x140056749  add     rsp, 90h
0x140056750  pop     r15
0x140056752  pop     r13
0x140056754  pop     r12
0x140056756  pop     rdi
0x140056757  pop     rsi
0x140056758  pop     rbx
0x140056759  pop     rbp
0x14005675a  retn
```
