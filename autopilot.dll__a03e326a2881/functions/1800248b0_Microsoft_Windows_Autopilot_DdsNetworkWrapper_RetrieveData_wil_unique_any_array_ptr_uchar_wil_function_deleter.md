# Microsoft::Windows::Autopilot::DdsNetworkWrapper::RetrieveData(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &)

- ea: `0x1800248b0`
- end: `0x180024c2e`
- name: `?RetrieveData@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJAEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@Z`
- size: `894`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023cb0`
- `0x1800250d8`

## callees

- `0x18000994b`
- `0x1800105d4`
- `0x1800105f4`
- `0x180021d84`
- `0x180022134`
- `0x1800248b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002496f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024a36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024a55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024b03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024b92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024bb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024bfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002496f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024a36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024a55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024b03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024b92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024bb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024bfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800249b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024a73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800249b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024a73`
- `WINHTTP!WinHttpReadData` at `0x180024adb`
- `WINHTTP!WinHttpReadData` at `0x180024adb`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800248f2`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800248f2`

## string_xrefs

- `0x180024904`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x1800249d3`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024a9b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024aed`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024b78`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024be2`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::RetrieveData(__int64 a1, __int64 a2)
{
  DWORD v4; // esi
  const char *v5; // r9
  unsigned int LastError; // ebx
  _QWORD *v8; // rdi
  LPVOID v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r12
  char *v12; // rdi
  int v13; // r14d
  __int64 i; // rsi
  __int64 v15; // r15
  __int64 v16; // r14
  void *v17; // rax
  void *v18; // rdi
  const char *v19; // r9
  unsigned int v20; // ebx
  __int64 v21; // rdx
  void *v22; // rdi
  const char *v23; // r9
  int v24[2]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v25; // [rsp+28h] [rbp-60h]
  char v26; // [rsp+30h] [rbp-58h] BYREF
  __int128 v27; // [rsp+40h] [rbp-48h] BYREF
  __int64 v28; // [rsp+50h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  DWORD dwNumberOfBytesAvailable; // [rsp+90h] [rbp+8h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+A0h] [rbp+18h] BYREF

  v27 = 0;
  v28 = 0;
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
      std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(&v27);
      return LastError;
    }
    if ( !dwNumberOfBytesAvailable )
    {
      if ( v4 )
      {
        v8 = (_QWORD *)v27;
        if ( *((_QWORD *)&v27 + 1) - (_QWORD)v27 == 16 )
        {
          if ( a2 != (_QWORD)v27 )
          {
            v9 = *(LPVOID *)a2;
            if ( *(_QWORD *)a2 )
            {
              CoTaskMemFree(*(LPVOID *)a2);
              *(_QWORD *)a2 = 0;
              *(_QWORD *)(a2 + 8) = 0;
              v9 = 0;
            }
            v10 = *(_QWORD *)(a2 + 8);
            *(_QWORD *)a2 = *v8;
            *(_QWORD *)(a2 + 8) = v8[1];
            *v8 = v9;
            v8[1] = v10;
          }
        }
        else
        {
          v11 = v4;
          v12 = (char *)CoTaskMemAlloc(v4);
          if ( !v12 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2D3,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
              (const char *)0x8007000ELL,
              v24[0]);
            std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(&v27);
            return 2147942414LL;
          }
          v13 = 0;
          v15 = *((_QWORD *)&v27 + 1);
          for ( i = v27; i != v15; i += 16 )
          {
            memcpy_0(&v12[v13], *(const void **)i, *(_QWORD *)(i + 8));
            v13 += *(_DWORD *)(i + 8);
          }
          if ( (char *)a2 != &v26 )
          {
            if ( *(_QWORD *)a2 )
            {
              CoTaskMemFree(*(LPVOID *)a2);
              *(_QWORD *)(a2 + 8) = 0;
            }
            *(_QWORD *)a2 = v12;
            *(_QWORD *)(a2 + 8) = v11;
            v12 = 0;
          }
          if ( v12 )
            CoTaskMemFree(v12);
        }
      }
      std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(&v27);
      return 0;
    }
    v16 = dwNumberOfBytesAvailable;
    v17 = CoTaskMemAlloc(dwNumberOfBytesAvailable);
    v18 = v17;
    *(_QWORD *)v24 = v17;
    v25 = v16;
    if ( !v17 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B9,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)0x8007000ELL,
        0);
      std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(&v27);
      return 2147942414LL;
    }
    dwNumberOfBytesRead = 0;
    if ( !WinHttpReadData(*(HINTERNET *)(a1 + 80), v17, v16, &dwNumberOfBytesRead) )
    {
      v20 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x2C0,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
              v19);
      CoTaskMemFree(v18);
      std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(&v27);
      return v20;
    }
    v21 = *((_QWORD *)&v27 + 1);
    if ( *((_QWORD *)&v27 + 1) == v28 )
    {
      try
      {
        std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::_Emplace_reallocate<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(
          &v27,
          *((_QWORD *)&v27 + 1),
          v24);
        v22 = *(void **)v24;
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x2E1,
                               (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                               v23);
      }
    }
    else
    {
      **((_QWORD **)&v27 + 1) = v18;
      *(_QWORD *)(v21 + 8) = v16;
      v22 = 0;
      v25 = 0;
      *((_QWORD *)&v27 + 1) += 16LL;
    }
    if ( dwNumberOfBytesRead + v4 < v4 )
      break;
    if ( dwNumberOfBytesRead != dwNumberOfBytesAvailable )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C6,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)0x8000FFFFLL,
        v24[0]);
      if ( v22 )
        CoTaskMemFree(v22);
      std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(&v27);
      return 2147549183LL;
    }
    v4 += dwNumberOfBytesRead;
    if ( v22 )
    {
      CoTaskMemFree(v22);
      *(_QWORD *)v24 = 0;
      v25 = 0;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2C3,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
    (const char *)0x80070216LL,
    v24[0]);
  if ( v22 )
    CoTaskMemFree(v22);
  std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(&v27);
  return 2147942934LL;
}

```

