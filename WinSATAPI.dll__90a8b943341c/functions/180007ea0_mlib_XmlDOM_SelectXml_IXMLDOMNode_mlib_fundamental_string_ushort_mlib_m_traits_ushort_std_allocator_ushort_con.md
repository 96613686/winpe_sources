# mlib::XmlDOM::SelectXml(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMNodeList * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180007ea0`
- end: `0x18000847b`
- name: `?SelectXml@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@1PEAPEAUIXMLDOMNodeList@@PEAV42@@Z`
- size: `1499`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001980`
- `0x180007850`
- `0x180007b90`
- `0x18001f530`
- `0x18002cd94`

## callees

- `0x180006494`
- `0x180007ea0`
- `0x18000cf90`
- `0x18000e490`
- `0x180012bf3`
- `0x180015f4c`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180007f10`
- `OLEAUT32!__imp_SysAllocString` at `0x180007f10`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f01`
- `OLEAUT32!__imp_SysFreeString` at `0x180007fde`
- `OLEAUT32!__imp_SysFreeString` at `0x180007fee`
- `OLEAUT32!__imp_SysFreeString` at `0x180007ffe`
- `OLEAUT32!__imp_SysFreeString` at `0x180008063`
- `OLEAUT32!__imp_SysFreeString` at `0x180008073`
- `OLEAUT32!__imp_SysFreeString` at `0x180008083`
- `OLEAUT32!__imp_SysFreeString` at `0x1800080fe`
- `OLEAUT32!__imp_SysFreeString` at `0x18000810d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000811c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000820c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000821b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000822b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800082b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800082c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800082d0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800083b4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800083c4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800083d4`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f01`
- `OLEAUT32!__imp_SysFreeString` at `0x180007fde`
- `OLEAUT32!__imp_SysFreeString` at `0x180007fee`
- `OLEAUT32!__imp_SysFreeString` at `0x180007ffe`
- `OLEAUT32!__imp_SysFreeString` at `0x180008063`
- `OLEAUT32!__imp_SysFreeString` at `0x180008073`
- `OLEAUT32!__imp_SysFreeString` at `0x180008083`
- `OLEAUT32!__imp_SysFreeString` at `0x1800080fe`
- `OLEAUT32!__imp_SysFreeString` at `0x18000810d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000811c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000820c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000821b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000822b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800082b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800082c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800082d0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800083b4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800083c4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800083d4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180008196`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180008196`

## string_xrefs

- `0x180007fcc`: `base\winsat\mlib\mxmldom.cpp`
- `0x1800080ee`: `base\winsat\mlib\mxmldom.cpp`
- `0x1800081fc`: `base\winsat\mlib\mxmldom.cpp`
- `0x1800082a0`: `base\winsat\mlib\mxmldom.cpp`
- `0x180008369`: `base\winsat\mlib\mxmldom.cpp`
- `0x1800083a2`: `base\winsat\mlib\mxmldom.cpp`
- `0x180007fa0`: `cannot select nodes in an XML document`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall mlib::XmlDOM::SelectXml(__int64 a1, __int64 a2, _QWORD **a3, _QWORD *a4, __int64 a5)
{
  OLECHAR *v8; // rbx
  OLECHAR *v9; // rdi
  const OLECHAR *v10; // rsi
  OLECHAR *v11; // rsi
  __int64 v12; // rax
  const OLECHAR *i; // r14
  unsigned __int64 v14; // r14
  unsigned __int64 *v15; // rax
  unsigned __int64 cchCount2; // r12
  int v17; // eax
  unsigned int v18; // r14d
  unsigned int v20; // ebx
  const WCHAR *v21; // r8
  int v22; // eax
  unsigned int v23; // edi
  int v24; // eax
  unsigned int v25; // eax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  __int64 *v29; // [rsp+40h] [rbp-71h] BYREF
  __int64 v30; // [rsp+48h] [rbp-69h] BYREF
  char pExceptionObject; // [rsp+50h] [rbp-61h] BYREF
  __int64 v32; // [rsp+58h] [rbp-59h]
  BSTR bstrString; // [rsp+60h] [rbp-51h] BYREF
  BSTR v34; // [rsp+68h] [rbp-49h] BYREF
  _QWORD **v35; // [rsp+70h] [rbp-41h]
  __int128 v36; // [rsp+78h] [rbp-39h]
  __int64 v37; // [rsp+88h] [rbp-29h]
  __int64 v38; // [rsp+90h] [rbp-21h]
  OLECHAR *v39; // [rsp+98h] [rbp-19h]
  __int128 v40; // [rsp+A0h] [rbp-11h] BYREF
  __int64 v41; // [rsp+B0h] [rbp-1h]

  v38 = -2;
  v35 = a3;
  v32 = a5;
  v30 = 0;
  v29 = 0;
  v8 = 0;
  bstrString = 0;
  v9 = 0;
  v34 = 0;
  *a4 = 0;
  v10 = *(const OLECHAR **)(*(_QWORD *)a2 + 24LL);
  if ( !v10 )
  {
    v20 = mlib::XmlDOM::ReportCOMError_w(
            (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
            824,
            -2147024882,
            0,
            (__int64)&unk_180050618,
            a5,
            (__int64)L"cannot allocate memory for a string");
    SysFreeString(0);
    SysFreeString(0);
    SysFreeString(0);
    if ( v29 )
      (*(void (__fastcall **)(__int64 *))(*v29 + 16))(v29);
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    return v20;
  }
  SysFreeString(0);
  v11 = SysAllocString(v10);
  v39 = v11;
  if ( !v11 )
    ATL::AtlThrowImpl(-2147024882);
  v12 = 0x10000;
  for ( i = &String2; ; ++i )
  {
    if ( !v12 )
      throw (mlib::CStringTooBig *)&pExceptionObject;
    if ( !*i )
      break;
    --v12;
  }
  v14 = i - &String2;
  v15 = *a3;
  cchCount2 = **a3;
  if ( cchCount2 )
  {
    if ( v14 )
    {
      v21 = (const WCHAR *)v15[3];
      v22 = cchCount2 >= v14
          ? CompareStringW(0x400u, 0x1000u, v21, v14, &String2, v14)
          : CompareStringW(0x400u, 0x1000u, v21, cchCount2, &String2, cchCount2);
      if ( v22 == 2 && cchCount2 == v14 )
        goto LABEL_9;
    }
    goto LABEL_33;
  }
  if ( v14 )
  {
LABEL_33:
    ATL::CComBSTR::operator=(&bstrString, L"SelectionNamespaces");
    v8 = bstrString;
    if ( bstrString )
    {
      ATL::CComBSTR::operator=(&v34, (*v35)[3]);
      v9 = v34;
      if ( !v34 )
      {
        v23 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                838,
                -2147024882,
                0,
                (__int64)&unk_180050618,
                v32,
                (__int64)L"cannot allocate memory for a string");
        SysFreeString(0);
        SysFreeString(v8);
        SysFreeString(v11);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
        return v23;
      }
      v24 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 184LL))(a1, &v30);
      if ( v24 >= 0 )
      {
        if ( !v30 )
          goto LABEL_9;
        v26 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v30)(
                v30,
                &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                &v29);
        if ( v26 < 0 )
        {
          v25 = mlib::XmlDOM::ReportCOMError_w(
                  (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                  853,
                  v26,
                  v30,
                  (__int64)&GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
                  v32,
                  (__int64)L"cannot get a document node");
        }
        else
        {
          *(_QWORD *)&v36 = 8;
          v37 = 0;
          *((_QWORD *)&v36 + 1) = v9;
          v27 = *v29;
          v40 = v36;
          v41 = 0;
          v28 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, __int128 *))(v27 + 640))(v29, v8, &v40);
          if ( v28 >= 0 )
            goto LABEL_9;
          v25 = mlib::XmlDOM::ReportCOMError_w(
                  (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                  862,
                  v28,
                  (_DWORD)v29,
                  (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                  v32,
                  (__int64)L"cannot set the %s document propert",
                  v8);
        }
      }
      else
      {
        v25 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                844,
                v24,
                a1,
                (__int64)&GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
                v32,
                (__int64)L"cannot get owner document");
      }
      v18 = v25;
      SysFreeString(v9);
      SysFreeString(v8);
      SysFreeString(v11);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
      return v18;
    }
    v20 = mlib::XmlDOM::ReportCOMError_w(
            (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
            832,
            -2147024882,
            0,
            (__int64)&unk_180050618,
            v32,
            (__int64)L"cannot allocate memory for a string");
    SysFreeString(0);
    SysFreeString(0);
    SysFreeString(v11);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
    return v20;
  }
LABEL_9:
  v17 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD *))(*(_QWORD *)a1 + 288LL))(a1, v11, a4);
  if ( v17 < 0 )
  {
    *a4 = 0;
    v18 = mlib::XmlDOM::ReportCOMError_w(
            (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
            871,
            v17,
            a1,
            (__int64)&GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
            v32,
            (__int64)L"cannot select nodes in an XML document");
    SysFreeString(v9);
    SysFreeString(v8);
    SysFreeString(v11);
    if ( v29 )
      (*(void (__fastcall **)(__int64 *))(*v29 + 16))(v29);
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    return v18;
  }
  SysFreeString(v9);
  SysFreeString(v8);
  SysFreeString(v11);
  if ( v29 )
    (*(void (__fastcall **)(__int64 *))(*v29 + 16))(v29);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  return 0;
}

```

