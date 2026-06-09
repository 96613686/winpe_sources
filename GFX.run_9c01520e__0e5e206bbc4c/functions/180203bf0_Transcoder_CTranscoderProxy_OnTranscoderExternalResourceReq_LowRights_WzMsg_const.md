# Transcoder::CTranscoderProxy::OnTranscoderExternalResourceReq(LowRights::WzMsg const &)

- ea: `0x180203bf0`
- end: `0x180204165`
- name: `?OnTranscoderExternalResourceReq@CTranscoderProxy@Transcoder@@AEAAPEAUWzMsg@LowRights@@AEBU34@@Z`
- size: `1397`
- prototype: `struct LowRights::WzMsg *(Transcoder::CTranscoderProxy *__hidden this, const struct LowRights::WzMsg *)`
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x180203b80`

## callees

- `0x18000c29c`
- `0x1800578b0`
- `0x180057e70`
- `0x180072d00`
- `0x180077780`
- `0x1800abc9c`
- `0x18014508c`
- `0x180159780`
- `0x18017f970`
- `0x1801815d0`
- `0x1801878b8`
- `0x1801d78fc`
- `0x1801e4820`
- `0x180202ab0`
- `0x180202d38`
- `0x180203410`
- `0x18020356c`
- `0x180203bf0`
- `0x180204368`

## import_xrefs

- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x180203f00`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x180203f00`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x180203cfd`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x180203d24`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x180203cfd`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x180203d24`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x180203d0d`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x180203d0d`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180203e8d`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180203e8d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180203fee`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180203fee`
- `Mso20Win32Client!__imp_?MsoHrGetFileByteStream@@YAJPEB_WKPEAPEAUIByteStream@@@Z` at `0x180203f44`
- `Mso20Win32Client!__imp_?MsoHrGetFileByteStream@@YAJPEB_WKPEAPEAUIByteStream@@@Z` at `0x180203f44`

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
0x180203bf0  mov     r11, rsp
0x180203bf3  mov     [r11+18h], rbx
0x180203bf7  mov     [r11+20h], rsi
0x180203bfb  push    rdi
0x180203bfc  push    r14
0x180203bfe  push    r15
0x180203c00  sub     rsp, 160h
0x180203c07  mov     rax, cs:__security_cookie
0x180203c0e  xor     rax, rsp
0x180203c11  mov     [rsp+178h+var_20], rax
0x180203c19  mov     rsi, rdx
0x180203c1c  mov     r14, rcx
0x180203c1f  mov     [rsp+178h+var_F8], rdx
0x180203c27  xor     r15d, r15d
0x180203c2a  xorps   xmm0, xmm0
0x180203c2d  movups  xmmword ptr [rsp+178h+var_C8], xmm0
0x180203c35  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180203c3d  movdqu  [rsp+178h+var_B8], xmm1
0x180203c46  mov     [r11-0C8h], r15w
0x180203c4e  add     rdx, 10h
0x180203c52  lea     rcx, [r11-68h]
0x180203c56  call    ??$?0PEB_W$0A@@path@filesystem@std@@QEAA@AEBQEB_WW4format@012@@Z; std::filesystem::path::path(wchar_t const * const &,std::filesystem::path::format)
0x180203c5b  lea     rdx, [rsp+178h+var_E8]
0x180203c63  mov     rcx, rax
0x180203c66  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x180203c6b  lea     rcx, [rsp+178h+var_68]
0x180203c73  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203c78  lea     rdi, [rsp+178h+var_E8]
0x180203c80  cmp     [rsp+178h+var_D0], 7
0x180203c89  cmova   rdi, qword ptr [rsp+178h+var_E8]
0x180203c92  mov     rbx, [rsp+178h+var_D8]
0x180203c9a  call    __std_fs_code_page
0x180203c9f  mov     [rsp+178h+var_118], rdi
0x180203ca4  mov     [rsp+178h+var_110], rbx
0x180203ca9  lea     r8, [rsp+178h+var_118]
0x180203cae  mov     edx, eax; CodePage
0x180203cb0  lea     rcx, [rsp+178h+Src]; Src
0x180203cb8  call    ??$_Convert_wide_to_narrow@U?$char_traits@D@std@@V?$allocator@D@2@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@W4__std_code_page@@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@AEBV?$allocator@D@0@@Z; std::_Convert_wide_to_narrow<std::char_traits<char>>(__std_code_page,std::wstring_view,std::allocator<char> const &)
0x180203cbd  lea     r8, [rsp+178h+Src]
0x180203cc5  cmp     [rsp+178h+var_70], 0Fh
0x180203cce  cmova   r8, [rsp+178h+Src]
0x180203cd7  lea     rcx, [r14+20h]
0x180203cdb  lea     rdx, [rsp+178h+var_138]
0x180203ce0  call    ??R?$FunctorThrow@$$A6A?AV?$unique_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@@std@@PEBD@Z@Mso@@QEBA?AV?$unique_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@@std@@PEBD@Z; Mso::FunctorThrow<std::unique_ptr<std::istream> (char const *)>::operator()(char const *)
0x180203ce5  lea     rcx, [rsp+178h+Src]
0x180203ced  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180203cf2  xor     edx, edx
0x180203cf4  lea     r8d, [r15+2]
0x180203cf8  mov     rcx, [rsp+178h+var_138]
0x180203cfd  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x180203d03  lea     rdx, [rsp+178h+var_118]
0x180203d08  mov     rcx, [rsp+178h+var_138]
0x180203d0d  call    cs:__imp_?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::istream::tellg(void)
0x180203d13  mov     rbx, [rax+8]
0x180203d17  add     rbx, [rax]
0x180203d1a  xor     r8d, r8d
0x180203d1d  xor     edx, edx
0x180203d1f  mov     rcx, [rsp+178h+var_138]
0x180203d24  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x180203d2a  test    rbx, rbx
0x180203d2d  jnz     short loc_180203D6E
0x180203d2f  xor     r8d, r8d; wchar_t *
0x180203d32  mov     edx, 80070057h; unsigned int
0x180203d37  mov     rcx, rsi; struct LowRights::BaseMsg *
0x180203d3a  call    ?CreateResponse@WzMsg@LowRights@@SAPEAU12@AEBUBaseMsg@2@KPEB_W@Z; LowRights::WzMsg::CreateResponse(LowRights::BaseMsg const &,ulong,wchar_t const *)
0x180203d3f  mov     rbx, rax
0x180203d42  lea     rcx, [rsp+178h+var_138]
0x180203d47  call    ??1?$unique_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::istream>::~unique_ptr<std::istream>(void)
0x180203d4c  lea     rcx, [rsp+178h+var_E8]
0x180203d54  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203d59  lea     rcx, [rsp+178h+var_C8]
0x180203d61  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203d66  mov     rax, rbx
0x180203d69  jmp     loc_18020413C
0x180203d6e  lea     rcx, [r14+8]
0x180203d72  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x180203d77  mov     r8, rax
0x180203d7a  mov     rcx, [rax]
0x180203d7d  mov     rax, [rcx+20h]
0x180203d81  lea     rdx, [rsp+178h+var_A8]
0x180203d89  mov     rcx, r8
0x180203d8c  call    cs:__guard_dispatch_icall_fptr
0x180203d92  lock inc dword ptr [r14+28h]
0x180203d97  mov     edx, [r14+28h]
0x180203d9b  lea     rcx, [rsp+178h+Src]
0x180203da3  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@I@Z; std::to_wstring(uint)
0x180203da8  mov     r8, rax
0x180203dab  lea     rdx, aRequestedresou; "requestedresource"
0x180203db2  lea     rcx, [rsp+178h+var_68]
0x180203dba  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_W$$QEAV10@@Z; std::operator+<wchar_t>(wchar_t const * const,std::wstring &&)
0x180203dbf  mov     rdx, rax
0x180203dc2  lea     rcx, [rsp+178h+var_C8]
0x180203dca  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180203dcf  lea     rcx, [rsp+178h+var_68]
0x180203dd7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203ddc  lea     rcx, [rsp+178h+Src]
0x180203de4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203de9  lea     rax, [rsp+178h+var_C8]
0x180203df1  cmp     qword ptr [rsp+178h+var_B8+8], 7
0x180203dfa  cmova   rax, [rsp+178h+var_C8]
0x180203e03  mov     [rsp+178h+var_118], rax
0x180203e08  mov     rax, qword ptr [rsp+178h+var_B8]
0x180203e10  mov     [rsp+178h+var_110], rax
0x180203e15  lea     rdx, [rsp+178h+var_118]
0x180203e1a  lea     rcx, [rsp+178h+Src]
0x180203e22  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180203e27  lea     rax, [rsp+178h+var_A8]
0x180203e2f  cmp     [rsp+178h+var_90], 7
0x180203e38  cmova   rax, qword ptr [rsp+178h+var_A8]
0x180203e41  mov     [rsp+178h+var_118], rax
0x180203e46  lea     rdx, [rsp+178h+var_118]
0x180203e4b  lea     rcx, [rsp+178h+var_68]
0x180203e53  call    ??$?0PEB_W$0A@@path@filesystem@std@@QEAA@AEBQEB_WW4format@012@@Z; std::filesystem::path::path(wchar_t const * const &,std::filesystem::path::format)
0x180203e58  lea     r8, [rsp+178h+Src]
0x180203e60  mov     rdx, rax
0x180203e63  lea     rcx, [rsp+178h+var_40]; Src
0x180203e6b  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180203e70  lea     rcx, [rsp+178h+var_68]
0x180203e78  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203e7d  lea     rcx, [rsp+178h+Src]
0x180203e85  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203e8a  mov     rcx, rbx; Size
0x180203e8d  call    cs:__imp_malloc
0x180203e93  mov     rdi, rax
0x180203e96  test    rax, rax
0x180203e99  jnz     short loc_180203EF5
0x180203e9b  xor     r8d, r8d; wchar_t *
0x180203e9e  mov     edx, 8007000Eh; unsigned int
0x180203ea3  mov     rcx, rsi; struct LowRights::BaseMsg *
0x180203ea6  call    ?CreateResponse@WzMsg@LowRights@@SAPEAU12@AEBUBaseMsg@2@KPEB_W@Z; LowRights::WzMsg::CreateResponse(LowRights::BaseMsg const &,ulong,wchar_t const *)
0x180203eab  mov     rbx, rax
0x180203eae  lea     rcx, [rsp+178h+var_40]
0x180203eb6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203ebb  lea     rcx, [rsp+178h+var_A8]
0x180203ec3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203ec8  lea     rcx, [rsp+178h+var_138]
0x180203ecd  call    ??1?$unique_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::istream>::~unique_ptr<std::istream>(void)
0x180203ed2  lea     rcx, [rsp+178h+var_E8]
0x180203eda  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203edf  nop
0x180203ee0  lea     rcx, [rsp+178h+var_C8]
0x180203ee8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203eed  mov     rax, rbx
0x180203ef0  jmp     loc_18020413C
0x180203ef5  mov     r8, rbx
0x180203ef8  mov     rdx, rdi
0x180203efb  mov     rcx, [rsp+178h+var_138]
0x180203f00  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x180203f06  mov     [rsp+178h+var_130], r15
0x180203f0b  lea     rdx, [rsp+178h+var_40]
0x180203f13  lea     rcx, [rsp+178h+Src]
0x180203f1b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180203f20  lea     rcx, [rsp+178h+Src]
0x180203f28  cmp     [rsp+178h+var_70], 7
0x180203f31  cmova   rcx, [rsp+178h+Src]
0x180203f3a  lea     r8, [rsp+178h+var_130]
0x180203f3f  mov     edx, 40002h
0x180203f44  call    cs:__imp_?MsoHrGetFileByteStream@@YAJPEB_WKPEAPEAUIByteStream@@@Z; MsoHrGetFileByteStream(wchar_t const *,ulong,IByteStream * *)
0x180203f4a  mov     r14d, eax
0x180203f4d  lea     rcx, [rsp+178h+Src]
0x180203f55  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203f5a  test    r14d, r14d
0x180203f5d  jns     short loc_180203FD8
0x180203f5f  xor     r8d, r8d; wchar_t *
0x180203f62  mov     edx, r14d; unsigned int
0x180203f65  mov     rcx, rsi; struct LowRights::BaseMsg *
0x180203f68  call    ?CreateResponse@WzMsg@LowRights@@SAPEAU12@AEBUBaseMsg@2@KPEB_W@Z; LowRights::WzMsg::CreateResponse(LowRights::BaseMsg const &,ulong,wchar_t const *)
0x180203f6d  mov     rbx, rax
0x180203f70  mov     rcx, [rsp+178h+var_130]
0x180203f75  test    rcx, rcx
0x180203f78  jz      short loc_180203F8D
0x180203f7a  mov     [rsp+178h+var_130], r15
0x180203f7f  mov     rdx, [rcx]
0x180203f82  mov     rax, [rdx+10h]
0x180203f86  call    cs:__guard_dispatch_icall_fptr
0x180203f8c  nop
0x180203f8d  lea     rcx, [rsp+178h+var_40]
0x180203f95  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203f9a  lea     rcx, [rsp+178h+var_A8]
0x180203fa2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203fa7  lea     rcx, [rsp+178h+var_138]
0x180203fac  call    ??1?$unique_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::istream>::~unique_ptr<std::istream>(void)
0x180203fb1  lea     rcx, [rsp+178h+var_E8]
0x180203fb9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203fbe  lea     rcx, [rsp+178h+var_C8]
0x180203fc6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203fcb  nop     dword ptr [rax+rax+00h]
0x180203fd0  mov     rax, rbx
0x180203fd3  jmp     loc_18020413C
0x180203fd8  mov     [rsp+178h+var_128], r15d
0x180203fdd  mov     rcx, [rsp+178h+var_130]
0x180203fe2  test    rcx, rcx
0x180203fe5  jnz     short loc_180203FF5
0x180203fe7  xor     edx, edx
0x180203fe9  mov     ecx, 1E3C3840h
0x180203fee  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180203ff4  nop
0x180203ff5  mov     rax, [rcx]
0x180203ff8  mov     edx, 0FFFFFFFFh
0x180203ffd  cmp     rbx, rdx
0x180204000  jbe     short loc_180204009
0x180204002  mov     ecx, 5
0x180204007  int     29h; Win8: RtlFailFast(ecx)
0x180204009  mov     [rsp+178h+var_150], r15
0x18020400e  lea     rdx, [rsp+178h+var_128]
0x180204013  mov     [rsp+178h+var_158], rdx
0x180204018  mov     r9d, ebx
0x18020401b  mov     r8, rdi
0x18020401e  xor     edx, edx
0x180204020  mov     rax, [rax+20h]
0x180204024  call    cs:__guard_dispatch_icall_fptr
0x18020402a  test    eax, eax
0x18020402c  jns     short loc_1802040A1
0x18020402e  xor     r8d, r8d; wchar_t *
0x180204031  mov     edx, eax; unsigned int
0x180204033  mov     rcx, rsi; struct LowRights::BaseMsg *
0x180204036  call    ?CreateResponse@WzMsg@LowRights@@SAPEAU12@AEBUBaseMsg@2@KPEB_W@Z; LowRights::WzMsg::CreateResponse(LowRights::BaseMsg const &,ulong,wchar_t const *)
0x18020403b  mov     rbx, rax
0x18020403e  mov     rcx, [rsp+178h+var_130]
0x180204043  test    rcx, rcx
0x180204046  jz      short loc_18020405B
0x180204048  mov     [rsp+178h+var_130], r15
0x18020404d  mov     rdx, [rcx]
0x180204050  mov     rax, [rdx+10h]
0x180204054  call    cs:__guard_dispatch_icall_fptr
0x18020405a  nop
0x18020405b  lea     rcx, [rsp+178h+var_40]
0x180204063  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180204068  lea     rcx, [rsp+178h+var_A8]
0x180204070  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180204075  lea     rcx, [rsp+178h+var_138]
0x18020407a  call    ??1?$unique_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::istream>::~unique_ptr<std::istream>(void)
0x18020407f  lea     rcx, [rsp+178h+var_E8]
0x180204087  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18020408c  lea     rcx, [rsp+178h+var_C8]
0x180204094  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180204099  mov     rax, rbx
0x18020409c  jmp     loc_18020413C
0x1802040a1  mov     rcx, [rsp+178h+var_130]
0x1802040a6  test    rcx, rcx
0x1802040a9  jz      short loc_1802040BE
0x1802040ab  mov     [rsp+178h+var_130], r15
0x1802040b0  mov     rax, [rcx]
0x1802040b3  mov     rax, [rax+10h]
0x1802040b7  call    cs:__guard_dispatch_icall_fptr
0x1802040bd  nop
0x1802040be  lea     rcx, [rsp+178h+var_40]
0x1802040c6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1802040cb  lea     rcx, [rsp+178h+var_A8]
0x1802040d3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1802040d8  lea     rcx, [rsp+178h+var_138]
0x1802040dd  call    ??1?$unique_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::istream>::~unique_ptr<std::istream>(void)
0x1802040e2  lea     rcx, [rsp+178h+var_E8]
0x1802040ea  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1802040ef  lea     r8, [rsp+178h+var_C8]
0x1802040f7  cmp     qword ptr [rsp+178h+var_B8+8], 7
0x180204100  cmova   r8, [rsp+178h+var_C8]; wchar_t *
0x180204109  xor     edx, edx; unsigned int
0x18020410b  mov     rcx, rsi; struct LowRights::BaseMsg *
0x18020410e  call    ?CreateResponse@WzMsg@LowRights@@SAPEAU12@AEBUBaseMsg@2@KPEB_W@Z; LowRights::WzMsg::CreateResponse(LowRights::BaseMsg const &,ulong,wchar_t const *)
0x180204113  mov     rbx, rax
0x180204116  lea     rcx, [rsp+178h+var_C8]
0x18020411e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180204123  mov     rax, rbx
0x180204126  jmp     short loc_18020413C
0x180204128  jmp     short $+2
0x18020412a  lea     rcx, [rsp+178h+var_C8]
0x180204132  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180204137  mov     rax, [rsp+178h+var_118]
0x18020413c  mov     rcx, [rsp+178h+var_20]
0x180204144  xor     rcx, rsp; StackCookie
0x180204147  call    __security_check_cookie
0x18020414c  lea     r11, [rsp+178h+var_18]
0x180204154  mov     rbx, [r11+30h]
0x180204158  mov     rsi, [r11+38h]
0x18020415c  mov     rsp, r11
0x18020415f  pop     r15
0x180204161  pop     r14
0x180204163  pop     rdi
0x180204164  retn
```
