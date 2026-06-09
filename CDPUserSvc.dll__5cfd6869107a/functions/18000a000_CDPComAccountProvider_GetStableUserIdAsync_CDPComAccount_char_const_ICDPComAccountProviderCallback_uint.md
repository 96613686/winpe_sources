# CDPComAccountProvider::GetStableUserIdAsync(CDPComAccount *,char const *,ICDPComAccountProviderCallback *,uint *)

- ea: `0x18000a000`
- end: `0x18000a236`
- name: `?GetStableUserIdAsync@CDPComAccountProvider@@UEAAJPEAUCDPComAccount@@PEBDPEAUICDPComAccountProviderCallback@@PEAI@Z`
- size: `566`
- prototype: `__int64 __fastcall(CDPComAccountProvider *__hidden this, struct CDPComAccount *, const char *, struct ICDPComAccountProviderCallback *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180003678`
- `0x180004eb0`
- `0x1800097d0`
- `0x180009ae0`
- `0x18000a000`
- `0x18000a2c0`
- `0x180020cc4`
- `0x180064010`

## import_xrefs

- `cdp!CDPCreateAccountInternalForUser` at `0x18000a080`
- `cdp!CDPCreateAccountInternalForUser` at `0x18000a080`

## string_xrefs

- `0x18000a12a`: `..\cdpcomaccountprovider.cpp`
- `0x18000a15e`: `..\cdpcomaccountprovider.cpp`
- `0x18000a1b9`: `..\cdpcomaccountprovider.cpp`
- `0x18000a1ef`: `..\cdpcomaccountprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDPComAccountProvider::GetStableUserIdAsync(
        CDPComAccountProvider *this,
        struct CDPComAccount *a2,
        const char *a3,
        struct ICDPComAccountProviderCallback *a4,
        unsigned int *a5)
{
  int v8; // eax
  int CurrentUserContextToken; // eax
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v20; // rcx
  unsigned int v21; // ebx
  int v22; // [rsp+30h] [rbp-30h] BYREF
  __int64 v23; // [rsp+38h] [rbp-28h] BYREF
  __int64 v24; // [rsp+40h] [rbp-20h] BYREF
  __int64 v25; // [rsp+48h] [rbp-18h] BYREF
  std::_Ref_count_base *v26; // [rsp+50h] [rbp-10h]
  unsigned int v27; // [rsp+88h] [rbp+28h] BYREF
  struct ICDPComAccountProviderCallback *v28; // [rsp+98h] [rbp+38h] BYREF

  v28 = a4;
  if ( !a2 )
  {
    v22 = 80;
LABEL_15:
    v27 = -2147024809;
LABEL_16:
    Log<long &,char const (&)[40],int>((__int64)this, (__int64)a2, &v27, "..\\cdpcomaccountprovider.cpp", &v22);
    return v27;
  }
  if ( !a4 )
  {
    v22 = 81;
    goto LABEL_15;
  }
  if ( !a5 )
  {
    v22 = 82;
    goto LABEL_15;
  }
  v8 = CDPComAccountProvider::EnsureAccountProviderInitialized(this);
  if ( v8 < 0 )
  {
    v27 = v8;
    v22 = 84;
    goto LABEL_16;
  }
  CurrentUserContextToken = cdp::GetCurrentUserContextToken((cdp *)&v24, (unsigned __int64 *)a2);
  if ( CurrentUserContextToken < 0 )
  {
    v27 = CurrentUserContextToken;
    v22 = 89;
    goto LABEL_16;
  }
  v23 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  v10 = CDPCreateAccountInternalForUser(*(_QWORD *)a2, *((unsigned __int16 *)a2 + 4), v24, &v23);
  if ( v10 < 0 )
  {
    v27 = v10;
    v22 = 93;
    Log<long &,char const (&)[40],int>(v12, v11, &v27, "..\\cdpcomaccountprovider.cpp", &v22);
    v20 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return v27;
  }
  cdp::MakeSharedNoThrow<CDPComAccountProvider::AccountProviderCallback,ICDPComAccountProviderCallback * &>(
    &v25,
    (__int64 *)&v28);
  if ( !v25 )
  {
    v27 = -2147024882;
    v22 = 95;
    Log<long &,char const (&)[40],int>(v14, v13, &v27, "..\\cdpcomaccountprovider.cpp", &v22);
    v21 = v27;
    if ( v26 )
      std::_Ref_count_base::_Decref(v26);
    goto LABEL_23;
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, const char *))(**((_QWORD **)this + 19) + 48LL))(
          *((_QWORD *)this + 19),
          v23,
          a3);
  if ( v15 < 0 )
  {
    v27 = v15;
    v22 = 96;
    Log<long &,char const (&)[40],int>(v17, v16, &v27, "..\\cdpcomaccountprovider.cpp", &v22);
    if ( v26 )
      std::_Ref_count_base::_Decref(v26);
    v21 = v27;
LABEL_23:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    return v21;
  }
  if ( v26 )
    std::_Ref_count_base::_Decref(v26);
  v18 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return 0;
}

```

