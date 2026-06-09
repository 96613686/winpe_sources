# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18001e998`
- end: `0x18001ec2c`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `660`
- prototype: ``
- caller_count: `6`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e5b8`
- `0x18001e618`
- `0x18001e678`
- `0x18001e6d8`
- `0x180026ea0`
- `0x18002cb08`

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
- `0x18001e998`
- `0x180024304`
- `0x1800248b0`
- `0x180035010`

## string_xrefs

- `0x18001e9fd`: `combase.dll`
- `0x18001eb26`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  __int64 v13; // rdx
  unsigned __int64 v14; // r8
  __int64 v15; // r14
  unsigned __int64 v16; // rcx
  __int64 v17; // rdi
  __int64 last_trivial_2; // rax
  __int64 v19; // rax
  const WCHAR *v20; // rax
  HMODULE v21; // rdi
  FARPROC v22; // rax
  bool v23; // zf
  unsigned int (__fastcall ***v25)(_QWORD, __int64, __int64); // [rsp+20h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-40h] BYREF
  _QWORD v27[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v28; // [rsp+40h] [rbp-28h]
  unsigned __int64 v29; // [rsp+48h] [rbp-20h]

  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, __int64))winrt_activation_handler)(v8, a3, a4);
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
      ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v25);
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
            if ( !((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v22)(
                    *a2,
                    &v25)
              && !(**v25)(v25, a3, a4) )
            {
              *a1 = 0;
              if ( v25 )
                winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v25);
              if ( v29 > 7 )
                std::_Deallocate<16>(v27[0], 2 * v29 + 2);
              v28 = 0;
              LOWORD(v27[0]) = 0;
              v23 = pperrinfo == 0;
              goto LABEL_30;
            }
            if ( v25 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v25);
          }
          WINRT_IMPL_FreeLibrary(v21);
        }
      }
      SetErrorInfo_0(0, pperrinfo);
      *a1 = ActivationFactory_0;
      if ( v29 > 7 )
        std::_Deallocate<16>(v27[0], 2 * v29 + 2);
      v28 = 0;
      LOWORD(v27[0]) = 0;
      v23 = pperrinfo == 0;
LABEL_30:
      v29 = 7;
      if ( !v23 )
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
0x18001e998  push    rbp
0x18001e99a  push    rbx
0x18001e99b  push    rsi
0x18001e99c  push    rdi
0x18001e99d  push    r12
0x18001e99f  push    r13
0x18001e9a1  push    r14
0x18001e9a3  push    r15
0x18001e9a5  mov     rbp, rsp
0x18001e9a8  sub     rsp, 68h
0x18001e9ac  mov     rax, cs:__security_cookie
0x18001e9b3  xor     rax, rsp
0x18001e9b6  mov     [rbp+var_18], rax
0x18001e9ba  mov     r13, r9
0x18001e9bd  mov     r12, r8
0x18001e9c0  mov     r15, rdx
0x18001e9c3  mov     rsi, rcx
0x18001e9c6  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18001e9cd  mov     r8, r9
0x18001e9d0  mov     rdx, r12
0x18001e9d3  mov     rcx, [r15]
0x18001e9d6  test    rax, rax
0x18001e9d9  jz      short loc_18001E9E7
0x18001e9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9e0  mov     [rsi], eax
0x18001e9e2  jmp     loc_18001EC0C
0x18001e9e7  call    RoGetActivationFactory_0
0x18001e9ec  mov     ebx, eax
0x18001e9ee  cmp     eax, 800401F0h
0x18001e9f3  jnz     short loc_18001EA49
0x18001e9f5  xor     edx, edx; hFile
0x18001e9f7  mov     r8d, 1000h; dwFlags
0x18001e9fd  lea     rcx, LibFileName; "combase.dll"
0x18001ea04  call    LoadLibraryExW_0
0x18001ea09  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18001ea10  mov     rcx, rax; hModule
0x18001ea13  call    WINRT_IMPL_GetProcAddress
0x18001ea18  test    rax, rax
0x18001ea1b  jnz     short loc_18001EA28
0x18001ea1d  mov     dword ptr [rsi], 800401F0h
0x18001ea23  jmp     loc_18001EC0C
0x18001ea28  mov     [rbp+var_48], 0
0x18001ea30  lea     rcx, [rbp+var_48]
0x18001ea34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea39  mov     r8, r13
0x18001ea3c  mov     rdx, r12
0x18001ea3f  mov     rcx, [r15]
0x18001ea42  call    RoGetActivationFactory_0
0x18001ea47  mov     ebx, eax
0x18001ea49  test    ebx, ebx
0x18001ea4b  jnz     short loc_18001EA54
0x18001ea4d  mov     [rsi], ebx
0x18001ea4f  jmp     loc_18001EC0C
0x18001ea54  mov     [rbp+pperrinfo], 0
0x18001ea5c  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18001ea60  xor     ecx, ecx; dwReserved
0x18001ea62  call    GetErrorInfo_0
0x18001ea67  mov     rdx, r15
0x18001ea6a  lea     rcx, [rbp+var_38]
0x18001ea6e  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x18001ea73  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001ea77  mov     rdx, [rbp+var_28]
0x18001ea7b  lea     rcx, [rbp+var_38]
0x18001ea7f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ea84  mov     r14, rax
0x18001ea87  test    rdx, rdx
0x18001ea8a  jz      loc_18001EBBF
0x18001ea90  lea     rcx, [rdx-1]
0x18001ea94  cmp     rcx, r8
0x18001ea97  cmovnb  rcx, r8
0x18001ea9b  add     rax, 2
0x18001ea9f  lea     rdi, [rax+rcx*2]
0x18001eaa3  mov     r8d, 2Eh ; '.'
0x18001eaa9  mov     rdx, rdi
0x18001eaac  mov     rcx, r14
0x18001eaaf  call    __std_find_last_trivial_2
0x18001eab4  cmp     rax, rdi
0x18001eab7  jz      loc_18001EBBF
0x18001eabd  sub     rax, r14
0x18001eac0  sar     rax, 1
0x18001eac3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001eac7  jz      loc_18001EBBF
0x18001eacd  mov     rdx, rax
0x18001ead0  lea     rcx, [rbp+var_38]
0x18001ead4  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001ead9  lea     rdx, aDll; ".dll"
0x18001eae0  lea     rcx, [rbp+var_38]
0x18001eae4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001eae9  lea     rcx, [rbp+var_38]
0x18001eaed  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001eaf2  mov     rcx, rax; lpLibFileName
0x18001eaf5  xor     edx, edx; hFile
0x18001eaf7  mov     r8d, 1000h; dwFlags
0x18001eafd  call    LoadLibraryExW_0
0x18001eb02  mov     rdi, rax
0x18001eb05  mov     rdx, [rbp+var_28]
0x18001eb09  add     rdx, 0FFFFFFFFFFFFFFFCh
0x18001eb0d  lea     rcx, [rbp+var_38]
0x18001eb11  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001eb16  xor     r14d, r14d
0x18001eb19  test    rdi, rdi
0x18001eb1c  lea     r8, [r14-1]
0x18001eb20  jz      loc_18001EA77
0x18001eb26  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x18001eb2d  mov     rcx, rdi; hModule
0x18001eb30  call    WINRT_IMPL_GetProcAddress
0x18001eb35  test    rax, rax
0x18001eb38  jz      short loc_18001EB76
0x18001eb3a  mov     [rbp+var_48], r14
0x18001eb3e  lea     rdx, [rbp+var_48]
0x18001eb42  mov     rcx, [r15]
0x18001eb45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb4a  test    eax, eax
0x18001eb4c  jnz     short loc_18001EB67
0x18001eb4e  mov     rcx, [rbp+var_48]
0x18001eb52  mov     rax, [rcx]
0x18001eb55  mov     r8, r13
0x18001eb58  mov     rdx, r12
0x18001eb5b  mov     rax, [rax]
0x18001eb5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb63  test    eax, eax
0x18001eb65  jz      short loc_18001EB83
0x18001eb67  cmp     [rbp+var_48], r14
0x18001eb6b  jz      short loc_18001EB76
0x18001eb6d  lea     rcx, [rbp+var_48]
0x18001eb71  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001eb76  mov     rcx, rdi; hLibModule
0x18001eb79  call    WINRT_IMPL_FreeLibrary
0x18001eb7e  jmp     loc_18001EA73
0x18001eb83  mov     [rsi], r14d
0x18001eb86  cmp     [rbp+var_48], r14
0x18001eb8a  jz      short loc_18001EB95
0x18001eb8c  lea     rcx, [rbp+var_48]
0x18001eb90  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001eb95  mov     rdx, [rbp+var_20]
0x18001eb99  cmp     rdx, 7
0x18001eb9d  jbe     short loc_18001EBB0
0x18001eb9f  lea     rdx, ds:2[rdx*2]
0x18001eba7  mov     rcx, [rbp+var_38]
0x18001ebab  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001ebb0  mov     [rbp+var_28], r14
0x18001ebb4  mov     word ptr [rbp+var_38], r14w
0x18001ebb9  cmp     [rbp+pperrinfo], r14
0x18001ebbd  jmp     short loc_18001EBF9
0x18001ebbf  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18001ebc3  xor     ecx, ecx; dwReserved
0x18001ebc5  call    SetErrorInfo_0
0x18001ebca  mov     [rsi], ebx
0x18001ebcc  mov     rdx, [rbp+var_20]
0x18001ebd0  cmp     rdx, 7
0x18001ebd4  jbe     short loc_18001EBE7
0x18001ebd6  lea     rdx, ds:2[rdx*2]
0x18001ebde  mov     rcx, [rbp+var_38]
0x18001ebe2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001ebe7  mov     [rbp+var_28], 0
0x18001ebef  xor     eax, eax
0x18001ebf1  mov     word ptr [rbp+var_38], ax
0x18001ebf5  cmp     [rbp+pperrinfo], rax
0x18001ebf9  mov     [rbp+var_20], 7
0x18001ec01  jz      short loc_18001EC0C
0x18001ec03  lea     rcx, [rbp+pperrinfo]
0x18001ec07  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ec0c  mov     rax, rsi
0x18001ec0f  mov     rcx, [rbp+var_18]
0x18001ec13  xor     rcx, rsp; StackCookie
0x18001ec16  call    __security_check_cookie
0x18001ec1b  add     rsp, 68h
0x18001ec1f  pop     r15
0x18001ec21  pop     r14
0x18001ec23  pop     r13
0x18001ec25  pop     r12
0x18001ec27  pop     rdi
0x18001ec28  pop     rsi
0x18001ec29  pop     rbx
0x18001ec2a  pop     rbp
0x18001ec2b  retn
```
