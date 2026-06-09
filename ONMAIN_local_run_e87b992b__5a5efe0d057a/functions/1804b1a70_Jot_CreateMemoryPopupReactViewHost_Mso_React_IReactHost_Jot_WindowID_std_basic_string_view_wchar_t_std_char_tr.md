# Jot::CreateMemoryPopupReactViewHost(Mso::React::IReactHost &,Jot::WindowID,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,Jot::MemoryWindowPerfMarkers const &,Jot::MemoryWindowLaunchSource)

- ea: `0x1804b1a70`
- end: `0x1804b1e4a`
- name: `?CreateMemoryPopupReactViewHost@Jot@@YA?AV?$TCntPtr@UIReactViewHost@React@Mso@@@Mso@@AEAUIReactHost@React@3@VWindowID@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBUMemoryWindowPerfMarkers@1@W4MemoryWindowLaunchSource@1@@Z`
- size: `986`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config`

## callees

- `0x18005ce78`
- `0x18006eaec`
- `0x180164b00`
- `0x180168334`
- `0x1802e2200`
- `0x1802e50d0`
- `0x1802e5170`
- `0x1802e5190`
- `0x180356d5c`
- `0x180358f00`
- `0x1804b1924`
- `0x1804b1a70`
- `0x1804b1e50`

## import_xrefs

- `MSVCP140!_Xtime_get_ticks` at `0x1804b1aaf`
- `MSVCP140!_Xtime_get_ticks` at `0x1804b1aaf`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1804b1c9b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1804b1d8b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1804b1df6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1804b1c9b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1804b1d8b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1804b1df6`
- `Mso20Win32Client!__imp_?WriteObjectEnd@JsonWriter@JSHost@Mso@@QEAAXXZ` at `0x1804b1bbe`
- `Mso20Win32Client!__imp_?WriteObjectEnd@JsonWriter@JSHost@Mso@@QEAAXXZ` at `0x1804b1bbe`
- `Mso20Win32Client!__imp_??0JsonWriter@JSHost@Mso@@QEAA@XZ` at `0x1804b1abf`
- `Mso20Win32Client!__imp_??0JsonWriter@JSHost@Mso@@QEAA@XZ` at `0x1804b1abf`
- `Mso20Win32Client!__imp_?WriteRekaObject@JSHost@Mso@@YAXAEAUIRekaWriter@12@PEB_W@Z` at `0x1804b1afe`
- `Mso20Win32Client!__imp_?WriteRekaObject@JSHost@Mso@@YAXAEAUIRekaWriter@12@PEB_W@Z` at `0x1804b1b5f`
- `Mso20Win32Client!__imp_?WriteRekaObject@JSHost@Mso@@YAXAEAUIRekaWriter@12@PEB_W@Z` at `0x1804b1afe`
- `Mso20Win32Client!__imp_?WriteRekaObject@JSHost@Mso@@YAXAEAUIRekaWriter@12@PEB_W@Z` at `0x1804b1b5f`
- `Mso20Win32Client!__imp_?WriteObjectStart@JsonWriter@JSHost@Mso@@QEAAXXZ` at `0x1804b1aca`
- `Mso20Win32Client!__imp_?WriteObjectStart@JsonWriter@JSHost@Mso@@QEAAXXZ` at `0x1804b1aca`
- `Mso20Win32Client!__imp_?ToWString@JsonWriter@JSHost@Mso@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ` at `0x1804b1bcd`
- `Mso20Win32Client!__imp_?ToWString@JsonWriter@JSHost@Mso@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ` at `0x1804b1bcd`
- `Mso20Win32Client!__imp_?WritePropertyName@JsonWriter@JSHost@Mso@@QEAAXPEB_W@Z` at `0x1804b1ba1`
- `Mso20Win32Client!__imp_?WritePropertyName@JsonWriter@JSHost@Mso@@QEAAXPEB_W@Z` at `0x1804b1ba1`
- `Mso20Win32Client!__imp_?WriteRekaObject@JSHost@Mso@@YAXAEAUIRekaWriter@12@I@Z` at `0x1804b1b2f`
- `Mso20Win32Client!__imp_?WriteRekaObject@JSHost@Mso@@YAXAEAUIRekaWriter@12@I@Z` at `0x1804b1b8f`
- `Mso20Win32Client!__imp_?WriteRekaObject@JSHost@Mso@@YAXAEAUIRekaWriter@12@I@Z` at `0x1804b1b2f`
- `Mso20Win32Client!__imp_?WriteRekaObject@JSHost@Mso@@YAXAEAUIRekaWriter@12@I@Z` at `0x1804b1b8f`

