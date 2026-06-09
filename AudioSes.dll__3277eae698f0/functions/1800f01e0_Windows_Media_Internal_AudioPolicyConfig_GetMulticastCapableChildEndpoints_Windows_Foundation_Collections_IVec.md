# Windows::Media::Internal::AudioPolicyConfig::GetMulticastCapableChildEndpoints(Windows::Foundation::Collections::IVectorView<HSTRING__ *> * *)

- ea: `0x1800f01e0`
- end: `0x1800f04ed`
- name: `?GetMulticastCapableChildEndpoints@AudioPolicyConfig@Internal@Media@Windows@@UEAAJPEAPEAU?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@4@@Z`
- size: `781`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000f700`
- `0x180010a90`
- `0x180011d0c`
- `0x180011e7c`
- `0x180066e10`
- `0x1800ec934`
- `0x1800ecde0`
- `0x1800ee71c`
- `0x1800f01e0`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f036f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f0395`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f03e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f036f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f0395`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f03e5`

## string_xrefs

- `0x1800f020a`: `avcore\audiocore\client\audiopolicymanager\lib\audiopolicyconfigmanager.cpp`
- `0x1800f0241`: `avcore\audiocore\client\audiopolicymanager\lib\audiopolicyconfigmanager.cpp`
- `0x1800f028d`: `avcore\audiocore\client\audiopolicymanager\lib\audiopolicyconfigmanager.cpp`
- `0x1800f02d3`: `avcore\audiocore\client\audiopolicymanager\lib\audiopolicyconfigmanager.cpp`
- `0x1800f0380`: `avcore\audiocore\client\audiopolicymanager\lib\audiopolicyconfigmanager.cpp`
- `0x1800f03d0`: `avcore\audiocore\client\audiopolicymanager\lib\audiopolicyconfigmanager.cpp`
- `0x1800f044f`: `avcore\audiocore\client\audiopolicymanager\lib\audiopolicyconfigmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Media::Internal::AudioPolicyConfig::GetMulticastCapableChildEndpoints(
        const unsigned __int16 *a1,
        __int64 a2)
{
  unsigned int v3; // ebx
  int AudioServerBindingHandle; // eax
  int v5; // eax
  __int64 v6; // rcx
  void *v7; // rcx
  int v8; // eax
  unsigned int v9; // edi
  unsigned int n; // ebx
  void *v11; // rcx
  unsigned int v12; // edi
  __int64 v13; // rbx
  int v14; // eax
  unsigned int v15; // esi
  int v16; // eax
  unsigned int j; // ebx
  unsigned int i; // ebx
  void *v19; // rcx
  int v20; // eax
  unsigned int m; // ebx
  unsigned int k; // ebx
  void *v23; // rcx
  __int64 v25; // [rsp+20h] [rbp-30h] BYREF
  void *v26; // [rsp+28h] [rbp-28h] BYREF
  _QWORD v27[4]; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  unsigned int v29; // [rsp+88h] [rbp+38h] BYREF
  void *v30; // [rsp+90h] [rbp+40h] BYREF
  HSTRING string; // [rsp+98h] [rbp+48h] BYREF

  if ( a2 )
  {
    v26 = 0;
    AudioServerBindingHandle = GetAudioServerBindingHandle(a1, L"Audiosrv", &v26);
    v3 = AudioServerBindingHandle;
    if ( AudioServerBindingHandle >= 0 )
    {
      v29 = 0;
      v30 = 0;
      v27[0] = &v26;
      v27[1] = &v29;
      v27[2] = &v30;
      v5 = lambda_8bfd50c11e58c5d53493af3017671484_::operator()(v27);
      v3 = v5;
      if ( v5 >= 0 )
      {
        v25 = 0;
        v8 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(
               v6,
               &v25);
        v9 = v8;
        if ( v8 >= 0 )
        {
          v12 = 0;
          v13 = v25;
          while ( v12 < v29 )
          {
            string = 0;
            v14 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&string, (char *)v30 + 8 * v12);
            v15 = v14;
            if ( v14 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x739,
                (unsigned int)"avcore\\audiocore\\client\\audiopolicymanager\\lib\\audiopolicyconfigmanager.cpp",
                (const char *)(unsigned int)v14,
                v25);
              WindowsDeleteString(string);
              string = 0;
              wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,wil::err_returncode_policy>(&v25);
              for ( i = 0; i < v29; ++i )
                operator delete(*((void **)v30 + i));
              goto LABEL_24;
            }
            v16 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v13 + 104LL))(v13, string);
            v15 = v16;
            if ( v16 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x73A,
                (unsigned int)"avcore\\audiocore\\client\\audiopolicymanager\\lib\\audiopolicyconfigmanager.cpp",
                (const char *)(unsigned int)v16,
                v25);
              WindowsDeleteString(string);
              string = 0;
              wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,wil::err_returncode_policy>(&v25);
              for ( j = 0; j < v29; ++j )
                operator delete(*((void **)v30 + j));
LABEL_24:
              v19 = v30;
              v30 = 0;
              if ( v19 )
                operator delete(v19);
              v3 = v15;
              goto LABEL_36;
            }
            WindowsDeleteString(string);
            ++v12;
          }
          v20 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 64LL))(v13, a2);
          v9 = v20;
          if ( v20 >= 0 )
          {
            wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,wil::err_returncode_policy>(&v25);
            for ( k = 0; k < v29; ++k )
              operator delete(*((void **)v30 + k));
            v23 = v30;
            v30 = 0;
            if ( v23 )
              operator delete(v23);
            v3 = 0;
            goto LABEL_36;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x73D,
            (unsigned int)"avcore\\audiocore\\client\\audiopolicymanager\\lib\\audiopolicyconfigmanager.cpp",
            (const char *)(unsigned int)v20,
            v25);
          wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,wil::err_returncode_policy>(&v25);
          for ( m = 0; m < v29; ++m )
            operator delete(*((void **)v30 + m));
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x734,
            (unsigned int)"avcore\\audiocore\\client\\audiopolicymanager\\lib\\audiopolicyconfigmanager.cpp",
            (const char *)(unsigned int)v8,
            v25);
          wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,wil::err_returncode_policy>(&v25);
          for ( n = 0; n < v29; ++n )
            operator delete(*((void **)v30 + n));
        }
        v11 = v30;
        v30 = 0;
        if ( v11 )
          operator delete(v11);
        v3 = v9;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x729,
          (unsigned int)"avcore\\audiocore\\client\\audiopolicymanager\\lib\\audiopolicyconfigmanager.cpp",
          (const char *)(unsigned int)v5,
          v25);
        v7 = v30;
        v30 = 0;
        if ( v7 )
          operator delete(v7);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71A,
        (unsigned int)"avcore\\audiocore\\client\\audiopolicymanager\\lib\\audiopolicyconfigmanager.cpp",
        (const char *)(unsigned int)AudioServerBindingHandle,
        v25);
    }
LABEL_36:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v26);
    return v3;
  }
  v3 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x717,
    (unsigned int)"avcore\\audiocore\\client\\audiopolicymanager\\lib\\audiopolicyconfigmanager.cpp",
    (const char *)0x80004003LL,
    v25);
  return v3;
}

```

