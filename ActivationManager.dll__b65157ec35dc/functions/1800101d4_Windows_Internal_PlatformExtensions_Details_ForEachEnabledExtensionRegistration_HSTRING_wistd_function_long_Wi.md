# Windows::Internal::PlatformExtensions::Details::ForEachEnabledExtensionRegistration(HSTRING__ *,wistd::function<long (Windows::Internal::PlatformExtensions::Details::ExtensionRegistration const *,bool,bool *)> const &)

- ea: `0x1800101d4`
- end: `0x18001050c`
- name: `?ForEachEnabledExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@AEBV?$function@$$A6AJPEBVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@_NPEA_N@Z@wistd@@@Z`
- size: `824`
- prototype: `__int64 __fastcall(HSTRING string)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ef28`

## callees

- `0x18000b5c0`
- `0x1800101d4`
- `0x180010514`
- `0x18003afb4`
- `0x18003b450`
- `0x180047048`
- `0x180047068`
- `0x18005ae90`
- `0x18005b37c`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010236`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010236`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800102fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800102fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800102d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800102d1`

## string_xrefs

- `0x180010264`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x18001027f`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x180010342`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x180010477`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x1800104b7`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x1800104d2`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::ForEachEnabledExtensionRegistration(
        HSTRING string,
        __int64 a2)
{
  HKEY *v4; // rbx
  PCWSTR StringRawBuffer; // rax
  int v6; // eax
  unsigned int v7; // edi
  HKEY v8; // r14
  HKEY *v9; // rdi
  HKEY v10; // rsi
  int v11; // eax
  unsigned __int64 i; // rdi
  int v13; // eax
  unsigned int v14; // esi
  __int64 v15; // rcx
  __int64 v17; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResultc; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  char v22; // [rsp+30h] [rbp-D0h] BYREF
  char v23[8]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  HKEY *v26; // [rsp+50h] [rbp-B0h]
  HKEY v27; // [rsp+58h] [rbp-A8h] BYREF
  char v28; // [rsp+60h] [rbp-A0h]
  char *v29; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h] BYREF
  HKEY *v31; // [rsp+78h] [rbp-88h] BYREF
  WCHAR SubKey[128]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v4 = (HKEY *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x155,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
      (const char *)0x8007000ELL,
      phkResult);
    goto LABEL_25;
  }
  *v4 = (HKEY)&Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`vftable';
  v4[1] = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v6 = StringCchPrintfW(SubKey, 0x80u, L"SOFTWARE\\Classes\\OneCoreContracts\\%s", StringRawBuffer);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x129,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
      (const char *)(unsigned int)v6,
      phkResult);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x156,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
      (const char *)v7,
      phkResultc);
    Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`scalar deleting destructor'(
      (Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *)v4,
      1u);
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x160,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
      (const char *)v7,
      phkResulta);
    return v7;
  }
  v26 = v4 + 1;
  v27 = 0;
  v28 = 1;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &v27);
  if ( v28 )
  {
    v8 = v27;
    v9 = v26;
    v10 = *v26;
    if ( *v26 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v24);
      RegCloseKey(v10);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v24);
    }
    *v9 = v8;
  }
  v31 = v4;
  v25 = 0;
  v11 = (*((__int64 (__fastcall **)(HKEY *, unsigned __int64 *))*v4 + 1))(v4, &v25);
  v7 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
      (const char *)(unsigned int)v11,
      phkResultb);
    (*(void (__fastcall **)(HKEY *, __int64))*v4)(v4, 1);
    return v7;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v25 )
      goto LABEL_19;
    v24 = 0;
    v13 = (*((__int64 (__fastcall **)(HKEY *, unsigned __int64, __int64 *))*v4 + 2))(v4, i, &v24);
    v14 = v13;
    if ( v13 < 0 )
      break;
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 40LL))(v24);
      v22 = 0;
      v29 = &v22;
      v23[0] = 0;
      v30 = v24;
      v15 = *(_QWORD *)(a2 + 112);
      if ( !v15 )
        __fastfail(7u);
      v13 = (*(__int64 (__fastcall **)(__int64, __int64 *, char *, char **))(*(_QWORD *)v15 + 32LL))(
              v15,
              &v30,
              v23,
              &v29);
      v14 = v13;
      if ( v13 < 0 )
      {
        v17 = 389;
        goto LABEL_23;
      }
      if ( !v22 )
      {
        wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
          &v24,
          0);
LABEL_19:
        (*(void (__fastcall **)(HKEY *, __int64))*v4)(v4, 1);
        return 0;
      }
    }
    wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
      &v24,
      0);
  }
  v17 = 365;
LABEL_23:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v17,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
    (const char *)(unsigned int)v13,
    phkResultb);
  wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
    &v24,
    0);
  wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
    &v31,
    0);
  return v14;
}

