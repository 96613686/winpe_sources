# mlib::XmlDOM::SelectXml(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMNodeList * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x140056088`
- end: `0x1400563e3`
- name: `?SelectXml@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@1PEAPEAUIXMLDOMNodeList@@PEAV42@@Z`
- size: `859`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14004da24`
- `0x14004db60`
- `0x140053ef0`
- `0x140054550`
- `0x14005497c`
- `0x140054d0c`

## callees

- `0x14000712c`
- `0x140016780`
- `0x140053e14`
- `0x1400557f4`
- `0x140056088`
- `0x14011a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14005612d`
- `OLEAUT32!__imp_SysFreeString` at `0x140056136`
- `OLEAUT32!__imp_SysFreeString` at `0x1400561b4`
- `OLEAUT32!__imp_SysFreeString` at `0x1400561bd`
- `OLEAUT32!__imp_SysFreeString` at `0x1400561c7`
- `OLEAUT32!__imp_SysFreeString` at `0x14005622b`
- `OLEAUT32!__imp_SysFreeString` at `0x140056394`
- `OLEAUT32!__imp_SysFreeString` at `0x14005639e`
- `OLEAUT32!__imp_SysFreeString` at `0x1400563a8`
- `OLEAUT32!__imp_SysFreeString` at `0x14005612d`
- `OLEAUT32!__imp_SysFreeString` at `0x140056136`
- `OLEAUT32!__imp_SysFreeString` at `0x1400561b4`
- `OLEAUT32!__imp_SysFreeString` at `0x1400561bd`
- `OLEAUT32!__imp_SysFreeString` at `0x1400561c7`
- `OLEAUT32!__imp_SysFreeString` at `0x14005622b`
- `OLEAUT32!__imp_SysFreeString` at `0x140056394`
- `OLEAUT32!__imp_SysFreeString` at `0x14005639e`
- `OLEAUT32!__imp_SysFreeString` at `0x1400563a8`

## string_xrefs

- `0x14005611c`: `base\winsat\mlib\mxmldom.cpp`
- `0x1400561a3`: `base\winsat\mlib\mxmldom.cpp`
- `0x14005621a`: `base\winsat\mlib\mxmldom.cpp`
- `0x14005627d`: `base\winsat\mlib\mxmldom.cpp`
- `0x14005634b`: `base\winsat\mlib\mxmldom.cpp`
- `0x140056380`: `cannot select nodes in an XML document`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall mlib::XmlDOM::SelectXml(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4, __int64 a5)
{
  OLECHAR *v8; // rbx
  OLECHAR *v9; // rdi
  OLECHAR *v10; // rsi
  unsigned int v11; // r14d
  OLECHAR *v12; // rcx
  OLECHAR *v13; // rcx
  OLECHAR *v14; // rcx
  int v15; // eax
  const wchar_t *v16; // rcx
  int v17; // edx
  unsigned int v18; // eax
  int v19; // eax
  int v20; // eax
  BSTR bstrString; // [rsp+40h] [rbp-40h] BYREF
  OLECHAR *v23; // [rsp+48h] [rbp-38h] BYREF
  OLECHAR *v24; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v25[4]; // [rsp+60h] [rbp-20h] BYREF
  __int64 v26; // [rsp+B8h] [rbp+38h] BYREF
  __int64 (__fastcall ***v27)(_QWORD, GUID *, __int64 *); // [rsp+C8h] [rbp+48h] BYREF

  v27 = 0;
  v26 = 0;
  bstrString = 0;
  v8 = 0;
  v23 = 0;
  v9 = 0;
  v24 = 0;
  *a4 = 0;
  ATL::CComBSTR::operator=(&bstrString, *(_QWORD *)(*(_QWORD *)a2 + 24LL));
  v10 = bstrString;
  if ( bstrString )
  {
    if ( (unsigned int)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::compare(
                         a3,
                         &qword_14012B318) )
    {
      ATL::CComBSTR::operator=(&v23, L"SelectionNamespaces");
      v8 = v23;
      if ( !v23 )
      {
        v11 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                832,
                -2147024882,
                0,
                (__int64)qword_1401C3B08,
                a5,
                (__int64)L"cannot allocate memory for a string");
        SysFreeString(0);
        v13 = 0;
LABEL_6:
        SysFreeString(v13);
        v12 = v10;
        goto LABEL_7;
      }
      ATL::CComBSTR::operator=(&v24, *(_QWORD *)(*(_QWORD *)a3 + 24LL));
      v9 = v24;
      if ( !v24 )
      {
        v11 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                838,
                -2147024882,
                0,
                (__int64)qword_1401C3B08,
                a5,
                (__int64)L"cannot allocate memory for a string");
        v14 = 0;
LABEL_10:
        SysFreeString(v14);
        v13 = v8;
        goto LABEL_6;
      }
      v15 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a1 + 184LL))(
              a1,
              &v27);
      if ( v15 < 0 )
      {
        v16 = L"cannot get owner document";
        v17 = 844;
LABEL_13:
        v18 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                v17,
                v15,
                a1,
                (__int64)&GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
                a5,
                (__int64)v16);
LABEL_14:
        v11 = v18;
        v14 = v9;
        goto LABEL_10;
      }
      if ( v27 )
      {
        v19 = (**v27)(v27, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &v26);
        if ( v19 < 0 )
        {
          v18 = mlib::XmlDOM::ReportCOMError_w(
                  (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                  853,
                  v19,
                  (_DWORD)v27,
                  (__int64)&GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
                  a5,
                  (__int64)L"cannot get a document node");
          goto LABEL_14;
        }
        v25[0] = 8;
        v25[1] = v9;
        v25[2] = 0;
        v20 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD *))(*(_QWORD *)v26 + 640LL))(v26, v8, v25);
        if ( v20 < 0 )
        {
          v18 = mlib::XmlDOM::ReportCOMError_w(
                  (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                  862,
                  v20,
                  v26,
                  (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                  a5,
                  (__int64)L"cannot set the %s document propert",
                  v8);
          goto LABEL_14;
        }
      }
    }
    v15 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD *))(*(_QWORD *)a1 + 288LL))(a1, v10, a4);
    if ( v15 >= 0 )
    {
      SysFreeString(v9);
      SysFreeString(v8);
      SysFreeString(v10);
      v11 = 0;
      goto LABEL_23;
    }
    *a4 = 0;
    v16 = L"cannot select nodes in an XML document";
    v17 = 871;
    goto LABEL_13;
  }
  v11 = mlib::XmlDOM::ReportCOMError_w(
          (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
          824,
          -2147024882,
          0,
          (__int64)qword_1401C3B08,
          a5,
          (__int64)L"cannot allocate memory for a string");
  SysFreeString(0);
  SysFreeString(0);
  v12 = 0;
LABEL_7:
  SysFreeString(v12);
LABEL_23:
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v26);
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v27);
  return v11;
}

```

