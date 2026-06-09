# Microsoft::Windows::Autopilot::HttpNetworkWrapper::RetrieveData(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &)

- ea: `0x1801b6514`
- end: `0x1801b69a7`
- name: `?RetrieveData@HttpNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@Z`
- size: `1171`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801b6c90`

## callees

- `0x180063f8b`
- `0x180067e34`
- `0x180067e54`
- `0x18006bb78`
- `0x180080c10`
- `0x1800e1e8c`
- `0x18019d34c`
- `0x18019d534`
- `0x18019d668`
- `0x1801b5d5c`
- `0x1801b6514`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b668e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b6788`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b668e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b6788`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1801b65a1`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1801b65a1`
- `WINHTTP!WinHttpReadData` at `0x1801b681c`
- `WINHTTP!WinHttpReadData` at `0x1801b681c`

## string_xrefs

- `0x1801b655e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b65b6`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b66b9`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b67ba`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b6831`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b68b0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b691c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b6974`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Autopilot::HttpNetworkWrapper::RetrieveData(__int64 a1, __int64 a2, __int64 a3)
{
  int ContentTypeFromHeaders; // eax
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 result; // rax
  SIZE_T v9; // rbx
  unsigned int LastError; // ebx
  char *v11; // rdi
  int v12; // r14d
  __int64 i; // rbx
  __int64 v14; // rsi
  DWORD v15; // edi
  char *v16; // rdx
  const char *v17; // r9
  unsigned int v18; // ebx
  DWORD dwNumberOfBytesRead; // [rsp+20h] [rbp-58h] BYREF
  __int64 v20; // [rsp+28h] [rbp-50h]
  char *v21; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-40h]
  __int128 v23; // [rsp+40h] [rbp-38h] BYREF
  __int64 v24; // [rsp+50h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  DWORD dwNumberOfBytesAvailable; // [rsp+98h] [rbp+20h] BYREF

  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
    {
      ContentTypeFromHeaders = Microsoft::Windows::Autopilot::ExtractContentTypeFromHeaders(*(HINTERNET *)(a1 + 24));
      v6 = ContentTypeFromHeaders;
      if ( ContentTypeFromHeaders >= 0 )
      {
        v23 = 0;
        v24 = 0;
        v9 = 0;
        while ( 1 )
        {
          dwNumberOfBytesAvailable = 0;
          if ( !WinHttpQueryDataAvailable(*(HINTERNET *)(a1 + 24), &dwNumberOfBytesAvailable) )
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x1E6,
                          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\httpnetworkwrapper.cpp",
                          v7);
            if ( (_QWORD)v23 )
            {
              std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(
                v23,
                *((_QWORD *)&v23 + 1));
              std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF0uLL);
            }
            return LastError;
          }
          if ( !dwNumberOfBytesAvailable )
          {
            if ( (_DWORD)v9 )
            {
              if ( *((_QWORD *)&v23 + 1) - (_QWORD)v23 == 16 )
              {
                wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator=(
                  a3,
                  v23);
                if ( (_QWORD)v23 )
                {
                  std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(
                    v23,
                    *((_QWORD *)&v23 + 1));
                  std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF0uLL);
                }
                return 0;
              }
              else
              {
                v11 = (char *)CoTaskMemAlloc(v9);
                v21 = v11;
                v22 = v9;
                if ( v11 )
                {
                  v12 = 0;
                  v14 = *((_QWORD *)&v23 + 1);
                  for ( i = v23; i != v14; i += 16 )
                  {
                    memcpy_0(&v11[v12], *(const void **)i, *(_QWORD *)(i + 8));
                    v12 += *(_DWORD *)(i + 8);
                  }
                  wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator=(
                    a3,
                    &v21);
                  wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v21);
                  if ( (_QWORD)v23 )
                  {
                    std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(
                      v23,
                      *((_QWORD *)&v23 + 1));
                    std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF0uLL);
                  }
                  return 0;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x207,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\httpnetworkwrapper.cpp",
                    (const char *)0x8007000ELL,
                    dwNumberOfBytesRead);
                  wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v21);
                  if ( (_QWORD)v23 )
                  {
                    std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(
                      v23,
                      *((_QWORD *)&v23 + 1));
                    std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF0uLL);
                  }
                  return 2147942414LL;
                }
              }
            }
            else
            {
              if ( (_QWORD)v23 )
              {
                std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(
                  v23,
                  *((_QWORD *)&v23 + 1));
                std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF0uLL);
              }
              return 0;
            }
          }
          v15 = dwNumberOfBytesAvailable;
          v20 = dwNumberOfBytesAvailable;
          v16 = (char *)CoTaskMemAlloc(dwNumberOfBytesAvailable);
          v21 = v16;
          v22 = __PAIR64__(HIDWORD(v20), v15);
          if ( !v16 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1ED,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\httpnetworkwrapper.cpp",
              (const char *)0x8007000ELL,
              dwNumberOfBytesRead);
            wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v21);
            if ( (_QWORD)v23 )
            {
              std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(
                v23,
                *((_QWORD *)&v23 + 1));
              std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF0uLL);
            }
            return 2147942414LL;
          }
          dwNumberOfBytesRead = 0;
          if ( !WinHttpReadData(*(HINTERNET *)(a1 + 24), v16, v15, &dwNumberOfBytesRead) )
          {
            v18 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1F4,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\httpnetworkwrapper.cpp",
                    v17);
            wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v21);
            if ( (_QWORD)v23 )
            {
              std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(
                v23,
                *((_QWORD *)&v23 + 1));
              std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF0uLL);
            }
            return v18;
          }
          std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::emplace_back<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(
            &v23,
            &v21);
          if ( dwNumberOfBytesRead + (unsigned int)v9 < (unsigned int)v9 )
            break;
          if ( dwNumberOfBytesRead != dwNumberOfBytesAvailable )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1FA,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\httpnetworkwrapper.cpp",
              (const char *)0x8000FFFFLL,
              dwNumberOfBytesRead);
            wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v21);
            if ( (_QWORD)v23 )
            {
              std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(
                v23,
                *((_QWORD *)&v23 + 1));
              std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF0uLL);
            }
            return 2147549183LL;
          }
          v9 = dwNumberOfBytesRead + (unsigned int)v9;
          wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v21);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F7,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\httpnetworkwrapper.cpp",
          (const char *)0x80070216LL,
          dwNumberOfBytesRead);
        wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v21);
        if ( (_QWORD)v23 )
        {
          std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(
            v23,
            *((_QWORD *)&v23 + 1));
          std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF0uLL);
        }
        result = 2147942934LL;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1DF,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\httpnetworkwrapper.cpp",
          (const char *)(unsigned int)ContentTypeFromHeaders,
          dwNumberOfBytesRead);
        result = v6;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DD,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\httpnetworkwrapper.cpp",
        (const char *)0x80004001LL,
        dwNumberOfBytesRead);
      result = 2147500033LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x215,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\httpnetworkwrapper.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x1801b6514  mov     [rsp+arg_0], rbx
0x1801b6519  mov     [rsp+arg_8], rsi
0x1801b651e  push    rdi
0x1801b651f  push    r14
0x1801b6521  push    r15
0x1801b6523  sub     rsp, 60h
0x1801b6527  mov     r15, r8
0x1801b652a  mov     rbx, rdx
0x1801b652d  mov     rsi, rcx
0x1801b6530  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1801b6537  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1801b653c  test    al, al
0x1801b653e  jz      loc_1801B6967
0x1801b6544  mov     rdx, rbx
0x1801b6547  mov     rcx, [rsi+18h]; hRequest
0x1801b654b  call    ?ExtractContentTypeFromHeaders@Autopilot@Windows@Microsoft@@YAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::ExtractContentTypeFromHeaders(void *,std::wstring &)
0x1801b6550  mov     ebx, eax
0x1801b6552  test    eax, eax
0x1801b6554  jns     short loc_1801B6576
0x1801b6556  mov     rcx, [rsp+78h]; this
0x1801b655b  mov     r9d, eax; char *
0x1801b655e  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b6565  mov     edx, 1DFh; void *
0x1801b656a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b656f  mov     eax, ebx
0x1801b6571  jmp     loc_1801B6990
0x1801b6576  xorps   xmm0, xmm0
0x1801b6579  movdqu  [rsp+78h+var_38], xmm0
0x1801b657f  mov     [rsp+78h+var_28], 0
0x1801b6588  xor     ebx, ebx
0x1801b658a  mov     [rsp+78h+dwNumberOfBytesAvailable], 0
0x1801b6595  lea     rdx, [rsp+78h+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x1801b659d  mov     rcx, [rsi+18h]; hRequest
0x1801b65a1  call    cs:__imp_WinHttpQueryDataAvailable
0x1801b65a8  nop     dword ptr [rax+rax+00h]
0x1801b65ad  test    eax, eax
0x1801b65af  jnz     short loc_1801B65FA
0x1801b65b1  mov     rcx, [rsp+78h]; this
0x1801b65b6  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b65bd  mov     edx, 1E6h; void *
0x1801b65c2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801b65c7  mov     ebx, eax
0x1801b65c9  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b65ce  test    rcx, rcx
0x1801b65d1  jz      short loc_1801B65F3
0x1801b65d3  mov     rdx, qword ptr [rsp+78h+var_38+8]
0x1801b65d8  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801b65dd  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b65e2  mov     rdx, [rsp+78h+var_28]
0x1801b65e7  sub     rdx, rcx
0x1801b65ea  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801b65ee  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801b65f3  mov     eax, ebx
0x1801b65f5  jmp     loc_1801B6990
0x1801b65fa  mov     eax, [rsp+78h+dwNumberOfBytesAvailable]
0x1801b6601  test    eax, eax
0x1801b6603  jnz     loc_1801B677D
0x1801b6609  test    ebx, ebx
0x1801b660b  jnz     short loc_1801B663E
0x1801b660d  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b6612  test    rcx, rcx
0x1801b6615  jz      short loc_1801B6637
0x1801b6617  mov     rdx, qword ptr [rsp+78h+var_38+8]
0x1801b661c  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801b6621  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b6626  mov     rdx, [rsp+78h+var_28]
0x1801b662b  sub     rdx, rcx
0x1801b662e  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801b6632  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801b6637  xor     eax, eax
0x1801b6639  jmp     loc_1801B6990
0x1801b663e  mov     rax, qword ptr [rsp+78h+var_38+8]
0x1801b6643  mov     rdx, qword ptr [rsp+78h+var_38]
0x1801b6648  sub     rax, rdx
0x1801b664b  cmp     rax, 10h
0x1801b664f  jnz     short loc_1801B668B
0x1801b6651  mov     rcx, r15
0x1801b6654  call    ??4?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator=(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &&)
0x1801b6659  nop
0x1801b665a  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b665f  test    rcx, rcx
0x1801b6662  jz      short loc_1801B6684
0x1801b6664  mov     rdx, qword ptr [rsp+78h+var_38+8]
0x1801b6669  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801b666e  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b6673  mov     rdx, [rsp+78h+var_28]
0x1801b6678  sub     rdx, rcx
0x1801b667b  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801b667f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801b6684  xor     eax, eax
0x1801b6686  jmp     loc_1801B6990
0x1801b668b  mov     rcx, rbx; cb
0x1801b668e  call    cs:__imp_CoTaskMemAlloc
0x1801b6695  nop     dword ptr [rax+rax+00h]
0x1801b669a  mov     rdi, rax
0x1801b669d  mov     [rsp+78h+var_48], rax
0x1801b66a2  mov     [rsp+78h+var_40], rbx
0x1801b66a7  test    rax, rax
0x1801b66aa  jnz     short loc_1801B6706
0x1801b66ac  mov     rcx, [rsp+78h]; this
0x1801b66b1  mov     ebx, 8007000Eh
0x1801b66b6  mov     r9d, ebx; char *
0x1801b66b9  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b66c0  mov     edx, 207h; void *
0x1801b66c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b66ca  lea     rcx, [rsp+78h+var_48]
0x1801b66cf  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b66d4  nop
0x1801b66d5  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b66da  test    rcx, rcx
0x1801b66dd  jz      short loc_1801B66FF
0x1801b66df  mov     rdx, qword ptr [rsp+78h+var_38+8]
0x1801b66e4  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801b66e9  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b66ee  mov     rdx, [rsp+78h+var_28]
0x1801b66f3  sub     rdx, rcx
0x1801b66f6  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801b66fa  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801b66ff  mov     eax, ebx
0x1801b6701  jmp     loc_1801B6990
0x1801b6706  xor     r14d, r14d
0x1801b6709  mov     rbx, qword ptr [rsp+78h+var_38]
0x1801b670e  mov     rsi, qword ptr [rsp+78h+var_38+8]
0x1801b6713  jmp     short loc_1801B672F
0x1801b6715  mov     ecx, r14d
0x1801b6718  add     rcx, rdi; void *
0x1801b671b  mov     r8, [rbx+8]; Size
0x1801b671f  mov     rdx, [rbx]; Src
0x1801b6722  call    memcpy_0
0x1801b6727  add     r14d, [rbx+8]
0x1801b672b  add     rbx, 10h
0x1801b672f  cmp     rbx, rsi
0x1801b6732  jnz     short loc_1801B6715
0x1801b6734  lea     rdx, [rsp+78h+var_48]
0x1801b6739  mov     rcx, r15
0x1801b673c  call    ??4?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator=(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &&)
0x1801b6741  lea     rcx, [rsp+78h+var_48]
0x1801b6746  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b674b  nop
0x1801b674c  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b6751  test    rcx, rcx
0x1801b6754  jz      short loc_1801B6776
0x1801b6756  mov     rdx, qword ptr [rsp+78h+var_38+8]
0x1801b675b  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801b6760  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b6765  mov     rdx, [rsp+78h+var_28]
0x1801b676a  sub     rdx, rcx
0x1801b676d  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801b6771  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801b6776  xor     eax, eax
0x1801b6778  jmp     loc_1801B6990
0x1801b677d  mov     rdi, rax
0x1801b6780  mov     [rsp+78h+var_50], rax
0x1801b6785  mov     rcx, rax; cb
0x1801b6788  call    cs:__imp_CoTaskMemAlloc
0x1801b678f  nop     dword ptr [rax+rax+00h]
0x1801b6794  mov     rdx, rax; lpBuffer
0x1801b6797  mov     [rsp+78h+var_48], rax
0x1801b679c  mov     dword ptr [rsp+78h+var_40], edi
0x1801b67a0  mov     eax, dword ptr [rsp+78h+var_50+4]
0x1801b67a4  mov     dword ptr [rsp+78h+var_40+4], eax
0x1801b67a8  test    rdx, rdx
0x1801b67ab  jnz     short loc_1801B6808
0x1801b67ad  mov     rcx, [rsp+78h]; this
0x1801b67b2  mov     ebx, 8007000Eh
0x1801b67b7  mov     r9d, ebx; char *
0x1801b67ba  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b67c1  mov     edx, 1EDh; void *
0x1801b67c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b67cb  nop
0x1801b67cc  lea     rcx, [rsp+78h+var_48]
0x1801b67d1  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b67d6  nop
0x1801b67d7  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b67dc  test    rcx, rcx
0x1801b67df  jz      short loc_1801B6801
0x1801b67e1  mov     rdx, qword ptr [rsp+78h+var_38+8]
0x1801b67e6  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801b67eb  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b67f0  mov     rdx, [rsp+78h+var_28]
0x1801b67f5  sub     rdx, rcx
0x1801b67f8  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801b67fc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801b6801  mov     eax, ebx
0x1801b6803  jmp     loc_1801B6990
0x1801b6808  mov     [rsp+78h+dwNumberOfBytesRead], 0; int
0x1801b6810  lea     r9, [rsp+78h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x1801b6815  mov     r8d, edi; dwNumberOfBytesToRead
0x1801b6818  mov     rcx, [rsi+18h]; hRequest
0x1801b681c  call    cs:__imp_WinHttpReadData
0x1801b6823  nop     dword ptr [rax+rax+00h]
0x1801b6828  test    eax, eax
0x1801b682a  jnz     short loc_1801B6880
0x1801b682c  mov     rcx, [rsp+78h]; this
0x1801b6831  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b6838  mov     edx, 1F4h; void *
0x1801b683d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801b6842  mov     ebx, eax
0x1801b6844  lea     rcx, [rsp+78h+var_48]
0x1801b6849  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b684e  nop
0x1801b684f  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b6854  test    rcx, rcx
0x1801b6857  jz      short loc_1801B6879
0x1801b6859  mov     rdx, qword ptr [rsp+78h+var_38+8]
0x1801b685e  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801b6863  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b6868  mov     rdx, [rsp+78h+var_28]
0x1801b686d  sub     rdx, rcx
0x1801b6870  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801b6874  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801b6879  mov     eax, ebx
0x1801b687b  jmp     loc_1801B6990
0x1801b6880  lea     rdx, [rsp+78h+var_48]
0x1801b6885  lea     rcx, [rsp+78h+var_38]
0x1801b688a  call    ??$emplace_back@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAAAEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@$$QEAV23@@Z; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::emplace_back<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &&)
0x1801b688f  mov     eax, [rsp+78h+dwNumberOfBytesRead]
0x1801b6893  lea     ecx, [rax+rbx]
0x1801b6896  cmp     ecx, ebx
0x1801b6898  jb      short loc_1801B690F
0x1801b689a  cmp     eax, [rsp+78h+dwNumberOfBytesAvailable]
0x1801b68a1  jz      short loc_1801B68FE
0x1801b68a3  mov     rcx, [rsp+78h]; this
0x1801b68a8  mov     ebx, 8000FFFFh
0x1801b68ad  mov     r9d, ebx; char *
0x1801b68b0  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b68b7  mov     edx, 1FAh; void *
0x1801b68bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b68c1  nop
0x1801b68c2  lea     rcx, [rsp+78h+var_48]
0x1801b68c7  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b68cc  nop
0x1801b68cd  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b68d2  test    rcx, rcx
0x1801b68d5  jz      short loc_1801B68F7
0x1801b68d7  mov     rdx, qword ptr [rsp+78h+var_38+8]
0x1801b68dc  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801b68e1  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b68e6  mov     rdx, [rsp+78h+var_28]
0x1801b68eb  sub     rdx, rcx
0x1801b68ee  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801b68f2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801b68f7  mov     eax, ebx
0x1801b68f9  jmp     loc_1801B6990
0x1801b68fe  mov     ebx, ecx
0x1801b6900  lea     rcx, [rsp+78h+var_48]
0x1801b6905  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b690a  jmp     loc_1801B658A
0x1801b690f  mov     rcx, [rsp+78h]; this
0x1801b6914  mov     ebx, 80070216h
0x1801b6919  mov     r9d, ebx; char *
0x1801b691c  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b6923  mov     edx, 1F7h; void *
0x1801b6928  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b692d  nop
0x1801b692e  lea     rcx, [rsp+78h+var_48]
0x1801b6933  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b6938  nop
0x1801b6939  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b693e  test    rcx, rcx
0x1801b6941  jz      short loc_1801B6963
0x1801b6943  mov     rdx, qword ptr [rsp+78h+var_38+8]
0x1801b6948  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801b694d  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b6952  mov     rdx, [rsp+78h+var_28]
0x1801b6957  sub     rdx, rcx
0x1801b695a  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801b695e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801b6963  mov     eax, ebx
0x1801b6965  jmp     short loc_1801B6990
0x1801b6967  mov     rcx, [rsp+78h]; this
0x1801b696c  mov     ebx, 80004001h
0x1801b6971  mov     r9d, ebx; char *
0x1801b6974  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b697b  mov     edx, 1DDh; void *
0x1801b6980  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b6985  mov     eax, ebx
0x1801b6987  jmp     short loc_1801B6990
0x1801b6989  mov     eax, [rsp+78h+dwNumberOfBytesAvailable]
0x1801b6990  lea     r11, [rsp+78h+var_18]
0x1801b6995  mov     rbx, [r11+20h]
0x1801b6999  mov     rsi, [r11+28h]
0x1801b699d  mov     rsp, r11
0x1801b69a0  pop     r15
0x1801b69a2  pop     r14
0x1801b69a4  pop     rdi
0x1801b69a5  retn
```
