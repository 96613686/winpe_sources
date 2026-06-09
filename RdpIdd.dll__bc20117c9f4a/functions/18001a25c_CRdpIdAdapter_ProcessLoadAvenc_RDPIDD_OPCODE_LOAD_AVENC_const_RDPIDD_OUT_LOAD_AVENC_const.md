# CRdpIdAdapter::ProcessLoadAvenc(_RDPIDD_OPCODE_LOAD_AVENC * const,_RDPIDD_OUT_LOAD_AVENC * const)

- ea: `0x18001a25c`
- end: `0x18001a5b7`
- name: `?ProcessLoadAvenc@CRdpIdAdapter@@AEAAXQEAU_RDPIDD_OPCODE_LOAD_AVENC@@QEAU_RDPIDD_OUT_LOAD_AVENC@@@Z`
- size: `859`
- prototype: `void __fastcall(CRdpIdAdapter *__hidden this, struct _RDPIDD_OPCODE_LOAD_AVENC *const, struct _RDPIDD_OUT_LOAD_AVENC *const)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting`

## callers

- `0x1800185bc`

## callees

- `0x180001af0`
- `0x180004484`
- `0x180006f60`
- `0x180007b2c`
- `0x18000d614`
- `0x18000ebfc`
- `0x180012ad4`
- `0x180012b14`
- `0x180013294`
- `0x18001a25c`
- `0x18001b1a0`
- `0x18001dd70`
- `0x18001ddf4`
- `0x180020d00`
- `0x180021570`
- `0x180021780`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a37f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a37f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001a31f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001a31f`

## string_xrefs

- `0x18001a290`: `Video encoder dll has already been loaded`
- `0x18001a354`: `Failed to load video encoder dll`
- `0x18001a4ed`: `AdapterAvencVersion: Iface: %#x.%#x, Dll: %#x.%#x, Build: %#x`

## pseudocode

```c
void __fastcall CRdpIdAdapter::ProcessLoadAvenc(
        CRdpIdAdapter *this,
        struct _RDPIDD_OPCODE_LOAD_AVENC *const a2,
        struct _RDPIDD_OUT_LOAD_AVENC *const a3)
{
  HMODULE *v3; // r12
  char *v7; // r8
  unsigned __int64 v8; // rdx
  char *v9; // rcx
  char *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rbx
  __int64 v13; // r8
  char *v14; // rdi
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rbx
  unsigned int v17; // eax
  _DWORD *v18; // r8
  int v19; // r8d
  int v20; // r9d
  char *v21; // [rsp+28h] [rbp-61h]
  char *v22; // [rsp+28h] [rbp-61h]
  const char *v23; // [rsp+30h] [rbp-59h]
  __int64 v24; // [rsp+30h] [rbp-59h]
  __int64 v25; // [rsp+38h] [rbp-51h]
  __int64 v26; // [rsp+40h] [rbp-49h]
  __int64 v27; // [rsp+48h] [rbp-41h]
  int v28; // [rsp+60h] [rbp-29h] BYREF
  int v29; // [rsp+64h] [rbp-25h] BYREF
  int v30; // [rsp+68h] [rbp-21h] BYREF
  int v31; // [rsp+6Ch] [rbp-1Dh] BYREF
  int v32; // [rsp+70h] [rbp-19h] BYREF
  HMODULE v33; // [rsp+78h] [rbp-11h] BYREF
  const char *v34; // [rsp+80h] [rbp-9h] BYREF
  __int64 v35; // [rsp+88h] [rbp-1h] BYREF
  GUID *v36; // [rsp+90h] [rbp+7h] BYREF
  _DWORD v37[4]; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v3 = (HMODULE *)((char *)this + 416);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xBCD,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)0x80070057LL,
    *((_QWORD *)this + 52) != 0,
    (bool)"Video encoder dll has already been loaded",
    v23);
  v7 = (char *)this + 384;
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)a2 + v8 + 6) );
  v9 = (char *)this + 384;
  if ( v8 > *((_QWORD *)this + 51) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
      v9,
      v8,
      v7,
      (char *)a2 + 12);
  }
  else
  {
    v10 = (char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9, v8, v7);
    v12 = 2 * v11;
    *(_QWORD *)(v13 + 16) = v11;
    v14 = v10;
    memmove_0(v10, (char *)a2 + 12, 2 * v11);
    *(_WORD *)&v14[v12] = 0;
  }
  LibraryW = LoadLibraryW((LPCWSTR)a2 + 6);
  v33 = LibraryW;
  if ( v3 != &v33 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      v3,
      LibraryW);
    v33 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v33);
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,0>(
    retaddr,
    3028,
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    v3,
    "Failed to load video encoder dll");
  ProcAddress = GetProcAddress(*v3, "NegotiateVersions");
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<long (*)(Rdp::Avenc::AVENC_VERSION_INFO const *,Rdp::Avenc::AVENC_VERSION_INFO *,Rdp::Avenc::AVENC_VERSION_INFO *),0>(
    retaddr,
    3033,
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    ProcAddress,
    "Failed to load address of NegotiateVersions");
  v37[1] = *((_DWORD *)this + 86);
  v37[2] = *((_DWORD *)this + 87);
  v37[0] = 16;
  v37[3] = 0;
  v17 = ((__int64 (__fastcall *)(_DWORD *, char *, char *))ProcAddress)(v37, (char *)this + 352, (char *)this + 368);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xBE9,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)v17,
    (int)"Failed to negotiate versions with Avenc",
    v21);
  v18 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v18 > 4u && (unsigned __int8)tlgKeywordOn(v18, 0x400000000000LL) )
  {
    v28 = *((_DWORD *)this + 95);
    v29 = *((_DWORD *)this + 94);
    v30 = *((_DWORD *)this + 93);
    v31 = *((_DWORD *)this + 90);
    v32 = *((_DWORD *)this + 89);
    v34 = "Avenc versions";
    v36 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
    v35 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v19,
      (unsigned int)byte_18004C6CD,
      v19,
      v20,
      (__int64)&v36,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v32,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v28);
  }
  LODWORD(v27) = *((_DWORD *)this + 95);
  LODWORD(v26) = *((_DWORD *)this + 94);
  LODWORD(v25) = *((_DWORD *)this + 93);
  LODWORD(v24) = *((_DWORD *)this + 90);
  LODWORD(v22) = *((_DWORD *)this + 89);
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"AdapterAvencVersion: Iface: %#x.%#x, Dll: %#x.%#x, Build: %#x",
    "CRdpIdAdapter::ProcessLoadAvenc",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    0xBFAu,
    v22,
    v24,
    v25,
    v26,
    v27);
  if ( a3 )
  {
    *(_DWORD *)a3 = 20;
    *((_DWORD *)a3 + 1) = *((_DWORD *)this + 93);
    *((_DWORD *)a3 + 2) = *((_DWORD *)this + 94);
    *((_DWORD *)a3 + 3) = *((_DWORD *)this + 89);
    *((_DWORD *)a3 + 4) = *((_DWORD *)this + 90);
  }
  if ( *(_QWORD *)((char *)a2 + 532) || *(_QWORD *)((char *)a2 + 540) )
    CRdpIdAdapter::ProcessStartProcessor(this, (const struct _GUID *)((char *)a2 + 532));
}

```

