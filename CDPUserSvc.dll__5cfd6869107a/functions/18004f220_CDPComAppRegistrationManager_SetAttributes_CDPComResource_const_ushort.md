# CDPComAppRegistrationManager::SetAttributes(CDPComResource const *,ushort)

- ea: `0x18004f220`
- end: `0x18004f5e0`
- name: `?SetAttributes@CDPComAppRegistrationManager@@UEAAJPEBUCDPComResource@@G@Z`
- size: `960`
- prototype: `__int64 __fastcall(CDPComAppRegistrationManager *__hidden this, const struct CDPComResource *, unsigned __int16)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002a4c`
- `0x180003678`
- `0x180004a58`
- `0x180005c64`
- `0x18000ecb8`
- `0x180014aa0`
- `0x18001d044`
- `0x18002c570`
- `0x18003ff10`
- `0x1800410f0`
- `0x18004e518`
- `0x18004e73c`
- `0x18004e768`
- `0x18004e878`
- `0x18004f220`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004f4b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004f4b2`
- `cdp!CDPCreateResourceCollection` at `0x18004f412`
- `cdp!CDPCreateResourceCollection` at `0x18004f412`

## string_xrefs

- `0x18004f2b1`: `com.microsoft.r.cdp.attribute`
- `0x18004f270`: `..\cdpcomappregistrationmanager.cpp`
- `0x18004f441`: `..\cdpcomappregistrationmanager.cpp`
- `0x18004f4f0`: `..\cdpcomappregistrationmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall CDPComAppRegistrationManager::SetAttributes(
        CDPComAppRegistrationManager *this,
        const struct CDPComResource *a2,
        unsigned __int16 a3)
{
  __int64 v3; // r12
  __int64 v6; // rax
  __int64 v7; // rsi
  __int64 v8; // rax
  unsigned __int16 i; // di
  __int64 v10; // rbx
  __int64 v11; // rsi
  _QWORD *v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // rsi
  _QWORD *v15; // rdi
  int v16; // ebx
  int v17; // edx
  int v18; // ecx
  int v19; // eax
  int v20; // edx
  int v21; // ecx
  unsigned int v22; // [rsp+30h] [rbp-F8h] BYREF
  CDPComAppRegistrationManager *v23; // [rsp+38h] [rbp-F0h] BYREF
  __int64 v24; // [rsp+40h] [rbp-E8h] BYREF
  const char *v25; // [rsp+48h] [rbp-E0h] BYREF
  __int64 v26; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v27; // [rsp+58h] [rbp-D0h]
  _QWORD v28[3]; // [rsp+68h] [rbp-C0h] BYREF
  _QWORD v29[3]; // [rsp+80h] [rbp-A8h] BYREF
  _QWORD v30[3]; // [rsp+98h] [rbp-90h] BYREF
  _QWORD v31[3]; // [rsp+B0h] [rbp-78h] BYREF
  __int64 *v32; // [rsp+C8h] [rbp-60h] BYREF
  __int64 v33; // [rsp+D0h] [rbp-58h] BYREF
  char v34; // [rsp+D8h] [rbp-50h]

  v3 = a3;
  v23 = this;
  if ( a2 )
  {
    v24 = 0;
    std::vector<std::string>::vector<std::string>(v28, a3);
    std::vector<std::string>::vector<std::string>(&v26, v3);
    v25 = "com.microsoft.r.cdp.attribute";
    std::vector<char *>::vector<char *>(v31, v3, &v25);
    for ( i = 0; i < (unsigned __int16)v3; ++i )
    {
      v6 = std::string::string((__int64)&v32, *((_QWORD *)a2 + 5 * i));
      v7 = 32LL * i;
      std::string::operator=(v7 + v28[0], v6);
      std::string::_Tidy_deallocate(&v32);
      v8 = std::string::string((__int64)&v32, *((_QWORD *)a2 + 5 * i + 2));
      std::string::operator=(v7 + v26, v8);
      std::string::_Tidy_deallocate(&v32);
    }
    std::vector<char *>::vector<char *>(v30, v3);
    std::vector<char *>::vector<char *>(v29, v3);
    v10 = v28[0];
    v11 = v28[1];
    v12 = (_QWORD *)v30[0];
    while ( v10 != v11 )
    {
      *v12 = std::_String_val<std::_Simple_types<char>>::_Myptr(v10);
      v10 += 32;
      ++v12;
    }
    v13 = v26;
    v14 = v27;
    v15 = (_QWORD *)v29[0];
    if ( v26 != v27 )
    {
      do
      {
        *v15 = std::_String_val<std::_Simple_types<char>>::_Myptr(v13);
        v13 += 32;
        ++v15;
      }
      while ( v13 != v14 );
      v15 = (_QWORD *)v29[0];
    }
    v32 = &v24;
    v33 = 0;
    v34 = 1;
    v16 = CDPCreateResourceCollection(v30[0], v15, v31[0], (unsigned __int16)v3, &v33);
    wil::details::out_param_t<Microsoft::WRL::ComPtr<ICDPResourceCollection>>::~out_param_t<Microsoft::WRL::ComPtr<ICDPResourceCollection>>(&v32);
    if ( v16 >= 0 )
    {
      AcquireSRWLockExclusive((PSRWLOCK)v23 + 4);
      v25 = (char *)v23 + 32;
      v19 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v23 + 3) + 32LL))(*((_QWORD *)v23 + 3), v24);
      if ( v19 >= 0 )
      {
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v25);
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(v29);
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(v30);
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(v31);
        std::vector<std::string>::_Tidy(&v26);
        std::vector<std::string>::_Tidy(v28);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
        return 0;
      }
      else
      {
        v22 = v19;
        LODWORD(v23) = 77;
        Log<long &,char const (&)[36],int>(
          v21,
          v20,
          (unsigned int)&v22,
          (unsigned int)"..\\cdpcomappregistrationmanager.cpp",
          (__int64)&v23);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v25);
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(v29);
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(v30);
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(v31);
        std::vector<std::string>::_Tidy(&v26);
        std::vector<std::string>::_Tidy(v28);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
        return v22;
      }
    }
    else
    {
      v22 = v16;
      LODWORD(v23) = 74;
      Log<long &,char const (&)[36],int>(
        v18,
        v17,
        (unsigned int)&v22,
        (unsigned int)"..\\cdpcomappregistrationmanager.cpp",
        (__int64)&v23);
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(v29);
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(v30);
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(v31);
      std::vector<std::string>::_Tidy(&v26);
      std::vector<std::string>::_Tidy(v28);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      return v22;
    }
  }
  else
  {
    v22 = -2147024809;
    LODWORD(v23) = 40;
    Log<long &,char const (&)[36],int>(
      (_DWORD)this,
      0,
      (unsigned int)&v22,
      (unsigned int)"..\\cdpcomappregistrationmanager.cpp",
      (__int64)&v23);
    return v22;
  }
}