## disassembly

```asm
0x140056088  mov     [rsp-28h+arg_0], rbx
0x14005608d  mov     [rsp-28h+arg_10], rsi
0x140056092  push    rbp
0x140056093  push    rdi
0x140056094  push    r12
0x140056096  push    r14
0x140056098  push    r15
0x14005609a  mov     rbp, rsp
0x14005609d  sub     rsp, 80h
0x1400560a4  mov     r12, r9
0x1400560a7  mov     r15, r8
0x1400560aa  mov     r14, rcx
0x1400560ad  mov     [rbp+arg_18], 0
0x1400560b5  mov     [rbp+arg_8], 0
0x1400560bd  mov     [rbp+bstrString], 0
0x1400560c5  xor     ebx, ebx
0x1400560c7  mov     [rbp+var_38], rbx
0x1400560cb  xor     edi, edi
0x1400560cd  mov     [rbp+var_30], rdi
0x1400560d1  mov     [r9], rdi
0x1400560d4  mov     rdx, [rdx]
0x1400560d7  mov     rdx, [rdx+18h]
0x1400560db  lea     rcx, [rbp+bstrString]
0x1400560df  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1400560e4  mov     rsi, [rbp+bstrString]
0x1400560e8  test    rsi, rsi
0x1400560eb  jnz     short loc_140056144
0x1400560ed  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x1400560f4  mov     [rsp+80h+var_50], rax
0x1400560f9  mov     rax, [rbp+arg_20]
0x1400560fd  mov     [rsp+80h+var_58], rax
0x140056102  lea     rax, qword_1401C3B08
0x140056109  mov     [rsp+80h+var_60], rax
0x14005610e  xor     r9d, r9d
0x140056111  mov     edx, 338h
0x140056116  mov     r8d, 8007000Eh
0x14005611c  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140056123  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140056128  mov     r14d, eax
0x14005612b  xor     ecx, ecx; bstrString
0x14005612d  call    cs:__imp_SysFreeString
0x140056133  nop
0x140056134  xor     ecx, ecx; bstrString
0x140056136  call    cs:__imp_SysFreeString
0x14005613c  nop
0x14005613d  xor     ecx, ecx
0x14005613f  jmp     loc_1400561C7
0x140056144  lea     rdx, qword_14012B318
0x14005614b  mov     rcx, r15
0x14005614e  call    ?compare@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBAHPEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::compare(ushort const *)
0x140056153  test    eax, eax
0x140056155  jz      loc_14005635C
0x14005615b  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x140056162  lea     rcx, [rbp+var_38]
0x140056166  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x14005616b  mov     rbx, [rbp+var_38]
0x14005616f  test    rbx, rbx
0x140056172  jnz     short loc_1400561D2
0x140056174  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x14005617b  mov     [rsp+80h+var_50], rax
0x140056180  mov     rax, [rbp+arg_20]
0x140056184  mov     [rsp+80h+var_58], rax
0x140056189  lea     rax, qword_1401C3B08
0x140056190  mov     [rsp+80h+var_60], rax
0x140056195  xor     r9d, r9d
0x140056198  mov     edx, 340h
0x14005619d  mov     r8d, 8007000Eh
0x1400561a3  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x1400561aa  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x1400561af  mov     r14d, eax
0x1400561b2  xor     ecx, ecx; bstrString
0x1400561b4  call    cs:__imp_SysFreeString
0x1400561ba  nop
0x1400561bb  xor     ecx, ecx; bstrString
0x1400561bd  call    cs:__imp_SysFreeString
0x1400561c3  nop
0x1400561c4  mov     rcx, rsi; bstrString
0x1400561c7  call    cs:__imp_SysFreeString
0x1400561cd  jmp     loc_1400563B1
0x1400561d2  mov     rdx, [r15]
0x1400561d5  mov     rdx, [rdx+18h]
0x1400561d9  lea     rcx, [rbp+var_30]
0x1400561dd  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1400561e2  mov     rdi, [rbp+var_30]
0x1400561e6  test    rdi, rdi
0x1400561e9  jnz     short loc_140056237
0x1400561eb  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x1400561f2  mov     [rsp+80h+var_50], rax
0x1400561f7  mov     rax, [rbp+arg_20]
0x1400561fb  mov     [rsp+80h+var_58], rax
0x140056200  lea     rax, qword_1401C3B08
0x140056207  mov     [rsp+80h+var_60], rax
0x14005620c  xor     r9d, r9d
0x14005620f  mov     edx, 346h
0x140056214  mov     r8d, 8007000Eh
0x14005621a  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140056221  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140056226  mov     r14d, eax
0x140056229  xor     ecx, ecx; bstrString
0x14005622b  call    cs:__imp_SysFreeString
0x140056231  nop
0x140056232  mov     rcx, rbx
0x140056235  jmp     short loc_1400561BD
0x140056237  mov     rax, [r14]
0x14005623a  lea     rdx, [rbp+arg_18]
0x14005623e  mov     rcx, r14
0x140056241  mov     rax, [rax+0B8h]
0x140056248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005624d  test    eax, eax
0x14005624f  jns     short loc_140056291
0x140056251  lea     rcx, aCannotGetOwner; "cannot get owner document"
0x140056258  mov     edx, 34Ch
0x14005625d  mov     [rsp+80h+var_50], rcx
0x140056262  mov     rcx, [rbp+arg_20]
0x140056266  mov     [rsp+80h+var_58], rcx
0x14005626b  mov     r9, r14
0x14005626e  lea     rcx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x140056275  mov     [rsp+80h+var_60], rcx
0x14005627a  mov     r8d, eax
0x14005627d  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140056284  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140056289  mov     r14d, eax
0x14005628c  mov     rcx, rdi
0x14005628f  jmp     short loc_14005622B
0x140056291  mov     rcx, [rbp+arg_18]
0x140056295  test    rcx, rcx
0x140056298  jz      loc_14005635C
0x14005629e  mov     rax, [rcx]
0x1400562a1  lea     r8, [rbp+arg_8]
0x1400562a5  lea     r15, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x1400562ac  mov     rdx, r15
0x1400562af  mov     rax, [rax]
0x1400562b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400562b7  test    eax, eax
0x1400562b9  jns     short loc_1400562E2
0x1400562bb  lea     rcx, aCannotGetADocu; "cannot get a document node"
0x1400562c2  mov     [rsp+80h+var_50], rcx
0x1400562c7  mov     rcx, [rbp+arg_20]
0x1400562cb  mov     [rsp+80h+var_58], rcx
0x1400562d0  lea     rcx, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60
0x1400562d7  mov     r9, [rbp+arg_18]
0x1400562db  mov     edx, 355h
0x1400562e0  jmp     short loc_140056275
0x1400562e2  xorps   xmm0, xmm0
0x1400562e5  xor     edx, edx
0x1400562e7  movups  [rbp+var_20], xmm0
0x1400562eb  lea     eax, [rdx+8]
0x1400562ee  mov     word ptr [rbp+var_20], ax
0x1400562f2  mov     qword ptr [rbp+var_20+8], rdi
0x1400562f6  mov     rcx, [rbp+arg_8]
0x1400562fa  movups  xmm0, [rbp+var_20]
0x1400562fe  movaps  [rbp+var_20], xmm0
0x140056302  mov     [rbp+var_10], rdx
0x140056306  mov     rax, [rcx]
0x140056309  lea     r8, [rbp+var_20]
0x14005630d  mov     rdx, rbx
0x140056310  mov     rax, [rax+280h]
0x140056317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005631c  test    eax, eax
0x14005631e  jns     short loc_14005635C
0x140056320  mov     [rsp+80h+var_48], rbx
0x140056325  lea     rcx, aCannotSetTheSD; "cannot set the %s document propert"
0x14005632c  mov     [rsp+80h+var_50], rcx
0x140056331  mov     rcx, [rbp+arg_20]
0x140056335  mov     [rsp+80h+var_58], rcx
0x14005633a  mov     [rsp+80h+var_60], r15
0x14005633f  mov     r9, [rbp+arg_8]
0x140056343  mov     r8d, eax
0x140056346  mov     edx, 35Eh
0x14005634b  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140056352  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140056357  jmp     loc_140056289
0x14005635c  mov     rax, [r14]
0x14005635f  mov     r8, r12
0x140056362  mov     rdx, rsi
0x140056365  mov     rcx, r14
0x140056368  mov     rax, [rax+120h]
0x14005636f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056374  test    eax, eax
0x140056376  jns     short loc_140056391
0x140056378  mov     qword ptr [r12], 0
0x140056380  lea     rcx, aCannotSelectNo; "cannot select nodes in an XML document"
0x140056387  mov     edx, 367h
0x14005638c  jmp     loc_14005625D
0x140056391  mov     rcx, rdi; bstrString
0x140056394  call    cs:__imp_SysFreeString
0x14005639a  nop
0x14005639b  mov     rcx, rbx; bstrString
0x14005639e  call    cs:__imp_SysFreeString
0x1400563a4  nop
0x1400563a5  mov     rcx, rsi; bstrString
0x1400563a8  call    cs:__imp_SysFreeString
0x1400563ae  xor     r14d, r14d
0x1400563b1  lea     rcx, [rbp+arg_8]
0x1400563b5  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x1400563ba  nop
0x1400563bb  lea     rcx, [rbp+arg_18]
0x1400563bf  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x1400563c4  mov     eax, r14d
0x1400563c7  lea     r11, [rsp+80h+var_s0]
0x1400563cf  mov     rbx, [r11+30h]
0x1400563d3  mov     rsi, [r11+40h]
0x1400563d7  mov     rsp, r11
0x1400563da  pop     r15
0x1400563dc  pop     r14
0x1400563de  pop     r12
0x1400563e0  pop     rdi
0x1400563e1  pop     rbp
0x1400563e2  retn
```
