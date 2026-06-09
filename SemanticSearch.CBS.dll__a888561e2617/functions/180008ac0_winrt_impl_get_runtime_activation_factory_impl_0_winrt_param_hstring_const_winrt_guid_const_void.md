# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x180008ac0`
- end: `0x180008e5a`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `922`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, __int64)`
- caller_count: `39`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008080`
- `0x180008350`
- `0x180008ef0`
- `0x180009900`
- `0x18002ff90`
- `0x1800301b0`
- `0x180030380`
- `0x180030590`
- `0x180030820`
- `0x1800309e0`
- `0x180030c90`
- `0x180030e50`
- `0x180031070`
- `0x180031340`
- `0x180031690`
- `0x1800318a0`
- `0x180031b70`
- `0x180031ec0`
- `0x1800320d0`
- `0x1800323a0`
- `0x180032620`
- `0x1800327d0`
- `0x18003c780`
- `0x18003ca30`
- `0x18003cc00`
- `0x18003ce10`
- `0x18003d0a0`
- `0x18003d260`
- `0x18003d530`
- `0x18003d880`
- `0x18003da90`
- `0x18003dd90`
- `0x18003e010`
- `0x18003e1c0`
- `0x18003ea50`
- `0x18003ef70`
- `0x180043e30`
- `0x18004a500`
- `0x18004a760`

## callees

- `0x180002bb0`
- `0x180008520`
- `0x180008600`
- `0x180008690`
- `0x180008940`
- `0x180008ac0`
- `0x18004c070`
- `0x18004d390`
- `0x180051385`
- `0x1800513af`
- `0x1800513b5`
- `0x18005170f`
- `0x180051715`
- `0x180051727`
- `0x18005e260`

## string_xrefs

