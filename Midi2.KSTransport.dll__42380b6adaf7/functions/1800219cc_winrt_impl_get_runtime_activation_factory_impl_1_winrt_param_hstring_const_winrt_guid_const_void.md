# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x1800219cc`
- end: `0x180021c34`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `616`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800218f4`

## callees

- `0x180003fe0`
- `0x180004410`
- `0x180005368`
- `0x180005380`
- `0x180005398`
- `0x180005479`
- `0x180005491`
- `0x1800054b5`
- `0x18000c250`
- `0x18000d1c0`
- `0x18000f304`
- `0x180011400`
- `0x1800152cc`
- `0x1800219cc`
- `0x180041010`

## string_xrefs

- `0x180021a30`: `combase.dll`
- `0x180021b8d`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<1>(_DWORD *a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  const wchar_t *v13; // rdx
  __int64 v14; // r8
  LPCWSTR *v15; // r14
  char *v16; // rdi
  __int64 last_trivial_2; // rax
  const WCHAR *v18; // rcx
  HMODULE v19; // rdi
  FARPROC v20; // rax
  __int64 v21; // rax
  __int64 v23; // [rsp+20h] [rbp-40h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-38h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v26; // [rsp+40h] [rbp-20h]
  unsigned __int64 v27; // [rsp+48h] [rbp-18h]

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
      v23 = 0;
      ((void (__fastcall *)(__int64 *))ProcAddress)(&v23);
      ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
    }
    if ( ActivationFactory_0 )
    {
      pperrinfo = 0;
      GetErrorInfo_0(0, &pperrinfo);
      *(_OWORD *)lpLibFileName = 0;
      v26 = 0;
      v27 = 0;
      v12 = *a2;
      if ( *a2 )
      {
        v13 = *(const wchar_t **)(v12 + 16);
        v14 = *(unsigned int *)(v12 + 4);
      }
      else
      {
        v13 = &S1;
        v14 = 0;
      }
      std::wstring::_Construct<1,unsigned short const *>(lpLibFileName, v13, v14);
      while ( 1 )
      {
        v15 = lpLibFileName;
        if ( v27 > 7 )
          v15 = (LPCWSTR *)lpLibFileName[0];
        if ( !v26 )
          break;
        v16 = (char *)v15 + 2 * v26;
        last_trivial_2 = _std_find_last_trivial_2(v15, v16, 46);
        if ( (char *)last_trivial_2 == v16 || (last_trivial_2 - (__int64)v15) >> 1 == -1 )
          break;
        std::wstring::resize(lpLibFileName);
        std::wstring::operator+=(lpLibFileName, L".dll");
        v18 = (const WCHAR *)lpLibFileName;
        if ( v27 > 7 )
          v18 = lpLibFileName[0];
        v19 = LoadLibraryExW_0(v18, 0, 0x1000u);
        std::wstring::resize(lpLibFileName);
        if ( v19 )
        {
          v20 = WINRT_IMPL_GetProcAddress(v19, "DllGetActivationFactory");
          if ( v20 )
          {
            v23 = 0;
            if ( !((unsigned int (__fastcall *)(_QWORD, __int64 *))v20)(*a2, &v23) )
            {
              v21 = v23;
              v23 = 0;
              *a4 = v21;
              *a1 = 0;
              goto LABEL_28;
            }
            if ( v23 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
          }
          WINRT_IMPL_FreeLibrary(v19);
        }
      }
      SetErrorInfo_0(0, pperrinfo);
      *a1 = ActivationFactory_0;
LABEL_28:
      std::wstring::~wstring(lpLibFileName);
      if ( pperrinfo )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
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
0x1800219cc  push    rbp
0x1800219ce  push    rbx
0x1800219cf  push    rsi
0x1800219d0  push    rdi
0x1800219d1  push    r12
0x1800219d3  push    r14
0x1800219d5  push    r15
0x1800219d7  mov     rbp, rsp
0x1800219da  sub     rsp, 60h
0x1800219de  mov     rax, cs:__security_cookie
0x1800219e5  xor     rax, rsp
0x1800219e8  mov     [rbp+var_10], rax
0x1800219ec  mov     r15, r9
0x1800219ef  mov     rdi, r8
0x1800219f2  mov     r12, rdx
0x1800219f5  mov     rsi, rcx
0x1800219f8  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x1800219ff  mov     r8, r9
0x180021a02  mov     rdx, rdi
0x180021a05  mov     rcx, [r12]
0x180021a09  test    rax, rax
0x180021a0c  jz      short loc_180021A1A
0x180021a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a13  mov     [rsi], eax
0x180021a15  jmp     loc_180021C16
0x180021a1a  call    RoGetActivationFactory_0
0x180021a1f  mov     ebx, eax
0x180021a21  cmp     eax, 800401F0h
0x180021a26  jnz     short loc_180021A7D
0x180021a28  xor     edx, edx; hFile
0x180021a2a  mov     r8d, 1000h; dwFlags
0x180021a30  lea     rcx, aCombaseDll; "combase.dll"
0x180021a37  call    LoadLibraryExW_0
0x180021a3c  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x180021a43  mov     rcx, rax; hModule
0x180021a46  call    WINRT_IMPL_GetProcAddress
0x180021a4b  test    rax, rax
0x180021a4e  jnz     short loc_180021A5B
0x180021a50  mov     dword ptr [rsi], 800401F0h
0x180021a56  jmp     loc_180021C16
0x180021a5b  mov     [rbp+var_40], 0
0x180021a63  lea     rcx, [rbp+var_40]
0x180021a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a6c  mov     r8, r15
0x180021a6f  mov     rdx, rdi
0x180021a72  mov     rcx, [r12]
0x180021a76  call    RoGetActivationFactory_0
0x180021a7b  mov     ebx, eax
0x180021a7d  test    ebx, ebx
0x180021a7f  jnz     short loc_180021A88
0x180021a81  mov     [rsi], ebx
0x180021a83  jmp     loc_180021C16
0x180021a88  mov     [rbp+pperrinfo], 0
0x180021a90  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180021a94  xor     ecx, ecx; dwReserved
0x180021a96  call    GetErrorInfo_0
0x180021a9b  xorps   xmm0, xmm0
0x180021a9e  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x180021aa2  mov     [rbp+var_20], 0
0x180021aaa  mov     [rbp+var_18], 0
0x180021ab2  mov     rax, [r12]
0x180021ab6  test    rax, rax
0x180021ab9  jz      short loc_180021AC5
0x180021abb  mov     rdx, [rax+10h]
0x180021abf  mov     r8d, [rax+4]
0x180021ac3  jmp     short loc_180021ACF
0x180021ac5  lea     rdx, S1
0x180021acc  xor     r8d, r8d
0x180021acf  lea     rcx, [rbp+lpLibFileName]
0x180021ad3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180021ad8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180021adc  mov     rax, [rbp+var_20]
0x180021ae0  lea     r14, [rbp+lpLibFileName]
0x180021ae4  cmp     [rbp+var_18], 7
0x180021ae9  cmova   r14, [rbp+lpLibFileName]
0x180021aee  test    rax, rax
0x180021af1  jz      loc_180021BF0
0x180021af7  dec     rax
0x180021afa  cmp     rax, rcx
0x180021afd  cmovnb  rax, rcx
0x180021b01  inc     rax
0x180021b04  lea     rdi, [r14+rax*2]
0x180021b08  mov     r8d, 2Eh ; '.'
0x180021b0e  mov     rdx, rdi
0x180021b11  mov     rcx, r14
0x180021b14  call    __std_find_last_trivial_2
0x180021b19  cmp     rax, rdi
0x180021b1c  jz      loc_180021BF0
0x180021b22  sub     rax, r14
0x180021b25  sar     rax, 1
0x180021b28  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021b2c  jz      loc_180021BF0
0x180021b32  mov     rdx, rax
0x180021b35  lea     rcx, [rbp+lpLibFileName]; Src
0x180021b39  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180021b3e  lea     rdx, aDll; ".dll"
0x180021b45  lea     rcx, [rbp+lpLibFileName]; Src
0x180021b49  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x180021b4e  lea     rcx, [rbp+lpLibFileName]
0x180021b52  cmp     [rbp+var_18], 7
0x180021b57  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x180021b5c  xor     edx, edx; hFile
0x180021b5e  mov     r8d, 1000h; dwFlags
0x180021b64  call    LoadLibraryExW_0
0x180021b69  mov     rdi, rax
0x180021b6c  mov     rdx, [rbp+var_20]
0x180021b70  add     rdx, 0FFFFFFFFFFFFFFFCh
0x180021b74  lea     rcx, [rbp+lpLibFileName]; Src
0x180021b78  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180021b7d  test    rdi, rdi
0x180021b80  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180021b87  jz      loc_180021ADC
0x180021b8d  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x180021b94  mov     rcx, rdi; hModule
0x180021b97  call    WINRT_IMPL_GetProcAddress
0x180021b9c  test    rax, rax
0x180021b9f  jnz     short loc_180021BAE
0x180021ba1  mov     rcx, rdi; hLibModule
0x180021ba4  call    WINRT_IMPL_FreeLibrary
0x180021ba9  jmp     loc_180021AD8
0x180021bae  mov     [rbp+var_40], 0
0x180021bb6  lea     rdx, [rbp+var_40]
0x180021bba  mov     rcx, [r12]
0x180021bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bc3  test    eax, eax
0x180021bc5  jz      short loc_180021BD9
0x180021bc7  cmp     [rbp+var_40], 0
0x180021bcc  jz      short loc_180021BA1
0x180021bce  lea     rcx, [rbp+var_40]
0x180021bd2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180021bd7  jmp     short loc_180021BA1
0x180021bd9  mov     rax, [rbp+var_40]
0x180021bdd  mov     [rbp+var_40], 0
0x180021be5  mov     [r15], rax
0x180021be8  mov     dword ptr [rsi], 0
0x180021bee  jmp     short loc_180021BFD
0x180021bf0  mov     rdx, [rbp+pperrinfo]; perrinfo
0x180021bf4  xor     ecx, ecx; dwReserved
0x180021bf6  call    SetErrorInfo_0
0x180021bfb  mov     [rsi], ebx
0x180021bfd  lea     rcx, [rbp+lpLibFileName]; void *
0x180021c01  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021c06  cmp     [rbp+pperrinfo], 0
0x180021c0b  jz      short loc_180021C16
0x180021c0d  lea     rcx, [rbp+pperrinfo]
0x180021c11  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180021c16  mov     rax, rsi
0x180021c19  mov     rcx, [rbp+var_10]
0x180021c1d  xor     rcx, rsp; StackCookie
0x180021c20  call    __security_check_cookie
0x180021c25  add     rsp, 60h
0x180021c29  pop     r15
0x180021c2b  pop     r14
0x180021c2d  pop     r12
0x180021c2f  pop     rdi
0x180021c30  pop     rsi
0x180021c31  pop     rbx
0x180021c32  pop     rbp
0x180021c33  retn
```
