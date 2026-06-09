# PCPKspOpenStorageProvider

- ea: `0x18001d590`
- end: `0x18001dbca`
- name: `PCPKspOpenStorageProvider`
- size: `1594`
- prototype: `__int64 __fastcall(PCPStorageProvider **, __int64, int)`
- caller_count: `0`
- callee_count: `22`
- tags: `broker_com_uri`

## callees

- `0x18000f730`
- `0x1800113f0`
- `0x180011554`
- `0x1800133c4`
- `0x180014a60`
- `0x180015660`
- `0x1800157c0`
- `0x18001c00c`
- `0x18001c258`
- `0x18001c308`
- `0x18001d590`
- `0x18001e100`
- `0x18001e2d0`
- `0x18001edb0`
- `0x18001f1cc`
- `0x18001f2f0`
- `0x18001fe60`
- `0x18003bad0`
- `0x18004f7fc`
- `0x1800764d0`
- `0x1800769bc`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d961`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d961`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d91a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d91a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001d610`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001d610`
- `tbs!Tbsi_GetDeviceInfo` at `0x18001d7dc`
- `tbs!Tbsi_GetDeviceInfo` at `0x18001d7dc`

## string_xrefs

- `0x18001d774`: `ProviderOpenAlgorithmProvider`
- `0x18001d7af`: `TpmProvider::CreateProvider`
- `0x18001d5e0`: `PCPKspOpenStorageProvider`
- `0x18001d997`: `PCPKspOpenStorageProvider`
- `0x18001d61c`: `PCPKspOpenStorageProvider`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall PCPKspOpenStorageProvider(PCPStorageProvider **a1, __int64 a2, int a3)
{
  bool v4; // di
  const char *v5; // r9
  __int64 result; // rax
  PCPStorageProvider *v7; // rax
  PCPStorageProvider *v8; // r15
  __int16 v9; // r12
  TpmProvider *v10; // rbx
  TpmProvider *v11; // rax
  TpmProvider *v12; // r14
  int v13; // r12d
  void (__fastcall ***v14)(_QWORD, __int64); // rcx
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rbx
  const wchar_t *v18; // rax
  int v19; // r12d
  int v20; // eax
  int v21; // ebx
  TpmProvider *v22; // rax
  int v23; // [rsp+20h] [rbp-278h]
  int v24; // [rsp+20h] [rbp-278h]
  int v25; // [rsp+40h] [rbp-258h] BYREF
  int v26; // [rsp+44h] [rbp-254h] BYREF
  int v27; // [rsp+48h] [rbp-250h] BYREF
  _QWORD v28[2]; // [rsp+50h] [rbp-248h] BYREF
  _QWORD v29[2]; // [rsp+60h] [rbp-238h] BYREF
  char v30; // [rsp+70h] [rbp-228h]
  _QWORD v31[2]; // [rsp+80h] [rbp-218h] BYREF
  __int128 v32; // [rsp+90h] [rbp-208h]
  int *v33; // [rsp+A0h] [rbp-1F8h]
  int *v34; // [rsp+A8h] [rbp-1F0h]
  __int64 v35; // [rsp+B0h] [rbp-1E8h]
  DWORD TickCount; // [rsp+B8h] [rbp-1E0h]
  char v37; // [rsp+BCh] [rbp-1DCh]
  PCPStorageProvider *v38; // [rsp+C0h] [rbp-1D8h]
  _BYTE v39[24]; // [rsp+C8h] [rbp-1D0h] BYREF
  _BYTE v40[24]; // [rsp+E0h] [rbp-1B8h] BYREF
  __int128 v41; // [rsp+F8h] [rbp-1A0h] BYREF
  _QWORD v42[42]; // [rsp+110h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]
  int v44; // [rsp+2B0h] [rbp+18h] BYREF

  v44 = a3;
  wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v42);
  v42[0] = &KspDebugProvider::KspDebugActivity::`vftable';
  try
  {
    KspDebugProvider::KspDebugActivity::StartActivity(
      (KspDebugProvider::KspDebugActivity *)v42,
      "PCPKspOpenStorageProvider");
    v25 = 0;
    v27 = 0;
    v4 = (v44 & 0x40) != 0;
    v31[0] = L"PCPKspOpenStorageProvider";
    v31[1] = a1;
    v32 = 0;
    v33 = &v25;
    v34 = &v44;
    v35 = 0;
    TickCount = GetTickCount();
    v37 = 0;
    if ( !a1 )
    {
      v25 = -2146893785;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17D,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)0x80090027LL,
        v23);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v31);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v42);
      return 2148073511LL;
    }
    *a1 = 0;
    if ( (v44 & 0xFFFFEFBF) != 0 )
    {
      v25 = -2146893815;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x183,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)0x80090009LL,
        v23);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v31);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v42);
      return 2148073481LL;
    }
    v7 = (PCPStorageProvider *)operator new(0xC8u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v7 )
      v8 = PCPStorageProvider::PCPStorageProvider(v7);
    else
      v8 = 0;
    v38 = v8;
    if ( !v8 )
    {
      v25 = -2147024888;
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v31);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v42);
      return 2147942408LL;
    }
    v9 = v44 & 0x1000;
    KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v40, L"ProviderOpenAlgorithmProvider", 1);
    v28[0] = 0;
    v29[0] = v28;
    v10 = 0;
    v29[1] = 0;
    v30 = 1;
    v26 = 0;
    KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v39, L"TpmProvider::CreateProvider", &v26);
    v41 = 0;
    if ( (unsigned int)Tbsi_GetDeviceInfo(16, &v41) || DWORD1(v41) != 2 )
    {
      v22 = (TpmProvider *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
      v12 = v22;
      if ( v22 )
      {
        TpmProvider::TpmProvider(v22);
        *(_QWORD *)v12 = &TpmProvider12::`vftable';
