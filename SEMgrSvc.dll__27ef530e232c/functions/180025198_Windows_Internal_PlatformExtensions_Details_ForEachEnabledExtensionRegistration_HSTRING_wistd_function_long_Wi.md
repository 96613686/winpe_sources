# Windows::Internal::PlatformExtensions::Details::ForEachEnabledExtensionRegistration(HSTRING__ *,wistd::function<long (Windows::Internal::PlatformExtensions::Details::ExtensionRegistration const *,bool,bool *)> const &)

- ea: `0x180025198`
- end: `0x180025530`
- name: `?ForEachEnabledExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@AEBV?$function@$$A6AJPEBVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@_NPEA_N@Z@wistd@@@Z`
- size: `920`
- prototype: `__int64 __fastcall(HSTRING string)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18002d124`

## callees

- `0x1800049a0`
- `0x1800049c4`
- `0x180004e9c`
- `0x18000c964`
- `0x18000d4ec`
- `0x18000e4b8`
- `0x180025198`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800252d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800252d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800252eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800252eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025202`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025202`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025263`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800252e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025263`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800252e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800252b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800252b9`

## string_xrefs

- `0x18002522e`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180025249`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180025325`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180025477`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x1800254d1`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x1800254ec`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

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
  HKEY v8; // rcx
  HKEY v9; // r12
  HKEY v10; // r15
  DWORD LastError; // edi
  int v12; // eax
  __int64 v13; // rdi
  int v14; // r14d
  __int64 v15; // rcx
  void (__fastcall ***v16)(_QWORD, __int64); // rcx
  bool v17; // zf
  void (__fastcall ***v19)(_QWORD, __int64); // rcx
  __int64 v20; // rdx
  void (__fastcall ***v21)(_QWORD, __int64); // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResultc; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  char v26; // [rsp+30h] [rbp-D0h] BYREF
  char v27[8]; // [rsp+38h] [rbp-C8h] BYREF
  void (__fastcall ***v28)(_QWORD, __int64); // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  HKEY *v30; // [rsp+50h] [rbp-B0h]
  HKEY v31; // [rsp+58h] [rbp-A8h] BYREF
  char v32; // [rsp+60h] [rbp-A0h]
  char *v33; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v34[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[128]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v4 = (HKEY *)operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v4 )
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x155,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)0x8007000ELL,
      phkResult);
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x160,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)v7,
      phkResulta);
    return v7;
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
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)v6,
      phkResult);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x156,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)v7,
      phkResultc);
    v8 = v4[1];
    if ( v8 )
      RegCloseKey(v8);
    *v4 = (HKEY)&Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollection::`vftable';
    operator delete(v4);
    goto LABEL_30;
  }
  v30 = v4 + 1;
  v31 = 0;
  v32 = 1;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &v31);
  if ( v32 )
  {
    v9 = v31;
    v10 = *v30;
    if ( *v30 )
    {
      LastError = GetLastError();
      RegCloseKey(v10);
      SetLastError(LastError);
    }
    *v30 = v9;
  }
  v34[1] = v4;
  v29 = 0;
  v12 = (*((__int64 (__fastcall **)(HKEY *, unsigned __int64 *))*v4 + 1))(v4, &v29);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)v12,
      phkResultb);
    (*(void (__fastcall **)(HKEY *, __int64))*v4)(v4, 1);
    return v7;
  }
  v13 = 0;
  if ( v29 )
  {
    while ( 1 )
    {
      v28 = 0;
      v14 = (*((__int64 (__fastcall **)(HKEY *, __int64, void (__fastcall ****)(_QWORD, __int64)))*v4 + 2))(
              v4,
              v13,
              &v28);
      if ( v14 < 0 )
        break;
      if ( !((unsigned __int8 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64)))(*v28)[1])(v28) )
      {
        ((void (__fastcall *)(void (__fastcall ***)(_QWORD, __int64)))(*v28)[5])(v28);
        v26 = 0;
        v33 = &v26;
        v27[0] = 0;
        v34[0] = v28;
        v15 = *(_QWORD *)(a2 + 112);
        if ( !v15 )
          wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
        v14 = (*(__int64 (__fastcall **)(__int64, _QWORD *, char *, char **))(*(_QWORD *)v15 + 32LL))(
                v15,
                v34,
                v27,
                &v33);
        if ( v14 < 0 )
        {
          v20 = 389;
          goto LABEL_26;
        }
        if ( !v26 )
        {
          v19 = v28;
          v28 = 0;
          if ( v19 )
            (**v19)(v19, 1);
          goto LABEL_21;
        }
      }
      v16 = v28;
      v17 = v28 == 0;
      v28 = 0;
      if ( !v17 )
        (**v16)(v16, 1);
      if ( ++v13 >= v29 )
        goto LABEL_21;
    }
    v20 = 365;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)v14,
      phkResultb);
    v21 = v28;
    v17 = v28 == 0;
    v28 = 0;
    if ( !v17 )
      (**v21)(v21, 1);
    (*(void (__fastcall **)(HKEY *, __int64))*v4)(v4, 1);
    return (unsigned int)v14;
  }
  else
  {
LABEL_21:
    (*(void (__fastcall **)(HKEY *, __int64))*v4)(v4, 1);
    return 0;
  }
}

```