## disassembly

```asm
0x180007ea0  push    rbp
0x180007ea2  push    rbx
0x180007ea3  push    rsi
0x180007ea4  push    rdi
0x180007ea5  push    r12
0x180007ea7  push    r13
0x180007ea9  push    r14
0x180007eab  push    r15
0x180007ead  lea     rbp, [rsp-17h]
0x180007eb2  sub     rsp, 0C8h
0x180007eb9  mov     [rbp+4Fh+var_70], 0FFFFFFFFFFFFFFFEh
0x180007ec1  mov     r15, r9
0x180007ec4  mov     r12, r8
0x180007ec7  mov     [rbp+4Fh+var_90], r8
0x180007ecb  mov     r13, rcx
0x180007ece  mov     rcx, [rbp+4Fh+arg_20]
0x180007ed2  mov     [rbp+4Fh+var_A8], rcx
0x180007ed6  xor     eax, eax
0x180007ed8  mov     [rbp+4Fh+var_B8], rax
0x180007edc  mov     [rbp+4Fh+var_C0], rax
0x180007ee0  mov     ebx, eax
0x180007ee2  mov     [rbp+4Fh+bstrString], rax
0x180007ee6  mov     edi, eax
0x180007ee8  mov     [rbp+4Fh+var_98], rax
0x180007eec  mov     [r9], rax
0x180007eef  mov     rax, [rdx]
0x180007ef2  mov     rsi, [rax+18h]
0x180007ef6  test    rsi, rsi
0x180007ef9  jz      loc_1800080C3
0x180007eff  xor     ecx, ecx; bstrString
0x180007f01  call    cs:__imp_SysFreeString
0x180007f08  nop     dword ptr [rax+rax+00h]
0x180007f0d  mov     rcx, rsi; psz
0x180007f10  call    cs:__imp_SysAllocString
0x180007f17  nop     dword ptr [rax+rax+00h]
0x180007f1c  mov     rsi, rax
0x180007f1f  mov     [rbp+4Fh+var_68], rax
0x180007f23  test    rax, rax
0x180007f26  jz      loc_18000815C
0x180007f2c  mov     eax, 10000h
0x180007f31  lea     rcx, String2
0x180007f38  mov     r14, rcx
0x180007f3b  nop     dword ptr [rax+rax+00h]
0x180007f40  test    rax, rax
0x180007f43  jz      loc_18000804F
0x180007f49  cmp     word ptr [r14], 0
0x180007f4e  jz      short loc_180007F59
0x180007f50  add     r14, 2
0x180007f54  dec     rax
0x180007f57  jmp     short loc_180007F40
0x180007f59  sub     r14, rcx
0x180007f5c  sar     r14, 1
0x180007f5f  mov     rax, [r12]
0x180007f63  mov     r12, [rax]
0x180007f66  test    r12, r12
0x180007f69  jnz     loc_180008167
0x180007f6f  test    r14, r14
0x180007f72  jnz     loc_1800081B0
0x180007f78  mov     rax, [r13+0]
0x180007f7c  mov     r8, r15
0x180007f7f  mov     rdx, rsi
0x180007f82  mov     rcx, r13
0x180007f85  mov     rax, [rax+120h]
0x180007f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f91  test    eax, eax
0x180007f93  jns     loc_180008060
0x180007f99  mov     qword ptr [r15], 0
0x180007fa0  lea     rcx, aCannotSelectNo; "cannot select nodes in an XML document"
0x180007fa7  mov     [rsp+100h+var_D0], rcx
0x180007fac  mov     rcx, [rbp+4Fh+var_A8]
0x180007fb0  mov     qword ptr [rsp+100h+cchCount2], rcx
0x180007fb5  lea     rcx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x180007fbc  mov     [rsp+100h+lpString2], rcx
0x180007fc1  mov     r9, r13
0x180007fc4  mov     r8d, eax
0x180007fc7  mov     edx, 367h
0x180007fcc  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180007fd3  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180007fd8  mov     r14d, eax
0x180007fdb  mov     rcx, rdi; bstrString
0x180007fde  call    cs:__imp_SysFreeString
0x180007fe5  nop     dword ptr [rax+rax+00h]
0x180007fea  nop
0x180007feb  mov     rcx, rbx; bstrString
0x180007fee  call    cs:__imp_SysFreeString
0x180007ff5  nop     dword ptr [rax+rax+00h]
0x180007ffa  nop
0x180007ffb  mov     rcx, rsi; bstrString
0x180007ffe  call    cs:__imp_SysFreeString
0x180008005  nop     dword ptr [rax+rax+00h]
0x18000800a  nop
0x18000800b  mov     rcx, [rbp+4Fh+var_C0]
0x18000800f  test    rcx, rcx
0x180008012  jz      short loc_180008021
0x180008014  mov     rax, [rcx]
0x180008017  mov     rax, [rax+10h]
0x18000801b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008020  nop
0x180008021  mov     rcx, [rbp+4Fh+var_B8]
0x180008025  test    rcx, rcx
0x180008028  jz      short loc_180008037
0x18000802a  mov     rax, [rcx]
0x18000802d  mov     rax, [rax+10h]
0x180008031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008036  nop
0x180008037  mov     eax, r14d
0x18000803a  add     rsp, 0C8h
0x180008041  pop     r15
0x180008043  pop     r14
0x180008045  pop     r13
0x180008047  pop     r12
0x180008049  pop     rdi
0x18000804a  pop     rsi
0x18000804b  pop     rbx
0x18000804c  pop     rbp
0x18000804d  retn
0x18000804f  lea     rdx, _TI1?AVCStringTooBig@mlib@@; pThrowInfo
0x180008056  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18000805a  call    _CxxThrowException_0
0x180008060  mov     rcx, rdi; bstrString
0x180008063  call    cs:__imp_SysFreeString
0x18000806a  nop     dword ptr [rax+rax+00h]
0x18000806f  nop
0x180008070  mov     rcx, rbx; bstrString
0x180008073  call    cs:__imp_SysFreeString
0x18000807a  nop     dword ptr [rax+rax+00h]
0x18000807f  nop
0x180008080  mov     rcx, rsi; bstrString
0x180008083  call    cs:__imp_SysFreeString
0x18000808a  nop     dword ptr [rax+rax+00h]
0x18000808f  nop
0x180008090  mov     rcx, [rbp+4Fh+var_C0]
0x180008094  test    rcx, rcx
0x180008097  jz      short loc_1800080A6
0x180008099  mov     rax, [rcx]
0x18000809c  mov     rax, [rax+10h]
0x1800080a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080a5  nop
0x1800080a6  mov     rcx, [rbp+4Fh+var_B8]
0x1800080aa  test    rcx, rcx
0x1800080ad  jz      short loc_1800080BC
0x1800080af  mov     rax, [rcx]
0x1800080b2  mov     rax, [rax+10h]
0x1800080b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080bb  nop
0x1800080bc  xor     eax, eax
0x1800080be  jmp     loc_18000803A
0x1800080c3  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x1800080ca  mov     [rsp+100h+var_D0], rax
0x1800080cf  mov     qword ptr [rsp+100h+cchCount2], rcx
0x1800080d4  lea     rax, unk_180050618
0x1800080db  mov     [rsp+100h+lpString2], rax
0x1800080e0  xor     r9d, r9d
0x1800080e3  mov     edx, 338h
0x1800080e8  mov     r8d, 8007000Eh
0x1800080ee  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x1800080f5  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x1800080fa  mov     ebx, eax
0x1800080fc  xor     ecx, ecx; bstrString
0x1800080fe  call    cs:__imp_SysFreeString
0x180008105  nop     dword ptr [rax+rax+00h]
0x18000810a  nop
0x18000810b  xor     ecx, ecx; bstrString
0x18000810d  call    cs:__imp_SysFreeString
0x180008114  nop     dword ptr [rax+rax+00h]
0x180008119  nop
0x18000811a  xor     ecx, ecx; bstrString
0x18000811c  call    cs:__imp_SysFreeString
0x180008123  nop     dword ptr [rax+rax+00h]
0x180008128  nop
0x180008129  mov     rcx, [rbp+4Fh+var_C0]
0x18000812d  test    rcx, rcx
0x180008130  jz      short loc_18000813F
0x180008132  mov     rax, [rcx]
0x180008135  mov     rax, [rax+10h]
0x180008139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000813e  nop
0x18000813f  mov     rcx, [rbp+4Fh+var_B8]
0x180008143  test    rcx, rcx
0x180008146  jz      short loc_180008155
0x180008148  mov     rax, [rcx]
0x18000814b  mov     rax, [rax+10h]
0x18000814f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008154  nop
0x180008155  mov     eax, ebx
0x180008157  jmp     loc_18000803A
0x18000815c  mov     ecx, 8007000Eh; int
0x180008161  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008167  test    r14, r14
0x18000816a  jz      short loc_1800081B0
0x18000816c  mov     r8, [rax+18h]; lpString1
0x180008170  mov     edx, 1000h; dwCmpFlags
0x180008175  cmp     r12, r14
0x180008178  jnb     short loc_180008184
0x18000817a  mov     [rsp+100h+cchCount2], r12d
0x18000817f  mov     r9d, r12d
0x180008182  jmp     short loc_18000818C
0x180008184  mov     [rsp+100h+cchCount2], r14d; cchCount2
0x180008189  mov     r9d, r14d; cchCount1
0x18000818c  mov     [rsp+100h+lpString2], rcx; lpString2
0x180008191  mov     ecx, 400h; Locale
0x180008196  call    cs:__imp_CompareStringW
0x18000819d  nop     dword ptr [rax+rax+00h]
0x1800081a2  add     eax, 0FFFFFFFEh
0x1800081a5  jnz     short loc_1800081B0
0x1800081a7  cmp     r12, r14
0x1800081aa  jz      loc_180007F78
0x1800081b0  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x1800081b7  lea     rcx, [rbp+4Fh+bstrString]
0x1800081bb  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1800081c0  mov     rbx, [rbp+4Fh+bstrString]
0x1800081c4  test    rbx, rbx
0x1800081c7  jnz     loc_180008250
0x1800081cd  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x1800081d4  mov     [rsp+100h+var_D0], rax
0x1800081d9  mov     rcx, [rbp+4Fh+var_A8]
0x1800081dd  mov     qword ptr [rsp+100h+cchCount2], rcx
0x1800081e2  lea     rax, unk_180050618
0x1800081e9  mov     [rsp+100h+lpString2], rax
0x1800081ee  xor     r9d, r9d
0x1800081f1  mov     edx, 340h
0x1800081f6  mov     r8d, 8007000Eh
0x1800081fc  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180008203  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180008208  mov     ebx, eax
0x18000820a  xor     ecx, ecx; bstrString
0x18000820c  call    cs:__imp_SysFreeString
0x180008213  nop     dword ptr [rax+rax+00h]
0x180008218  nop
0x180008219  xor     ecx, ecx; bstrString
0x18000821b  call    cs:__imp_SysFreeString
0x180008222  nop     dword ptr [rax+rax+00h]
0x180008227  nop
0x180008228  mov     rcx, rsi; bstrString
0x18000822b  call    cs:__imp_SysFreeString
0x180008232  nop     dword ptr [rax+rax+00h]
0x180008237  nop
0x180008238  lea     rcx, [rbp+4Fh+var_C0]
0x18000823c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008241  nop
0x180008242  lea     rcx, [rbp+4Fh+var_B8]
0x180008246  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000824b  jmp     loc_180008155
0x180008250  mov     rax, [rbp+4Fh+var_90]
0x180008254  mov     rax, [rax]
0x180008257  mov     rdx, [rax+18h]
0x18000825b  lea     rcx, [rbp+4Fh+var_98]
0x18000825f  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180008264  mov     rdi, [rbp+4Fh+var_98]
0x180008268  test    rdi, rdi
0x18000826b  jnz     loc_1800082F7
0x180008271  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x180008278  mov     [rsp+100h+var_D0], rax
0x18000827d  mov     rcx, [rbp+4Fh+var_A8]
0x180008281  mov     qword ptr [rsp+100h+cchCount2], rcx
0x180008286  lea     rax, unk_180050618
0x18000828d  mov     [rsp+100h+lpString2], rax
0x180008292  xor     r9d, r9d
0x180008295  mov     edx, 346h
0x18000829a  mov     r8d, 8007000Eh
0x1800082a0  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x1800082a7  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x1800082ac  mov     edi, eax
0x1800082ae  xor     ecx, ecx; bstrString
0x1800082b0  call    cs:__imp_SysFreeString
0x1800082b7  nop     dword ptr [rax+rax+00h]
0x1800082bc  nop
0x1800082bd  mov     rcx, rbx; bstrString
0x1800082c0  call    cs:__imp_SysFreeString
0x1800082c7  nop     dword ptr [rax+rax+00h]
0x1800082cc  nop
0x1800082cd  mov     rcx, rsi; bstrString
0x1800082d0  call    cs:__imp_SysFreeString
0x1800082d7  nop     dword ptr [rax+rax+00h]
0x1800082dc  nop
0x1800082dd  lea     rcx, [rbp+4Fh+var_C0]
0x1800082e1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800082e6  nop
0x1800082e7  lea     rcx, [rbp+4Fh+var_B8]
0x1800082eb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800082f0  mov     eax, edi
0x1800082f2  jmp     loc_18000803A
0x1800082f7  mov     rax, [r13+0]
0x1800082fb  lea     rdx, [rbp+4Fh+var_B8]
0x1800082ff  mov     rcx, r13
0x180008302  mov     rax, [rax+0B8h]
0x180008309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000830e  test    eax, eax
0x180008310  jns     loc_1800083F9
0x180008316  lea     rcx, aCannotGetOwner; "cannot get owner document"
0x18000831d  mov     [rsp+100h+var_D0], rcx
0x180008322  mov     rcx, [rbp+4Fh+var_A8]
0x180008326  mov     qword ptr [rsp+100h+cchCount2], rcx
0x18000832b  lea     rcx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x180008332  mov     r9, r13
0x180008335  mov     edx, 34Ch
0x18000833a  jmp     short loc_180008361
0x18000833c  lea     rcx, aCannotGetADocu; "cannot get a document node"
0x180008343  mov     [rsp+100h+var_D0], rcx
0x180008348  mov     rcx, [rbp+4Fh+var_A8]
  ... truncated ...
```
