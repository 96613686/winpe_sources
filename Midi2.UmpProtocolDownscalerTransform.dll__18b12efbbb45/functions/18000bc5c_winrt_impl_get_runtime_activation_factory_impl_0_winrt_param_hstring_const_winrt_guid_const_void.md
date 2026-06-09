# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18000bc5c`
- end: `0x18000bfc4`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `872`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b8fc`
- `0x18000bafc`

## callees

- `0x180002a60`
- `0x180002e70`
- `0x180003b10`
- `0x180003b28`
- `0x180003b34`
- `0x180003b55`
- `0x180003b79`
- `0x180003ba9`
- `0x18000b238`
- `0x18000b5dc`
- `0x18000b770`
- `0x18000bc5c`
- `0x18000d0ac`
- `0x180011e0c`
- `0x180013010`

## string_xrefs

- `0x18000bcc4`: `combase.dll`
- `0x18000bf04`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 *v12; // rdx
  LPCWSTR *v13; // r14
  char *v14; // rdi
  __int64 last_trivial_2; // rax
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rdi
  LPCWSTR *v18; // rcx
  unsigned __int64 v19; // rcx
  LPCWSTR *v20; // r8
  _WORD *v21; // rdi
  unsigned __int64 v22; // rdi
  LPCWSTR *v23; // rcx
  const WCHAR *v24; // rcx
  HMODULE v25; // rdi
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // r8
  LPCWSTR *v28; // rcx
  FARPROC v29; // rax
  unsigned int (__fastcall ***v31)(_QWORD, __int64, __int64); // [rsp+30h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int64 v34; // [rsp+50h] [rbp-28h]
  unsigned __int64 v35; // [rsp+58h] [rbp-20h]

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
    v31 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v31);
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
  v34 = 0;
  v35 = 0;
  if ( *a2 )
    v12 = *(__int64 **)(*a2 + 16LL);
  else
    v12 = &qword_180015B20;
  std::wstring::_Construct<1,unsigned short const *>(lpLibFileName, v12);
  while ( 1 )
  {
    do
    {
      v13 = lpLibFileName;
      if ( v35 > 7 )
        v13 = (LPCWSTR *)lpLibFileName[0];
      if ( !v34
        || (v14 = (char *)v13 + 2 * v34,
            last_trivial_2 = _std_find_last_trivial_2(v13, v14, 46),
            (char *)last_trivial_2 == v14)
        || (v16 = (last_trivial_2 - (__int64)v13) >> 1, v16 == -1) )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        goto LABEL_57;
      }
      v17 = v34;
      if ( v16 > v34 )
      {
        v19 = v16 - v34;
        if ( v16 - v34 > v35 - v34 )
        {
          ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAAEAV34__KG_Z__KG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0G_Z__KG_Z(lpLibFileName);
        }
        else
        {
          v34 = (last_trivial_2 - (__int64)v13) >> 1;
          v20 = lpLibFileName;
          if ( v35 > 7 )
            v20 = (LPCWSTR *)lpLibFileName[0];
          v21 = (_WORD *)v20 + v17;
          if ( v19 )
          {
            while ( v19 )
            {
              *v21++ = 0;
              --v19;
            }
          }
          *((_WORD *)v20 + v16) = 0;
        }
      }
      else
      {
        v34 = (last_trivial_2 - (__int64)v13) >> 1;
        v18 = lpLibFileName;
        if ( v35 > 7 )
          v18 = (LPCWSTR *)lpLibFileName[0];
        *((_WORD *)v18 + v16) = 0;
      }
      v22 = v34;
      if ( v35 - v34 < 4 )
      {
        ____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
          lpLibFileName,
          4);
      }
      else
      {
        v34 += 4LL;
        v23 = lpLibFileName;
        if ( v35 > 7 )
          v23 = (LPCWSTR *)lpLibFileName[0];
        *(LPCWSTR *)((char *)v23 + 2 * v22) = (LPCWSTR)0x6C006C0064002ELL;
        *((_WORD *)v23 + v22 + 4) = 0;
      }
      v24 = (const WCHAR *)lpLibFileName;
      if ( v35 > 7 )
        v24 = lpLibFileName[0];
      v25 = LoadLibraryExW_0(v24, 0, 0x1000u);
      v26 = v34;
      v27 = v34 - 4;
      v28 = lpLibFileName;
      if ( v34 >= 4 )
      {
        v34 -= 4LL;
        if ( v35 > 7 )
          v28 = (LPCWSTR *)lpLibFileName[0];
LABEL_45:
        *((_WORD *)v28 + v27) = 0;
        continue;
      }
      if ( v35 - v34 >= 0xFFFFFFFFFFFFFFFCuLL )
      {
        v34 -= 4LL;
        if ( v35 > 7 )
          v28 = (LPCWSTR *)lpLibFileName[0];
        *(LPCWSTR *)((char *)v28 + 2 * v26) = 0;
        goto LABEL_45;
      }
      ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAAEAV34__KG_Z__KG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0G_Z__KG_Z(lpLibFileName);
    }
    while ( !v25 );
    v29 = WINRT_IMPL_GetProcAddress(v25, "DllGetActivationFactory");
    if ( !v29 )
      goto LABEL_53;
    v31 = 0;
    if ( !((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v29)(
            *a2,
            &v31)
      && !(**v31)(v31, a3, a4) )
    {
      break;
    }
    if ( v31 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v31);
LABEL_53:
    WINRT_IMPL_FreeLibrary(v25);
  }
  *a1 = 0;
  if ( v31 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v31);
LABEL_57:
  std::wstring::~wstring(lpLibFileName);
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x18000bc5c  push    rbp
0x18000bc5e  push    rbx
0x18000bc5f  push    rsi
0x18000bc60  push    rdi
0x18000bc61  push    r12
0x18000bc63  push    r13
0x18000bc65  push    r14
0x18000bc67  push    r15
0x18000bc69  mov     rbp, rsp
0x18000bc6c  sub     rsp, 78h
0x18000bc70  mov     rax, cs:__security_cookie
0x18000bc77  xor     rax, rsp
0x18000bc7a  mov     [rbp+var_18], rax
0x18000bc7e  mov     r13, r9
0x18000bc81  mov     r12, r8
0x18000bc84  mov     r15, rdx
0x18000bc87  mov     rsi, rcx
0x18000bc8a  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18000bc91  xor     r14d, r14d
0x18000bc94  mov     r8, r9
0x18000bc97  mov     rdx, r12
0x18000bc9a  mov     rcx, [r15]
0x18000bc9d  test    rax, rax
0x18000bca0  jz      short loc_18000BCAE
0x18000bca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bca7  mov     [rsi], eax
0x18000bca9  jmp     loc_18000BFA4
0x18000bcae  call    RoGetActivationFactory_0
0x18000bcb3  mov     ebx, eax
0x18000bcb5  cmp     eax, 800401F0h
0x18000bcba  jnz     short loc_18000BD0C
0x18000bcbc  xor     edx, edx; hFile
0x18000bcbe  mov     r8d, 1000h; dwFlags
0x18000bcc4  lea     rcx, aCombaseDll; "combase.dll"
0x18000bccb  call    LoadLibraryExW_0
0x18000bcd0  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18000bcd7  mov     rcx, rax; hModule
0x18000bcda  call    WINRT_IMPL_GetProcAddress
0x18000bcdf  test    rax, rax
0x18000bce2  jnz     short loc_18000BCEF
0x18000bce4  mov     dword ptr [rsi], 800401F0h
0x18000bcea  jmp     loc_18000BFA4
0x18000bcef  mov     [rbp+var_48], r14
0x18000bcf3  lea     rcx, [rbp+var_48]
0x18000bcf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcfc  mov     r8, r13
0x18000bcff  mov     rdx, r12
0x18000bd02  mov     rcx, [r15]
0x18000bd05  call    RoGetActivationFactory_0
0x18000bd0a  mov     ebx, eax
0x18000bd0c  test    ebx, ebx
0x18000bd0e  jnz     short loc_18000BD18
0x18000bd10  mov     [rsi], r14d
0x18000bd13  jmp     loc_18000BFA4
0x18000bd18  mov     [rbp+pperrinfo], r14
0x18000bd1c  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000bd20  xor     ecx, ecx; dwReserved
0x18000bd22  call    GetErrorInfo_0
0x18000bd27  xorps   xmm0, xmm0
0x18000bd2a  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x18000bd2e  mov     [rbp+var_28], r14
0x18000bd32  mov     [rbp+var_20], r14
0x18000bd36  mov     rax, [r15]
0x18000bd39  test    rax, rax
0x18000bd3c  jz      short loc_18000BD48
0x18000bd3e  mov     rdx, [rax+10h]
0x18000bd42  mov     r8d, [rax+4]
0x18000bd46  jmp     short loc_18000BD52
0x18000bd48  lea     rdx, qword_180015B20
0x18000bd4f  mov     r8, r14
0x18000bd52  lea     rcx, [rbp+lpLibFileName]
0x18000bd56  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000bd5b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000bd5f  mov     rax, [rbp+var_28]
0x18000bd63  lea     r14, [rbp+lpLibFileName]
0x18000bd67  cmp     [rbp+var_20], 7
0x18000bd6c  cmova   r14, [rbp+lpLibFileName]
0x18000bd71  test    rax, rax
0x18000bd74  jz      loc_18000BF7E
0x18000bd7a  dec     rax
0x18000bd7d  cmp     rax, rcx
0x18000bd80  cmovnb  rax, rcx
0x18000bd84  inc     rax
0x18000bd87  lea     rdi, [r14+rax*2]
0x18000bd8b  mov     r8d, 2Eh ; '.'
0x18000bd91  mov     rdx, rdi
0x18000bd94  mov     rcx, r14
0x18000bd97  call    __std_find_last_trivial_2
0x18000bd9c  mov     rdx, rax
0x18000bd9f  cmp     rax, rdi
0x18000bda2  jz      loc_18000BF7E
0x18000bda8  sub     rdx, r14
0x18000bdab  sar     rdx, 1
0x18000bdae  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18000bdb2  jz      loc_18000BF7E
0x18000bdb8  mov     rdi, [rbp+var_28]
0x18000bdbc  cmp     rdx, rdi
0x18000bdbf  ja      short loc_18000BDDB
0x18000bdc1  mov     [rbp+var_28], rdx
0x18000bdc5  lea     rcx, [rbp+lpLibFileName]
0x18000bdc9  cmp     [rbp+var_20], 7
0x18000bdce  cmova   rcx, [rbp+lpLibFileName]
0x18000bdd3  xor     eax, eax
0x18000bdd5  mov     [rcx+rdx*2], ax
0x18000bdd9  jmp     short loc_18000BE28
0x18000bddb  mov     rcx, rdx
0x18000bdde  sub     rcx, rdi
0x18000bde1  mov     rax, [rbp+var_20]
0x18000bde5  sub     rax, rdi
0x18000bde8  cmp     rcx, rax
0x18000bdeb  ja      short loc_18000BE19
0x18000bded  mov     [rbp+var_28], rdx
0x18000bdf1  lea     r8, [rbp+lpLibFileName]
0x18000bdf5  cmp     [rbp+var_20], 7
0x18000bdfa  cmova   r8, [rbp+lpLibFileName]
0x18000bdff  lea     rdi, [r8+rdi*2]
0x18000be03  test    rcx, rcx
0x18000be06  jz      short loc_18000BE10
0x18000be08  xor     eax, eax
0x18000be0a  movzx   eax, ax
0x18000be0d  rep stosw
0x18000be10  xor     eax, eax
0x18000be12  mov     [r8+rdx*2], ax
0x18000be17  jmp     short loc_18000BE28
0x18000be19  mov     r9, rcx
0x18000be1c  mov     rdx, rcx
0x18000be1f  lea     rcx, [rbp+lpLibFileName]; Src
0x18000be23  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV34@_KG@Z@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0G@Z@_KG@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_,unsigned __int64,ushort>(unsigned __int64,`std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_,unsigned __int64,ushort)
0x18000be28  mov     rdi, [rbp+var_28]
0x18000be2c  mov     rax, [rbp+var_20]
0x18000be30  sub     rax, rdi
0x18000be33  mov     ecx, 4
0x18000be38  cmp     rax, rcx
0x18000be3b  jb      short loc_18000BE69
0x18000be3d  lea     rdx, [rdi+4]
0x18000be41  mov     [rbp+var_28], rdx
0x18000be45  lea     rcx, [rbp+lpLibFileName]
0x18000be49  cmp     [rbp+var_20], 7
0x18000be4e  cmova   rcx, [rbp+lpLibFileName]
0x18000be53  mov     rax, 6C006C0064002Eh
0x18000be5d  mov     [rcx+rdi*2], rax
0x18000be61  xor     eax, eax
0x18000be63  mov     [rcx+rdx*2], ax
0x18000be67  jmp     short loc_18000BE7A
0x18000be69  mov     [rsp+78h+var_58], rcx; __int64
0x18000be6e  mov     rdx, rcx
0x18000be71  lea     rcx, [rbp+lpLibFileName]; Src
0x18000be75  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@G@01@AEAAAEAV01@QEBG0@Z@PEBG_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64)
0x18000be7a  lea     rcx, [rbp+lpLibFileName]
0x18000be7e  cmp     [rbp+var_20], 7
0x18000be83  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x18000be88  xor     edx, edx; hFile
0x18000be8a  mov     r8d, 1000h; dwFlags
0x18000be90  call    LoadLibraryExW_0
0x18000be95  mov     rdi, rax
0x18000be98  mov     rdx, [rbp+var_28]
0x18000be9c  lea     r8, [rdx-4]
0x18000bea0  lea     rcx, [rbp+lpLibFileName]; Src
0x18000bea4  cmp     r8, rdx
0x18000bea7  ja      short loc_18000BEBB
0x18000bea9  mov     [rbp+var_28], r8
0x18000bead  cmp     [rbp+var_20], 7
0x18000beb2  cmova   rcx, [rbp+lpLibFileName]
0x18000beb7  xor     eax, eax
0x18000beb9  jmp     short loc_18000BEE2
0x18000bebb  mov     rax, [rbp+var_20]
0x18000bebf  sub     rax, rdx
0x18000bec2  mov     r10, 0FFFFFFFFFFFFFFFCh
0x18000bec9  cmp     rax, r10
0x18000becc  jb      short loc_18000BEE9
0x18000bece  mov     [rbp+var_28], r8
0x18000bed2  cmp     [rbp+var_20], 7
0x18000bed7  cmova   rcx, [rbp+lpLibFileName]
0x18000bedc  xor     eax, eax
0x18000bede  mov     [rcx+rdx*2], rax
0x18000bee2  mov     [rcx+r8*2], ax
0x18000bee7  jmp     short loc_18000BEF4
0x18000bee9  mov     r9, r10
0x18000beec  mov     rdx, r10
0x18000beef  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV34@_KG@Z@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0G@Z@_KG@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_,unsigned __int64,ushort>(unsigned __int64,`std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_,unsigned __int64,ushort)
0x18000bef4  test    rdi, rdi
0x18000bef7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000befe  jz      loc_18000BD5F
0x18000bf04  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x18000bf0b  mov     rcx, rdi; hModule
0x18000bf0e  call    WINRT_IMPL_GetProcAddress
0x18000bf13  test    rax, rax
0x18000bf16  jz      short loc_18000BF59
0x18000bf18  mov     [rbp+var_48], 0
0x18000bf20  lea     rdx, [rbp+var_48]
0x18000bf24  mov     rcx, [r15]
0x18000bf27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf2c  test    eax, eax
0x18000bf2e  jnz     short loc_18000BF49
0x18000bf30  mov     rcx, [rbp+var_48]
0x18000bf34  mov     rax, [rcx]
0x18000bf37  mov     r8, r13
0x18000bf3a  mov     rdx, r12
0x18000bf3d  mov     rax, [rax]
0x18000bf40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf45  test    eax, eax
0x18000bf47  jz      short loc_18000BF66
0x18000bf49  cmp     [rbp+var_48], 0
0x18000bf4e  jz      short loc_18000BF59
0x18000bf50  lea     rcx, [rbp+var_48]
0x18000bf54  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000bf59  mov     rcx, rdi; hLibModule
0x18000bf5c  call    WINRT_IMPL_FreeLibrary
0x18000bf61  jmp     loc_18000BD5B
0x18000bf66  mov     dword ptr [rsi], 0
0x18000bf6c  cmp     [rbp+var_48], 0
0x18000bf71  jz      short loc_18000BF8B
0x18000bf73  lea     rcx, [rbp+var_48]
0x18000bf77  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000bf7c  jmp     short loc_18000BF8B
0x18000bf7e  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18000bf82  xor     ecx, ecx; dwReserved
0x18000bf84  call    SetErrorInfo_0
0x18000bf89  mov     [rsi], ebx
0x18000bf8b  lea     rcx, [rbp+lpLibFileName]
0x18000bf8f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000bf94  cmp     [rbp+pperrinfo], 0
0x18000bf99  jz      short loc_18000BFA4
0x18000bf9b  lea     rcx, [rbp+pperrinfo]
0x18000bf9f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000bfa4  mov     rax, rsi
0x18000bfa7  mov     rcx, [rbp+var_18]
0x18000bfab  xor     rcx, rsp; StackCookie
0x18000bfae  call    __security_check_cookie
0x18000bfb3  add     rsp, 78h
0x18000bfb7  pop     r15
0x18000bfb9  pop     r14
0x18000bfbb  pop     r13
0x18000bfbd  pop     r12
0x18000bfbf  pop     rdi
0x18000bfc0  pop     rsi
0x18000bfc1  pop     rbx
0x18000bfc2  pop     rbp
0x18000bfc3  retn
```