- `0x180008b2b`: `combase.dll`
- `0x180008d9f`: `DllGetActivationFactory`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // esi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  __int64 *v13; // rdx
  __int64 v14; // r8
  LPCWSTR *v15; // rbx
  char *v16; // rdi
  __int64 last_trivial_2; // rax
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rdi
  LPCWSTR *v20; // rax
  unsigned __int64 v21; // rcx
  LPCWSTR *v22; // r8
  _WORD *v23; // rdi
  unsigned __int64 v24; // rcx
  LPCWSTR *v25; // rax
  const WCHAR *v26; // rcx
  HMODULE v27; // rbx
  unsigned __int64 v28; // r8
  unsigned __int64 v29; // rcx
  LPCWSTR *v30; // rax
  LPCWSTR *v31; // rdx
  _WORD *v32; // rdi
  __int64 i; // rcx
  FARPROC v34; // rax
  unsigned int (__fastcall ***v37)(_QWORD, __int64, __int64); // [rsp+38h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int64 v39; // [rsp+50h] [rbp-28h]
  unsigned __int64 v40; // [rsp+58h] [rbp-20h]
  IErrorInfo *pperrinfo; // [rsp+60h] [rbp-18h] BYREF

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
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v37);
    ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
  }
  if ( !ActivationFactory_0 )
  {
    *a1 = 0;
    return a1;
  }
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  *(_OWORD *)lpLibFileName = 0;
  v39 = 0;
  v40 = 0;
  v12 = *a2;
  if ( *a2 )
  {
    v13 = *(__int64 **)(v12 + 16);
    v14 = *(unsigned int *)(v12 + 4);
  }
  else
  {
    v13 = &qword_18006D0D8;
    v14 = 0;
  }
  std::wstring::_Construct<1,wchar_t const *>(lpLibFileName, v13, v14);
  while ( 1 )
  {
    do
    {
      v15 = lpLibFileName;
      if ( v40 > 7 )
        v15 = (LPCWSTR *)lpLibFileName[0];
      if ( !v39
        || (v16 = (char *)v15 + 2 * v39,
            last_trivial_2 = _std_find_last_trivial_2(v15, v16, 46),
            (char *)last_trivial_2 == v16)
        || (v18 = (last_trivial_2 - (__int64)v15) >> 1, v18 == -1) )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        goto LABEL_59;
      }
      v19 = v39;
      if ( v18 > v39 )
      {
        v21 = v18 - v39;
        if ( v18 - v39 > v40 - v39 )
        {
          _mm_lfence();
          ____Reallocate_grow_by_V_lambda_1___1__append___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAAEAV34__K_W_Z__K_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0_W_Z__K_W_Z(lpLibFileName);
        }
        else
        {
          v39 = (last_trivial_2 - (__int64)v15) >> 1;
          v22 = lpLibFileName;
          if ( v40 > 7 )
            v22 = (LPCWSTR *)lpLibFileName[0];
          v23 = (_WORD *)v22 + v19;
          if ( v21 )
          {
            while ( v21 )
            {
              *v23++ = 0;
              --v21;
            }
          }
          *((_WORD *)v22 + v18) = 0;
        }
      }
      else
      {
        v39 = (last_trivial_2 - (__int64)v15) >> 1;
        v20 = lpLibFileName;
        if ( v40 > 7 )
          v20 = (LPCWSTR *)lpLibFileName[0];
        *((_WORD *)v20 + v18) = 0;
      }
      v24 = v39;
      if ( v40 - v39 < 4 )
      {
        _mm_lfence();
        ____Reallocate_grow_by_V_lambda_1___1__append___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAAEAV34_QEB_W_K_Z_PEB_W_K___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEB_W0_Z_PEB_W_K_Z(
          lpLibFileName,
          4);
      }
      else
      {
        v39 += 4LL;
        v25 = lpLibFileName;
        if ( v40 > 7 )
          v25 = (LPCWSTR *)lpLibFileName[0];
        *(LPCWSTR *)((char *)v25 + 2 * v24) = (LPCWSTR)0x6C006C0064002ELL;
        *((_WORD *)v25 + v24 + 4) = 0;
      }
      v26 = (const WCHAR *)lpLibFileName;
      if ( v40 > 7 )
        v26 = lpLibFileName[0];
      v27 = LoadLibraryExW_0(v26, 0, 0x1000u);
      v28 = v39;
      v29 = v39 - 4;
      if ( v39 < 4 )
      {
        if ( v40 - v39 < 0xFFFFFFFFFFFFFFFCuLL )
        {
          ____Reallocate_grow_by_V_lambda_1___1__append___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAAEAV34__K_W_Z__K_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0_W_Z__K_W_Z(lpLibFileName);
        }
        else
        {
          v39 -= 4LL;
          v31 = lpLibFileName;
          if ( v40 > 7 )
            v31 = (LPCWSTR *)lpLibFileName[0];
          v32 = (_WORD *)v31 + v28;
          for ( i = 0x7FFFFFFFFFFFFFFCLL; i; --i )
            *v32++ = 0;
          *((_WORD *)v31 + v28 - 4) = 0;
        }
      }
      else
      {
        v39 -= 4LL;
        v30 = lpLibFileName;
        if ( v40 > 7 )
          v30 = (LPCWSTR *)lpLibFileName[0];
        *((_WORD *)v30 + v29) = 0;
      }
    }
    while ( !v27 );
    v34 = WINRT_IMPL_GetProcAddress(v27, "DllGetActivationFactory");
    if ( v34 )
      break;
LABEL_55:
    WINRT_IMPL_FreeLibrary(v27);
  }
  v37 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v34)(*a2, &v37)
    || (**v37)(v37, a3, a4) )
  {
    if ( v37 )
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v37);
    goto LABEL_55;
  }
  *a1 = 0;
  if ( v37 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v37);
