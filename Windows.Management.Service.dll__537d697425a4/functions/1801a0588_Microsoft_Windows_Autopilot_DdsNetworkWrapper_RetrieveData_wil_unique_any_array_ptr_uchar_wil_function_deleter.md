# Microsoft::Windows::Autopilot::DdsNetworkWrapper::RetrieveData(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &)

- ea: `0x1801a0588`
- end: `0x1801a09a8`
- name: `?RetrieveData@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJAEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@Z`
- size: `1056`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18019f170`
- `0x1801a0c8c`

## callees

- `0x180063f8b`
- `0x180067e34`
- `0x180067e54`
- `0x18006bb78`
- `0x1800e1e8c`
- `0x18019d34c`
- `0x18019d534`
- `0x18019d668`
- `0x1801a0588`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a06b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a07ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a06b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a07ac`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1801a05c5`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1801a05c5`
- `WINHTTP!WinHttpReadData` at `0x1801a0849`
- `WINHTTP!WinHttpReadData` at `0x1801a0849`

## string_xrefs

- `0x1801a05da`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x1801a06dd`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x1801a07e1`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x1801a085e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x1801a08e0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x1801a0949`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1801a0588  push    rbx
0x1801a058a  push    rsi
0x1801a058b  push    rdi
0x1801a058c  push    r14
0x1801a058e  push    r15
0x1801a0590  sub     rsp, 50h
0x1801a0594  mov     r15, rdx
0x1801a0597  mov     rsi, rcx
0x1801a059a  xorps   xmm0, xmm0
0x1801a059d  movdqu  [rsp+78h+var_48], xmm0
0x1801a05a3  mov     [rsp+78h+var_38], 0
0x1801a05ac  xor     ebx, ebx
0x1801a05ae  mov     [rsp+78h+dwNumberOfBytesAvailable], 0
0x1801a05b9  lea     rdx, [rsp+78h+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x1801a05c1  mov     rcx, [rsi+50h]; hRequest
0x1801a05c5  call    cs:__imp_WinHttpQueryDataAvailable
0x1801a05cc  nop     dword ptr [rax+rax+00h]
0x1801a05d1  test    eax, eax
0x1801a05d3  jnz     short loc_1801A061E
0x1801a05d5  mov     rcx, [rsp+78h]; this
0x1801a05da  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a05e1  mov     edx, 2B2h; void *
0x1801a05e6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801a05eb  mov     ebx, eax
0x1801a05ed  mov     rcx, qword ptr [rsp+78h+var_48]
0x1801a05f2  test    rcx, rcx
0x1801a05f5  jz      short loc_1801A0617
0x1801a05f7  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x1801a05fc  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801a0601  mov     rcx, qword ptr [rsp+78h+var_48]
0x1801a0606  mov     rdx, [rsp+78h+var_38]
0x1801a060b  sub     rdx, rcx
0x1801a060e  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801a0612  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801a0617  mov     eax, ebx
0x1801a0619  jmp     loc_1801A099B
0x1801a061e  mov     eax, [rsp+78h+dwNumberOfBytesAvailable]
0x1801a0625  test    eax, eax
0x1801a0627  jnz     loc_1801A079E
0x1801a062d  test    ebx, ebx
0x1801a062f  jnz     short loc_1801A0662
0x1801a0631  mov     rcx, qword ptr [rsp+78h+var_48]
0x1801a0636  test    rcx, rcx
0x1801a0639  jz      short loc_1801A065B
0x1801a063b  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x1801a0640  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801a0645  mov     rcx, qword ptr [rsp+78h+var_48]
0x1801a064a  mov     rdx, [rsp+78h+var_38]
0x1801a064f  sub     rdx, rcx
0x1801a0652  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801a0656  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801a065b  xor     eax, eax
0x1801a065d  jmp     loc_1801A099B
0x1801a0662  mov     rax, qword ptr [rsp+78h+var_48+8]
0x1801a0667  mov     rdx, qword ptr [rsp+78h+var_48]
0x1801a066c  sub     rax, rdx
0x1801a066f  cmp     rax, 10h
0x1801a0673  jnz     short loc_1801A06AF
0x1801a0675  mov     rcx, r15
0x1801a0678  call    ??4?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator=(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &&)
0x1801a067d  nop
0x1801a067e  mov     rcx, qword ptr [rsp+78h+var_48]
0x1801a0683  test    rcx, rcx
0x1801a0686  jz      short loc_1801A06A8
0x1801a0688  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x1801a068d  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801a0692  mov     rcx, qword ptr [rsp+78h+var_48]
0x1801a0697  mov     rdx, [rsp+78h+var_38]
0x1801a069c  sub     rdx, rcx
0x1801a069f  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801a06a3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801a06a8  xor     eax, eax
0x1801a06aa  jmp     loc_1801A099B
0x1801a06af  mov     rcx, rbx; cb
0x1801a06b2  call    cs:__imp_CoTaskMemAlloc
0x1801a06b9  nop     dword ptr [rax+rax+00h]
0x1801a06be  mov     rdi, rax
0x1801a06c1  mov     qword ptr [rsp+78h+var_58], rax; int
0x1801a06c6  mov     [rsp+78h+var_50], rbx
0x1801a06cb  test    rax, rax
0x1801a06ce  jnz     short loc_1801A072A
0x1801a06d0  mov     rcx, [rsp+78h]; this
0x1801a06d5  mov     ebx, 8007000Eh
0x1801a06da  mov     r9d, ebx; char *
0x1801a06dd  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a06e4  mov     edx, 2D3h; void *
0x1801a06e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a06ee  lea     rcx, [rsp+78h+var_58]
0x1801a06f3  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801a06f8  nop
0x1801a06f9  mov     rcx, qword ptr [rsp+78h+var_48]
0x1801a06fe  test    rcx, rcx
0x1801a0701  jz      short loc_1801A0723
0x1801a0703  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x1801a0708  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801a070d  mov     rcx, qword ptr [rsp+78h+var_48]
0x1801a0712  mov     rdx, [rsp+78h+var_38]
0x1801a0717  sub     rdx, rcx
0x1801a071a  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801a071e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801a0723  mov     eax, ebx
0x1801a0725  jmp     loc_1801A099B
0x1801a072a  xor     esi, esi
0x1801a072c  mov     rbx, qword ptr [rsp+78h+var_48]
0x1801a0731  mov     r14, qword ptr [rsp+78h+var_48+8]
0x1801a0736  jmp     short loc_1801A0750
0x1801a0738  mov     ecx, esi
0x1801a073a  add     rcx, rdi; void *
0x1801a073d  mov     r8, [rbx+8]; Size
0x1801a0741  mov     rdx, [rbx]; Src
0x1801a0744  call    memcpy_0
0x1801a0749  add     esi, [rbx+8]
0x1801a074c  add     rbx, 10h
0x1801a0750  cmp     rbx, r14
0x1801a0753  jnz     short loc_1801A0738
0x1801a0755  lea     rdx, [rsp+78h+var_58]
0x1801a075a  mov     rcx, r15
0x1801a075d  call    ??4?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator=(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &&)
0x1801a0762  lea     rcx, [rsp+78h+var_58]
0x1801a0767  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801a076c  nop
0x1801a076d  mov     rcx, qword ptr [rsp+78h+var_48]
0x1801a0772  test    rcx, rcx
0x1801a0775  jz      short loc_1801A0797
0x1801a0777  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x1801a077c  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801a0781  mov     rcx, qword ptr [rsp+78h+var_48]
0x1801a0786  mov     rdx, [rsp+78h+var_38]
0x1801a078b  sub     rdx, rcx
0x1801a078e  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801a0792  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801a0797  xor     eax, eax
0x1801a0799  jmp     loc_1801A099B
0x1801a079e  mov     rdi, rax
0x1801a07a1  mov     [rsp+78h+arg_18], rax
0x1801a07a9  mov     rcx, rax; cb
0x1801a07ac  call    cs:__imp_CoTaskMemAlloc
0x1801a07b3  nop     dword ptr [rax+rax+00h]
0x1801a07b8  mov     rdx, rax; lpBuffer
0x1801a07bb  mov     qword ptr [rsp+78h+var_58], rax; int
0x1801a07c0  mov     dword ptr [rsp+78h+var_50], edi
0x1801a07c4  mov     eax, dword ptr [rsp+78h+arg_18+4]
0x1801a07cb  mov     dword ptr [rsp+78h+var_50+4], eax
0x1801a07cf  test    rdx, rdx
0x1801a07d2  jnz     short loc_1801A082F
0x1801a07d4  mov     rcx, [rsp+78h]; this
0x1801a07d9  mov     ebx, 8007000Eh
0x1801a07de  mov     r9d, ebx; char *
0x1801a07e1  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a07e8  mov     edx, 2B9h; void *
0x1801a07ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a07f2  nop
0x1801a07f3  lea     rcx, [rsp+78h+var_58]
0x1801a07f8  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801a07fd  nop
0x1801a07fe  mov     rcx, qword ptr [rsp+78h+var_48]
0x1801a0803  test    rcx, rcx
0x1801a0806  jz      short loc_1801A0828
0x1801a0808  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x1801a080d  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801a0812  mov     rcx, qword ptr [rsp+78h+var_48]
0x1801a0817  mov     rdx, [rsp+78h+var_38]
0x1801a081c  sub     rdx, rcx
0x1801a081f  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801a0823  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801a0828  mov     eax, ebx
0x1801a082a  jmp     loc_1801A099B
0x1801a082f  mov     [rsp+78h+dwNumberOfBytesRead], 0
0x1801a083a  lea     r9, [rsp+78h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x1801a0842  mov     r8d, edi; dwNumberOfBytesToRead
0x1801a0845  mov     rcx, [rsi+50h]; hRequest
0x1801a0849  call    cs:__imp_WinHttpReadData
0x1801a0850  nop     dword ptr [rax+rax+00h]
0x1801a0855  test    eax, eax
0x1801a0857  jnz     short loc_1801A08AD
0x1801a0859  mov     rcx, [rsp+78h]; this
0x1801a085e  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a0865  mov     edx, 2C0h; void *
0x1801a086a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801a086f  mov     ebx, eax
0x1801a0871  lea     rcx, [rsp+78h+var_58]
0x1801a0876  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801a087b  nop
0x1801a087c  mov     rcx, qword ptr [rsp+78h+var_48]
0x1801a0881  test    rcx, rcx
0x1801a0884  jz      short loc_1801A08A6
0x1801a0886  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x1801a088b  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801a0890  mov     rcx, qword ptr [rsp+78h+var_48]
0x1801a0895  mov     rdx, [rsp+78h+var_38]
0x1801a089a  sub     rdx, rcx
0x1801a089d  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801a08a1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801a08a6  mov     eax, ebx
0x1801a08a8  jmp     loc_1801A099B
0x1801a08ad  lea     rdx, [rsp+78h+var_58]
0x1801a08b2  lea     rcx, [rsp+78h+var_48]
0x1801a08b7  call    ??$emplace_back@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAAAEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@$$QEAV23@@Z; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::emplace_back<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &&)
0x1801a08bc  mov     eax, [rsp+78h+dwNumberOfBytesRead]
0x1801a08c3  lea     ecx, [rax+rbx]
0x1801a08c6  cmp     ecx, ebx
0x1801a08c8  jb      short loc_1801A093C
0x1801a08ca  cmp     eax, [rsp+78h+dwNumberOfBytesAvailable]
0x1801a08d1  jz      short loc_1801A092B
0x1801a08d3  mov     rcx, [rsp+78h]; this
0x1801a08d8  mov     ebx, 8000FFFFh
0x1801a08dd  mov     r9d, ebx; char *
0x1801a08e0  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a08e7  mov     edx, 2C6h; void *
0x1801a08ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a08f1  nop
0x1801a08f2  lea     rcx, [rsp+78h+var_58]
0x1801a08f7  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801a08fc  nop
0x1801a08fd  mov     rcx, qword ptr [rsp+78h+var_48]
0x1801a0902  test    rcx, rcx
0x1801a0905  jz      short loc_1801A0927
0x1801a0907  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x1801a090c  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801a0911  mov     rcx, qword ptr [rsp+78h+var_48]
0x1801a0916  mov     rdx, [rsp+78h+var_38]
0x1801a091b  sub     rdx, rcx
0x1801a091e  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801a0922  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801a0927  mov     eax, ebx
0x1801a0929  jmp     short loc_1801A099B
0x1801a092b  mov     ebx, ecx
0x1801a092d  lea     rcx, [rsp+78h+var_58]
0x1801a0932  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801a0937  jmp     loc_1801A05AE
0x1801a093c  mov     rcx, [rsp+78h]; this
0x1801a0941  mov     ebx, 80070216h
0x1801a0946  mov     r9d, ebx; char *
0x1801a0949  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a0950  mov     edx, 2C3h; void *
0x1801a0955  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a095a  nop
0x1801a095b  lea     rcx, [rsp+78h+var_58]
0x1801a0960  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801a0965  nop
0x1801a0966  mov     rcx, qword ptr [rsp+78h+var_48]
0x1801a096b  test    rcx, rcx
0x1801a096e  jz      short loc_1801A0990
0x1801a0970  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x1801a0975  call    ??$_Destroy_range@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@YAXPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV12@AEAV?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>> &)
0x1801a097a  mov     rcx, qword ptr [rsp+78h+var_48]
0x1801a097f  mov     rdx, [rsp+78h+var_38]
0x1801a0984  sub     rdx, rcx
0x1801a0987  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801a098b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801a0990  mov     eax, ebx
0x1801a0992  jmp     short loc_1801A099B
0x1801a0994  mov     eax, [rsp+78h+dwNumberOfBytesAvailable]
0x1801a099b  add     rsp, 50h
0x1801a099f  pop     r15
0x1801a09a1  pop     r14
0x1801a09a3  pop     rdi
0x1801a09a4  pop     rsi
0x1801a09a5  pop     rbx
0x1801a09a6  retn
```
