# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x140009a40`
- end: `0x140009d83`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `835`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400098ec`

## callees

- `0x1400013c0`
- `0x1400016f0`
- `0x1400022c4`
- `0x1400022e8`
- `0x140002324`
- `0x140002330`
- `0x14000233c`
- `0x140002348`
- `0x1400094c0`
- `0x1400095cc`
- `0x140009760`
- `0x140009a40`
- `0x14000a428`
- `0x14000b3f0`
- `0x14000c010`

## string_xrefs

- `0x140009aa9`: `combase.dll`
- `0x140009cc2`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  LPCWSTR *v12; // r14
  char *v13; // rdi
  __int64 last_trivial_2; // rax
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rdi
  LPCWSTR *v17; // rcx
  unsigned __int64 v18; // rcx
  LPCWSTR *v19; // r8
  _WORD *v20; // rdi
  unsigned __int64 v21; // rdi
  LPCWSTR *v22; // rcx
  const WCHAR *v23; // rcx
  HMODULE v24; // rdi
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // r8
  LPCWSTR *v27; // rcx
  FARPROC v28; // rax
  unsigned int (__fastcall ***v30)(_QWORD, __int64, __int64); // [rsp+30h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int64 v33; // [rsp+50h] [rbp-28h]
  unsigned __int64 v34; // [rsp+58h] [rbp-20h]

  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, __int64))winrt_activation_handler)(v8, a3, a4);
    return a1;
  }
  ActivationFactory_0 = RoGetActivationFactory_0(v8, a3, a4);
  if ( ActivationFactory_0 == -2147221008 )
  {
    Library = LoadLibraryExW_0(L"combase.dll", 0, 0x1000u);
    ProcAddress = WINRT_IMPL_GetProcAddress(Library, "CoIncrementMTAUsage");
    if ( !ProcAddress )
    {
      *a1 = -2147221008;
      return a1;
    }
    v30 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v30);
    ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
  }
  if ( !ActivationFactory_0 )
  {
    *a1 = 0;
    return a1;
  }
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  std::wstring::wstring(lpLibFileName, a2);
  while ( 1 )
  {
    do
    {
      v12 = lpLibFileName;
      if ( v34 > 7 )
        v12 = (LPCWSTR *)lpLibFileName[0];
      if ( !v33
        || (v13 = (char *)v12 + 2 * v33,
            last_trivial_2 = _std_find_last_trivial_2(v12, v13, 46),
            (char *)last_trivial_2 == v13)
        || (v15 = (last_trivial_2 - (__int64)v12) >> 1, v15 == -1) )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        goto LABEL_54;
      }
      v16 = v33;
      if ( v15 > v33 )
      {
        v18 = v15 - v33;
        if ( v15 - v33 > v34 - v33 )
        {
          ____Reallocate_grow_by_V_lambda_1___1__append___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAAEAV34__K_W_Z__K_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0_W_Z__K_W_Z(lpLibFileName);
        }
        else
        {
          v33 = (last_trivial_2 - (__int64)v12) >> 1;
          v19 = lpLibFileName;
          if ( v34 > 7 )
            v19 = (LPCWSTR *)lpLibFileName[0];
          v20 = (_WORD *)v19 + v16;
          if ( v18 )
          {
            while ( v18 )
            {
              *v20++ = 0;
              --v18;
            }
          }
          *((_WORD *)v19 + v15) = 0;
        }
      }
      else
      {
        v33 = (last_trivial_2 - (__int64)v12) >> 1;
        v17 = lpLibFileName;
        if ( v34 > 7 )
          v17 = (LPCWSTR *)lpLibFileName[0];
        *((_WORD *)v17 + v15) = 0;
      }
      v21 = v33;
      if ( v34 - v33 < 4 )
      {
        ____Reallocate_grow_by_V_lambda_1___1_____Append__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W_K___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Append__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_K_Z(
          lpLibFileName,
          4);
      }
      else
      {
        v33 += 4LL;
        v22 = lpLibFileName;
        if ( v34 > 7 )
          v22 = (LPCWSTR *)lpLibFileName[0];
        *(LPCWSTR *)((char *)v22 + 2 * v21) = (LPCWSTR)0x6C006C0064002ELL;
        *((_WORD *)v22 + v21 + 4) = 0;
      }
      v23 = (const WCHAR *)lpLibFileName;
      if ( v34 > 7 )
        v23 = lpLibFileName[0];
      v24 = LoadLibraryExW_0(v23, 0, 0x1000u);
      v25 = v33;
      v26 = v33 - 4;
      v27 = lpLibFileName;
      if ( v33 >= 4 )
      {
        v33 -= 4LL;
        if ( v34 > 7 )
          v27 = (LPCWSTR *)lpLibFileName[0];
LABEL_42:
        *((_WORD *)v27 + v26) = 0;
        continue;
      }
      if ( v34 - v33 >= 0xFFFFFFFFFFFFFFFCuLL )
      {
        v33 -= 4LL;
        if ( v34 > 7 )
          v27 = (LPCWSTR *)lpLibFileName[0];
        *(LPCWSTR *)((char *)v27 + 2 * v25) = 0;
        goto LABEL_42;
      }
      ____Reallocate_grow_by_V_lambda_1___1__append___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAAEAV34__K_W_Z__K_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0_W_Z__K_W_Z(lpLibFileName);
    }
    while ( !v24 );
    v28 = WINRT_IMPL_GetProcAddress(v24, "DllGetActivationFactory");
    if ( !v28 )
      goto LABEL_50;
    v30 = 0;
    if ( !((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v28)(
            *a2,
            &v30)
      && !(**v30)(v30, a3, a4) )
    {
      break;
    }
    if ( v30 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v30);
LABEL_50:
    WINRT_IMPL_FreeLibrary(v24);
  }
  *a1 = 0;
  if ( v30 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v30);
LABEL_54:
  std::wstring::~wstring(lpLibFileName);
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x140009a40  push    rbp
0x140009a42  push    rbx
0x140009a43  push    rsi
0x140009a44  push    rdi
0x140009a45  push    r12
0x140009a47  push    r13
0x140009a49  push    r14
0x140009a4b  push    r15
0x140009a4d  mov     rbp, rsp
0x140009a50  sub     rsp, 78h
0x140009a54  mov     rax, cs:__security_cookie
0x140009a5b  xor     rax, rsp
0x140009a5e  mov     [rbp+var_18], rax
0x140009a62  mov     r12, r9
0x140009a65  mov     r15, r8
0x140009a68  mov     r13, rdx
0x140009a6b  mov     rsi, rcx
0x140009a6e  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x140009a75  xor     r14d, r14d
0x140009a78  mov     r8, r9
0x140009a7b  mov     rdx, r15
0x140009a7e  mov     rcx, [r13+0]
0x140009a82  test    rax, rax
0x140009a85  jz      short loc_140009A93
0x140009a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009a8c  mov     [rsi], eax
0x140009a8e  jmp     loc_140009D63
0x140009a93  call    RoGetActivationFactory_0
0x140009a98  mov     ebx, eax
0x140009a9a  cmp     eax, 800401F0h
0x140009a9f  jnz     short loc_140009AF2
0x140009aa1  xor     edx, edx; hFile
0x140009aa3  mov     r8d, 1000h; dwFlags
0x140009aa9  lea     rcx, LibFileName; "combase.dll"
0x140009ab0  call    LoadLibraryExW_0
0x140009ab5  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x140009abc  mov     rcx, rax; hModule
0x140009abf  call    WINRT_IMPL_GetProcAddress
0x140009ac4  test    rax, rax
0x140009ac7  jnz     short loc_140009AD4
0x140009ac9  mov     dword ptr [rsi], 800401F0h
0x140009acf  jmp     loc_140009D63
0x140009ad4  mov     [rbp+var_48], r14
0x140009ad8  lea     rcx, [rbp+var_48]
0x140009adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ae1  mov     r8, r12
0x140009ae4  mov     rdx, r15
0x140009ae7  mov     rcx, [r13+0]
0x140009aeb  call    RoGetActivationFactory_0
0x140009af0  mov     ebx, eax
0x140009af2  test    ebx, ebx
0x140009af4  jnz     short loc_140009AFE
0x140009af6  mov     [rsi], r14d
0x140009af9  jmp     loc_140009D63
0x140009afe  mov     [rbp+pperrinfo], r14
0x140009b02  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x140009b06  xor     ecx, ecx; dwReserved
0x140009b08  call    GetErrorInfo_0
0x140009b0d  mov     rdx, r13
0x140009b10  lea     rcx, [rbp+lpLibFileName]
0x140009b14  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<wchar_t> const &)
0x140009b19  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140009b1d  mov     rax, [rbp+var_28]
0x140009b21  lea     r14, [rbp+lpLibFileName]
0x140009b25  cmp     [rbp+var_20], 7
0x140009b2a  cmova   r14, [rbp+lpLibFileName]
0x140009b2f  test    rax, rax
0x140009b32  jz      loc_140009D3D
0x140009b38  dec     rax
0x140009b3b  cmp     rax, rcx
0x140009b3e  cmovnb  rax, rcx
0x140009b42  inc     rax
0x140009b45  lea     rdi, [r14+rax*2]
0x140009b49  mov     r8d, 2Eh ; '.'
0x140009b4f  mov     rdx, rdi
0x140009b52  mov     rcx, r14
0x140009b55  call    __std_find_last_trivial_2
0x140009b5a  mov     rdx, rax
0x140009b5d  cmp     rax, rdi
0x140009b60  jz      loc_140009D3D
0x140009b66  sub     rdx, r14
0x140009b69  sar     rdx, 1
0x140009b6c  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x140009b70  jz      loc_140009D3D
0x140009b76  mov     rdi, [rbp+var_28]
0x140009b7a  cmp     rdx, rdi
0x140009b7d  ja      short loc_140009B99
0x140009b7f  mov     [rbp+var_28], rdx
0x140009b83  lea     rcx, [rbp+lpLibFileName]
0x140009b87  cmp     [rbp+var_20], 7
0x140009b8c  cmova   rcx, [rbp+lpLibFileName]
0x140009b91  xor     eax, eax
0x140009b93  mov     [rcx+rdx*2], ax
0x140009b97  jmp     short loc_140009BE6
0x140009b99  mov     rcx, rdx
0x140009b9c  sub     rcx, rdi
0x140009b9f  mov     rax, [rbp+var_20]
0x140009ba3  sub     rax, rdi
0x140009ba6  cmp     rcx, rax
0x140009ba9  ja      short loc_140009BD7
0x140009bab  mov     [rbp+var_28], rdx
0x140009baf  lea     r8, [rbp+lpLibFileName]
0x140009bb3  cmp     [rbp+var_20], 7
0x140009bb8  cmova   r8, [rbp+lpLibFileName]
0x140009bbd  lea     rdi, [r8+rdi*2]
0x140009bc1  test    rcx, rcx
0x140009bc4  jz      short loc_140009BCE
0x140009bc6  xor     eax, eax
0x140009bc8  movzx   eax, ax
0x140009bcb  rep stosw
0x140009bce  xor     eax, eax
0x140009bd0  mov     [r8+rdx*2], ax
0x140009bd5  jmp     short loc_140009BE6
0x140009bd7  mov     r9, rcx
0x140009bda  mov     rdx, rcx
0x140009bdd  lea     rcx, [rbp+lpLibFileName]; Src
0x140009be1  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@_K_W@Z@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0_W@Z@_K_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t>(unsigned __int64,`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t)
0x140009be6  mov     rdi, [rbp+var_28]
0x140009bea  mov     rax, [rbp+var_20]
0x140009bee  sub     rax, rdi
0x140009bf1  mov     ecx, 4
0x140009bf6  cmp     rax, rcx
0x140009bf9  jb      short loc_140009C27
0x140009bfb  lea     rdx, [rdi+4]
0x140009bff  mov     [rbp+var_28], rdx
0x140009c03  lea     rcx, [rbp+lpLibFileName]
0x140009c07  cmp     [rbp+var_20], 7
0x140009c0c  cmova   rcx, [rbp+lpLibFileName]
0x140009c11  mov     rax, 6C006C0064002Eh
0x140009c1b  mov     [rcx+rdi*2], rax
0x140009c1f  xor     eax, eax
0x140009c21  mov     [rcx+rdx*2], ax
0x140009c25  jmp     short loc_140009C38
0x140009c27  mov     [rsp+78h+var_58], rcx; __int64
0x140009c2c  mov     rdx, rcx
0x140009c2f  lea     rcx, [rbp+lpLibFileName]; Src
0x140009c33  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *,unsigned __int64)
0x140009c38  lea     rcx, [rbp+lpLibFileName]
0x140009c3c  cmp     [rbp+var_20], 7
0x140009c41  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x140009c46  xor     edx, edx; hFile
0x140009c48  mov     r8d, 1000h; dwFlags
0x140009c4e  call    LoadLibraryExW_0
0x140009c53  mov     rdi, rax
0x140009c56  mov     rdx, [rbp+var_28]
0x140009c5a  lea     r8, [rdx-4]
0x140009c5e  lea     rcx, [rbp+lpLibFileName]; Src
0x140009c62  cmp     r8, rdx
0x140009c65  ja      short loc_140009C79
0x140009c67  mov     [rbp+var_28], r8
0x140009c6b  cmp     [rbp+var_20], 7
0x140009c70  cmova   rcx, [rbp+lpLibFileName]
0x140009c75  xor     eax, eax
0x140009c77  jmp     short loc_140009CA0
0x140009c79  mov     rax, [rbp+var_20]
0x140009c7d  sub     rax, rdx
0x140009c80  mov     r10, 0FFFFFFFFFFFFFFFCh
0x140009c87  cmp     rax, r10
0x140009c8a  jb      short loc_140009CA7
0x140009c8c  mov     [rbp+var_28], r8
0x140009c90  cmp     [rbp+var_20], 7
0x140009c95  cmova   rcx, [rbp+lpLibFileName]
0x140009c9a  xor     eax, eax
0x140009c9c  mov     [rcx+rdx*2], rax
0x140009ca0  mov     [rcx+r8*2], ax
0x140009ca5  jmp     short loc_140009CB2
0x140009ca7  mov     r9, r10
0x140009caa  mov     rdx, r10
0x140009cad  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@_K_W@Z@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0_W@Z@_K_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t>(unsigned __int64,`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t)
0x140009cb2  test    rdi, rdi
0x140009cb5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140009cbc  jz      loc_140009B1D
0x140009cc2  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x140009cc9  mov     rcx, rdi; hModule
0x140009ccc  call    WINRT_IMPL_GetProcAddress
0x140009cd1  test    rax, rax
0x140009cd4  jz      short loc_140009D18
0x140009cd6  mov     [rbp+var_48], 0
0x140009cde  lea     rdx, [rbp+var_48]
0x140009ce2  mov     rcx, [r13+0]
0x140009ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ceb  test    eax, eax
0x140009ced  jnz     short loc_140009D08
0x140009cef  mov     rcx, [rbp+var_48]
0x140009cf3  mov     rax, [rcx]
0x140009cf6  mov     r8, r12
0x140009cf9  mov     rdx, r15
0x140009cfc  mov     rax, [rax]
0x140009cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d04  test    eax, eax
0x140009d06  jz      short loc_140009D25
0x140009d08  cmp     [rbp+var_48], 0
0x140009d0d  jz      short loc_140009D18
0x140009d0f  lea     rcx, [rbp+var_48]
0x140009d13  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x140009d18  mov     rcx, rdi; hLibModule
0x140009d1b  call    WINRT_IMPL_FreeLibrary
0x140009d20  jmp     loc_140009B19
0x140009d25  mov     dword ptr [rsi], 0
0x140009d2b  cmp     [rbp+var_48], 0
0x140009d30  jz      short loc_140009D4A
0x140009d32  lea     rcx, [rbp+var_48]
0x140009d36  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x140009d3b  jmp     short loc_140009D4A
0x140009d3d  mov     rdx, [rbp+pperrinfo]; perrinfo
0x140009d41  xor     ecx, ecx; dwReserved
0x140009d43  call    SetErrorInfo_0
0x140009d48  mov     [rsi], ebx
0x140009d4a  lea     rcx, [rbp+lpLibFileName]
0x140009d4e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140009d53  cmp     [rbp+pperrinfo], 0
0x140009d58  jz      short loc_140009D63
0x140009d5a  lea     rcx, [rbp+pperrinfo]
0x140009d5e  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x140009d63  mov     rax, rsi
0x140009d66  mov     rcx, [rbp+var_18]
0x140009d6a  xor     rcx, rsp; StackCookie
0x140009d6d  call    __security_check_cookie
0x140009d72  add     rsp, 78h
0x140009d76  pop     r15
0x140009d78  pop     r14
0x140009d7a  pop     r13
0x140009d7c  pop     r12
0x140009d7e  pop     rdi
0x140009d7f  pop     rsi
0x140009d80  pop     rbx
0x140009d81  pop     rbp
0x140009d82  retn
```