## disassembly

```asm
0x18001a25c  mov     [rsp-8+arg_18], rbx
0x18001a261  push    rbp
0x18001a262  push    rsi
0x18001a263  push    rdi
0x18001a264  push    r12
0x18001a266  push    r13
0x18001a268  push    r14
0x18001a26a  push    r15
0x18001a26c  lea     rbp, [rsp-27h]
0x18001a271  sub     rsp, 0B0h
0x18001a278  mov     rax, cs:__security_cookie
0x18001a27f  xor     rax, rsp
0x18001a282  mov     [rbp+57h+var_38], rax
0x18001a286  lea     r12, [rcx+1A0h]
0x18001a28d  mov     r13, rdx
0x18001a290  lea     rdx, aVideoEncoderDl_0; "Video encoder dll has already been load"...
0x18001a297  mov     r14, r8
0x18001a29a  mov     [rsp+0E0h+var_B8], rdx; char *
0x18001a29f  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001a2a6  mov     rsi, rcx
0x18001a2a9  xor     edi, edi
0x18001a2ab  cmp     [r12], rdi
0x18001a2af  mov     r9d, 80070057h; char *
0x18001a2b5  mov     rcx, [rbp+5Fh]; this
0x18001a2b9  mov     edx, 0BCDh; void *
0x18001a2be  setnz   al
0x18001a2c1  mov     [rsp+0E0h+var_C0], al; char
0x18001a2c5  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001a2ca  lea     r8, [rsi+180h]
0x18001a2d1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001a2d5  lea     r15, [r13+0Ch]
0x18001a2d9  inc     rdx
0x18001a2dc  cmp     [r15+rdx*2], di
0x18001a2e1  jnz     short loc_18001A2D9
0x18001a2e3  mov     rcx, r8
0x18001a2e6  cmp     rdx, [r8+18h]
0x18001a2ea  ja      short loc_18001A314
0x18001a2ec  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001a2f1  lea     rbx, [rdx+rdx]
0x18001a2f5  mov     [r8+10h], rdx
0x18001a2f9  mov     r8, rbx; Size
0x18001a2fc  mov     rdx, r15; Src
0x18001a2ff  mov     rcx, rax; void *
0x18001a302  mov     rdi, rax
0x18001a305  call    memmove_0
0x18001a30a  xor     ecx, ecx
0x18001a30c  mov     [rbx+rdi], cx
0x18001a310  xor     edi, edi
0x18001a312  jmp     short loc_18001A31C
0x18001a314  mov     r9, r15
0x18001a317  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x18001a31c  mov     rcx, r15; lpLibFileName
0x18001a31f  call    cs:__imp_LoadLibraryW
0x18001a326  nop     dword ptr [rax+rax+00h]
0x18001a32b  lea     rcx, [rbp+57h+var_68]
0x18001a32f  mov     [rbp+57h+var_68], rax
0x18001a333  cmp     r12, rcx
0x18001a336  jz      short loc_18001A347
0x18001a338  mov     rdx, rax
0x18001a33b  mov     rcx, r12
0x18001a33e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18001a343  mov     [rbp+57h+var_68], rdi
0x18001a347  lea     rcx, [rbp+57h+var_68]
0x18001a34b  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18001a350  mov     rcx, [rbp+5Fh]
0x18001a354  lea     rax, aFailedToLoadVi; "Failed to load video encoder dll"
0x18001a35b  mov     r9, r12
0x18001a35e  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18001a363  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001a36a  mov     edx, 0BD4h
0x18001a36f  call    ??$Throw_GetLastErrorIfNullMsg@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,0>(void *,uint,char const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> const &,char const *,...)
0x18001a374  mov     rcx, [r12]; hModule
0x18001a378  lea     rdx, ProcName; "NegotiateVersions"
0x18001a37f  call    cs:__imp_GetProcAddress
0x18001a386  nop     dword ptr [rax+rax+00h]
0x18001a38b  mov     rcx, [rbp+5Fh]
0x18001a38f  lea     r15, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001a396  mov     rbx, rax
0x18001a399  mov     r8, r15
0x18001a39c  lea     rax, aFailedToLoadAd; "Failed to load address of NegotiateVers"...
0x18001a3a3  mov     r9, rbx
0x18001a3a6  mov     edx, 0BD9h
0x18001a3ab  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18001a3b0  call    ??$Throw_GetLastErrorIfNullMsg@P6AJPEBUAVENC_VERSION_INFO@Avenc@Rdp@@PEAU123@1@Z$0A@@in1diag3@details@wil@@YAP6AJPEBUAVENC_VERSION_INFO@Avenc@Rdp@@PEAU345@1@ZPEAXIPEBDP6AJ011@Z3ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<long (*)(Rdp::Avenc::AVENC_VERSION_INFO const *,Rdp::Avenc::AVENC_VERSION_INFO *,Rdp::Avenc::AVENC_VERSION_INFO *),0>(void *,uint,char const *,long (*)(Rdp::Avenc::AVENC_VERSION_INFO const *,Rdp::Avenc::AVENC_VERSION_INFO *,Rdp::Avenc::AVENC_VERSION_INFO *),char const *,...)
0x18001a3b5  mov     ecx, [rsi+158h]
0x18001a3bb  lea     r8, [rsi+170h]
0x18001a3c2  mov     [rbp+57h+var_44], ecx
0x18001a3c5  lea     rdx, [rsi+160h]
0x18001a3cc  mov     ecx, [rsi+15Ch]
0x18001a3d2  mov     rax, rbx
0x18001a3d5  mov     [rbp+57h+var_40], ecx
0x18001a3d8  lea     rcx, [rbp+57h+var_48]
0x18001a3dc  mov     [rbp+57h+var_48], 10h
0x18001a3e3  mov     [rbp+57h+var_3C], edi
0x18001a3e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3eb  mov     rcx, [rbp+5Fh]; this
0x18001a3ef  lea     rdx, aFailedToNegoti; "Failed to negotiate versions with Avenc"
0x18001a3f6  mov     qword ptr [rsp+0E0h+var_C0], rdx; int
0x18001a3fb  mov     r9d, eax; char *
0x18001a3fe  mov     edx, 0BE9h; void *
0x18001a403  mov     r8, r15; unsigned int
0x18001a406  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001a40b  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001a410  mov     r8, [rax+8]
0x18001a414  mov     eax, [r8]
0x18001a417  cmp     eax, 4
0x18001a41a  jbe     loc_18001A4DC
0x18001a420  mov     rdx, 400000000000h
0x18001a42a  mov     rcx, r8
0x18001a42d  call    _tlgKeywordOn
0x18001a432  test    al, al
0x18001a434  jz      loc_18001A4DC
0x18001a43a  mov     eax, [rsi+17Ch]
0x18001a440  lea     rdx, byte_18004C6CD
0x18001a447  mov     [rbp+57h+var_80], eax
0x18001a44a  mov     rcx, r8
0x18001a44d  mov     eax, [rsi+178h]
0x18001a453  mov     [rbp+57h+var_7C], eax
0x18001a456  mov     eax, [rsi+174h]
0x18001a45c  mov     [rbp+57h+var_78], eax
0x18001a45f  mov     eax, [rsi+168h]
0x18001a465  mov     [rbp+57h+var_74], eax
0x18001a468  mov     eax, [rsi+164h]
0x18001a46e  mov     [rbp+57h+var_70], eax
0x18001a471  lea     rax, aAvencVersions; "Avenc versions"
0x18001a478  mov     [rbp+57h+var_60], rax
0x18001a47c  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x18001a483  mov     [rbp+57h+var_50], rax
0x18001a487  lea     rax, [rbp+57h+var_80]
0x18001a48b  mov     [rsp+0E0h+var_88], rax
0x18001a490  lea     rax, [rbp+57h+var_7C]
0x18001a494  mov     [rsp+0E0h+var_90], rax
0x18001a499  lea     rax, [rbp+57h+var_78]
0x18001a49d  mov     [rsp+0E0h+var_98], rax
0x18001a4a2  lea     rax, [rbp+57h+var_74]
0x18001a4a6  mov     [rsp+0E0h+var_A0], rax
0x18001a4ab  lea     rax, [rbp+57h+var_70]
0x18001a4af  mov     [rsp+0E0h+var_A8], rax
0x18001a4b4  lea     rax, [rbp+57h+var_60]
0x18001a4b8  mov     [rsp+0E0h+var_B0], rax
0x18001a4bd  lea     rax, [rbp+57h+var_58]
0x18001a4c1  mov     [rsp+0E0h+var_B8], rax
0x18001a4c6  lea     rax, [rbp+57h+var_50]
0x18001a4ca  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18001a4cf  mov     [rbp+57h+var_58], 1000000h
0x18001a4d7  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U4@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@6666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001a4dc  mov     eax, [rsi+17Ch]
0x18001a4e2  lea     r8, aCrdpidadapterP_1; "CRdpIdAdapter::ProcessLoadAvenc"
0x18001a4e9  mov     dword ptr [rsp+0E0h+var_98], eax
0x18001a4ed  lea     rdx, aAdapteravencve; "AdapterAvencVersion: Iface: %#x.%#x, Dl"...
0x18001a4f4  mov     eax, [rsi+178h]
0x18001a4fa  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001a501  mov     dword ptr [rsp+0E0h+var_A0], eax
0x18001a505  mov     r9, r15; char *
0x18001a508  mov     eax, [rsi+174h]
0x18001a50e  mov     dword ptr [rsp+0E0h+var_A8], eax
0x18001a512  mov     eax, [rsi+168h]
0x18001a518  mov     dword ptr [rsp+0E0h+var_B0], eax
0x18001a51c  mov     eax, [rsi+164h]
0x18001a522  mov     dword ptr [rsp+0E0h+var_B8], eax
0x18001a526  mov     dword ptr [rsp+0E0h+var_C0], 0BFAh; unsigned int
0x18001a52e  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001a533  test    r14, r14
0x18001a536  jz      short loc_18001A567
0x18001a538  mov     dword ptr [r14], 14h
0x18001a53f  mov     eax, [rsi+174h]
0x18001a545  mov     [r14+4], eax
0x18001a549  mov     eax, [rsi+178h]
0x18001a54f  mov     [r14+8], eax
0x18001a553  mov     eax, [rsi+164h]
0x18001a559  mov     [r14+0Ch], eax
0x18001a55d  mov     eax, [rsi+168h]
0x18001a563  mov     [r14+10h], eax
0x18001a567  lea     rdx, [r13+214h]; struct _GUID *
0x18001a56e  mov     rax, [rdx]
0x18001a571  cmp     rax, qword ptr cs:xmmword_180046C80
0x18001a578  jnz     short loc_18001A587
0x18001a57a  mov     rax, [rdx+8]
0x18001a57e  cmp     rax, qword ptr cs:xmmword_180046C80+8
0x18001a585  jz      short loc_18001A58F
0x18001a587  mov     rcx, rsi; this
0x18001a58a  call    ?ProcessStartProcessor@CRdpIdAdapter@@AEAAXAEBU_GUID@@@Z; CRdpIdAdapter::ProcessStartProcessor(_GUID const &)
0x18001a58f  mov     rcx, [rbp+57h+var_38]
0x18001a593  xor     rcx, rsp; StackCookie
0x18001a596  call    __security_check_cookie
0x18001a59b  mov     rbx, [rsp+0E0h+arg_18]
0x18001a5a3  add     rsp, 0B0h
0x18001a5aa  pop     r15
0x18001a5ac  pop     r14
0x18001a5ae  pop     r13
0x18001a5b0  pop     r12
0x18001a5b2  pop     rdi
0x18001a5b3  pop     rsi
0x18001a5b4  pop     rbp
0x18001a5b5  retn
```