## pseudocode

```c
unsigned __int64 __fastcall Jot::CreateMemoryPopupReactViewHost(
        unsigned __int64 a1,
        __int64 a2,
        _DWORD *a3,
        struct Mso::JSHost::IRekaWriter **a4,
        __int64 a5,
        unsigned int a6)
{
  Mso::JSHost *v10; // rax
  Mso::JSHost *v11; // rbx
  const wchar_t *v12; // r8
  Mso::JSHost *v13; // rax
  Mso::JSHost *v14; // rbx
  unsigned int v15; // r8d
  Mso::JSHost *v16; // rax
  Mso::JSHost *v17; // rbx
  const wchar_t *v18; // r8
  Mso::JSHost *v19; // rax
  Mso::JSHost *v20; // rbx
  unsigned int v21; // r8d
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  void *v25; // rcx
  __m128i si128; // xmm1
  __int128 *v27; // rax
  __int64 v28; // rax
  void *v29; // rcx
  void *v30; // rcx
  __int64 v31; // rcx
  __int64 v33; // [rsp+20h] [rbp-C9h] BYREF
  void *Block; // [rsp+28h] [rbp-C1h] BYREF
  unsigned __int64 v35[2]; // [rsp+30h] [rbp-B9h] BYREF
  __int128 v36; // [rsp+40h] [rbp-A9h] BYREF
  __int128 v37; // [rsp+50h] [rbp-99h]
  __int128 Src; // [rsp+60h] [rbp-89h] BYREF
  __m128i v39; // [rsp+70h] [rbp-79h]
  __int128 v40; // [rsp+80h] [rbp-69h] BYREF
  __int64 v41; // [rsp+90h] [rbp-59h]
  __int64 v42; // [rsp+98h] [rbp-51h]
  _OWORD v43[2]; // [rsp+A0h] [rbp-49h] BYREF
  _QWORD v44[3]; // [rsp+C0h] [rbp-29h] BYREF
  unsigned __int64 v45; // [rsp+D8h] [rbp-11h]

  v35[0] = a1;
  Block = (void *)_Xtime_get_ticks();
  Mso::JSHost::JsonWriter::JsonWriter((Mso::JSHost::JsonWriter *)&v33);
  Mso::JSHost::JsonWriter::WriteObjectStart((Mso::JSHost::JsonWriter *)&v33);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v33);
  v11 = v10;
  (*(void (__fastcall **)(Mso::JSHost *, const wchar_t *))(*(_QWORD *)v10 + 40LL))(v10, L"windowKind");
  Mso::JSHost::WriteRekaObject(v11, (struct Mso::JSHost::IRekaWriter *)L"MemoryPopup", v12);
  LODWORD(a3) = *a3;
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v33);
  v14 = v13;
  (*(void (__fastcall **)(Mso::JSHost *, const wchar_t *))(*(_QWORD *)v13 + 40LL))(v13, L"windowId");
  Mso::JSHost::WriteRekaObject(v14, (struct Mso::JSHost::IRekaWriter *)(unsigned int)a3, v15);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v33);
  v17 = v16;
  (*(void (__fastcall **)(Mso::JSHost *, const wchar_t *))(*(_QWORD *)v16 + 40LL))(v16, L"noteId");
  Mso::JSHost::WriteRekaObject(v17, *a4, v18);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v33);
  v20 = v19;
  (*(void (__fastcall **)(Mso::JSHost *, const wchar_t *))(*(_QWORD *)v19 + 40LL))(v19, L"entryPoint");
  Mso::JSHost::WriteRekaObject(v20, (struct Mso::JSHost::IRekaWriter *)a6, v21);
  Mso::JSHost::JsonWriter::WritePropertyName((Mso::JSHost::JsonWriter *)&v33, L"perfMetrics");
  sub_1804B1924(&v33, a5, &Block);
  Mso::JSHost::JsonWriter::WriteObjectEnd((Mso::JSHost::JsonWriter *)&v33);
  v22 = Mso::JSHost::JsonWriter::ToWString(&v33, v44);
  v23 = std::wstring::insert(v22, 0, L"{\"hostContext\": ", 16);
  Src = 0;
  v39 = 0;
  Src = *(_OWORD *)v23;
  v39 = *(__m128i *)(v23 + 16);
  *(_QWORD *)(v23 + 24) = 7;
  *(_WORD *)v23 = 0;
  *(_QWORD *)(v23 + 16) = 0;
  v24 = std::wstring::append(&Src, (void *)L"}");
  v36 = 0;
  v37 = 0u;
  v36 = *(_OWORD *)v24;
  v37 = *(_OWORD *)(v24 + 16);
  *(_WORD *)v24 = 0;
  *(_QWORD *)(v24 + 16) = 0;
  *(_QWORD *)(v24 + 24) = 7;
  if ( v39.m128i_i64[1] > 7uLL )
  {
    v35[0] = 2 * v39.m128i_i64[1] + 2;
    v25 = (void *)Src;
    Block = (void *)Src;
    if ( v35[0] >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&Block, v35);
      v25 = Block;
    }
    free(v25);
  }
  *(_QWORD *)&Src = 19937;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v39 = si128;
  if ( v45 > 7 )
  {
    std::_Deallocate<16>(v44[0], 2 * v45 + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
  }
  v40 = 0;
  v42 = 15;
  LOBYTE(v40) = 0;
  v43[0] = 0;
  v43[1] = si128;
  LOBYTE(v43[0]) = 0;
  v41 = 14;
  memmove_0(&v40, "sdx_memory.app", 0xEu);
  BYTE14(v40) = 0;
  v27 = &v36;
  if ( *((_QWORD *)&v37 + 1) > 7u )
    v27 = (__int128 *)v36;
  *(_QWORD *)&Src = v27;
  *((_QWORD *)&Src + 1) = v37;
  v28 = Mso::StringCore::WStrToUTF8(v44, &Src);
  std::string::operator=(v43, v28);
  if ( v45 > 0xF )
  {
    v35[0] = v45 + 1;
    v29 = (void *)v44[0];
    Block = (void *)v44[0];
    if ( v45 + 1 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&Block, v35);
      v29 = Block;
    }
    free(v29);
  }
  (*(void (__fastcall **)(__int64, unsigned __int64, __int128 *))(*(_QWORD *)a2 + 80LL))(a2, a1, &v40);
  std::string::~string(v43);
  std::string::~string(&v40);
  if ( *((_QWORD *)&v37 + 1) > 7u )
  {
    v35[0] = 2LL * *((_QWORD *)&v37 + 1) + 2;
    v30 = (void *)v36;
    Block = (void *)v36;
    if ( v35[0] >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&Block, v35);
      v30 = Block;
    }
    free(v30);
  }
  *(_QWORD *)&v36 = 19937;
  *(_QWORD *)&v37 = 0;
  *((_QWORD *)&v37 + 1) = 15;
  v31 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  return a1;
}

```