LABEL_59:
  std::wstring::_Tidy_deallocate(lpLibFileName);
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x180008ac0  push    rbp
0x180008ac2  push    rbx
0x180008ac3  push    rsi
0x180008ac4  push    rdi
0x180008ac5  push    r12
0x180008ac7  push    r13
0x180008ac9  push    r14
0x180008acb  push    r15
0x180008acd  mov     rbp, rsp
0x180008ad0  sub     rsp, 78h
0x180008ad4  mov     rax, cs:__security_cookie
0x180008adb  xor     rax, rsp
0x180008ade  mov     [rbp+var_10], rax
0x180008ae2  mov     rdi, r9
0x180008ae5  mov     [rbp+var_48], r9
0x180008ae9  mov     r13, r8
0x180008aec  mov     r12, rdx
0x180008aef  mov     r15, rcx
0x180008af2  mov     rcx, [rdx]
0x180008af5  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180008afc  mov     r8, r9
0x180008aff  mov     rdx, r13
0x180008b02  test    rax, rax
0x180008b05  jz      short loc_180008B15
0x180008b07  call    cs:__guard_dispatch_icall_fptr
0x180008b0d  mov     [r15], eax
0x180008b10  jmp     loc_180008E3A
0x180008b15  call    RoGetActivationFactory_0
0x180008b1a  mov     esi, eax
0x180008b1c  cmp     eax, 800401F0h
0x180008b21  jnz     short loc_180008B72
0x180008b23  xor     edx, edx; hFile
0x180008b25  mov     r8d, 1000h; dwFlags
0x180008b2b  lea     rcx, LibFileName; "combase.dll"
0x180008b32  call    LoadLibraryExW_0
0x180008b37  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x180008b3e  mov     rcx, rax; hModule
0x180008b41  call    WINRT_IMPL_GetProcAddress
0x180008b46  test    rax, rax
0x180008b49  jnz     short loc_180008B57
0x180008b4b  mov     dword ptr [r15], 800401F0h
0x180008b52  jmp     loc_180008E3A
0x180008b57  lea     rcx, [rbp+var_40]
0x180008b5b  call    cs:__guard_dispatch_icall_fptr
0x180008b61  mov     r8, rdi
0x180008b64  mov     rdx, r13
0x180008b67  mov     rcx, [r12]
0x180008b6b  call    RoGetActivationFactory_0
0x180008b70  mov     esi, eax
0x180008b72  xor     r14d, r14d
0x180008b75  test    esi, esi
0x180008b77  jnz     short loc_180008B81
0x180008b79  mov     [r15], r14d
0x180008b7c  jmp     loc_180008E3A
0x180008b81  mov     [rbp+pperrinfo], r14
0x180008b85  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180008b89  xor     ecx, ecx; dwReserved
0x180008b8b  call    GetErrorInfo_0
0x180008b90  xorps   xmm0, xmm0
0x180008b93  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x180008b97  mov     [rbp+var_28], r14
0x180008b9b  mov     [rbp+var_20], r14
0x180008b9f  mov     rax, [r12]
0x180008ba3  test    rax, rax
0x180008ba6  jz      short loc_180008BB2
0x180008ba8  mov     rdx, [rax+10h]
0x180008bac  mov     r8d, [rax+4]
0x180008bb0  jmp     short loc_180008BBC
0x180008bb2  lea     rdx, qword_18006D0D8
0x180008bb9  mov     r8, r14
0x180008bbc  lea     rcx, [rbp+lpLibFileName]
0x180008bc0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180008bc5  nop     word ptr [rax+rax+00000000h]
0x180008bd0  lea     rbx, [rbp+lpLibFileName]
0x180008bd4  cmp     [rbp+var_20], 7
0x180008bd9  cmova   rbx, [rbp+lpLibFileName]
0x180008bde  mov     rcx, [rbp+var_28]
0x180008be2  test    rcx, rcx
0x180008be5  jz      loc_180008E14
0x180008beb  dec     rcx
0x180008bee  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008bf5  cmp     rcx, rax
0x180008bf8  cmovb   rax, rcx
0x180008bfc  inc     rax
0x180008bff  lea     rdi, [rbx+rax*2]
0x180008c03  mov     r8d, 2Eh ; '.'
0x180008c09  mov     rdx, rdi
0x180008c0c  mov     rcx, rbx
0x180008c0f  call    __std_find_last_trivial_2
0x180008c14  mov     rdx, rax
0x180008c17  cmp     rax, rdi
0x180008c1a  jz      loc_180008E14
0x180008c20  sub     rdx, rbx
0x180008c23  sar     rdx, 1
0x180008c26  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180008c2a  jz      loc_180008E14
0x180008c30  mov     rdi, [rbp+var_28]
0x180008c34  cmp     rdx, rdi
0x180008c37  ja      short loc_180008C52
0x180008c39  mov     [rbp+var_28], rdx
0x180008c3d  lea     rax, [rbp+lpLibFileName]
0x180008c41  cmp     [rbp+var_20], 7
0x180008c46  cmova   rax, [rbp+lpLibFileName]
0x180008c4b  mov     [rax+rdx*2], r14w
0x180008c50  jmp     short loc_180008CA1
0x180008c52  mov     rcx, rdx
0x180008c55  sub     rcx, rdi
0x180008c58  mov     r9, [rbp+var_20]
0x180008c5c  mov     rax, r9
0x180008c5f  sub     rax, rdi
0x180008c62  cmp     rcx, rax
0x180008c65  ja      short loc_180008C8F
0x180008c67  mov     [rbp+var_28], rdx
0x180008c6b  lea     r8, [rbp+lpLibFileName]
0x180008c6f  cmp     r9, 7
0x180008c73  cmova   r8, [rbp+lpLibFileName]
0x180008c78  lea     rdi, [r8+rdi*2]
0x180008c7c  test    rcx, rcx
0x180008c7f  jz      short loc_180008C88
0x180008c81  movzx   eax, r14w
0x180008c85  rep stosw
0x180008c88  mov     [r8+rdx*2], r14w
0x180008c8d  jmp     short loc_180008CA1
0x180008c8f  lfence
0x180008c92  mov     r9, rcx
0x180008c95  mov     rdx, rcx
0x180008c98  lea     rcx, [rbp+lpLibFileName]; Src
0x180008c9c  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@_K_W@Z@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0_W@Z@_K_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t>(unsigned __int64,`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t)
0x180008ca1  mov     rcx, [rbp+var_28]
0x180008ca5  mov     rdx, [rbp+var_20]
0x180008ca9  mov     rax, rdx
0x180008cac  sub     rax, rcx
0x180008caf  cmp     rax, 4
0x180008cb3  jb      short loc_180008CE0
0x180008cb5  lea     rax, [rcx+4]
0x180008cb9  mov     [rbp+var_28], rax
0x180008cbd  lea     rax, [rbp+lpLibFileName]
0x180008cc1  cmp     rdx, 7
0x180008cc5  cmova   rax, [rbp+lpLibFileName]
0x180008cca  mov     rdx, 6C006C0064002Eh
0x180008cd4  mov     [rax+rcx*2], rdx
0x180008cd8  mov     [rax+rcx*2+8], r14w
0x180008cde  jmp     short loc_180008D01
0x180008ce0  lfence
0x180008ce3  mov     [rsp+78h+var_58], 4; __int64
0x180008cec  lea     r9, aDll; ".dll"
0x180008cf3  mov     edx, 4
0x180008cf8  lea     rcx, [rbp+lpLibFileName]; Src
0x180008cfc  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@QEB_W_K@Z@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@QEB_W0@Z@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *,unsigned __int64>(unsigned __int64,`std::wstring::append(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *,unsigned __int64)
0x180008d01  lea     rcx, [rbp+lpLibFileName]
0x180008d05  cmp     [rbp+var_20], 7
0x180008d0a  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x180008d0f  xor     edx, edx; hFile
0x180008d11  mov     r8d, 1000h; dwFlags
0x180008d17  call    LoadLibraryExW_0
0x180008d1c  mov     rbx, rax
0x180008d1f  mov     r8, [rbp+var_28]
0x180008d23  lea     rcx, [r8-4]
0x180008d27  cmp     rcx, r8
0x180008d2a  ja      short loc_180008D45
0x180008d2c  mov     [rbp+var_28], rcx
0x180008d30  lea     rax, [rbp+lpLibFileName]
0x180008d34  cmp     [rbp+var_20], 7
0x180008d39  cmova   rax, [rbp+lpLibFileName]
0x180008d3e  mov     [rax+rcx*2], r14w
0x180008d43  jmp     short loc_180008D96
0x180008d45  mov     rdi, [rbp+var_20]
0x180008d49  mov     rax, rdi
0x180008d4c  sub     rax, r8
0x180008d4f  cmp     rax, 0FFFFFFFFFFFFFFFCh
0x180008d53  jb      short loc_180008D83
0x180008d55  mov     [rbp+var_28], rcx
0x180008d59  lea     rdx, [rbp+lpLibFileName]
0x180008d5d  cmp     rdi, 7
0x180008d61  cmova   rdx, [rbp+lpLibFileName]
0x180008d66  lea     rdi, [rdx+r8*2]
0x180008d6a  movzx   eax, r14w
0x180008d6e  mov     rcx, 7FFFFFFFFFFFFFFCh
0x180008d78  rep stosw
0x180008d7b  mov     [rdx+r8*2-8], r14w
0x180008d81  jmp     short loc_180008D96
0x180008d83  mov     rdx, 0FFFFFFFFFFFFFFFCh
0x180008d8a  mov     r9, rdx
0x180008d8d  lea     rcx, [rbp+lpLibFileName]; Src
0x180008d91  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@_K_W@Z@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0_W@Z@_K_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t>(unsigned __int64,`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t)
0x180008d96  test    rbx, rbx
0x180008d99  jz      loc_180008BD0
0x180008d9f  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x180008da6  mov     rcx, rbx; hModule
0x180008da9  call    WINRT_IMPL_GetProcAddress
0x180008dae  test    rax, rax
0x180008db1  jz      short loc_180008DF3
0x180008db3  mov     [rbp+var_40], r14
0x180008db7  lea     rdx, [rbp+var_40]
0x180008dbb  mov     rcx, [r12]
0x180008dbf  call    cs:__guard_dispatch_icall_fptr
0x180008dc5  test    eax, eax
0x180008dc7  jnz     short loc_180008DE4
0x180008dc9  mov     rcx, [rbp+var_40]
0x180008dcd  mov     rax, [rcx]
0x180008dd0  mov     r8, [rbp+var_48]
0x180008dd4  mov     rdx, r13
0x180008dd7  mov     rax, [rax]
0x180008dda  call    cs:__guard_dispatch_icall_fptr
0x180008de0  test    eax, eax
0x180008de2  jz      short loc_180008E00
0x180008de4  cmp     [rbp+var_40], r14
0x180008de8  jz      short loc_180008DF3
0x180008dea  lea     rcx, [rbp+var_40]
0x180008dee  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180008df3  mov     rcx, rbx; hLibModule
0x180008df6  call    WINRT_IMPL_FreeLibrary
0x180008dfb  jmp     loc_180008BD0
0x180008e00  mov     [r15], r14d
0x180008e03  cmp     [rbp+var_40], r14
0x180008e07  jz      short loc_180008E22
0x180008e09  lea     rcx, [rbp+var_40]
0x180008e0d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180008e12  jmp     short loc_180008E22
0x180008e14  mov     rdx, [rbp+pperrinfo]; perrinfo
0x180008e18  xor     ecx, ecx; dwReserved
0x180008e1a  call    SetErrorInfo_0
0x180008e1f  mov     [r15], esi
0x180008e22  lea     rcx, [rbp+lpLibFileName]
0x180008e26  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180008e2b  cmp     [rbp+pperrinfo], r14
0x180008e2f  jz      short loc_180008E3A
0x180008e31  lea     rcx, [rbp+pperrinfo]
0x180008e35  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180008e3a  mov     rax, r15
0x180008e3d  mov     rcx, [rbp+var_10]
0x180008e41  xor     rcx, rsp; StackCookie
0x180008e44  call    __security_check_cookie
0x180008e49  add     rsp, 78h
0x180008e4d  pop     r15
0x180008e4f  pop     r14
0x180008e51  pop     r13
0x180008e53  pop     r12
0x180008e55  pop     rdi
0x180008e56  pop     rsi
0x180008e57  pop     rbx
0x180008e58  pop     rbp
0x180008e59  retn
```
