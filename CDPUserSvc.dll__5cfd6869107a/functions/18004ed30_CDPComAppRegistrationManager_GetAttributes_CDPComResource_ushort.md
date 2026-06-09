# CDPComAppRegistrationManager::GetAttributes(CDPComResource * *,ushort *)

- ea: `0x18004ed30`
- end: `0x18004f0e2`
- name: `?GetAttributes@CDPComAppRegistrationManager@@UEAAJPEAPEAUCDPComResource@@PEAG@Z`
- size: `946`
- prototype: `__int64 __fastcall(CDPComAppRegistrationManager *__hidden this, struct CDPComResource **, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003678`
- `0x180005c64`
- `0x180013908`
- `0x18001d044`
- `0x18001d9d0`
- `0x18004e630`
- `0x18004ed30`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004edbe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004edbe`

## string_xrefs

- `0x18004ed7b`: `..\cdpcomappregistrationmanager.cpp`
- `0x18004ee10`: `..\cdpcomappregistrationmanager.cpp`
- `0x18004ee7c`: `..\cdpcomappregistrationmanager.cpp`
- `0x18004ef53`: `..\cdpcomappregistrationmanager.cpp`
- `0x18004efff`: `..\cdpcomappregistrationmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall CDPComAppRegistrationManager::GetAttributes(RTL_SRWLOCK *this, LPVOID *a2, unsigned __int16 *a3)
{
  RTL_SRWLOCK *v7; // rbx
  PVOID Ptr; // rdi
  __int64 (__fastcall *v9)(PVOID, __int64 *); // rbx
  int v10; // eax
  int v11; // edx
  int v12; // ecx
  int v13; // eax
  int v14; // edx
  int v15; // ecx
  unsigned int v16; // eax
  unsigned __int16 i; // bx
  int v18; // eax
  int v19; // edx
  int v20; // ecx
  unsigned __int16 j; // bx
  __int64 v22; // rcx
  int v23; // eax
  int v24; // edx
  int v25; // ecx
  unsigned __int16 k; // bx
  __int64 v27; // rcx
  unsigned __int16 m; // bx
  __int64 v29; // rcx
  int v30; // [rsp+30h] [rbp-78h] BYREF
  __int64 v31; // [rsp+38h] [rbp-70h] BYREF
  RTL_SRWLOCK *v32; // [rsp+40h] [rbp-68h] BYREF
  __int128 v33; // [rsp+48h] [rbp-60h] BYREF
  __int64 v34; // [rsp+58h] [rbp-50h]
  unsigned int *v35; // [rsp+60h] [rbp-48h]
  __int128 *v36; // [rsp+68h] [rbp-40h]
  char v37; // [rsp+70h] [rbp-38h]
  unsigned int v38; // [rsp+B8h] [rbp+10h] BYREF
  unsigned int v39; // [rsp+C8h] [rbp+20h] BYREF

  if ( !a2 )
  {
    v39 = 92;
LABEL_3:
    v38 = -2147467261;
    Log<long &,char const (&)[36],int>(
      (_DWORD)this,
      (_DWORD)a2,
      (unsigned int)&v38,
      (unsigned int)"..\\cdpcomappregistrationmanager.cpp",
      (__int64)&v39);
    return v38;
  }
  if ( !a3 )
  {
    v39 = 93;
    goto LABEL_3;
  }
  *a3 = 0;
  *a2 = 0;
  v7 = this + 4;
  AcquireSRWLockShared(this + 4);
  v32 = v7;
  v31 = 0;
  Ptr = this[3].Ptr;
  v9 = *(__int64 (__fastcall **)(PVOID, __int64 *))(*(_QWORD *)Ptr + 40LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  v10 = v9(Ptr, &v31);
  if ( v10 >= 0 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v31 + 24LL))(v31, &v38);
    if ( v13 >= 0 )
    {
      v16 = (unsigned __int16)v38;
      if ( (_WORD)v38 )
      {
        *a3 = v38;
        v33 = 0;
        v34 = 0;
        std::vector<ICDPResource *>::_Construct_n<>(&v33, v16);
        v35 = &v38;
        v36 = &v33;
        v37 = 1;
        for ( i = 0; i < (unsigned __int16)v38; ++i )
        {
          v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v31 + 32LL))(v31, i, v33 + 8LL * i);
          if ( v18 < 0 )
          {
            v39 = v18;
            v30 = 128;
            Log<long &,char const (&)[36],int>(
              v20,
              v19,
              (unsigned int)&v39,
              (unsigned int)"..\\cdpcomappregistrationmanager.cpp",
              (__int64)&v30);
            for ( j = 0; j < (unsigned __int16)v38; ++j )
            {
              v22 = *(_QWORD *)(v33 + 8LL * j);
              if ( v22 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            }
LABEL_18:
            std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(&v33);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v32);
            return v39;
          }
        }
        v23 = ComResourcesFromCDPResources(v33, (unsigned __int16)v38, a2);
        if ( v23 < 0 )
        {
          v39 = v23;
          v30 = 131;
          Log<long &,char const (&)[36],int>(
            v25,
            v24,
            (unsigned int)&v39,
            (unsigned int)"..\\cdpcomappregistrationmanager.cpp",
            (__int64)&v30);
          for ( k = 0; k < (unsigned __int16)v38; ++k )
          {
            v27 = *(_QWORD *)(v33 + 8LL * k);
            if ( v27 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          }
          goto LABEL_18;
        }
        for ( m = 0; m < (unsigned __int16)v38; ++m )
        {
          v29 = *(_QWORD *)(v33 + 8LL * m);
          if ( v29 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        }
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(&v33);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v32);
      return 0;
    }
    else
    {
      v39 = v13;
      v30 = 108;
      Log<long &,char const (&)[36],int>(
        v15,
        v14,
        (unsigned int)&v39,
        (unsigned int)"..\\cdpcomappregistrationmanager.cpp",
        (__int64)&v30);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v32);
      return v39;
    }
  }
  else
  {
    v39 = v10;
    v30 = 105;
    Log<long &,char const (&)[36],int>(
      v12,
      v11,
      (unsigned int)&v39,
      (unsigned int)"..\\cdpcomappregistrationmanager.cpp",
      (__int64)&v30);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v32);
    return v39;
  }
}

