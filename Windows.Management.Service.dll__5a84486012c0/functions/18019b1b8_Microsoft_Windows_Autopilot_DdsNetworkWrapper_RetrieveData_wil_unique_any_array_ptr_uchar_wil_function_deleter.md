# Microsoft::Windows::Autopilot::DdsNetworkWrapper::RetrieveData(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &)

- ea: `0x18019b1b8`
- end: `0x18019b5c0`
- name: `?RetrieveData@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJAEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@Z`
- size: `1032`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180199ddc`
- `0x18019b890`

## callees

- `0x180063dab`
- `0x180067a34`
- `0x180067a54`
- `0x18006b690`
- `0x1800df644`
- `0x180198114`
- `0x1801982fc`
- `0x180198424`
- `0x18019b1b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18019b2dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18019b3d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18019b2dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18019b3d0`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18019b1f5`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18019b1f5`
- `WINHTTP!WinHttpReadData` at `0x18019b467`
- `WINHTTP!WinHttpReadData` at `0x18019b467`

## string_xrefs

- `0x18019b204`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019b301`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019b3ff`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019b476`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019b4f8`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019b561`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::RetrieveData(__int64 a1, __int64 a2)
{
  SIZE_T v4; // rbx
  const char *v5; // r9
  unsigned int LastError; // ebx
  char *v8; // rdi
  int v9; // esi
  __int64 i; // rbx
  __int64 v11; // r14
  DWORD v12; // edi
  void *v13; // rdx
  const char *v14; // r9
  unsigned int v15; // ebx
  const char *v16; // r9
  int v17[2]; // [rsp+20h] [rbp-58h] BYREF
  unsigned __int64 v18; // [rsp+28h] [rbp-50h]
  __int128 v19; // [rsp+30h] [rbp-48h] BYREF
  __int64 v20; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  DWORD dwNumberOfBytesAvailable; // [rsp+80h] [rbp+8h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+90h] [rbp+18h] BYREF
  __int64 v24; // [rsp+98h] [rbp+20h]

  v19 = 0;
  v20 = 0;
  v4 = 0;
  while ( 1 )
  {
    dwNumberOfBytesAvailable = 0;
    if ( !WinHttpQueryDataAvailable(*(HINTERNET *)(a1 + 80), &dwNumberOfBytesAvailable) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2B2,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                    v5);
      if ( (_QWORD)v19 )
      {
        std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(
          v19,
          *((_QWORD *)&v19 + 1));
        std::_Deallocate<16>(v19, (v20 - v19) & 0xFFFFFFFFFFFFFFF0uLL);
      }
      return LastError;
    }
    if ( !dwNumberOfBytesAvailable )
    {
      if ( (_DWORD)v4 )
      {
        if ( *((_QWORD *)&v19 + 1) - (_QWORD)v19 == 16 )
        {
          wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator=(
            a2,
            v19);
          if ( (_QWORD)v19 )
          {
            std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(
              v19,
              *((_QWORD *)&v19 + 1));
            std::_Deallocate<16>(v19, (v20 - v19) & 0xFFFFFFFFFFFFFFF0uLL);
          }
          return 0;
        }
        else
        {
          v8 = (char *)CoTaskMemAlloc(v4);
          *(_QWORD *)v17 = v8;
          v18 = v4;
          if ( v8 )
          {
            v9 = 0;
            v11 = *((_QWORD *)&v19 + 1);
            for ( i = v19; i != v11; i += 16 )
            {
              memcpy_0(&v8[v9], *(const void **)i, *(_QWORD *)(i + 8));
              v9 += *(_DWORD *)(i + 8);
            }
            wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator=(
              a2,
              v17);
            wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(v17);
            if ( (_QWORD)v19 )
            {
              std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(
                v19,
                *((_QWORD *)&v19 + 1));
              std::_Deallocate<16>(v19, (v20 - v19) & 0xFFFFFFFFFFFFFFF0uLL);
            }
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2D3,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
              (const char *)0x8007000ELL,
              0);
            wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(v17);
            if ( (_QWORD)v19 )
            {
              std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(
                v19,
                *((_QWORD *)&v19 + 1));
              std::_Deallocate<16>(v19, (v20 - v19) & 0xFFFFFFFFFFFFFFF0uLL);
            }
            return 2147942414LL;
          }
        }
      }
      else
      {
        if ( (_QWORD)v19 )
        {
          std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(
            v19,
            *((_QWORD *)&v19 + 1));
          std::_Deallocate<16>(v19, (v20 - v19) & 0xFFFFFFFFFFFFFFF0uLL);
        }
        return 0;
      }
    }
    v12 = dwNumberOfBytesAvailable;
    v24 = dwNumberOfBytesAvailable;
    v13 = CoTaskMemAlloc(dwNumberOfBytesAvailable);
    *(_QWORD *)v17 = v13;
    v18 = __PAIR64__(HIDWORD(v24), v12);
    if ( !v13 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B9,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)0x8007000ELL,
        0);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(v17);
      if ( (_QWORD)v19 )
      {
        std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(
          v19,
          *((_QWORD *)&v19 + 1));
        std::_Deallocate<16>(v19, (v20 - v19) & 0xFFFFFFFFFFFFFFF0uLL);
      }
      return 2147942414LL;
    }
    dwNumberOfBytesRead = 0;
    if ( !WinHttpReadData(*(HINTERNET *)(a1 + 80), v13, v12, &dwNumberOfBytesRead) )
    {
      v15 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x2C0,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
              v14);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(v17);
      if ( (_QWORD)v19 )
      {
        std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(
          v19,
          *((_QWORD *)&v19 + 1));
        std::_Deallocate<16>(v19, (v20 - v19) & 0xFFFFFFFFFFFFFFF0uLL);
      }
      return v15;
    }
    try
    {
      std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::emplace_back<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(
        &v19,
        v17);
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x2E1,
                             (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                             v16);
    }
    if ( dwNumberOfBytesRead + (unsigned int)v4 < (unsigned int)v4 )
      break;
    if ( dwNumberOfBytesRead != dwNumberOfBytesAvailable )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C6,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)0x8000FFFFLL,
        v17[0]);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(v17);
      if ( (_QWORD)v19 )
      {
        std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(
          v19,
          *((_QWORD *)&v19 + 1));
        std::_Deallocate<16>(v19, (v20 - v19) & 0xFFFFFFFFFFFFFFF0uLL);
      }
      return 2147549183LL;
    }
    v4 = dwNumberOfBytesRead + (unsigned int)v4;
    wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(v17);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2C3,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
    (const char *)0x80070216LL,
    v17[0]);
  wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(v17);
  if ( (_QWORD)v19 )
  {
    std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(
      v19,
      *((_QWORD *)&v19 + 1));
    std::_Deallocate<16>(v19, (v20 - v19) & 0xFFFFFFFFFFFFFFF0uLL);
  }
  return 2147942934LL;
}

