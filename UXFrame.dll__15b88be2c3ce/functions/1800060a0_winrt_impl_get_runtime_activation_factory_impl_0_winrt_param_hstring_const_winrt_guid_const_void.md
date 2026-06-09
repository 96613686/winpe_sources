# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x1800060a0`
- end: `0x1800062ae`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `526`
- prototype: ``
- caller_count: `33`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800054f4`
- `0x1800056e4`
- `0x180005850`
- `0x180005e28`
- `0x18000a4c8`
- `0x18000a7b4`
- `0x18001eaa0`
- `0x18001ec0c`
- `0x18001ed78`
- `0x18001f350`
- `0x18002ec04`
- `0x18002ed64`
- `0x18002eec8`
- `0x18003286c`
- `0x18003333c`
- `0x18003349c`
- `0x18003360c`
- `0x18003377c`
- `0x180033b5c`
- `0x18003a494`
- `0x18003a600`
- `0x18003a76c`
- `0x18003aa74`
- `0x18003abe0`
- `0x18003ad30`
- `0x18003af04`
- `0x18003b070`
- `0x18003b1dc`
- `0x18003b478`
- `0x18003b5c8`
- `0x18003b738`
- `0x18003bb18`
- `0x18003c1a8`

## callees

- `0x1800028ac`
- `0x180002b20`
- `0x180003db5`
- `0x180003dc1`
- `0x180003dfd`
- `0x180003e09`
- `0x180003e15`
- `0x1800049ac`
- `0x180004ad8`
- `0x180004f80`
- `0x1800052f0`
- `0x1800060a0`
- `0x180008968`
- `0x180008de8`
- `0x18005a010`

## string_xrefs

- `0x180006103`: `combase.dll`
- `0x1800061f0`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  LPCWSTR *v12; // rcx
  __int64 v13; // rax
  const WCHAR *v14; // rcx
  HMODULE v15; // rdi
  FARPROC v16; // rax
  unsigned int (__fastcall ***v18)(_QWORD, __int64, __int64); // [rsp+20h] [rbp-40h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-38h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v21; // [rsp+40h] [rbp-20h]
  unsigned __int64 v22; // [rsp+48h] [rbp-18h]

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
    v18 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v18);
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
      if ( v22 > 7 )
        v12 = (LPCWSTR *)lpLibFileName[0];
      v13 = std::_Traits_rfind_ch<std::char_traits<wchar_t>>(v12, v21);
      if ( v13 == -1 )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        goto LABEL_25;
      }
      std::wstring::resize(lpLibFileName, v13);
      std::wstring::_Append<wchar_t>(lpLibFileName);
      v14 = (const WCHAR *)lpLibFileName;
      if ( v22 > 7 )
        v14 = lpLibFileName[0];
      v15 = LoadLibraryExW_0(v14, 0, 0x1000u);
      std::wstring::resize(lpLibFileName, v21 - 4);
    }
    while ( !v15 );
    v16 = WINRT_IMPL_GetProcAddress(v15, "DllGetActivationFactory");
    if ( v16 )
      break;
LABEL_21:
    WINRT_IMPL_FreeLibrary(v15);
  }
  v18 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v16)(*a2, &v18)
    || (**v18)(v18, a3, a4) )
  {
    if ( v18 )
      winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v18);
    goto LABEL_21;
  }
  *a1 = 0;
  if ( v18 )
    winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v18);
LABEL_25:
  std::wstring::_Tidy_deallocate(lpLibFileName);
  if ( pperrinfo )
    winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x1800060a0  push    rbp
0x1800060a2  push    rbx
0x1800060a3  push    rsi
0x1800060a4  push    rdi
0x1800060a5  push    r12
0x1800060a7  push    r14
0x1800060a9  push    r15
0x1800060ab  mov     rbp, rsp
0x1800060ae  sub     rsp, 60h
0x1800060b2  mov     rax, cs:__security_cookie
0x1800060b9  xor     rax, rsp
0x1800060bc  mov     [rbp+var_10], rax
0x1800060c0  mov     r12, r9
0x1800060c3  mov     r15, r8
0x1800060c6  mov     r14, rdx
0x1800060c9  mov     rsi, rcx
0x1800060cc  mov     rcx, [rdx]
0x1800060cf  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x1800060d6  mov     r8, r9
0x1800060d9  mov     rdx, r15
0x1800060dc  test    rax, rax
0x1800060df  jz      short loc_1800060ED
0x1800060e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060e6  mov     [rsi], eax
0x1800060e8  jmp     loc_180006290
0x1800060ed  call    RoGetActivationFactory_0
0x1800060f2  mov     ebx, eax
0x1800060f4  cmp     eax, 800401F0h
0x1800060f9  jnz     short loc_18000614F
0x1800060fb  xor     edx, edx; hFile
0x1800060fd  mov     r8d, 1000h; dwFlags
0x180006103  lea     rcx, LibFileName; "combase.dll"
0x18000610a  call    LoadLibraryExW_0
0x18000610f  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x180006116  mov     rcx, rax; hModule
0x180006119  call    WINRT_IMPL_GetProcAddress
0x18000611e  test    rax, rax
0x180006121  jnz     short loc_18000612E
0x180006123  mov     dword ptr [rsi], 800401F0h
0x180006129  jmp     loc_180006290
0x18000612e  mov     [rbp+var_40], 0
0x180006136  lea     rcx, [rbp+var_40]
0x18000613a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000613f  mov     r8, r12
0x180006142  mov     rdx, r15
0x180006145  mov     rcx, [r14]
0x180006148  call    RoGetActivationFactory_0
0x18000614d  mov     ebx, eax
0x18000614f  test    ebx, ebx
0x180006151  jnz     short loc_18000615A
0x180006153  mov     [rsi], ebx
0x180006155  jmp     loc_180006290
0x18000615a  mov     [rbp+pperrinfo], 0
0x180006162  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180006166  xor     ecx, ecx; dwReserved
0x180006168  call    GetErrorInfo_0
0x18000616d  mov     rdx, r14
0x180006170  lea     rcx, [rbp+lpLibFileName]
0x180006174  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<wchar_t> const &)
0x180006179  lea     rcx, [rbp+lpLibFileName]
0x18000617d  cmp     [rbp+var_18], 7
0x180006182  cmova   rcx, [rbp+lpLibFileName]
0x180006187  mov     rdx, [rbp+var_20]
0x18000618b  call    ??$_Traits_rfind_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_rfind_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x180006190  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006194  jz      loc_18000626A
0x18000619a  mov     rdx, rax
0x18000619d  lea     rcx, [rbp+lpLibFileName]
0x1800061a1  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800061a6  mov     r8d, 4
0x1800061ac  lea     rdx, aDll; ".dll"
0x1800061b3  lea     rcx, [rbp+lpLibFileName]; Src
0x1800061b7  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800061bc  lea     rcx, [rbp+lpLibFileName]
0x1800061c0  cmp     [rbp+var_18], 7
0x1800061c5  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x1800061ca  xor     edx, edx; hFile
0x1800061cc  mov     r8d, 1000h; dwFlags
0x1800061d2  call    LoadLibraryExW_0
0x1800061d7  mov     rdi, rax
0x1800061da  mov     rdx, [rbp+var_20]
0x1800061de  add     rdx, 0FFFFFFFFFFFFFFFCh
0x1800061e2  lea     rcx, [rbp+lpLibFileName]
0x1800061e6  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800061eb  test    rdi, rdi
0x1800061ee  jz      short loc_180006179
0x1800061f0  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x1800061f7  mov     rcx, rdi; hModule
0x1800061fa  call    WINRT_IMPL_GetProcAddress
0x1800061ff  test    rax, rax
0x180006202  jz      short loc_180006245
0x180006204  mov     [rbp+var_40], 0
0x18000620c  lea     rdx, [rbp+var_40]
0x180006210  mov     rcx, [r14]
0x180006213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006218  test    eax, eax
0x18000621a  jnz     short loc_180006235
0x18000621c  mov     rcx, [rbp+var_40]
0x180006220  mov     rax, [rcx]
0x180006223  mov     r8, r12
0x180006226  mov     rdx, r15
0x180006229  mov     rax, [rax]
0x18000622c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006231  test    eax, eax
0x180006233  jz      short loc_180006252
0x180006235  cmp     [rbp+var_40], 0
0x18000623a  jz      short loc_180006245
0x18000623c  lea     rcx, [rbp+var_40]
0x180006240  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x180006245  mov     rcx, rdi; hLibModule
0x180006248  call    WINRT_IMPL_FreeLibrary
0x18000624d  jmp     loc_180006179
0x180006252  mov     dword ptr [rsi], 0
0x180006258  cmp     [rbp+var_40], 0
0x18000625d  jz      short loc_180006277
0x18000625f  lea     rcx, [rbp+var_40]
0x180006263  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x180006268  jmp     short loc_180006277
0x18000626a  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18000626e  xor     ecx, ecx; dwReserved
0x180006270  call    SetErrorInfo_0
0x180006275  mov     [rsi], ebx
0x180006277  lea     rcx, [rbp+lpLibFileName]
0x18000627b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180006280  cmp     [rbp+pperrinfo], 0
0x180006285  jz      short loc_180006290
0x180006287  lea     rcx, [rbp+pperrinfo]
0x18000628b  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x180006290  mov     rax, rsi
0x180006293  mov     rcx, [rbp+var_10]
0x180006297  xor     rcx, rsp; StackCookie
0x18000629a  call    __security_check_cookie
0x18000629f  add     rsp, 60h
0x1800062a3  pop     r15
0x1800062a5  pop     r14
0x1800062a7  pop     r12
0x1800062a9  pop     rdi
0x1800062aa  pop     rsi
0x1800062ab  pop     rbx
0x1800062ac  pop     rbp
0x1800062ad  retn
```
