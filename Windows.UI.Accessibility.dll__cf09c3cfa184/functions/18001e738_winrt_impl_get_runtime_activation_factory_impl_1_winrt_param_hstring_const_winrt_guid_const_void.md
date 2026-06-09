# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18001e738`
- end: `0x18001e990`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `600`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e558`

## callees

- `0x180003980`
- `0x180004625`
- `0x180004655`
- `0x180004661`
- `0x180004bf0`
- `0x180005109`
- `0x1800051f4`
- `0x180005242`
- `0x1800072d8`
- `0x180010dec`
- `0x1800166d4`
- `0x18001a7ac`
- `0x18001e738`
- `0x180024304`
- `0x1800248b0`
- `0x180035010`

## string_xrefs

- `0x18001e79c`: `combase.dll`
- `0x18001e8c6`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<1>(_DWORD *a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  __int64 v13; // rdx
  unsigned __int64 v14; // r8
  __int64 v15; // r15
  unsigned __int64 v16; // rcx
  __int64 v17; // rdi
  __int64 last_trivial_2; // rax
  __int64 v19; // rax
  const WCHAR *v20; // rax
  HMODULE v21; // rdi
  FARPROC v22; // rax
  __int64 v23; // rax
  __int64 v25; // [rsp+20h] [rbp-40h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-38h] BYREF
  _QWORD v27[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v28; // [rsp+40h] [rbp-20h]
  unsigned __int64 v29; // [rsp+48h] [rbp-18h]

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
      v25 = 0;
      ((void (__fastcall *)(__int64 *))ProcAddress)(&v25);
      ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
    }
    if ( ActivationFactory_0 )
    {
      pperrinfo = 0;
      GetErrorInfo_0(0, &pperrinfo);
      std::wstring::wstring(v27, a2);
      while ( 1 )
      {
        v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
        v15 = v12;
        if ( !v13 )
          break;
        v16 = v13 - 1;
        if ( v13 - 1 >= v14 )
          v16 = v14;
        v17 = v12 + 2 + 2 * v16;
        last_trivial_2 = _std_find_last_trivial_2(v12, v17, 46);
        if ( last_trivial_2 == v17 )
          break;
        v19 = (last_trivial_2 - v15) >> 1;
        if ( v19 == -1 )
          break;
        std::wstring::resize(v27, v19);
        std::wstring::append(v27, L".dll");
        v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
        v21 = LoadLibraryExW_0(v20, 0, 0x1000u);
        std::wstring::resize(v27, v28 - 4);
        if ( v21 )
        {
          v22 = WINRT_IMPL_GetProcAddress(v21, "DllGetActivationFactory");
          if ( v22 )
          {
            v25 = 0;
            if ( !((unsigned int (__fastcall *)(_QWORD, __int64 *))v22)(*a2, &v25) )
            {
              v23 = v25;
              v25 = 0;
              *a4 = v23;
              *a1 = 0;
              goto LABEL_23;
            }
            if ( v25 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v25);
          }
          WINRT_IMPL_FreeLibrary(v21);
        }
      }
      SetErrorInfo_0(0, pperrinfo);
      *a1 = ActivationFactory_0;
LABEL_23:
      if ( v29 > 7 )
        std::_Deallocate<16>(v27[0], 2 * v29 + 2);
      LOWORD(v27[0]) = 0;
      v29 = 7;
      v28 = 0;
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
0x18001e738  push    rbp
0x18001e73a  push    rbx
0x18001e73b  push    rsi
0x18001e73c  push    rdi
0x18001e73d  push    r12
0x18001e73f  push    r14
0x18001e741  push    r15
0x18001e743  mov     rbp, rsp
0x18001e746  sub     rsp, 60h
0x18001e74a  mov     rax, cs:__security_cookie
0x18001e751  xor     rax, rsp
0x18001e754  mov     [rbp+var_10], rax
0x18001e758  mov     r14, r9
0x18001e75b  mov     rdi, r8
0x18001e75e  mov     r12, rdx
0x18001e761  mov     rsi, rcx
0x18001e764  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18001e76b  mov     r8, r9
0x18001e76e  mov     rdx, rdi
0x18001e771  mov     rcx, [r12]
0x18001e775  test    rax, rax
0x18001e778  jz      short loc_18001E786
0x18001e77a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e77f  mov     [rsi], eax
0x18001e781  jmp     loc_18001E972
0x18001e786  call    RoGetActivationFactory_0
0x18001e78b  mov     ebx, eax
0x18001e78d  cmp     eax, 800401F0h
0x18001e792  jnz     short loc_18001E7E9
0x18001e794  xor     edx, edx; hFile
0x18001e796  mov     r8d, 1000h; dwFlags
0x18001e79c  lea     rcx, LibFileName; "combase.dll"
0x18001e7a3  call    LoadLibraryExW_0
0x18001e7a8  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18001e7af  mov     rcx, rax; hModule
0x18001e7b2  call    WINRT_IMPL_GetProcAddress
0x18001e7b7  test    rax, rax
0x18001e7ba  jnz     short loc_18001E7C7
0x18001e7bc  mov     dword ptr [rsi], 800401F0h
0x18001e7c2  jmp     loc_18001E972
0x18001e7c7  mov     [rbp+var_40], 0
0x18001e7cf  lea     rcx, [rbp+var_40]
0x18001e7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7d8  mov     r8, r14
0x18001e7db  mov     rdx, rdi
0x18001e7de  mov     rcx, [r12]
0x18001e7e2  call    RoGetActivationFactory_0
0x18001e7e7  mov     ebx, eax
0x18001e7e9  test    ebx, ebx
0x18001e7eb  jnz     short loc_18001E7F4
0x18001e7ed  mov     [rsi], ebx
0x18001e7ef  jmp     loc_18001E972
0x18001e7f4  mov     [rbp+pperrinfo], 0
0x18001e7fc  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18001e800  xor     ecx, ecx; dwReserved
0x18001e802  call    GetErrorInfo_0
0x18001e807  mov     rdx, r12
0x18001e80a  lea     rcx, [rbp+var_30]
0x18001e80e  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x18001e813  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001e817  mov     rdx, [rbp+var_20]
0x18001e81b  lea     rcx, [rbp+var_30]
0x18001e81f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001e824  mov     r15, rax
0x18001e827  test    rdx, rdx
0x18001e82a  jz      loc_18001E929
0x18001e830  lea     rcx, [rdx-1]
0x18001e834  cmp     rcx, r8
0x18001e837  cmovnb  rcx, r8
0x18001e83b  add     rax, 2
0x18001e83f  lea     rdi, [rax+rcx*2]
0x18001e843  mov     r8d, 2Eh ; '.'
0x18001e849  mov     rdx, rdi
0x18001e84c  mov     rcx, r15
0x18001e84f  call    __std_find_last_trivial_2
0x18001e854  cmp     rax, rdi
0x18001e857  jz      loc_18001E929
0x18001e85d  sub     rax, r15
0x18001e860  sar     rax, 1
0x18001e863  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e867  jz      loc_18001E929
0x18001e86d  mov     rdx, rax
0x18001e870  lea     rcx, [rbp+var_30]
0x18001e874  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001e879  lea     rdx, aDll; ".dll"
0x18001e880  lea     rcx, [rbp+var_30]
0x18001e884  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001e889  lea     rcx, [rbp+var_30]
0x18001e88d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001e892  mov     rcx, rax; lpLibFileName
0x18001e895  xor     edx, edx; hFile
0x18001e897  mov     r8d, 1000h; dwFlags
0x18001e89d  call    LoadLibraryExW_0
0x18001e8a2  mov     rdi, rax
0x18001e8a5  mov     rdx, [rbp+var_20]
0x18001e8a9  add     rdx, 0FFFFFFFFFFFFFFFCh
0x18001e8ad  lea     rcx, [rbp+var_30]
0x18001e8b1  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001e8b6  test    rdi, rdi
0x18001e8b9  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18001e8c0  jz      loc_18001E817
0x18001e8c6  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x18001e8cd  mov     rcx, rdi; hModule
0x18001e8d0  call    WINRT_IMPL_GetProcAddress
0x18001e8d5  test    rax, rax
0x18001e8d8  jnz     short loc_18001E8E7
0x18001e8da  mov     rcx, rdi; hLibModule
0x18001e8dd  call    WINRT_IMPL_FreeLibrary
0x18001e8e2  jmp     loc_18001E813
0x18001e8e7  mov     [rbp+var_40], 0
0x18001e8ef  lea     rdx, [rbp+var_40]
0x18001e8f3  mov     rcx, [r12]
0x18001e8f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8fc  test    eax, eax
0x18001e8fe  jz      short loc_18001E912
0x18001e900  cmp     [rbp+var_40], 0
0x18001e905  jz      short loc_18001E8DA
0x18001e907  lea     rcx, [rbp+var_40]
0x18001e90b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e910  jmp     short loc_18001E8DA
0x18001e912  mov     rax, [rbp+var_40]
0x18001e916  mov     [rbp+var_40], 0
0x18001e91e  mov     [r14], rax
0x18001e921  mov     dword ptr [rsi], 0
0x18001e927  jmp     short loc_18001E936
0x18001e929  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18001e92d  xor     ecx, ecx; dwReserved
0x18001e92f  call    SetErrorInfo_0
0x18001e934  mov     [rsi], ebx
0x18001e936  mov     rdx, [rbp+var_18]
0x18001e93a  cmp     rdx, 7
0x18001e93e  jbe     short loc_18001E951
0x18001e940  lea     rdx, ds:2[rdx*2]
0x18001e948  mov     rcx, [rbp+var_30]
0x18001e94c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e951  xor     eax, eax
0x18001e953  cmp     [rbp+pperrinfo], rax
0x18001e957  mov     word ptr [rbp+var_30], ax
0x18001e95b  mov     [rbp+var_18], 7
0x18001e963  mov     [rbp+var_20], rax
0x18001e967  jz      short loc_18001E972
0x18001e969  lea     rcx, [rbp+pperrinfo]
0x18001e96d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e972  mov     rax, rsi
0x18001e975  mov     rcx, [rbp+var_10]
0x18001e979  xor     rcx, rsp; StackCookie
0x18001e97c  call    __security_check_cookie
0x18001e981  add     rsp, 60h
0x18001e985  pop     r15
0x18001e987  pop     r14
0x18001e989  pop     r12
0x18001e98b  pop     rdi
0x18001e98c  pop     rsi
0x18001e98d  pop     rbx
0x18001e98e  pop     rbp
0x18001e98f  retn
```