## disassembly

```asm
0x180025198  mov     [rsp-8+arg_10], rbx
0x18002519d  push    rbp
0x18002519e  push    rsi
0x18002519f  push    rdi
0x1800251a0  push    r12
0x1800251a2  push    r13
0x1800251a4  push    r14
0x1800251a6  push    r15
0x1800251a8  lea     rbp, [rsp-90h]
0x1800251b0  sub     rsp, 190h
0x1800251b7  mov     rax, cs:__security_cookie
0x1800251be  xor     rax, rsp
0x1800251c1  mov     [rbp+0C0h+var_40], rax
0x1800251c8  mov     r13, rdx
0x1800251cb  mov     rdi, rcx
0x1800251ce  xor     r15d, r15d
0x1800251d1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800251d8  lea     esi, [r15+10h]
0x1800251dc  mov     ecx, esi; unsigned __int64
0x1800251de  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800251e3  mov     rbx, rax
0x1800251e6  test    rax, rax
0x1800251e9  jz      loc_1800254C2
0x1800251ef  lea     rax, ??_7ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`vftable'
0x1800251f6  mov     [rbx], rax
0x1800251f9  mov     [rbx+8], r15
0x1800251fd  xor     edx, edx; length
0x1800251ff  mov     rcx, rdi; string
0x180025202  call    cs:__imp_WindowsGetStringRawBuffer
0x180025208  mov     r9, rax
0x18002520b  lea     r8, aSoftwareClasse; "SOFTWARE\\Classes\\OneCoreContracts\\%s"
0x180025212  lea     edx, [rsi+70h]; unsigned __int64
0x180025215  lea     rcx, [rbp+0C0h+SubKey]; unsigned __int16 *
0x180025219  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002521e  mov     edi, eax
0x180025220  test    eax, eax
0x180025222  jns     short loc_180025283
0x180025224  mov     rcx, [rbp+0C8h]; this
0x18002522b  mov     r9d, eax; char *
0x18002522e  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180025235  mov     edx, 129h; void *
0x18002523a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002523f  mov     rcx, [rbp+0C8h]; this
0x180025246  mov     r9d, edi; char *
0x180025249  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180025250  mov     edx, 156h; void *
0x180025255  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002525a  mov     rcx, [rbx+8]; hKey
0x18002525e  test    rcx, rcx
0x180025261  jz      short loc_180025269
0x180025263  call    cs:__imp_RegCloseKey
0x180025269  lea     rax, ??_7ExtensionRegistrationCollection@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollection::`vftable'
0x180025270  mov     [rbx], rax
0x180025273  mov     rdx, rsi
0x180025276  mov     rcx, rbx; Block
0x180025279  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002527e  jmp     loc_1800254E2
0x180025283  lea     rax, [rbx+8]
0x180025287  mov     [rsp+1C0h+var_170], rax
0x18002528c  mov     [rsp+1C0h+var_168], r15
0x180025291  mov     esi, 1
0x180025296  mov     [rsp+1C0h+var_160], sil
0x18002529b  lea     rax, [rsp+1C0h+var_168]
0x1800252a0  mov     qword ptr [rsp+1C0h+phkResult], rax; int
0x1800252a5  mov     r9d, 20019h; samDesired
0x1800252ab  xor     r8d, r8d; ulOptions
0x1800252ae  lea     rdx, [rbp+0C0h+SubKey]; lpSubKey
0x1800252b2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800252b9  call    cs:__imp_RegOpenKeyExW
0x1800252bf  cmp     [rsp+1C0h+var_160], r15b
0x1800252c4  jz      short loc_1800252F7
0x1800252c6  mov     r12, [rsp+1C0h+var_168]
0x1800252cb  mov     r14, [rsp+1C0h+var_170]
0x1800252d0  mov     r15, [r14]
0x1800252d3  test    r15, r15
0x1800252d6  jz      short loc_1800252F1
0x1800252d8  call    cs:__imp_GetLastError
0x1800252de  mov     edi, eax
0x1800252e0  mov     rcx, r15; hKey
0x1800252e3  call    cs:__imp_RegCloseKey
0x1800252e9  mov     ecx, edi; dwErrCode
0x1800252eb  call    cs:__imp_SetLastError
0x1800252f1  mov     [r14], r12
0x1800252f4  xor     r15d, r15d
0x1800252f7  mov     [rsp+1C0h+var_148], rbx
0x1800252fc  mov     [rsp+1C0h+var_178], r15
0x180025301  mov     rax, [rbx]
0x180025304  lea     rdx, [rsp+1C0h+var_178]
0x180025309  mov     rcx, rbx
0x18002530c  mov     rax, [rax+8]
0x180025310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025315  mov     edi, eax
0x180025317  test    eax, eax
0x180025319  jns     short loc_180025355
0x18002531b  mov     rcx, [rbp+0C8h]; this
0x180025322  mov     r9d, eax; char *
0x180025325  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18002532c  mov     edx, 163h; void *
0x180025331  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025336  nop
0x180025337  test    rbx, rbx
0x18002533a  jz      loc_1800254FE
0x180025340  mov     rax, [rbx]
0x180025343  mov     edx, esi
0x180025345  mov     rcx, rbx
0x180025348  mov     rax, [rax]
0x18002534b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025350  jmp     loc_1800254FE
0x180025355  mov     rdi, r15
0x180025358  cmp     [rsp+1C0h+var_178], r15
0x18002535d  jbe     loc_18002542E
0x180025363  mov     [rsp+1C0h+var_180], r15
0x180025368  mov     rax, [rbx]
0x18002536b  lea     r8, [rsp+1C0h+var_180]
0x180025370  mov     rdx, rdi
0x180025373  mov     rcx, rbx
0x180025376  mov     rax, [rax+10h]
0x18002537a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002537f  mov     r14d, eax
0x180025382  test    eax, eax
0x180025384  js      loc_18002546F
0x18002538a  mov     rcx, [rsp+1C0h+var_180]
0x18002538f  mov     rax, [rcx]
0x180025392  mov     rax, [rax+8]
0x180025396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002539b  test    al, al
0x18002539d  jnz     short loc_180025404
0x18002539f  mov     rcx, [rsp+1C0h+var_180]
0x1800253a4  mov     rax, [rcx]
0x1800253a7  mov     rax, [rax+28h]
0x1800253ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253b0  mov     [rsp+1C0h+var_190], r15b
0x1800253b5  lea     rax, [rsp+1C0h+var_190]
0x1800253ba  mov     [rsp+1C0h+var_158], rax
0x1800253bf  mov     [rsp+1C0h+var_188], r15b
0x1800253c4  mov     rax, [rsp+1C0h+var_180]
0x1800253c9  mov     [rsp+1C0h+var_150], rax
0x1800253ce  mov     rcx, [r13+70h]; this
0x1800253d2  test    rcx, rcx
0x1800253d5  jz      loc_18002552A
0x1800253db  mov     rax, [rcx]
0x1800253de  lea     r9, [rsp+1C0h+var_158]
0x1800253e3  lea     r8, [rsp+1C0h+var_188]
0x1800253e8  lea     rdx, [rsp+1C0h+var_150]
0x1800253ed  mov     rax, [rax+20h]
0x1800253f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253f6  mov     r14d, eax
0x1800253f9  test    eax, eax
0x1800253fb  js      short loc_180025468
0x1800253fd  cmp     [rsp+1C0h+var_190], r15b
0x180025402  jz      short loc_18002544A
0x180025404  mov     rcx, [rsp+1C0h+var_180]
0x180025409  test    rcx, rcx
0x18002540c  mov     [rsp+1C0h+var_180], r15
0x180025411  jz      short loc_180025420
0x180025413  mov     rax, [rcx]
0x180025416  mov     edx, esi
0x180025418  mov     rax, [rax]
0x18002541b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025420  add     rdi, rsi
0x180025423  cmp     rdi, [rsp+1C0h+var_178]
0x180025428  jb      loc_180025363
0x18002542e  test    rbx, rbx
0x180025431  jz      short loc_180025443
0x180025433  mov     rax, [rbx]
0x180025436  mov     edx, esi
0x180025438  mov     rcx, rbx
0x18002543b  mov     rax, [rax]
0x18002543e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025443  xor     eax, eax
0x180025445  jmp     loc_180025500
0x18002544a  mov     rcx, [rsp+1C0h+var_180]
0x18002544f  mov     [rsp+1C0h+var_180], r15
0x180025454  test    rcx, rcx
0x180025457  jz      short loc_18002542E
0x180025459  mov     rax, [rcx]
0x18002545c  mov     edx, esi
0x18002545e  mov     rax, [rax]
0x180025461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025466  jmp     short loc_18002542E
0x180025468  mov     edx, 185h
0x18002546d  jmp     short loc_180025474
0x18002546f  mov     edx, 16Dh; void *
0x180025474  mov     r9d, r14d; char *
0x180025477  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18002547e  mov     rcx, [rbp+0C8h]; this
0x180025485  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002548a  nop
0x18002548b  mov     rcx, [rsp+1C0h+var_180]
0x180025490  test    rcx, rcx
0x180025493  mov     [rsp+1C0h+var_180], r15
0x180025498  jz      short loc_1800254A8
0x18002549a  mov     rax, [rcx]
0x18002549d  mov     edx, esi
0x18002549f  mov     rax, [rax]
0x1800254a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254a7  nop
0x1800254a8  test    rbx, rbx
0x1800254ab  jz      short loc_1800254BD
0x1800254ad  mov     rax, [rbx]
0x1800254b0  mov     edx, esi
0x1800254b2  mov     rcx, rbx
0x1800254b5  mov     rax, [rax]
0x1800254b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254bd  mov     eax, r14d
0x1800254c0  jmp     short loc_180025500
0x1800254c2  mov     rcx, [rbp+0C8h]; this
0x1800254c9  mov     edi, 8007000Eh
0x1800254ce  mov     r9d, edi; char *
0x1800254d1  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\platf"...
0x1800254d8  mov     edx, 155h; void *
0x1800254dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800254e2  mov     rcx, [rbp+0C8h]; this
0x1800254e9  mov     r9d, edi; char *
0x1800254ec  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\platf"...
0x1800254f3  mov     edx, 160h; void *
0x1800254f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800254fd  nop
0x1800254fe  mov     eax, edi
0x180025500  mov     rcx, [rbp+0C0h+var_40]
0x180025507  xor     rcx, rsp; StackCookie
0x18002550a  call    __security_check_cookie
0x18002550f  mov     rbx, [rsp+1C0h+arg_10]
0x180025517  add     rsp, 190h
0x18002551e  pop     r15
0x180025520  pop     r14
0x180025522  pop     r13
0x180025524  pop     r12
0x180025526  pop     rdi
0x180025527  pop     rsi
0x180025528  pop     rbp
0x180025529  retn
0x18002552a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
