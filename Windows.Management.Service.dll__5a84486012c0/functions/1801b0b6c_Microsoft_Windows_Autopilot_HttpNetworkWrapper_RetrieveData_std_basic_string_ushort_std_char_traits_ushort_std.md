# Microsoft::Windows::Autopilot::HttpNetworkWrapper::RetrieveData(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &)

- ea: `0x1801b0b6c`
- end: `0x1801b0fe7`
- name: `?RetrieveData@HttpNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@Z`
- size: `1147`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801b12b0`

## callees

- `0x180063dab`
- `0x180067a34`
- `0x180067a54`
- `0x18006b690`
- `0x1800801fc`
- `0x1800df644`
- `0x180198114`
- `0x1801982fc`
- `0x180198424`
- `0x1801b03f8`
- `0x1801b0b6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b0ce0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b0dd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b0ce0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b0dd4`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1801b0bf9`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1801b0bf9`
- `WINHTTP!WinHttpReadData` at `0x1801b0e62`
- `WINHTTP!WinHttpReadData` at `0x1801b0e62`

## string_xrefs

- `0x1801b0bb6`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b0c08`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b0d05`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b0e00`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b0e71`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b0ef0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b0f5c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b0fb4`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=22 #try_helpers=1
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
0x1801b0b6c  mov     [rsp+arg_0], rbx
0x1801b0b71  mov     [rsp+arg_8], rsi
0x1801b0b76  push    rdi
0x1801b0b77  push    r14
0x1801b0b79  push    r15
0x1801b0b7b  sub     rsp, 60h
0x1801b0b7f  mov     r15, r8
0x1801b0b82  mov     rbx, rdx
0x1801b0b85  mov     rsi, rcx
0x1801b0b88  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1801b0b8f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1801b0b94  test    al, al
0x1801b0b96  jz      loc_1801B0FA7
0x1801b0b9c  mov     rdx, rbx
0x1801b0b9f  mov     rcx, [rsi+18h]; hRequest
0x1801b0ba3  call    ?ExtractContentTypeFromHeaders@Autopilot@Windows@Microsoft@@YAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::ExtractContentTypeFromHeaders(void *,std::wstring &)
0x1801b0ba8  mov     ebx, eax
0x1801b0baa  test    eax, eax
0x1801b0bac  jns     short loc_1801B0BCE
0x1801b0bae  mov     rcx, [rsp+78h]; this
0x1801b0bb3  mov     r9d, eax; char *
0x1801b0bb6  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b0bbd  mov     edx, 1DFh; void *
0x1801b0bc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b0bc7  mov     eax, ebx
0x1801b0bc9  jmp     loc_1801B0FD0
0x1801b0bce  xorps   xmm0, xmm0
0x1801b0bd1  movdqu  [rsp+78h+var_38], xmm0
0x1801b0bd7  mov     [rsp+78h+var_28], 0
0x1801b0be0  xor     ebx, ebx
0x1801b0be2  mov     [rsp+78h+dwNumberOfBytesAvailable], 0
0x1801b0bed  lea     rdx, [rsp+78h+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x1801b0bf5  mov     rcx, [rsi+18h]; hRequest
0x1801b0bf9  call    cs:__imp_WinHttpQueryDataAvailable
0x1801b0bff  test    eax, eax
0x1801b0c01  jnz     short loc_1801B0C4C
0x1801b0c03  mov     rcx, [rsp+78h]; this
0x1801b0c08  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b0c0f  mov     edx, 1E6h; void *
0x1801b0c14  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801b0c19  mov     ebx, eax
0x1801b0c1b  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b0c20  test    rcx, rcx
0x1801b0c23  jz      short loc_1801B0C45
0x1801b0c25  mov     rdx, qword ptr [rsp+78h+var_38+8]
0x1801b0c2a  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801b0c2f  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b0c34  mov     rdx, [rsp+78h+var_28]
0x1801b0c39  sub     rdx, rcx
0x1801b0c3c  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801b0c40  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801b0c45  mov     eax, ebx
0x1801b0c47  jmp     loc_1801B0FD0
0x1801b0c4c  mov     eax, [rsp+78h+dwNumberOfBytesAvailable]
0x1801b0c53  test    eax, eax
0x1801b0c55  jnz     loc_1801B0DC9
0x1801b0c5b  test    ebx, ebx
0x1801b0c5d  jnz     short loc_1801B0C90
0x1801b0c5f  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b0c64  test    rcx, rcx
0x1801b0c67  jz      short loc_1801B0C89
0x1801b0c69  mov     rdx, qword ptr [rsp+78h+var_38+8]
0x1801b0c6e  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801b0c73  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b0c78  mov     rdx, [rsp+78h+var_28]
0x1801b0c7d  sub     rdx, rcx
0x1801b0c80  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801b0c84  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801b0c89  xor     eax, eax
0x1801b0c8b  jmp     loc_1801B0FD0
0x1801b0c90  mov     rax, qword ptr [rsp+78h+var_38+8]
0x1801b0c95  mov     rdx, qword ptr [rsp+78h+var_38]
0x1801b0c9a  sub     rax, rdx
0x1801b0c9d  cmp     rax, 10h
0x1801b0ca1  jnz     short loc_1801B0CDD
0x1801b0ca3  mov     rcx, r15
0x1801b0ca6  call    ??4?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator=(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &&)
0x1801b0cab  nop
0x1801b0cac  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b0cb1  test    rcx, rcx
0x1801b0cb4  jz      short loc_1801B0CD6
0x1801b0cb6  mov     rdx, qword ptr [rsp+78h+var_38+8]
0x1801b0cbb  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801b0cc0  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b0cc5  mov     rdx, [rsp+78h+var_28]
0x1801b0cca  sub     rdx, rcx
0x1801b0ccd  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801b0cd1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801b0cd6  xor     eax, eax
0x1801b0cd8  jmp     loc_1801B0FD0
0x1801b0cdd  mov     rcx, rbx; cb
0x1801b0ce0  call    cs:__imp_CoTaskMemAlloc
0x1801b0ce6  mov     rdi, rax
0x1801b0ce9  mov     [rsp+78h+var_48], rax
0x1801b0cee  mov     [rsp+78h+var_40], rbx
0x1801b0cf3  test    rax, rax
0x1801b0cf6  jnz     short loc_1801B0D52
0x1801b0cf8  mov     rcx, [rsp+78h]; this
0x1801b0cfd  mov     ebx, 8007000Eh
0x1801b0d02  mov     r9d, ebx; char *
0x1801b0d05  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b0d0c  mov     edx, 207h; void *
0x1801b0d11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b0d16  lea     rcx, [rsp+78h+var_48]
0x1801b0d1b  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b0d20  nop
0x1801b0d21  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b0d26  test    rcx, rcx
0x1801b0d29  jz      short loc_1801B0D4B
0x1801b0d2b  mov     rdx, qword ptr [rsp+78h+var_38+8]
0x1801b0d30  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801b0d35  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b0d3a  mov     rdx, [rsp+78h+var_28]
0x1801b0d3f  sub     rdx, rcx
0x1801b0d42  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801b0d46  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801b0d4b  mov     eax, ebx
0x1801b0d4d  jmp     loc_1801B0FD0
0x1801b0d52  xor     r14d, r14d
0x1801b0d55  mov     rbx, qword ptr [rsp+78h+var_38]
0x1801b0d5a  mov     rsi, qword ptr [rsp+78h+var_38+8]
0x1801b0d5f  jmp     short loc_1801B0D7B
0x1801b0d61  mov     ecx, r14d
0x1801b0d64  add     rcx, rdi; void *
0x1801b0d67  mov     r8, [rbx+8]; Size
0x1801b0d6b  mov     rdx, [rbx]; Src
0x1801b0d6e  call    memcpy_0
0x1801b0d73  add     r14d, [rbx+8]
0x1801b0d77  add     rbx, 10h
0x1801b0d7b  cmp     rbx, rsi
0x1801b0d7e  jnz     short loc_1801B0D61
0x1801b0d80  lea     rdx, [rsp+78h+var_48]
0x1801b0d85  mov     rcx, r15
0x1801b0d88  call    ??4?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator=(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &&)
0x1801b0d8d  lea     rcx, [rsp+78h+var_48]
0x1801b0d92  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b0d97  nop
0x1801b0d98  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b0d9d  test    rcx, rcx
0x1801b0da0  jz      short loc_1801B0DC2
0x1801b0da2  mov     rdx, qword ptr [rsp+78h+var_38+8]
0x1801b0da7  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801b0dac  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b0db1  mov     rdx, [rsp+78h+var_28]
0x1801b0db6  sub     rdx, rcx
0x1801b0db9  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801b0dbd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801b0dc2  xor     eax, eax
0x1801b0dc4  jmp     loc_1801B0FD0
0x1801b0dc9  mov     rdi, rax
0x1801b0dcc  mov     [rsp+78h+var_50], rax
0x1801b0dd1  mov     rcx, rax; cb
0x1801b0dd4  call    cs:__imp_CoTaskMemAlloc
0x1801b0dda  mov     rdx, rax; lpBuffer
0x1801b0ddd  mov     [rsp+78h+var_48], rax
0x1801b0de2  mov     dword ptr [rsp+78h+var_40], edi
0x1801b0de6  mov     eax, dword ptr [rsp+78h+var_50+4]
0x1801b0dea  mov     dword ptr [rsp+78h+var_40+4], eax
0x1801b0dee  test    rdx, rdx
0x1801b0df1  jnz     short loc_1801B0E4E
0x1801b0df3  mov     rcx, [rsp+78h]; this
0x1801b0df8  mov     ebx, 8007000Eh
0x1801b0dfd  mov     r9d, ebx; char *
0x1801b0e00  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b0e07  mov     edx, 1EDh; void *
0x1801b0e0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b0e11  nop
0x1801b0e12  lea     rcx, [rsp+78h+var_48]
0x1801b0e17  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b0e1c  nop
0x1801b0e1d  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b0e22  test    rcx, rcx
0x1801b0e25  jz      short loc_1801B0E47
0x1801b0e27  mov     rdx, qword ptr [rsp+78h+var_38+8]
0x1801b0e2c  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801b0e31  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b0e36  mov     rdx, [rsp+78h+var_28]
0x1801b0e3b  sub     rdx, rcx
0x1801b0e3e  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801b0e42  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801b0e47  mov     eax, ebx
0x1801b0e49  jmp     loc_1801B0FD0
0x1801b0e4e  mov     [rsp+78h+dwNumberOfBytesRead], 0; int
0x1801b0e56  lea     r9, [rsp+78h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x1801b0e5b  mov     r8d, edi; dwNumberOfBytesToRead
0x1801b0e5e  mov     rcx, [rsi+18h]; hRequest
0x1801b0e62  call    cs:__imp_WinHttpReadData
0x1801b0e68  test    eax, eax
0x1801b0e6a  jnz     short loc_1801B0EC0
0x1801b0e6c  mov     rcx, [rsp+78h]; this
0x1801b0e71  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b0e78  mov     edx, 1F4h; void *
0x1801b0e7d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801b0e82  mov     ebx, eax
0x1801b0e84  lea     rcx, [rsp+78h+var_48]
0x1801b0e89  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b0e8e  nop
0x1801b0e8f  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b0e94  test    rcx, rcx
0x1801b0e97  jz      short loc_1801B0EB9
0x1801b0e99  mov     rdx, qword ptr [rsp+78h+var_38+8]
0x1801b0e9e  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801b0ea3  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b0ea8  mov     rdx, [rsp+78h+var_28]
0x1801b0ead  sub     rdx, rcx
0x1801b0eb0  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801b0eb4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801b0eb9  mov     eax, ebx
0x1801b0ebb  jmp     loc_1801B0FD0
0x1801b0ec0  lea     rdx, [rsp+78h+var_48]
0x1801b0ec5  lea     rcx, [rsp+78h+var_38]
0x1801b0eca  call    ??$emplace_back@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAAAEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@$$QEAV23@@Z; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::emplace_back<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &&)
0x1801b0ecf  mov     eax, [rsp+78h+dwNumberOfBytesRead]
0x1801b0ed3  lea     ecx, [rax+rbx]
0x1801b0ed6  cmp     ecx, ebx
0x1801b0ed8  jb      short loc_1801B0F4F
0x1801b0eda  cmp     eax, [rsp+78h+dwNumberOfBytesAvailable]
0x1801b0ee1  jz      short loc_1801B0F3E
0x1801b0ee3  mov     rcx, [rsp+78h]; this
0x1801b0ee8  mov     ebx, 8000FFFFh
0x1801b0eed  mov     r9d, ebx; char *
0x1801b0ef0  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b0ef7  mov     edx, 1FAh; void *
0x1801b0efc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b0f01  nop
0x1801b0f02  lea     rcx, [rsp+78h+var_48]
0x1801b0f07  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b0f0c  nop
0x1801b0f0d  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b0f12  test    rcx, rcx
0x1801b0f15  jz      short loc_1801B0F37
0x1801b0f17  mov     rdx, qword ptr [rsp+78h+var_38+8]
0x1801b0f1c  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801b0f21  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b0f26  mov     rdx, [rsp+78h+var_28]
0x1801b0f2b  sub     rdx, rcx
0x1801b0f2e  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801b0f32  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801b0f37  mov     eax, ebx
0x1801b0f39  jmp     loc_1801B0FD0
0x1801b0f3e  mov     ebx, ecx
0x1801b0f40  lea     rcx, [rsp+78h+var_48]
0x1801b0f45  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b0f4a  jmp     loc_1801B0BE2
0x1801b0f4f  mov     rcx, [rsp+78h]; this
0x1801b0f54  mov     ebx, 80070216h
0x1801b0f59  mov     r9d, ebx; char *
0x1801b0f5c  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b0f63  mov     edx, 1F7h; void *
0x1801b0f68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b0f6d  nop
0x1801b0f6e  lea     rcx, [rsp+78h+var_48]
0x1801b0f73  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801b0f78  nop
0x1801b0f79  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b0f7e  test    rcx, rcx
0x1801b0f81  jz      short loc_1801B0FA3
0x1801b0f83  mov     rdx, qword ptr [rsp+78h+var_38+8]
0x1801b0f88  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801b0f8d  mov     rcx, qword ptr [rsp+78h+var_38]
0x1801b0f92  mov     rdx, [rsp+78h+var_28]
0x1801b0f97  sub     rdx, rcx
0x1801b0f9a  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801b0f9e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801b0fa3  mov     eax, ebx
0x1801b0fa5  jmp     short loc_1801B0FD0
0x1801b0fa7  mov     rcx, [rsp+78h]; this
0x1801b0fac  mov     ebx, 80004001h
0x1801b0fb1  mov     r9d, ebx; char *
0x1801b0fb4  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b0fbb  mov     edx, 1DDh; void *
0x1801b0fc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b0fc5  mov     eax, ebx
0x1801b0fc7  jmp     short loc_1801B0FD0
0x1801b0fc9  mov     eax, [rsp+78h+dwNumberOfBytesAvailable]
0x1801b0fd0  lea     r11, [rsp+78h+var_18]
0x1801b0fd5  mov     rbx, [r11+20h]
0x1801b0fd9  mov     rsi, [r11+28h]
0x1801b0fdd  mov     rsp, r11
0x1801b0fe0  pop     r15
0x1801b0fe2  pop     r14
0x1801b0fe4  pop     rdi
0x1801b0fe5  retn
```
