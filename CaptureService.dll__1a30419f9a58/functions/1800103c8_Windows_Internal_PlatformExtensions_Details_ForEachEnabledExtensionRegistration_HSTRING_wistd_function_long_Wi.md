# Windows::Internal::PlatformExtensions::Details::ForEachEnabledExtensionRegistration(HSTRING__ *,wistd::function<long (Windows::Internal::PlatformExtensions::Details::ExtensionRegistration const *,bool,bool *)> const &)

- ea: `0x1800103c8`
- end: `0x180010561`
- name: `?ForEachEnabledExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@AEBV?$function@$$A6AJPEBVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@_NPEA_N@Z@wistd@@@Z`
- size: `409`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180017520`

## callees

- `0x18000907c`
- `0x1800103c8`
- `0x18001136c`
- `0x1800188fc`
- `0x180022010`

## string_xrefs

- `0x180010428`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180010534`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::ForEachEnabledExtensionRegistration(
        HSTRING a1,
        __int64 a2)
{
  int ExtensionRegistrationsForExtensionPoint; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rsi
  unsigned __int64 i; // rbx
  int v8; // edi
  __int64 v9; // rcx
  __int64 v11; // rdx
  int v12; // [rsp+20h] [rbp-40h]
  __int64 v13; // [rsp+30h] [rbp-30h] BYREF
  __int64 v14; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v15; // [rsp+40h] [rbp-20h] BYREF
  char *v16; // [rsp+48h] [rbp-18h] BYREF
  __int64 v17; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  char v19; // [rsp+90h] [rbp+30h] BYREF
  char v20; // [rsp+98h] [rbp+38h] BYREF

  v14 = 0;
  ExtensionRegistrationsForExtensionPoint = Windows::Internal::PlatformExtensions::Details::GetExtensionRegistrationsForExtensionPoint(a1);
  v4 = ExtensionRegistrationsForExtensionPoint;
  if ( ExtensionRegistrationsForExtensionPoint < 0 )
  {
    v5 = 352;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)ExtensionRegistrationsForExtensionPoint,
      v12);
    goto LABEL_20;
  }
  v15 = 0;
  v6 = v14;
  ExtensionRegistrationsForExtensionPoint = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v14 + 8LL))(
                                              v14,
                                              &v15);
  v4 = ExtensionRegistrationsForExtensionPoint;
  if ( ExtensionRegistrationsForExtensionPoint < 0 )
  {
    v5 = 355;
    goto LABEL_5;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v15 )
      goto LABEL_15;
    v13 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, __int64 *))(*(_QWORD *)v6 + 16LL))(v6, i, &v13);
    if ( v8 < 0 )
      break;
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 40LL))(v13);
      v19 = 0;
      v16 = &v19;
      v20 = 0;
      v17 = v13;
      v9 = *(_QWORD *)(a2 + 112);
      if ( !v9 )
        __fastfail(7u);
      v8 = (*(__int64 (__fastcall **)(__int64, __int64 *, char *, char **))(*(_QWORD *)v9 + 32LL))(v9, &v17, &v20, &v16);
      if ( v8 < 0 )
      {
        v11 = 389;
        goto LABEL_19;
      }
      if ( !v19 )
      {
        wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
          &v13,
          0);
LABEL_15:
        wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
          &v14,
          0);
        return 0;
      }
    }
    wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
      &v13,
      0);
  }
  v11 = 365;
LABEL_19:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
    (const char *)(unsigned int)v8,
    v12);
  wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
    &v13,
    0);
  v4 = v8;
LABEL_20:
  wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
    &v14,
    0);
  return v4;
}