```

## disassembly

```asm
0x18004ed30  mov     rax, rsp
0x18004ed33  mov     [rax+8], rbx
0x18004ed37  mov     [rax+18h], rsi
0x18004ed3b  push    rdi
0x18004ed3c  push    r12
0x18004ed3e  push    r13
0x18004ed40  push    r14
0x18004ed42  push    r15
0x18004ed44  sub     rsp, 80h
0x18004ed4b  mov     rsi, r8
0x18004ed4e  mov     r14, rdx
0x18004ed51  mov     rdi, rcx
0x18004ed54  xor     r12d, r12d
0x18004ed57  test    rdx, rdx
0x18004ed5a  jnz     short loc_18004ED9B
0x18004ed5c  mov     dword ptr [rax+20h], 5Ch ; '\'
0x18004ed63  mov     [rsp+0A8h+arg_8], 80004003h
0x18004ed6e  lea     rax, [rsp+0A8h+arg_18]
0x18004ed76  mov     [rsp+0A8h+var_88], rax
0x18004ed7b  lea     r9, aCdpcomappregis; "..\\cdpcomappregistrationmanager.cpp"
0x18004ed82  lea     r8, [rsp+0A8h+arg_8]
0x18004ed8a  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x18004ed8f  mov     eax, [rsp+0A8h+arg_8]
0x18004ed96  jmp     loc_18004F0C5
0x18004ed9b  test    rsi, rsi
0x18004ed9e  jnz     short loc_18004EDAD
0x18004eda0  mov     [rsp+0A8h+arg_18], 5Dh ; ']'
0x18004edab  jmp     short loc_18004ED63
0x18004edad  mov     [r8], r12w
0x18004edb1  mov     [rdx], r12
0x18004edb4  mov     r15d, r12d
0x18004edb7  lea     rbx, [rcx+20h]
0x18004edbb  mov     rcx, rbx; SRWLock
0x18004edbe  call    cs:__imp_AcquireSRWLockShared
0x18004edc4  mov     [rsp+0A8h+var_68], rbx
0x18004edc9  mov     [rsp+0A8h+var_70], r12
0x18004edce  mov     rdi, [rdi+18h]
0x18004edd2  mov     rax, [rdi]
0x18004edd5  mov     rbx, [rax+28h]
0x18004edd9  lea     rcx, [rsp+0A8h+var_70]
0x18004edde  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ede3  lea     rdx, [rsp+0A8h+var_70]
0x18004ede8  mov     rcx, rdi
0x18004edeb  mov     rax, rbx
0x18004edee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004edf3  test    eax, eax
0x18004edf5  jns     short loc_18004EE46
0x18004edf7  mov     [rsp+0A8h+arg_18], eax
0x18004edfe  mov     [rsp+0A8h+var_78], 69h ; 'i'
0x18004ee06  lea     rax, [rsp+0A8h+var_78]
0x18004ee0b  mov     [rsp+0A8h+var_88], rax
0x18004ee10  lea     r9, aCdpcomappregis; "..\\cdpcomappregistrationmanager.cpp"
0x18004ee17  lea     r8, [rsp+0A8h+arg_18]
0x18004ee1f  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x18004ee24  nop
0x18004ee25  lea     rcx, [rsp+0A8h+var_70]
0x18004ee2a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ee2f  nop
0x18004ee30  lea     rcx, [rsp+0A8h+var_68]
0x18004ee35  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18004ee3a  mov     eax, [rsp+0A8h+arg_18]
0x18004ee41  jmp     loc_18004F0C5
0x18004ee46  mov     rcx, [rsp+0A8h+var_70]
0x18004ee4b  mov     rax, [rcx]
0x18004ee4e  lea     rdx, [rsp+0A8h+arg_8]
0x18004ee56  mov     rax, [rax+18h]
0x18004ee5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee5f  test    eax, eax
0x18004ee61  jns     short loc_18004EEB2
0x18004ee63  mov     [rsp+0A8h+arg_18], eax
0x18004ee6a  mov     [rsp+0A8h+var_78], 6Ch ; 'l'
0x18004ee72  lea     rax, [rsp+0A8h+var_78]
0x18004ee77  mov     [rsp+0A8h+var_88], rax
0x18004ee7c  lea     r9, aCdpcomappregis; "..\\cdpcomappregistrationmanager.cpp"
0x18004ee83  lea     r8, [rsp+0A8h+arg_18]
0x18004ee8b  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x18004ee90  nop
0x18004ee91  lea     rcx, [rsp+0A8h+var_70]
0x18004ee96  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ee9b  nop
0x18004ee9c  lea     rcx, [rsp+0A8h+var_68]
0x18004eea1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18004eea6  mov     eax, [rsp+0A8h+arg_18]
0x18004eead  jmp     loc_18004F0C5
0x18004eeb2  movzx   eax, word ptr [rsp+0A8h+arg_8]
0x18004eeba  test    ax, ax
0x18004eebd  jz      loc_18004F0A2
0x18004eec3  mov     [rsi], ax
0x18004eec6  xorps   xmm0, xmm0
0x18004eec9  movdqu  [rsp+0A8h+var_60], xmm0
0x18004eecf  mov     [rsp+0A8h+var_50], r12
0x18004eed4  mov     edx, eax
0x18004eed6  lea     rcx, [rsp+0A8h+var_60]
0x18004eedb  call    ??$_Construct_n@$$V@?$vector@PEAVICDPResource@@V?$allocator@PEAVICDPResource@@@std@@@std@@AEAAX_K@Z; std::vector<ICDPResource *>::_Construct_n<>(unsigned __int64)
0x18004eee0  nop
0x18004eee1  lea     rdi, [rsp+0A8h+arg_8]
0x18004eee9  mov     [rsp+0A8h+var_48], rdi
0x18004eeee  lea     r13, [rsp+0A8h+var_60]
0x18004eef3  mov     [rsp+0A8h+var_40], r13
0x18004eef8  mov     si, 1
0x18004eefc  mov     [rsp+0A8h+var_38], sil
0x18004ef01  mov     ebx, r12d
0x18004ef04  cmp     bx, word ptr [rsp+0A8h+arg_8]
0x18004ef0c  jnb     loc_18004EFC9
0x18004ef12  mov     rcx, [rsp+0A8h+var_70]
0x18004ef17  mov     r9, [rcx]
0x18004ef1a  movzx   edx, bx
0x18004ef1d  mov     rax, qword ptr [rsp+0A8h+var_60]
0x18004ef22  lea     r8, [rax+rdx*8]
0x18004ef26  movzx   edx, bx
0x18004ef29  mov     rax, [r9+20h]
0x18004ef2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef32  test    eax, eax
0x18004ef34  jns     loc_18004EFC1
0x18004ef3a  mov     [rsp+0A8h+arg_18], eax
0x18004ef41  mov     [rsp+0A8h+var_78], 80h
0x18004ef49  lea     rax, [rsp+0A8h+var_78]
0x18004ef4e  mov     [rsp+0A8h+var_88], rax
0x18004ef53  lea     r9, aCdpcomappregis; "..\\cdpcomappregistrationmanager.cpp"
0x18004ef5a  lea     r8, [rsp+0A8h+arg_18]
0x18004ef62  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x18004ef67  nop
0x18004ef68  mov     ebx, r12d
0x18004ef6b  cmp     r12w, [rdi]
0x18004ef6f  jnb     short loc_18004EF95
0x18004ef71  movzx   ecx, bx
0x18004ef74  mov     rax, [r13+0]
0x18004ef78  mov     rcx, [rax+rcx*8]
0x18004ef7c  test    rcx, rcx
0x18004ef7f  jz      short loc_18004EF8D
0x18004ef81  mov     rax, [rcx]
0x18004ef84  mov     rax, [rax+10h]
0x18004ef88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef8d  add     bx, si
0x18004ef90  cmp     bx, [rdi]
0x18004ef93  jb      short loc_18004EF71
0x18004ef95  lea     rcx, [rsp+0A8h+var_60]
0x18004ef9a  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(void)
0x18004ef9f  nop
0x18004efa0  lea     rcx, [rsp+0A8h+var_70]
0x18004efa5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004efaa  nop
0x18004efab  lea     rcx, [rsp+0A8h+var_68]
0x18004efb0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18004efb5  mov     eax, [rsp+0A8h+arg_18]
0x18004efbc  jmp     loc_18004F0C5
0x18004efc1  add     bx, si
0x18004efc4  jmp     loc_18004EF04
0x18004efc9  movzx   edx, word ptr [rsp+0A8h+arg_8]
0x18004efd1  mov     r8, r14
0x18004efd4  mov     rcx, qword ptr [rsp+0A8h+var_60]
0x18004efd9  call    ComResourcesFromCDPResources
0x18004efde  test    eax, eax
0x18004efe0  jns     loc_18004F06A
0x18004efe6  mov     [rsp+0A8h+arg_18], eax
0x18004efed  mov     [rsp+0A8h+var_78], 83h
0x18004eff5  lea     rax, [rsp+0A8h+var_78]
0x18004effa  mov     [rsp+0A8h+var_88], rax
0x18004efff  lea     r9, aCdpcomappregis; "..\\cdpcomappregistrationmanager.cpp"
0x18004f006  lea     r8, [rsp+0A8h+arg_18]
0x18004f00e  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x18004f013  nop
0x18004f014  mov     ebx, r12d
0x18004f017  cmp     r12w, [rdi]
0x18004f01b  jnb     short loc_18004F041
0x18004f01d  movzx   ecx, bx
0x18004f020  mov     rax, [r13+0]
0x18004f024  mov     rcx, [rax+rcx*8]
0x18004f028  test    rcx, rcx
0x18004f02b  jz      short loc_18004F039
0x18004f02d  mov     rax, [rcx]
0x18004f030  mov     rax, [rax+10h]
0x18004f034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f039  add     bx, si
0x18004f03c  cmp     bx, [rdi]
0x18004f03f  jb      short loc_18004F01D
0x18004f041  lea     rcx, [rsp+0A8h+var_60]
0x18004f046  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(void)
0x18004f04b  nop
0x18004f04c  lea     rcx, [rsp+0A8h+var_70]
0x18004f051  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004f056  nop
0x18004f057  lea     rcx, [rsp+0A8h+var_68]
0x18004f05c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18004f061  mov     eax, [rsp+0A8h+arg_18]
0x18004f068  jmp     short loc_18004F0C5
0x18004f06a  mov     ebx, r12d
0x18004f06d  cmp     r12w, [rdi]
0x18004f071  jnb     short loc_18004F097
0x18004f073  movzx   ecx, bx
0x18004f076  mov     rax, [r13+0]
0x18004f07a  mov     rcx, [rax+rcx*8]
0x18004f07e  test    rcx, rcx
0x18004f081  jz      short loc_18004F08F
0x18004f083  mov     rax, [rcx]
0x18004f086  mov     rax, [rax+10h]
0x18004f08a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f08f  add     bx, si
0x18004f092  cmp     bx, [rdi]
0x18004f095  jb      short loc_18004F073
0x18004f097  lea     rcx, [rsp+0A8h+var_60]
0x18004f09c  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>>>(void)
0x18004f0a1  nop
0x18004f0a2  lea     rcx, [rsp+0A8h+var_70]
0x18004f0a7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004f0ac  nop
0x18004f0ad  lea     rcx, [rsp+0A8h+var_68]
0x18004f0b2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18004f0b7  nop
0x18004f0b8  jmp     short loc_18004F0C2
0x18004f0ba  mov     r15d, [rsp+0A8h+arg_8]
0x18004f0c2  mov     eax, r15d
0x18004f0c5  lea     r11, [rsp+0A8h+var_28]
0x18004f0cd  mov     rbx, [r11+30h]
0x18004f0d1  mov     rsi, [r11+40h]
0x18004f0d5  mov     rsp, r11
0x18004f0d8  pop     r15
0x18004f0da  pop     r14
0x18004f0dc  pop     r13
0x18004f0de  pop     r12
0x18004f0e0  pop     rdi
0x18004f0e1  retn
```