## disassembly

```asm
0x18000a000  mov     [rsp-18h+arg_0], rbx
0x18000a005  mov     [rsp-18h+arg_10], rsi
0x18000a00a  mov     [rsp-18h+arg_18], r9
0x18000a00f  push    rbp
0x18000a010  push    rdi
0x18000a011  push    r14
0x18000a013  mov     rbp, rsp
0x18000a016  sub     rsp, 60h
0x18000a01a  mov     r14, r8
0x18000a01d  mov     rbx, rdx
0x18000a020  mov     rsi, rcx
0x18000a023  test    rdx, rdx
0x18000a026  jz      loc_18000A113
0x18000a02c  test    r9, r9
0x18000a02f  jz      loc_18000A20F
0x18000a035  mov     rdi, [rbp+arg_20]
0x18000a039  test    rdi, rdi
0x18000a03c  jz      loc_18000A21B
0x18000a042  call    ?EnsureAccountProviderInitialized@CDPComAccountProvider@@AEAAJXZ; CDPComAccountProvider::EnsureAccountProviderInitialized(void)
0x18000a047  test    eax, eax
0x18000a049  js      loc_18000A227
0x18000a04f  lea     rcx, [rbp+var_20]; this
0x18000a053  call    ?GetCurrentUserContextToken@cdp@@YAJAEA_K@Z; cdp::GetCurrentUserContextToken(unsigned __int64 &)
0x18000a058  test    eax, eax
0x18000a05a  js      loc_18000A13F
0x18000a060  mov     [rbp+var_28], 0
0x18000a068  lea     rcx, [rbp+var_28]
0x18000a06c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a071  lea     r9, [rbp+var_28]
0x18000a075  mov     r8, [rbp+var_20]
0x18000a079  movzx   edx, word ptr [rbx+8]
0x18000a07d  mov     rcx, [rbx]
0x18000a080  call    cs:__imp_CDPCreateAccountInternalForUser
0x18000a086  test    eax, eax
0x18000a088  js      loc_18000A14B
0x18000a08e  lea     rdx, [rbp+arg_18]
0x18000a092  lea     rcx, [rbp+var_18]
0x18000a096  call    ??$MakeSharedNoThrow@VAccountProviderCallback@CDPComAccountProvider@@AEAPEAUICDPComAccountProviderCallback@@@cdp@@YA?AV?$shared_ptr@VAccountProviderCallback@CDPComAccountProvider@@@std@@AEAPEAUICDPComAccountProviderCallback@@@Z; cdp::MakeSharedNoThrow<CDPComAccountProvider::AccountProviderCallback,ICDPComAccountProviderCallback * &>(ICDPComAccountProviderCallback * &)
0x18000a09b  mov     r9, [rbp+var_18]
0x18000a09f  test    r9, r9
0x18000a0a2  jz      loc_18000A1A2
0x18000a0a8  mov     rcx, [rsi+98h]
0x18000a0af  mov     rax, [rcx]
0x18000a0b2  mov     [rsp+60h+var_40], rdi
0x18000a0b7  mov     r8, r14
0x18000a0ba  mov     rdx, [rbp+var_28]
0x18000a0be  mov     rax, [rax+30h]
0x18000a0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0c7  test    eax, eax
0x18000a0c9  js      loc_18000A1DC
0x18000a0cf  mov     rcx, [rbp+var_10]; this
0x18000a0d3  test    rcx, rcx
0x18000a0d6  jz      short loc_18000A0DE
0x18000a0d8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a0dd  nop
0x18000a0de  mov     rcx, [rbp+var_28]
0x18000a0e2  test    rcx, rcx
0x18000a0e5  jz      short loc_18000A0FC
0x18000a0e7  mov     [rbp+var_28], 0
0x18000a0ef  mov     rax, [rcx]
0x18000a0f2  mov     rax, [rax+10h]
0x18000a0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0fb  nop
0x18000a0fc  xor     eax, eax
0x18000a0fe  lea     r11, [rsp+60h+var_s0]
0x18000a103  mov     rbx, [r11+20h]
0x18000a107  mov     rsi, [r11+30h]
0x18000a10b  mov     rsp, r11
0x18000a10e  pop     r14
0x18000a110  pop     rdi
0x18000a111  pop     rbp
0x18000a112  retn
0x18000a113  mov     [rbp+var_30], 50h ; 'P'
0x18000a11a  mov     [rbp+arg_8], 80070057h
0x18000a121  lea     rax, [rbp+var_30]
0x18000a125  mov     [rsp+60h+var_40], rax
0x18000a12a  lea     r9, aCdpcomaccountp; "..\\cdpcomaccountprovider.cpp"
0x18000a131  lea     r8, [rbp+arg_8]
0x18000a135  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x18000a13a  mov     eax, [rbp+arg_8]
0x18000a13d  jmp     short loc_18000A0FE
0x18000a13f  mov     [rbp+arg_8], eax
0x18000a142  mov     [rbp+var_30], 59h ; 'Y'
0x18000a149  jmp     short loc_18000A121
0x18000a14b  mov     [rbp+arg_8], eax
0x18000a14e  mov     [rbp+var_30], 5Dh ; ']'
0x18000a155  lea     rax, [rbp+var_30]
0x18000a159  mov     [rsp+60h+var_40], rax
0x18000a15e  lea     r9, aCdpcomaccountp; "..\\cdpcomaccountprovider.cpp"
0x18000a165  lea     r8, [rbp+arg_8]
0x18000a169  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x18000a16e  nop
0x18000a16f  mov     rcx, [rbp+var_28]
0x18000a173  test    rcx, rcx
0x18000a176  jz      short loc_18000A18D
0x18000a178  mov     [rbp+var_28], 0
0x18000a180  mov     rdx, [rcx]
0x18000a183  mov     rax, [rdx+10h]
0x18000a187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a18c  nop
0x18000a18d  jmp     short loc_18000A13A
0x18000a18f  mov     ebx, [rbp+arg_8]
0x18000a192  lea     rcx, [rbp+var_28]
0x18000a196  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a19b  mov     eax, ebx
0x18000a19d  jmp     loc_18000A0FE
0x18000a1a2  mov     [rbp+arg_8], 8007000Eh
0x18000a1a9  mov     [rbp+var_30], 5Fh ; '_'
0x18000a1b0  lea     rax, [rbp+var_30]
0x18000a1b4  mov     [rsp+60h+var_40], rax
0x18000a1b9  lea     r9, aCdpcomaccountp; "..\\cdpcomaccountprovider.cpp"
0x18000a1c0  lea     r8, [rbp+arg_8]
0x18000a1c4  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x18000a1c9  mov     ebx, [rbp+arg_8]
0x18000a1cc  mov     rcx, [rbp+var_10]; this
0x18000a1d0  test    rcx, rcx
0x18000a1d3  jz      short loc_18000A192
0x18000a1d5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a1da  jmp     short loc_18000A192
0x18000a1dc  mov     [rbp+arg_8], eax
0x18000a1df  mov     [rbp+var_30], 60h ; '`'
0x18000a1e6  lea     rax, [rbp+var_30]
0x18000a1ea  mov     [rsp+60h+var_40], rax
0x18000a1ef  lea     r9, aCdpcomaccountp; "..\\cdpcomaccountprovider.cpp"
0x18000a1f6  lea     r8, [rbp+arg_8]
0x18000a1fa  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x18000a1ff  mov     rcx, [rbp+var_10]; this
0x18000a203  test    rcx, rcx
0x18000a206  jz      short loc_18000A18F
0x18000a208  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a20d  jmp     short loc_18000A18F
0x18000a20f  mov     [rbp+var_30], 51h ; 'Q'
0x18000a216  jmp     loc_18000A11A
0x18000a21b  mov     [rbp+var_30], 52h ; 'R'
0x18000a222  jmp     loc_18000A11A
0x18000a227  mov     [rbp+arg_8], eax
0x18000a22a  mov     [rbp+var_30], 54h ; 'T'
0x18000a231  jmp     loc_18000A121
```