```

## disassembly

```asm
0x1800103c8  mov     [rsp-18h+arg_0], rbx
0x1800103cd  mov     [rsp-18h+arg_8], rsi
0x1800103d2  push    rbp
0x1800103d3  push    rdi
0x1800103d4  push    r14
0x1800103d6  mov     rbp, rsp
0x1800103d9  sub     rsp, 60h
0x1800103dd  mov     r14, rdx
0x1800103e0  mov     [rbp+var_28], 0
0x1800103e8  lea     rdx, [rbp+var_28]
0x1800103ec  call    ?GetExtensionRegistrationsForExtensionPoint@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAV?$unique_ptr@VExtensionRegistrationCollection@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistrationCollection@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@@Z; Windows::Internal::PlatformExtensions::Details::GetExtensionRegistrationsForExtensionPoint(HSTRING__ *,wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollection,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollection>> *)
0x1800103f1  mov     ebx, eax
0x1800103f3  test    eax, eax
0x1800103f5  jns     short loc_1800103FE
0x1800103f7  mov     edx, 160h
0x1800103fc  jmp     short loc_180010428
0x1800103fe  mov     [rbp+var_20], 0
0x180010406  mov     rsi, [rbp+var_28]
0x18001040a  mov     rax, [rsi]
0x18001040d  lea     rdx, [rbp+var_20]
0x180010411  mov     rcx, rsi
0x180010414  mov     rax, [rax+8]
0x180010418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001041d  mov     ebx, eax
0x18001041f  test    eax, eax
0x180010421  jns     short loc_180010440
0x180010423  mov     edx, 163h; void *
0x180010428  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18001042f  mov     r9d, eax; char *
0x180010432  mov     rcx, [rbp+18h]; this
0x180010436  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001043b  jmp     loc_180010552
0x180010440  xor     ebx, ebx
0x180010442  cmp     rbx, [rbp+var_20]
0x180010446  jnb     loc_1800104FC
0x18001044c  mov     [rbp+var_30], 0
0x180010454  mov     rax, [rsi]
0x180010457  lea     r8, [rbp+var_30]
0x18001045b  mov     rdx, rbx
0x18001045e  mov     rcx, rsi
0x180010461  mov     rax, [rax+10h]
0x180010465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001046a  mov     edi, eax
0x18001046c  test    eax, eax
0x18001046e  js      loc_18001052C
0x180010474  mov     rcx, [rbp+var_30]
0x180010478  mov     rax, [rcx]
0x18001047b  mov     rax, [rax+8]
0x18001047f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010484  test    al, al
0x180010486  jnz     short loc_1800104DD
0x180010488  mov     rcx, [rbp+var_30]
0x18001048c  mov     rax, [rcx]
0x18001048f  mov     rax, [rax+28h]
0x180010493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010498  mov     [rbp+arg_10], 0
0x18001049c  lea     rax, [rbp+arg_10]
0x1800104a0  mov     [rbp+var_18], rax
0x1800104a4  mov     [rbp+arg_18], 0
0x1800104a8  mov     rax, [rbp+var_30]
0x1800104ac  mov     [rbp+var_10], rax
0x1800104b0  mov     rcx, [r14+70h]
0x1800104b4  test    rcx, rcx
0x1800104b7  jz      short loc_180010525
0x1800104b9  mov     rax, [rcx]
0x1800104bc  lea     r9, [rbp+var_18]
0x1800104c0  lea     r8, [rbp+arg_18]
0x1800104c4  lea     rdx, [rbp+var_10]
0x1800104c8  mov     rax, [rax+20h]
0x1800104cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104d1  mov     edi, eax
0x1800104d3  test    eax, eax
0x1800104d5  js      short loc_18001051E
0x1800104d7  cmp     [rbp+arg_10], 0
0x1800104db  jz      short loc_1800104F0
0x1800104dd  xor     edx, edx
0x1800104df  lea     rcx, [rbp+var_30]
0x1800104e3  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x1800104e8  inc     rbx
0x1800104eb  jmp     loc_180010442
0x1800104f0  xor     edx, edx
0x1800104f2  lea     rcx, [rbp+var_30]
0x1800104f6  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x1800104fb  nop
0x1800104fc  xor     edx, edx
0x1800104fe  lea     rcx, [rbp+var_28]
0x180010502  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x180010507  xor     eax, eax
0x180010509  lea     r11, [rsp+60h+var_s0]
0x18001050e  mov     rbx, [r11+20h]
0x180010512  mov     rsi, [r11+28h]
0x180010516  mov     rsp, r11
0x180010519  pop     r14
0x18001051b  pop     rdi
0x18001051c  pop     rbp
0x18001051d  retn
0x18001051e  mov     edx, 185h
0x180010523  jmp     short loc_180010531
0x180010525  mov     ecx, 7
0x18001052a  int     29h; Win8: RtlFailFast(ecx)
0x18001052c  mov     edx, 16Dh; void *
0x180010531  mov     r9d, edi; char *
0x180010534  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18001053b  mov     rcx, [rbp+18h]; this
0x18001053f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010544  nop
0x180010545  xor     edx, edx
0x180010547  lea     rcx, [rbp+var_30]
0x18001054b  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x180010550  mov     ebx, edi
0x180010552  xor     edx, edx
0x180010554  lea     rcx, [rbp+var_28]
0x180010558  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x18001055d  mov     eax, ebx
0x18001055f  jmp     short loc_180010509
```
