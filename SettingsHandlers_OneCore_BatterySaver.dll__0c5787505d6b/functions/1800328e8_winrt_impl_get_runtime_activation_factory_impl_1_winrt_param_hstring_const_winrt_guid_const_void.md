# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x1800328e8`
- end: `0x180032b14`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `556`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180032888`

## callees

- `0x180009190`
- `0x180009d80`
- `0x18000a111`
- `0x18000a129`
- `0x18000a135`
- `0x18000a485`
- `0x18000a491`
- `0x18001155c`
- `0x1800144c4`
- `0x1800173f0`
- `0x1800328e8`
- `0x180037aac`
- `0x1800399f8`
- `0x180039a24`
- `0x18004c010`

## string_xrefs

- `0x180032949`: `combase.dll`
- `0x180032a3c`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<1>(_DWORD *a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  const WCHAR *v13; // rdx
  __int64 v14; // r8
  const WCHAR *v15; // rcx
  HMODULE v16; // rdi
  FARPROC v17; // rax
  __int64 v18; // rax
  __int64 v20; // rax
  __int64 v21; // [rsp+20h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+30h] [rbp-38h] BYREF
  __m128i si128; // [rsp+40h] [rbp-28h]

  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD *))winrt_activation_handler)(v8, a3, a4);
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
    v21 = 0;
    ((void (__fastcall *)(__int64 *))ProcAddress)(&v21);
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
  si128 = 0;
  v12 = *a2;
  if ( *a2 )
  {
    v13 = *(const WCHAR **)(v12 + 16);
    v14 = *(unsigned int *)(v12 + 4);
  }
  else
  {
    v13 = &word_180054D68;
    v14 = 0;
  }
  std::wstring::_Construct<1,unsigned short const *>(lpLibFileName, v13, v14);
  while ( 1 )
  {
    do
    {
      v18 = std::wstring::rfind(lpLibFileName);
      if ( v18 == -1 )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        goto LABEL_23;
      }
      std::wstring::resize(lpLibFileName, v18);
      std::wstring::append(lpLibFileName, L".dll");
      v15 = (const WCHAR *)lpLibFileName;
      if ( si128.m128i_i64[1] > 7uLL )
        v15 = lpLibFileName[0];
      v16 = LoadLibraryExW_0(v15, 0, 0x1000u);
      std::wstring::resize(lpLibFileName, si128.m128i_i64[0] - 4);
    }
    while ( !v16 );
    v17 = WINRT_IMPL_GetProcAddress(v16, "DllGetActivationFactory");
    if ( v17 )
      break;
LABEL_20:
    WINRT_IMPL_FreeLibrary(v16);
  }
  v21 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, __int64 *))v17)(*a2, &v21) )
  {
    if ( v21 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v21);
    goto LABEL_20;
  }
  v20 = v21;
  v21 = 0;
  *a4 = v20;
  *a1 = 0;
LABEL_23:
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>((_QWORD *)lpLibFileName[0], (const struct std::nothrow_t *)(2 * si128.m128i_i64[1] + 2));
  LOWORD(lpLibFileName[0]) = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x1800328e8  push    rbp
0x1800328ea  push    rbx
0x1800328eb  push    rsi
0x1800328ec  push    rdi
0x1800328ed  push    r14
0x1800328ef  push    r15
0x1800328f1  mov     rbp, rsp
0x1800328f4  sub     rsp, 68h
0x1800328f8  mov     rax, cs:__security_cookie
0x1800328ff  xor     rax, rsp
0x180032902  mov     [rbp+var_18], rax
0x180032906  mov     r14, r9
0x180032909  mov     rdi, r8
0x18003290c  mov     r15, rdx
0x18003290f  mov     rsi, rcx
0x180032912  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180032919  mov     r8, r9
0x18003291c  mov     rdx, rdi
0x18003291f  mov     rcx, [r15]
0x180032922  test    rax, rax
0x180032925  jz      short loc_180032933
0x180032927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003292c  mov     [rsi], eax
0x18003292e  jmp     loc_180032AE1
0x180032933  call    RoGetActivationFactory_0
0x180032938  mov     ebx, eax
0x18003293a  cmp     eax, 800401F0h
0x18003293f  jnz     short loc_180032995
0x180032941  xor     edx, edx; hFile
0x180032943  mov     r8d, 1000h; dwFlags
0x180032949  lea     rcx, LibFileName; "combase.dll"
0x180032950  call    LoadLibraryExW_0
0x180032955  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18003295c  mov     rcx, rax; hModule
0x18003295f  call    WINRT_IMPL_GetProcAddress
0x180032964  test    rax, rax
0x180032967  jnz     short loc_180032974
0x180032969  mov     dword ptr [rsi], 800401F0h
0x18003296f  jmp     loc_180032AE1
0x180032974  mov     [rbp+var_48], 0
0x18003297c  lea     rcx, [rbp+var_48]
0x180032980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032985  mov     r8, r14
0x180032988  mov     rdx, rdi
0x18003298b  mov     rcx, [r15]
0x18003298e  call    RoGetActivationFactory_0
0x180032993  mov     ebx, eax
0x180032995  test    ebx, ebx
0x180032997  jnz     short loc_1800329A0
0x180032999  mov     [rsi], ebx
0x18003299b  jmp     loc_180032AE1
0x1800329a0  mov     [rbp+pperrinfo], 0
0x1800329a8  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x1800329ac  xor     ecx, ecx; dwReserved
0x1800329ae  call    GetErrorInfo_0
0x1800329b3  xorps   xmm0, xmm0
0x1800329b6  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x1800329ba  xorps   xmm1, xmm1
0x1800329bd  movdqu  [rbp+var_28], xmm1
0x1800329c2  mov     rax, [r15]
0x1800329c5  test    rax, rax
0x1800329c8  jz      short loc_1800329D4
0x1800329ca  mov     rdx, [rax+10h]
0x1800329ce  mov     r8d, [rax+4]
0x1800329d2  jmp     short loc_1800329DE
0x1800329d4  lea     rdx, word_180054D68
0x1800329db  xor     r8d, r8d
0x1800329de  lea     rcx, [rbp+lpLibFileName]
0x1800329e2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800329e7  jmp     loc_180032A84
0x1800329ec  mov     rdx, rax
0x1800329ef  lea     rcx, [rbp+lpLibFileName]
0x1800329f3  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800329f8  lea     rdx, aDll; ".dll"
0x1800329ff  lea     rcx, [rbp+lpLibFileName]; Src
0x180032a03  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180032a08  lea     rcx, [rbp+lpLibFileName]
0x180032a0c  cmp     qword ptr [rbp+var_28+8], 7
0x180032a11  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x180032a16  xor     edx, edx; hFile
0x180032a18  mov     r8d, 1000h; dwFlags
0x180032a1e  call    LoadLibraryExW_0
0x180032a23  mov     rdi, rax
0x180032a26  mov     rdx, qword ptr [rbp+var_28]
0x180032a2a  add     rdx, 0FFFFFFFFFFFFFFFCh
0x180032a2e  lea     rcx, [rbp+lpLibFileName]
0x180032a32  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180032a37  test    rdi, rdi
0x180032a3a  jz      short loc_180032A84
0x180032a3c  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x180032a43  mov     rcx, rdi; hModule
0x180032a46  call    WINRT_IMPL_GetProcAddress
0x180032a4b  test    rax, rax
0x180032a4e  jz      short loc_180032A7C
0x180032a50  mov     [rbp+var_48], 0
0x180032a58  lea     rdx, [rbp+var_48]
0x180032a5c  mov     rcx, [r15]
0x180032a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a64  test    eax, eax
0x180032a66  jz      loc_180032AFD
0x180032a6c  cmp     [rbp+var_48], 0
0x180032a71  jz      short loc_180032A7C
0x180032a73  lea     rcx, [rbp+var_48]
0x180032a77  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180032a7c  mov     rcx, rdi; hLibModule
0x180032a7f  call    WINRT_IMPL_FreeLibrary
0x180032a84  lea     rcx, [rbp+lpLibFileName]
0x180032a88  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::rfind(ushort,unsigned __int64)
0x180032a8d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180032a91  jnz     loc_1800329EC
0x180032a97  mov     rdx, [rbp+pperrinfo]; perrinfo
0x180032a9b  xor     ecx, ecx; dwReserved
0x180032a9d  call    SetErrorInfo_0
0x180032aa2  mov     [rsi], ebx
0x180032aa4  mov     rdx, qword ptr [rbp+var_28+8]
0x180032aa8  cmp     rdx, 7
0x180032aac  jbe     short loc_180032ABF
0x180032aae  lea     rdx, ds:2[rdx*2]
0x180032ab6  mov     rcx, [rbp+lpLibFileName]
0x180032aba  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180032abf  xor     eax, eax
0x180032ac1  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180032ac9  cmp     [rbp+pperrinfo], rax
0x180032acd  mov     word ptr [rbp+lpLibFileName], ax
0x180032ad1  movdqu  [rbp+var_28], xmm0
0x180032ad6  jz      short loc_180032AE1
0x180032ad8  lea     rcx, [rbp+pperrinfo]
0x180032adc  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180032ae1  mov     rax, rsi
0x180032ae4  mov     rcx, [rbp+var_18]
0x180032ae8  xor     rcx, rsp; StackCookie
0x180032aeb  call    __security_check_cookie
0x180032af0  add     rsp, 68h
0x180032af4  pop     r15
0x180032af6  pop     r14
0x180032af8  pop     rdi
0x180032af9  pop     rsi
0x180032afa  pop     rbx
0x180032afb  pop     rbp
0x180032afc  retn
0x180032afd  mov     rax, [rbp+var_48]
0x180032b01  mov     [rbp+var_48], 0
0x180032b09  mov     [r14], rax
0x180032b0c  mov     dword ptr [rsi], 0
0x180032b12  jmp     short loc_180032AA4
```
