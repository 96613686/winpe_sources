# Transcoder::CTranscoderProxy::OnTranscoderExternalResourceReq(LowRights::WzMsg const &)

- ea: `0x1802008c0`
- end: `0x180200e35`
- name: `?OnTranscoderExternalResourceReq@CTranscoderProxy@Transcoder@@AEAAPEAUWzMsg@LowRights@@AEBU34@@Z`
- size: `1397`
- prototype: `struct LowRights::WzMsg *(Transcoder::CTranscoderProxy *__hidden this, const struct LowRights::WzMsg *)`
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x180200850`

## callees

- `0x18000c300`
- `0x180056ee0`
- `0x1800573f0`
- `0x180064e30`
- `0x18007aa30`
- `0x18008ea00`
- `0x18008ea40`
- `0x18008feec`
- `0x1800982e4`
- `0x180179338`
- `0x180183d28`
- `0x1801d3afc`
- `0x1801e0e40`
- `0x1801ff780`
- `0x1801ffa08`
- `0x1802000e0`
- `0x18020023c`
- `0x1802008c0`
- `0x180201038`

## import_xrefs

- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x180200bd0`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x180200bd0`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x1802009cd`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x1802009f4`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x1802009cd`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x1802009f4`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x1802009dd`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x1802009dd`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180200b5d`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180200b5d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180200cbe`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180200cbe`
- `Mso20Win32Client!__imp_?MsoHrGetFileByteStream@@YAJPEB_WKPEAPEAUIByteStream@@@Z` at `0x180200c14`
- `Mso20Win32Client!__imp_?MsoHrGetFileByteStream@@YAJPEB_WKPEAPEAUIByteStream@@@Z` at `0x180200c14`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
struct LowRights::WzMsg *__fastcall Transcoder::CTranscoderProxy::OnTranscoderExternalResourceReq(
        Transcoder::CTranscoderProxy *this,
        const struct LowRights::WzMsg *a2)
{
  __int64 v4; // rax
  struct LowRights::WzMsg *v5; // rdi
  UINT v6; // edx
  _QWORD *v7; // r8
  _QWORD *v8; // rax
  size_t v9; // rbx
  struct LowRights::WzMsg *Response; // rbx
  struct LowRights::WzMsg *result; // rax
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // rax
  wchar_t **v15; // rax
  struct LowRights::WzMsg *v16; // rax
  void *v17; // rax
  void *v18; // rdi
  struct LowRights::WzMsg *v19; // rbx
  const wchar_t *v20; // rcx
  signed int FileByteStream; // r14d
  struct LowRights::WzMsg *v22; // rbx
  struct IByteStream *v23; // rcx
  struct IByteStream *v24; // rcx
  signed int v25; // eax
  struct IByteStream *v26; // rcx
  struct IByteStream *v27; // rcx
  const wchar_t *v28; // r8
  struct LowRights::WzMsg *v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  const wchar_t *v33; // r8
  __int64 v34; // [rsp+40h] [rbp-138h] BYREF
  struct IByteStream *v35; // [rsp+48h] [rbp-130h] BYREF
  _DWORD v36[4]; // [rsp+50h] [rbp-128h] BYREF
  struct LowRights::WzMsg *v37; // [rsp+60h] [rbp-118h] BYREF
  __int64 v38; // [rsp+68h] [rbp-110h]
  const struct LowRights::BaseMsg *v39; // [rsp+80h] [rbp-F8h]
  const std::exception *v40; // [rsp+88h] [rbp-F0h] BYREF
  __int128 v41; // [rsp+90h] [rbp-E8h] BYREF
  __int128 v42; // [rsp+A0h] [rbp-D8h]
  wchar_t *v43[2]; // [rsp+B0h] [rbp-C8h] BYREF
  __m128i si128; // [rsp+C0h] [rbp-B8h]
  __int128 v45; // [rsp+D0h] [rbp-A8h] BYREF
  __int128 v46; // [rsp+E0h] [rbp-98h]
  _QWORD Src[3]; // [rsp+F0h] [rbp-88h] BYREF
  unsigned __int64 v48; // [rsp+108h] [rbp-70h]
  _BYTE v49[40]; // [rsp+110h] [rbp-68h] BYREF
  _BYTE v50[32]; // [rsp+138h] [rbp-40h] BYREF

  try
  {
    v39 = a2;
    *(_OWORD *)v43 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v43[0]) = 0;
    v4 = std::filesystem::path::path(v49, (char *)a2 + 16);
    std::filesystem::path::filename(v4, &v41);
    std::wstring::~wstring(v49);
    v5 = (struct LowRights::WzMsg *)&v41;
    if ( *((_QWORD *)&v42 + 1) > 7u )
      v5 = (struct LowRights::WzMsg *)v41;
    v37 = v5;
    v38 = v42;
    v6 = _std_fs_code_page();
    std::_Convert_wide_to_narrow<std::char_traits<char>>(Src, v6);
    v7 = Src;
    if ( v48 > 0xF )
      v7 = (_QWORD *)Src[0];
    Mso::FunctorThrow<std::unique_ptr<std::istream> (char const *)>::operator()((char *)this + 32, &v34, v7);
    std::string::~string(Src);
    std::istream::seekg(v34, 0, 2);
    v8 = (_QWORD *)std::istream::tellg(v34, &v37);
    v9 = *v8 + v8[1];
    std::istream::seekg(v34, 0, 0);
    if ( !v9 )
    {
      Response = LowRights::WzMsg::CreateResponse(a2, 0x80070057, 0);
      std::unique_ptr<std::istream>::~unique_ptr<std::istream>(&v34);
      std::wstring::~wstring(&v41);
      std::wstring::~wstring(v43);
      return Response;
    }
    v12 = Mso::TCntPtr<IWICImagingFactory>::operator->((char *)this + 8);
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v12 + 32LL))(v12, &v45);
    _InterlockedIncrement((volatile signed __int32 *)this + 10);
    v13 = std::to_wstring(Src, *((unsigned int *)this + 10));
    v14 = std::operator+<wchar_t>(v49, L"requestedresource", v13);
    std::wstring::operator=(v43, v14);
    std::wstring::~wstring(v49);
    std::wstring::~wstring(Src);
    v15 = v43;
    if ( si128.m128i_i64[1] > 7uLL )
      v15 = (wchar_t **)v43[0];
    v37 = (struct LowRights::WzMsg *)v15;
    v38 = si128.m128i_i64[0];
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(Src, &v37);
    v16 = (struct LowRights::WzMsg *)&v45;
    if ( *((_QWORD *)&v46 + 1) > 7u )
      v16 = (struct LowRights::WzMsg *)v45;
    v37 = v16;
    std::filesystem::path::path(v49, &v37);
    std::filesystem::operator/(v50);
    std::wstring::~wstring(v49);
    std::wstring::~wstring(Src);
    v17 = malloc(v9);
    v18 = v17;
    if ( !v17 )
    {
      v19 = LowRights::WzMsg::CreateResponse(a2, 0x8007000E, 0);
      std::wstring::~wstring(v50);
      std::wstring::~wstring(&v45);
      std::unique_ptr<std::istream>::~unique_ptr<std::istream>(&v34);
      std::wstring::~wstring(&v41);
      std::wstring::~wstring(v43);
      return v19;
    }
    std::istream::read(v34, v17, v9);
    v35 = 0;
    std::wstring::wstring(Src, v50);
    v20 = (const wchar_t *)Src;
    if ( v48 > 7 )
      v20 = (const wchar_t *)Src[0];
    FileByteStream = MsoHrGetFileByteStream(v20, 0x40002u, &v35);
    std::wstring::~wstring(Src);
    if ( FileByteStream < 0 )
    {
      v22 = LowRights::WzMsg::CreateResponse(a2, FileByteStream, 0);
      v23 = v35;
      if ( v35 )
      {
        v35 = 0;
        (*(void (__fastcall **)(struct IByteStream *))(*(_QWORD *)v23 + 16LL))(v23);
      }
LABEL_19:
      std::wstring::~wstring(v50);
      std::wstring::~wstring(&v45);
      std::unique_ptr<std::istream>::~unique_ptr<std::istream>(&v34);
      std::wstring::~wstring(&v41);
      std::wstring::~wstring(v43);
      return v22;
    }
    v36[0] = 0;
    v24 = v35;
    if ( !v35 )
      CrashWithRecovery(0x1E3C3840u, 0);
    if ( v9 > 0xFFFFFFFF )
      __fastfail(5u);
    v25 = (*(__int64 (__fastcall **)(struct IByteStream *, _QWORD, void *, _QWORD, _DWORD *, _QWORD))(*(_QWORD *)v24 + 32LL))(
            v24,
            0,
            v18,
            (unsigned int)v9,
            v36,
            0);
    if ( v25 < 0 )
    {
      v22 = LowRights::WzMsg::CreateResponse(a2, v25, 0);
      v26 = v35;
      if ( v35 )
      {
        v35 = 0;
        (*(void (__fastcall **)(struct IByteStream *))(*(_QWORD *)v26 + 16LL))(v26);
      }
      goto LABEL_19;
    }
    v27 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(struct IByteStream *))(*(_QWORD *)v27 + 16LL))(v27);
    }
    std::wstring::~wstring(v50);
    std::wstring::~wstring(&v45);
    std::unique_ptr<std::istream>::~unique_ptr<std::istream>(&v34);
    std::wstring::~wstring(&v41);
    v28 = (const wchar_t *)v43;
    if ( si128.m128i_i64[1] > 7uLL )
      v28 = v43[0];
    v29 = LowRights::WzMsg::CreateResponse(a2, 0, v28);
    std::wstring::~wstring(v43);
    result = v29;
  }
  catch ( const std::exception *v40 )
  {
    v30 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v40 + 8LL))(v40);
    v37 = (struct LowRights::WzMsg *)v30;
    v31 = -1;
    do
      ++v31;
    while ( *(_BYTE *)(v31 + v30) );
    v38 = v31;
    v32 = Mso::StringCore::TryUTF8ToWStr(v49, &v37);
    v45 = 0;
    *(_QWORD *)&v46 = 0;
    *((_QWORD *)&v46 + 1) = 7;
    LOWORD(v45) = 0;
    if ( *(_BYTE *)(v32 + 32) )
    {
      v41 = 0;
      v42 = 0u;
      v41 = *(_OWORD *)v32;
      v42 = *(_OWORD *)(v32 + 16);
      *(_QWORD *)(v32 + 16) = 0;
      *(_QWORD *)(v32 + 24) = 7;
      *(_WORD *)v32 = 0;
    }
    else
    {
      v41 = v45;
      v42 = v46;
      *(_QWORD *)&v46 = 0;
      *((_QWORD *)&v46 + 1) = 7;
      LOWORD(v45) = 0;
    }
    std::wstring::~wstring(&v45);
    std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v49);
    v33 = (const wchar_t *)&v41;
    if ( *((_QWORD *)&v42 + 1) > 7u )
      v33 = (const wchar_t *)v41;
    v37 = LowRights::WzMsg::CreateResponse(v39, 0x8000FFFF, v33);
    std::wstring::~wstring(&v41);
    goto LABEL_33;
  }
  catch ( ... )
  {
    v37 = LowRights::WzMsg::CreateResponse(v39, 0x8000FFFF, 0);
LABEL_33:
    std::wstring::~wstring(v43);
    return v37;
  }
  return result;
}

