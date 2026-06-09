# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x180017a90`
- end: `0x180017c80`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `496`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001781c`

## callees

- `0x180002d40`
- `0x180003b4c`
- `0x180004428`
- `0x180004434`
- `0x180004645`
- `0x180004651`
- `0x18000468d`
- `0x180004a0c`
- `0x1800061ec`
- `0x18000f8a8`
- `0x18000f97c`
- `0x180010ef0`
- `0x1800115a4`
- `0x180017a90`
- `0x180048010`

## string_xrefs

- `0x180017af1`: `combase.dll`
- `0x180017bde`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<1>(_DWORD *a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // r8
  LPCWSTR *v13; // rcx
  __int64 v14; // rax
  const WCHAR *v15; // rcx
  HMODULE v16; // rdi
  FARPROC v17; // rax
  __int64 v18; // rax
  __int64 v20; // [rsp+20h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v23; // [rsp+40h] [rbp-28h]
  unsigned __int64 v24; // [rsp+48h] [rbp-20h]

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
      v20 = 0;
      ((void (__fastcall *)(__int64 *))ProcAddress)(&v20);
      ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
    }
    if ( ActivationFactory_0 )
    {
      pperrinfo = 0;
      GetErrorInfo_0(0, &pperrinfo);
      std::wstring::wstring(lpLibFileName, a2);
      while ( 1 )
      {
        v13 = lpLibFileName;
        if ( v24 > 7 )
          v13 = (LPCWSTR *)lpLibFileName[0];
        v14 = std::_Traits_rfind_ch<std::char_traits<unsigned short>>(v13, v23, v12, 46);
        if ( v14 == -1 )
          break;
        std::wstring::resize(lpLibFileName, v14);
        std::wstring::append(lpLibFileName, L".dll");
        v15 = (const WCHAR *)lpLibFileName;
        if ( v24 > 7 )
          v15 = lpLibFileName[0];
        v16 = LoadLibraryExW_0(v15, 0, 0x1000u);
        std::wstring::resize(lpLibFileName, v23 - 4);
        if ( v16 )
        {
          v17 = WINRT_IMPL_GetProcAddress(v16, "DllGetActivationFactory");
          if ( v17 )
          {
            v20 = 0;
            if ( !((unsigned int (__fastcall *)(_QWORD, __int64 *))v17)(*a2, &v20) )
            {
              v18 = v20;
              v20 = 0;
              *a4 = v18;
              *a1 = 0;
              goto LABEL_23;
            }
            if ( v20 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
          }
          WINRT_IMPL_FreeLibrary(v16);
        }
      }
      SetErrorInfo_0(0, pperrinfo);
      *a1 = ActivationFactory_0;
LABEL_23:
      std::wstring::_Tidy_deallocate(lpLibFileName);
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
0x180017a90  push    rbp
0x180017a92  push    rbx
0x180017a93  push    rsi
0x180017a94  push    rdi
0x180017a95  push    r14
0x180017a97  push    r15
0x180017a99  mov     rbp, rsp
0x180017a9c  sub     rsp, 68h
0x180017aa0  mov     rax, cs:__security_cookie
0x180017aa7  xor     rax, rsp
0x180017aaa  mov     [rbp+var_18], rax
0x180017aae  mov     r14, r9
0x180017ab1  mov     rdi, r8
0x180017ab4  mov     r15, rdx
0x180017ab7  mov     rsi, rcx
0x180017aba  mov     rcx, [rdx]
0x180017abd  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180017ac4  mov     r8, r9
0x180017ac7  mov     rdx, rdi
0x180017aca  test    rax, rax
0x180017acd  jz      short loc_180017ADB
0x180017acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ad4  mov     [rsi], eax
0x180017ad6  jmp     loc_180017C64
0x180017adb  call    RoGetActivationFactory_0
0x180017ae0  mov     ebx, eax
0x180017ae2  cmp     eax, 800401F0h
0x180017ae7  jnz     short loc_180017B3D
0x180017ae9  xor     edx, edx; hFile
0x180017aeb  mov     r8d, 1000h; dwFlags
0x180017af1  lea     rcx, LibFileName; "combase.dll"
0x180017af8  call    LoadLibraryExW_0
0x180017afd  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x180017b04  mov     rcx, rax; hModule
0x180017b07  call    WINRT_IMPL_GetProcAddress
0x180017b0c  test    rax, rax
0x180017b0f  jnz     short loc_180017B1C
0x180017b11  mov     dword ptr [rsi], 800401F0h
0x180017b17  jmp     loc_180017C64
0x180017b1c  mov     [rbp+var_48], 0
0x180017b24  lea     rcx, [rbp+var_48]
0x180017b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b2d  mov     r8, r14
0x180017b30  mov     rdx, rdi
0x180017b33  mov     rcx, [r15]
0x180017b36  call    RoGetActivationFactory_0
0x180017b3b  mov     ebx, eax
0x180017b3d  test    ebx, ebx
0x180017b3f  jnz     short loc_180017B48
0x180017b41  mov     [rsi], ebx
0x180017b43  jmp     loc_180017C64
0x180017b48  mov     [rbp+pperrinfo], 0
0x180017b50  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180017b54  xor     ecx, ecx; dwReserved
0x180017b56  call    GetErrorInfo_0
0x180017b5b  mov     rdx, r15
0x180017b5e  lea     rcx, [rbp+lpLibFileName]
0x180017b62  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x180017b67  lea     rcx, [rbp+lpLibFileName]
0x180017b6b  cmp     [rbp+var_20], 7
0x180017b70  cmova   rcx, [rbp+lpLibFileName]
0x180017b75  mov     r9d, 2Eh ; '.'
0x180017b7b  mov     rdx, [rbp+var_28]
0x180017b7f  call    ??$_Traits_rfind_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_rfind_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x180017b84  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180017b88  jz      loc_180017C3E
0x180017b8e  mov     rdx, rax
0x180017b91  lea     rcx, [rbp+lpLibFileName]
0x180017b95  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180017b9a  lea     rdx, aDll; ".dll"
0x180017ba1  lea     rcx, [rbp+lpLibFileName]
0x180017ba5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180017baa  lea     rcx, [rbp+lpLibFileName]
0x180017bae  cmp     [rbp+var_20], 7
0x180017bb3  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x180017bb8  xor     edx, edx; hFile
0x180017bba  mov     r8d, 1000h; dwFlags
0x180017bc0  call    LoadLibraryExW_0
0x180017bc5  mov     rdi, rax
0x180017bc8  mov     rdx, [rbp+var_28]
0x180017bcc  add     rdx, 0FFFFFFFFFFFFFFFCh
0x180017bd0  lea     rcx, [rbp+lpLibFileName]
0x180017bd4  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180017bd9  test    rdi, rdi
0x180017bdc  jz      short loc_180017B67
0x180017bde  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x180017be5  mov     rcx, rdi; hModule
0x180017be8  call    WINRT_IMPL_GetProcAddress
0x180017bed  test    rax, rax
0x180017bf0  jz      short loc_180017C1A
0x180017bf2  mov     [rbp+var_48], 0
0x180017bfa  lea     rdx, [rbp+var_48]
0x180017bfe  mov     rcx, [r15]
0x180017c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c06  test    eax, eax
0x180017c08  jz      short loc_180017C27
0x180017c0a  cmp     [rbp+var_48], 0
0x180017c0f  jz      short loc_180017C1A
0x180017c11  lea     rcx, [rbp+var_48]
0x180017c15  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180017c1a  mov     rcx, rdi; hLibModule
0x180017c1d  call    WINRT_IMPL_FreeLibrary
0x180017c22  jmp     loc_180017B67
0x180017c27  mov     rax, [rbp+var_48]
0x180017c2b  mov     [rbp+var_48], 0
0x180017c33  mov     [r14], rax
0x180017c36  mov     dword ptr [rsi], 0
0x180017c3c  jmp     short loc_180017C4B
0x180017c3e  mov     rdx, [rbp+pperrinfo]; perrinfo
0x180017c42  xor     ecx, ecx; dwReserved
0x180017c44  call    SetErrorInfo_0
0x180017c49  mov     [rsi], ebx
0x180017c4b  lea     rcx, [rbp+lpLibFileName]
0x180017c4f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017c54  cmp     [rbp+pperrinfo], 0
0x180017c59  jz      short loc_180017C64
0x180017c5b  lea     rcx, [rbp+pperrinfo]
0x180017c5f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180017c64  mov     rax, rsi
0x180017c67  mov     rcx, [rbp+var_18]
0x180017c6b  xor     rcx, rsp; StackCookie
0x180017c6e  call    __security_check_cookie
0x180017c73  add     rsp, 68h
0x180017c77  pop     r15
0x180017c79  pop     r14
0x180017c7b  pop     rdi
0x180017c7c  pop     rsi
0x180017c7d  pop     rbx
0x180017c7e  pop     rbp
0x180017c7f  retn
```
