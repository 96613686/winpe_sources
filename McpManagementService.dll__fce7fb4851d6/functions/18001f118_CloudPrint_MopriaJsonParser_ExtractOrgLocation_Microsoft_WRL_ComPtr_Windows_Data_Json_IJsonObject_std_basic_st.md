# CloudPrint::MopriaJsonParser::ExtractOrgLocation(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18001f118`
- end: `0x18001f54e`
- name: `?ExtractOrgLocation@MopriaJsonParser@CloudPrint@@SAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1078`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f9a4`

## callees

- `0x180003a60`
- `0x180009fc0`
- `0x18000c4cc`
- `0x18000e164`
- `0x18000e208`
- `0x18000e2dc`
- `0x18000f7a4`
- `0x180012700`
- `0x18001bfe4`
- `0x18001ddb4`
- `0x18001ea14`
- `0x18001eab0`
- `0x18001ebc4`
- `0x18001ed80`
- `0x18001eeb8`
- `0x18001f118`
- `0x1800212a4`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f30f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f30f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f2d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f3c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f2d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f3c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CloudPrint::MopriaJsonParser::ExtractOrgLocation(__int64 *a1, __int64 a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, _QWORD); // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  unsigned int i; // esi
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64); // rbx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, double *); // rbx
  __int64 v16; // rax
  __int64 v17; // rdi
  int (__fastcall *v18)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v19; // rax
  __int64 v20; // rdi
  int (__fastcall *v21)(__int64, _QWORD, double *); // rbx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 *v24; // rdx
  __int64 *v25; // rbx
  __int64 v26; // rax
  __int64 j; // rcx
  __int64 k; // rcx
  __int64 **v29; // rcx
  __int64 *m; // rax
  __int64 *n; // rcx
  __int64 v33; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v34; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v35; // [rsp+38h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C8h] BYREF
  __int64 (__fastcall ***v37)(_QWORD, GUID *, __int64); // [rsp+48h] [rbp-C0h] BYREF
  double v38; // [rsp+50h] [rbp-B8h] BYREF
  double v39; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v40[4]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v41[16]; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v42[24]; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v43[80]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v44[32]; // [rsp+F8h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]

  v40[3] = a1;
  CloudPrintHelperTelemetry::WatchCurrentThread(v43, "ExtractOrgLocation");
  *(_QWORD *)(a2 + 16) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr() = 0;
  v37 = 0;
  memset(v40, 0, 24);
  std::_Tree<std::_Tmap_traits<unsigned int,std::wstring,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::wstring>>,0>>::_Alloc_sentinel_and_proxy(&v40[1]);
  LODWORD(v35) = 0;
  v4 = *a1;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)*a1 + 72LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v44, off_18003F128);
  v7 = v5(v4, *(_QWORD *)(v6 + 24), &v37);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 417;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\util\\cloudprinthelperutil.cpp",
      (const char *)(unsigned int)v7,
      v33);
    goto LABEL_46;
  }
  v7 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
         &v37,
         (__int64)v40);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 418;
    goto LABEL_5;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v40[0] + 56LL))(v40[0], &v35);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 419;
    goto LABEL_5;
  }
  for ( i = 0; i < (unsigned int)v35; ++i )
  {
    v34 = 0;
    v11 = v37;
    v12 = (*v37)[6];
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    v13 = v12(v11, (GUID *)i, (__int64)&v34);
    v8 = v13;
    if ( v13 < 0 )
    {
      v23 = 424;
      goto LABEL_19;
    }
    v39 = 0.0;
    v14 = v34;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, double *))(*(_QWORD *)v34 + 88LL);
    v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v44, off_18003F140);
    v13 = v15(v14, *(_QWORD *)(v16 + 24), &v39);
    v8 = v13;
    if ( v13 < 0 )
    {
      v23 = 428;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\util\\cloudprinthelperutil.cpp",
        (const char *)(unsigned int)v13,
        v33);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
      goto LABEL_46;
    }
    string = 0;
    v17 = v34;
    v18 = *(int (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v34 + 80LL);
    WindowsDeleteString(0);
    string = 0;
    v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v44, off_18003F170);
    if ( v18(v17, *(_QWORD *)(v19 + 24), &string) < 0 )
    {
      v38 = 0.0;
      v20 = v34;
      v21 = *(int (__fastcall **)(__int64, _QWORD, double *))(*(_QWORD *)v34 + 88LL);
      v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v44, off_18003F158);
      if ( v21(v20, *(_QWORD *)(v22 + 24), &v38) >= 0 )
      {
        std::_Integral_to_string<unsigned short,unsigned int>(v44, (unsigned int)(int)v38);
        LODWORD(v33) = (int)v39;
        std::_Tree<std::_Tmap_traits<unsigned int,std::wstring,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::wstring>>,0>>::_Emplace<unsigned int,std::wstring>(
          &v40[1],
          v42,
          &v33,
          v44);
        std::wstring::_Tidy_deallocate((__int64)v44);
      }
    }
    else
    {
      v38 = COERCE_DOUBLE(WindowsGetStringRawBuffer(string, 0));
      LODWORD(v33) = (int)v39;
      std::_Tree<std::_Tmap_traits<unsigned int,std::wstring,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::wstring>>,0>>::_Emplace<unsigned int,unsigned short const *>(
        &v40[1],
        v41,
        &v33,
        &v38);
    }
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  }
  v24 = (__int64 *)v40[1];
  v25 = *(__int64 **)v40[1];
  while ( v25 != v24 )
  {
    std::wstring::append(a2, v25 + 5);
    v24 = (__int64 *)v40[1];
    v26 = v40[1];
    if ( *(_BYTE *)(v40[1] + 25LL) )
    {
      v26 = *(_QWORD *)(v40[1] + 16LL);
    }
    else if ( *(_BYTE *)(*(_QWORD *)v40[1] + 25LL) )
    {
      for ( j = *(_QWORD *)(v40[1] + 8LL); !*(_BYTE *)(j + 25) && v26 == *(_QWORD *)j; j = *(_QWORD *)(j + 8) )
        v26 = j;
      if ( !*(_BYTE *)(v26 + 25) )
        v26 = j;
    }
    else
    {
      v26 = *(_QWORD *)v40[1];
      for ( k = *(_QWORD *)(*(_QWORD *)v40[1] + 16LL); !*(_BYTE *)(k + 25); k = *(_QWORD *)(v26 + 16) )
        v26 = *(_QWORD *)(v26 + 16);
    }
    if ( v25 != (__int64 *)v26 )
    {
      std::wstring::append(a2, (__int64)L"\\");
      v24 = (__int64 *)v40[1];
    }
    v29 = (__int64 **)v25[2];
    if ( *((_BYTE *)v29 + 25) )
    {
      for ( m = (__int64 *)v25[1]; !*((_BYTE *)m + 25) && v25 == (__int64 *)m[2]; m = (__int64 *)m[1] )
        v25 = m;
      v25 = m;
    }
    else
    {
      v25 = (__int64 *)v25[2];
      for ( n = *v29; !*((_BYTE *)n + 25); n = (__int64 *)*n )
        v25 = n;
    }
  }
  v8 = 0;
LABEL_46:
  std::_Tree<std::_Tmap_traits<unsigned int,std::wstring,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned int,std::wstring,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::wstring>>,0>>(&v40[1]);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v40);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v43);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
  return v8;
}

```

