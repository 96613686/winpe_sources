# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x180004e3c`
- end: `0x1800050b3`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `631`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008efc`

## callees

- `0x1800029b0`
- `0x180002dc0`
- `0x180003ad0`
- `0x180003b9c`
- `0x180003bcc`
- `0x180003dff`
- `0x180003e0b`
- `0x180003e47`
- `0x180004a68`
- `0x180004ad8`
- `0x180004e3c`
- `0x180005ebc`
- `0x180008a80`
- `0x180008adc`
- `0x1800094bc`
- `0x180009918`
- `0x18002b010`

## string_xrefs

- `0x180004ea5`: `combase.dll`
- `0x180004fee`: `DllGetActivationFactory`

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
  _QWORD v25[2]; // [rsp+20h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+30h] [rbp-38h] BYREF
  __int128 v27; // [rsp+38h] [rbp-30h] BYREF
  __int64 v28; // [rsp+48h] [rbp-20h]
  __int64 v29; // [rsp+50h] [rbp-18h]

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
    v25[0] = 0;
    ((void (__fastcall *)(_QWORD *))ProcAddress)(v25);
    ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
  }
  if ( !ActivationFactory_0 )
  {
    *a1 = 0;
    return a1;
  }
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  v27 = 0;
  v28 = 0;
  v29 = 0;
  winrt::hstring::operator std::basic_string_view<unsigned short>(a2, v25);
  std::wstring::_Construct<1,unsigned short const *>(&v27, v25[0], v25[1]);
  while ( 1 )
  {
    do
    {
      v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v27);
      v15 = v12;
      if ( !v13 )
        goto LABEL_25;
      v16 = v13 - 1;
      if ( v13 - 1 >= v14 )
        v16 = v14;
      v17 = v12 + 2 + 2 * v16;
      last_trivial_2 = _std_find_last_trivial_2(v12, v17, 46);
      if ( last_trivial_2 == v17 || (v19 = (last_trivial_2 - v15) >> 1, v19 == -1) )
      {
LABEL_25:
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        std::wstring::_Tidy_deallocate(&v27);
        v23 = pperrinfo == 0;
        goto LABEL_26;
      }
      std::wstring::resize(&v27, v19);
      std::wstring::_Append<unsigned short>(&v27, L".dll", 4);
      v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v27);
      v21 = LoadLibraryExW_0(v20, 0, 0x1000u);
      std::wstring::resize(&v27, v28 - 4);
    }
    while ( !v21 );
    v22 = WINRT_IMPL_GetProcAddress(v21, "DllGetActivationFactory");
    if ( v22 )
      break;
LABEL_21:
    WINRT_IMPL_FreeLibrary(v21);
  }
  v25[0] = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, _QWORD *))v22)(*a2, v25)
    || (**(unsigned int (__fastcall ***)(_QWORD, __int64, __int64))v25[0])(v25[0], a3, a4) )
  {
    if ( v25[0] )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v25);
    goto LABEL_21;
  }
  *a1 = 0;
  if ( v25[0] )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v25);
  std::wstring::_Tidy_deallocate(&v27);
  v23 = pperrinfo == 0;
LABEL_26:
  if ( !v23 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x180004e3c  push    rbp
0x180004e3e  push    rbx
0x180004e3f  push    rsi
0x180004e40  push    rdi
0x180004e41  push    r12
0x180004e43  push    r13
0x180004e45  push    r14
0x180004e47  push    r15
0x180004e49  mov     rbp, rsp
0x180004e4c  sub     rsp, 68h
0x180004e50  mov     rax, cs:__security_cookie
0x180004e57  xor     rax, rsp
0x180004e5a  mov     [rbp+var_10], rax
0x180004e5e  mov     r12, r9
0x180004e61  mov     r15, r8
0x180004e64  mov     r13, rdx
0x180004e67  mov     rsi, rcx
0x180004e6a  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180004e71  xor     r14d, r14d
0x180004e74  mov     r8, r9
0x180004e77  mov     rdx, r15
0x180004e7a  mov     rcx, [r13+0]
0x180004e7e  test    rax, rax
0x180004e81  jz      short loc_180004E8F
0x180004e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e88  mov     [rsi], eax
0x180004e8a  jmp     loc_180005093
0x180004e8f  call    RoGetActivationFactory_0
0x180004e94  mov     ebx, eax
0x180004e96  cmp     eax, 800401F0h
0x180004e9b  jnz     short loc_180004EEE
0x180004e9d  xor     edx, edx; hFile
0x180004e9f  mov     r8d, 1000h; dwFlags
0x180004ea5  lea     rcx, LibFileName; "combase.dll"
0x180004eac  call    LoadLibraryExW_0
0x180004eb1  lea     rdx, ProcName; "CoIncrementMTAUsage"
0x180004eb8  mov     rcx, rax; hModule
0x180004ebb  call    WINRT_IMPL_GetProcAddress
0x180004ec0  test    rax, rax
0x180004ec3  jnz     short loc_180004ED0
0x180004ec5  mov     dword ptr [rsi], 800401F0h
0x180004ecb  jmp     loc_180005093
0x180004ed0  mov     [rbp+var_48], r14
0x180004ed4  lea     rcx, [rbp+var_48]
0x180004ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004edd  mov     r8, r12
0x180004ee0  mov     rdx, r15
0x180004ee3  mov     rcx, [r13+0]
0x180004ee7  call    RoGetActivationFactory_0
0x180004eec  mov     ebx, eax
0x180004eee  test    ebx, ebx
0x180004ef0  jnz     short loc_180004EFA
0x180004ef2  mov     [rsi], r14d
0x180004ef5  jmp     loc_180005093
0x180004efa  mov     [rbp+pperrinfo], r14
0x180004efe  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180004f02  xor     ecx, ecx; dwReserved
0x180004f04  call    GetErrorInfo_0
0x180004f09  xorps   xmm0, xmm0
0x180004f0c  movups  [rbp+var_30], xmm0
0x180004f10  mov     [rbp+var_20], r14
0x180004f14  mov     [rbp+var_18], r14
0x180004f18  lea     rdx, [rbp+var_48]
0x180004f1c  mov     rcx, r13
0x180004f1f  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x180004f24  mov     r8, [rbp+var_40]
0x180004f28  mov     rdx, [rbp+var_48]
0x180004f2c  lea     rcx, [rbp+var_30]
0x180004f30  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180004f35  or      r8, 0FFFFFFFFFFFFFFFFh
0x180004f39  mov     rdx, [rbp+var_20]
0x180004f3d  lea     rcx, [rbp+var_30]
0x180004f41  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180004f46  mov     r14, rax
0x180004f49  test    rdx, rdx
0x180004f4c  jz      loc_18000506D
0x180004f52  lea     rcx, [rdx-1]
0x180004f56  cmp     rcx, r8
0x180004f59  cmovnb  rcx, r8
0x180004f5d  add     rax, 2
0x180004f61  lea     rdi, [rax+rcx*2]
0x180004f65  mov     r8d, 2Eh ; '.'
0x180004f6b  mov     rdx, rdi
0x180004f6e  mov     rcx, r14
0x180004f71  call    __std_find_last_trivial_2
0x180004f76  cmp     rax, rdi
0x180004f79  jz      loc_18000506D
0x180004f7f  sub     rax, r14
0x180004f82  sar     rax, 1
0x180004f85  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004f89  jz      loc_18000506D
0x180004f8f  mov     rdx, rax
0x180004f92  lea     rcx, [rbp+var_30]
0x180004f96  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180004f9b  mov     r8d, 4
0x180004fa1  lea     rdx, aDll; ".dll"
0x180004fa8  lea     rcx, [rbp+var_30]
0x180004fac  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180004fb1  lea     rcx, [rbp+var_30]
0x180004fb5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180004fba  mov     rcx, rax; lpLibFileName
0x180004fbd  xor     edx, edx; hFile
0x180004fbf  mov     r8d, 1000h; dwFlags
0x180004fc5  call    LoadLibraryExW_0
0x180004fca  mov     rdi, rax
0x180004fcd  mov     rdx, [rbp+var_20]
0x180004fd1  add     rdx, 0FFFFFFFFFFFFFFFCh
0x180004fd5  lea     rcx, [rbp+var_30]
0x180004fd9  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180004fde  xor     r14d, r14d
0x180004fe1  test    rdi, rdi
0x180004fe4  lea     r8, [r14-1]
0x180004fe8  jz      loc_180004F39
0x180004fee  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x180004ff5  mov     rcx, rdi; hModule
0x180004ff8  call    WINRT_IMPL_GetProcAddress
0x180004ffd  test    rax, rax
0x180005000  jz      short loc_18000503F
0x180005002  mov     [rbp+var_48], r14
0x180005006  lea     rdx, [rbp+var_48]
0x18000500a  mov     rcx, [r13+0]
0x18000500e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005013  test    eax, eax
0x180005015  jnz     short loc_180005030
0x180005017  mov     rcx, [rbp+var_48]
0x18000501b  mov     rax, [rcx]
0x18000501e  mov     r8, r12
0x180005021  mov     rdx, r15
0x180005024  mov     rax, [rax]
0x180005027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000502c  test    eax, eax
0x18000502e  jz      short loc_18000504C
0x180005030  cmp     [rbp+var_48], r14
0x180005034  jz      short loc_18000503F
0x180005036  lea     rcx, [rbp+var_48]
0x18000503a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000503f  mov     rcx, rdi; hLibModule
0x180005042  call    WINRT_IMPL_FreeLibrary
0x180005047  jmp     loc_180004F35
0x18000504c  mov     [rsi], r14d
0x18000504f  cmp     [rbp+var_48], r14
0x180005053  jz      short loc_18000505E
0x180005055  lea     rcx, [rbp+var_48]
0x180005059  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000505e  lea     rcx, [rbp+var_30]
0x180005062  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180005067  cmp     [rbp+pperrinfo], r14
0x18000506b  jmp     short loc_180005088
0x18000506d  mov     rdx, [rbp+pperrinfo]; perrinfo
0x180005071  xor     ecx, ecx; dwReserved
0x180005073  call    SetErrorInfo_0
0x180005078  mov     [rsi], ebx
0x18000507a  lea     rcx, [rbp+var_30]
0x18000507e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180005083  cmp     [rbp+pperrinfo], 0
0x180005088  jz      short loc_180005093
0x18000508a  lea     rcx, [rbp+pperrinfo]
0x18000508e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180005093  mov     rax, rsi
0x180005096  mov     rcx, [rbp+var_10]
0x18000509a  xor     rcx, rsp; StackCookie
0x18000509d  call    __security_check_cookie
0x1800050a2  add     rsp, 68h
0x1800050a6  pop     r15
0x1800050a8  pop     r14
0x1800050aa  pop     r13
0x1800050ac  pop     r12
0x1800050ae  pop     rdi
0x1800050af  pop     rsi
0x1800050b0  pop     rbx
0x1800050b1  pop     rbp
0x1800050b2  retn
```
