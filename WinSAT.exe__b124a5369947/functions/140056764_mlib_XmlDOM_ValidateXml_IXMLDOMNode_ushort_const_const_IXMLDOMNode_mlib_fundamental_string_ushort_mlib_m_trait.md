# mlib::XmlDOM::ValidateXml(IXMLDOMNode *,ushort const * const,IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x140056764`
- end: `0x140056b06`
- name: `?ValidateXml@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@QEBG0PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z`
- size: `930`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140012f64`

## callees

- `0x14000712c`
- `0x1400196bc`
- `0x140019a1c`
- `0x140053e14`
- `0x1400557f4`
- `0x140056764`
- `0x14011a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140056898`
- `OLEAUT32!__imp_SysFreeString` at `0x14005690b`
- `OLEAUT32!__imp_SysFreeString` at `0x140056915`
- `OLEAUT32!__imp_SysFreeString` at `0x140056a40`
- `OLEAUT32!__imp_SysFreeString` at `0x140056a4a`
- `OLEAUT32!__imp_SysFreeString` at `0x140056898`
- `OLEAUT32!__imp_SysFreeString` at `0x14005690b`
- `OLEAUT32!__imp_SysFreeString` at `0x140056915`
- `OLEAUT32!__imp_SysFreeString` at `0x140056a40`
- `OLEAUT32!__imp_SysFreeString` at `0x140056a4a`
- `ole32!CoCreateInstance` at `0x140056822`
- `ole32!CoCreateInstance` at `0x140056822`

## string_xrefs

- `0x140056886`: `base\winsat\mlib\mxmldom.cpp`
- `0x1400568f9`: `base\winsat\mlib\mxmldom.cpp`
- `0x140056ac9`: `base\winsat\mlib\mxmldom.cpp`
- `0x14005682c`: `cannot create an IXMLDOMSchemaCollection object`
- `0x140056a9e`: `cannot prarse XML%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall mlib::XmlDOM::ValidateXml(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v6; // ebx
  int v7; // eax
  unsigned int v8; // eax
  HRESULT v9; // eax
  int v10; // r8d
  int v11; // edx
  OLECHAR *v12; // rbx
  unsigned int v13; // edi
  OLECHAR *v14; // rcx
  int v15; // eax
  unsigned int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  const wchar_t *v21; // [rsp+38h] [rbp-59h]
  BSTR bstrString; // [rsp+48h] [rbp-49h] BYREF
  __int64 v23; // [rsp+50h] [rbp-41h] BYREF
  __int64 v24; // [rsp+58h] [rbp-39h] BYREF
  unsigned int v25; // [rsp+60h] [rbp-31h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-29h] BYREF
  BSTR v27; // [rsp+70h] [rbp-21h] BYREF
  __int128 v28; // [rsp+78h] [rbp-19h]
  __int128 v29; // [rsp+98h] [rbp+7h] BYREF
  __int64 v30; // [rsp+A8h] [rbp+17h]
  __int64 v31; // [rsp+100h] [rbp+6Fh] BYREF

  v31 = a2;
  v6 = (int)a1;
  ppv = 0;
  v24 = 0;
  v23 = 0;
  v27 = 0;
  bstrString = 0;
  v28 = 0;
  v7 = (**a1)(a1, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &v24);
  if ( v7 >= 0 )
  {
    v9 = CoCreateInstance(&mlib::XmlDOM::clsIDSchema, 0, 0x15u, &GUID_373984c8_b845_449b_91e7_45ac83036ade, &ppv);
    if ( v9 < 0 )
    {
      v21 = L"cannot create an IXMLDOMSchemaCollection object";
      v10 = v9;
      v11 = 721;
LABEL_7:
      v8 = mlib::XmlDOM::ReportCOMError_w(
             (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
             v11,
             v10,
             0,
             (__int64)qword_1401C3B08,
             a4,
             (__int64)v21);
      goto LABEL_8;
    }
    ATL::CComBSTR::operator=(&v27, &qword_14012B318);
    v12 = v27;
    if ( !v27 )
    {
      v21 = L"cannot allocate memory for a string";
      v11 = 727;
      v10 = -2147024882;
      goto LABEL_7;
    }
    LOWORD(v28) = 9;
    *((_QWORD *)&v28 + 1) = a3;
    v29 = v28;
    v30 = 0;
    v15 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int128 *))(*(_QWORD *)ppv + 56LL))(ppv, v27, &v29);
    if ( v15 >= 0 )
    {
      *((_QWORD *)&v28 + 1) = ppv;
      v29 = v28;
      v30 = 0;
      v17 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v24 + 624LL))(v24, &v29);
      if ( v17 >= 0 )
      {
        v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 632LL))(v24, &v23);
        if ( v18 >= 0 )
        {
          if ( v18 == 1 )
          {
            v19 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v23 + 72LL))(v23, &bstrString);
            if ( v19 < 0 )
            {
              v16 = mlib::XmlDOM::ReportCOMError_w(
                      (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                      777,
                      v19,
                      v23,
                      (__int64)&GUID_3efaa426_272f_11d2_836f_0000f87a7782,
                      a4,
                      (__int64)L"cannot obtain the parsing error");
              goto LABEL_11;
            }
            v25 = -1;
            LODWORD(v31) = -1;
            (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v23 + 88LL))(v23, &v25);
            (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 96LL))(v23, &v31);
            if ( !a4 )
            {
              v16 = mlib::XmlDOM::ReportCOMError_w(
                      (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                      772,
                      -2147467259,
                      0,
                      (__int64)qword_1401C3B08,
                      0,
                      (__int64)L"cannot prarse XML%s",
                      *(_QWORD *)(MEMORY[0] + 24LL));
              goto LABEL_11;
            }
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::reserve(
              a4,
              2048);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
              a4,
              L"\nLine %ld Col %ld\n%s",
              v25,
              (unsigned int)v31,
              bstrString);
          }
          SysFreeString(bstrString);
          SysFreeString(v12);
          v13 = 0;
          goto LABEL_22;
        }
        v16 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                753,
                v18,
                v24,
                (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                a4,
                (__int64)L"cannot validate");
      }
      else
      {
        v16 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                746,
                v17,
                v24,
                (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                a4,
                (__int64)L"cannot add a reference");
      }
    }
    else
    {
      v16 = mlib::XmlDOM::ReportCOMError_w(
              (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
              736,
              v15,
              (_DWORD)ppv,
              (__int64)&GUID_373984c8_b845_449b_91e7_45ac83036ade,
              a4,
              (__int64)L"cannot add data to a collection");
    }
LABEL_11:
    v13 = v16;
    SysFreeString(bstrString);
    v14 = v12;
    goto LABEL_12;
  }
  v8 = mlib::XmlDOM::ReportCOMError_w(
         (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
         709,
         v7,
         v6,
         (__int64)&GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
         a4,
         (__int64)L"cannot query interface");
LABEL_8:
  v13 = v8;
  SysFreeString(bstrString);
  v14 = 0;
LABEL_12:
  SysFreeString(v14);
LABEL_22:
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v23);
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v24);
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&ppv);
  return v13;
}