## disassembly

```asm
0x1800248b0  mov     [rsp+arg_8], rbx
0x1800248b5  push    rsi
0x1800248b6  push    rdi
0x1800248b7  push    r12
0x1800248b9  push    r14
0x1800248bb  push    r15
0x1800248bd  sub     rsp, 60h
0x1800248c1  mov     rbx, rdx
0x1800248c4  mov     r15, rcx
0x1800248c7  xorps   xmm0, xmm0
0x1800248ca  movdqu  [rsp+88h+var_48], xmm0
0x1800248d0  mov     [rsp+88h+var_38], 0
0x1800248d9  xor     esi, esi
0x1800248db  mov     [rsp+88h+dwNumberOfBytesAvailable], 0
0x1800248e6  lea     rdx, [rsp+88h+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x1800248ee  mov     rcx, [r15+50h]; hRequest
0x1800248f2  call    cs:__imp_WinHttpQueryDataAvailable
0x1800248f8  test    eax, eax
0x1800248fa  jnz     short loc_180024928
0x1800248fc  mov     rcx, [rsp+88h]; this
0x180024904  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002490b  mov     edx, 2B2h; void *
0x180024910  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180024915  mov     ebx, eax
0x180024917  lea     rcx, [rsp+88h+var_48]
0x18002491c  call    ??1?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(void)
0x180024921  mov     eax, ebx
0x180024923  jmp     loc_180024C18
0x180024928  mov     eax, [rsp+88h+dwNumberOfBytesAvailable]
0x18002492f  test    eax, eax
0x180024931  jnz     loc_180024A6D
0x180024937  test    esi, esi
0x180024939  jnz     short loc_18002494C
0x18002493b  lea     rcx, [rsp+88h+var_48]
0x180024940  call    ??1?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(void)
0x180024945  xor     eax, eax
0x180024947  jmp     loc_180024C18
0x18002494c  mov     rdi, qword ptr [rsp+88h+var_48]
0x180024951  mov     rax, qword ptr [rsp+88h+var_48+8]
0x180024956  sub     rax, rdi
0x180024959  cmp     rax, 10h
0x18002495d  jnz     short loc_1800249B0
0x18002495f  cmp     rbx, rdi
0x180024962  jz      short loc_18002499F
0x180024964  mov     rdx, [rbx]
0x180024967  test    rdx, rdx
0x18002496a  jz      short loc_180024986
0x18002496c  mov     rcx, rdx; pv
0x18002496f  call    cs:__imp_CoTaskMemFree
0x180024975  mov     qword ptr [rbx], 0
0x18002497c  mov     qword ptr [rbx+8], 0
0x180024984  xor     edx, edx
0x180024986  mov     rcx, [rbx+8]
0x18002498a  mov     rax, [rdi]
0x18002498d  mov     [rbx], rax
0x180024990  mov     rax, [rdi+8]
0x180024994  mov     [rbx+8], rax
0x180024998  mov     [rdi], rdx
0x18002499b  mov     [rdi+8], rcx
0x18002499f  lea     rcx, [rsp+88h+var_48]
0x1800249a4  call    ??1?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(void)
0x1800249a9  xor     eax, eax
0x1800249ab  jmp     loc_180024C18
0x1800249b0  mov     r12d, esi
0x1800249b3  mov     ecx, esi; cb
0x1800249b5  call    cs:__imp_CoTaskMemAlloc
0x1800249bb  mov     rdi, rax
0x1800249be  test    rax, rax
0x1800249c1  jnz     short loc_1800249F6
0x1800249c3  mov     rcx, [rsp+88h]; this
0x1800249cb  mov     ebx, 8007000Eh
0x1800249d0  mov     r9d, ebx; char *
0x1800249d3  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800249da  mov     edx, 2D3h; void *
0x1800249df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800249e4  nop
0x1800249e5  lea     rcx, [rsp+88h+var_48]
0x1800249ea  call    ??1?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(void)
0x1800249ef  mov     eax, ebx
0x1800249f1  jmp     loc_180024C18
0x1800249f6  xor     r14d, r14d
0x1800249f9  mov     rsi, qword ptr [rsp+88h+var_48]
0x1800249fe  mov     r15, qword ptr [rsp+88h+var_48+8]
0x180024a03  jmp     short loc_180024A1F
0x180024a05  mov     ecx, r14d
0x180024a08  add     rcx, rdi; void *
0x180024a0b  mov     r8, [rsi+8]; Size
0x180024a0f  mov     rdx, [rsi]; Src
0x180024a12  call    memcpy_0
0x180024a17  add     r14d, [rsi+8]
0x180024a1b  add     rsi, 10h
0x180024a1f  cmp     rsi, r15
0x180024a22  jnz     short loc_180024A05
0x180024a24  lea     rax, [rsp+88h+var_58]
0x180024a29  cmp     rbx, rax
0x180024a2c  jz      short loc_180024A4D
0x180024a2e  mov     rcx, [rbx]; pv
0x180024a31  test    rcx, rcx
0x180024a34  jz      short loc_180024A44
0x180024a36  call    cs:__imp_CoTaskMemFree
0x180024a3c  mov     qword ptr [rbx+8], 0
0x180024a44  mov     [rbx], rdi
0x180024a47  mov     [rbx+8], r12
0x180024a4b  xor     edi, edi
0x180024a4d  test    rdi, rdi
0x180024a50  jz      short loc_180024A5C
0x180024a52  mov     rcx, rdi; pv
0x180024a55  call    cs:__imp_CoTaskMemFree
0x180024a5b  nop
0x180024a5c  lea     rcx, [rsp+88h+var_48]
0x180024a61  call    ??1?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(void)
0x180024a66  xor     eax, eax
0x180024a68  jmp     loc_180024C18
0x180024a6d  mov     r14, rax
0x180024a70  mov     rcx, rax; cb
0x180024a73  call    cs:__imp_CoTaskMemAlloc
0x180024a79  mov     rdi, rax
0x180024a7c  mov     qword ptr [rsp+88h+var_68], rax; int
0x180024a81  mov     [rsp+88h+var_60], r14
0x180024a86  test    rax, rax
0x180024a89  jnz     short loc_180024ABE
0x180024a8b  mov     rcx, [rsp+88h]; this
0x180024a93  mov     ebx, 8007000Eh
0x180024a98  mov     r9d, ebx; char *
0x180024a9b  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180024aa2  mov     edx, 2B9h; void *
0x180024aa7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024aac  nop
0x180024aad  lea     rcx, [rsp+88h+var_48]
0x180024ab2  call    ??1?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(void)
0x180024ab7  mov     eax, ebx
0x180024ab9  jmp     loc_180024C18
0x180024abe  mov     [rsp+88h+dwNumberOfBytesRead], 0
0x180024ac9  lea     r9, [rsp+88h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x180024ad1  mov     r8d, r14d; dwNumberOfBytesToRead
0x180024ad4  mov     rdx, rdi; lpBuffer
0x180024ad7  mov     rcx, [r15+50h]; hRequest
0x180024adb  call    cs:__imp_WinHttpReadData
0x180024ae1  test    eax, eax
0x180024ae3  jnz     short loc_180024B1B
0x180024ae5  mov     rcx, [rsp+88h]; this
0x180024aed  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180024af4  mov     edx, 2C0h; void *
0x180024af9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180024afe  mov     ebx, eax
0x180024b00  mov     rcx, rdi; pv
0x180024b03  call    cs:__imp_CoTaskMemFree
0x180024b09  nop
0x180024b0a  lea     rcx, [rsp+88h+var_48]
0x180024b0f  call    ??1?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(void)
0x180024b14  mov     eax, ebx
0x180024b16  jmp     loc_180024C18
0x180024b1b  mov     rdx, qword ptr [rsp+88h+var_48+8]
0x180024b20  cmp     rdx, [rsp+88h+var_38]
0x180024b25  jz      short loc_180024B3D
0x180024b27  mov     [rdx], rdi
0x180024b2a  mov     [rdx+8], r14
0x180024b2e  xor     edi, edi
0x180024b30  mov     [rsp+88h+var_60], rdi
0x180024b35  add     qword ptr [rsp+88h+var_48+8], 10h
0x180024b3b  jmp     short loc_180024B51
0x180024b3d  lea     r8, [rsp+88h+var_68]
0x180024b42  lea     rcx, [rsp+88h+var_48]
0x180024b47  call    ??$_Emplace_reallocate@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@AEAAPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::_Emplace_reallocate<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &&)
0x180024b4c  mov     rdi, qword ptr [rsp+88h+var_68]
0x180024b51  mov     eax, [rsp+88h+dwNumberOfBytesRead]
0x180024b58  lea     ecx, [rax+rsi]
0x180024b5b  cmp     ecx, esi
0x180024b5d  jb      short loc_180024BD2
0x180024b5f  cmp     eax, [rsp+88h+dwNumberOfBytesAvailable]
0x180024b66  jz      short loc_180024BA7
0x180024b68  mov     rcx, [rsp+88h]; this
0x180024b70  mov     ebx, 8000FFFFh
0x180024b75  mov     r9d, ebx; char *
0x180024b78  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180024b7f  mov     edx, 2C6h; void *
0x180024b84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024b89  nop
0x180024b8a  test    rdi, rdi
0x180024b8d  jz      short loc_180024B99
0x180024b8f  mov     rcx, rdi; pv
0x180024b92  call    cs:__imp_CoTaskMemFree
0x180024b98  nop
0x180024b99  lea     rcx, [rsp+88h+var_48]
0x180024b9e  call    ??1?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(void)
0x180024ba3  mov     eax, ebx
0x180024ba5  jmp     short loc_180024C18
0x180024ba7  mov     esi, ecx
0x180024ba9  test    rdi, rdi
0x180024bac  jz      loc_1800248DB
0x180024bb2  mov     rcx, rdi; pv
0x180024bb5  call    cs:__imp_CoTaskMemFree
0x180024bbb  mov     qword ptr [rsp+88h+var_68], 0
0x180024bc4  mov     [rsp+88h+var_60], 0
0x180024bcd  jmp     loc_1800248DB
0x180024bd2  mov     rcx, [rsp+88h]; this
0x180024bda  mov     ebx, 80070216h
0x180024bdf  mov     r9d, ebx; char *
0x180024be2  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180024be9  mov     edx, 2C3h; void *
0x180024bee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024bf3  nop
0x180024bf4  test    rdi, rdi
0x180024bf7  jz      short loc_180024C03
0x180024bf9  mov     rcx, rdi; pv
0x180024bfc  call    cs:__imp_CoTaskMemFree
0x180024c02  nop
0x180024c03  lea     rcx, [rsp+88h+var_48]
0x180024c08  call    ??1?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(void)
0x180024c0d  mov     eax, ebx
0x180024c0f  jmp     short loc_180024C18
0x180024c11  mov     eax, [rsp+88h+dwNumberOfBytesAvailable]
0x180024c18  mov     rbx, [rsp+88h+arg_8]
0x180024c20  add     rsp, 60h
0x180024c24  pop     r15
0x180024c26  pop     r14
0x180024c28  pop     r12
0x180024c2a  pop     rdi
0x180024c2b  pop     rsi
0x180024c2c  retn
```
