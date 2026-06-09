# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x180007a00`
- end: `0x180007d7a`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `890`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, _QWORD *)`
- caller_count: `4`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007d80`
- `0x180033300`
- `0x18003f480`
- `0x18004a990`

## callees

- `0x180002bb0`
- `0x180007a00`
- `0x180008520`
- `0x180008600`
- `0x180008690`
- `0x180008940`
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

- `0x180007a67`: `combase.dll`
- `0x180007cd0`: `DllGetActivationFactory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<1>(_DWORD *a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // esi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  __int64 *v13; // rdx
  unsigned __int64 v14; // r8
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
  __int64 v35; // rax
  __int64 v37; // [rsp+30h] [rbp-48h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int64 v39; // [rsp+48h] [rbp-30h]
  unsigned __int64 v40; // [rsp+50h] [rbp-28h]
  IErrorInfo *pperrinfo; // [rsp+58h] [rbp-20h] BYREF

  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD *))winrt_activation_handler)(v8, a3, a4);
  }
  else
  {
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
      ((void (__fastcall *)(__int64 *))ProcAddress)(&v37);
      ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
    }
    if ( ActivationFactory_0 )
    {
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
        v15 = lpLibFileName;
        if ( v40 > 7 )
          v15 = (LPCWSTR *)lpLibFileName[0];
        if ( !v39 )
          break;
        v16 = (char *)v15 + 2 * v39;
        last_trivial_2 = _std_find_last_trivial_2(v15, v16, 46);
        if ( (char *)last_trivial_2 == v16 )
          break;
        v18 = (last_trivial_2 - (__int64)v15) >> 1;
        if ( v18 == -1 )
          break;
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
        if ( v27 )
        {
          v34 = WINRT_IMPL_GetProcAddress(v27, "DllGetActivationFactory");
          if ( v34 )
          {
            v37 = 0;
            if ( !((unsigned int (__fastcall *)(_QWORD, __int64 *))v34)(*a2, &v37) )
            {
              v35 = v37;
              v37 = 0;
              *a4 = v35;
              *a1 = 0;
              goto LABEL_58;
            }
            if ( v37 )
              winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v37);
          }
          WINRT_IMPL_FreeLibrary(v27);
        }
      }
      SetErrorInfo_0(0, pperrinfo);
      *a1 = ActivationFactory_0;
LABEL_58:
      std::wstring::_Tidy_deallocate(lpLibFileName);
      if ( pperrinfo )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&pperrinfo);
    }
    else
    {
      *a1 = 0;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180007a00  push    rbp
0x180007a02  push    rbx
0x180007a03  push    rsi
0x180007a04  push    rdi
0x180007a05  push    r12
0x180007a07  push    r13
0x180007a09  push    r14
0x180007a0b  push    r15
0x180007a0d  mov     rbp, rsp
0x180007a10  sub     rsp, 78h
0x180007a14  mov     rax, cs:__security_cookie
0x180007a1b  xor     rax, rsp
0x180007a1e  mov     [rbp+var_18], rax
0x180007a22  mov     r13, r9
0x180007a25  mov     rdi, r8
0x180007a28  mov     r12, rdx
0x180007a2b  mov     r15, rcx
0x180007a2e  mov     rcx, [rdx]
0x180007a31  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180007a38  mov     r8, r9
0x180007a3b  mov     rdx, rdi
0x180007a3e  test    rax, rax
0x180007a41  jz      short loc_180007A51
0x180007a43  call    cs:__guard_dispatch_icall_fptr
0x180007a49  mov     [r15], eax
0x180007a4c  jmp     loc_180007D5A
0x180007a51  call    RoGetActivationFactory_0
0x180007a56  mov     esi, eax
0x180007a58  cmp     eax, 800401F0h
0x180007a5d  jnz     short loc_180007AAE
0x180007a5f  xor     edx, edx; hFile
0x180007a61  mov     r8d, 1000h; dwFlags
0x180007a67  lea     rcx, LibFileName; "combase.dll"
0x180007a6e  call    LoadLibraryExW_0
0x180007a73  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x180007a7a  mov     rcx, rax; hModule
0x180007a7d  call    WINRT_IMPL_GetProcAddress
0x180007a82  test    rax, rax
0x180007a85  jnz     short loc_180007A93
0x180007a87  mov     dword ptr [r15], 800401F0h
0x180007a8e  jmp     loc_180007D5A
0x180007a93  lea     rcx, [rbp+var_48]
0x180007a97  call    cs:__guard_dispatch_icall_fptr
0x180007a9d  mov     r8, r13
0x180007aa0  mov     rdx, rdi
0x180007aa3  mov     rcx, [r12]
0x180007aa7  call    RoGetActivationFactory_0
0x180007aac  mov     esi, eax
0x180007aae  xor     r14d, r14d
0x180007ab1  test    esi, esi
0x180007ab3  jnz     short loc_180007ABD
0x180007ab5  mov     [r15], r14d
0x180007ab8  jmp     loc_180007D5A
0x180007abd  mov     [rbp+pperrinfo], r14
0x180007ac1  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180007ac5  xor     ecx, ecx; dwReserved
0x180007ac7  call    GetErrorInfo_0
0x180007acc  xorps   xmm0, xmm0
0x180007acf  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x180007ad3  mov     [rbp+var_30], r14
0x180007ad7  mov     [rbp+var_28], r14
0x180007adb  mov     rax, [r12]
0x180007adf  test    rax, rax
0x180007ae2  jz      short loc_180007AEE
0x180007ae4  mov     rdx, [rax+10h]
0x180007ae8  mov     r8d, [rax+4]
0x180007aec  jmp     short loc_180007AF8
0x180007aee  lea     rdx, qword_18006D0D8
0x180007af5  mov     r8, r14
0x180007af8  lea     rcx, [rbp+lpLibFileName]
0x180007afc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180007b01  lea     rbx, [rbp+lpLibFileName]
0x180007b05  cmp     [rbp+var_28], 7
0x180007b0a  cmova   rbx, [rbp+lpLibFileName]
0x180007b0f  mov     rcx, [rbp+var_30]
0x180007b13  test    rcx, rcx
0x180007b16  jz      loc_180007D34
0x180007b1c  dec     rcx
0x180007b1f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180007b26  cmp     rcx, rax
0x180007b29  cmovb   rax, rcx
0x180007b2d  inc     rax
0x180007b30  lea     rdi, [rbx+rax*2]
0x180007b34  mov     r8d, 2Eh ; '.'
0x180007b3a  mov     rdx, rdi
0x180007b3d  mov     rcx, rbx
0x180007b40  call    __std_find_last_trivial_2
0x180007b45  mov     rdx, rax
0x180007b48  cmp     rax, rdi
0x180007b4b  jz      loc_180007D34
0x180007b51  sub     rdx, rbx
0x180007b54  sar     rdx, 1
0x180007b57  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180007b5b  jz      loc_180007D34
0x180007b61  mov     rdi, [rbp+var_30]
0x180007b65  cmp     rdx, rdi
0x180007b68  ja      short loc_180007B83
0x180007b6a  mov     [rbp+var_30], rdx
0x180007b6e  lea     rax, [rbp+lpLibFileName]
0x180007b72  cmp     [rbp+var_28], 7
0x180007b77  cmova   rax, [rbp+lpLibFileName]
0x180007b7c  mov     [rax+rdx*2], r14w
0x180007b81  jmp     short loc_180007BD2
0x180007b83  mov     rcx, rdx
0x180007b86  sub     rcx, rdi
0x180007b89  mov     r9, [rbp+var_28]
0x180007b8d  mov     rax, r9
0x180007b90  sub     rax, rdi
0x180007b93  cmp     rcx, rax
0x180007b96  ja      short loc_180007BC0
0x180007b98  mov     [rbp+var_30], rdx
0x180007b9c  lea     r8, [rbp+lpLibFileName]
0x180007ba0  cmp     r9, 7
0x180007ba4  cmova   r8, [rbp+lpLibFileName]
0x180007ba9  lea     rdi, [r8+rdi*2]
0x180007bad  test    rcx, rcx
0x180007bb0  jz      short loc_180007BB9
0x180007bb2  movzx   eax, r14w
0x180007bb6  rep stosw
0x180007bb9  mov     [r8+rdx*2], r14w
0x180007bbe  jmp     short loc_180007BD2
0x180007bc0  lfence
0x180007bc3  mov     r9, rcx
0x180007bc6  mov     rdx, rcx
0x180007bc9  lea     rcx, [rbp+lpLibFileName]; Src
0x180007bcd  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@_K_W@Z@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0_W@Z@_K_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t>(unsigned __int64,`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t)
0x180007bd2  mov     rcx, [rbp+var_30]
0x180007bd6  mov     rdx, [rbp+var_28]
0x180007bda  mov     rax, rdx
0x180007bdd  sub     rax, rcx
0x180007be0  cmp     rax, 4
0x180007be4  jb      short loc_180007C11
0x180007be6  lea     rax, [rcx+4]
0x180007bea  mov     [rbp+var_30], rax
0x180007bee  lea     rax, [rbp+lpLibFileName]
0x180007bf2  cmp     rdx, 7
0x180007bf6  cmova   rax, [rbp+lpLibFileName]
0x180007bfb  mov     rdx, 6C006C0064002Eh
0x180007c05  mov     [rax+rcx*2], rdx
0x180007c09  mov     [rax+rcx*2+8], r14w
0x180007c0f  jmp     short loc_180007C32
0x180007c11  lfence
0x180007c14  mov     [rsp+78h+var_58], 4; __int64
0x180007c1d  lea     r9, aDll; ".dll"
0x180007c24  mov     edx, 4
0x180007c29  lea     rcx, [rbp+lpLibFileName]; Src
0x180007c2d  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@QEB_W_K@Z@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@QEB_W0@Z@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *,unsigned __int64>(unsigned __int64,`std::wstring::append(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *,unsigned __int64)
0x180007c32  lea     rcx, [rbp+lpLibFileName]
0x180007c36  cmp     [rbp+var_28], 7
0x180007c3b  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x180007c40  xor     edx, edx; hFile
0x180007c42  mov     r8d, 1000h; dwFlags
0x180007c48  call    LoadLibraryExW_0
0x180007c4d  mov     rbx, rax
0x180007c50  mov     r8, [rbp+var_30]
0x180007c54  lea     rcx, [r8-4]
0x180007c58  cmp     rcx, r8
0x180007c5b  ja      short loc_180007C76
0x180007c5d  mov     [rbp+var_30], rcx
0x180007c61  lea     rax, [rbp+lpLibFileName]
0x180007c65  cmp     [rbp+var_28], 7
0x180007c6a  cmova   rax, [rbp+lpLibFileName]
0x180007c6f  mov     [rax+rcx*2], r14w
0x180007c74  jmp     short loc_180007CC7
0x180007c76  mov     rdi, [rbp+var_28]
0x180007c7a  mov     rax, rdi
0x180007c7d  sub     rax, r8
0x180007c80  cmp     rax, 0FFFFFFFFFFFFFFFCh
0x180007c84  jb      short loc_180007CB4
0x180007c86  mov     [rbp+var_30], rcx
0x180007c8a  lea     rdx, [rbp+lpLibFileName]
0x180007c8e  cmp     rdi, 7
0x180007c92  cmova   rdx, [rbp+lpLibFileName]
0x180007c97  lea     rdi, [rdx+r8*2]
0x180007c9b  movzx   eax, r14w
0x180007c9f  mov     rcx, 7FFFFFFFFFFFFFFCh
0x180007ca9  rep stosw
0x180007cac  mov     [rdx+r8*2-8], r14w
0x180007cb2  jmp     short loc_180007CC7
0x180007cb4  mov     rdx, 0FFFFFFFFFFFFFFFCh
0x180007cbb  mov     r9, rdx
0x180007cbe  lea     rcx, [rbp+lpLibFileName]; Src
0x180007cc2  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@_K_W@Z@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0_W@Z@_K_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t>(unsigned __int64,`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t)
0x180007cc7  test    rbx, rbx
0x180007cca  jz      loc_180007B01
0x180007cd0  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x180007cd7  mov     rcx, rbx; hModule
0x180007cda  call    WINRT_IMPL_GetProcAddress
0x180007cdf  test    rax, rax
0x180007ce2  jnz     short loc_180007CF1
0x180007ce4  mov     rcx, rbx; hLibModule
0x180007ce7  call    WINRT_IMPL_FreeLibrary
0x180007cec  jmp     loc_180007B01
0x180007cf1  mov     [rbp+var_48], r14
0x180007cf5  lea     rdx, [rbp+var_48]
0x180007cf9  mov     rcx, [r12]
0x180007cfd  call    cs:__guard_dispatch_icall_fptr
0x180007d03  test    eax, eax
0x180007d05  jz      short loc_180007D23
0x180007d07  cmp     [rbp+var_48], r14
0x180007d0b  jz      short loc_180007D16
0x180007d0d  lea     rcx, [rbp+var_48]
0x180007d11  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180007d16  mov     rcx, rbx; hLibModule
0x180007d19  call    WINRT_IMPL_FreeLibrary
0x180007d1e  jmp     loc_180007B01
0x180007d23  mov     rax, [rbp+var_48]
0x180007d27  mov     [rbp+var_48], r14
0x180007d2b  mov     [r13+0], rax
0x180007d2f  mov     [r15], r14d
0x180007d32  jmp     short loc_180007D42
0x180007d34  mov     rdx, [rbp+pperrinfo]; perrinfo
0x180007d38  xor     ecx, ecx; dwReserved
0x180007d3a  call    SetErrorInfo_0
0x180007d3f  mov     [r15], esi
0x180007d42  lea     rcx, [rbp+lpLibFileName]
0x180007d46  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180007d4b  cmp     [rbp+pperrinfo], r14
0x180007d4f  jz      short loc_180007D5A
0x180007d51  lea     rcx, [rbp+pperrinfo]
0x180007d55  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180007d5a  mov     rax, r15
0x180007d5d  mov     rcx, [rbp+var_18]
0x180007d61  xor     rcx, rsp; StackCookie
0x180007d64  call    __security_check_cookie
0x180007d69  add     rsp, 78h
0x180007d6d  pop     r15
0x180007d6f  pop     r14
0x180007d71  pop     r13
0x180007d73  pop     r12
0x180007d75  pop     rdi
0x180007d76  pop     rsi
0x180007d77  pop     rbx
0x180007d78  pop     rbp
0x180007d79  retn
```