LABEL_13:
        v28[1] = v12;
        if ( v12 )
        {
          if ( (v9 & 0x1000) != 0 || (*(int (__fastcall **)(TpmProvider *))(*(_QWORD *)v12 + 1128LL))(v12) >= 0 )
          {
            v10 = v12;
            v13 = v26;
          }
          else
          {
            v13 = -2144795647;
            v26 = -2144795647;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x36,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmprovider.cpp",
              (const char *)0x80290401LL,
              v23);
            (**(void (__fastcall ***)(TpmProvider *, __int64))v12)(v12, 1);
          }
        }
        else
        {
          v13 = -2147024888;
          v26 = -2147024888;
        }
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v39);
        v14 = (void (__fastcall ***)(_QWORD, __int64))v28[0];
        v28[0] = v10;
        if ( v14 )
        {
          (**v14)(v14, 1);
          v10 = (TpmProvider *)v28[0];
        }
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2D,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcprovider.cpp",
            (const char *)(unsigned int)v13,
            v23);
          wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(v28, 0);
        }
        else
        {
          *((_QWORD *)v8 + 17) = v10;
          v28[0] = 0;
          v13 = 0;
        }
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v40);
        v15 = SecurityStatusFromHResult(v13);
        v16 = v15;
        v25 = v15;
        if ( v15 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x18D,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
            (const char *)(unsigned int)v15,
            v23);
          PCPStorageProvider::`vector deleting destructor'(v8, 1u);
          KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v31);
          KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v42);
          return v16;
        }
        else
        {
          v17 = *((_QWORD *)v8 + 17);
          KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v29, L"ProviderGetProperty", 1);
          v18 = (const wchar_t *)EnumeratedFromStringProperty(65);
          KspDebugProvider::TraceLoggingInfo("Property = %ls", v18);
          if ( (*(_DWORD *)(v17 + 12) & 1) == 0 )
            EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 16));
          v19 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v17 + 1112LL))(v17, 65, 0, 0);
          if ( (*(_DWORD *)(v17 + 12) & 1) == 0 )
            LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 16));
          v20 = PcpFromHResult(v19);
          v21 = v20;
          if ( v20 >= 0 )
          {
            KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v29);
LABEL_29:
            v25 = 0;
            *((_BYTE *)v8 + 92) |= v4;
            *a1 = v8;
            KspDebugProvider::KspDebugActivity::Stop(
              (KspDebugProvider::KspDebugActivity *)v42,
              "PCPKspOpenStorageProvider");
            KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v31);
            KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v42);
            return 0;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4F,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcprovider.cpp",
            (const char *)(unsigned int)v20,
            (int)&v27);
          KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v29);
          v25 = v21;
          if ( (v44 & 0x1000) != 0 )
          {
            *((_DWORD *)v8 + 2) = 0;
            goto LABEL_29;
          }
          KspDebugProvider::TraceLoggingError("No TPM present. hr = 0x%X", v21);
          v25 = -2146893776;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x19A,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
            (const char *)0x80090030LL,
            v24);
          PCPStorageProvider::`vector deleting destructor'(v8, 1u);
          KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v31);
          KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v42);
          return 2148073520LL;
        }
      }
    }
    else
    {
      v11 = (TpmProvider *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
      v12 = v11;
      if ( v11 )
      {
        TpmProvider::TpmProvider(v11);
        *(_QWORD *)v12 = &TpmProvider20::`vftable';
        goto LABEL_13;
      }
    }
    v12 = 0;
    goto LABEL_13;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1A7,
                           (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x18001d590  mov     [rsp+arg_8], rbx
0x18001d595  mov     [rsp+arg_18], rsi
0x18001d59a  mov     [rsp+arg_10], r8d
0x18001d59f  push    rdi
0x18001d5a0  push    r12
0x18001d5a2  push    r13
0x18001d5a4  push    r14
0x18001d5a6  push    r15
0x18001d5a8  sub     rsp, 270h
0x18001d5af  mov     rax, cs:__security_cookie
0x18001d5b6  xor     rax, rsp
0x18001d5b9  mov     [rsp+298h+var_38], rax
0x18001d5c1  mov     rsi, rcx
0x18001d5c4  lea     rcx, [rsp+298h+var_188]
0x18001d5cc  call    ??0?$ActivityBase@VKspDebugProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001d5d1  lea     rax, ??_7KspDebugActivity@KspDebugProvider@@6B@; const KspDebugProvider::KspDebugActivity::`vftable'
0x18001d5d8  mov     [rsp+298h+var_188], rax
0x18001d5e0  lea     rdx, aPcpkspopenstor; "PCPKspOpenStorageProvider"
0x18001d5e7  lea     rcx, [rsp+298h+var_188]; this
0x18001d5ef  call    ?StartActivity@KspDebugActivity@KspDebugProvider@@QEAAXPEBD@Z; KspDebugProvider::KspDebugActivity::StartActivity(char const *)
0x18001d5f4  nop
0x18001d5f5  xor     r13d, r13d
0x18001d5f8  mov     [rsp+298h+var_258], r13d
0x18001d5fd  mov     [rsp+298h+var_250], r13d
0x18001d602  mov     edi, [rsp+298h+arg_10]
0x18001d609  shr     edi, 6
0x18001d60c  and     dil, 1
0x18001d610  call    cs:__imp_GetTickCount
0x18001d617  nop     dword ptr [rax+rax+00h]
0x18001d61c  lea     rcx, aPcpkspopenstor_0; "PCPKspOpenStorageProvider"
0x18001d623  mov     [rsp+298h+var_218], rcx
0x18001d62b  mov     [rsp+298h+var_210], rsi
0x18001d633  xorps   xmm0, xmm0
0x18001d636  movdqa  [rsp+298h+var_208], xmm0
0x18001d63f  lea     rcx, [rsp+298h+var_258]
0x18001d644  mov     [rsp+298h+var_1F8], rcx
0x18001d64c  lea     rcx, [rsp+298h+arg_10]
0x18001d654  mov     [rsp+298h+var_1F0], rcx
0x18001d65c  mov     [rsp+298h+var_1E8], r13
0x18001d664  mov     [rsp+298h+var_1E0], eax
0x18001d66b  mov     [rsp+298h+var_1DC], r13b
0x18001d673  test    rsi, rsi
0x18001d676  jnz     short loc_18001D6EE
0x18001d678  mov     [rsp+298h+var_258], 80090027h
0x18001d680  mov     rcx, [rsp+298h]; this
0x18001d688  mov     r9d, 80090027h; char *
0x18001d68e  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18001d695  mov     edx, 17Dh; void *
0x18001d69a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d69f  nop
0x18001d6a0  lea     rcx, [rsp+298h+var_218]; this
0x18001d6a8  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18001d6ad  nop
0x18001d6ae  lea     rcx, [rsp+298h+var_188]; this
0x18001d6b6  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18001d6bb  mov     eax, 80090027h
0x18001d6c0  mov     rcx, [rsp+298h+var_38]
0x18001d6c8  xor     rcx, rsp; StackCookie
0x18001d6cb  call    __security_check_cookie
0x18001d6d0  lea     r11, [rsp+298h+var_28]
0x18001d6d8  mov     rbx, [r11+38h]
0x18001d6dc  mov     rsi, [r11+48h]
0x18001d6e0  mov     rsp, r11
0x18001d6e3  pop     r15
0x18001d6e5  pop     r14
0x18001d6e7  pop     r13
0x18001d6e9  pop     r12
0x18001d6eb  pop     rdi
0x18001d6ec  retn
0x18001d6ee  mov     [rsi], r13
0x18001d6f1  test    [rsp+298h+arg_10], 0FFFFEFBFh
0x18001d6fc  jnz     loc_18001DA9B
0x18001d702  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d709  mov     ecx, 0C8h; unsigned __int64
0x18001d70e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001d713  test    rax, rax
0x18001d716  jz      loc_18001DA53
0x18001d71c  mov     rcx, rax; this
0x18001d71f  call    ??0PCPStorageProvider@@QEAA@XZ; PCPStorageProvider::PCPStorageProvider(void)
0x18001d724  mov     r15, rax
0x18001d727  mov     [rsp+298h+var_1D8], r15
0x18001d72f  test    r15, r15
0x18001d732  jnz     short loc_18001D762
0x18001d734  mov     r12d, 80070008h
0x18001d73a  mov     [rsp+298h+var_258], r12d
0x18001d73f  lea     rcx, [rsp+298h+var_218]; this
0x18001d747  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18001d74c  nop
0x18001d74d  lea     rcx, [rsp+298h+var_188]; this
0x18001d755  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18001d75a  mov     eax, r12d
0x18001d75d  jmp     loc_18001D6C0
0x18001d762  mov     r12d, [rsp+298h+arg_10]
0x18001d76a  and     r12d, 1000h
0x18001d771  mov     r8b, 1; bool
0x18001d774  lea     rdx, aProvideropenal; "ProviderOpenAlgorithmProvider"
0x18001d77b  lea     rcx, [rsp+298h+var_1B8]; this
0x18001d783  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18001d788  nop
0x18001d789  mov     [rsp+298h+var_248], r13
0x18001d78e  lea     rax, [rsp+298h+var_248]
0x18001d793  mov     [rsp+298h+var_238], rax
0x18001d798  mov     rbx, r13
0x18001d79b  mov     [rsp+298h+var_230], rbx
0x18001d7a0  mov     [rsp+298h+var_228], 1
0x18001d7a5  mov     [rsp+298h+var_254], r13d
0x18001d7aa  lea     r8, [rsp+298h+var_254]; int *
0x18001d7af  lea     rdx, aTpmproviderCre; "TpmProvider::CreateProvider"
0x18001d7b6  lea     rcx, [rsp+298h+var_1D0]; this
0x18001d7be  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x18001d7c3  nop
0x18001d7c4  xorps   xmm0, xmm0
0x18001d7c7  movups  [rsp+298h+var_1A0], xmm0
0x18001d7cf  lea     rdx, [rsp+298h+var_1A0]
0x18001d7d7  mov     ecx, 10h
0x18001d7dc  call    cs:__imp_Tbsi_GetDeviceInfo
0x18001d7e3  nop     dword ptr [rax+rax+00h]
0x18001d7e8  test    eax, eax
0x18001d7ea  jnz     loc_18001D9CE
0x18001d7f0  cmp     dword ptr [rsp+298h+var_1A0+4], 2
0x18001d7f8  jnz     loc_18001D9CE
0x18001d7fe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d805  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001d80a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001d80f  mov     r14, rax
0x18001d812  test    rax, rax
0x18001d815  jz      loc_18001D9E7
0x18001d81b  mov     rcx, rax; this
0x18001d81e  call    ??0TpmProvider@@IEAA@XZ; TpmProvider::TpmProvider(void)
0x18001d823  lea     rax, ??_7TpmProvider20@@6B@; const TpmProvider20::`vftable'
0x18001d82a  mov     [r14], rax
0x18001d82d  mov     [rsp+298h+var_240], r14
0x18001d832  test    r14, r14
0x18001d835  jnz     short loc_18001D844
0x18001d837  mov     r12d, 80070008h
0x18001d83d  mov     [rsp+298h+var_254], r12d
0x18001d842  jmp     short loc_18001D86D
0x18001d844  bt      r12d, 0Ch
0x18001d849  jb      short loc_18001D865
0x18001d84b  mov     rax, [r14]
0x18001d84e  mov     rcx, r14
0x18001d851  mov     rax, [rax+468h]
0x18001d858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d85d  test    eax, eax
0x18001d85f  js      loc_18001DA5B
0x18001d865  mov     rbx, r14
0x18001d868  mov     r12d, [rsp+298h+var_254]
0x18001d86d  lea     rcx, [rsp+298h+var_1D0]; this
0x18001d875  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18001d87a  nop
0x18001d87b  mov     rcx, [rsp+298h+var_248]
0x18001d880  mov     [rsp+298h+var_248], rbx
0x18001d885  test    rcx, rcx
0x18001d888  jz      short loc_18001D89F
0x18001d88a  mov     rax, [rcx]
0x18001d88d  mov     edx, 1
0x18001d892  mov     rax, [rax]
0x18001d895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d89a  mov     rbx, [rsp+298h+var_248]
0x18001d89f  test    r12d, r12d
0x18001d8a2  js      loc_18001DAE8
0x18001d8a8  mov     [r15+88h], rbx
0x18001d8af  mov     [rsp+298h+var_248], r13
0x18001d8b4  mov     r12d, r13d
0x18001d8b7  lea     rcx, [rsp+298h+var_1B8]; this
0x18001d8bf  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18001d8c4  mov     ecx, r12d; int
0x18001d8c7  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x18001d8cc  mov     ebx, eax
0x18001d8ce  mov     [rsp+298h+var_258], eax
0x18001d8d2  test    eax, eax
0x18001d8d4  js      loc_18001DA06
0x18001d8da  mov     rbx, [r15+88h]
0x18001d8e1  mov     r8b, 1; bool
0x18001d8e4  lea     rdx, aProvidergetpro; "ProviderGetProperty"
0x18001d8eb  lea     rcx, [rsp+298h+var_238]; this
0x18001d8f0  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18001d8f5  nop
0x18001d8f6  mov     ecx, 41h ; 'A'
0x18001d8fb  call    ?EnumeratedFromStringProperty@@YAPEBGW4KspProp@@@Z; EnumeratedFromStringProperty(KspProp)
0x18001d900  mov     rdx, rax
0x18001d903  lea     rcx, aPropertyLs; "Property = %ls"
0x18001d90a  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x18001d90f  mov     eax, [rbx+0Ch]
0x18001d912  test    al, 1
0x18001d914  jnz     short loc_18001D926
0x18001d916  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001d91a  call    cs:__imp_EnterCriticalSection
0x18001d921  nop     dword ptr [rax+rax+00h]
0x18001d926  mov     rax, [rbx]
0x18001d929  mov     [rsp+298h+var_270], r13d
0x18001d92e  lea     rcx, [rsp+298h+var_250]
0x18001d933  mov     qword ptr [rsp+298h+var_278], rcx; int
0x18001d938  xor     r9d, r9d
0x18001d93b  xor     r8d, r8d
0x18001d93e  mov     edx, 41h ; 'A'
0x18001d943  mov     rcx, rbx
0x18001d946  mov     rax, [rax+458h]
0x18001d94d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d952  mov     r12d, eax
0x18001d955  mov     edx, [rbx+0Ch]
0x18001d958  test    dl, 1
0x18001d95b  jnz     short loc_18001D96D
0x18001d95d  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001d961  call    cs:__imp_LeaveCriticalSection
0x18001d968  nop     dword ptr [rax+rax+00h]
0x18001d96d  mov     ecx, r12d; int
0x18001d970  call    ?PcpFromHResult@@YAJJ@Z; PcpFromHResult(long)
0x18001d975  mov     ebx, eax
0x18001d977  test    eax, eax
0x18001d979  js      loc_18001DB17
0x18001d97f  lea     rcx, [rsp+298h+var_238]; this
0x18001d984  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18001d989  mov     eax, r13d
0x18001d98c  mov     [rsp+298h+var_258], eax
0x18001d990  or      [r15+5Ch], dil
0x18001d994  mov     [rsi], r15
0x18001d997  lea     rdx, aPcpkspopenstor; "PCPKspOpenStorageProvider"
0x18001d99e  lea     rcx, [rsp+298h+var_188]; this
0x18001d9a6  call    ?Stop@KspDebugActivity@KspDebugProvider@@QEAAXPEBD@Z; KspDebugProvider::KspDebugActivity::Stop(char const *)
0x18001d9ab  nop
0x18001d9ac  lea     rcx, [rsp+298h+var_218]; this
0x18001d9b4  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18001d9b9  nop
0x18001d9ba  lea     rcx, [rsp+298h+var_188]; this
0x18001d9c2  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18001d9c7  xor     eax, eax
0x18001d9c9  jmp     loc_18001D6C0
0x18001d9ce  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d9d5  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001d9da  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001d9df  mov     r14, rax
0x18001d9e2  test    rax, rax
0x18001d9e5  jnz     short loc_18001D9EF
0x18001d9e7  mov     r14, r13
0x18001d9ea  jmp     loc_18001D82D
0x18001d9ef  mov     rcx, r14; this
0x18001d9f2  call    ??0TpmProvider@@IEAA@XZ; TpmProvider::TpmProvider(void)
0x18001d9f7  lea     rax, ??_7TpmProvider12@@6B@; const TpmProvider12::`vftable'
0x18001d9fe  mov     [r14], rax
0x18001da01  jmp     loc_18001D82D
0x18001da06  mov     rcx, [rsp+298h]; this
0x18001da0e  mov     r9d, ebx; char *
0x18001da11  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18001da18  mov     edx, 18Dh; void *
0x18001da1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001da22  nop
0x18001da23  mov     edx, 1; unsigned int
0x18001da28  mov     rcx, r15; this
0x18001da2b  call    ??_EPCPStorageProvider@@UEAAPEAXI@Z; PCPStorageProvider::`vector deleting destructor'(uint)
0x18001da30  nop
0x18001da31  lea     rcx, [rsp+298h+var_218]; this
0x18001da39  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18001da3e  nop
0x18001da3f  lea     rcx, [rsp+298h+var_188]; this
0x18001da47  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18001da4c  mov     eax, ebx
0x18001da4e  jmp     loc_18001D6C0
0x18001da53  mov     r15, r13
0x18001da56  jmp     loc_18001D727
0x18001da5b  mov     r12d, 80290401h
0x18001da61  mov     [rsp+298h+var_254], r12d
0x18001da66  mov     rcx, [rsp+298h]; this
0x18001da6e  mov     r9d, r12d; char *
0x18001da71  lea     r8, aOnecoreBaseNgs_16; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18001da78  mov     edx, 36h ; '6'; void *
0x18001da7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001da82  nop
0x18001da83  mov     rax, [r14]
0x18001da86  mov     edx, 1
0x18001da8b  mov     rcx, r14
0x18001da8e  mov     rax, [rax]
0x18001da91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da96  jmp     loc_18001D86D
0x18001da9b  mov     [rsp+298h+var_258], 80090009h
0x18001daa3  mov     rcx, [rsp+298h]; this
0x18001daab  mov     r9d, 80090009h; char *
0x18001dab1  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18001dab8  mov     edx, 183h; void *
0x18001dabd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dac2  nop
0x18001dac3  lea     rcx, [rsp+298h+var_218]; this
0x18001dacb  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18001dad0  nop
0x18001dad1  lea     rcx, [rsp+298h+var_188]; this
0x18001dad9  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18001dade  mov     eax, 80090009h
0x18001dae3  jmp     loc_18001D6C0
0x18001dae8  mov     rcx, [rsp+298h]; this
0x18001daf0  mov     r9d, r12d; char *
0x18001daf3  lea     r8, aOnecoreBaseNgs_25; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18001dafa  mov     edx, 2Dh ; '-'; void *
0x18001daff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001db04  nop
0x18001db05  xor     edx, edx
0x18001db07  lea     rcx, [rsp+298h+var_248]
0x18001db0c  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x18001db11  nop
0x18001db12  jmp     loc_18001D8B7
0x18001db17  mov     rcx, [rsp+298h]; this
  ... truncated ...
```