```

## disassembly

```asm
0x18004f220  push    rbx
0x18004f222  push    rsi
0x18004f223  push    rdi
0x18004f224  push    r12
0x18004f226  push    r13
0x18004f228  push    r14
0x18004f22a  push    r15
0x18004f22c  sub     rsp, 0F0h
0x18004f233  mov     rax, cs:__security_cookie
0x18004f23a  xor     rax, rsp
0x18004f23d  mov     [rsp+128h+var_40], rax
0x18004f245  movzx   r12d, r8w
0x18004f249  mov     r14, rdx
0x18004f24c  mov     [rsp+128h+var_F0], rcx
0x18004f251  test    rdx, rdx
0x18004f254  jnz     short loc_18004F28A
0x18004f256  mov     [rsp+128h+var_F8], 80070057h
0x18004f25e  mov     dword ptr [rsp+128h+var_F0], 28h ; '('
0x18004f266  lea     rax, [rsp+128h+var_F0]
0x18004f26b  mov     [rsp+128h+var_108], rax
0x18004f270  lea     r9, aCdpcomappregis; "..\\cdpcomappregistrationmanager.cpp"
0x18004f277  lea     r8, [rsp+128h+var_F8]
0x18004f27c  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x18004f281  mov     eax, [rsp+128h+var_F8]
0x18004f285  jmp     loc_18004F5BD
0x18004f28a  xor     r15d, r15d
0x18004f28d  mov     [rsp+128h+var_E8], r15
0x18004f292  mov     rbx, r12
0x18004f295  mov     rdx, r12
0x18004f298  lea     rcx, [rsp+128h+var_C0]
0x18004f29d  call    ??0?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@QEAA@_KAEBV?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@@Z; std::vector<std::string>::vector<std::string>(unsigned __int64,std::allocator<std::string> const &)
0x18004f2a2  nop
0x18004f2a3  mov     rdx, rbx
0x18004f2a6  lea     rcx, [rsp+128h+var_D8]
0x18004f2ab  call    ??0?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@QEAA@_KAEBV?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@@Z; std::vector<std::string>::vector<std::string>(unsigned __int64,std::allocator<std::string> const &)
0x18004f2b0  nop
0x18004f2b1  lea     rax, aComMicrosoftRC; "com.microsoft.r.cdp.attribute"
0x18004f2b8  mov     [rsp+128h+var_E0], rax
0x18004f2bd  lea     r8, [rsp+128h+var_E0]
0x18004f2c2  mov     rdx, rbx
0x18004f2c5  lea     rcx, [rsp+128h+var_78]
0x18004f2cd  call    ??$?0V?$allocator@PEAD@std@@$0A@@?$vector@PEADV?$allocator@PEAD@std@@@std@@QEAA@_KAEBQEADAEBV?$allocator@PEAD@1@@Z; std::vector<char *>::vector<char *>(unsigned __int64,char * const &,std::allocator<char *> const &)
0x18004f2d2  nop
0x18004f2d3  xor     edi, edi
0x18004f2d5  cmp     di, r12w
0x18004f2d9  jnb     short loc_18004F348
0x18004f2db  movzx   esi, di
0x18004f2de  lea     r13, [rsi+rsi*4]
0x18004f2e2  mov     rdx, [r14+r13*8]
0x18004f2e6  lea     rcx, [rsp+128h+var_60]
0x18004f2ee  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004f2f3  mov     rdx, rax
0x18004f2f6  shl     rsi, 5
0x18004f2fa  mov     rcx, [rsp+128h+var_C0]
0x18004f2ff  add     rcx, rsi
0x18004f302  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18004f307  lea     rcx, [rsp+128h+var_60]
0x18004f30f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004f314  mov     rdx, [r14+r13*8+10h]
0x18004f319  lea     rcx, [rsp+128h+var_60]
0x18004f321  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004f326  mov     rdx, rax
0x18004f329  mov     rcx, [rsp+128h+var_D8]
0x18004f32e  add     rcx, rsi
0x18004f331  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18004f336  lea     rcx, [rsp+128h+var_60]
0x18004f33e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004f343  inc     di
0x18004f346  jmp     short loc_18004F2D5
0x18004f348  mov     rdx, rbx
0x18004f34b  lea     rcx, [rsp+128h+var_90]
0x18004f353  call    ??0?$vector@PEADV?$allocator@PEAD@std@@@std@@QEAA@_KAEBV?$allocator@PEAD@1@@Z; std::vector<char *>::vector<char *>(unsigned __int64,std::allocator<char *> const &)
0x18004f358  nop
0x18004f359  mov     rdx, rbx
0x18004f35c  lea     rcx, [rsp+128h+var_A8]
0x18004f364  call    ??0?$vector@PEADV?$allocator@PEAD@std@@@std@@QEAA@_KAEBV?$allocator@PEAD@1@@Z; std::vector<char *>::vector<char *>(unsigned __int64,std::allocator<char *> const &)
0x18004f369  nop
0x18004f36a  mov     rbx, [rsp+128h+var_C0]
0x18004f36f  mov     rsi, [rsp+128h+var_B8]
0x18004f374  mov     rdi, [rsp+128h+var_90]
0x18004f37c  jmp     short loc_18004F391
0x18004f37e  mov     rcx, rbx
0x18004f381  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18004f386  mov     [rdi], rax
0x18004f389  add     rbx, 20h ; ' '
0x18004f38d  lea     rdi, [rdi+8]
0x18004f391  cmp     rbx, rsi
0x18004f394  jnz     short loc_18004F37E
0x18004f396  mov     rbx, [rsp+128h+var_D8]
0x18004f39b  mov     rsi, [rsp+128h+var_D0]
0x18004f3a0  mov     rdi, [rsp+128h+var_A8]
0x18004f3a8  cmp     rbx, rsi
0x18004f3ab  jz      short loc_18004F3CD
0x18004f3ad  mov     rcx, rbx
0x18004f3b0  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18004f3b5  mov     [rdi], rax
0x18004f3b8  add     rbx, 20h ; ' '
0x18004f3bc  lea     rdi, [rdi+8]
0x18004f3c0  cmp     rbx, rsi
0x18004f3c3  jnz     short loc_18004F3AD
0x18004f3c5  mov     rdi, [rsp+128h+var_A8]
0x18004f3cd  lea     rax, [rsp+128h+var_E8]
0x18004f3d2  mov     [rsp+128h+var_60], rax
0x18004f3da  mov     [rsp+128h+var_58], 0
0x18004f3e6  mov     [rsp+128h+var_50], 1
0x18004f3ee  lea     rax, [rsp+128h+var_58]
0x18004f3f6  mov     [rsp+128h+var_108], rax
0x18004f3fb  movzx   r9d, r12w
0x18004f3ff  mov     r8, [rsp+128h+var_78]
0x18004f407  mov     rdx, rdi
0x18004f40a  mov     rcx, [rsp+128h+var_90]
0x18004f412  call    cs:__imp_CDPCreateResourceCollection
0x18004f418  mov     ebx, eax
0x18004f41a  lea     rcx, [rsp+128h+var_60]
0x18004f422  call    ??1?$out_param_t@V?$ComPtr@VICDPResourceCollection@@@WRL@Microsoft@@@details@wil@@QEAA@XZ; wil::details::out_param_t<Microsoft::WRL::ComPtr<ICDPResourceCollection>>::~out_param_t<Microsoft::WRL::ComPtr<ICDPResourceCollection>>(void)
0x18004f427  test    ebx, ebx
0x18004f429  jns     short loc_18004F4A6
0x18004f42b  mov     [rsp+128h+var_F8], ebx
0x18004f42f  mov     dword ptr [rsp+128h+var_F0], 4Ah ; 'J'
0x18004f437  lea     rax, [rsp+128h+var_F0]
0x18004f43c  mov     [rsp+128h+var_108], rax
0x18004f441  lea     r9, aCdpcomappregis; "..\\cdpcomappregistrationmanager.cpp"
0x18004f448  lea     r8, [rsp+128h+var_F8]
0x18004f44d  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x18004f452  nop
0x18004f453  lea     rcx, [rsp+128h+var_A8]
0x18004f45b  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(void)
0x18004f460  nop
0x18004f461  lea     rcx, [rsp+128h+var_90]
0x18004f469  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(void)
0x18004f46e  nop
0x18004f46f  lea     rcx, [rsp+128h+var_78]
0x18004f477  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(void)
0x18004f47c  nop
0x18004f47d  lea     rcx, [rsp+128h+var_D8]
0x18004f482  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x18004f487  nop
0x18004f488  lea     rcx, [rsp+128h+var_C0]
0x18004f48d  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x18004f492  nop
0x18004f493  lea     rcx, [rsp+128h+var_E8]
0x18004f498  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004f49d  mov     eax, [rsp+128h+var_F8]
0x18004f4a1  jmp     loc_18004F5BD
0x18004f4a6  mov     r13, [rsp+128h+var_F0]
0x18004f4ab  lea     rbx, [r13+20h]
0x18004f4af  mov     rcx, rbx; SRWLock
0x18004f4b2  call    cs:__imp_AcquireSRWLockExclusive
0x18004f4b8  mov     [rsp+128h+var_E0], rbx
0x18004f4bd  mov     rcx, [r13+18h]
0x18004f4c1  mov     rax, [rcx]
0x18004f4c4  mov     rdx, [rsp+128h+var_E8]
0x18004f4c9  mov     rax, [rax+20h]
0x18004f4cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f4d2  test    eax, eax
0x18004f4d4  jns     loc_18004F55D
0x18004f4da  mov     [rsp+128h+var_F8], eax
0x18004f4de  mov     dword ptr [rsp+128h+var_F0], 4Dh ; 'M'
0x18004f4e6  lea     rax, [rsp+128h+var_F0]
0x18004f4eb  mov     [rsp+128h+var_108], rax
0x18004f4f0  lea     r9, aCdpcomappregis; "..\\cdpcomappregistrationmanager.cpp"
0x18004f4f7  lea     r8, [rsp+128h+var_F8]
0x18004f4fc  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x18004f501  nop
0x18004f502  lea     rcx, [rsp+128h+var_E0]
0x18004f507  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18004f50c  nop
0x18004f50d  lea     rcx, [rsp+128h+var_A8]
0x18004f515  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(void)
0x18004f51a  nop
0x18004f51b  lea     rcx, [rsp+128h+var_90]
0x18004f523  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(void)
0x18004f528  nop
0x18004f529  lea     rcx, [rsp+128h+var_78]
0x18004f531  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(void)
0x18004f536  nop
0x18004f537  lea     rcx, [rsp+128h+var_D8]
0x18004f53c  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x18004f541  nop
0x18004f542  lea     rcx, [rsp+128h+var_C0]
0x18004f547  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x18004f54c  nop
0x18004f54d  lea     rcx, [rsp+128h+var_E8]
0x18004f552  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004f557  mov     eax, [rsp+128h+var_F8]
0x18004f55b  jmp     short loc_18004F5BD
0x18004f55d  lea     rcx, [rsp+128h+var_E0]
0x18004f562  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18004f567  nop
0x18004f568  lea     rcx, [rsp+128h+var_A8]
0x18004f570  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(void)
0x18004f575  nop
0x18004f576  lea     rcx, [rsp+128h+var_90]
0x18004f57e  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(void)
0x18004f583  nop
0x18004f584  lea     rcx, [rsp+128h+var_78]
0x18004f58c  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(void)
0x18004f591  nop
0x18004f592  lea     rcx, [rsp+128h+var_D8]
0x18004f597  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x18004f59c  nop
0x18004f59d  lea     rcx, [rsp+128h+var_C0]
0x18004f5a2  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x18004f5a7  nop
0x18004f5a8  lea     rcx, [rsp+128h+var_E8]
0x18004f5ad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004f5b2  nop
0x18004f5b3  jmp     short loc_18004F5BA
0x18004f5b5  mov     r15d, dword ptr [rsp+128h+var_F0]
0x18004f5ba  mov     eax, r15d
0x18004f5bd  mov     rcx, [rsp+128h+var_40]
0x18004f5c5  xor     rcx, rsp; StackCookie
0x18004f5c8  call    __security_check_cookie
0x18004f5cd  add     rsp, 0F0h
0x18004f5d4  pop     r15
0x18004f5d6  pop     r14
0x18004f5d8  pop     r13
0x18004f5da  pop     r12
0x18004f5dc  pop     rdi
0x18004f5dd  pop     rsi
0x18004f5de  pop     rbx
0x18004f5df  retn
```