## disassembly

```asm
0x1804b1a70  push    rbp
0x1804b1a72  push    rbx
0x1804b1a73  push    rsi
0x1804b1a74  push    rdi
0x1804b1a75  push    r12
0x1804b1a77  push    r13
0x1804b1a79  push    r14
0x1804b1a7b  push    r15
0x1804b1a7d  lea     rbp, [rsp-0Fh]
0x1804b1a82  sub     rsp, 0F8h
0x1804b1a89  mov     rax, cs:__security_cookie
0x1804b1a90  xor     rax, rsp
0x1804b1a93  mov     [rbp+47h+var_50], rax
0x1804b1a97  mov     rsi, r9
0x1804b1a9a  mov     rdi, r8
0x1804b1a9d  mov     r12, rdx
0x1804b1aa0  mov     r15, rcx
0x1804b1aa3  mov     [rsp+130h+var_100], rcx
0x1804b1aa8  mov     r14, [rbp+47h+arg_20]
0x1804b1aac  xor     r13d, r13d
0x1804b1aaf  call    cs:__imp__Xtime_get_ticks
0x1804b1ab5  mov     [rsp+130h+Block], rax
0x1804b1aba  lea     rcx, [rsp+130h+var_110]
0x1804b1abf  call    cs:__imp_??0JsonWriter@JSHost@Mso@@QEAA@XZ; Mso::JSHost::JsonWriter::JsonWriter(void)
0x1804b1ac5  lea     rcx, [rsp+130h+var_110]
0x1804b1aca  call    cs:__imp_?WriteObjectStart@JsonWriter@JSHost@Mso@@QEAAXXZ; Mso::JSHost::JsonWriter::WriteObjectStart(void)
0x1804b1ad0  lea     rcx, [rsp+130h+var_110]
0x1804b1ad5  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x1804b1ada  mov     rbx, rax
0x1804b1add  mov     rax, [rax]
0x1804b1ae0  lea     rdx, aWindowkind; "windowKind"
0x1804b1ae7  mov     rcx, rbx
0x1804b1aea  mov     rax, [rax+28h]
0x1804b1aee  call    cs:__guard_dispatch_icall_fptr
0x1804b1af4  lea     rdx, aMemorypopup; "MemoryPopup"
0x1804b1afb  mov     rcx, rbx
0x1804b1afe  call    cs:__imp_?WriteRekaObject@JSHost@Mso@@YAXAEAUIRekaWriter@12@PEB_W@Z; Mso::JSHost::WriteRekaObject(Mso::JSHost::IRekaWriter &,wchar_t const *)
0x1804b1b04  mov     edi, [rdi]
0x1804b1b06  lea     rcx, [rsp+130h+var_110]
0x1804b1b0b  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x1804b1b10  mov     rbx, rax
0x1804b1b13  mov     rax, [rax]
0x1804b1b16  lea     rdx, aWindowid_0; "windowId"
0x1804b1b1d  mov     rcx, rbx
0x1804b1b20  mov     rax, [rax+28h]
0x1804b1b24  call    cs:__guard_dispatch_icall_fptr
0x1804b1b2a  mov     edx, edi
0x1804b1b2c  mov     rcx, rbx
0x1804b1b2f  call    cs:__imp_?WriteRekaObject@JSHost@Mso@@YAXAEAUIRekaWriter@12@I@Z; Mso::JSHost::WriteRekaObject(Mso::JSHost::IRekaWriter &,uint)
0x1804b1b35  lea     rcx, [rsp+130h+var_110]
0x1804b1b3a  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x1804b1b3f  mov     rbx, rax
0x1804b1b42  mov     rax, [rax]
0x1804b1b45  lea     rdx, aNoteid; "noteId"
0x1804b1b4c  mov     rcx, rbx
0x1804b1b4f  mov     rax, [rax+28h]
0x1804b1b53  call    cs:__guard_dispatch_icall_fptr
0x1804b1b59  mov     rdx, [rsi]
0x1804b1b5c  mov     rcx, rbx
0x1804b1b5f  call    cs:__imp_?WriteRekaObject@JSHost@Mso@@YAXAEAUIRekaWriter@12@PEB_W@Z; Mso::JSHost::WriteRekaObject(Mso::JSHost::IRekaWriter &,wchar_t const *)
0x1804b1b65  lea     rcx, [rsp+130h+var_110]
0x1804b1b6a  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x1804b1b6f  mov     rbx, rax
0x1804b1b72  mov     rax, [rax]
0x1804b1b75  lea     rdx, aEntrypoint; "entryPoint"
0x1804b1b7c  mov     rcx, rbx
0x1804b1b7f  mov     rax, [rax+28h]
0x1804b1b83  call    cs:__guard_dispatch_icall_fptr
0x1804b1b89  mov     edx, [rbp+47h+arg_28]
0x1804b1b8c  mov     rcx, rbx
0x1804b1b8f  call    cs:__imp_?WriteRekaObject@JSHost@Mso@@YAXAEAUIRekaWriter@12@I@Z; Mso::JSHost::WriteRekaObject(Mso::JSHost::IRekaWriter &,uint)
0x1804b1b95  lea     rdx, aPerfmetrics; "perfMetrics"
0x1804b1b9c  lea     rcx, [rsp+130h+var_110]
0x1804b1ba1  call    cs:__imp_?WritePropertyName@JsonWriter@JSHost@Mso@@QEAAXPEB_W@Z; Mso::JSHost::JsonWriter::WritePropertyName(wchar_t const *)
0x1804b1ba7  lea     r8, [rsp+130h+Block]
0x1804b1bac  mov     rdx, r14
0x1804b1baf  lea     rcx, [rsp+130h+var_110]
0x1804b1bb4  call    sub_1804B1924
0x1804b1bb9  lea     rcx, [rsp+130h+var_110]
0x1804b1bbe  call    cs:__imp_?WriteObjectEnd@JsonWriter@JSHost@Mso@@QEAAXXZ; Mso::JSHost::JsonWriter::WriteObjectEnd(void)
0x1804b1bc4  lea     rdx, [rbp+47h+var_70]
0x1804b1bc8  lea     rcx, [rsp+130h+var_110]
0x1804b1bcd  call    cs:__imp_?ToWString@JsonWriter@JSHost@Mso@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::JSHost::JsonWriter::ToWString(void)
0x1804b1bd3  lea     r9d, [r13+10h]
0x1804b1bd7  lea     r8, aHostcontext; "{\"hostContext\": "
0x1804b1bde  xor     edx, edx
0x1804b1be0  mov     rcx, rax
0x1804b1be3  call    ?insert@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_KQEB_W0@Z; std::wstring::insert(unsigned __int64,wchar_t const * const,unsigned __int64)
0x1804b1be8  xorps   xmm0, xmm0
0x1804b1beb  movups  [rsp+130h+Src], xmm0
0x1804b1bf0  xorps   xmm1, xmm1
0x1804b1bf3  movdqu  [rbp+47h+var_C0], xmm1
0x1804b1bf8  movups  xmm0, xmmword ptr [rax]
0x1804b1bfb  movups  [rsp+130h+Src], xmm0
0x1804b1c00  movups  xmm1, xmmword ptr [rax+10h]
0x1804b1c04  movups  [rbp+47h+var_C0], xmm1
0x1804b1c08  mov     qword ptr [rax+18h], 7
0x1804b1c10  mov     [rax], r13w
0x1804b1c14  mov     [rax+10h], r13
0x1804b1c18  lea     rdx, SubStr; "}"
0x1804b1c1f  lea     rcx, [rsp+130h+Src]; Src
0x1804b1c24  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x1804b1c29  xorps   xmm0, xmm0
0x1804b1c2c  movups  [rsp+130h+var_F0], xmm0
0x1804b1c31  mov     qword ptr [rsp+130h+var_E0], r13
0x1804b1c36  mov     qword ptr [rsp+130h+var_E0+8], r13
0x1804b1c3b  movups  xmm0, xmmword ptr [rax]
0x1804b1c3e  movups  [rsp+130h+var_F0], xmm0
0x1804b1c43  movups  xmm1, xmmword ptr [rax+10h]
0x1804b1c47  movups  [rsp+130h+var_E0], xmm1
0x1804b1c4c  mov     [rax], r13w
0x1804b1c50  mov     [rax+10h], r13
0x1804b1c54  mov     qword ptr [rax+18h], 7
0x1804b1c5c  mov     esi, 1000h
0x1804b1c61  mov     rax, qword ptr [rbp+47h+var_C0+8]
0x1804b1c65  cmp     rax, 7
0x1804b1c69  jbe     short loc_1804B1CA1
0x1804b1c6b  lea     rax, ds:2[rax*2]
0x1804b1c73  mov     [rsp+130h+var_100], rax
0x1804b1c78  mov     rcx, qword ptr [rsp+130h+Src]
0x1804b1c7d  mov     [rsp+130h+Block], rcx
0x1804b1c82  cmp     rax, rsi
0x1804b1c85  jb      short loc_1804B1C9B
0x1804b1c87  lea     rdx, [rsp+130h+var_100]; unsigned __int64 *
0x1804b1c8c  lea     rcx, [rsp+130h+Block]; void **
0x1804b1c91  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x1804b1c96  mov     rcx, [rsp+130h+Block]; Block
0x1804b1c9b  call    cs:__imp_free
0x1804b1ca1  mov     r14d, 4DE1h
0x1804b1ca7  mov     qword ptr [rsp+130h+Src], r14
0x1804b1cac  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1804b1cb4  movdqu  [rbp+47h+var_C0], xmm1
0x1804b1cb9  mov     rdx, [rbp+47h+var_58]
0x1804b1cbd  cmp     rdx, 7
0x1804b1cc1  jbe     short loc_1804B1CDC
0x1804b1cc3  lea     rdx, ds:2[rdx*2]
0x1804b1ccb  mov     rcx, [rbp+47h+var_70]
0x1804b1ccf  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1804b1cd4  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1804b1cdc  xorps   xmm0, xmm0
0x1804b1cdf  movups  [rbp+47h+var_B0], xmm0
0x1804b1ce3  mov     edi, 0Fh
0x1804b1ce8  mov     [rbp+47h+var_98], rdi
0x1804b1cec  mov     byte ptr [rbp+47h+var_B0], r13b
0x1804b1cf0  movups  [rbp+47h+var_90], xmm0
0x1804b1cf4  movdqa  [rbp+47h+var_80], xmm1
0x1804b1cf9  mov     byte ptr [rbp+47h+var_90], r13b
0x1804b1cfd  lea     edx, [rdi-1]
0x1804b1d00  lea     rbx, [rbp+47h+var_B0]
0x1804b1d04  mov     [rbp+47h+var_A0], rdx
0x1804b1d08  mov     r8d, edx; Size
0x1804b1d0b  lea     rdx, aSdxMemoryApp; "sdx_memory.app"
0x1804b1d12  mov     rcx, rbx; void *
0x1804b1d15  call    memmove_0
0x1804b1d1a  mov     [rbx+0Eh], r13b
0x1804b1d1e  lea     rax, [rsp+130h+var_F0]
0x1804b1d23  cmp     qword ptr [rsp+130h+var_E0+8], 7
0x1804b1d29  cmova   rax, qword ptr [rsp+130h+var_F0]
0x1804b1d2f  mov     qword ptr [rsp+130h+Src], rax
0x1804b1d34  mov     rax, qword ptr [rsp+130h+var_E0]
0x1804b1d39  mov     qword ptr [rsp+130h+Src+8], rax
0x1804b1d3e  lea     rdx, [rsp+130h+Src]
0x1804b1d43  lea     rcx, [rbp+47h+var_70]
0x1804b1d47  call    ?WStrToUTF8@StringCore@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@4@@Z; Mso::StringCore::WStrToUTF8(std::wstring_view const &)
0x1804b1d4c  mov     rdx, rax
0x1804b1d4f  lea     rcx, [rbp+47h+var_90]
0x1804b1d53  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1804b1d58  mov     rax, [rbp+47h+var_58]
0x1804b1d5c  cmp     rax, rdi
0x1804b1d5f  jbe     short loc_1804B1D91
0x1804b1d61  inc     rax
0x1804b1d64  mov     [rsp+130h+var_100], rax
0x1804b1d69  mov     rcx, [rbp+47h+var_70]
0x1804b1d6d  mov     [rsp+130h+Block], rcx
0x1804b1d72  cmp     rax, rsi
0x1804b1d75  jb      short loc_1804B1D8B
0x1804b1d77  lea     rdx, [rsp+130h+var_100]; unsigned __int64 *
0x1804b1d7c  lea     rcx, [rsp+130h+Block]; void **
0x1804b1d81  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x1804b1d86  mov     rcx, [rsp+130h+Block]; Block
0x1804b1d8b  call    cs:__imp_free
0x1804b1d91  mov     rax, [r12]
0x1804b1d95  lea     r8, [rbp+47h+var_B0]
0x1804b1d99  mov     rdx, r15
0x1804b1d9c  mov     rcx, r12
0x1804b1d9f  mov     rax, [rax+50h]
0x1804b1da3  call    cs:__guard_dispatch_icall_fptr
0x1804b1da9  lea     rcx, [rbp+47h+var_90]; void *
0x1804b1dad  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1804b1db2  lea     rcx, [rbp+47h+var_B0]; void *
0x1804b1db6  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1804b1dbb  mov     rax, qword ptr [rsp+130h+var_E0+8]
0x1804b1dc0  cmp     rax, 7
0x1804b1dc4  jbe     short loc_1804B1DFC
0x1804b1dc6  lea     rax, ds:2[rax*2]
0x1804b1dce  mov     [rsp+130h+var_100], rax
0x1804b1dd3  mov     rcx, qword ptr [rsp+130h+var_F0]
0x1804b1dd8  mov     [rsp+130h+Block], rcx
0x1804b1ddd  cmp     rax, rsi
0x1804b1de0  jb      short loc_1804B1DF6
0x1804b1de2  lea     rdx, [rsp+130h+var_100]; unsigned __int64 *
0x1804b1de7  lea     rcx, [rsp+130h+Block]; void **
0x1804b1dec  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x1804b1df1  mov     rcx, [rsp+130h+Block]; Block
0x1804b1df6  call    cs:__imp_free
0x1804b1dfc  mov     qword ptr [rsp+130h+var_F0], r14
0x1804b1e01  mov     qword ptr [rsp+130h+var_E0], r13
0x1804b1e06  mov     qword ptr [rsp+130h+var_E0+8], rdi
0x1804b1e0b  mov     rcx, [rsp+130h+var_110]
0x1804b1e10  test    rcx, rcx
0x1804b1e13  jz      short loc_1804B1E27
0x1804b1e15  mov     [rsp+130h+var_110], r13
0x1804b1e1a  mov     rdx, [rcx]
0x1804b1e1d  mov     rax, [rdx+10h]
0x1804b1e21  call    cs:__guard_dispatch_icall_fptr
0x1804b1e27  mov     rax, r15
0x1804b1e2a  mov     rcx, [rbp+47h+var_50]
0x1804b1e2e  xor     rcx, rsp; StackCookie
0x1804b1e31  call    __security_check_cookie
0x1804b1e36  add     rsp, 0F8h
0x1804b1e3d  pop     r15
0x1804b1e3f  pop     r14
0x1804b1e41  pop     r13
0x1804b1e43  pop     r12
0x1804b1e45  pop     rdi
0x1804b1e46  pop     rsi
0x1804b1e47  pop     rbx
0x1804b1e48  pop     rbp
0x1804b1e49  retn
```