```

## disassembly

```asm
0x1800101d4  mov     [rsp-8+arg_10], rbx
0x1800101d9  push    rbp
0x1800101da  push    rsi
0x1800101db  push    rdi
0x1800101dc  push    r14
0x1800101de  push    r15
0x1800101e0  lea     rbp, [rsp-90h]
0x1800101e8  sub     rsp, 190h
0x1800101ef  mov     rax, cs:__security_cookie
0x1800101f6  xor     rax, rsp
0x1800101f9  mov     [rbp+0B0h+var_30], rax
0x180010200  mov     r15, rdx
0x180010203  mov     rdi, rcx
0x180010206  xor     esi, esi
0x180010208  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001020f  lea     ecx, [rsi+10h]; unsigned __int64
0x180010212  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010217  mov     rbx, rax
0x18001021a  test    rax, rax
0x18001021d  jz      loc_1800104A8
0x180010223  lea     rax, ??_7ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`vftable'
0x18001022a  mov     [rbx], rax
0x18001022d  mov     [rbx+8], rsi
0x180010231  xor     edx, edx; length
0x180010233  mov     rcx, rdi; string
0x180010236  call    cs:__imp_WindowsGetStringRawBuffer
0x18001023c  mov     r9, rax
0x18001023f  lea     r8, aSoftwareClasse; "SOFTWARE\\Classes\\OneCoreContracts\\%s"
0x180010246  mov     edx, 80h; unsigned __int64
0x18001024b  lea     rcx, [rbp+0B0h+SubKey]; unsigned __int16 *
0x18001024f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010254  mov     edi, eax
0x180010256  test    eax, eax
0x180010258  jns     short loc_1800102A0
0x18001025a  mov     rcx, [rbp+0B8h]; this
0x180010261  mov     r9d, eax; char *
0x180010264  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x18001026b  mov     edx, 129h; void *
0x180010270  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010275  mov     rcx, [rbp+0B8h]; this
0x18001027c  mov     r9d, edi; char *
0x18001027f  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180010286  mov     edx, 156h; void *
0x18001028b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010290  lea     edx, [rsi+1]; unsigned int
0x180010293  mov     rcx, rbx; this
0x180010296  call    ??_GExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@UEAAPEAXI@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`scalar deleting destructor'(uint)
0x18001029b  jmp     loc_1800104C8
0x1800102a0  lea     rax, [rbx+8]
0x1800102a4  mov     [rsp+1B0h+var_160], rax
0x1800102a9  mov     [rsp+1B0h+var_158], rsi
0x1800102ae  mov     [rsp+1B0h+var_150], 1
0x1800102b3  lea     rax, [rsp+1B0h+var_158]
0x1800102b8  mov     qword ptr [rsp+1B0h+phkResult], rax; int
0x1800102bd  mov     r9d, 20019h; samDesired
0x1800102c3  xor     r8d, r8d; ulOptions
0x1800102c6  lea     rdx, [rbp+0B0h+SubKey]; lpSubKey
0x1800102ca  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800102d1  call    cs:__imp_RegOpenKeyExW
0x1800102d7  cmp     [rsp+1B0h+var_150], sil
0x1800102dc  jz      short loc_180010310
0x1800102de  mov     r14, [rsp+1B0h+var_158]
0x1800102e3  mov     rdi, [rsp+1B0h+var_160]
0x1800102e8  mov     rsi, [rdi]
0x1800102eb  test    rsi, rsi
0x1800102ee  jz      short loc_18001030D
0x1800102f0  lea     rcx, [rsp+1B0h+var_170]; this
0x1800102f5  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800102fa  mov     rcx, rsi; hKey
0x1800102fd  call    cs:__imp_RegCloseKey
0x180010303  lea     rcx, [rsp+1B0h+var_170]; this
0x180010308  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001030d  mov     [rdi], r14
0x180010310  mov     [rsp+1B0h+var_138], rbx
0x180010315  mov     [rsp+1B0h+var_168], 0
0x18001031e  mov     rax, [rbx]
0x180010321  lea     rdx, [rsp+1B0h+var_168]
0x180010326  mov     rcx, rbx
0x180010329  mov     rax, [rax+8]
0x18001032d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010332  mov     edi, eax
0x180010334  test    eax, eax
0x180010336  jns     short loc_180010375
0x180010338  mov     rcx, [rbp+0B8h]; this
0x18001033f  mov     r9d, eax; char *
0x180010342  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180010349  mov     edx, 163h; void *
0x18001034e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010353  nop
0x180010354  test    rbx, rbx
0x180010357  jz      loc_1800104E4
0x18001035d  mov     rcx, [rbx]
0x180010360  mov     rax, [rcx]
0x180010363  mov     edx, 1
0x180010368  mov     rcx, rbx
0x18001036b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010370  jmp     loc_1800104E4
0x180010375  xor     edi, edi
0x180010377  cmp     rdi, [rsp+1B0h+var_168]
0x18001037c  jnb     loc_180010442
0x180010382  mov     [rsp+1B0h+var_170], 0
0x18001038b  mov     rax, [rbx]
0x18001038e  lea     r8, [rsp+1B0h+var_170]
0x180010393  mov     rdx, rdi
0x180010396  mov     rcx, rbx
0x180010399  mov     rax, [rax+10h]
0x18001039d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103a2  mov     esi, eax
0x1800103a4  test    eax, eax
0x1800103a6  js      loc_18001046F
0x1800103ac  mov     rcx, [rsp+1B0h+var_170]
0x1800103b1  mov     rax, [rcx]
0x1800103b4  mov     rax, [rax+8]
0x1800103b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103bd  test    al, al
0x1800103bf  jnz     short loc_180010421
0x1800103c1  mov     rcx, [rsp+1B0h+var_170]
0x1800103c6  mov     rax, [rcx]
0x1800103c9  mov     rax, [rax+28h]
0x1800103cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103d2  mov     [rsp+1B0h+var_180], 0
0x1800103d7  lea     rax, [rsp+1B0h+var_180]
0x1800103dc  mov     [rsp+1B0h+var_148], rax
0x1800103e1  mov     [rsp+1B0h+var_178], 0
0x1800103e6  mov     rax, [rsp+1B0h+var_170]
0x1800103eb  mov     [rsp+1B0h+var_140], rax
0x1800103f0  mov     rcx, [r15+70h]
0x1800103f4  test    rcx, rcx
0x1800103f7  jz      short loc_180010468
0x1800103f9  mov     rax, [rcx]
0x1800103fc  lea     r9, [rsp+1B0h+var_148]
0x180010401  lea     r8, [rsp+1B0h+var_178]
0x180010406  lea     rdx, [rsp+1B0h+var_140]
0x18001040b  mov     rax, [rax+20h]
0x18001040f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010414  mov     esi, eax
0x180010416  test    eax, eax
0x180010418  js      short loc_180010461
0x18001041a  cmp     [rsp+1B0h+var_180], 0
0x18001041f  jz      short loc_180010435
0x180010421  xor     edx, edx
0x180010423  lea     rcx, [rsp+1B0h+var_170]
0x180010428  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x18001042d  inc     rdi
0x180010430  jmp     loc_180010377
0x180010435  xor     edx, edx
0x180010437  lea     rcx, [rsp+1B0h+var_170]
0x18001043c  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x180010441  nop
0x180010442  test    rbx, rbx
0x180010445  jz      short loc_18001045A
0x180010447  mov     rax, [rbx]
0x18001044a  mov     edx, 1
0x18001044f  mov     rcx, rbx
0x180010452  mov     rax, [rax]
0x180010455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001045a  xor     eax, eax
0x18001045c  jmp     loc_1800104E6
0x180010461  mov     edx, 185h
0x180010466  jmp     short loc_180010474
0x180010468  mov     ecx, 7
0x18001046d  int     29h; Win8: RtlFailFast(ecx)
0x18001046f  mov     edx, 16Dh; void *
0x180010474  mov     r9d, eax; char *
0x180010477  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x18001047e  mov     rcx, [rbp+0B8h]; this
0x180010485  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001048a  nop
0x18001048b  xor     edx, edx
0x18001048d  lea     rcx, [rsp+1B0h+var_170]
0x180010492  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x180010497  nop
0x180010498  xor     edx, edx
0x18001049a  lea     rcx, [rsp+1B0h+var_138]
0x18001049f  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x1800104a4  mov     eax, esi
0x1800104a6  jmp     short loc_1800104E6
0x1800104a8  mov     rcx, [rbp+0B8h]; this
0x1800104af  mov     edi, 8007000Eh
0x1800104b4  mov     r9d, edi; char *
0x1800104b7  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x1800104be  mov     edx, 155h; void *
0x1800104c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800104c8  mov     rcx, [rbp+0B8h]; this
0x1800104cf  mov     r9d, edi; char *
0x1800104d2  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x1800104d9  mov     edx, 160h; void *
0x1800104de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800104e3  nop
0x1800104e4  mov     eax, edi
0x1800104e6  mov     rcx, [rbp+0B0h+var_30]
0x1800104ed  xor     rcx, rsp; StackCookie
0x1800104f0  call    __security_check_cookie
0x1800104f5  mov     rbx, [rsp+1B0h+arg_10]
0x1800104fd  add     rsp, 190h
0x180010504  pop     r15
0x180010506  pop     r14
0x180010508  pop     rdi
0x180010509  pop     rsi
0x18001050a  pop     rbp
0x18001050b  retn
```
