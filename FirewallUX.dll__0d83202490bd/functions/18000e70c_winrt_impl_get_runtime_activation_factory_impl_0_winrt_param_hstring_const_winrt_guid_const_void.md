# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18000e70c`
- end: `0x18000e9cb`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `703`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, __int64)`
- caller_count: `15`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ca50`
- `0x18000cba4`
- `0x18000ccf8`
- `0x18000cfe4`
- `0x18000d1b0`
- `0x18000d4d8`
- `0x18000d800`
- `0x18000d9cc`
- `0x18000e264`
- `0x18000e2c4`
- `0x18001bb50`
- `0x18001bca4`
- `0x18001bdf8`
- `0x18001bf4c`
- `0x18001c6f8`

## callees

- `0x1800021c0`
- `0x180002d85`
- `0x180003a40`
- `0x180003dcd`
- `0x180003dd9`
- `0x180003e2d`
- `0x180003e39`
- `0x180003e45`
- `0x18000b5d0`
- `0x18000c3e4`
- `0x18000c730`
- `0x18000e70c`
- `0x18000f098`
- `0x180014c14`
- `0x18002d010`

## string_xrefs

- `0x18000e774`: `combase.dll`
- `0x18000e907`: `DllGetActivationFactory`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // edi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  const wchar_t *v13; // rdx
  __int64 v14; // r8
  LPCWSTR *v15; // r14
  LPCWSTR *v16; // rbx
  __int64 last_trivial_2; // rax
  unsigned __int64 v18; // r8
  LPCWSTR *v19; // rcx
  const WCHAR *v20; // rcx
  HMODULE v21; // rbx
  FARPROC v22; // rax
  bool v23; // zf
  unsigned int (__fastcall ***v25)(_QWORD, __int64, __int64); // [rsp+30h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int64 v28; // [rsp+50h] [rbp-28h]
  unsigned __int64 v29; // [rsp+58h] [rbp-20h]

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
    v25 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v25);
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
  v28 = 0;
  v29 = 0;
  v12 = *a2;
  if ( *a2 )
  {
    v13 = *(const wchar_t **)(v12 + 16);
    v14 = *(unsigned int *)(v12 + 4);
  }
  else
  {
    v13 = &szFile;
    v14 = 0;
  }
  std::wstring::_Construct<1,unsigned short const *>(lpLibFileName, v13, v14);
  while ( 1 )
  {
    do
    {
      v15 = lpLibFileName;
      if ( v29 > 7 )
        v15 = (LPCWSTR *)lpLibFileName[0];
      if ( !v28
        || (v16 = &v15[v28 / 4],
            last_trivial_2 = _std_find_last_trivial_2(v15, v16, 46),
            (LPCWSTR *)last_trivial_2 == v16)
        || (last_trivial_2 - (__int64)v15) >> 1 == -1 )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        std::wstring::~wstring(lpLibFileName);
        v23 = pperrinfo == 0;
        goto LABEL_36;
      }
      std::wstring::resize(lpLibFileName);
      v18 = v28;
      if ( v29 - v28 < 4 )
      {
        ____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
          lpLibFileName,
          4);
      }
      else
      {
        v28 += 4LL;
        v19 = lpLibFileName;
        if ( v29 > 7 )
          v19 = (LPCWSTR *)lpLibFileName[0];
        *(LPCWSTR *)((char *)v19 + 2 * v18) = (LPCWSTR)0x6C006C0064002ELL;
        *((_WORD *)v19 + v18 + 4) = 0;
      }
      v20 = (const WCHAR *)lpLibFileName;
      if ( v29 > 7 )
        v20 = lpLibFileName[0];
      v21 = LoadLibraryExW_0(v20, 0, 0x1000u);
      std::wstring::resize(lpLibFileName);
    }
    while ( !v21 );
    v22 = WINRT_IMPL_GetProcAddress(v21, "DllGetActivationFactory");
    if ( v22 )
      break;
LABEL_31:
    WINRT_IMPL_FreeLibrary(v21);
  }
  v25 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v22)(*a2, &v25)
    || (**v25)(v25, a3, a4) )
  {
    if ( v25 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v25);
    goto LABEL_31;
  }
  *a1 = 0;
  if ( v25 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v25);
  std::wstring::~wstring(lpLibFileName);
  v23 = pperrinfo == 0;
