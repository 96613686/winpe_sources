# ProviderOpenAlgorithmProvider(void * *,ushort const *,ulong)

- ea: `0x1800138e0`
- end: `0x180013af2`
- name: `?ProviderOpenAlgorithmProvider@@YAJPEAPEAXPEBGK@Z`
- size: `530`
- prototype: `__int64 __fastcall(void **, const unsigned __int16 *, unsigned int)`
- caller_count: `6`
- callee_count: `10`
- tags: ``

## callers

- `0x180015ac0`
- `0x18001bb00`
- `0x180036f88`
- `0x180038efc`
- `0x18003ae74`
- `0x180059b78`

## callees

- `0x1800133c4`
- `0x1800138e0`
- `0x180014a60`
- `0x180015660`
- `0x1800157c0`
- `0x18001c00c`
- `0x18004f7fc`
- `0x1800764d0`
- `0x1800769bc`
- `0x1800c8010`

## import_xrefs

- `tbs!Tbsi_GetDeviceInfo` at `0x180013960`
- `tbs!Tbsi_GetDeviceInfo` at `0x180013960`

## string_xrefs

- `0x18001390c`: `ProviderOpenAlgorithmProvider`
- `0x18001393f`: `TpmProvider::CreateProvider`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ProviderOpenAlgorithmProvider(TpmProvider **a1, const unsigned __int16 *a2, __int16 a3)
{
  TpmProvider *v5; // rbx
  TpmProvider *v6; // rax
  TpmProvider *v7; // rdi
  int v8; // esi
  void (__fastcall ***v9)(_QWORD, __int64); // rcx
  TpmProvider *v11; // rax
  char *v12; // [rsp+20h] [rbp-59h] BYREF
  _QWORD v13[4]; // [rsp+28h] [rbp-51h] BYREF
  char v14; // [rsp+48h] [rbp-31h]
  int *v15[3]; // [rsp+50h] [rbp-29h] BYREF
  int *v16[3]; // [rsp+68h] [rbp-11h] BYREF
  __int128 v17; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v15, L"ProviderOpenAlgorithmProvider", 1);
  v13[0] = 0;
  v13[2] = v13;
  v5 = 0;
  v13[3] = 0;
  v14 = 1;
  LODWORD(v12) = 0;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v16, L"TpmProvider::CreateProvider", (const int *)&v12);
  v17 = 0;
  if ( !(unsigned int)Tbsi_GetDeviceInfo(16, &v17) && DWORD1(v17) == 2 )
  {
    v6 = (TpmProvider *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v6;
    if ( v6 )
    {
      TpmProvider::TpmProvider(v6);
      *(_QWORD *)v7 = &TpmProvider20::`vftable';
      goto LABEL_5;
    }
    goto LABEL_15;
  }
  v11 = (TpmProvider *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v11;
  if ( !v11 )
  {
LABEL_15:
    v7 = 0;
    goto LABEL_5;
  }
  TpmProvider::TpmProvider(v11);
  *(_QWORD *)v7 = &TpmProvider12::`vftable';
LABEL_5:
  v13[1] = v7;
  if ( v7 )
  {
    if ( (a3 & 0x1000) != 0 || (*(int (__fastcall **)(TpmProvider *))(*(_QWORD *)v7 + 1128LL))(v7) >= 0 )
    {
      v5 = v7;
      v8 = (int)v12;
    }
    else
    {
      v8 = -2144795647;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmprovider.cpp",
        (const char *)0x80290401LL,
        -2144795647);
      (**(void (__fastcall ***)(TpmProvider *, __int64))v7)(v7, 1);
    }
  }
  else
  {
    v8 = -2147024888;
    LODWORD(v12) = -2147024888;
  }
  KspFunctionLogger::~KspFunctionLogger(v16);
  v9 = (void (__fastcall ***)(_QWORD, __int64))v13[0];
  v13[0] = v5;
  if ( v9 )
  {
    (**v9)(v9, 1);
    v5 = (TpmProvider *)v13[0];
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcprovider.cpp",
      (const char *)(unsigned int)v8,
      (int)v12);
    wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(v13, 0);
    KspFunctionLogger::~KspFunctionLogger(v15);
    return (unsigned int)v8;
  }
  else
  {
    *a1 = v5;
    v13[0] = 0;
    KspFunctionLogger::~KspFunctionLogger(v15);
    return 0;
  }
}

