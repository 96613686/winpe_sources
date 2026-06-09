# Mso::SVG::SVGImage::Save(IStream &,bool,Mso::SVG::SVGSaveParams const &)

- ea: `0x180005420`
- end: `0x1800058a6`
- name: `?Save@SVGImage@SVG@Mso@@UEAAXAEAUIStream@@_NAEBUSVGSaveParams@23@@Z`
- size: `1158`
- prototype: `void(Mso::SVG::SVGImage *__hidden this, struct IStream *, bool, const struct Mso::SVG::SVGSaveParams *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005420`
- `0x180007360`
- `0x1800079f8`
- `0x1800081d0`
- `0x180008bdc`
- `0x1800091d0`
- `0x180011290`
- `0x180139c14`
- `0x18013ba2c`
- `0x18013d700`
- `0x18013f810`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180005535`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180005535`
- `OLEAUT32!__imp_SysFreeString` at `0x1800057d7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800057d7`
- `OLEAUT32!__imp_VariantInit` at `0x1800055c9`
- `OLEAUT32!__imp_VariantInit` at `0x1800055c9`
- `mso40uiWin32Client!__imp_?CreateSAXXMLReader@Ofc@@YAXAEAV?$TCntPtr@UISAXXMLReader@@@1@@Z` at `0x1800055af`
- `mso40uiWin32Client!__imp_?CreateSAXXMLReader@Ofc@@YAXAEAV?$TCntPtr@UISAXXMLReader@@@1@@Z` at `0x1800055af`
- `Mso20Win32Client!__imp_?MsoCopyStream@@YAJPEAUIStream@@0@Z` at `0x1800054b3`
- `Mso20Win32Client!__imp_?MsoCopyStream@@YAJPEAUIStream@@0@Z` at `0x1800054b3`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x180005675`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x180005675`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z` at `0x1800056d4`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z` at `0x1800056d4`
- `Mso20Win32Client!__imp_?Load@XMLDOMDocument@Dom@Xml@Mso@@SAJAEBUDocumentIdentifier@234@AEBUDocumentLoadSettings@234@PEAPEAV1234@@Z` at `0x180005597`
- `Mso20Win32Client!__imp_?Load@XMLDOMDocument@Dom@Xml@Mso@@SAJAEBUDocumentIdentifier@234@AEBUDocumentLoadSettings@234@PEAPEAV1234@@Z` at `0x180005597`
- `MSVCP140!??1?$basic_iostream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x18000581d`
- `MSVCP140!??1?$basic_iostream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x18000581d`
- `MSVCP140!??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x180005827`
- `MSVCP140!??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x180005827`
- `MSVCP140!_Mtx_unlock` at `0x180005846`
- `MSVCP140!_Mtx_unlock` at `0x180005846`
- `MSVCP140!_Mtx_lock` at `0x18000546a`
- `MSVCP140!_Mtx_lock` at `0x18000546a`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180005478`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180005494`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180005478`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180005494`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180005728`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180005728`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180005721`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180005721`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Mso::SVG::SVGImage::Save(
        Mso::SVG::SVGImage *this,
        struct IStream *a2,
        char a3,
        const struct Mso::SVG::SVGSaveParams *a4)
{
  char *v8; // rdi
  struct IStream *v9; // rcx
  int v10; // eax
  OLECHAR *v11; // rbx
  const OLECHAR *v12; // rcx
  unsigned __int64 v13; // rdx
  BOOL v14; // edx
  struct Mso::Xml::Dom::XMLDOMDocument *v15; // r8
  __int64 v16; // rax
  int v17; // r15d
  void *v18; // rcx
  int v19; // ecx
  __int64 v20; // rcx
  struct IStream *v21; // rcx
  _DWORD v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct IStream *v23; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v24; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v25; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG v27; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR *v28; // [rsp+90h] [rbp-70h]
  _QWORD v29[2]; // [rsp+98h] [rbp-68h] BYREF
  char *v30; // [rsp+A8h] [rbp-58h]
  _QWORD v31[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v32[8]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v33[8]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v34[120]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v35[104]; // [rsp+148h] [rbp+48h] BYREF
  OLECHAR *strIn[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  _QWORD v37[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  int v38; // [rsp+1E0h] [rbp+E0h]
  __int16 v39; // [rsp+1E4h] [rbp+E4h]
  void *Block[2]; // [rsp+1E8h] [rbp+E8h]
  __m128i si128; // [rsp+1F8h] [rbp+F8h]

  v8 = (char *)this + 48;
  v30 = (char *)this + 48;
  if ( _Mtx_lock((Mso::SVG::SVGImage *)((char *)this + 48)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)v8 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v8 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( *((_BYTE *)this + 136) )
  {
    v9 = (struct IStream *)*((_QWORD *)this + 18);
    if ( v9 )
    {
      v10 = MsoCopyStream(v9, a2);
      if ( v10 >= 0 )
        goto LABEL_38;
      goto LABEL_41;
    }
  }
  std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v31);
  Mso::SVG::Environment::Serialize(*((_QWORD *)this + 16), v32, a4);
  std::wstringbuf::str(v33, strIn);
  v11 = 0;
  v28 = 0;
  v12 = (const OLECHAR *)strIn;
  if ( strIn[3] > (OLECHAR *)7 )
    v12 = strIn[0];
  v13 = (unsigned __int64)strIn[2] & ((unsigned __int128)-(__int128)(unsigned __int64)v12 >> 64);
  if ( v12 )
  {
    if ( v13 > 0xFFFFFFFF )
      goto LABEL_42;
    v11 = SysAllocStringLen(v12, v13);
    v28 = v11;
    v14 = v11 != 0;
  }
  else
  {
    v14 = 1;
  }
  if ( !v14 )
  {
    Ofc::CHResultException::ThrowTag(-2147024882, 0x138D862u);
    __debugbreak();
  }
  v29[0] = 1;
  v29[1] = v11;
  v22[0] = 256;
  v22[1] = 0x1000000;
  v23 = 0;
  if ( (int)Mso::Xml::Dom::XMLDOMDocument::Load(
              (const struct Mso::Xml::Dom::DocumentIdentifier *)v29,
              (const struct Mso::Xml::Dom::DocumentLoadSettings *)v22,
              (struct Mso::Xml::Dom::XMLDOMDocument **)&v23) < 0 )
  {
    v24 = 0;
    Ofc::CreateSAXXMLReader(&v24);
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)v11;
    v16 = *v24;
    v27 = pvarg;
    v17 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *))(v16 + 152))(v24, &v27);
    v37[1] = "SH_ErrorCode";
    v38 = v17;
    v39 = 4;
    *(_OWORD *)Block = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(Block[0]) = 0;
    v37[0] = &Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable';
    if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(38028109, 1890, 10) )
    {
      v25 = v37;
      *(_QWORD *)&v27.vt = &Mso::Logging::CompositeStructuredTrace::`vftable';
      v27.llVal = (LONGLONG)&v25;
      v27.pRecInfo = (IRecordInfo *)&pvarg;
      Mso::Logging::MsoSendStructuredTraceTag(38028109, 1890, 10);
    }
    if ( si128.m128i_i64[1] > 7uLL )
    {
      v18 = Block[0];
      if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
      {
        v18 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v18 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v18);
    }
    v19 = -2147467259;
    if ( v17 < 0 )
      v19 = v17;
    Ofc::CHResultException::ThrowTag(v19, 0x138D863u);
LABEL_41:
    Ofc::CHResultException::ThrowTag(v10, 0x138D861u);
LABEL_42:
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  Mso::SVG::SaveSVGToStream((Mso::SVG *)a2, v23, v15);
  if ( *((struct IStream **)this + 18) != a2 )
  {
    if ( a2 )
      ((void (__fastcall *)(struct IStream *))a2->lpVtbl->AddRef)(a2);
    v20 = *((_QWORD *)this + 18);
    if ( v20 )
    {
      *((_QWORD *)this + 18) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    *((_QWORD *)this + 18) = a2;
  }
  *((_BYTE *)this + 136) = 1;
  v21 = v23;
  if ( v23 )
  {
    v23 = 0;
    ((void (__fastcall *)(struct IStream *))v21->lpVtbl->AddRef)(v21);
  }
  if ( v11 )
    SysFreeString(v11);
  std::wstring::~wstring(strIn);
  *(_QWORD *)((char *)v31 + *(int *)(v31[0] + 4LL)) = &std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vftable';
  *(_DWORD *)((char *)&v30 + *(int *)(v31[0] + 4LL) + 4) = *(_DWORD *)(v31[0] + 4LL) - 152;
  std::wstringbuf::~wstringbuf(v33);
  std::wiostream::~basic_iostream<wchar_t,std::char_traits<wchar_t>>(v34);
  std::wios::~wios<wchar_t,std::char_traits<wchar_t>>(v35);
LABEL_38:
  if ( a3 )
    (*(void (__fastcall **)(Mso::SVG::SVGImage *))(*(_QWORD *)this + 96LL))(this);
  _Mtx_unlock((_Mtx_t)v8);
}

```

## disassembly

```asm
0x180005420  mov     [rsp-8+arg_10], rbx
0x180005425  push    rbp
0x180005426  push    rsi
0x180005427  push    rdi
0x180005428  push    r12
0x18000542a  push    r13
0x18000542c  push    r14
0x18000542e  push    r15
0x180005430  lea     rbp, [rsp-110h]
0x180005438  sub     rsp, 210h
0x18000543f  mov     rax, cs:__security_cookie
0x180005446  xor     rax, rsp
0x180005449  mov     [rbp+140h+var_38], rax
0x180005450  mov     rbx, r9
0x180005453  mov     r12b, r8b
0x180005456  mov     r14, rdx
0x180005459  mov     rsi, rcx
0x18000545c  xor     r13d, r13d
0x18000545f  lea     rdi, [rcx+30h]
0x180005463  mov     [rbp+140h+var_198], rdi
0x180005467  mov     rcx, rdi; _Mtx_t
0x18000546a  call    cs:__imp__Mtx_lock
0x180005470  test    eax, eax
0x180005472  jz      short loc_18000547F
0x180005474  lea     ecx, [r13+5]
0x180005478  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000547e  int     3; Trap to Debugger
0x18000547f  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x180005486  jnz     short loc_18000549B
0x180005488  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x18000548f  mov     ecx, 6
0x180005494  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000549a  nop
0x18000549b  cmp     [rsi+88h], r13b
0x1800054a2  jz      short loc_1800054C6
0x1800054a4  mov     rcx, [rsi+90h]
0x1800054ab  test    rcx, rcx
0x1800054ae  jz      short loc_1800054C6
0x1800054b0  mov     rdx, r14
0x1800054b3  call    cs:__imp_?MsoCopyStream@@YAJPEAUIStream@@0@Z; MsoCopyStream(IStream *,IStream *)
0x1800054b9  test    eax, eax
0x1800054bb  js      loc_180005884
0x1800054c1  jmp     loc_18000582D
0x1800054c6  lea     rcx, [rbp+140h+var_190]
0x1800054ca  call    ??0?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x1800054cf  nop
0x1800054d0  mov     r8, rbx
0x1800054d3  lea     rdx, [rbp+140h+var_180]
0x1800054d7  mov     rcx, [rsi+80h]
0x1800054de  call    ?Serialize@Environment@SVG@Mso@@QEAAXAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@std@@AEBUSVGSaveParams@23@@Z; Mso::SVG::Environment::Serialize(std::wostream &,Mso::SVG::SVGSaveParams const &)
0x1800054e3  lea     rdx, [rbp+140h+strIn]
0x1800054ea  lea     rcx, [rbp+140h+var_178]
0x1800054ee  call    ?str@?$basic_stringbuf@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEGBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::wstringbuf::str(void)
0x1800054f3  nop
0x1800054f4  mov     rbx, r13
0x1800054f7  mov     [rbp+140h+var_1B0], rbx
0x1800054fb  lea     rcx, [rbp+140h+strIn]
0x180005502  cmp     [rbp+140h+var_78], 7
0x18000550a  cmova   rcx, [rbp+140h+strIn]; strIn
0x180005512  mov     rax, rcx
0x180005515  neg     rax
0x180005518  sbb     rdx, rdx
0x18000551b  and     rdx, [rbp+140h+var_80]; ui
0x180005522  test    rcx, rcx
0x180005525  jz      short loc_18000554D
0x180005527  mov     eax, 0FFFFFFFFh
0x18000552c  cmp     rdx, rax
0x18000552f  ja      loc_180005895
0x180005535  call    cs:__imp_SysAllocStringLen
0x18000553b  mov     rbx, rax
0x18000553e  mov     [rbp+140h+var_1B0], rax
0x180005542  mov     edx, r13d
0x180005545  test    rax, rax
0x180005548  setnz   dl
0x18000554b  jmp     short loc_180005552
0x18000554d  mov     edx, 1
0x180005552  mov     eax, edx
0x180005554  neg     eax
0x180005556  sbb     ecx, ecx
0x180005558  not     ecx
0x18000555a  and     ecx, 8007000Eh; int
0x180005560  test    edx, edx
0x180005562  jz      loc_18000589B
0x180005568  mov     [rbp+140h+var_1A8], 1
0x180005570  mov     [rbp+140h+var_1A0], rbx
0x180005574  mov     [rsp+240h+var_210], 100h
0x18000557c  mov     [rsp+240h+var_20C], 1000000h
0x180005584  mov     [rsp+240h+var_208], r13
0x180005589  lea     r8, [rsp+240h+var_208]
0x18000558e  lea     rdx, [rsp+240h+var_210]
0x180005593  lea     rcx, [rbp+140h+var_1A8]
0x180005597  call    cs:__imp_?Load@XMLDOMDocument@Dom@Xml@Mso@@SAJAEBUDocumentIdentifier@234@AEBUDocumentLoadSettings@234@PEAPEAV1234@@Z; Mso::Xml::Dom::XMLDOMDocument::Load(Mso::Xml::Dom::DocumentIdentifier const &,Mso::Xml::Dom::DocumentLoadSettings const &,Mso::Xml::Dom::XMLDOMDocument * *)
0x18000559d  test    eax, eax
0x18000559f  jns     loc_180005759
0x1800055a5  mov     [rsp+240h+var_200], r13
0x1800055aa  lea     rcx, [rsp+240h+var_200]
0x1800055af  call    cs:__imp_?CreateSAXXMLReader@Ofc@@YAXAEAV?$TCntPtr@UISAXXMLReader@@@1@@Z; Ofc::CreateSAXXMLReader(Ofc::TCntPtr<ISAXXMLReader> &)
0x1800055b5  xorps   xmm0, xmm0
0x1800055b8  xor     eax, eax
0x1800055ba  movups  xmmword ptr [rsp+240h+pvarg], xmm0
0x1800055bf  mov     qword ptr [rsp+240h+pvarg+10h], rax
0x1800055c4  lea     rcx, [rsp+240h+pvarg]; pvarg
0x1800055c9  call    cs:__imp_VariantInit
0x1800055cf  mov     eax, 8
0x1800055d4  mov     word ptr [rsp+240h+pvarg], ax
0x1800055d9  mov     qword ptr [rsp+240h+pvarg+8], rbx
0x1800055de  mov     rcx, [rsp+240h+var_200]
0x1800055e3  mov     rax, [rcx]
0x1800055e6  movups  xmm0, xmmword ptr [rsp+240h+pvarg]
0x1800055eb  movaps  [rsp+240h+var_1D0], xmm0
0x1800055f0  movsd   xmm1, qword ptr [rsp+240h+pvarg+10h]
0x1800055f6  movsd   [rbp+140h+var_1C0], xmm1
0x1800055fb  lea     rdx, [rsp+240h+var_1D0]
0x180005600  mov     rax, [rax+98h]
0x180005607  call    cs:__guard_dispatch_icall_fptr
0x18000560d  mov     r15d, eax
0x180005610  lea     rax, aShErrorcode; "SH_ErrorCode"
0x180005617  mov     [rbp+140h+var_68], rax
0x18000561e  mov     [rbp+140h+var_60], r15d
0x180005625  mov     eax, 4
0x18000562a  mov     [rbp+140h+var_5C], ax
0x180005631  xorps   xmm0, xmm0
0x180005634  movups  xmmword ptr [rbp+140h+Block], xmm0
0x18000563b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180005643  movdqu  [rbp+140h+var_48], xmm1
0x18000564b  mov     word ptr [rbp+140h+Block], r13w
0x180005653  lea     rax, ??_7ClassifiedStructuredErrorId@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable'
0x18000565a  mov     [rbp+140h+var_70], rax
0x180005661  mov     edx, 762h
0x180005666  mov     ecx, 244434Dh
0x18000566b  mov     r9d, 2
0x180005671  lea     r8d, [r9+8]
0x180005675  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x18000567b  test    al, al
0x18000567d  jz      short loc_1800056DA
0x18000567f  lea     rax, [rbp+140h+var_70]
0x180005686  mov     [rsp+240h+var_1F8], rax
0x18000568b  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x180005692  mov     qword ptr [rsp+240h+var_1D0], rax
0x180005697  lea     rax, [rsp+240h+var_1F8]
0x18000569c  mov     qword ptr [rsp+240h+var_1D0+8], rax
0x1800056a1  lea     rax, [rsp+240h+pvarg]
0x1800056a6  mov     [rbp+140h+var_1C0], rax
0x1800056aa  mov     r9d, 2
0x1800056b0  lea     rax, [rsp+240h+var_1D0]
0x1800056b5  mov     [rsp+240h+var_218], rax
0x1800056ba  lea     rax, aSaxParserFailu; "SAX parser failure for SVG save data"
0x1800056c1  mov     [rsp+240h+Reserved], rax
0x1800056c6  mov     edx, 762h
0x1800056cb  mov     ecx, 244434Dh
0x1800056d0  lea     r8d, [r9+8]
0x1800056d4  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,char const *,Mso::Logging::IStructuredTrace const &)
0x1800056da  mov     rax, qword ptr [rbp+140h+var_48+8]
0x1800056e1  cmp     rax, 7
0x1800056e5  jbe     short loc_18000572E
0x1800056e7  mov     rcx, [rbp+140h+Block]; Block
0x1800056ee  mov     rdx, rcx
0x1800056f1  lea     rax, ds:2[rax*2]
0x1800056f9  cmp     rax, 1000h
0x1800056ff  jb      short loc_180005728
0x180005701  mov     rcx, [rcx-8]
0x180005705  sub     rdx, rcx
0x180005708  lea     rax, [rdx-8]
0x18000570c  cmp     rax, 1Fh
0x180005710  jbe     short loc_180005728
0x180005712  mov     [rsp+240h+Reserved], r13; Reserved
0x180005717  xor     r9d, r9d; LineNo
0x18000571a  xor     r8d, r8d; FileName
0x18000571d  xor     edx, edx; FunctionName
0x18000571f  xor     ecx, ecx; Expression
0x180005721  call    cs:__imp__invoke_watson
0x180005728  call    cs:__imp_free
0x18000572e  mov     ecx, 80004005h
0x180005733  test    r15d, r15d
0x180005736  cmovs   ecx, r15d; int
0x18000573a  test    ecx, ecx
0x18000573c  js      loc_180005876
0x180005742  mov     rcx, [rsp+240h+var_200]
0x180005747  test    rcx, rcx
0x18000574a  jz      short loc_180005759
0x18000574c  mov     rax, [rcx]
0x18000574f  mov     rax, [rax+10h]
0x180005753  call    cs:__guard_dispatch_icall_fptr
0x180005759  mov     rdx, [rsp+240h+var_208]; struct IStream *
0x18000575e  mov     rcx, r14; this
0x180005761  call    ?SaveSVGToStream@SVG@Mso@@YAXAEAUIStream@@AEAVXMLDOMDocument@Dom@Xml@2@@Z; Mso::SVG::SaveSVGToStream(IStream &,Mso::Xml::Dom::XMLDOMDocument &)
0x180005766  cmp     [rsi+90h], r14
0x18000576d  jz      short loc_1800057AB
0x18000576f  test    r14, r14
0x180005772  jz      short loc_180005784
0x180005774  mov     rax, [r14]
0x180005777  mov     rcx, r14
0x18000577a  mov     rax, [rax+8]
0x18000577e  call    cs:__guard_dispatch_icall_fptr
0x180005784  mov     rcx, [rsi+90h]
0x18000578b  test    rcx, rcx
0x18000578e  jz      short loc_1800057A4
0x180005790  mov     [rsi+90h], r13
0x180005797  mov     rax, [rcx]
0x18000579a  mov     rax, [rax+10h]
0x18000579e  call    cs:__guard_dispatch_icall_fptr
0x1800057a4  mov     [rsi+90h], r14
0x1800057ab  mov     byte ptr [rsi+88h], 1
0x1800057b2  mov     rcx, [rsp+240h+var_208]
0x1800057b7  test    rcx, rcx
0x1800057ba  jz      short loc_1800057CF
0x1800057bc  mov     [rsp+240h+var_208], r13
0x1800057c1  mov     rax, [rcx]
0x1800057c4  mov     rax, [rax+8]
0x1800057c8  call    cs:__guard_dispatch_icall_fptr
0x1800057ce  nop
0x1800057cf  test    rbx, rbx
0x1800057d2  jz      short loc_1800057DE
0x1800057d4  mov     rcx, rbx; bstrString
0x1800057d7  call    cs:__imp_SysFreeString
0x1800057dd  nop
0x1800057de  lea     rcx, [rbp+140h+strIn]; void *
0x1800057e5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800057ea  mov     rax, [rbp+140h+var_190]
0x1800057ee  movsxd  rcx, dword ptr [rax+4]
0x1800057f2  lea     rax, ??_7?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@6B@; const std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vftable'
0x1800057f9  mov     [rbp+rcx+140h+var_190], rax
0x1800057fe  mov     rax, [rbp+140h+var_190]
0x180005802  movsxd  rcx, dword ptr [rax+4]
0x180005806  lea     edx, [rcx-98h]
0x18000580c  mov     dword ptr [rbp+rcx+140h+var_198+4], edx
0x180005810  lea     rcx, [rbp+140h+var_178]
0x180005814  call    ??1?$basic_stringbuf@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UEAA@XZ; std::wstringbuf::~wstringbuf(void)
0x180005819  lea     rcx, [rbp+140h+var_170]
0x18000581d  call    cs:__imp_??1?$basic_iostream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ; std::wiostream::~basic_iostream<wchar_t,std::char_traits<wchar_t>>(void)
0x180005823  lea     rcx, [rbp+140h+var_F8]
0x180005827  call    cs:__imp_??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ; std::wios::~wios<wchar_t,std::char_traits<wchar_t>>(void)
0x18000582d  test    r12b, r12b
0x180005830  jz      short loc_180005843
0x180005832  mov     rax, [rsi]
0x180005835  mov     rcx, rsi
0x180005838  mov     rax, [rax+60h]
0x18000583c  call    cs:__guard_dispatch_icall_fptr
0x180005842  nop
0x180005843  mov     rcx, rdi; _Mtx_t
0x180005846  call    cs:__imp__Mtx_unlock
0x18000584c  mov     rcx, [rbp+140h+var_38]
0x180005853  xor     rcx, rsp; StackCookie
0x180005856  call    __security_check_cookie
0x18000585b  mov     rbx, [rsp+240h+arg_10]
0x180005863  add     rsp, 210h
0x18000586a  pop     r15
0x18000586c  pop     r14
0x18000586e  pop     r13
0x180005870  pop     r12
0x180005872  pop     rdi
0x180005873  pop     rsi
0x180005874  pop     rbp
0x180005875  retn
0x180005876  mov     edx, 138D863h; unsigned int
0x18000587b  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180005880  nop
0x180005881  jmp     short $+2
0x180005883  nop
0x180005884  mov     edx, 138D861h; unsigned int
0x180005889  mov     ecx, eax; int
0x18000588b  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180005890  nop
0x180005891  jmp     short loc_180005894
0x180005894  nop
0x180005895  call    ?SafeIntOnOverflow@SafeInt_InvalidParameter@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow(void)
0x18000589b  mov     edx, 138D862h; unsigned int
0x1800058a0  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1800058a5  int     3; Trap to Debugger
```