LABEL_36:
  if ( !v23 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x18000e70c  push    rbp
0x18000e70e  push    rbx
0x18000e70f  push    rsi
0x18000e710  push    rdi
0x18000e711  push    r12
0x18000e713  push    r13
0x18000e715  push    r14
0x18000e717  push    r15
0x18000e719  mov     rbp, rsp
0x18000e71c  sub     rsp, 78h
0x18000e720  mov     rax, cs:__security_cookie
0x18000e727  xor     rax, rsp
0x18000e72a  mov     [rbp+var_18], rax
0x18000e72e  mov     r13, r9
0x18000e731  mov     r12, r8
0x18000e734  mov     r15, rdx
0x18000e737  mov     rsi, rcx
0x18000e73a  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18000e741  xor     r14d, r14d
0x18000e744  mov     r8, r9
0x18000e747  mov     rdx, r12
0x18000e74a  mov     rcx, [r15]
0x18000e74d  test    rax, rax
0x18000e750  jz      short loc_18000E75E
0x18000e752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e757  mov     [rsi], eax
0x18000e759  jmp     loc_18000E9AB
0x18000e75e  call    RoGetActivationFactory_0
0x18000e763  mov     edi, eax
0x18000e765  cmp     eax, 800401F0h
0x18000e76a  jnz     short loc_18000E7BC
0x18000e76c  xor     edx, edx; hFile
0x18000e76e  mov     r8d, 1000h; dwFlags
0x18000e774  lea     rcx, LibFileName; "combase.dll"
0x18000e77b  call    LoadLibraryExW_0
0x18000e780  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18000e787  mov     rcx, rax; hModule
0x18000e78a  call    WINRT_IMPL_GetProcAddress
0x18000e78f  test    rax, rax
0x18000e792  jnz     short loc_18000E79F
0x18000e794  mov     dword ptr [rsi], 800401F0h
0x18000e79a  jmp     loc_18000E9AB
0x18000e79f  mov     [rbp+var_48], r14
0x18000e7a3  lea     rcx, [rbp+var_48]
0x18000e7a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7ac  mov     r8, r13
0x18000e7af  mov     rdx, r12
0x18000e7b2  mov     rcx, [r15]
0x18000e7b5  call    RoGetActivationFactory_0
0x18000e7ba  mov     edi, eax
0x18000e7bc  test    edi, edi
0x18000e7be  jnz     short loc_18000E7C8
0x18000e7c0  mov     [rsi], r14d
0x18000e7c3  jmp     loc_18000E9AB
0x18000e7c8  mov     [rbp+pperrinfo], r14
0x18000e7cc  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000e7d0  xor     ecx, ecx; dwReserved
0x18000e7d2  call    GetErrorInfo_0
0x18000e7d7  xorps   xmm0, xmm0
0x18000e7da  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x18000e7de  mov     [rbp+var_28], r14
0x18000e7e2  mov     [rbp+var_20], r14
0x18000e7e6  mov     rax, [r15]
0x18000e7e9  test    rax, rax
0x18000e7ec  jz      short loc_18000E7F8
0x18000e7ee  mov     rdx, [rax+10h]
0x18000e7f2  mov     r8d, [rax+4]
0x18000e7f6  jmp     short loc_18000E802
0x18000e7f8  lea     rdx, szFile
0x18000e7ff  mov     r8, r14
0x18000e802  lea     rcx, [rbp+lpLibFileName]
0x18000e806  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000e80b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000e80f  mov     rax, [rbp+var_28]
0x18000e813  lea     r14, [rbp+lpLibFileName]
0x18000e817  cmp     [rbp+var_20], 7
0x18000e81c  cmova   r14, [rbp+lpLibFileName]
0x18000e821  test    rax, rax
0x18000e824  jz      loc_18000E985
0x18000e82a  dec     rax
0x18000e82d  cmp     rax, rcx
0x18000e830  cmovnb  rax, rcx
0x18000e834  inc     rax
0x18000e837  lea     rbx, [r14+rax*2]
0x18000e83b  mov     r8d, 2Eh ; '.'
0x18000e841  mov     rdx, rbx
0x18000e844  mov     rcx, r14
0x18000e847  call    __std_find_last_trivial_2
0x18000e84c  cmp     rax, rbx
0x18000e84f  jz      loc_18000E985
0x18000e855  sub     rax, r14
0x18000e858  sar     rax, 1
0x18000e85b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e85f  jz      loc_18000E985
0x18000e865  mov     rdx, rax
0x18000e868  lea     rcx, [rbp+lpLibFileName]; Src
0x18000e86c  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000e871  mov     r8, [rbp+var_28]
0x18000e875  mov     rax, [rbp+var_20]
0x18000e879  sub     rax, r8
0x18000e87c  mov     ecx, 4
0x18000e881  cmp     rax, rcx
0x18000e884  jb      short loc_18000E8B4
0x18000e886  lea     rdx, [r8+4]
0x18000e88a  mov     [rbp+var_28], rdx
0x18000e88e  lea     rcx, [rbp+lpLibFileName]
0x18000e892  cmp     [rbp+var_20], 7
0x18000e897  cmova   rcx, [rbp+lpLibFileName]
0x18000e89c  mov     rax, 6C006C0064002Eh
0x18000e8a6  mov     [rcx+r8*2], rax
0x18000e8aa  xor     r14d, r14d
0x18000e8ad  mov     [rcx+rdx*2], r14w
0x18000e8b2  jmp     short loc_18000E8C8
0x18000e8b4  mov     [rsp+78h+var_58], rcx; __int64
0x18000e8b9  mov     rdx, rcx
0x18000e8bc  lea     rcx, [rbp+lpLibFileName]; Src
0x18000e8c0  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@G@01@AEAAAEAV01@QEBG0@Z@PEBG_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64)
0x18000e8c5  xor     r14d, r14d
0x18000e8c8  lea     rcx, [rbp+lpLibFileName]
0x18000e8cc  cmp     [rbp+var_20], 7
0x18000e8d1  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x18000e8d6  xor     edx, edx; hFile
0x18000e8d8  mov     r8d, 1000h; dwFlags
0x18000e8de  call    LoadLibraryExW_0
0x18000e8e3  mov     rbx, rax
0x18000e8e6  mov     rdx, [rbp+var_28]
0x18000e8ea  add     rdx, 0FFFFFFFFFFFFFFFCh
0x18000e8ee  lea     rcx, [rbp+lpLibFileName]; Src
0x18000e8f2  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000e8f7  test    rbx, rbx
0x18000e8fa  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e901  jz      loc_18000E80F
0x18000e907  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x18000e90e  mov     rcx, rbx; hModule
0x18000e911  call    WINRT_IMPL_GetProcAddress
0x18000e916  test    rax, rax
0x18000e919  jz      short loc_18000E957
0x18000e91b  mov     [rbp+var_48], r14
0x18000e91f  lea     rdx, [rbp+var_48]
0x18000e923  mov     rcx, [r15]
0x18000e926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e92b  test    eax, eax
0x18000e92d  jnz     short loc_18000E948
0x18000e92f  mov     rcx, [rbp+var_48]
0x18000e933  mov     rax, [rcx]
0x18000e936  mov     r8, r13
0x18000e939  mov     rdx, r12
0x18000e93c  mov     rax, [rax]
0x18000e93f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e944  test    eax, eax
0x18000e946  jz      short loc_18000E964
0x18000e948  cmp     [rbp+var_48], r14
0x18000e94c  jz      short loc_18000E957
0x18000e94e  lea     rcx, [rbp+var_48]
0x18000e952  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000e957  mov     rcx, rbx; hLibModule
0x18000e95a  call    WINRT_IMPL_FreeLibrary
0x18000e95f  jmp     loc_18000E80B
0x18000e964  mov     [rsi], r14d
0x18000e967  cmp     [rbp+var_48], r14
0x18000e96b  jz      short loc_18000E976
0x18000e96d  lea     rcx, [rbp+var_48]
0x18000e971  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000e976  lea     rcx, [rbp+lpLibFileName]
0x18000e97a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e97f  cmp     [rbp+pperrinfo], r14
0x18000e983  jmp     short loc_18000E9A0
0x18000e985  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18000e989  xor     ecx, ecx; dwReserved
0x18000e98b  call    SetErrorInfo_0
0x18000e990  mov     [rsi], edi
0x18000e992  lea     rcx, [rbp+lpLibFileName]
0x18000e996  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e99b  cmp     [rbp+pperrinfo], 0
0x18000e9a0  jz      short loc_18000E9AB
0x18000e9a2  lea     rcx, [rbp+pperrinfo]
0x18000e9a6  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000e9ab  mov     rax, rsi
0x18000e9ae  mov     rcx, [rbp+var_18]
0x18000e9b2  xor     rcx, rsp; StackCookie
0x18000e9b5  call    __security_check_cookie
0x18000e9ba  add     rsp, 78h
0x18000e9be  pop     r15
0x18000e9c0  pop     r14
0x18000e9c2  pop     r13
0x18000e9c4  pop     r12
0x18000e9c6  pop     rdi
0x18000e9c7  pop     rsi
0x18000e9c8  pop     rbx
0x18000e9c9  pop     rbp
0x18000e9ca  retn
```
