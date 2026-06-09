# _lambda_cf59f7f2adf01739b63675bbfd49b35b_::operator()

- ea: `0x180019044`
- end: `0x1800193e4`
- name: `_lambda_cf59f7f2adf01739b63675bbfd49b35b_::operator()`
- size: `928`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001b4f0`

## callees

- `0x18000e2bc`
- `0x18001136c`
- `0x180018b18`
- `0x180018d14`
- `0x180019044`
- `0x180019e60`
- `0x18001bd7c`
- `0x18001c6ec`
- `0x18001cd34`
- `0x18001cd80`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001912d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001912d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800192b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800192b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001920f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001920f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800191b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800192d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800192e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800191b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800192d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800192e6`

## string_xrefs

- `0x1800193bc`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18001937e`: `shell\oobe\user\dll\oobesyncengineapi.cpp`
- `0x180019392`: `shell\oobe\user\dll\oobesyncengineapi.cpp`
- `0x1800193a7`: `shell\oobe\user\dll\oobesyncengineapi.cpp`
- `0x1800193d1`: `shell\oobe\user\dll\oobesyncengineapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall lambda_cf59f7f2adf01739b63675bbfd49b35b_::operator()(_DWORD ***a1)
{
  int v2; // eax
  __int64 v3; // rbx
  int v4; // eax
  const char *v5; // r9
  __int64 result; // rax
  _DWORD *v7; // rcx
  HRESULT v8; // eax
  int i; // eax
  __int64 (__fastcall *v10)(__int64, _QWORD, HSTRING *); // rbx
  int v11; // eax
  LPVOID v12; // rdi
  __int64 (__fastcall *v13)(LPVOID, PCWSTR, char *); // rbx
  PCWSTR StringRawBuffer; // rax
  unsigned int v15; // ebx
  char v16; // al
  int v17; // r9d
  void *v18; // rcx
  int v19; // r8d
  unsigned __int64 j; // rdx
  int v21; // eax
  int ppv; // [rsp+20h] [rbp-D8h]
  __int64 v23; // [rsp+30h] [rbp-C8h]
  unsigned int v24; // [rsp+38h] [rbp-C0h]
  HSTRING string; // [rsp+40h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B0h] BYREF
  __int128 v27; // [rsp+50h] [rbp-A8h] BYREF
  char v28; // [rsp+60h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-88h] BYREF
  __int64 v30; // [rsp+80h] [rbp-78h]
  unsigned __int64 v31; // [rsp+88h] [rbp-70h]
  _BYTE v32[8]; // [rsp+90h] [rbp-68h] BYREF
  int v33; // [rsp+98h] [rbp-60h]
  HSTRING v34; // [rsp+A0h] [rbp-58h]
  _BYTE v35[16]; // [rsp+A8h] [rbp-50h] BYREF
  char v36; // [rsp+B8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]
  __int64 v38; // [rsp+100h] [rbp+8h] BYREF
  int v39; // [rsp+108h] [rbp+10h] BYREF
  LPVOID v40; // [rsp+110h] [rbp+18h] BYREF
  __int64 v41; // [rsp+118h] [rbp+20h] BYREF

  v41 = 0;
  try
  {
    v2 = OOBEOneDriveOptin::TokenizeAumids();
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x129,
        (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
        (const char *)(unsigned int)v2,
        ppv);
    v39 = 0;
    v3 = v41;
    v4 = OOBEOneDriveOptin::GetAndValidateNumRequests(retaddr, v41, &v39);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12D,
        (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
        (const char *)(unsigned int)v4,
        ppv);
    if ( v39 )
    {
      **a1[2] = v39;
      v7 = (*a1)[6];
      v40 = v7;
      if ( v7 )
      {
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 8LL))(v7);
        v7 = v40;
      }
      if ( !v7 )
      {
        v40 = 0;
        v8 = CoCreateInstance(&CLSID_TaskbandPin, 0, 1u, &GUID_53d51c3c_d7e0_4fec_b4c6_33b4f8a41c64, &v40);
        if ( v8 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x139,
            (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
            (const char *)(unsigned int)v8,
            ppv);
      }
      v29 = 0;
      v30 = 0;
      v31 = 0;
      v38 = v3;
      v23 = v3;
      v24 = 0;
      string = 0;
      wil::vector_range<Windows::Foundation::Collections::IVector<HSTRING__ *>,wil::err_exception_policy>::end(
        &v38,
        v32);
      for ( i = 0; i != v33; i = ++v24 )
      {
        v10 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v23 + 48LL);
        WindowsDeleteString(string);
        string = 0;
        v11 = v10(v23, v24, &string);
        if ( v11 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1CBE,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
            (const char *)(unsigned int)v11,
            ppv);
        pv = 0;
        v12 = v40;
        v13 = *(__int64 (__fastcall **)(LPVOID, PCWSTR, char *))(*(_QWORD *)v40 + 120LL);
        *(_QWORD *)&v27 = &pv;
        *((_QWORD *)&v27 + 1) = 0;
        v28 = 1;
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v15 = v13(v12, StringRawBuffer, (char *)&v27 + 8);
        wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v27);
        if ( ((v15 + 0x80000000) & 0x80000000) != 0 || (v16 = 1, v15 == -2147023728) )
          v16 = 0;
        if ( v16 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x142,
            (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
            (const char *)v15,
            ppv);
        LOBYTE(v38) = (v15 & 0x80000000) == 0;
        v27 = *(_OWORD *)std::vector<bool>::end(&v29, v35);
        std::vector<bool>::_Insert_n((unsigned int)&v29, (unsigned int)&v36, (unsigned int)&v27, v17, (__int64)&v38);
        v18 = pv;
        pv = 0;
        if ( v18 )
          CoTaskMemFree(v18);
      }
      WindowsDeleteString(v34);
      v34 = 0;
      WindowsDeleteString(string);
      v19 = 0;
      for ( j = 0; j < v31; ++j )
      {
        v21 = *(_DWORD *)(v29 + 4 * (j >> 5));
        if ( _bittest(&v21, j & 0x1F) )
          v19 |= 1 << j;
      }
      **a1[3] = v19;
      std::vector<bool>::~vector<bool>(&v29, j);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v40);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v41);
      result = 0;
    }
    else
    {
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v41);
      result = 0;
    }
  }
  catch ( ... )
  {
    LODWORD(v38) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x151,
                     (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
                     v5);
    return (unsigned int)v38;
  }
  return result;
}