```

## disassembly

```asm
0x18019b1b8  push    rbx
0x18019b1ba  push    rsi
0x18019b1bb  push    rdi
0x18019b1bc  push    r14
0x18019b1be  push    r15
0x18019b1c0  sub     rsp, 50h
0x18019b1c4  mov     r15, rdx
0x18019b1c7  mov     rsi, rcx
0x18019b1ca  xorps   xmm0, xmm0
0x18019b1cd  movdqu  [rsp+78h+var_48], xmm0
0x18019b1d3  mov     [rsp+78h+var_38], 0
0x18019b1dc  xor     ebx, ebx
0x18019b1de  mov     [rsp+78h+dwNumberOfBytesAvailable], 0
0x18019b1e9  lea     rdx, [rsp+78h+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x18019b1f1  mov     rcx, [rsi+50h]; hRequest
0x18019b1f5  call    cs:__imp_WinHttpQueryDataAvailable
0x18019b1fb  test    eax, eax
0x18019b1fd  jnz     short loc_18019B248
0x18019b1ff  mov     rcx, [rsp+78h]; this
0x18019b204  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019b20b  mov     edx, 2B2h; void *
0x18019b210  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18019b215  mov     ebx, eax
0x18019b217  mov     rcx, qword ptr [rsp+78h+var_48]
0x18019b21c  test    rcx, rcx
0x18019b21f  jz      short loc_18019B241
0x18019b221  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x18019b226  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x18019b22b  mov     rcx, qword ptr [rsp+78h+var_48]
0x18019b230  mov     rdx, [rsp+78h+var_38]
0x18019b235  sub     rdx, rcx
0x18019b238  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18019b23c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18019b241  mov     eax, ebx
0x18019b243  jmp     loc_18019B5B3
0x18019b248  mov     eax, [rsp+78h+dwNumberOfBytesAvailable]
0x18019b24f  test    eax, eax
0x18019b251  jnz     loc_18019B3C2
0x18019b257  test    ebx, ebx
0x18019b259  jnz     short loc_18019B28C
0x18019b25b  mov     rcx, qword ptr [rsp+78h+var_48]
0x18019b260  test    rcx, rcx
0x18019b263  jz      short loc_18019B285
0x18019b265  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x18019b26a  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x18019b26f  mov     rcx, qword ptr [rsp+78h+var_48]
0x18019b274  mov     rdx, [rsp+78h+var_38]
0x18019b279  sub     rdx, rcx
0x18019b27c  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18019b280  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18019b285  xor     eax, eax
0x18019b287  jmp     loc_18019B5B3
0x18019b28c  mov     rax, qword ptr [rsp+78h+var_48+8]
0x18019b291  mov     rdx, qword ptr [rsp+78h+var_48]
0x18019b296  sub     rax, rdx
0x18019b299  cmp     rax, 10h
0x18019b29d  jnz     short loc_18019B2D9
0x18019b29f  mov     rcx, r15
0x18019b2a2  call    ??4?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator=(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &&)
0x18019b2a7  nop
0x18019b2a8  mov     rcx, qword ptr [rsp+78h+var_48]
0x18019b2ad  test    rcx, rcx
0x18019b2b0  jz      short loc_18019B2D2
0x18019b2b2  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x18019b2b7  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x18019b2bc  mov     rcx, qword ptr [rsp+78h+var_48]
0x18019b2c1  mov     rdx, [rsp+78h+var_38]
0x18019b2c6  sub     rdx, rcx
0x18019b2c9  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18019b2cd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18019b2d2  xor     eax, eax
0x18019b2d4  jmp     loc_18019B5B3
0x18019b2d9  mov     rcx, rbx; cb
0x18019b2dc  call    cs:__imp_CoTaskMemAlloc
0x18019b2e2  mov     rdi, rax
0x18019b2e5  mov     qword ptr [rsp+78h+var_58], rax; int
0x18019b2ea  mov     [rsp+78h+var_50], rbx
0x18019b2ef  test    rax, rax
0x18019b2f2  jnz     short loc_18019B34E
0x18019b2f4  mov     rcx, [rsp+78h]; this
0x18019b2f9  mov     ebx, 8007000Eh
0x18019b2fe  mov     r9d, ebx; char *
0x18019b301  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019b308  mov     edx, 2D3h; void *
0x18019b30d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019b312  lea     rcx, [rsp+78h+var_58]
0x18019b317  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18019b31c  nop
0x18019b31d  mov     rcx, qword ptr [rsp+78h+var_48]
0x18019b322  test    rcx, rcx
0x18019b325  jz      short loc_18019B347
0x18019b327  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x18019b32c  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x18019b331  mov     rcx, qword ptr [rsp+78h+var_48]
0x18019b336  mov     rdx, [rsp+78h+var_38]
0x18019b33b  sub     rdx, rcx
0x18019b33e  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18019b342  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18019b347  mov     eax, ebx
0x18019b349  jmp     loc_18019B5B3
0x18019b34e  xor     esi, esi
0x18019b350  mov     rbx, qword ptr [rsp+78h+var_48]
0x18019b355  mov     r14, qword ptr [rsp+78h+var_48+8]
0x18019b35a  jmp     short loc_18019B374
0x18019b35c  mov     ecx, esi
0x18019b35e  add     rcx, rdi; void *
0x18019b361  mov     r8, [rbx+8]; Size
0x18019b365  mov     rdx, [rbx]; Src
0x18019b368  call    memcpy_0
0x18019b36d  add     esi, [rbx+8]
0x18019b370  add     rbx, 10h
0x18019b374  cmp     rbx, r14
0x18019b377  jnz     short loc_18019B35C
0x18019b379  lea     rdx, [rsp+78h+var_58]
0x18019b37e  mov     rcx, r15
0x18019b381  call    ??4?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator=(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &&)
0x18019b386  lea     rcx, [rsp+78h+var_58]
0x18019b38b  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18019b390  nop
0x18019b391  mov     rcx, qword ptr [rsp+78h+var_48]
0x18019b396  test    rcx, rcx
0x18019b399  jz      short loc_18019B3BB
0x18019b39b  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x18019b3a0  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x18019b3a5  mov     rcx, qword ptr [rsp+78h+var_48]
0x18019b3aa  mov     rdx, [rsp+78h+var_38]
0x18019b3af  sub     rdx, rcx
0x18019b3b2  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18019b3b6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18019b3bb  xor     eax, eax
0x18019b3bd  jmp     loc_18019B5B3
0x18019b3c2  mov     rdi, rax
0x18019b3c5  mov     [rsp+78h+arg_18], rax
0x18019b3cd  mov     rcx, rax; cb
0x18019b3d0  call    cs:__imp_CoTaskMemAlloc
0x18019b3d6  mov     rdx, rax; lpBuffer
0x18019b3d9  mov     qword ptr [rsp+78h+var_58], rax; int
0x18019b3de  mov     dword ptr [rsp+78h+var_50], edi
0x18019b3e2  mov     eax, dword ptr [rsp+78h+arg_18+4]
0x18019b3e9  mov     dword ptr [rsp+78h+var_50+4], eax
0x18019b3ed  test    rdx, rdx
0x18019b3f0  jnz     short loc_18019B44D
0x18019b3f2  mov     rcx, [rsp+78h]; this
0x18019b3f7  mov     ebx, 8007000Eh
0x18019b3fc  mov     r9d, ebx; char *
0x18019b3ff  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019b406  mov     edx, 2B9h; void *
0x18019b40b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019b410  nop
0x18019b411  lea     rcx, [rsp+78h+var_58]
0x18019b416  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18019b41b  nop
0x18019b41c  mov     rcx, qword ptr [rsp+78h+var_48]
0x18019b421  test    rcx, rcx
0x18019b424  jz      short loc_18019B446
0x18019b426  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x18019b42b  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x18019b430  mov     rcx, qword ptr [rsp+78h+var_48]
0x18019b435  mov     rdx, [rsp+78h+var_38]
0x18019b43a  sub     rdx, rcx
0x18019b43d  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18019b441  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18019b446  mov     eax, ebx
0x18019b448  jmp     loc_18019B5B3
0x18019b44d  mov     [rsp+78h+dwNumberOfBytesRead], 0
0x18019b458  lea     r9, [rsp+78h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18019b460  mov     r8d, edi; dwNumberOfBytesToRead
0x18019b463  mov     rcx, [rsi+50h]; hRequest
0x18019b467  call    cs:__imp_WinHttpReadData
0x18019b46d  test    eax, eax
0x18019b46f  jnz     short loc_18019B4C5
0x18019b471  mov     rcx, [rsp+78h]; this
0x18019b476  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019b47d  mov     edx, 2C0h; void *
0x18019b482  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18019b487  mov     ebx, eax
0x18019b489  lea     rcx, [rsp+78h+var_58]
0x18019b48e  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18019b493  nop
0x18019b494  mov     rcx, qword ptr [rsp+78h+var_48]
0x18019b499  test    rcx, rcx
0x18019b49c  jz      short loc_18019B4BE
0x18019b49e  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x18019b4a3  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x18019b4a8  mov     rcx, qword ptr [rsp+78h+var_48]
0x18019b4ad  mov     rdx, [rsp+78h+var_38]
0x18019b4b2  sub     rdx, rcx
0x18019b4b5  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18019b4b9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18019b4be  mov     eax, ebx
0x18019b4c0  jmp     loc_18019B5B3
0x18019b4c5  lea     rdx, [rsp+78h+var_58]
0x18019b4ca  lea     rcx, [rsp+78h+var_48]
0x18019b4cf  call    ??$emplace_back@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAAAEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@$$QEAV23@@Z; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::emplace_back<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &&)
0x18019b4d4  mov     eax, [rsp+78h+dwNumberOfBytesRead]
0x18019b4db  lea     ecx, [rax+rbx]
0x18019b4de  cmp     ecx, ebx
0x18019b4e0  jb      short loc_18019B554
0x18019b4e2  cmp     eax, [rsp+78h+dwNumberOfBytesAvailable]
0x18019b4e9  jz      short loc_18019B543
0x18019b4eb  mov     rcx, [rsp+78h]; this
0x18019b4f0  mov     ebx, 8000FFFFh
0x18019b4f5  mov     r9d, ebx; char *
0x18019b4f8  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019b4ff  mov     edx, 2C6h; void *
0x18019b504  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019b509  nop
0x18019b50a  lea     rcx, [rsp+78h+var_58]
0x18019b50f  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18019b514  nop
0x18019b515  mov     rcx, qword ptr [rsp+78h+var_48]
0x18019b51a  test    rcx, rcx
0x18019b51d  jz      short loc_18019B53F
0x18019b51f  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x18019b524  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x18019b529  mov     rcx, qword ptr [rsp+78h+var_48]
0x18019b52e  mov     rdx, [rsp+78h+var_38]
0x18019b533  sub     rdx, rcx
0x18019b536  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18019b53a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18019b53f  mov     eax, ebx
0x18019b541  jmp     short loc_18019B5B3
0x18019b543  mov     ebx, ecx
0x18019b545  lea     rcx, [rsp+78h+var_58]
0x18019b54a  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18019b54f  jmp     loc_18019B1DE
0x18019b554  mov     rcx, [rsp+78h]; this
0x18019b559  mov     ebx, 80070216h
0x18019b55e  mov     r9d, ebx; char *
0x18019b561  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019b568  mov     edx, 2C3h; void *
0x18019b56d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019b572  nop
0x18019b573  lea     rcx, [rsp+78h+var_58]
0x18019b578  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18019b57d  nop
0x18019b57e  mov     rcx, qword ptr [rsp+78h+var_48]
0x18019b583  test    rcx, rcx
0x18019b586  jz      short loc_18019B5A8
0x18019b588  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x18019b58d  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x18019b592  mov     rcx, qword ptr [rsp+78h+var_48]
0x18019b597  mov     rdx, [rsp+78h+var_38]
0x18019b59c  sub     rdx, rcx
0x18019b59f  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18019b5a3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18019b5a8  mov     eax, ebx
0x18019b5aa  jmp     short loc_18019B5B3
0x18019b5ac  mov     eax, [rsp+78h+dwNumberOfBytesAvailable]
0x18019b5b3  add     rsp, 50h
0x18019b5b7  pop     r15
0x18019b5b9  pop     r14
0x18019b5bb  pop     rdi
0x18019b5bc  pop     rsi
0x18019b5bd  pop     rbx
0x18019b5be  retn
```
