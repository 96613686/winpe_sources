# Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(HSTRING__ *,ushort *,unsigned __int64,_GUID const *)

- ea: `0x180017520`
- end: `0x180017762`
- name: `?TryLookupExtensionPointImplementationAcid@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAG_KPEBU_GUID@@@Z`
- size: `578`
- prototype: `__int64 __fastcall(HSTRING this, HSTRING, unsigned __int16 *, unsigned __int64, const struct _GUID *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015d0c`

## callees

- `0x180002e60`
- `0x180003bc8`
- `0x180005488`
- `0x180005568`
- `0x18000907c`
- `0x18000e180`
- `0x18000fd50`
- `0x1800103c8`
- `0x1800123bc`
- `0x180014f34`
- `0x180015380`
- `0x180017520`

## string_xrefs

- `0x180017577`: `TryLookupExtensionPointImplementationAcid`
- `0x1800176f6`: `The product platform extension registry is invalid. There are multiple extensions and no default registered for the extension point.`
- `0x1800176cc`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18001770c`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(
        HSTRING this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _OWORD *a4)
{
  char v6; // bl
  void **v7; // rax
  int v8; // edi
  int v10; // [rsp+20h] [rbp-E0h]
  char *v11[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v12; // [rsp+40h] [rbp-C0h] BYREF
  RTL_SRWLOCK *v13; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v14; // [rsp+58h] [rbp-A8h] BYREF
  struct tagComCallData v15[3]; // [rsp+60h] [rbp-A0h] BYREF
  int v16; // [rsp+90h] [rbp-70h] BYREF
  const char *v17; // [rsp+98h] [rbp-68h]
  __int64 v18; // [rsp+A0h] [rbp-60h]
  char v19; // [rsp+A8h] [rbp-58h]
  int v20; // [rsp+B0h] [rbp-50h]
  _BYTE v21[152]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v22; // [rsp+150h] [rbp+50h]
  int v23; // [rsp+160h] [rbp+60h]
  __int64 v24; // [rsp+168h] [rbp+68h]
  void **p_pUserDefined; // [rsp+170h] [rbp+70h]
  __int64 v26; // [rsp+178h] [rbp+78h]
  __int64 v27; // [rsp+180h] [rbp+80h]
  struct tagComCallData *v28; // [rsp+188h] [rbp+88h]
  __int64 v29; // [rsp+190h] [rbp+90h]
  int v30; // [rsp+198h] [rbp+98h]
  int *v31; // [rsp+1A0h] [rbp+A0h]
  char v32; // [rsp+1A8h] [rbp+A8h]
  _BYTE v33[8]; // [rsp+1B0h] [rbp+B0h] BYREF
  _QWORD v34[14]; // [rsp+1B8h] [rbp+B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  v12 = a2;
  v14 = 128;
  LODWORD(v15[0].pUserDefined) = 0;
  BYTE4(v15[0].pUserDefined) = 0;
  v19 = 0;
  v16 = 0;
  v17 = "TryLookupExtensionPointImplementationAcid";
  v18 = 0;
  v20 = 0;
  v22 = 0;
  memset_0(v21, 0, sizeof(v21));
  v6 = 1;
  v23 = 1;
  v24 = 0;
  p_pUserDefined = &v15[0].pUserDefined;
  v26 = 0;
  v27 = 0;
  v28 = v15;
  v29 = 0;
  v30 = 0;
  v31 = &v16;
  v32 = 0;
  *(_QWORD *)&v15[0].dwDispid = &Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::`vftable';
  if ( a4 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      v15,
      &v13);
    v7 = p_pUserDefined;
    *(_OWORD *)(p_pUserDefined + 3) = *a4;
    *((_BYTE *)v7 + 4) = 1;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  }
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(
    (Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *)v15,
    this);
  *v12 = 0;
  LOBYTE(v11[0]) = 0;
  HIDWORD(v11[0]) = 0;
  v34[0] = &wistd::__function::__func<_lambda_4f9cb091d726181fa859ce89134efc24_,long (Windows::Internal::PlatformExtensions::Details::ExtensionRegistration const *,bool,bool *)>::`vftable';
  v34[1] = &v12;
  v34[2] = &v14;
  v34[3] = v15;
  v34[4] = v11;
  v34[5] = (char *)v11 + 4;
  v34[13] = v34;
  v8 = Windows::Internal::PlatformExtensions::Details::ForEachEnabledExtensionRegistration(this, v33);
  wistd::function<void (void)>::~function<void (void)>(v33);
  if ( v8 >= 0 )
  {
    if ( LOBYTE(v11[0]) || SHIDWORD(v11[0]) <= 1 )
      v6 = 0;
    LOBYTE(v10) = v6;
    wil::details::in1diag3::FailFast_HrIfMsg(
      retaddr,
      (void *)0x1BB,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)0x8007000DLL,
      v10,
      (bool)"The product platform extension registry is invalid. There are multiple extensions and no default registered "
            "for the extension point.",
      v11[0]);
    Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::Stop(
      (Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *)v15,
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
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::~TryLookupExtensionPointImplementationAcid(v15);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180017520  mov     [rsp-8+arg_10], rbx
0x180017525  mov     [rsp-8+arg_18], rsi
0x18001752a  push    rbp
0x18001752b  push    rdi
0x18001752c  push    r14
0x18001752e  lea     rbp, [rsp-130h]
0x180017536  sub     rsp, 230h
0x18001753d  mov     rax, cs:__security_cookie
0x180017544  xor     rax, rsp
0x180017547  mov     [rbp+140h+var_18], rax
0x18001754e  mov     rdi, r9
0x180017551  mov     rsi, rcx
0x180017554  mov     [rsp+240h+var_200], rdx
0x180017559  mov     [rsp+240h+var_1E8], 80h
0x180017562  xor     r14d, r14d
0x180017565  mov     [rsp+240h+var_1D8], r14d
0x18001756a  mov     [rsp+240h+var_1D4], r14b
0x18001756f  mov     [rbp+140h+var_198], r14b
0x180017573  mov     [rbp+140h+var_1B0], r14d
0x180017577  lea     rax, aTrylookupexten; "TryLookupExtensionPointImplementationAc"...
0x18001757e  mov     [rbp+140h+var_1A8], rax
0x180017582  mov     [rbp+140h+var_1A0], r14
0x180017586  mov     [rbp+140h+var_190], r14d
0x18001758a  xorps   xmm0, xmm0
0x18001758d  movdqa  [rbp+140h+var_F0], xmm0
0x180017592  xor     edx, edx; Val
0x180017594  mov     r8d, 98h; Size
0x18001759a  lea     rcx, [rbp+140h+var_188]; void *
0x18001759e  call    memset_0
0x1800175a3  lea     ebx, [r14+1]
0x1800175a7  mov     [rbp+140h+var_E0], ebx
0x1800175aa  xor     eax, eax
0x1800175ac  mov     [rbp+140h+var_D8], rax
0x1800175b0  lea     rax, [rsp+240h+var_1D8]
0x1800175b5  mov     [rbp+140h+var_D0], rax
0x1800175b9  mov     [rbp+140h+var_C8], r14
0x1800175bd  mov     [rbp+140h+var_C0], r14
0x1800175c4  lea     rax, [rsp+240h+var_1E0]
0x1800175c9  mov     [rbp+140h+var_B8], rax
0x1800175d0  mov     [rbp+140h+var_B0], r14
0x1800175d7  mov     [rbp+140h+var_A8], r14d
0x1800175de  lea     rax, [rbp+140h+var_1B0]
0x1800175e2  mov     [rbp+140h+var_A0], rax
0x1800175e9  mov     [rbp+140h+var_98], r14b
0x1800175f0  lea     rax, ??_7TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::`vftable'
0x1800175f7  mov     [rsp+240h+var_1E0], rax
0x1800175fc  test    rdi, rdi
0x1800175ff  jz      short loc_180017629
0x180017601  lea     rdx, [rsp+240h+var_1F0]
0x180017606  lea     rcx, [rsp+240h+var_1E0]
0x18001760b  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180017610  mov     rax, [rbp+140h+var_D0]
0x180017614  movups  xmm0, xmmword ptr [rdi]
0x180017617  movdqu  xmmword ptr [rax+18h], xmm0
0x18001761c  mov     [rax+4], bl
0x18001761f  lea     rcx, [rsp+240h+var_1F0]
0x180017624  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180017629  mov     rdx, rsi; HSTRING
0x18001762c  lea     rcx, [rsp+240h+var_1E0]; this
0x180017631  call    ?StartActivity@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(HSTRING__ *)
0x180017636  mov     rax, [rsp+240h+var_200]
0x18001763b  mov     [rax], r14w
0x18001763f  mov     byte ptr [rsp+240h+var_210], r14b; char *
0x180017644  mov     dword ptr [rsp+240h+var_210+4], r14d
0x180017649  lea     rax, ??_7?$__func@V_lambda_4f9cb091d726181fa859ce89134efc24_@@$$A6AJPEBVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@_NPEA_N@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_4f9cb091d726181fa859ce89134efc24_,long (Windows::Internal::PlatformExtensions::Details::ExtensionRegistration const *,bool,bool *)>::`vftable'
0x180017650  mov     [rbp+140h+var_88], rax
0x180017657  lea     rax, [rsp+240h+var_200]
0x18001765c  mov     [rbp+140h+var_80], rax
0x180017663  lea     rax, [rsp+240h+var_1E8]
0x180017668  mov     [rbp+140h+var_78], rax
0x18001766f  lea     rax, [rsp+240h+var_1E0]
0x180017674  mov     [rbp+140h+var_70], rax
0x18001767b  lea     rax, [rsp+240h+var_210]
0x180017680  mov     [rbp+140h+var_68], rax
0x180017687  lea     rax, [rsp+240h+var_210+4]
0x18001768c  mov     [rbp+140h+var_60], rax
0x180017693  lea     rax, [rbp+140h+var_88]
0x18001769a  mov     [rbp+140h+var_20], rax
0x1800176a1  lea     rdx, [rbp+140h+var_90]
0x1800176a8  mov     rcx, rsi
0x1800176ab  call    ?ForEachEnabledExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@AEBV?$function@$$A6AJPEBVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@_NPEA_N@Z@wistd@@@Z; Windows::Internal::PlatformExtensions::Details::ForEachEnabledExtensionRegistration(HSTRING__ *,wistd::function<long (Windows::Internal::PlatformExtensions::Details::ExtensionRegistration const *,bool,bool *)> const &)
0x1800176b0  mov     edi, eax
0x1800176b2  lea     rcx, [rbp+140h+var_90]
0x1800176b9  call    ??1?$function@$$A6AXXZ@wistd@@QEAA@XZ; wistd::function<void (void)>::~function<void (void)>(void)
0x1800176be  test    edi, edi
0x1800176c0  jns     short loc_1800176DF
0x1800176c2  mov     rcx, [rbp+148h]; this
0x1800176c9  mov     r9d, edi; char *
0x1800176cc  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x1800176d3  mov     edx, 1B7h; void *
0x1800176d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800176dd  jmp     short loc_18001772F
0x1800176df  cmp     byte ptr [rsp+240h+var_210], r14b
0x1800176e4  jnz     short loc_1800176EC
0x1800176e6  cmp     dword ptr [rsp+240h+var_210+4], ebx
0x1800176ea  jg      short loc_1800176EF
0x1800176ec  mov     bl, r14b
0x1800176ef  mov     rcx, [rbp+148h]; this
0x1800176f6  lea     rax, aTheProductPlat; "The product platform extension registry"...
0x1800176fd  mov     qword ptr [rsp+240h+var_218], rax; bool
0x180017702  mov     byte ptr [rsp+240h+var_220], bl; int
0x180017706  mov     r9d, 8007000Dh; char *
0x18001770c  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180017713  mov     edx, 1BBh; void *
0x180017718  call    ?FailFast_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::FailFast_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001771d  mov     rdx, [rsp+240h+var_200]; unsigned __int16 *
0x180017722  lea     rcx, [rsp+240h+var_1E0]; this
0x180017727  call    ?Stop@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEBG@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::Stop(ushort const *)
0x18001772c  mov     edi, r14d
0x18001772f  lea     rcx, [rsp+240h+var_1E0]; this
0x180017734  call    ??1TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAA@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::~TryLookupExtensionPointImplementationAcid(void)
0x180017739  mov     eax, edi
0x18001773b  mov     rcx, [rbp+140h+var_18]
0x180017742  xor     rcx, rsp; StackCookie
0x180017745  call    __security_check_cookie
0x18001774a  lea     r11, [rsp+240h+var_10]
0x180017752  mov     rbx, [r11+30h]
0x180017756  mov     rsi, [r11+38h]
0x18001775a  mov     rsp, r11
0x18001775d  pop     r14
0x18001775f  pop     rdi
0x180017760  pop     rbp
0x180017761  retn
```