```

## disassembly

```asm
0x180019044  mov     rax, rsp
0x180019047  push    rbx
0x180019048  push    rsi
0x180019049  push    rdi
0x18001904a  push    r14
0x18001904c  push    r15
0x18001904e  sub     rsp, 0D0h
0x180019055  mov     rsi, rcx
0x180019058  xor     r14d, r14d
0x18001905b  mov     [rax+20h], r14
0x18001905f  mov     rdx, [rcx+8]
0x180019063  lea     r8, [rax+20h]
0x180019067  mov     rdx, [rdx]
0x18001906a  call    ?TokenizeAumids@OOBEOneDriveOptin@@AEAAJPEBGPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@Z; OOBEOneDriveOptin::TokenizeAumids(ushort const *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x18001906f  mov     rcx, [rsp+0F8h]; this
0x180019077  test    eax, eax
0x180019079  js      loc_18001937B
0x18001907f  mov     [rsp+0F8h+arg_8], r14d
0x180019087  lea     r8, [rsp+0F8h+arg_8]
0x18001908f  mov     rbx, [rsp+0F8h+arg_18]
0x180019097  mov     rdx, rbx
0x18001909a  call    ?GetAndValidateNumRequests@OOBEOneDriveOptin@@AEAAJPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@PEAI@Z; OOBEOneDriveOptin::GetAndValidateNumRequests(Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *,uint *)
0x18001909f  mov     rcx, [rsp+0F8h]; this
0x1800190a7  test    eax, eax
0x1800190a9  js      loc_18001938F
0x1800190af  mov     edx, [rsp+0F8h+arg_8]
0x1800190b6  test    edx, edx
0x1800190b8  jnz     short loc_1800190CE
0x1800190ba  lea     rcx, [rsp+0F8h+arg_18]
0x1800190c2  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x1800190c7  xor     eax, eax
0x1800190c9  jmp     loc_18001936C
0x1800190ce  mov     rax, [rsi+10h]
0x1800190d2  mov     rcx, [rax]
0x1800190d5  mov     [rcx], edx
0x1800190d7  mov     rcx, [rsi]
0x1800190da  mov     rcx, [rcx+30h]
0x1800190de  mov     [rsp+0F8h+arg_10], rcx
0x1800190e6  test    rcx, rcx
0x1800190e9  jz      short loc_1800190FF
0x1800190eb  mov     rax, [rcx]
0x1800190ee  mov     rax, [rax+8]
0x1800190f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190f7  mov     rcx, [rsp+0F8h+arg_10]
0x1800190ff  test    rcx, rcx
0x180019102  jnz     short loc_180019143
0x180019104  mov     [rsp+0F8h+arg_10], r14
0x18001910c  lea     rax, [rsp+0F8h+arg_10]
0x180019114  mov     qword ptr [rsp+0F8h+ppv], rax; int
0x180019119  lea     r9, _GUID_53d51c3c_d7e0_4fec_b4c6_33b4f8a41c64; riid
0x180019120  xor     edx, edx; pUnkOuter
0x180019122  lea     r8d, [rcx+1]; dwClsContext
0x180019126  lea     rcx, CLSID_TaskbandPin; rclsid
0x18001912d  call    cs:__imp_CoCreateInstance
0x180019133  mov     rcx, [rsp+0F8h]; this
0x18001913b  test    eax, eax
0x18001913d  js      loc_1800193A4
0x180019143  xorps   xmm0, xmm0
0x180019146  movdqu  [rsp+0F8h+var_88], xmm0
0x18001914c  mov     [rsp+0F8h+var_78], r14
0x180019154  mov     [rsp+0F8h+var_70], r14
0x18001915c  mov     [rsp+0F8h+arg_0], rbx
0x180019164  mov     [rsp+0F8h+var_C8], rbx
0x180019169  mov     [rsp+0F8h+var_C0], r14d
0x18001916e  mov     [rsp+0F8h+string], r14
0x180019173  lea     rdx, [rsp+0F8h+var_68]
0x18001917b  lea     rcx, [rsp+0F8h+arg_0]
0x180019183  call    ?end@?$vector_range@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVector<HSTRING__ *>,wil::err_exception_policy>::end(void)
0x180019188  nop
0x180019189  mov     r15d, 80000000h
0x18001918f  mov     eax, [rsp+0F8h+var_C0]
0x180019193  cmp     eax, [rsp+0F8h+var_60]
0x18001919a  jz      loc_1800192CB
0x1800191a0  mov     rdi, [rsp+0F8h+var_C8]
0x1800191a5  mov     rax, [rdi]
0x1800191a8  mov     rbx, [rax+30h]
0x1800191ac  mov     rcx, [rsp+0F8h+string]; string
0x1800191b1  call    cs:__imp_WindowsDeleteString
0x1800191b7  mov     [rsp+0F8h+string], r14
0x1800191bc  lea     r8, [rsp+0F8h+string]
0x1800191c1  mov     edx, [rsp+0F8h+var_C0]
0x1800191c5  mov     rcx, rdi
0x1800191c8  mov     rax, rbx
0x1800191cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191d0  mov     rcx, [rsp+0F8h]; this
0x1800191d8  test    eax, eax
0x1800191da  js      loc_1800193B9
0x1800191e0  mov     [rsp+0F8h+pv], r14
0x1800191e5  mov     rdi, [rsp+0F8h+arg_10]
0x1800191ed  mov     rax, [rdi]
0x1800191f0  mov     rbx, [rax+78h]
0x1800191f4  lea     rax, [rsp+0F8h+pv]
0x1800191f9  mov     qword ptr [rsp+0F8h+var_A8], rax
0x1800191fe  mov     qword ptr [rsp+0F8h+var_A8+8], r14
0x180019203  mov     [rsp+0F8h+var_98], 1
0x180019208  xor     edx, edx; length
0x18001920a  mov     rcx, [rsp+0F8h+string]; string
0x18001920f  call    cs:__imp_WindowsGetStringRawBuffer
0x180019215  lea     r8, [rsp+0F8h+var_A8+8]
0x18001921a  mov     rdx, rax
0x18001921d  mov     rcx, rdi
0x180019220  mov     rax, rbx
0x180019223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019228  mov     ebx, eax
0x18001922a  lea     rcx, [rsp+0F8h+var_A8]
0x18001922f  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180019234  lea     ecx, [rbx+r15]
0x180019238  test    r15d, ecx
0x18001923b  jnz     short loc_180019247
0x18001923d  cmp     ebx, 80070490h
0x180019243  mov     al, 1
0x180019245  jnz     short loc_18001924A
0x180019247  mov     al, r14b
0x18001924a  mov     rcx, [rsp+0F8h]; this
0x180019252  test    al, al
0x180019254  jnz     loc_1800193CE
0x18001925a  shr     ebx, 1Fh
0x18001925d  xor     bl, 1
0x180019260  mov     byte ptr [rsp+0F8h+arg_0], bl
0x180019267  lea     rdx, [rsp+0F8h+var_50]
0x18001926f  lea     rcx, [rsp+0F8h+var_88]
0x180019274  call    ?end@?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@2@XZ; std::vector<bool>::end(void)
0x180019279  movups  xmm0, xmmword ptr [rax]
0x18001927c  movdqu  [rsp+0F8h+var_A8], xmm0
0x180019282  lea     rax, [rsp+0F8h+arg_0]
0x18001928a  mov     qword ptr [rsp+0F8h+ppv], rax
0x18001928f  lea     r8, [rsp+0F8h+var_A8]
0x180019294  lea     rdx, [rsp+0F8h+var_40]
0x18001929c  lea     rcx, [rsp+0F8h+var_88]
0x1800192a1  call    ?_Insert_n@?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@2@V?$_Vb_const_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@2@_KAEB_N@Z; std::vector<bool>::_Insert_n(std::_Vb_const_iterator<std::_Wrap_alloc<std::allocator<uint>>>,unsigned __int64,bool const &)
0x1800192a6  nop
0x1800192a7  mov     rcx, [rsp+0F8h+pv]; pv
0x1800192ac  mov     [rsp+0F8h+pv], r14
0x1800192b1  test    rcx, rcx
0x1800192b4  jz      short loc_1800192BC
0x1800192b6  call    cs:__imp_CoTaskMemFree
0x1800192bc  mov     eax, [rsp+0F8h+var_C0]
0x1800192c0  inc     eax
0x1800192c2  mov     [rsp+0F8h+var_C0], eax
0x1800192c6  jmp     loc_180019193
0x1800192cb  mov     rcx, [rsp+0F8h+var_58]; string
0x1800192d3  call    cs:__imp_WindowsDeleteString
0x1800192d9  mov     [rsp+0F8h+var_58], r14
0x1800192e1  mov     rcx, [rsp+0F8h+string]; string
0x1800192e6  call    cs:__imp_WindowsDeleteString
0x1800192ec  mov     r8d, r14d
0x1800192ef  mov     rdx, r14
0x1800192f2  mov     r9, [rsp+0F8h+var_70]
0x1800192fa  test    r9, r9
0x1800192fd  jz      short loc_180019330
0x1800192ff  mov     r10, qword ptr [rsp+0F8h+var_88]
0x180019304  mov     al, dl
0x180019306  and     al, 1Fh
0x180019308  movzx   ecx, al
0x18001930b  mov     rax, rdx
0x18001930e  shr     rax, 5
0x180019312  mov     eax, [r10+rax*4]
0x180019316  bt      eax, ecx
0x180019319  jnb     short loc_180019328
0x18001931b  mov     rcx, rdx
0x18001931e  mov     eax, 1
0x180019323  shl     eax, cl
0x180019325  or      r8d, eax
0x180019328  inc     rdx
0x18001932b  cmp     rdx, r9
0x18001932e  jb      short loc_180019304
0x180019330  mov     rax, [rsi+18h]
0x180019334  mov     rcx, [rax]
0x180019337  mov     [rcx], r8d
0x18001933a  lea     rcx, [rsp+0F8h+var_88]
0x18001933f  call    ??1?$vector@_NV?$allocator@_N@std@@@std@@QEAA@XZ; std::vector<bool>::~vector<bool>(void)
0x180019344  nop
0x180019345  lea     rcx, [rsp+0F8h+arg_10]
0x18001934d  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180019352  nop
0x180019353  lea     rcx, [rsp+0F8h+arg_18]
0x18001935b  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180019360  nop
0x180019361  xor     eax, eax
0x180019363  jmp     short loc_18001936C
0x180019365  mov     eax, dword ptr [rsp+0F8h+arg_0]
0x18001936c  add     rsp, 0D0h
0x180019373  pop     r15
0x180019375  pop     r14
0x180019377  pop     rdi
0x180019378  pop     rsi
0x180019379  pop     rbx
0x18001937a  retn
0x18001937b  mov     r9d, eax; char *
0x18001937e  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x180019385  mov     edx, 129h; void *
0x18001938a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001938f  mov     r9d, eax; char *
0x180019392  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x180019399  mov     edx, 12Dh; void *
0x18001939e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800193a4  mov     r9d, eax; char *
0x1800193a7  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x1800193ae  mov     edx, 139h; void *
0x1800193b3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800193b9  mov     r9d, eax; char *
0x1800193bc  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800193c3  mov     edx, 1CBEh; void *
0x1800193c8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800193ce  mov     r9d, ebx; char *
0x1800193d1  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x1800193d8  mov     edx, 142h; void *
0x1800193dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