## disassembly

```asm
0x1800f01e0  mov     [rsp-28h+arg_0], rbx
0x1800f01e5  push    rbp
0x1800f01e6  push    rsi
0x1800f01e7  push    rdi
0x1800f01e8  push    r14
0x1800f01ea  push    r15
0x1800f01ec  mov     rbp, rsp
0x1800f01ef  sub     rsp, 50h
0x1800f01f3  mov     r14, rdx
0x1800f01f6  xor     r15d, r15d
0x1800f01f9  test    rdx, rdx
0x1800f01fc  jnz     short loc_1800F0220
0x1800f01fe  mov     rcx, [rbp+28h]; this
0x1800f0202  mov     ebx, 80004003h
0x1800f0207  mov     r9d, ebx; char *
0x1800f020a  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\client\\audiopolicym"...
0x1800f0211  mov     edx, 717h; void *
0x1800f0216  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f021b  jmp     loc_1800F04D7
0x1800f0220  mov     [rbp+var_28], r15
0x1800f0224  lea     r8, [rbp+var_28]; void **
0x1800f0228  lea     rdx, aAudiosrv_0; "Audiosrv"
0x1800f022f  call    ?GetAudioServerBindingHandle@@YAJPEBG0PEAPEAX@Z; GetAudioServerBindingHandle(ushort const *,ushort const *,void * *)
0x1800f0234  mov     ebx, eax
0x1800f0236  test    eax, eax
0x1800f0238  jns     short loc_1800F0257
0x1800f023a  mov     rcx, [rbp+28h]; this
0x1800f023e  mov     r9d, eax; char *
0x1800f0241  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\client\\audiopolicym"...
0x1800f0248  mov     edx, 71Ah; void *
0x1800f024d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0252  jmp     loc_1800F04CE
0x1800f0257  mov     [rbp+arg_8], r15d
0x1800f025b  mov     [rbp+arg_10], r15
0x1800f025f  lea     rax, [rbp+var_28]
0x1800f0263  mov     [rbp+var_20], rax
0x1800f0267  lea     rax, [rbp+arg_8]
0x1800f026b  mov     [rbp+var_18], rax
0x1800f026f  lea     rax, [rbp+arg_10]
0x1800f0273  mov     [rbp+var_10], rax
0x1800f0277  lea     rcx, [rbp+var_20]
0x1800f027b  call    _lambda_8bfd50c11e58c5d53493af3017671484___operator__
0x1800f0280  mov     ebx, eax
0x1800f0282  test    eax, eax
0x1800f0284  jns     short loc_1800F02B9
0x1800f0286  mov     rcx, [rbp+28h]; this
0x1800f028a  mov     r9d, eax; char *
0x1800f028d  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\client\\audiopolicym"...
0x1800f0294  mov     edx, 729h; void *
0x1800f0299  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f029e  mov     rcx, [rbp+arg_10]; void *
0x1800f02a2  mov     [rbp+arg_10], r15
0x1800f02a6  test    rcx, rcx
0x1800f02a9  jz      loc_1800F04CE
0x1800f02af  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800f02b4  jmp     loc_1800F04CE
0x1800f02b9  mov     [rbp+var_30], r15
0x1800f02bd  lea     rdx, [rbp+var_30]
0x1800f02c1  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x1800f02c6  mov     edi, eax
0x1800f02c8  test    eax, eax
0x1800f02ca  jns     short loc_1800F0325
0x1800f02cc  mov     rcx, [rbp+28h]; this
0x1800f02d0  mov     r9d, eax; char *
0x1800f02d3  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\client\\audiopolicym"...
0x1800f02da  mov     edx, 734h; void *
0x1800f02df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f02e4  lea     rcx, [rbp+var_30]
0x1800f02e8  call    ??1?$com_ptr_t@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,wil::err_returncode_policy>(void)
0x1800f02ed  mov     ebx, r15d
0x1800f02f0  cmp     [rbp+arg_8], r15d
0x1800f02f4  jbe     short loc_1800F030C
0x1800f02f6  mov     eax, ebx
0x1800f02f8  mov     rcx, [rbp+arg_10]
0x1800f02fc  mov     rcx, [rcx+rax*8]; void *
0x1800f0300  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800f0305  inc     ebx
0x1800f0307  cmp     ebx, [rbp+arg_8]
0x1800f030a  jb      short loc_1800F02F6
0x1800f030c  mov     rcx, [rbp+arg_10]; void *
0x1800f0310  mov     [rbp+arg_10], r15
0x1800f0314  test    rcx, rcx
0x1800f0317  jz      short loc_1800F031E
0x1800f0319  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800f031e  mov     ebx, edi
0x1800f0320  jmp     loc_1800F04CE
0x1800f0325  mov     edi, r15d
0x1800f0328  mov     rbx, [rbp+var_30]
0x1800f032c  cmp     edi, [rbp+arg_8]
0x1800f032f  jnb     loc_1800F0430
0x1800f0335  mov     [rbp+string], r15
0x1800f0339  mov     ecx, edi
0x1800f033b  mov     rax, [rbp+arg_10]
0x1800f033f  lea     rdx, [rax+rcx*8]
0x1800f0343  lea     rcx, [rbp+string]
0x1800f0347  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1800f034c  mov     esi, eax
0x1800f034e  test    eax, eax
0x1800f0350  js      short loc_1800F03C9
0x1800f0352  mov     rax, [rbx]
0x1800f0355  mov     rdx, [rbp+string]
0x1800f0359  mov     rcx, rbx
0x1800f035c  mov     rax, [rax+68h]
0x1800f0360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0365  mov     esi, eax
0x1800f0367  test    eax, eax
0x1800f0369  js      short loc_1800F0379
0x1800f036b  mov     rcx, [rbp+string]; string
0x1800f036f  call    cs:__imp_WindowsDeleteString
0x1800f0375  inc     edi
0x1800f0377  jmp     short loc_1800F032C
0x1800f0379  mov     rcx, [rbp+28h]; this
0x1800f037d  mov     r9d, esi; char *
0x1800f0380  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\client\\audiopolicym"...
0x1800f0387  mov     edx, 73Ah; void *
0x1800f038c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0391  mov     rcx, [rbp+string]; string
0x1800f0395  call    cs:__imp_WindowsDeleteString
0x1800f039b  mov     [rbp+string], r15
0x1800f039f  lea     rcx, [rbp+var_30]
0x1800f03a3  call    ??1?$com_ptr_t@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,wil::err_returncode_policy>(void)
0x1800f03a8  mov     ebx, r15d
0x1800f03ab  cmp     [rbp+arg_8], r15d
0x1800f03af  jbe     short loc_1800F0417
0x1800f03b1  mov     eax, ebx
0x1800f03b3  mov     rcx, [rbp+arg_10]
0x1800f03b7  mov     rcx, [rcx+rax*8]; void *
0x1800f03bb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800f03c0  inc     ebx
0x1800f03c2  cmp     ebx, [rbp+arg_8]
0x1800f03c5  jb      short loc_1800F03B1
0x1800f03c7  jmp     short loc_1800F0417
0x1800f03c9  mov     rcx, [rbp+28h]; this
0x1800f03cd  mov     r9d, esi; char *
0x1800f03d0  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\client\\audiopolicym"...
0x1800f03d7  mov     edx, 739h; void *
0x1800f03dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f03e1  mov     rcx, [rbp+string]; string
0x1800f03e5  call    cs:__imp_WindowsDeleteString
0x1800f03eb  mov     [rbp+string], r15
0x1800f03ef  lea     rcx, [rbp+var_30]
0x1800f03f3  call    ??1?$com_ptr_t@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,wil::err_returncode_policy>(void)
0x1800f03f8  mov     ebx, r15d
0x1800f03fb  cmp     [rbp+arg_8], r15d
0x1800f03ff  jbe     short loc_1800F0417
0x1800f0401  mov     eax, ebx
0x1800f0403  mov     rcx, [rbp+arg_10]
0x1800f0407  mov     rcx, [rcx+rax*8]; void *
0x1800f040b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800f0410  inc     ebx
0x1800f0412  cmp     ebx, [rbp+arg_8]
0x1800f0415  jb      short loc_1800F0401
0x1800f0417  mov     rcx, [rbp+arg_10]; void *
0x1800f041b  mov     [rbp+arg_10], r15
0x1800f041f  test    rcx, rcx
0x1800f0422  jz      short loc_1800F0429
0x1800f0424  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800f0429  mov     ebx, esi
0x1800f042b  jmp     loc_1800F04CE
0x1800f0430  mov     rax, [rbx]
0x1800f0433  mov     rdx, r14
0x1800f0436  mov     rcx, rbx
0x1800f0439  mov     rax, [rax+40h]
0x1800f043d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0442  mov     edi, eax
0x1800f0444  test    eax, eax
0x1800f0446  jns     short loc_1800F0491
0x1800f0448  mov     rcx, [rbp+28h]; this
0x1800f044c  mov     r9d, eax; char *
0x1800f044f  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\client\\audiopolicym"...
0x1800f0456  mov     edx, 73Dh; void *
0x1800f045b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0460  lea     rcx, [rbp+var_30]
0x1800f0464  call    ??1?$com_ptr_t@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,wil::err_returncode_policy>(void)
0x1800f0469  mov     ebx, r15d
0x1800f046c  cmp     [rbp+arg_8], r15d
0x1800f0470  jbe     loc_1800F030C
0x1800f0476  mov     eax, ebx
0x1800f0478  mov     rcx, [rbp+arg_10]
0x1800f047c  mov     rcx, [rcx+rax*8]; void *
0x1800f0480  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800f0485  inc     ebx
0x1800f0487  cmp     ebx, [rbp+arg_8]
0x1800f048a  jb      short loc_1800F0476
0x1800f048c  jmp     loc_1800F030C
0x1800f0491  lea     rcx, [rbp+var_30]
0x1800f0495  call    ??1?$com_ptr_t@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,wil::err_returncode_policy>(void)
0x1800f049a  mov     ebx, r15d
0x1800f049d  cmp     [rbp+arg_8], r15d
0x1800f04a1  jbe     short loc_1800F04B9
0x1800f04a3  mov     eax, ebx
0x1800f04a5  mov     rcx, [rbp+arg_10]
0x1800f04a9  mov     rcx, [rcx+rax*8]; void *
0x1800f04ad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800f04b2  inc     ebx
0x1800f04b4  cmp     ebx, [rbp+arg_8]
0x1800f04b7  jb      short loc_1800F04A3
0x1800f04b9  mov     rcx, [rbp+arg_10]; void *
0x1800f04bd  mov     [rbp+arg_10], r15
0x1800f04c1  test    rcx, rcx
0x1800f04c4  jz      short loc_1800F04CB
0x1800f04c6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800f04cb  mov     ebx, r15d
0x1800f04ce  lea     rcx, [rbp+var_28]
0x1800f04d2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800f04d7  mov     eax, ebx
0x1800f04d9  mov     rbx, [rsp+50h+arg_0]
0x1800f04e1  add     rsp, 50h
0x1800f04e5  pop     r15
0x1800f04e7  pop     r14
0x1800f04e9  pop     rdi
0x1800f04ea  pop     rsi
0x1800f04eb  pop     rbp
0x1800f04ec  retn
```
