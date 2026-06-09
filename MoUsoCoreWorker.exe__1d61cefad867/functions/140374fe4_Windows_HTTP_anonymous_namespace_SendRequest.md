# Windows::HTTP::_anonymous_namespace_::SendRequest

- ea: `0x140374fe4`
- end: `0x140375654`
- name: `Windows::HTTP::_anonymous_namespace_::SendRequest`
- size: `1648`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x140375c90`
- `0x140375efc`

## callees

- `0x14003c578`
- `0x140040184`
- `0x140045404`
- `0x140057a20`
- `0x140075a18`
- `0x1400a3d80`
- `0x14012d864`
- `0x140374fe4`
- `0x140379070`
- `0x14037b4b0`
- `0x140380b50`

## import_xrefs

- `WINHTTP!WinHttpAddRequestHeaders` at `0x1403753dc`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1403753dc`
- `WINHTTP!WinHttpOpenRequest` at `0x14037536a`
- `WINHTTP!WinHttpOpenRequest` at `0x14037536a`
- `WINHTTP!WinHttpSendRequest` at `0x14037542e`
- `WINHTTP!WinHttpSendRequest` at `0x14037542e`
- `WINHTTP!WinHttpOpen` at `0x14037503d`
- `WINHTTP!WinHttpOpen` at `0x14037503d`
- `WINHTTP!WinHttpConnect` at `0x140375322`
- `WINHTTP!WinHttpConnect` at `0x140375322`
- `WINHTTP!WinHttpSetTimeouts` at `0x140375300`
- `WINHTTP!WinHttpSetTimeouts` at `0x140375300`
- `WINHTTP!WinHttpSetOption` at `0x14037506b`
- `WINHTTP!WinHttpSetOption` at `0x14037506b`

## string_xrefs

