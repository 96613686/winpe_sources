# CtapHybridReencodeResponse

- ea: `0x180049e44`
- end: `0x18004a5d5`
- name: `CtapHybridReencodeResponse`
- size: `1937`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801082ac`

## callees

- `0x18001687c`
- `0x18001cd78`
- `0x18002a314`
- `0x1800328dc`
- `0x18003cf80`
- `0x18003d854`
- `0x18003e8cc`
- `0x180046768`
- `0x180049e44`
- `0x18004a5dc`
- `0x1800537a4`
- `0x18006c82c`
- `0x1800d1870`
- `0x1800d2d14`
- `0x1800d3830`
- `0x1800d4eb4`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a182`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a1be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a1d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a1ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a452`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a488`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a49e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a563`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a579`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a588`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a5a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a182`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a1be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a1d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a1ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a452`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a488`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a49e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a563`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a579`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a588`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a5a4`

## string_xrefs

- `0x180049f38`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x18004a0f3`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x18004a14b`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x18004a253`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x18004a3b1`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x18004a40f`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x18004a517`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CtapHybridReencodeResponse(__int64 a1, char a2, _QWORD *a3, __int64 a4, __int64 a5, __int64 a6)
{
  void *v8; // rdi
  unsigned int CredentialResponse; // eax
  unsigned int v10; // eax
  int v11; // edx
  int v12; // ebx
  int v13; // ebx
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  HLOCAL v18; // rcx
  HLOCAL v19; // rcx
  HLOCAL v20; // rcx
  unsigned int AssertionResponse; // eax
  unsigned int v22; // eax
  _QWORD *v23; // rax
  int v24; // edx
  int v25; // ebx
  int v26; // ebx
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  HLOCAL v31; // rcx
  HLOCAL v32; // rcx
  _QWORD *v33; // rcx
  unsigned int v34; // eax
  unsigned int v35; // eax
  HLOCAL v36; // rcx
  HLOCAL v37; // rcx
  bool v38; // zf
  HLOCAL v39; // rcx
  __int64 result; // rax
  unsigned int v41; // [rsp+20h] [rbp-148h]
  unsigned int v42; // [rsp+20h] [rbp-148h]
  unsigned int v43; // [rsp+20h] [rbp-148h]
  unsigned int v44; // [rsp+20h] [rbp-148h]
  void *v45; // [rsp+38h] [rbp-130h]
  int v46; // [rsp+40h] [rbp-128h] BYREF
  HLOCAL v47; // [rsp+48h] [rbp-120h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-118h] BYREF
  unsigned int v49; // [rsp+58h] [rbp-110h] BYREF
  HLOCAL v50; // [rsp+60h] [rbp-108h] BYREF
  HLOCAL v51; // [rsp+68h] [rbp-100h] BYREF
  HLOCAL *p_hMem; // [rsp+70h] [rbp-F8h] BYREF
  unsigned int v53[2]; // [rsp+78h] [rbp-F0h] BYREF
  HLOCAL v54; // [rsp+80h] [rbp-E8h]
  HLOCAL *v55; // [rsp+88h] [rbp-E0h] BYREF
  unsigned int v56[2]; // [rsp+90h] [rbp-D8h] BYREF
  HLOCAL v57; // [rsp+98h] [rbp-D0h]
  HLOCAL v58; // [rsp+A0h] [rbp-C8h] BYREF
  HLOCAL v59; // [rsp+A8h] [rbp-C0h] BYREF
  void *v60; // [rsp+B0h] [rbp-B8h] BYREF
  HLOCAL v61; // [rsp+B8h] [rbp-B0h] BYREF
  __int64 v62; // [rsp+C0h] [rbp-A8h]
  _BYTE v63[40]; // [rsp+D0h] [rbp-98h] BYREF
  unsigned __int16 v64; // [rsp+F8h] [rbp-70h]
  __int64 v65; // [rsp+100h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  try
  {
    v62 = a1;
    LODWORD(v58) = 0;
    v61 = 0;
    v49 = 0;
    v8 = 0;
    v60 = 0;
    if ( a2 == 1 )
    {
      std::vector<unsigned char>::_Assign_counted_range<unsigned char const *>(a5, *a3 + 1LL, a3[1] - (*a3 + 1LL));
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl'::`2'::impl) )
      {
        v47 = 0;
        v55 = &v47;
        *(_QWORD *)v56 = 0;
        LOBYTE(v57) = 1;
        CredentialResponse = CtapCborDecodeMakeCredentialResponse(
                               *((_DWORD *)a3 + 2) - (unsigned int)*a3 - 2,
                               *(_DWORD *)a3 + 2,
                               (unsigned int)v56,
                               0,
                               0);
        v10 = CtapCborErrorToWin32Error(CredentialResponse);
        if ( v10 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x190,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
            (const char *)v10,
            v41);
        wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v55);
        v51 = 0;
        v11 = *((_DWORD *)v47 + 33);
        if ( v11 && *(_DWORD *)(a4 + 160) )
        {
          v46 = 0;
          v50 = 0;
          v55 = &v50;
          *(_QWORD *)v56 = 0;
          LOBYTE(v57) = 1;
          v12 = CtapCborDecodeExtension((int)L"prf", v11, *((_QWORD *)v47 + 17), (int)&v46, (__int64)v56, 0, 0, v45);
          wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v55);
          if ( !v12 )
          {
            v55 = &v51;
            *(_QWORD *)v56 = 0;
            LOBYTE(v57) = 1;
            v13 = CtapCborDecodePrfResults((unsigned int)v46, v50, v56);
            wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v55);
            if ( !v13 )
            {
              memset_0(v63, 0, 0x58u);
              if ( !(unsigned int)CtapCborUnpackAuthenticatorData(*((unsigned int *)v47 + 4), *((_QWORD *)v47 + 3), v63) )
              {
                v55 = (HLOCAL *)v64;
                *(_QWORD *)v56 = v65;
                v57 = v51;
                v46 = 0;
                v58 = 0;
                p_hMem = &v58;
                *(_QWORD *)v53 = 0;
                LOBYTE(v54) = 1;
                v14 = CtapCborEncodeCredWithHmacSecret(&v55, &v46, v53, 0);
                v15 = CtapCborErrorToWin32Error(v14);
                if ( v15 )
                  wil::details::in1diag3::Throw_Win32(
                    retaddr,
                    (void *)0x1B4,
                    (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
                    (const char *)v15,
                    v42);
                wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
                hMem = 0;
                v16 = CtapCborEncodeAppendToArray((unsigned int)&v49, (unsigned int)&hMem, v46, (_DWORD)v58, 0);
                v17 = CtapCborErrorToWin32Error(v16);
                if ( v17 )
                  wil::details::in1diag3::Throw_Win32(
                    retaddr,
                    (void *)0x1BB,
                    (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
                    (const char *)v17,
                    v43);
                wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::operator=(
                  &v60,
                  &hMem);
                if ( hMem )
                  LocalFree(hMem);
                v8 = v60;
                std::vector<unsigned char>::_Assign_counted_range<unsigned char const *>(a6, v60, v49);
                v18 = v58;
                v58 = 0;
                if ( v18 )
                  LocalFree(v18);
              }
            }
          }
          v19 = v50;
          v50 = 0;
          if ( v19 )
            LocalFree(v19);
        }
        v20 = v51;
        v51 = 0;
        if ( v20 )
          LocalFree(v20);
LABEL_48:
        v37 = v47;
        v38 = v47 == 0;
        v47 = 0;
        if ( !v38 )
          LocalFree(v37);
      }
    }
    else if ( a2 == 2 )
    {
      v47 = 0;
      p_hMem = &v47;
      *(_QWORD *)v53 = 0;
      LOBYTE(v54) = 1;
      AssertionResponse = CtapCborDecodeGetAssertionResponse(
                            *((_DWORD *)a3 + 2) - (unsigned int)*a3 - 2,
                            *(_DWORD *)a3 + 2,
                            (unsigned int)v53,
                            0,
                            0);
      v22 = CtapCborErrorToWin32Error(AssertionResponse);
      if ( v22 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1CB,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
          (const char *)v22,
          v44);
      wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
      hMem = 0;
      v23 = v47;
      v24 = *((_DWORD *)v47 + 50);
      if ( v24 && *(_DWORD *)(a4 + 160) )
      {
        v46 = 0;
        v50 = 0;
        p_hMem = &v50;
        *(_QWORD *)v53 = 0;
        LOBYTE(v54) = 1;
        v25 = CtapCborDecodeExtension((int)L"prf", v24, *((_QWORD *)v47 + 26), (int)&v46, (__int64)v53, 0, 0, v45);
        wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
        if ( !v25 )
        {
          p_hMem = &hMem;
          *(_QWORD *)v53 = 0;
          LOBYTE(v54) = 1;
          v26 = CtapCborDecodePrfResults((unsigned int)v46, v50, v53);
          wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
          if ( !v26 )
          {
            HIDWORD(p_hMem) = 0;
            LODWORD(p_hMem) = *((_DWORD *)v47 + 9);
            *(_QWORD *)v53 = *((_QWORD *)v47 + 5);
            v54 = hMem;
            v46 = 0;
            v51 = 0;
            v55 = &v51;
            *(_QWORD *)v56 = 0;
            LOBYTE(v57) = 1;
            v27 = CtapCborEncodeCredWithHmacSecret(&p_hMem, &v46, v56, 0);
            v28 = CtapCborErrorToWin32Error(v27);
            if ( v28 )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x1E9,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
                (const char *)v28,
                v44);
            wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v55);
            v59 = 0;
            v29 = CtapCborEncodeAppendToArray((unsigned int)&v49, (unsigned int)&v59, v46, (_DWORD)v51, 0);
            v30 = CtapCborErrorToWin32Error(v29);
            if ( v30 )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x1F0,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
                (const char *)v30,
                v44);
            wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::operator=(
              &v60,
              &v59);
            if ( v59 )
              LocalFree(v59);
            v8 = v60;
            std::vector<unsigned char>::_Assign_counted_range<unsigned char const *>(a6, v60, v49);
            v31 = v51;
            v51 = 0;
            if ( v31 )
              LocalFree(v31);
          }
        }
        v32 = v50;
        v50 = 0;
        if ( v32 )
          LocalFree(v32);
        v23 = v47;
      }
      v33 = (_QWORD *)v23[21];
      if ( v33 )
      {
        v33[4] = 0;
        v33[3] = 0;
        v33[2] = 0;
        v23 = v47;
      }
      *((_DWORD *)v23 + 44) = 0;
      p_hMem = &v61;
      *(_QWORD *)v53 = 0;
      LOBYTE(v54) = 1;
      v34 = CtapCborEncodeGetAssertionResponse(v47, &v58, v53, 0);
      v35 = CtapCborErrorToWin32Error(v34);
      if ( v35 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x205,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
          (const char *)v35,
          v44);
      wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
      std::vector<unsigned char>::_Assign_counted_range<unsigned char const *>(a5, v61, (unsigned int)v58);
      v36 = hMem;
      hMem = 0;
      if ( v36 )
        LocalFree(v36);
      goto LABEL_48;
    }
    if ( v8 )
      LocalFree(v8);
    v39 = v61;
    v61 = 0;
    if ( v39 )
      LocalFree(v39);
    result = 0;
  }
  catch ( ... )
  {
    std::string::_Assign<char>(v62, "FAILED_TO_REENCODE_RESPONSE", 27);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180049e44  mov     r11, rsp
0x180049e47  mov     [r11+10h], rbx
0x180049e4b  push    rsi
0x180049e4c  push    rdi
0x180049e4d  push    r12
0x180049e4f  push    r14
0x180049e51  push    r15
0x180049e53  sub     rsp, 140h
0x180049e5a  mov     rax, cs:__security_cookie
0x180049e61  xor     rax, rsp
0x180049e64  mov     [rsp+168h+var_38], rax
0x180049e6c  mov     rsi, r9
0x180049e6f  mov     rbx, r8
0x180049e72  mov     [rsp+168h+var_A8], rcx
0x180049e7a  mov     r14, [rsp+168h+arg_20]
0x180049e82  mov     r15, [rsp+168h+arg_28]
0x180049e8a  xor     r12d, r12d
0x180049e8d  mov     [r11-0C8h], r12d
0x180049e94  mov     [r11-0B0h], r12
0x180049e9b  mov     [rsp+168h+var_110], r12d
0x180049ea0  mov     edi, r12d
0x180049ea3  mov     [r11-0B8h], r12
0x180049eaa  cmp     dl, 1
0x180049ead  jnz     loc_18004A1F6
0x180049eb3  mov     rdx, [r8]
0x180049eb6  inc     rdx
0x180049eb9  mov     r8, [r8+8]
0x180049ebd  sub     r8, rdx
0x180049ec0  mov     rcx, r14
0x180049ec3  call    ??$_Assign_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEBE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar const *>(uchar const *,unsigned __int64)
0x180049ec8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF> `wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl(void)'::`2'::impl
0x180049ecf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(void)
0x180049ed4  test    al, al
0x180049ed6  jz      loc_18004A580
0x180049edc  mov     [rsp+168h+var_120], r12
0x180049ee1  lea     rax, [rsp+168h+var_120]
0x180049ee6  mov     [rsp+168h+var_E0], rax
0x180049eee  mov     qword ptr [rsp+168h+var_D8], r12
0x180049ef6  mov     byte ptr [rsp+168h+var_D0], 1
0x180049efe  mov     rax, [rbx]
0x180049f01  lea     rdx, [rax+2]
0x180049f05  mov     ecx, [rbx+8]
0x180049f08  sub     ecx, eax
0x180049f0a  sub     ecx, 2
0x180049f0d  mov     qword ptr [rsp+168h+var_148], r12; unsigned int
0x180049f12  xor     r9d, r9d
0x180049f15  lea     r8, [rsp+168h+var_D8]
0x180049f1d  call    CtapCborDecodeMakeCredentialResponse
0x180049f22  mov     ecx, eax
0x180049f24  call    CtapCborErrorToWin32Error
0x180049f29  mov     rcx, [rsp+168h]; this
0x180049f31  test    eax, eax
0x180049f33  jz      short loc_180049F4A
0x180049f35  mov     r9d, eax; char *
0x180049f38  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180049f3f  mov     edx, 190h; void *
0x180049f44  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180049f4a  lea     rcx, [rsp+168h+var_E0]
0x180049f52  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180049f57  mov     [rsp+168h+var_100], r12
0x180049f5c  mov     r8, [rsp+168h+var_120]
0x180049f61  mov     edx, [r8+84h]; int
0x180049f68  test    edx, edx
0x180049f6a  jz      loc_18004A1DB
0x180049f70  cmp     [rsi+0A0h], r12d
0x180049f77  jz      loc_18004A1DB
0x180049f7d  mov     [rsp+168h+var_128], r12d
0x180049f82  mov     [rsp+168h+var_108], r12
0x180049f87  lea     rax, [rsp+168h+var_108]
0x180049f8c  mov     [rsp+168h+var_E0], rax
0x180049f94  mov     qword ptr [rsp+168h+var_D8], r12
0x180049f9c  mov     byte ptr [rsp+168h+var_D0], 1
0x180049fa4  mov     [rsp+168h+var_138], r12; __int64
0x180049fa9  mov     [rsp+168h+var_140], r12; __int64
0x180049fae  lea     rax, [rsp+168h+var_D8]
0x180049fb6  mov     qword ptr [rsp+168h+var_148], rax; unsigned int
0x180049fbb  lea     r9, [rsp+168h+var_128]; int
0x180049fc0  mov     r8, [r8+88h]; int
0x180049fc7  lea     rcx, aPrf_0; "prf"
0x180049fce  call    CtapCborDecodeExtension
0x180049fd3  mov     ebx, eax
0x180049fd5  lea     rcx, [rsp+168h+var_E0]
0x180049fdd  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180049fe2  test    ebx, ebx
0x180049fe4  jnz     loc_18004A1C5
0x180049fea  lea     rax, [rsp+168h+var_100]
0x180049fef  mov     [rsp+168h+var_E0], rax
0x180049ff7  mov     qword ptr [rsp+168h+var_D8], r12
0x180049fff  mov     byte ptr [rsp+168h+var_D0], 1
0x18004a007  lea     r8, [rsp+168h+var_D8]
0x18004a00f  mov     rdx, [rsp+168h+var_108]
0x18004a014  mov     ecx, [rsp+168h+var_128]
0x18004a018  call    CtapCborDecodePrfResults
0x18004a01d  mov     ebx, eax
0x18004a01f  lea     rcx, [rsp+168h+var_E0]
0x18004a027  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18004a02c  test    ebx, ebx
0x18004a02e  jnz     loc_18004A1C5
0x18004a034  xor     edx, edx; Val
0x18004a036  lea     r8d, [rbx+58h]; Size
0x18004a03a  lea     rcx, [rsp+168h+var_98]; void *
0x18004a042  call    memset_0
0x18004a047  lea     r8, [rsp+168h+var_98]
0x18004a04f  mov     rcx, [rsp+168h+var_120]
0x18004a054  mov     rdx, [rcx+18h]
0x18004a058  mov     ecx, [rcx+10h]
0x18004a05b  call    CtapCborUnpackAuthenticatorData
0x18004a060  test    eax, eax
0x18004a062  jnz     loc_18004A1C5
0x18004a068  mov     dword ptr [rsp+168h+var_E0+4], r12d
0x18004a070  movzx   eax, [rsp+168h+var_70]
0x18004a078  mov     dword ptr [rsp+168h+var_E0], eax
0x18004a07f  mov     rax, [rsp+168h+var_68]
0x18004a087  mov     qword ptr [rsp+168h+var_D8], rax
0x18004a08f  mov     rax, [rsp+168h+var_100]
0x18004a094  mov     [rsp+168h+var_D0], rax
0x18004a09c  mov     [rsp+168h+var_128], r12d
0x18004a0a1  mov     [rsp+168h+var_C8], r12
0x18004a0a9  lea     rax, [rsp+168h+var_C8]
0x18004a0b1  mov     [rsp+168h+var_F8], rax
0x18004a0b6  mov     qword ptr [rsp+168h+var_F0], r12
0x18004a0bb  mov     byte ptr [rsp+168h+var_E8], 1
0x18004a0c3  xor     r9d, r9d
0x18004a0c6  lea     r8, [rsp+168h+var_F0]
0x18004a0cb  lea     rdx, [rsp+168h+var_128]
0x18004a0d0  lea     rcx, [rsp+168h+var_E0]
0x18004a0d8  call    CtapCborEncodeCredWithHmacSecret
0x18004a0dd  mov     ecx, eax
0x18004a0df  call    CtapCborErrorToWin32Error
0x18004a0e4  mov     rcx, [rsp+168h]; this
0x18004a0ec  test    eax, eax
0x18004a0ee  jz      short loc_18004A105
0x18004a0f0  mov     r9d, eax; char *
0x18004a0f3  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18004a0fa  mov     edx, 1B4h; void *
0x18004a0ff  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004a105  lea     rcx, [rsp+168h+var_F8]
0x18004a10a  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18004a10f  mov     [rsp+168h+hMem], r12
0x18004a114  mov     qword ptr [rsp+168h+var_148], r12; unsigned int
0x18004a119  mov     r9, [rsp+168h+var_C8]
0x18004a121  mov     r8d, [rsp+168h+var_128]
0x18004a126  lea     rdx, [rsp+168h+hMem]
0x18004a12b  lea     rcx, [rsp+168h+var_110]
0x18004a130  call    CtapCborEncodeAppendToArray
0x18004a135  mov     ecx, eax
0x18004a137  call    CtapCborErrorToWin32Error
0x18004a13c  mov     rcx, [rsp+168h]; this
0x18004a144  test    eax, eax
0x18004a146  jz      short loc_18004A15C
0x18004a148  mov     r9d, eax; char *
0x18004a14b  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18004a152  mov     edx, 1BBh; void *
0x18004a157  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004a15c  mov     rax, [rsp+168h+hMem]
0x18004a161  mov     [rsp+168h+hMem], rax
0x18004a166  lea     rdx, [rsp+168h+hMem]
0x18004a16b  lea     rcx, [rsp+168h+var_B8]
0x18004a173  call    ??4?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::operator=(wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &&)
0x18004a178  mov     rcx, [rsp+168h+hMem]; hMem
0x18004a17d  test    rcx, rcx
0x18004a180  jz      short loc_18004A188
0x18004a182  call    cs:__imp_LocalFree
0x18004a188  mov     rdi, [rsp+168h+var_B8]
0x18004a190  mov     r8, rdi
0x18004a193  sub     r8, rdi
0x18004a196  mov     eax, [rsp+168h+var_110]
0x18004a19a  add     r8, rax
0x18004a19d  mov     rdx, rdi
0x18004a1a0  mov     rcx, r15
0x18004a1a3  call    ??$_Assign_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEBE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar const *>(uchar const *,unsigned __int64)
0x18004a1a8  nop
0x18004a1a9  mov     rcx, [rsp+168h+var_C8]; hMem
0x18004a1b1  mov     [rsp+168h+var_C8], r12
0x18004a1b9  test    rcx, rcx
0x18004a1bc  jz      short loc_18004A1C5
0x18004a1be  call    cs:__imp_LocalFree
0x18004a1c4  nop
0x18004a1c5  mov     rcx, [rsp+168h+var_108]; hMem
0x18004a1ca  mov     [rsp+168h+var_108], r12
0x18004a1cf  test    rcx, rcx
0x18004a1d2  jz      short loc_18004A1DB
0x18004a1d4  call    cs:__imp_LocalFree
0x18004a1da  nop
0x18004a1db  mov     rcx, [rsp+168h+var_100]; hMem
0x18004a1e0  mov     [rsp+168h+var_100], r12
0x18004a1e5  test    rcx, rcx
0x18004a1e8  jz      short loc_18004A1F1
0x18004a1ea  call    cs:__imp_LocalFree
0x18004a1f0  nop
0x18004a1f1  jmp     loc_18004A56A
0x18004a1f6  cmp     dl, 2
0x18004a1f9  jnz     loc_18004A580
0x18004a1ff  mov     [rsp+168h+var_120], r12
0x18004a204  lea     rax, [rsp+168h+var_120]
0x18004a209  mov     [rsp+168h+var_F8], rax
0x18004a20e  mov     qword ptr [rsp+168h+var_F0], r12
0x18004a213  mov     byte ptr [rsp+168h+var_E8], 1
0x18004a21b  mov     rax, [r8]
0x18004a21e  lea     rdx, [rax+2]
0x18004a222  mov     ecx, [r8+8]
0x18004a226  sub     ecx, eax
0x18004a228  sub     ecx, 2
0x18004a22b  mov     qword ptr [rsp+168h+var_148], r12; unsigned int
0x18004a230  xor     r9d, r9d
0x18004a233  lea     r8, [rsp+168h+var_F0]
0x18004a238  call    CtapCborDecodeGetAssertionResponse
0x18004a23d  mov     ecx, eax
0x18004a23f  call    CtapCborErrorToWin32Error
0x18004a244  mov     rcx, [rsp+168h]; this
0x18004a24c  test    eax, eax
0x18004a24e  jz      short loc_18004A265
0x18004a250  mov     r9d, eax; char *
0x18004a253  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18004a25a  mov     edx, 1CBh; void *
0x18004a25f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004a265  lea     rcx, [rsp+168h+var_F8]
0x18004a26a  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18004a26f  mov     [rsp+168h+hMem], r12
0x18004a274  mov     rax, [rsp+168h+var_120]
0x18004a279  mov     edx, [rax+0C8h]; int
0x18004a27f  test    edx, edx
0x18004a281  jz      loc_18004A4A9
0x18004a287  cmp     [rsi+0A0h], r12d
0x18004a28e  jz      loc_18004A4A9
0x18004a294  mov     [rsp+168h+var_128], r12d
0x18004a299  mov     [rsp+168h+var_108], r12
0x18004a29e  lea     rcx, [rsp+168h+var_108]
0x18004a2a3  mov     [rsp+168h+var_F8], rcx
0x18004a2a8  mov     qword ptr [rsp+168h+var_F0], r12
0x18004a2ad  mov     byte ptr [rsp+168h+var_E8], 1
0x18004a2b5  mov     [rsp+168h+var_138], r12; __int64
0x18004a2ba  mov     [rsp+168h+var_140], r12; __int64
0x18004a2bf  lea     rcx, [rsp+168h+var_F0]
0x18004a2c4  mov     qword ptr [rsp+168h+var_148], rcx; unsigned int
0x18004a2c9  lea     r9, [rsp+168h+var_128]; int
0x18004a2ce  mov     r8, [rax+0D0h]; int
0x18004a2d5  lea     rcx, aPrf_0; "prf"
0x18004a2dc  call    CtapCborDecodeExtension
0x18004a2e1  mov     ebx, eax
0x18004a2e3  lea     rcx, [rsp+168h+var_F8]
0x18004a2e8  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18004a2ed  test    ebx, ebx
0x18004a2ef  jnz     loc_18004A48F
0x18004a2f5  lea     rax, [rsp+168h+hMem]
0x18004a2fa  mov     [rsp+168h+var_F8], rax
0x18004a2ff  mov     qword ptr [rsp+168h+var_F0], r12
0x18004a304  mov     byte ptr [rsp+168h+var_E8], 1
0x18004a30c  lea     r8, [rsp+168h+var_F0]
0x18004a311  mov     rdx, [rsp+168h+var_108]
0x18004a316  mov     ecx, [rsp+168h+var_128]
0x18004a31a  call    CtapCborDecodePrfResults
0x18004a31f  mov     ebx, eax
0x18004a321  lea     rcx, [rsp+168h+var_F8]
0x18004a326  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18004a32b  test    ebx, ebx
0x18004a32d  jnz     loc_18004A48F
0x18004a333  mov     dword ptr [rsp+168h+var_F8+4], r12d
0x18004a338  mov     rax, [rsp+168h+var_120]
0x18004a33d  mov     ecx, [rax+24h]
0x18004a340  mov     dword ptr [rsp+168h+var_F8], ecx
0x18004a344  mov     rcx, [rax+28h]
0x18004a348  mov     qword ptr [rsp+168h+var_F0], rcx
0x18004a34d  mov     rax, [rsp+168h+hMem]
0x18004a352  mov     [rsp+168h+var_E8], rax
0x18004a35a  mov     [rsp+168h+var_128], r12d
0x18004a35f  mov     [rsp+168h+var_100], r12
0x18004a364  lea     rax, [rsp+168h+var_100]
0x18004a369  mov     [rsp+168h+var_E0], rax
0x18004a371  mov     qword ptr [rsp+168h+var_D8], r12
0x18004a379  mov     byte ptr [rsp+168h+var_D0], 1
0x18004a381  xor     r9d, r9d
0x18004a384  lea     r8, [rsp+168h+var_D8]
0x18004a38c  lea     rdx, [rsp+168h+var_128]
0x18004a391  lea     rcx, [rsp+168h+var_F8]
0x18004a396  call    CtapCborEncodeCredWithHmacSecret
0x18004a39b  mov     ecx, eax
0x18004a39d  call    CtapCborErrorToWin32Error
0x18004a3a2  mov     rcx, [rsp+168h]; this
0x18004a3aa  test    eax, eax
0x18004a3ac  jz      short loc_18004A3C3
0x18004a3ae  mov     r9d, eax; char *
0x18004a3b1  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18004a3b8  mov     edx, 1E9h; void *
0x18004a3bd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004a3c3  lea     rcx, [rsp+168h+var_E0]
0x18004a3cb  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18004a3d0  mov     [rsp+168h+var_C0], r12
0x18004a3d8  mov     qword ptr [rsp+168h+var_148], r12; unsigned int
0x18004a3dd  mov     r9, [rsp+168h+var_100]
0x18004a3e2  mov     r8d, [rsp+168h+var_128]
0x18004a3e7  lea     rdx, [rsp+168h+var_C0]
0x18004a3ef  lea     rcx, [rsp+168h+var_110]
0x18004a3f4  call    CtapCborEncodeAppendToArray
0x18004a3f9  mov     ecx, eax
0x18004a3fb  call    CtapCborErrorToWin32Error
0x18004a400  mov     rcx, [rsp+168h]; this
0x18004a408  test    eax, eax
0x18004a40a  jz      short loc_18004A420
0x18004a40c  mov     r9d, eax; char *
  ... truncated ...
```