## disassembly

```asm
0x18001f118  mov     rax, rsp
0x18001f11b  mov     [rax+18h], rbx
0x18001f11f  mov     [rax+20h], rsi
0x18001f123  push    rbp
0x18001f124  push    rdi
0x18001f125  push    r12
0x18001f127  push    r14
0x18001f129  push    r15
0x18001f12b  lea     rbp, [rax-58h]
0x18001f12f  sub     rsp, 130h
0x18001f136  movaps  xmmword ptr [rax-38h], xmm6
0x18001f13a  mov     rax, cs:__security_cookie
0x18001f141  xor     rax, rsp
0x18001f144  mov     [rbp+50h+var_40], rax
0x18001f148  mov     r14, rdx
0x18001f14b  mov     r15, rcx
0x18001f14e  mov     [rsp+150h+var_E0], rcx
0x18001f153  xor     r12d, r12d
0x18001f156  lea     rdx, aExtractorgloca; "ExtractOrgLocation"
0x18001f15d  lea     rcx, [rbp+50h+var_B0]
0x18001f161  call    ?WatchCurrentThread@CloudPrintHelperTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; CloudPrintHelperTelemetry::WatchCurrentThread(char const *)
0x18001f166  nop
0x18001f167  mov     [r14+10h], r12
0x18001f16b  mov     rcx, r14
0x18001f16e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001f173  mov     [rax], r12w
0x18001f177  mov     [rsp+150h+var_110], r12
0x18001f17c  mov     qword ptr [rsp+150h+var_F8], r12
0x18001f181  xorps   xmm0, xmm0
0x18001f184  movdqu  xmmword ptr [rsp+150h+var_F8+8], xmm0
0x18001f18a  lea     rcx, [rsp+150h+var_F8+8]
0x18001f18f  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@IV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<uint,std::wstring,std::less<uint>,std::allocator<std::pair<uint const,std::wstring>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18001f194  nop
0x18001f195  mov     dword ptr [rsp+150h+var_120], r12d
0x18001f19a  mov     rdi, [r15]
0x18001f19d  mov     rax, [rdi]
0x18001f1a0  mov     rbx, [rax+48h]
0x18001f1a4  lea     rcx, [rsp+150h+var_110]
0x18001f1a9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f1ae  lea     rdx, off_18003F128; "attrs"
0x18001f1b5  lea     rcx, [rbp+50h+var_60]
0x18001f1b9  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001f1be  nop
0x18001f1bf  lea     r8, [rsp+150h+var_110]
0x18001f1c4  mov     rdx, [rax+18h]
0x18001f1c8  mov     rcx, rdi
0x18001f1cb  mov     rax, rbx
0x18001f1ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1d3  mov     ebx, eax
0x18001f1d5  test    eax, eax
0x18001f1d7  jns     short loc_18001F1E0
0x18001f1d9  mov     edx, 1A1h
0x18001f1de  jmp     short loc_18001F1FA
0x18001f1e0  lea     rdx, [rsp+150h+var_F8]
0x18001f1e5  lea     rcx, [rsp+150h+var_110]
0x18001f1ea  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x18001f1ef  mov     ebx, eax
0x18001f1f1  test    eax, eax
0x18001f1f3  jns     short loc_18001F212
0x18001f1f5  mov     edx, 1A2h; void *
0x18001f1fa  mov     rcx, [rbp+58h]; this
0x18001f1fe  mov     r9d, eax; char *
0x18001f201  lea     r8, aOnecoreuapPrin_1; "onecoreuap\\printscan\\print\\shared\\c"...
0x18001f208  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f20d  jmp     loc_18001F4EC
0x18001f212  mov     rcx, qword ptr [rsp+150h+var_F8]
0x18001f217  mov     rax, [rcx]
0x18001f21a  lea     rdx, [rsp+150h+var_120]
0x18001f21f  mov     rax, [rax+38h]
0x18001f223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f228  mov     ebx, eax
0x18001f22a  test    eax, eax
0x18001f22c  jns     short loc_18001F235
0x18001f22e  mov     edx, 1A3h
0x18001f233  jmp     short loc_18001F1FA
0x18001f235  mov     esi, r12d
0x18001f238  xorps   xmm6, xmm6
0x18001f23b  cmp     esi, dword ptr [rsp+150h+var_120]
0x18001f23f  jnb     loc_18001F40D
0x18001f245  mov     [rsp+150h+var_128], r12
0x18001f24a  mov     rdi, [rsp+150h+var_110]
0x18001f24f  mov     rax, [rdi]
0x18001f252  mov     rbx, [rax+30h]
0x18001f256  lea     rcx, [rsp+150h+var_128]
0x18001f25b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f260  lea     r8, [rsp+150h+var_128]
0x18001f265  mov     edx, esi
0x18001f267  mov     rcx, rdi
0x18001f26a  mov     rax, rbx
0x18001f26d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f272  mov     ebx, eax
0x18001f274  test    eax, eax
0x18001f276  js      loc_18001F3E5
0x18001f27c  movsd   [rsp+150h+var_100], xmm6
0x18001f282  mov     rdi, [rsp+150h+var_128]
0x18001f287  mov     rax, [rdi]
0x18001f28a  mov     rbx, [rax+58h]
0x18001f28e  lea     rdx, off_18003F140; "depth"
0x18001f295  lea     rcx, [rbp+50h+var_60]
0x18001f299  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001f29e  nop
0x18001f29f  lea     r8, [rsp+150h+var_100]
0x18001f2a4  mov     rdx, [rax+18h]
0x18001f2a8  mov     rcx, rdi
0x18001f2ab  mov     rax, rbx
0x18001f2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2b3  mov     ebx, eax
0x18001f2b5  test    eax, eax
0x18001f2b7  js      loc_18001F3DE
0x18001f2bd  mov     [rsp+150h+string], r12
0x18001f2c2  mov     rdi, [rsp+150h+var_128]
0x18001f2c7  mov     rax, [rdi]
0x18001f2ca  mov     rbx, [rax+50h]
0x18001f2ce  xor     ecx, ecx; string
0x18001f2d0  call    cs:__imp_WindowsDeleteString
0x18001f2d6  mov     [rsp+150h+string], r12
0x18001f2db  lea     rdx, off_18003F170; "vs"
0x18001f2e2  lea     rcx, [rbp+50h+var_60]
0x18001f2e6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001f2eb  nop
0x18001f2ec  lea     r8, [rsp+150h+string]
0x18001f2f1  mov     rdx, [rax+18h]
0x18001f2f5  mov     rcx, rdi
0x18001f2f8  mov     rax, rbx
0x18001f2fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f300  nop
0x18001f301  shr     eax, 1Fh
0x18001f304  xor     al, 1
0x18001f306  jz      short loc_18001F340
0x18001f308  xor     edx, edx; length
0x18001f30a  mov     rcx, [rsp+150h+string]; string
0x18001f30f  call    cs:__imp_WindowsGetStringRawBuffer
0x18001f315  mov     [rsp+150h+var_108], rax
0x18001f31a  cvttsd2si rax, [rsp+150h+var_100]
0x18001f321  mov     dword ptr [rsp+150h+var_130], eax
0x18001f325  lea     r9, [rsp+150h+var_108]
0x18001f32a  lea     r8, [rsp+150h+var_130]
0x18001f32f  lea     rdx, [rsp+150h+var_D8]
0x18001f334  lea     rcx, [rsp+150h+var_F8+8]
0x18001f339  call    ??$_Emplace@IPEBG@?$_Tree@V?$_Tmap_traits@IV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBIV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@$$QEAI$$QEAPEBG@Z; std::_Tree<std::_Tmap_traits<uint,std::wstring,std::less<uint>,std::allocator<std::pair<uint const,std::wstring>>,0>>::_Emplace<uint,ushort const *>(uint &&,ushort const * &&)
0x18001f33e  jmp     short loc_18001F3BD
0x18001f340  movsd   [rsp+150h+var_108], xmm6
0x18001f346  mov     rdi, [rsp+150h+var_128]
0x18001f34b  mov     rax, [rdi]
0x18001f34e  mov     rbx, [rax+58h]
0x18001f352  lea     rdx, off_18003F158; "vn"
0x18001f359  lea     rcx, [rbp+50h+var_60]
0x18001f35d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001f362  nop
0x18001f363  lea     r8, [rsp+150h+var_108]
0x18001f368  mov     rdx, [rax+18h]
0x18001f36c  mov     rcx, rdi
0x18001f36f  mov     rax, rbx
0x18001f372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f377  nop
0x18001f378  shr     eax, 1Fh
0x18001f37b  xor     al, 1
0x18001f37d  jz      short loc_18001F3BD
0x18001f37f  cvttsd2si rdx, [rsp+150h+var_108]
0x18001f386  lea     rcx, [rbp+50h+var_60]
0x18001f38a  call    ??$_Integral_to_string@GI@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@I@Z; std::_Integral_to_string<ushort,uint>(uint)
0x18001f38f  nop
0x18001f390  cvttsd2si rax, [rsp+150h+var_100]
0x18001f397  mov     dword ptr [rsp+150h+var_130], eax
0x18001f39b  lea     r9, [rbp+50h+var_60]
0x18001f39f  lea     r8, [rsp+150h+var_130]
0x18001f3a4  lea     rdx, [rbp+50h+var_C8]
0x18001f3a8  lea     rcx, [rsp+150h+var_F8+8]
0x18001f3ad  call    ??$_Emplace@IV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@IV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBIV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@$$QEAI$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<uint,std::wstring,std::less<uint>,std::allocator<std::pair<uint const,std::wstring>>,0>>::_Emplace<uint,std::wstring>(uint &&,std::wstring &&)
0x18001f3b2  nop
0x18001f3b3  lea     rcx, [rbp+50h+var_60]
0x18001f3b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f3bc  nop
0x18001f3bd  mov     rcx, [rsp+150h+string]; string
0x18001f3c2  call    cs:__imp_WindowsDeleteString
0x18001f3c8  mov     [rsp+150h+string], r12
0x18001f3cd  lea     rcx, [rsp+150h+var_128]
0x18001f3d2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f3d7  inc     esi
0x18001f3d9  jmp     loc_18001F23B
0x18001f3de  mov     edx, 1ACh
0x18001f3e3  jmp     short loc_18001F3EA
0x18001f3e5  mov     edx, 1A8h; void *
0x18001f3ea  lea     r8, aOnecoreuapPrin_1; "onecoreuap\\printscan\\print\\shared\\c"...
0x18001f3f1  mov     r9d, eax; char *
0x18001f3f4  mov     rcx, [rbp+58h]; this
0x18001f3f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f3fd  nop
0x18001f3fe  lea     rcx, [rsp+150h+var_128]
0x18001f403  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f408  jmp     loc_18001F4EC
0x18001f40d  mov     rdx, qword ptr [rsp+150h+var_F8+8]
0x18001f412  mov     rbx, [rdx]
0x18001f415  cmp     rbx, rdx
0x18001f418  jz      loc_18001F4E9
0x18001f41e  lea     rdx, [rbx+28h]
0x18001f422  mov     rcx, r14
0x18001f425  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18001f42a  mov     rdx, qword ptr [rsp+150h+var_F8+8]
0x18001f42f  mov     rax, rdx
0x18001f432  cmp     [rdx+19h], r12b
0x18001f436  jz      short loc_18001F43E
0x18001f438  mov     rax, [rdx+10h]
0x18001f43c  jmp     short loc_18001F481
0x18001f43e  mov     rcx, [rdx]
0x18001f441  cmp     [rcx+19h], r12b
0x18001f445  jz      short loc_18001F46A
0x18001f447  mov     rcx, [rdx+8]
0x18001f44b  jmp     short loc_18001F459
0x18001f44d  cmp     rax, [rcx]
0x18001f450  jnz     short loc_18001F45F
0x18001f452  mov     rax, rcx
0x18001f455  mov     rcx, [rcx+8]
0x18001f459  cmp     [rcx+19h], r12b
0x18001f45d  jz      short loc_18001F44D
0x18001f45f  cmp     [rax+19h], r12b
0x18001f463  jnz     short loc_18001F481
0x18001f465  mov     rax, rcx
0x18001f468  jmp     short loc_18001F481
0x18001f46a  mov     rax, rcx
0x18001f46d  mov     rcx, [rcx+10h]
0x18001f471  jmp     short loc_18001F47B
0x18001f473  mov     rax, [rax+10h]
0x18001f477  mov     rcx, [rax+10h]
0x18001f47b  cmp     [rcx+19h], r12b
0x18001f47f  jz      short loc_18001F473
0x18001f481  cmp     rbx, rax
0x18001f484  jz      short loc_18001F49A
0x18001f486  lea     rdx, asc_18002DEF8; "\\"
0x18001f48d  mov     rcx, r14
0x18001f490  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001f495  mov     rdx, qword ptr [rsp+150h+var_F8+8]
0x18001f49a  mov     rcx, [rbx+10h]
0x18001f49e  cmp     [rcx+19h], r12b
0x18001f4a2  jz      short loc_18001F4C5
0x18001f4a4  mov     rax, [rbx+8]
0x18001f4a8  jmp     short loc_18001F4B7
0x18001f4aa  cmp     rbx, [rax+10h]
0x18001f4ae  jnz     short loc_18001F4BD
0x18001f4b0  mov     rbx, rax
0x18001f4b3  mov     rax, [rax+8]
0x18001f4b7  cmp     [rax+19h], r12b
0x18001f4bb  jz      short loc_18001F4AA
0x18001f4bd  mov     rbx, rax
0x18001f4c0  jmp     loc_18001F415
0x18001f4c5  mov     rbx, rcx
0x18001f4c8  mov     rcx, [rcx]
0x18001f4cb  cmp     [rcx+19h], r12b
0x18001f4cf  jnz     loc_18001F415
0x18001f4d5  mov     rbx, rcx
0x18001f4d8  mov     rax, [rcx]
0x18001f4db  mov     rcx, rax
0x18001f4de  cmp     [rax+19h], r12b
0x18001f4e2  jz      short loc_18001F4D5
0x18001f4e4  jmp     loc_18001F415
0x18001f4e9  mov     ebx, r12d
0x18001f4ec  lea     rcx, [rsp+150h+var_F8+8]
0x18001f4f1  call    ??1?$_Tree@V?$_Tmap_traits@IV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uint,std::wstring,std::less<uint>,std::allocator<std::pair<uint const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<uint,std::wstring,std::less<uint>,std::allocator<std::pair<uint const,std::wstring>>,0>>(void)
0x18001f4f6  nop
0x18001f4f7  lea     rcx, [rsp+150h+var_F8]
0x18001f4fc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f501  nop
0x18001f502  lea     rcx, [rsp+150h+var_110]
0x18001f507  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f50c  nop
0x18001f50d  lea     rcx, [rbp+50h+var_B0]; this
0x18001f511  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18001f516  nop
0x18001f517  mov     rcx, r15
0x18001f51a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f51f  mov     eax, ebx
0x18001f521  mov     rcx, [rbp+50h+var_40]
0x18001f525  xor     rcx, rsp; StackCookie
0x18001f528  call    __security_check_cookie
0x18001f52d  lea     r11, [rsp+150h+var_20]
0x18001f535  mov     rbx, [r11+40h]
0x18001f539  mov     rsi, [r11+48h]
0x18001f53d  movaps  xmm6, xmmword ptr [r11-10h]
0x18001f542  mov     rsp, r11
0x18001f545  pop     r15
0x18001f547  pop     r14
0x18001f549  pop     r12
0x18001f54b  pop     rdi
0x18001f54c  pop     rbp
0x18001f54d  retn
```
