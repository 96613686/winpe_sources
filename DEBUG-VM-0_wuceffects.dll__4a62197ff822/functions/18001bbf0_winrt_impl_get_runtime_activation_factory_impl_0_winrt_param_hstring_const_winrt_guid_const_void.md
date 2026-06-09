# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18001bbf0`
- end: `0x18001be0c`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e83c`

## callees

- `0x180012040`
- `0x18001b620`
- `0x18001bbf0`
- `0x18001e7ac`
- `0x18001f760`
- `0x180021060`
- `0x180021df6`
- `0x180021e0e`
- `0x180021e1a`
- `0x18002234d`
- `0x180022371`
- `0x180022395`
- `0x18002584c`
- `0x180028ddc`
- `0x18002ad1c`
- `0x18002e010`

## string_xrefs

- `0x18001bc54`: `combase.dll`
- `0x18001bd4d`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  const WCHAR *v13; // rcx
  HMODULE v14; // rdi
  FARPROC v15; // rax
  _QWORD v17[2]; // [rsp+20h] [rbp-40h] BYREF
  IErrorInfo *pperrinfo; // [rsp+30h] [rbp-30h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+38h] [rbp-28h] BYREF
  __int128 v20; // [rsp+48h] [rbp-18h]

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
    v17[0] = 0;
    ((void (__fastcall *)(_QWORD *))ProcAddress)(v17);
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
  v20 = 0;
  winrt::hstring::operator std::basic_string_view<unsigned short>(a2, v17);
  std::wstring::_Construct<1,unsigned short const *>(lpLibFileName, v17[0], v17[1]);
  while ( 1 )
  {
    do
    {
      v12 = std::wstring::rfind(lpLibFileName);
      if ( v12 == -1 )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        goto LABEL_23;
      }
      std::wstring::resize(lpLibFileName, v12);
      std::wstring::_Append<unsigned short>(lpLibFileName);
      v13 = (const WCHAR *)lpLibFileName;
      if ( *((_QWORD *)&v20 + 1) > 7u )
        v13 = lpLibFileName[0];
      v14 = LoadLibraryExW_0(v13, 0, 0x1000u);
      std::wstring::resize(lpLibFileName, v20 - 4);
    }
    while ( !v14 );
    v15 = WINRT_IMPL_GetProcAddress(v14, "DllGetActivationFactory");
    if ( v15 )
      break;
LABEL_19:
    WINRT_IMPL_FreeLibrary(v14);
  }
  v17[0] = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, _QWORD *))v15)(*a2, v17)
    || (**(unsigned int (__fastcall ***)(_QWORD, __int64, __int64))v17[0])(v17[0], a3, a4) )
  {
    if ( v17[0] )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v17);
    goto LABEL_19;
  }
  *a1 = 0;
  if ( v17[0] )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v17);
LABEL_23:
  std::wstring::~wstring(lpLibFileName);
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x18001bbf0  push    rbp
0x18001bbf2  push    rbx
0x18001bbf3  push    rsi
0x18001bbf4  push    rdi
0x18001bbf5  push    r12
0x18001bbf7  push    r14
0x18001bbf9  push    r15
0x18001bbfb  mov     rbp, rsp
0x18001bbfe  sub     rsp, 60h
0x18001bc02  mov     rax, cs:__security_cookie
0x18001bc09  xor     rax, rsp
0x18001bc0c  mov     [rbp+var_8], rax
0x18001bc10  mov     r15, r9
0x18001bc13  mov     r14, r8
0x18001bc16  mov     r12, rdx
0x18001bc19  mov     rsi, rcx
0x18001bc1c  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18001bc23  mov     r8, r9
0x18001bc26  mov     rdx, r14
0x18001bc29  mov     rcx, [r12]
0x18001bc2d  test    rax, rax
0x18001bc30  jz      short loc_18001BC3E
0x18001bc32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc37  mov     [rsi], eax
0x18001bc39  jmp     loc_18001BDEE
0x18001bc3e  call    RoGetActivationFactory_0
0x18001bc43  mov     ebx, eax
0x18001bc45  cmp     eax, 800401F0h
0x18001bc4a  jnz     short loc_18001BCA1
0x18001bc4c  xor     edx, edx; hFile
0x18001bc4e  mov     r8d, 1000h; dwFlags
0x18001bc54  lea     rcx, LibFileName; "combase.dll"
0x18001bc5b  call    LoadLibraryExW_0
0x18001bc60  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18001bc67  mov     rcx, rax; hModule
0x18001bc6a  call    WINRT_IMPL_GetProcAddress
0x18001bc6f  test    rax, rax
0x18001bc72  jnz     short loc_18001BC7F
0x18001bc74  mov     dword ptr [rsi], 800401F0h
0x18001bc7a  jmp     loc_18001BDEE
0x18001bc7f  mov     [rbp+var_40], 0
0x18001bc87  lea     rcx, [rbp+var_40]
0x18001bc8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc90  mov     r8, r15
0x18001bc93  mov     rdx, r14
0x18001bc96  mov     rcx, [r12]
0x18001bc9a  call    RoGetActivationFactory_0
0x18001bc9f  mov     ebx, eax
0x18001bca1  test    ebx, ebx
0x18001bca3  jnz     short loc_18001BCAC
0x18001bca5  mov     [rsi], ebx
0x18001bca7  jmp     loc_18001BDEE
0x18001bcac  mov     [rbp+pperrinfo], 0
0x18001bcb4  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18001bcb8  xor     ecx, ecx; dwReserved
0x18001bcba  call    GetErrorInfo_0
0x18001bcbf  xorps   xmm0, xmm0
0x18001bcc2  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x18001bcc6  xorps   xmm1, xmm1
0x18001bcc9  movdqu  [rbp+var_18], xmm1
0x18001bcce  lea     rdx, [rbp+var_40]
0x18001bcd2  mov     rcx, r12
0x18001bcd5  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x18001bcda  mov     r8, [rbp+var_38]
0x18001bcde  mov     rdx, [rbp+var_40]
0x18001bce2  lea     rcx, [rbp+lpLibFileName]
0x18001bce6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001bceb  lea     rcx, [rbp+lpLibFileName]
0x18001bcef  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::rfind(ushort,unsigned __int64)
0x18001bcf4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001bcf8  jz      loc_18001BDC8
0x18001bcfe  mov     rdx, rax
0x18001bd01  lea     rcx, [rbp+lpLibFileName]
0x18001bd05  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001bd0a  mov     r8d, 4
0x18001bd10  lea     rcx, [rbp+lpLibFileName]; Src
0x18001bd14  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001bd19  lea     rcx, [rbp+lpLibFileName]
0x18001bd1d  cmp     qword ptr [rbp+var_18+8], 7
0x18001bd22  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x18001bd27  xor     edx, edx; hFile
0x18001bd29  mov     r8d, 1000h; dwFlags
0x18001bd2f  call    LoadLibraryExW_0
0x18001bd34  mov     rdi, rax
0x18001bd37  mov     rdx, qword ptr [rbp+var_18]
0x18001bd3b  add     rdx, 0FFFFFFFFFFFFFFFCh
0x18001bd3f  lea     rcx, [rbp+lpLibFileName]
0x18001bd43  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001bd48  test    rdi, rdi
0x18001bd4b  jz      short loc_18001BCEB
0x18001bd4d  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x18001bd54  mov     rcx, rdi; hModule
0x18001bd57  call    WINRT_IMPL_GetProcAddress
0x18001bd5c  test    rax, rax
0x18001bd5f  jz      short loc_18001BDA3
0x18001bd61  mov     [rbp+var_40], 0
0x18001bd69  lea     rdx, [rbp+var_40]
0x18001bd6d  mov     rcx, [r12]
0x18001bd71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd76  test    eax, eax
0x18001bd78  jnz     short loc_18001BD93
0x18001bd7a  mov     rcx, [rbp+var_40]
0x18001bd7e  mov     rax, [rcx]
0x18001bd81  mov     r8, r15
0x18001bd84  mov     rdx, r14
0x18001bd87  mov     rax, [rax]
0x18001bd8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd8f  test    eax, eax
0x18001bd91  jz      short loc_18001BDB0
0x18001bd93  cmp     [rbp+var_40], 0
0x18001bd98  jz      short loc_18001BDA3
0x18001bd9a  lea     rcx, [rbp+var_40]
0x18001bd9e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001bda3  mov     rcx, rdi; hLibModule
0x18001bda6  call    WINRT_IMPL_FreeLibrary
0x18001bdab  jmp     loc_18001BCEB
0x18001bdb0  mov     dword ptr [rsi], 0
0x18001bdb6  cmp     [rbp+var_40], 0
0x18001bdbb  jz      short loc_18001BDD5
0x18001bdbd  lea     rcx, [rbp+var_40]
0x18001bdc1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001bdc6  jmp     short loc_18001BDD5
0x18001bdc8  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18001bdcc  xor     ecx, ecx; dwReserved
0x18001bdce  call    SetErrorInfo_0
0x18001bdd3  mov     [rsi], ebx
0x18001bdd5  lea     rcx, [rbp+lpLibFileName]
0x18001bdd9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bdde  cmp     [rbp+pperrinfo], 0
0x18001bde3  jz      short loc_18001BDEE
0x18001bde5  lea     rcx, [rbp+pperrinfo]
0x18001bde9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001bdee  mov     rax, rsi
0x18001bdf1  mov     rcx, [rbp+var_8]
0x18001bdf5  xor     rcx, rsp; StackCookie
0x18001bdf8  call    __security_check_cookie
0x18001bdfd  add     rsp, 60h
0x18001be01  pop     r15
0x18001be03  pop     r14
0x18001be05  pop     r12
0x18001be07  pop     rdi
0x18001be08  pop     rsi
0x18001be09  pop     rbx
0x18001be0a  pop     rbp
0x18001be0b  retn
```
