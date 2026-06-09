# mlib::XmlDOM::LoadDocumentFromFile(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMDocument2 * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,bool)

- ea: `0x180001640`
- end: `0x180001977`
- name: `?LoadDocumentFromFile@XmlDOM@mlib@@SAJAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEAPEAUIXMLDOMDocument2@@PEAV32@_N@Z`
- size: `823`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180001980`
- `0x18002e99c`

## callees

- `0x180001640`
- `0x180006494`
- `0x180006584`
- `0x18000e490`
- `0x180012aa8`
- `0x180012b18`
- `0x180015f4c`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180001792`
- `OLEAUT32!__imp_SysAllocString` at `0x180001792`
- `OLEAUT32!__imp_VariantInit` at `0x180001762`
- `OLEAUT32!__imp_VariantInit` at `0x180001762`
- `OLEAUT32!__imp_VariantClear` at `0x18000177a`
- `OLEAUT32!__imp_VariantClear` at `0x18000182b`
- `OLEAUT32!__imp_VariantClear` at `0x18000189f`
- `OLEAUT32!__imp_VariantClear` at `0x18000190c`
- `OLEAUT32!__imp_VariantClear` at `0x180001942`
- `OLEAUT32!__imp_VariantClear` at `0x18000177a`
- `OLEAUT32!__imp_VariantClear` at `0x18000182b`
- `OLEAUT32!__imp_VariantClear` at `0x18000189f`
- `OLEAUT32!__imp_VariantClear` at `0x18000190c`
- `OLEAUT32!__imp_VariantClear` at `0x180001942`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000171b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000171b`

## string_xrefs

- `0x180001819`: `base\winsat\mlib\mxmldom.cpp`
- `0x18000188d`: `base\winsat\mlib\mxmldom.cpp`
- `0x1800018fa`: `base\winsat\mlib\mxmldom.cpp`
- `0x1800017f8`: `cannot create an IXMLDOMDocument2 document`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall mlib::XmlDOM::LoadDocumentFromFile(__int64 a1, char *a2, __int64 a3)
{
  const OLECHAR *v7; // r14
  __int64 v8; // rax
  int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  int v12; // eax
  unsigned int v13; // ebx
  LPVOID v14; // rax
  VARIANTARG pvarg; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG v16; // [rsp+60h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+B8h] [rbp+38h] BYREF
  __int16 v18; // [rsp+C8h] [rbp+48h] BYREF

  ppv = 0;
  v18 = 0;
  if ( dword_1800506A4 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800506A4);
    if ( dword_1800506A4 == -1 )
    {
      byte_1800506A3 = *a2;
      Init_thread_footer(&dword_1800506A4);
    }
  }
  *(_QWORD *)a2 = 0;
  if ( mlib::XmlDOM::fInitialized )
    goto LABEL_7;
  mlib::XmlDOM::clsIDDocument = 0;
  mlib::XmlDOM::clsIDSchema = 0;
  if ( mlib::XmlDOM::CheckMSXMLVersion() )
  {
    mlib::XmlDOM::fInitialized = 1;
LABEL_7:
    if ( CoCreateInstance(&mlib::XmlDOM::clsIDDocument, 0, 1u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &ppv) >= 0 )
    {
      VariantInit(&pvarg);
      v7 = *(const OLECHAR **)(*(_QWORD *)a1 + 24LL);
      VariantClear(&pvarg);
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)SysAllocString(v7);
      if ( !pvarg.llVal && v7 )
      {
        pvarg.vt = 10;
        pvarg.lVal = -2147024882;
        ATL::AtlThrowImpl(-2147024882);
      }
      v8 = *(_QWORD *)ppv;
      v16 = pvarg;
      v9 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(v8 + 464))(ppv, &v16, &v18);
      if ( v9 >= 0 )
      {
        if ( v18 )
        {
          v12 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 576LL))(ppv, 0xFFFFFFFFLL);
          if ( v12 >= 0 )
          {
            v14 = ppv;
            ppv = 0;
            *(_QWORD *)a2 = v14;
            VariantClear(&pvarg);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
            return 0;
          }
          else
          {
            v13 = mlib::XmlDOM::ReportCOMError_w(
                    (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                    246,
                    v12,
                    (_DWORD)ppv,
                    (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                    a3,
                    (__int64)L"cannot set the 'preserve white space' flag");
            VariantClear(&pvarg);
            if ( ppv )
              (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 16LL))(ppv, *(_QWORD *)ppv);
            return v13;
          }
        }
        else
        {
          v11 = mlib::XmlDOM::ReportCOMError_w(
                  (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                  235,
                  -2147467259,
                  (_DWORD)ppv,
                  (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                  a3,
                  (__int64)L"cannot load document from file '%s'",
                  *(_QWORD *)(*(_QWORD *)a1 + 24LL),
                  -2);
          VariantClear(&pvarg);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
          return v11;
        }
      }
      else
      {
        v10 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                230,
                v9,
                0,
                (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                a3,
                (__int64)L"cannot create an IXMLDOMDocument2 document");
        VariantClear(&pvarg);
        if ( ppv )
          (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 16LL))(ppv, *(_QWORD *)ppv);
        return v10;
      }
    }
    else
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
      return 2147500037LL;
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180001640  mov     rax, rsp
0x180001643  mov     [rax+20h], r9b
0x180001647  push    rbp
0x180001648  push    rdi
0x180001649  push    r12
0x18000164b  push    r14
0x18000164d  push    r15
0x18000164f  mov     rbp, rsp
0x180001652  sub     rsp, 80h
0x180001659  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x180001661  mov     [rax+8], rbx
0x180001665  mov     [rax+18h], rsi
0x180001669  mov     rsi, r8
0x18000166c  mov     rbx, rdx
0x18000166f  mov     rdi, rcx
0x180001672  xor     r15d, r15d
0x180001675  mov     [rbp+arg_8], r15
0x180001679  mov     [rbp+arg_18], r15w
0x18000167e  mov     edx, cs:_tls_index
0x180001684  mov     rax, gs:58h
0x18000168d  mov     ecx, 4
0x180001692  mov     rax, [rax+rdx*8]
0x180001696  mov     eax, [rcx+rax]
0x180001699  cmp     cs:dword_1800506A4, eax
0x18000169f  jle     short loc_1800016CB
0x1800016a1  lea     rcx, dword_1800506A4
0x1800016a8  call    _Init_thread_header
0x1800016ad  cmp     cs:dword_1800506A4, 0FFFFFFFFh
0x1800016b4  jnz     short loc_1800016CB
0x1800016b6  movzx   eax, byte ptr [rbx]
0x1800016b9  mov     cs:byte_1800506A3, al
0x1800016bf  lea     rcx, dword_1800506A4
0x1800016c6  call    _Init_thread_footer
0x1800016cb  mov     [rbx], r15
0x1800016ce  cmp     cs:?fInitialized@XmlDOM@mlib@@0_NA, 0; bool mlib::XmlDOM::fInitialized
0x1800016d5  jnz     short loc_1800016FB
0x1800016d7  xorps   xmm0, xmm0
0x1800016da  movups  xmmword ptr cs:?clsIDDocument@XmlDOM@mlib@@0U_GUID@@A.Data1, xmm0; _GUID mlib::XmlDOM::clsIDDocument ...
0x1800016e1  xorps   xmm1, xmm1
0x1800016e4  movups  xmmword ptr cs:?clsIDSchema@XmlDOM@mlib@@0U_GUID@@A.Data1, xmm1; _GUID mlib::XmlDOM::clsIDSchema ...
0x1800016eb  call    ?CheckMSXMLVersion@XmlDOM@mlib@@SA_NXZ; mlib::XmlDOM::CheckMSXMLVersion(void)
0x1800016f0  test    al, al
0x1800016f2  jz      short loc_18000173E
0x1800016f4  mov     cs:?fInitialized@XmlDOM@mlib@@0_NA, 1; bool mlib::XmlDOM::fInitialized
0x1800016fb  lea     rax, [rbp+arg_8]
0x1800016ff  mov     [rsp+80h+ppv], rax; ppv
0x180001704  lea     r12, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x18000170b  mov     r9, r12; riid
0x18000170e  xor     edx, edx; pUnkOuter
0x180001710  lea     r8d, [rdx+1]; dwClsContext
0x180001714  lea     rcx, ?clsIDDocument@XmlDOM@mlib@@0U_GUID@@A; rclsid
0x18000171b  call    cs:__imp_CoCreateInstance
0x180001722  nop     dword ptr [rax+rax+00h]
0x180001727  test    eax, eax
0x180001729  jns     short loc_18000175E
0x18000172b  lea     rcx, [rbp+arg_8]
0x18000172f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001734  mov     eax, 80004005h
0x180001739  jmp     loc_18000195A
0x18000173e  mov     rcx, [rbp+arg_8]
0x180001742  test    rcx, rcx
0x180001745  jz      short loc_180001754
0x180001747  mov     rax, [rcx]
0x18000174a  mov     rax, [rax+10h]
0x18000174e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001753  nop
0x180001754  mov     eax, 80004005h
0x180001759  jmp     loc_18000195A
0x18000175e  lea     rcx, [rbp+pvarg]; pvarg
0x180001762  call    cs:__imp_VariantInit
0x180001769  nop     dword ptr [rax+rax+00h]
0x18000176e  nop
0x18000176f  mov     rax, [rdi]
0x180001772  mov     r14, [rax+18h]
0x180001776  lea     rcx, [rbp+pvarg]; pvarg
0x18000177a  call    cs:__imp_VariantClear
0x180001781  nop     dword ptr [rax+rax+00h]
0x180001786  mov     eax, 8
0x18000178b  mov     word ptr [rbp+pvarg], ax
0x18000178f  mov     rcx, r14; psz
0x180001792  call    cs:__imp_SysAllocString
0x180001799  nop     dword ptr [rax+rax+00h]
0x18000179e  mov     qword ptr [rbp+pvarg+8], rax
0x1800017a2  test    rax, rax
0x1800017a5  jnz     short loc_1800017C7
0x1800017a7  test    r14, r14
0x1800017aa  jz      short loc_1800017C7
0x1800017ac  mov     eax, 0Ah
0x1800017b1  mov     word ptr [rbp+pvarg], ax
0x1800017b5  mov     dword ptr [rbp+pvarg+8], 8007000Eh
0x1800017bc  mov     ecx, 8007000Eh; int
0x1800017c1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800017c7  mov     rcx, [rbp+arg_8]
0x1800017cb  mov     rax, [rcx]
0x1800017ce  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800017d2  movaps  [rbp+var_20], xmm0
0x1800017d6  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1800017db  movsd   [rbp+var_10], xmm1
0x1800017e0  lea     r8, [rbp+arg_18]
0x1800017e4  lea     rdx, [rbp+var_20]
0x1800017e8  mov     rax, [rax+1D0h]
0x1800017ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017f4  test    eax, eax
0x1800017f6  jns     short loc_180001855
0x1800017f8  lea     rcx, aCannotCreateAn; "cannot create an IXMLDOMDocument2 docum"...
0x1800017ff  mov     [rsp+80h+var_50], rcx
0x180001804  mov     [rsp+80h+var_58], rsi
0x180001809  mov     [rsp+80h+ppv], r12
0x18000180e  xor     r9d, r9d
0x180001811  mov     r8d, eax
0x180001814  mov     edx, 0E6h
0x180001819  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180001820  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180001825  mov     ebx, eax
0x180001827  lea     rcx, [rbp+pvarg]; pvarg
0x18000182b  call    cs:__imp_VariantClear
0x180001832  nop     dword ptr [rax+rax+00h]
0x180001837  nop
0x180001838  mov     rcx, [rbp+arg_8]
0x18000183c  test    rcx, rcx
0x18000183f  jz      short loc_18000184E
0x180001841  mov     rdx, [rcx]
0x180001844  mov     rax, [rdx+10h]
0x180001848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000184d  nop
0x18000184e  mov     eax, ebx
0x180001850  jmp     loc_18000195A
0x180001855  cmp     [rbp+arg_18], 0
0x18000185a  jnz     short loc_1800018BC
0x18000185c  mov     rax, [rdi]
0x18000185f  mov     rcx, [rax+18h]
0x180001863  mov     [rsp+80h+var_48], rcx
0x180001868  lea     rax, aCannotLoadDocu; "cannot load document from file '%s'"
0x18000186f  mov     [rsp+80h+var_50], rax
0x180001874  mov     [rsp+80h+var_58], rsi
0x180001879  mov     [rsp+80h+ppv], r12
0x18000187e  mov     r9, [rbp+arg_8]
0x180001882  mov     edx, 0EBh
0x180001887  mov     r8d, 80004005h
0x18000188d  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180001894  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180001899  mov     ebx, eax
0x18000189b  lea     rcx, [rbp+pvarg]; pvarg
0x18000189f  call    cs:__imp_VariantClear
0x1800018a6  nop     dword ptr [rax+rax+00h]
0x1800018ab  nop
0x1800018ac  lea     rcx, [rbp+arg_8]
0x1800018b0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800018b5  mov     eax, ebx
0x1800018b7  jmp     loc_18000195A
0x1800018bc  mov     rcx, [rbp+arg_8]
0x1800018c0  mov     rax, [rcx]
0x1800018c3  mov     edx, 0FFFFFFFFh
0x1800018c8  mov     rax, [rax+240h]
0x1800018cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018d4  test    eax, eax
0x1800018d6  jns     short loc_180001933
0x1800018d8  lea     rcx, aCannotSetThePr; "cannot set the 'preserve white space' f"...
0x1800018df  mov     [rsp+80h+var_50], rcx
0x1800018e4  mov     [rsp+80h+var_58], rsi
0x1800018e9  mov     [rsp+80h+ppv], r12
0x1800018ee  mov     r9, [rbp+arg_8]
0x1800018f2  mov     r8d, eax
0x1800018f5  mov     edx, 0F6h
0x1800018fa  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180001901  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180001906  mov     ebx, eax
0x180001908  lea     rcx, [rbp+pvarg]; pvarg
0x18000190c  call    cs:__imp_VariantClear
0x180001913  nop     dword ptr [rax+rax+00h]
0x180001918  nop
0x180001919  mov     rcx, [rbp+arg_8]
0x18000191d  test    rcx, rcx
0x180001920  jz      short loc_18000192F
0x180001922  mov     rdx, [rcx]
0x180001925  mov     rax, [rdx+10h]
0x180001929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000192e  nop
0x18000192f  mov     eax, ebx
0x180001931  jmp     short loc_18000195A
0x180001933  mov     rax, [rbp+arg_8]
0x180001937  mov     [rbp+arg_8], r15
0x18000193b  mov     [rbx], rax
0x18000193e  lea     rcx, [rbp+pvarg]; pvarg
0x180001942  call    cs:__imp_VariantClear
0x180001949  nop     dword ptr [rax+rax+00h]
0x18000194e  nop
0x18000194f  lea     rcx, [rbp+arg_8]
0x180001953  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001958  xor     eax, eax
0x18000195a  lea     r11, [rsp+80h+var_s0]
0x180001962  mov     rbx, [r11+30h]
0x180001966  mov     rsi, [r11+40h]
0x18000196a  mov     rsp, r11
0x18000196d  pop     r15
0x18000196f  pop     r14
0x180001971  pop     r12
0x180001973  pop     rdi
0x180001974  pop     rbp
0x180001975  retn
```
