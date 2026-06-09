# Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(HSTRING__ *,ushort *,unsigned __int64,_GUID const *)

- ea: `0x140017060`
- end: `0x1400171f9`
- name: `?TryLookupExtensionPointImplementationAcid@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAG_KPEBU_GUID@@@Z`
- size: `409`
- prototype: `__int64 __fastcall(HSTRING this, unsigned __int16 *, unsigned __int16 *, _OWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x140016a54`

## callees

- `0x140003620`
- `0x140007c94`
- `0x140008ea8`
- `0x140009158`
- `0x140009760`
- `0x14000bd34`
- `0x14000c458`
- `0x14000ed00`
- `0x1400136fc`
- `0x14001492c`
- `0x14001544c`
- `0x140017060`

## string_xrefs

- `0x140017169`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x1400171a1`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x140017195`: `The product platform extension registry is invalid. There are multiple extensions and no default registered for the extension point.`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(
        HSTRING this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _OWORD *a4)
{
  char v6; // bl
  __int64 v7; // rax
  int v8; // edi
  int v10; // [rsp+20h] [rbp-E0h]
  char *v11[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v12; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v13[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v14; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v15[8]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v16[15]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v17[34]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v18; // [rsp+1F0h] [rbp+F0h]
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v12 = a2;
  v14 = 128;
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v17);
  v6 = 1;
  v17[0] = &Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::`vftable';
  if ( a4 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      v17,
      v13);
    v7 = v18;
    *(_OWORD *)(v18 + 24) = *a4;
    *(_BYTE *)(v7 + 4) = 1;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v13);
  }
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(
    (Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *)v17,
    this);
  *v12 = 0;
  v16[0] = &wistd::__function::__func<_lambda_4f9cb091d726181fa859ce89134efc24_,long (Windows::Internal::PlatformExtensions::Details::ExtensionRegistration const *,bool,bool *)>::`vftable';
  v16[1] = &v12;
  v16[2] = &v14;
  v16[3] = v17;
  v16[4] = v11;
  v16[5] = (char *)v11 + 4;
  LOBYTE(v11[0]) = 0;
  HIDWORD(v11[0]) = 0;
  v16[13] = v16;
  v8 = Windows::Internal::PlatformExtensions::Details::ForEachEnabledExtensionRegistration(this, v15);
  wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::~function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>(v15);
  if ( v8 >= 0 )
  {
    if ( LOBYTE(v11[0]) || SHIDWORD(v11[0]) <= 1 )
      v6 = 0;
    wil::details::in1diag3::FailFast_HrIfMsg(
      retaddr,
      (void *)0x1BB,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)0x8007000DLL,
      v6,
      (bool)"The product platform extension registry is invalid. There are multiple extensions and no default registered "
            "for the extension point.",
      v11[0]);
    Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::Stop(
      (Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *)v17,
      v12);
    v8 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B7,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)v8,
      v10);
  }
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::~TryLookupExtensionPointImplementationAcid((Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *)v17);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140017060  mov     [rsp-8+arg_10], rbx
0x140017065  push    rbp
0x140017066  push    rsi
0x140017067  push    rdi
0x140017068  lea     rbp, [rsp-140h]
0x140017070  sub     rsp, 240h
0x140017077  mov     rax, cs:__security_cookie
0x14001707e  xor     rax, rsp
0x140017081  mov     [rbp+150h+var_20], rax
0x140017088  mov     rsi, rcx
0x14001708b  mov     [rsp+250h+var_210], rdx
0x140017090  lea     rcx, [rbp+150h+var_170]; struct wil::details::IFailureCallback *
0x140017094  mov     [rsp+250h+var_1F8], 80h
0x14001709d  mov     rdi, r9
0x1400170a0  call    ??0?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400170a5  lea     rax, ??_7TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::`vftable'
0x1400170ac  mov     ebx, 1
0x1400170b1  mov     [rbp+150h+var_170], rax
0x1400170b5  test    rdi, rdi
0x1400170b8  jz      short loc_1400170E4
0x1400170ba  lea     rdx, [rsp+250h+var_200]
0x1400170bf  lea     rcx, [rbp+150h+var_170]
0x1400170c3  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400170c8  mov     rax, [rbp+150h+var_60]
0x1400170cf  lea     rcx, [rsp+250h+var_200]
0x1400170d4  movups  xmm0, xmmword ptr [rdi]
0x1400170d7  movdqu  xmmword ptr [rax+18h], xmm0
0x1400170dc  mov     [rax+4], bl
0x1400170df  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400170e4  mov     rdx, rsi; HSTRING
0x1400170e7  lea     rcx, [rbp+150h+var_170]; this
0x1400170eb  call    ?StartActivity@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(HSTRING__ *)
0x1400170f0  mov     rax, [rsp+250h+var_210]
0x1400170f5  lea     rdx, [rsp+250h+var_1F0]
0x1400170fa  xor     ecx, ecx
0x1400170fc  mov     [rax], cx
0x1400170ff  lea     rax, ??_7?$__func@V_lambda_4f9cb091d726181fa859ce89134efc24_@@$$A6AJPEBVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@_NPEA_N@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_4f9cb091d726181fa859ce89134efc24_,long (Windows::Internal::PlatformExtensions::Details::ExtensionRegistration const *,bool,bool *)>::`vftable'
0x140017106  mov     [rsp+250h+var_1E8], rax
0x14001710b  lea     rax, [rsp+250h+var_210]
0x140017110  mov     [rsp+250h+var_1E0], rax
0x140017115  lea     rax, [rsp+250h+var_1F8]
0x14001711a  mov     [rsp+250h+var_1D8], rax
0x14001711f  lea     rax, [rbp+150h+var_170]
0x140017123  mov     [rbp+150h+var_1D0], rax
0x140017127  lea     rax, [rsp+250h+var_220]
0x14001712c  mov     [rbp+150h+var_1C8], rax
0x140017130  lea     rax, [rsp+250h+var_220+4]
0x140017135  mov     [rbp+150h+var_1C0], rax
0x140017139  lea     rax, [rsp+250h+var_1E8]
0x14001713e  mov     byte ptr [rsp+250h+var_220], cl; char *
0x140017142  mov     dword ptr [rsp+250h+var_220+4], ecx
0x140017146  mov     rcx, rsi
0x140017149  mov     [rbp+150h+var_180], rax
0x14001714d  call    ?ForEachEnabledExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@AEBV?$function@$$A6AJPEBVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@_NPEA_N@Z@wistd@@@Z; Windows::Internal::PlatformExtensions::Details::ForEachEnabledExtensionRegistration(HSTRING__ *,wistd::function<long (Windows::Internal::PlatformExtensions::Details::ExtensionRegistration const *,bool,bool *)> const &)
0x140017152  lea     rcx, [rsp+250h+var_1F0]
0x140017157  mov     edi, eax
0x140017159  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x14001715e  test    edi, edi
0x140017160  jns     short loc_14001717F
0x140017162  mov     rcx, [rbp+158h]; this
0x140017169  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x140017170  mov     r9d, edi; char *
0x140017173  mov     edx, 1B7h; void *
0x140017178  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001717d  jmp     short loc_1400171CC
0x14001717f  cmp     byte ptr [rsp+250h+var_220], 0
0x140017184  jnz     short loc_14001718C
0x140017186  cmp     dword ptr [rsp+250h+var_220+4], ebx
0x14001718a  jg      short loc_14001718E
0x14001718c  xor     bl, bl
0x14001718e  mov     rcx, [rbp+158h]; this
0x140017195  lea     rax, aTheProductPlat; "The product platform extension registry"...
0x14001719c  mov     qword ptr [rsp+250h+var_228], rax; bool
0x1400171a1  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x1400171a8  mov     r9d, 8007000Dh; char *
0x1400171ae  mov     [rsp+250h+var_230], bl; char
0x1400171b2  mov     edx, 1BBh; void *
0x1400171b7  call    ?FailFast_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::FailFast_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1400171bc  mov     rdx, [rsp+250h+var_210]; unsigned __int16 *
0x1400171c1  lea     rcx, [rbp+150h+var_170]; this
0x1400171c5  call    ?Stop@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEBG@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::Stop(ushort const *)
0x1400171ca  xor     edi, edi
0x1400171cc  lea     rcx, [rbp+150h+var_170]; this
0x1400171d0  call    ??1TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAA@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::~TryLookupExtensionPointImplementationAcid(void)
0x1400171d5  mov     eax, edi
0x1400171d7  mov     rcx, [rbp+150h+var_20]
0x1400171de  xor     rcx, rsp; StackCookie
0x1400171e1  call    __security_check_cookie
0x1400171e6  mov     rbx, [rsp+250h+arg_10]
0x1400171ee  add     rsp, 240h
0x1400171f5  pop     rdi
0x1400171f6  pop     rsi
0x1400171f7  pop     rbp
0x1400171f8  retn
```