```

## disassembly

```asm
0x140056764  mov     rax, rsp
0x140056767  mov     [rax+8], rbx
0x14005676b  mov     [rax+18h], rsi
0x14005676f  mov     [rax+10h], rdx
0x140056773  push    rbp
0x140056774  push    rdi
0x140056775  push    r12
0x140056777  push    r13
0x140056779  push    r15
0x14005677b  lea     rbp, [rax-5Fh]
0x14005677f  sub     rsp, 0C0h
0x140056786  movaps  xmmword ptr [rax-38h], xmm6
0x14005678a  mov     rdi, r9
0x14005678d  mov     rsi, r8
0x140056790  mov     rbx, rcx
0x140056793  mov     [rbp+57h+var_80], 0
0x14005679b  mov     [rbp+57h+var_90], 0
0x1400567a3  mov     [rbp+57h+var_98], 0
0x1400567ab  mov     [rbp+57h+var_78], 0
0x1400567b3  mov     [rbp+57h+bstrString], 0
0x1400567bb  xorps   xmm0, xmm0
0x1400567be  xor     r13d, r13d
0x1400567c1  movups  [rbp+57h+var_70], xmm0
0x1400567c5  mov     rax, [rcx]
0x1400567c8  lea     r8, [rbp+57h+var_90]
0x1400567cc  lea     r12, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x1400567d3  mov     rdx, r12
0x1400567d6  mov     rax, [rax]
0x1400567d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400567de  test    eax, eax
0x1400567e0  jns     short loc_140056802
0x1400567e2  lea     rcx, aCannotQueryInt; "cannot query interface"
0x1400567e9  mov     [rsp+0E0h+var_B0], rcx
0x1400567ee  lea     rcx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x1400567f5  mov     r9, rbx
0x1400567f8  mov     r8d, eax
0x1400567fb  mov     edx, 2C5h
0x140056800  jmp     short loc_14005687C
0x140056802  lea     rax, [rbp+57h+var_80]
0x140056806  mov     [rsp+0E0h+ppv], rax; ppv
0x14005680b  lea     r15, _GUID_373984c8_b845_449b_91e7_45ac83036ade
0x140056812  mov     r9, r15; riid
0x140056815  xor     edx, edx; pUnkOuter
0x140056817  lea     r8d, [rdx+15h]; dwClsContext
0x14005681b  lea     rcx, ?clsIDSchema@XmlDOM@mlib@@0U_GUID@@A; rclsid
0x140056822  call    cs:__imp_CoCreateInstance
0x140056828  test    eax, eax
0x14005682a  jns     short loc_140056842
0x14005682c  lea     rcx, aCannotCreateAn_0; "cannot create an IXMLDOMSchemaCollectio"...
0x140056833  mov     [rsp+0E0h+var_B0], rcx
0x140056838  mov     r8d, eax
0x14005683b  mov     edx, 2D1h
0x140056840  jmp     short loc_140056872
0x140056842  lea     rdx, qword_14012B318
0x140056849  lea     rcx, [rbp+57h+var_78]
0x14005684d  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x140056852  mov     rbx, [rbp+57h+var_78]
0x140056856  test    rbx, rbx
0x140056859  jnz     short loc_1400568A3
0x14005685b  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x140056862  mov     [rsp+0E0h+var_B0], rax
0x140056867  mov     edx, 2D7h
0x14005686c  mov     r8d, 8007000Eh
0x140056872  xor     r9d, r9d
0x140056875  lea     rcx, qword_1401C3B08
0x14005687c  mov     [rsp+0E0h+var_B8], rdi
0x140056881  mov     [rsp+0E0h+ppv], rcx
0x140056886  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x14005688d  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140056892  mov     edi, eax
0x140056894  mov     rcx, [rbp+57h+bstrString]; bstrString
0x140056898  call    cs:__imp_SysFreeString
0x14005689e  nop
0x14005689f  xor     ecx, ecx
0x1400568a1  jmp     short loc_140056915
0x1400568a3  mov     eax, 9
0x1400568a8  mov     word ptr [rbp+57h+var_70], ax
0x1400568ac  mov     qword ptr [rbp+57h+var_70+8], rsi
0x1400568b0  mov     rcx, [rbp+57h+var_80]
0x1400568b4  movups  xmm0, [rbp+57h+var_70]
0x1400568b8  movaps  [rbp+57h+var_50], xmm0
0x1400568bc  mov     [rbp+57h+var_40], r13
0x1400568c0  mov     rax, [rcx]
0x1400568c3  lea     r8, [rbp+57h+var_50]
0x1400568c7  mov     rdx, rbx
0x1400568ca  mov     rax, [rax+38h]
0x1400568ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400568d3  test    eax, eax
0x1400568d5  jns     short loc_140056920
0x1400568d7  lea     rcx, aCannotAddDataT; "cannot add data to a collection"
0x1400568de  mov     [rsp+0E0h+var_B0], rcx
0x1400568e3  mov     [rsp+0E0h+var_B8], rdi
0x1400568e8  mov     [rsp+0E0h+ppv], r15
0x1400568ed  mov     r9, [rbp+57h+var_80]
0x1400568f1  mov     edx, 2E0h
0x1400568f6  mov     r8d, eax
0x1400568f9  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140056900  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140056905  mov     edi, eax
0x140056907  mov     rcx, [rbp+57h+bstrString]; bstrString
0x14005690b  call    cs:__imp_SysFreeString
0x140056911  nop
0x140056912  mov     rcx, rbx; bstrString
0x140056915  call    cs:__imp_SysFreeString
0x14005691b  jmp     loc_140056A52
0x140056920  mov     rax, [rbp+57h+var_80]
0x140056924  mov     qword ptr [rbp+57h+var_70+8], rax
0x140056928  mov     rcx, [rbp+57h+var_90]
0x14005692c  movups  xmm0, [rbp+57h+var_70]
0x140056930  movaps  [rbp+57h+var_50], xmm0
0x140056934  mov     [rbp+57h+var_40], r13
0x140056938  mov     rax, [rcx]
0x14005693b  lea     rdx, [rbp+57h+var_50]
0x14005693f  mov     rax, [rax+270h]
0x140056946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005694b  test    eax, eax
0x14005694d  jns     short loc_140056970
0x14005694f  lea     rcx, aCannotAddARefe; "cannot add a reference"
0x140056956  mov     [rsp+0E0h+var_B0], rcx
0x14005695b  mov     [rsp+0E0h+var_B8], rdi
0x140056960  mov     [rsp+0E0h+ppv], r12
0x140056965  mov     r9, [rbp+57h+var_90]
0x140056969  mov     edx, 2EAh
0x14005696e  jmp     short loc_1400568F6
0x140056970  mov     rcx, [rbp+57h+var_90]
0x140056974  mov     rax, [rcx]
0x140056977  lea     rdx, [rbp+57h+var_98]
0x14005697b  mov     rax, [rax+278h]
0x140056982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056987  test    eax, eax
0x140056989  jns     short loc_1400569AF
0x14005698b  lea     rcx, aCannotValidate; "cannot validate"
0x140056992  mov     [rsp+0E0h+var_B0], rcx
0x140056997  mov     [rsp+0E0h+var_B8], rdi
0x14005699c  mov     [rsp+0E0h+ppv], r12
0x1400569a1  mov     r9, [rbp+57h+var_90]
0x1400569a5  mov     edx, 2F1h
0x1400569aa  jmp     loc_1400568F6
0x1400569af  cmp     eax, 1
0x1400569b2  jnz     loc_140056A3C
0x1400569b8  mov     rcx, [rbp+57h+var_98]
0x1400569bc  mov     rax, [rcx]
0x1400569bf  lea     rdx, [rbp+57h+bstrString]
0x1400569c3  mov     rax, [rax+48h]
0x1400569c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400569cc  test    eax, eax
0x1400569ce  js      loc_140056ADA
0x1400569d4  or      eax, 0FFFFFFFFh
0x1400569d7  mov     [rbp+57h+var_88], eax
0x1400569da  mov     dword ptr [rbp+57h+arg_8], eax
0x1400569dd  mov     rcx, [rbp+57h+var_98]
0x1400569e1  mov     rax, [rcx]
0x1400569e4  lea     rdx, [rbp+57h+var_88]
0x1400569e8  mov     rax, [rax+58h]
0x1400569ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400569f1  mov     rcx, [rbp+57h+var_98]
0x1400569f5  mov     rax, [rcx]
0x1400569f8  lea     rdx, [rbp+57h+arg_8]
0x1400569fc  mov     rax, [rax+60h]
0x140056a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056a05  test    rdi, rdi
0x140056a08  jz      loc_140056A92
0x140056a0e  mov     edx, 800h
0x140056a13  mov     rcx, rdi
0x140056a16  call    ?reserve@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAX_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::reserve(unsigned __int64)
0x140056a1b  mov     rax, [rbp+57h+bstrString]
0x140056a1f  mov     [rsp+0E0h+ppv], rax
0x140056a24  mov     r9d, dword ptr [rbp+57h+arg_8]
0x140056a28  mov     r8d, [rbp+57h+var_88]
0x140056a2c  lea     rdx, aLineLdColLdS; "\nLine %ld Col %ld\n%s"
0x140056a33  mov     rcx, rdi
0x140056a36  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x140056a3b  nop
0x140056a3c  mov     rcx, [rbp+57h+bstrString]; bstrString
0x140056a40  call    cs:__imp_SysFreeString
0x140056a46  nop
0x140056a47  mov     rcx, rbx; bstrString
0x140056a4a  call    cs:__imp_SysFreeString
0x140056a50  xor     edi, edi
0x140056a52  lea     rcx, [rbp+57h+var_98]
0x140056a56  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140056a5b  nop
0x140056a5c  lea     rcx, [rbp+57h+var_90]
0x140056a60  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140056a65  nop
0x140056a66  lea     rcx, [rbp+57h+var_80]
0x140056a6a  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140056a6f  mov     eax, edi
0x140056a71  lea     r11, [rsp+0E0h+var_20]
0x140056a79  mov     rbx, [r11+30h]
0x140056a7d  mov     rsi, [r11+40h]
0x140056a81  movaps  xmm6, xmmword ptr [r11-10h]
0x140056a86  mov     rsp, r11
0x140056a89  pop     r15
0x140056a8b  pop     r13
0x140056a8d  pop     r12
0x140056a8f  pop     rdi
0x140056a90  pop     rbp
0x140056a91  retn
0x140056a92  mov     rax, [rdi]
0x140056a95  mov     rcx, [rax+18h]
0x140056a99  mov     [rsp+0E0h+var_A8], rcx
0x140056a9e  lea     rax, aCannotPrarseXm; "cannot prarse XML%s"
0x140056aa5  mov     [rsp+0E0h+var_B0], rax
0x140056aaa  mov     [rsp+0E0h+var_B8], r13
0x140056aaf  lea     rcx, qword_1401C3B08
0x140056ab6  mov     [rsp+0E0h+ppv], rcx
0x140056abb  xor     r9d, r9d
0x140056abe  mov     edx, 304h
0x140056ac3  mov     r8d, 80004005h
0x140056ac9  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140056ad0  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140056ad5  jmp     loc_140056905
0x140056ada  lea     rcx, aCannotObtainTh; "cannot obtain the parsing error"
0x140056ae1  mov     [rsp+0E0h+var_B0], rcx
0x140056ae6  mov     [rsp+0E0h+var_B8], rdi
0x140056aeb  lea     rcx, _GUID_3efaa426_272f_11d2_836f_0000f87a7782
0x140056af2  mov     [rsp+0E0h+ppv], rcx
0x140056af7  mov     r9, [rbp+57h+var_98]
0x140056afb  mov     edx, 309h
0x140056b00  jmp     loc_1400568F6
```