- `0x1403754e5`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1403754fb`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140375511`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140375527`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1403754ab`: `C:\__w\1\s\src\orchestrator\system\windows\common\HTTP.cpp`
- `0x1403754bd`: `C:\__w\1\s\src\orchestrator\system\windows\common\HTTP.cpp`
- `0x1403754cf`: `C:\__w\1\s\src\orchestrator\system\windows\common\HTTP.cpp`
- `0x1403755e5`: `C:\__w\1\s\src\orchestrator\system\windows\common\HTTP.cpp`
- `0x1403755f7`: `C:\__w\1\s\src\orchestrator\system\windows\common\HTTP.cpp`
- `0x140375609`: `C:\__w\1\s\src\orchestrator\system\windows\common\HTTP.cpp`
- `0x140375642`: `C:\__w\1\s\src\orchestrator\system\windows\common\HTTP.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall Windows::HTTP::_anonymous_namespace_::SendRequest(
        _QWORD *a1,
        LPCWSTR *a2,
        LPCWSTR *a3,
        LPCWSTR *a4,
        __int64 a5,
        __int64 a6,
        char a7)
{
  LPCWSTR *v7; // r12
  void *v9; // rax
  const char *v10; // r9
  void *v11; // r14
  const char *v12; // r9
  _QWORD *System; // rax
  volatile signed __int32 *v14; // rbx
  unsigned int (__fastcall *v15)(__int64, __int128 *, _QWORD **); // rbx
  wchar_t *traits_2_unsigned_short; // rax
  const char *v17; // r9
  __int64 v18; // r11
  __int64 v19; // rax
  __int64 v20; // rsi
  unsigned int (__fastcall *v21)(__int64, __int128 *, _QWORD **); // rbx
  wchar_t *v22; // rax
  const char *v23; // r9
  __int64 v24; // r11
  __int64 v25; // rax
  __int64 v26; // rdi
  unsigned int (__fastcall *v27)(__int64, __int128 *, _QWORD **); // rbx
  __int16 *v28; // rax
  const char *v29; // r9
  __int64 v30; // r11
  __int64 v31; // rax
  __int64 v32; // rbx
  unsigned int (__fastcall *v33)(__int64, __int128 *, _QWORD **); // r12
  wchar_t *v34; // rax
  const char *v35; // r9
  __int64 v36; // r11
  __int64 v37; // rax
  __int64 v38; // rdx
  const char *v39; // r9
  void *v40; // rax
  const char *v41; // r9
  void *v42; // rdi
  LPCWSTR *v43; // rbx
  const char *v44; // r9
  _QWORD **v45; // r12
  _QWORD *i; // rsi
  const WCHAR *v47; // rdx
  __int64 v48; // rdx
  const char *v49; // r9
  __int64 v50; // rax
  const char *v51; // r9
  volatile signed __int32 *v52; // rbx
  __int128 pExceptionObject; // [rsp+40h] [rbp-91h] BYREF
  __int64 v55; // [rsp+50h] [rbp-81h]
  _QWORD *v56; // [rsp+60h] [rbp-71h] BYREF
  LPCWSTR *v57; // [rsp+68h] [rbp-69h]
  LPCWSTR *v58; // [rsp+70h] [rbp-61h]
  LPCWSTR *v59; // [rsp+80h] [rbp-51h]
  void *v60; // [rsp+88h] [rbp-49h]
  int Buffer; // [rsp+90h] [rbp-41h] BYREF
  __int128 v62; // [rsp+98h] [rbp-39h] BYREF
  LPCWSTR lpszHeaders[2]; // [rsp+A8h] [rbp-29h] BYREF
  __int64 v64; // [rsp+B8h] [rbp-19h]
  unsigned __int64 v65; // [rsp+C0h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+47h]

  v58 = a4;
  v59 = a3;
  v7 = a2;
  v57 = a2;
  v56 = a1;
  v9 = WinHttpOpen(L"Devices", 4u, 0, 0, 0);
  v11 = v9;
  v60 = v9;
  if ( !v9 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3E,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\HTTP.cpp",
      v10);
  Buffer = 2048;
  if ( !WinHttpSetOption(v9, 0x54u, &Buffer, 4u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x41,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\HTTP.cpp",
      v12);
  v62 = 0;
  System = (_QWORD *)SystemInterface::Service::GetSystem(lpszHeaders);
  (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*System + 40LL))(*System, &v62);
  v14 = (volatile signed __int32 *)lpszHeaders[1];
  if ( lpszHeaders[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpszHeaders[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  if ( a7 )
  {
    v15 = *(unsigned int (__fastcall **)(__int64, __int128 *, _QWORD **))(*(_QWORD *)v62 + 56LL);
    LODWORD(v56) = 2;
    traits_2_unsigned_short = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                           L"HTTPResolveTimeoutInSeconds",
                                           L"{}: {}",
                                           0);
    if ( traits_2_unsigned_short == L"{}: {}"
      || (v19 = traits_2_unsigned_short - L"HTTPResolveTimeoutInSeconds", v19 == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v17);
    }
    *(_QWORD *)&pExceptionObject = L"HTTPResolveTimeoutInSeconds";
    *((_QWORD *)&pExceptionObject + 1) = v19;
    v20 = 1000LL * v15(v18, &pExceptionObject, &v56);
    v21 = *(unsigned int (__fastcall **)(__int64, __int128 *, _QWORD **))(*(_QWORD *)v62 + 56LL);
    LODWORD(v56) = 2;
    v22 = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                       L"HTTPConnectTimeoutInSeconds",
                       L"GET",
                       0);
    if ( v22 == L"GET" || (v25 = v22 - L"HTTPConnectTimeoutInSeconds", v25 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v23);
    *(_QWORD *)&pExceptionObject = L"HTTPConnectTimeoutInSeconds";
    *((_QWORD *)&pExceptionObject + 1) = v25;
    v26 = 1000LL * v21(v24, &pExceptionObject, &v56);
    v27 = *(unsigned int (__fastcall **)(__int64, __int128 *, _QWORD **))(*(_QWORD *)v62 + 56LL);
    LODWORD(v56) = 8;
    v28 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                       L"HTTPSendTimeoutInSeconds",
                       word_140487E12,
                       0);
    if ( v28 == word_140487E12 || (v31 = ((char *)v28 - (char *)L"HTTPSendTimeoutInSeconds") >> 1, v31 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v29);
    *(_QWORD *)&pExceptionObject = L"HTTPSendTimeoutInSeconds";
    *((_QWORD *)&pExceptionObject + 1) = v31;
    v32 = 1000LL * v27(v30, &pExceptionObject, &v56);
    v33 = *(unsigned int (__fastcall **)(__int64, __int128 *, _QWORD **))(*(_QWORD *)v62 + 56LL);
    LODWORD(v56) = 8;
    v34 = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                       L"HTTPReceiveTimeoutInSeconds",
                       L"POST",
                       0);
    if ( v34 == L"POST" || (v37 = v34 - L"HTTPReceiveTimeoutInSeconds", v37 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v35);
    *(_QWORD *)&pExceptionObject = L"HTTPReceiveTimeoutInSeconds";
    *((_QWORD *)&pExceptionObject + 1) = v37;
    v38 = 1000LL * v33(v36, &pExceptionObject, &v56);
    v7 = v57;
  }
  else
  {
    v38 = 60000;
    v20 = 60000;
    v26 = 60000;
    v32 = 60000;
  }
  if ( (int)v38 != v38 )
  {
    pExceptionObject = 0;
    v55 = 0;
    Concurrency::task_canceled::task_canceled((Concurrency::task_canceled *)&pExceptionObject);
    throw (gsl::narrowing_error *)&pExceptionObject;
  }
  if ( (int)v32 != v32 )
  {
    pExceptionObject = 0;
    v55 = 0;
    Concurrency::task_canceled::task_canceled((Concurrency::task_canceled *)&pExceptionObject);
    throw (gsl::narrowing_error *)&pExceptionObject;
  }
  if ( (int)v26 != v26 )
  {
    pExceptionObject = 0;
    v55 = 0;
    Concurrency::task_canceled::task_canceled((Concurrency::task_canceled *)&pExceptionObject);
    throw (gsl::narrowing_error *)&pExceptionObject;
  }
  if ( (int)v20 != v20 )
  {
    pExceptionObject = 0;
    v55 = 0;
    Concurrency::task_canceled::task_canceled((Concurrency::task_canceled *)&pExceptionObject);
    throw (gsl::narrowing_error *)&pExceptionObject;
  }
  if ( !WinHttpSetTimeouts(v11, v20, v26, v32, v38) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x4D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\HTTP.cpp",
      v39);
  v40 = WinHttpConnect(v11, *v7, 0x1BBu, 0);
  v42 = v40;
  v57 = (LPCWSTR *)v40;
  if ( !v40 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x50,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\HTTP.cpp",
      v41);
  v43 = (LPCWSTR *)WinHttpOpenRequest(v40, *v58, *v59, 0, 0, 0, 0x800000u);
  v58 = v43;
  if ( !v43 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x53,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\HTTP.cpp",
      v44);
  v45 = *(_QWORD ***)(a6 + 8);
  for ( i = *v45; i != v45; i = (_QWORD *)*i )
  {
    *(_QWORD *)&pExceptionObject = L"{}: {}";
    *((_QWORD *)&pExceptionObject + 1) = 6;
    std::format<std::wstring const &,std::wstring const &>(lpszHeaders);
    v47 = (const WCHAR *)lpszHeaders;
    if ( v65 > 7 )
      v47 = lpszHeaders[0];
    if ( !WinHttpAddRequestHeaders(v43, v47, 0xFFFFFFFF, 0x20000000u) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x57,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\HTTP.cpp",
        v49);
    std::wstring::~wstring(lpszHeaders, v48);
  }
  v50 = *(unsigned int *)(a5 + 8);
  if ( v50 != *(_QWORD *)(a5 + 8) )
  {
    *(_OWORD *)lpszHeaders = 0;
    v64 = 0;
    Concurrency::task_canceled::task_canceled((Concurrency::task_canceled *)lpszHeaders);
    throw (gsl::narrowing_error *)lpszHeaders;
  }
  if ( !WinHttpSendRequest(v43, 0, 0xFFFFFFFF, *(LPVOID *)a5, v50, v50, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x5B,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\HTTP.cpp",
      v51);
  *a1 = v11;
  a1[1] = v42;
  a1[2] = v43;
  v52 = (volatile signed __int32 *)*((_QWORD *)&v62 + 1);
  if ( *((_QWORD *)&v62 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v62 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
      if ( _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140374fe4  push    rbp
0x140374fe6  push    rbx
0x140374fe7  push    rsi
0x140374fe8  push    rdi
0x140374fe9  push    r12
0x140374feb  push    r13
0x140374fed  push    r14
0x140374fef  push    r15
0x140374ff1  lea     rbp, [rsp-7]
0x140374ff6  sub     rsp, 0D8h
0x140374ffd  mov     rax, cs:__security_cookie
0x140375004  xor     rax, rsp
0x140375007  mov     [rbp+3Fh+var_48], rax
0x14037500b  mov     [rbp+3Fh+var_A0], r9
0x14037500f  mov     [rbp+3Fh+var_90], r8
0x140375013  mov     r12, rdx
0x140375016  mov     [rbp+3Fh+var_A8], rdx
0x14037501a  mov     r15, rcx
0x14037501d  mov     [rbp+3Fh+var_B0], rcx
0x140375021  mov     r13, [rbp+3Fh+arg_20]
0x140375025  xor     edi, edi
0x140375027  mov     [rsp+110h+dwFlags], edi; dwFlags
0x14037502b  xor     r9d, r9d; pszProxyBypassW
0x14037502e  xor     r8d, r8d; pszProxyW
0x140375031  lea     ebx, [rdi+4]
0x140375034  mov     edx, ebx; dwAccessType
0x140375036  lea     rcx, pszAgentW; "Devices"
0x14037503d  call    cs:__imp_WinHttpOpen
0x140375043  mov     r14, rax
0x140375046  mov     [rbp+3Fh+var_88], rax
0x14037504a  mov     rcx, [rbp+47h]; this
0x14037504e  test    rax, rax
0x140375051  jz      loc_1403754BD
0x140375057  mov     [rbp+3Fh+Buffer], 800h
0x14037505e  mov     r9d, ebx; dwBufferLength
0x140375061  lea     r8, [rbp+3Fh+Buffer]; lpBuffer
0x140375065  lea     edx, [rdi+54h]; dwOption
0x140375068  mov     rcx, rax; hInternet
0x14037506b  call    cs:__imp_WinHttpSetOption
0x140375071  mov     rcx, [rbp+47h]; this
0x140375075  test    eax, eax
0x140375077  jz      loc_1403754CF
0x14037507d  xorps   xmm0, xmm0
0x140375080  movups  [rbp+3Fh+var_78], xmm0
0x140375084  lea     rcx, [rbp+3Fh+lpszHeaders]
0x140375088  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x14037508d  nop
0x14037508e  mov     rcx, [rax]
0x140375091  mov     rax, [rcx]
0x140375094  lea     rdx, [rbp+3Fh+var_78]
0x140375098  mov     rax, [rax+28h]
0x14037509c  call    _guard_dispatch_icall
0x1403750a1  nop
0x1403750a2  mov     rbx, [rbp+3Fh+lpszHeaders+8]
0x1403750a6  test    rbx, rbx
0x1403750a9  jz      short loc_1403750E2
0x1403750ab  or      eax, 0FFFFFFFFh
0x1403750ae  lock xadd [rbx+8], eax
0x1403750b3  cmp     eax, 1
0x1403750b6  jnz     short loc_1403750E2
0x1403750b8  mov     rax, [rbx]
0x1403750bb  mov     rcx, rbx
0x1403750be  mov     rax, [rax]
0x1403750c1  call    _guard_dispatch_icall
0x1403750c6  or      eax, 0FFFFFFFFh
0x1403750c9  lock xadd [rbx+0Ch], eax
0x1403750ce  cmp     eax, 1
0x1403750d1  jnz     short loc_1403750E2
0x1403750d3  mov     rax, [rbx]
0x1403750d6  mov     rcx, rbx
0x1403750d9  mov     rax, [rax+8]
0x1403750dd  call    _guard_dispatch_icall
0x1403750e2  cmp     [rbp+3Fh+arg_30], dil
0x1403750e6  jz      loc_1403752B6
0x1403750ec  mov     r11, qword ptr [rbp+3Fh+var_78]
0x1403750f0  mov     rax, [r11]
0x1403750f3  mov     rbx, [rax+38h]
0x1403750f7  mov     r12d, 2
0x1403750fd  mov     dword ptr [rbp+3Fh+var_B0], r12d
0x140375101  xor     r8d, r8d
0x140375104  lea     rdi, asc_140487DD0; "{}: {}"
0x14037510b  mov     rdx, rdi
0x14037510e  lea     rsi, aHttpresolvetim; "HTTPResolveTimeoutInSeconds"
0x140375115  mov     rcx, rsi
0x140375118  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x14037511d  cmp     rax, rdi
0x140375120  jz      loc_140375523
0x140375126  sub     rax, rsi
0x140375129  sar     rax, 1
0x14037512c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140375130  jz      loc_140375523
0x140375136  mov     qword ptr [rsp+110h+pExceptionObject], rsi
0x14037513b  mov     qword ptr [rsp+110h+pExceptionObject+8], rax
0x140375140  lea     r8, [rbp+3Fh+var_B0]
0x140375144  lea     rdx, [rsp+110h+pExceptionObject]
0x140375149  mov     rcx, r11
0x14037514c  mov     rax, rbx
0x14037514f  call    _guard_dispatch_icall
0x140375154  mov     eax, eax
0x140375156  imul    rsi, rax, 3E8h
0x14037515d  mov     r11, qword ptr [rbp+3Fh+var_78]
0x140375161  mov     rax, [r11]
0x140375164  mov     rbx, [rax+38h]
0x140375168  mov     dword ptr [rbp+3Fh+var_B0], r12d
0x14037516c  xor     r8d, r8d
0x14037516f  lea     rdi, aGet; "GET"
0x140375176  mov     rdx, rdi
0x140375179  lea     r12, aHttpconnecttim; "HTTPConnectTimeoutInSeconds"
0x140375180  mov     rcx, r12
0x140375183  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x140375188  cmp     rax, rdi
0x14037518b  jz      loc_14037550D
0x140375191  sub     rax, r12
0x140375194  sar     rax, 1
0x140375197  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14037519b  jz      loc_14037550D
0x1403751a1  mov     qword ptr [rsp+110h+pExceptionObject], r12
0x1403751a6  mov     qword ptr [rsp+110h+pExceptionObject+8], rax
0x1403751ab  lea     r8, [rbp+3Fh+var_B0]
0x1403751af  lea     rdx, [rsp+110h+pExceptionObject]
0x1403751b4  mov     rcx, r11
0x1403751b7  mov     rax, rbx
0x1403751ba  call    _guard_dispatch_icall
0x1403751bf  mov     eax, eax
0x1403751c1  imul    rdi, rax, 3E8h
0x1403751c8  mov     r11, qword ptr [rbp+3Fh+var_78]
0x1403751cc  mov     rax, [r11]
0x1403751cf  mov     rbx, [rax+38h]
0x1403751d3  mov     dword ptr [rbp+3Fh+var_B0], 8
0x1403751da  xor     r8d, r8d
0x1403751dd  lea     r12, word_140487E12
0x1403751e4  mov     rdx, r12
0x1403751e7  lea     rcx, aHttpsendtimeou; "HTTPSendTimeoutInSeconds"
0x1403751ee  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1403751f3  cmp     rax, r12
0x1403751f6  jz      loc_1403754F7
0x1403751fc  lea     rcx, aHttpsendtimeou; "HTTPSendTimeoutInSeconds"
0x140375203  sub     rax, rcx
0x140375206  sar     rax, 1
0x140375209  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14037520d  jz      loc_1403754F7
0x140375213  mov     qword ptr [rsp+110h+pExceptionObject], rcx
0x140375218  mov     qword ptr [rsp+110h+pExceptionObject+8], rax
0x14037521d  lea     r8, [rbp+3Fh+var_B0]
0x140375221  lea     rdx, [rsp+110h+pExceptionObject]
0x140375226  mov     rcx, r11
0x140375229  mov     rax, rbx
0x14037522c  call    _guard_dispatch_icall
0x140375231  mov     eax, eax
0x140375233  imul    rbx, rax, 3E8h
0x14037523a  mov     r11, qword ptr [rbp+3Fh+var_78]
0x14037523e  mov     rax, [r11]
0x140375241  mov     r12, [rax+38h]
0x140375245  mov     dword ptr [rbp+3Fh+var_B0], 8
0x14037524c  xor     r8d, r8d
0x14037524f  lea     rdx, aPost; "POST"
0x140375256  lea     rcx, aHttpreceivetim; "HTTPReceiveTimeoutInSeconds"
0x14037525d  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x140375262  lea     rcx, aPost; "POST"
0x140375269  cmp     rax, rcx
0x14037526c  jz      loc_1403754E1
0x140375272  lea     rcx, aHttpreceivetim; "HTTPReceiveTimeoutInSeconds"
0x140375279  sub     rax, rcx
0x14037527c  sar     rax, 1
0x14037527f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140375283  jz      loc_1403754E1
0x140375289  mov     qword ptr [rsp+110h+pExceptionObject], rcx
0x14037528e  mov     qword ptr [rsp+110h+pExceptionObject+8], rax
0x140375293  lea     r8, [rbp+3Fh+var_B0]
0x140375297  lea     rdx, [rsp+110h+pExceptionObject]
0x14037529c  mov     rcx, r11
0x14037529f  mov     rax, r12
0x1403752a2  call    _guard_dispatch_icall
0x1403752a7  mov     ecx, eax
0x1403752a9  imul    rdx, rcx, 3E8h
0x1403752b0  mov     r12, [rbp+3Fh+var_A8]
0x1403752b4  jmp     short loc_1403752C1
0x1403752b6  mov     edx, 0EA60h
0x1403752bb  mov     esi, edx
0x1403752bd  mov     edi, edx
0x1403752bf  mov     ebx, edx
0x1403752c1  movsxd  rax, edx
0x1403752c4  cmp     rax, rdx
0x1403752c7  jnz     loc_140375539
0x1403752cd  movsxd  rax, ebx
0x1403752d0  cmp     rax, rbx
0x1403752d3  jnz     loc_140375564
0x1403752d9  movsxd  rax, edi
0x1403752dc  cmp     rax, rdi
0x1403752df  jnz     loc_14037558F
0x1403752e5  movsxd  rax, esi
0x1403752e8  cmp     rax, rsi
0x1403752eb  jnz     loc_1403755BA
0x1403752f1  mov     [rsp+110h+dwFlags], edx; nReceiveTimeout
0x1403752f5  mov     r9d, ebx; nSendTimeout
0x1403752f8  mov     r8d, edi; nConnectTimeout
0x1403752fb  mov     edx, esi; nResolveTimeout
0x1403752fd  mov     rcx, r14; hInternet
0x140375300  call    cs:__imp_WinHttpSetTimeouts
0x140375306  mov     rcx, [rbp+47h]; this
0x14037530a  test    eax, eax
0x14037530c  jz      loc_1403755E5
0x140375312  mov     r8d, 1BBh; nServerPort
0x140375318  xor     r9d, r9d; dwReserved
0x14037531b  mov     rdx, [r12]; pswzServerName
0x14037531f  mov     rcx, r14; hSession
0x140375322  call    cs:__imp_WinHttpConnect
0x140375328  mov     rdi, rax
0x14037532b  mov     [rbp+3Fh+var_A8], rax
0x14037532f  mov     rcx, [rbp+47h]; this
0x140375333  test    rax, rax
0x140375336  jz      loc_1403755F7
0x14037533c  mov     [rsp+110h+var_E0], 800000h; dwFlags
0x140375344  mov     [rsp+110h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x14037534d  mov     qword ptr [rsp+110h+dwFlags], 0; pwszReferrer
0x140375356  xor     r9d, r9d; pwszVersion
0x140375359  mov     r8, [rbp+3Fh+var_90]
0x14037535d  mov     r8, [r8]; pwszObjectName
0x140375360  mov     rdx, [rbp+3Fh+var_A0]
0x140375364  mov     rdx, [rdx]; pwszVerb
0x140375367  mov     rcx, rax; hConnect
0x14037536a  call    cs:__imp_WinHttpOpenRequest
0x140375370  mov     rbx, rax
0x140375373  mov     [rbp+3Fh+var_A0], rax
0x140375377  mov     rcx, [rbp+47h]; this
0x14037537b  test    rax, rax
0x14037537e  jz      loc_140375609
0x140375384  mov     rax, [rbp+3Fh+arg_28]
0x140375388  mov     r12, [rax+8]
0x14037538c  mov     rsi, [r12]
0x140375390  cmp     rsi, r12
0x140375393  jz      short loc_140375402
0x140375395  lea     r8, [rsi+10h]
0x140375399  lea     rax, asc_140487DD0; "{}: {}"
0x1403753a0  mov     qword ptr [rsp+110h+pExceptionObject], rax
0x1403753a5  mov     qword ptr [rsp+110h+pExceptionObject+8], 6
0x1403753ae  lea     r9, [r8+20h]
0x1403753b2  lea     rdx, [rsp+110h+pExceptionObject]
0x1403753b7  lea     rcx, [rbp+3Fh+lpszHeaders]; Src
0x1403753bb  call    ??$format@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV12@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@U?$basic_format_string@_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV12@@0@AEBV10@1@Z; std::format<std::wstring const &,std::wstring const &>(std::basic_format_string<wchar_t,std::wstring const &,std::wstring const &>,std::wstring const &,std::wstring const &)
0x1403753c0  nop
0x1403753c1  lea     rdx, [rbp+3Fh+lpszHeaders]
0x1403753c5  cmp     [rbp+3Fh+var_50], 7
0x1403753ca  cmova   rdx, [rbp+3Fh+lpszHeaders]; lpszHeaders
0x1403753cf  mov     r9d, 20000000h; dwModifiers
0x1403753d5  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x1403753d9  mov     rcx, rbx; hRequest
0x1403753dc  call    cs:__imp_WinHttpAddRequestHeaders
0x1403753e2  mov     rcx, [rbp+47h]; this
0x1403753e6  test    eax, eax
0x1403753e8  jz      loc_140375642
0x1403753ee  lea     rcx, [rbp+3Fh+lpszHeaders]
0x1403753f2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1403753f7  mov     rax, [rsi]
0x1403753fa  mov     rsi, rax
0x1403753fd  cmp     rax, r12
0x140375400  jnz     short loc_140375395
0x140375402  mov     eax, [r13+8]
0x140375406  cmp     rax, [r13+8]
0x14037540a  jnz     loc_14037561B
0x140375410  mov     qword ptr [rsp+110h+var_E0], 0; dwContext
0x140375419  mov     dword ptr [rsp+110h+ppwszAcceptTypes], eax; dwTotalLength
0x14037541d  mov     [rsp+110h+dwFlags], eax; dwOptionalLength
0x140375421  mov     r9, [r13+0]; lpOptional
0x140375425  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x140375429  xor     edx, edx; lpszHeaders
0x14037542b  mov     rcx, rbx; hRequest
0x14037542e  call    cs:__imp_WinHttpSendRequest
0x140375434  mov     rcx, [rbp+47h]; this
0x140375438  test    eax, eax
0x14037543a  jz      short loc_1403754AB
0x14037543c  mov     [r15], r14
0x14037543f  mov     [r15+8], rdi
0x140375443  mov     [r15+10h], rbx
0x140375447  mov     rbx, qword ptr [rbp+3Fh+var_78+8]
0x14037544b  test    rbx, rbx
0x14037544e  jz      short loc_140375488
0x140375450  or      eax, 0FFFFFFFFh
0x140375453  lock xadd [rbx+8], eax
0x140375458  cmp     eax, 1
0x14037545b  jnz     short loc_140375488
0x14037545d  mov     rax, [rbx]
0x140375460  mov     rcx, rbx
0x140375463  mov     rax, [rax]
0x140375466  call    _guard_dispatch_icall
0x14037546b  or      edx, 0FFFFFFFFh
0x14037546e  lock xadd [rbx+0Ch], edx
0x140375473  cmp     edx, 1
0x140375476  jnz     short loc_140375488
0x140375478  mov     rdx, [rbx]
0x14037547b  mov     rcx, rbx
0x14037547e  mov     rax, [rdx+8]
0x140375482  call    _guard_dispatch_icall
0x140375487  nop
0x140375488  mov     rax, r15
0x14037548b  mov     rcx, [rbp+3Fh+var_48]
0x14037548f  xor     rcx, rsp; StackCookie
0x140375492  call    __security_check_cookie
0x140375497  add     rsp, 0D8h
0x14037549e  pop     r15
  ... truncated ...
```