```

## disassembly

```asm
0x1802008c0  mov     r11, rsp
0x1802008c3  mov     [r11+18h], rbx
0x1802008c7  mov     [r11+20h], rsi
0x1802008cb  push    rdi
0x1802008cc  push    r14
0x1802008ce  push    r15
0x1802008d0  sub     rsp, 160h
0x1802008d7  mov     rax, cs:__security_cookie
0x1802008de  xor     rax, rsp
0x1802008e1  mov     [rsp+178h+var_20], rax
0x1802008e9  mov     rsi, rdx
0x1802008ec  mov     r14, rcx
0x1802008ef  mov     [rsp+178h+var_F8], rdx
0x1802008f7  xor     r15d, r15d
0x1802008fa  xorps   xmm0, xmm0
0x1802008fd  movups  xmmword ptr [rsp+178h+var_C8], xmm0
0x180200905  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18020090d  movdqu  [rsp+178h+var_B8], xmm1
0x180200916  mov     [r11-0C8h], r15w
0x18020091e  add     rdx, 10h
0x180200922  lea     rcx, [r11-68h]
0x180200926  call    ??$?0PEB_W$0A@@path@filesystem@std@@QEAA@AEBQEB_WW4format@012@@Z; std::filesystem::path::path(wchar_t const * const &,std::filesystem::path::format)
0x18020092b  lea     rdx, [rsp+178h+var_E8]
0x180200933  mov     rcx, rax
0x180200936  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x18020093b  lea     rcx, [rsp+178h+var_68]
0x180200943  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200948  lea     rdi, [rsp+178h+var_E8]
0x180200950  cmp     [rsp+178h+var_D0], 7
0x180200959  cmova   rdi, qword ptr [rsp+178h+var_E8]
0x180200962  mov     rbx, [rsp+178h+var_D8]
0x18020096a  call    __std_fs_code_page
0x18020096f  mov     [rsp+178h+var_118], rdi
0x180200974  mov     [rsp+178h+var_110], rbx
0x180200979  lea     r8, [rsp+178h+var_118]
0x18020097e  mov     edx, eax; CodePage
0x180200980  lea     rcx, [rsp+178h+Src]; Src
0x180200988  call    ??$_Convert_wide_to_narrow@U?$char_traits@D@std@@V?$allocator@D@2@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@W4__std_code_page@@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@AEBV?$allocator@D@0@@Z; std::_Convert_wide_to_narrow<std::char_traits<char>>(__std_code_page,std::wstring_view,std::allocator<char> const &)
0x18020098d  lea     r8, [rsp+178h+Src]
0x180200995  cmp     [rsp+178h+var_70], 0Fh
0x18020099e  cmova   r8, [rsp+178h+Src]
0x1802009a7  lea     rcx, [r14+20h]
0x1802009ab  lea     rdx, [rsp+178h+var_138]
0x1802009b0  call    ??R?$FunctorThrow@$$A6A?AV?$unique_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@@std@@PEBD@Z@Mso@@QEBA?AV?$unique_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@@std@@PEBD@Z; Mso::FunctorThrow<std::unique_ptr<std::istream> (char const *)>::operator()(char const *)
0x1802009b5  lea     rcx, [rsp+178h+Src]
0x1802009bd  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1802009c2  xor     edx, edx
0x1802009c4  lea     r8d, [r15+2]
0x1802009c8  mov     rcx, [rsp+178h+var_138]
0x1802009cd  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x1802009d3  lea     rdx, [rsp+178h+var_118]
0x1802009d8  mov     rcx, [rsp+178h+var_138]
0x1802009dd  call    cs:__imp_?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::istream::tellg(void)
0x1802009e3  mov     rbx, [rax+8]
0x1802009e7  add     rbx, [rax]
0x1802009ea  xor     r8d, r8d
0x1802009ed  xor     edx, edx
0x1802009ef  mov     rcx, [rsp+178h+var_138]
0x1802009f4  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x1802009fa  test    rbx, rbx
0x1802009fd  jnz     short loc_180200A3E
0x1802009ff  xor     r8d, r8d; wchar_t *
0x180200a02  mov     edx, 80070057h; unsigned int
0x180200a07  mov     rcx, rsi; struct LowRights::BaseMsg *
0x180200a0a  call    ?CreateResponse@WzMsg@LowRights@@SAPEAU12@AEBUBaseMsg@2@KPEB_W@Z; LowRights::WzMsg::CreateResponse(LowRights::BaseMsg const &,ulong,wchar_t const *)
0x180200a0f  mov     rbx, rax
0x180200a12  lea     rcx, [rsp+178h+var_138]
0x180200a17  call    ??1?$unique_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::istream>::~unique_ptr<std::istream>(void)
0x180200a1c  lea     rcx, [rsp+178h+var_E8]
0x180200a24  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200a29  lea     rcx, [rsp+178h+var_C8]
0x180200a31  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200a36  mov     rax, rbx
0x180200a39  jmp     loc_180200E0C
0x180200a3e  lea     rcx, [r14+8]
0x180200a42  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x180200a47  mov     r8, rax
0x180200a4a  mov     rcx, [rax]
0x180200a4d  mov     rax, [rcx+20h]
0x180200a51  lea     rdx, [rsp+178h+var_A8]
0x180200a59  mov     rcx, r8
0x180200a5c  call    cs:__guard_dispatch_icall_fptr
0x180200a62  lock inc dword ptr [r14+28h]
0x180200a67  mov     edx, [r14+28h]
0x180200a6b  lea     rcx, [rsp+178h+Src]
0x180200a73  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@I@Z; std::to_wstring(uint)
0x180200a78  mov     r8, rax
0x180200a7b  lea     rdx, aRequestedresou; "requestedresource"
0x180200a82  lea     rcx, [rsp+178h+var_68]
0x180200a8a  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_W$$QEAV10@@Z; std::operator+<wchar_t>(wchar_t const * const,std::wstring &&)
0x180200a8f  mov     rdx, rax
0x180200a92  lea     rcx, [rsp+178h+var_C8]
0x180200a9a  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180200a9f  lea     rcx, [rsp+178h+var_68]
0x180200aa7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200aac  lea     rcx, [rsp+178h+Src]
0x180200ab4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200ab9  lea     rax, [rsp+178h+var_C8]
0x180200ac1  cmp     qword ptr [rsp+178h+var_B8+8], 7
0x180200aca  cmova   rax, [rsp+178h+var_C8]
0x180200ad3  mov     [rsp+178h+var_118], rax
0x180200ad8  mov     rax, qword ptr [rsp+178h+var_B8]
0x180200ae0  mov     [rsp+178h+var_110], rax
0x180200ae5  lea     rdx, [rsp+178h+var_118]
0x180200aea  lea     rcx, [rsp+178h+Src]
0x180200af2  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180200af7  lea     rax, [rsp+178h+var_A8]
0x180200aff  cmp     [rsp+178h+var_90], 7
0x180200b08  cmova   rax, qword ptr [rsp+178h+var_A8]
0x180200b11  mov     [rsp+178h+var_118], rax
0x180200b16  lea     rdx, [rsp+178h+var_118]
0x180200b1b  lea     rcx, [rsp+178h+var_68]
0x180200b23  call    ??$?0PEB_W$0A@@path@filesystem@std@@QEAA@AEBQEB_WW4format@012@@Z; std::filesystem::path::path(wchar_t const * const &,std::filesystem::path::format)
0x180200b28  lea     r8, [rsp+178h+Src]
0x180200b30  mov     rdx, rax
0x180200b33  lea     rcx, [rsp+178h+var_40]; Src
0x180200b3b  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180200b40  lea     rcx, [rsp+178h+var_68]
0x180200b48  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200b4d  lea     rcx, [rsp+178h+Src]
0x180200b55  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200b5a  mov     rcx, rbx; Size
0x180200b5d  call    cs:__imp_malloc
0x180200b63  mov     rdi, rax
0x180200b66  test    rax, rax
0x180200b69  jnz     short loc_180200BC5
0x180200b6b  xor     r8d, r8d; wchar_t *
0x180200b6e  mov     edx, 8007000Eh; unsigned int
0x180200b73  mov     rcx, rsi; struct LowRights::BaseMsg *
0x180200b76  call    ?CreateResponse@WzMsg@LowRights@@SAPEAU12@AEBUBaseMsg@2@KPEB_W@Z; LowRights::WzMsg::CreateResponse(LowRights::BaseMsg const &,ulong,wchar_t const *)
0x180200b7b  mov     rbx, rax
0x180200b7e  lea     rcx, [rsp+178h+var_40]
0x180200b86  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200b8b  lea     rcx, [rsp+178h+var_A8]
0x180200b93  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200b98  lea     rcx, [rsp+178h+var_138]
0x180200b9d  call    ??1?$unique_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::istream>::~unique_ptr<std::istream>(void)
0x180200ba2  lea     rcx, [rsp+178h+var_E8]
0x180200baa  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200baf  nop
0x180200bb0  lea     rcx, [rsp+178h+var_C8]
0x180200bb8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200bbd  mov     rax, rbx
0x180200bc0  jmp     loc_180200E0C
0x180200bc5  mov     r8, rbx
0x180200bc8  mov     rdx, rdi
0x180200bcb  mov     rcx, [rsp+178h+var_138]
0x180200bd0  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x180200bd6  mov     [rsp+178h+var_130], r15
0x180200bdb  lea     rdx, [rsp+178h+var_40]
0x180200be3  lea     rcx, [rsp+178h+Src]
0x180200beb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180200bf0  lea     rcx, [rsp+178h+Src]
0x180200bf8  cmp     [rsp+178h+var_70], 7
0x180200c01  cmova   rcx, [rsp+178h+Src]
0x180200c0a  lea     r8, [rsp+178h+var_130]
0x180200c0f  mov     edx, 40002h
0x180200c14  call    cs:__imp_?MsoHrGetFileByteStream@@YAJPEB_WKPEAPEAUIByteStream@@@Z; MsoHrGetFileByteStream(wchar_t const *,ulong,IByteStream * *)
0x180200c1a  mov     r14d, eax
0x180200c1d  lea     rcx, [rsp+178h+Src]
0x180200c25  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200c2a  test    r14d, r14d
0x180200c2d  jns     short loc_180200CA8
0x180200c2f  xor     r8d, r8d; wchar_t *
0x180200c32  mov     edx, r14d; unsigned int
0x180200c35  mov     rcx, rsi; struct LowRights::BaseMsg *
0x180200c38  call    ?CreateResponse@WzMsg@LowRights@@SAPEAU12@AEBUBaseMsg@2@KPEB_W@Z; LowRights::WzMsg::CreateResponse(LowRights::BaseMsg const &,ulong,wchar_t const *)
0x180200c3d  mov     rbx, rax
0x180200c40  mov     rcx, [rsp+178h+var_130]
0x180200c45  test    rcx, rcx
0x180200c48  jz      short loc_180200C5D
0x180200c4a  mov     [rsp+178h+var_130], r15
0x180200c4f  mov     rdx, [rcx]
0x180200c52  mov     rax, [rdx+10h]
0x180200c56  call    cs:__guard_dispatch_icall_fptr
0x180200c5c  nop
0x180200c5d  lea     rcx, [rsp+178h+var_40]
0x180200c65  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200c6a  lea     rcx, [rsp+178h+var_A8]
0x180200c72  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200c77  lea     rcx, [rsp+178h+var_138]
0x180200c7c  call    ??1?$unique_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::istream>::~unique_ptr<std::istream>(void)
0x180200c81  lea     rcx, [rsp+178h+var_E8]
0x180200c89  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200c8e  lea     rcx, [rsp+178h+var_C8]
0x180200c96  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200c9b  nop     dword ptr [rax+rax+00h]
0x180200ca0  mov     rax, rbx
0x180200ca3  jmp     loc_180200E0C
0x180200ca8  mov     [rsp+178h+var_128], r15d
0x180200cad  mov     rcx, [rsp+178h+var_130]
0x180200cb2  test    rcx, rcx
0x180200cb5  jnz     short loc_180200CC5
0x180200cb7  xor     edx, edx
0x180200cb9  mov     ecx, 1E3C3840h
0x180200cbe  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180200cc4  nop
0x180200cc5  mov     rax, [rcx]
0x180200cc8  mov     edx, 0FFFFFFFFh
0x180200ccd  cmp     rbx, rdx
0x180200cd0  jbe     short loc_180200CD9
0x180200cd2  mov     ecx, 5
0x180200cd7  int     29h; Win8: RtlFailFast(ecx)
0x180200cd9  mov     [rsp+178h+var_150], r15
0x180200cde  lea     rdx, [rsp+178h+var_128]
0x180200ce3  mov     [rsp+178h+var_158], rdx
0x180200ce8  mov     r9d, ebx
0x180200ceb  mov     r8, rdi
0x180200cee  xor     edx, edx
0x180200cf0  mov     rax, [rax+20h]
0x180200cf4  call    cs:__guard_dispatch_icall_fptr
0x180200cfa  test    eax, eax
0x180200cfc  jns     short loc_180200D71
0x180200cfe  xor     r8d, r8d; wchar_t *
0x180200d01  mov     edx, eax; unsigned int
0x180200d03  mov     rcx, rsi; struct LowRights::BaseMsg *
0x180200d06  call    ?CreateResponse@WzMsg@LowRights@@SAPEAU12@AEBUBaseMsg@2@KPEB_W@Z; LowRights::WzMsg::CreateResponse(LowRights::BaseMsg const &,ulong,wchar_t const *)
0x180200d0b  mov     rbx, rax
0x180200d0e  mov     rcx, [rsp+178h+var_130]
0x180200d13  test    rcx, rcx
0x180200d16  jz      short loc_180200D2B
0x180200d18  mov     [rsp+178h+var_130], r15
0x180200d1d  mov     rdx, [rcx]
0x180200d20  mov     rax, [rdx+10h]
0x180200d24  call    cs:__guard_dispatch_icall_fptr
0x180200d2a  nop
0x180200d2b  lea     rcx, [rsp+178h+var_40]
0x180200d33  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200d38  lea     rcx, [rsp+178h+var_A8]
0x180200d40  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200d45  lea     rcx, [rsp+178h+var_138]
0x180200d4a  call    ??1?$unique_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::istream>::~unique_ptr<std::istream>(void)
0x180200d4f  lea     rcx, [rsp+178h+var_E8]
0x180200d57  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200d5c  lea     rcx, [rsp+178h+var_C8]
0x180200d64  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200d69  mov     rax, rbx
0x180200d6c  jmp     loc_180200E0C
0x180200d71  mov     rcx, [rsp+178h+var_130]
0x180200d76  test    rcx, rcx
0x180200d79  jz      short loc_180200D8E
0x180200d7b  mov     [rsp+178h+var_130], r15
0x180200d80  mov     rax, [rcx]
0x180200d83  mov     rax, [rax+10h]
0x180200d87  call    cs:__guard_dispatch_icall_fptr
0x180200d8d  nop
0x180200d8e  lea     rcx, [rsp+178h+var_40]
0x180200d96  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200d9b  lea     rcx, [rsp+178h+var_A8]
0x180200da3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200da8  lea     rcx, [rsp+178h+var_138]
0x180200dad  call    ??1?$unique_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::istream>::~unique_ptr<std::istream>(void)
0x180200db2  lea     rcx, [rsp+178h+var_E8]
0x180200dba  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200dbf  lea     r8, [rsp+178h+var_C8]
0x180200dc7  cmp     qword ptr [rsp+178h+var_B8+8], 7
0x180200dd0  cmova   r8, [rsp+178h+var_C8]; wchar_t *
0x180200dd9  xor     edx, edx; unsigned int
0x180200ddb  mov     rcx, rsi; struct LowRights::BaseMsg *
0x180200dde  call    ?CreateResponse@WzMsg@LowRights@@SAPEAU12@AEBUBaseMsg@2@KPEB_W@Z; LowRights::WzMsg::CreateResponse(LowRights::BaseMsg const &,ulong,wchar_t const *)
0x180200de3  mov     rbx, rax
0x180200de6  lea     rcx, [rsp+178h+var_C8]
0x180200dee  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200df3  mov     rax, rbx
0x180200df6  jmp     short loc_180200E0C
0x180200df8  jmp     short $+2
0x180200dfa  lea     rcx, [rsp+178h+var_C8]
0x180200e02  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200e07  mov     rax, [rsp+178h+var_118]
0x180200e0c  mov     rcx, [rsp+178h+var_20]
0x180200e14  xor     rcx, rsp; StackCookie
0x180200e17  call    __security_check_cookie
0x180200e1c  lea     r11, [rsp+178h+var_18]
0x180200e24  mov     rbx, [r11+30h]
0x180200e28  mov     rsi, [r11+38h]
0x180200e2c  mov     rsp, r11
0x180200e2f  pop     r15
0x180200e31  pop     r14
0x180200e33  pop     rdi
0x180200e34  retn
```