```

## disassembly

```asm
0x1800138e0  push    rbp
0x1800138e2  push    rbx
0x1800138e3  push    rsi
0x1800138e4  push    rdi
0x1800138e5  push    r14
0x1800138e7  push    r15
0x1800138e9  lea     rbp, [rsp-2Fh]
0x1800138ee  sub     rsp, 0A8h
0x1800138f5  mov     rax, cs:__security_cookie
0x1800138fc  xor     rax, rsp
0x1800138ff  mov     [rbp+57h+var_40], rax
0x180013903  mov     esi, r8d
0x180013906  mov     r14, rcx
0x180013909  mov     r8b, 1; bool
0x18001390c  lea     rdx, aProvideropenal; "ProviderOpenAlgorithmProvider"
0x180013913  lea     rcx, [rbp+57h+var_80]; this
0x180013917  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18001391c  nop
0x18001391d  xor     r15d, r15d
0x180013920  mov     [rbp+57h+var_A8], r15
0x180013924  lea     rax, [rbp+57h+var_A8]
0x180013928  mov     [rbp+57h+var_98], rax
0x18001392c  mov     ebx, r15d
0x18001392f  mov     [rbp+57h+var_90], rbx
0x180013933  mov     [rbp+57h+var_88], 1
0x180013937  mov     dword ptr [rbp+57h+var_B0], r15d
0x18001393b  lea     r8, [rbp+57h+var_B0]; int *
0x18001393f  lea     rdx, aTpmproviderCre; "TpmProvider::CreateProvider"
0x180013946  lea     rcx, [rbp+57h+var_68]; this
0x18001394a  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x18001394f  nop
0x180013950  xorps   xmm0, xmm0
0x180013953  movups  [rbp+57h+var_50], xmm0
0x180013957  lea     rdx, [rbp+57h+var_50]
0x18001395b  mov     ecx, 10h
0x180013960  call    cs:__imp_Tbsi_GetDeviceInfo
0x180013967  nop     dword ptr [rax+rax+00h]
0x18001396c  test    eax, eax
0x18001396e  jnz     loc_180013A4C
0x180013974  cmp     dword ptr [rbp+57h+var_50+4], 2
0x180013978  jnz     loc_180013A4C
0x18001397e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013985  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001398a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001398f  mov     rdi, rax
0x180013992  test    rax, rax
0x180013995  jz      loc_180013A65
0x18001399b  mov     rcx, rax; this
0x18001399e  call    ??0TpmProvider@@IEAA@XZ; TpmProvider::TpmProvider(void)
0x1800139a3  lea     rax, ??_7TpmProvider20@@6B@; const TpmProvider20::`vftable'
0x1800139aa  mov     [rdi], rax
0x1800139ad  mov     [rbp+57h+var_A0], rdi
0x1800139b1  test    rdi, rdi
0x1800139b4  jz      loc_180013A42
0x1800139ba  bt      esi, 0Ch
0x1800139be  jb      short loc_1800139DA
0x1800139c0  mov     rax, [rdi]
0x1800139c3  mov     rcx, rdi
0x1800139c6  mov     rax, [rax+468h]
0x1800139cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139d2  test    eax, eax
0x1800139d4  js      loc_180013A84
0x1800139da  mov     rbx, rdi
0x1800139dd  mov     esi, dword ptr [rbp+57h+var_B0]
0x1800139e0  lea     rcx, [rbp+57h+var_68]; this
0x1800139e4  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800139e9  nop
0x1800139ea  mov     rcx, [rbp+57h+var_A8]
0x1800139ee  mov     [rbp+57h+var_A8], rbx
0x1800139f2  test    rcx, rcx
0x1800139f5  jz      short loc_180013A0B
0x1800139f7  mov     rax, [rcx]
0x1800139fa  mov     edx, 1
0x1800139ff  mov     rax, [rax]
0x180013a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a07  mov     rbx, [rbp+57h+var_A8]
0x180013a0b  test    esi, esi
0x180013a0d  js      loc_180013ABD
0x180013a13  mov     [r14], rbx
0x180013a16  mov     [rbp+57h+var_A8], r15
0x180013a1a  lea     rcx, [rbp+57h+var_80]; this
0x180013a1e  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180013a23  xor     eax, eax
0x180013a25  mov     rcx, [rbp+57h+var_40]
0x180013a29  xor     rcx, rsp; StackCookie
0x180013a2c  call    __security_check_cookie
0x180013a31  add     rsp, 0A8h
0x180013a38  pop     r15
0x180013a3a  pop     r14
0x180013a3c  pop     rdi
0x180013a3d  pop     rsi
0x180013a3e  pop     rbx
0x180013a3f  pop     rbp
0x180013a40  retn
0x180013a42  mov     esi, 80070008h
0x180013a47  mov     dword ptr [rbp+57h+var_B0], esi
0x180013a4a  jmp     short loc_1800139E0
0x180013a4c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013a53  mov     ecx, 58h ; 'X'; unsigned __int64
0x180013a58  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180013a5d  mov     rdi, rax
0x180013a60  test    rax, rax
0x180013a63  jnz     short loc_180013A6D
0x180013a65  mov     rdi, r15
0x180013a68  jmp     loc_1800139AD
0x180013a6d  mov     rcx, rdi; this
0x180013a70  call    ??0TpmProvider@@IEAA@XZ; TpmProvider::TpmProvider(void)
0x180013a75  lea     rax, ??_7TpmProvider12@@6B@; const TpmProvider12::`vftable'
0x180013a7c  mov     [rdi], rax
0x180013a7f  jmp     loc_1800139AD
0x180013a84  mov     esi, 80290401h
0x180013a89  mov     dword ptr [rbp+57h+var_B0], esi
0x180013a8c  mov     rcx, [rbp+5Fh]; this
0x180013a90  mov     r9d, esi; char *
0x180013a93  lea     r8, aOnecoreBaseNgs_16; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180013a9a  mov     edx, 36h ; '6'; void *
0x180013a9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013aa4  nop
0x180013aa5  mov     rax, [rdi]
0x180013aa8  mov     edx, 1
0x180013aad  mov     rcx, rdi
0x180013ab0  mov     rax, [rax]
0x180013ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ab8  jmp     loc_1800139E0
0x180013abd  mov     rcx, [rbp+5Fh]; this
0x180013ac1  mov     r9d, esi; char *
0x180013ac4  lea     r8, aOnecoreBaseNgs_25; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180013acb  mov     edx, 2Dh ; '-'; void *
0x180013ad0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013ad5  nop
0x180013ad6  xor     edx, edx
0x180013ad8  lea     rcx, [rbp+57h+var_A8]
0x180013adc  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x180013ae1  nop
0x180013ae2  lea     rcx, [rbp+57h+var_80]; this
0x180013ae6  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180013aeb  mov     eax, esi
0x180013aed  jmp     loc_180013A25
```
