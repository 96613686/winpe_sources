# PCPStorageProvider::GetSrkPathQualifier(ushort *)

- ea: `0x180011c60`
- end: `0x1800123dc`
- name: `?GetSrkPathQualifier@PCPStorageProvider@@AEAAJPEAG@Z`
- size: `1916`
- prototype: `int(PCPStorageProvider *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180012640`

## callees

- `0x18000f730`
- `0x1800113f0`
- `0x180011554`
- `0x180011c60`
- `0x1800123f0`
- `0x1800133c4`
- `0x180014a60`
- `0x180015660`
- `0x1800157c0`
- `0x18001c00c`
- `0x180022d14`
- `0x180023510`
- `0x18004e4b8`
- `0x18004f7fc`
- `0x18005247c`
- `0x1800764d0`
- `0x1800768a0`
- `0x180076998`
- `0x1800769bc`
- `0x18007704c`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011f11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012023`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011f11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012023`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011eca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011fdc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011eca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011fdc`
- `tbs!Tbsi_GetDeviceInfo` at `0x180011d3e`
- `tbs!Tbsi_GetDeviceInfo` at `0x180011d3e`

## string_xrefs

- `0x180011ccd`: `ProviderOpenAlgorithmProvider`
- `0x180011c94`: `PCPStorageProvider::GetSrkPathQualifier`
- `0x180011d11`: `TpmProvider::CreateProvider`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall PCPStorageProvider::GetSrkPathQualifier(PCPStorageProvider *this, unsigned __int16 *a2)
{
  unsigned __int16 *v2; // rsi
  void *v3; // rdi
  TpmProvider *v4; // rax
  TpmProvider *v5; // rbx
  TpmProvider *v6; // r14
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  void (__fastcall ***v10)(_QWORD, __int64); // rcx
  char *v11; // rbx
  const wchar_t *v12; // rax
  int v13; // r14d
  int v14; // eax
  unsigned int v15; // ebx
  unsigned int *v16; // rax
  unsigned int *v17; // r14
  char *v18; // rbx
  const wchar_t *v19; // rax
  int v20; // r15d
  int v21; // eax
  unsigned int v22; // ebx
  unsigned int v23; // ebx
  __int64 v24; // rdi
  __int64 v25; // rdx
  __int64 v26; // rcx
  unsigned __int16 v27; // ax
  unsigned __int64 v28; // rdx
  unsigned __int64 i; // rbx
  int v30; // eax
  unsigned int v31; // edi
  const struct std::nothrow_t *v32; // rdx
  void *v33; // rax
  TpmProvider *v34; // rax
  const struct std::nothrow_t *v35; // rdx
  const struct std::nothrow_t *v36; // rdx
  void *v37; // rcx
  const struct std::nothrow_t *v38; // rdx
  int v39; // [rsp+20h] [rbp-128h]
  int v40; // [rsp+20h] [rbp-128h]
  int v41; // [rsp+20h] [rbp-128h]
  int v42; // [rsp+20h] [rbp-128h]
  int v43; // [rsp+20h] [rbp-128h]
  unsigned int Size; // [rsp+40h] [rbp-108h] BYREF
  unsigned int Size_4; // [rsp+44h] [rbp-104h] BYREF
  unsigned __int64 v46; // [rsp+48h] [rbp-100h] BYREF
  void *v47; // [rsp+50h] [rbp-F8h] BYREF
  void **v48; // [rsp+58h] [rbp-F0h] BYREF
  char v49; // [rsp+60h] [rbp-E8h]
  void *v50[2]; // [rsp+68h] [rbp-E0h] BYREF
  __int64 v51; // [rsp+78h] [rbp-D0h]
  unsigned __int16 *v52; // [rsp+80h] [rbp-C8h] BYREF
  unsigned int *v53; // [rsp+88h] [rbp-C0h]
  int *v54[3]; // [rsp+90h] [rbp-B8h] BYREF
  int *v55[3]; // [rsp+A8h] [rbp-A0h] BYREF
  int *v56[5]; // [rsp+C0h] [rbp-88h] BYREF
  char v57; // [rsp+E8h] [rbp-60h]
  __int128 v58; // [rsp+F0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v2 = a2;
  v52 = a2;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v55, L"PCPStorageProvider::GetSrkPathQualifier", 1);
  try
  {
    if ( !v2 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)0x80090027LL,
        v39);
      KspFunctionLogger::~KspFunctionLogger(v55);
      return 2148073511LL;
    }
    *v2 = 0;
    v47 = 0;
    v48 = &v47;
    v49 = 1;
    KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v54, L"ProviderOpenAlgorithmProvider", 1);
    v46 = 0;
    v56[3] = (int *)&v46;
    v3 = 0;
    v56[4] = 0;
    v57 = 1;
    Size_4 = 0;
    KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v56, L"TpmProvider::CreateProvider", (const int *)&Size_4);
    v58 = 0;
    if ( (unsigned int)Tbsi_GetDeviceInfo(16, &v58) || DWORD1(v58) != 2 )
    {
      v34 = (TpmProvider *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
      v5 = v34;
      if ( v34 )
      {
        TpmProvider::TpmProvider(v34);
        *(_QWORD *)v5 = &TpmProvider12::`vftable';
        goto LABEL_7;
      }
    }
    else
    {
      v4 = (TpmProvider *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
      v5 = v4;
      if ( v4 )
      {
        TpmProvider::TpmProvider(v4);
        *(_QWORD *)v5 = &TpmProvider20::`vftable';
LABEL_7:
        v6 = v5;
        v53 = (unsigned int *)v5;
        if ( v5 )
        {
          if ( (*(int (__fastcall **)(TpmProvider *))(*(_QWORD *)v5 + 1128LL))(v5) < 0 )
          {
            v7 = -2144795647;
            Size_4 = -2144795647;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x36,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmprovider.cpp",
              (const char *)0x80290401LL,
              v39);
            (**(void (__fastcall ***)(TpmProvider *, __int64))v6)(v6, 1);
          }
          else
          {
            v3 = v5;
            v7 = Size_4;
          }
          KspFunctionLogger::~KspFunctionLogger(v56);
        }
        else
        {
          Size_4 = -2147024888;
          KspFunctionLogger::~KspFunctionLogger(v56);
          v7 = -2147024888;
        }
        v10 = (void (__fastcall ***)(_QWORD, __int64))v46;
        v46 = (unsigned __int64)v3;
        if ( v10 )
        {
          (**v10)(v10, 1);
          v3 = (void *)v46;
        }
        if ( (v7 & 0x80000000) != 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2D,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcprovider.cpp",
            (const char *)v7,
            v39);
          wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v46, 0);
          KspFunctionLogger::~KspFunctionLogger(v54);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6F,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
            (const char *)v7,
            v43);
          wil::details::lambda_call__lambda_3fe9b03595c8f0fa011834c046571006___::reset(&v48);
          KspFunctionLogger::~KspFunctionLogger(v55);
          return v7;
        }
        v47 = v3;
        v46 = 0;
        KspFunctionLogger::~KspFunctionLogger(v54);
        Size = 0;
        v11 = (char *)v47;
        KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v54, L"ProviderGetProperty", 1);
        v12 = EnumeratedFromStringProperty(0x4Cu);
        KspDebugProvider::TraceLoggingInfo("Property = %ls", v12);
        if ( (*((_DWORD *)v11 + 3) & 1) == 0 )
          EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 16));
        v13 = (*(__int64 (__fastcall **)(char *, __int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 1112LL))(v11, 76, 0, 0);
        if ( (*((_DWORD *)v11 + 3) & 1) == 0 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 16));
        v14 = PcpFromHResult(v13);
        v15 = v14;
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4F,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcprovider.cpp",
            (const char *)(unsigned int)v14,
            (int)&Size);
          KspFunctionLogger::~KspFunctionLogger(v54);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x75,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
            (const char *)v15,
            v41);
          wil::details::lambda_call__lambda_3fe9b03595c8f0fa011834c046571006___::reset(&v48);
          KspFunctionLogger::~KspFunctionLogger(v55);
          return v15;
        }
        KspFunctionLogger::~KspFunctionLogger(v54);
        v16 = (unsigned int *)operator new[](Size, (const struct std::nothrow_t *)&std::nothrow);
        v17 = v16;
        if ( v16 )
          memset_0(v16, 0, Size);
        else
          v17 = 0;
        v53 = v17;
        if ( !v17 )
        {
          wil::details::lambda_call__lambda_3fe9b03595c8f0fa011834c046571006___::reset(&v48);
          KspFunctionLogger::~KspFunctionLogger(v55);
          return 2147942408LL;
        }
        v18 = (char *)v47;
        KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v54, L"ProviderGetProperty", 1);
        v19 = EnumeratedFromStringProperty(0x4Cu);
        KspDebugProvider::TraceLoggingInfo("Property = %ls", v19);
        if ( (*((_DWORD *)v18 + 3) & 1) == 0 )
          EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
        v20 = (*(__int64 (__fastcall **)(char *, __int64, unsigned int *, _QWORD))(*(_QWORD *)v18 + 1112LL))(
                v18,
                76,
                v17,
                Size);
        if ( (*((_DWORD *)v18 + 3) & 1) == 0 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
        v21 = PcpFromHResult(v20);
        v22 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4F,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcprovider.cpp",
            (const char *)(unsigned int)v21,
            (int)&Size);
          KspFunctionLogger::~KspFunctionLogger(v54);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7B,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
            (const char *)v22,
            v42);
          operator delete(v17, v38);
          wil::details::lambda_call__lambda_3fe9b03595c8f0fa011834c046571006___::reset(&v48);
          KspFunctionLogger::~KspFunctionLogger(v55);
          return v22;
        }
        KspFunctionLogger::~KspFunctionLogger(v54);
        v49 = 0;
        ProviderCloseAlgorithmProvider(v47);
        v23 = v17[3];
        v24 = v17[2];
        v27 = HWSecurityBooster::TpmAlgIDFromValue(v26, v25);
        HWSecurityBooster::HashData(v50, v27, (char *)v17 + v24 + 24, v23);
        v28 = 42;
        v46 = 42;
        for ( i = 0; i < (char *)v50[1] - (char *)v50[0]; ++i )
        {
          v30 = StringCchPrintfExW(v2, v28, &v52, &v46, 0x800u, L"%02x");
          v31 = v30;
          if ( v30 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x91,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
              (const char *)(unsigned int)v30,
              v40);
            if ( !v50[0] )
              goto LABEL_45;
            v36 = (const struct std::nothrow_t *)(v51 - (unsigned __int64)v50[0]);
            if ( v51 - (unsigned __int64)v50[0] < 0x1000 )
            {
              v37 = v50[0];
              goto LABEL_44;
            }
            v37 = (void *)*((_QWORD *)v50[0] - 1);
            if ( (unsigned __int64)((char *)v50[0] - (char *)v37 - 8) <= 0x1F )
            {
              v36 = (const struct std::nothrow_t *)((char *)v36 + 39);
LABEL_44:
              operator delete(v37, v36);
              *(_OWORD *)v50 = 0;
              v51 = 0;
LABEL_45:
              operator delete(v17, v35);
              KspFunctionLogger::~KspFunctionLogger(v55);
              return v31;
            }
LABEL_56:
            __fastfail(5u);
          }
          v28 = v46;
          v2 = v52;
        }
        if ( v50[0] )
        {
          v32 = (const struct std::nothrow_t *)(v51 - (unsigned __int64)v50[0]);
          if ( v51 - (unsigned __int64)v50[0] >= 0x1000 )
          {
            v33 = (void *)*((_QWORD *)v50[0] - 1);
            if ( (unsigned __int64)((char *)v50[0] - (char *)v33 - 8) > 0x1F )
              goto LABEL_56;
            v32 = (const struct std::nothrow_t *)((char *)v32 + 39);
          }
          else
          {
            v33 = v50[0];
          }
          operator delete(v33, v32);
          *(_OWORD *)v50 = 0;
          v51 = 0;
        }
        operator delete(v17, (const struct std::nothrow_t *)v28);
        KspFunctionLogger::~KspFunctionLogger(v55);
        return 0;
      }
    }
    v5 = 0;
    goto LABEL_7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x95,
                           (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180011c60  push    rbx
0x180011c62  push    rsi
0x180011c63  push    rdi
0x180011c64  push    r12
0x180011c66  push    r14
0x180011c68  push    r15
0x180011c6a  sub     rsp, 118h
0x180011c71  mov     rax, cs:__security_cookie
0x180011c78  xor     rax, rsp
0x180011c7b  mov     [rsp+148h+var_48], rax
0x180011c83  mov     rsi, rdx
0x180011c86  mov     [rsp+148h+var_C8], rdx
0x180011c8e  xor     r12d, r12d
0x180011c91  mov     r8b, 1; bool
0x180011c94  lea     rdx, aPcpstorageprov_14; "PCPStorageProvider::GetSrkPathQualifier"
0x180011c9b  lea     rcx, [rsp+148h+var_A0]; this
0x180011ca3  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180011ca8  nop
0x180011ca9  test    rsi, rsi
0x180011cac  jz      loc_180011DBE
0x180011cb2  mov     [rsi], r12w
0x180011cb6  mov     [rsp+148h+var_F8], r12
0x180011cbb  lea     rax, [rsp+148h+var_F8]
0x180011cc0  mov     [rsp+148h+var_F0], rax
0x180011cc5  mov     [rsp+148h+var_E8], 1
0x180011cca  mov     r8b, 1; bool
0x180011ccd  lea     rdx, aProvideropenal; "ProviderOpenAlgorithmProvider"
0x180011cd4  lea     rcx, [rsp+148h+var_B8]; this
0x180011cdc  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180011ce1  nop
0x180011ce2  mov     [rsp+148h+var_100], r12
0x180011ce7  lea     rax, [rsp+148h+var_100]
0x180011cec  mov     [rsp+148h+var_70], rax
0x180011cf4  mov     edi, r12d
0x180011cf7  mov     [rsp+148h+var_68], r12
0x180011cff  mov     [rsp+148h+var_60], 1
0x180011d07  mov     dword ptr [rsp+148h+Size+4], r12d
0x180011d0c  lea     r8, [rsp+148h+Size+4]; int *
0x180011d11  lea     rdx, aTpmproviderCre; "TpmProvider::CreateProvider"
0x180011d18  lea     rcx, [rsp+148h+var_88]; this
0x180011d20  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x180011d25  nop
0x180011d26  xorps   xmm0, xmm0
0x180011d29  movups  [rsp+148h+var_58], xmm0
0x180011d31  lea     rdx, [rsp+148h+var_58]
0x180011d39  mov     ecx, 10h
0x180011d3e  call    cs:__imp_Tbsi_GetDeviceInfo
0x180011d45  nop     dword ptr [rax+rax+00h]
0x180011d4a  test    eax, eax
0x180011d4c  jnz     loc_18001214D
0x180011d52  cmp     dword ptr [rsp+148h+var_58+4], 2
0x180011d5a  jnz     loc_18001214D
0x180011d60  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011d67  mov     ecx, 58h ; 'X'; unsigned __int64
0x180011d6c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180011d71  mov     rbx, rax
0x180011d74  test    rax, rax
0x180011d77  jz      loc_1800121F4
0x180011d7d  mov     rcx, rax; this
0x180011d80  call    ??0TpmProvider@@IEAA@XZ; TpmProvider::TpmProvider(void)
0x180011d85  lea     rax, ??_7TpmProvider20@@6B@; const TpmProvider20::`vftable'
0x180011d8c  mov     [rbx], rax
0x180011d8f  mov     r14, rbx
0x180011d92  mov     [rsp+148h+var_C0], rbx
0x180011d9a  test    rbx, rbx
0x180011d9d  jnz     short loc_180011E12
0x180011d9f  mov     dword ptr [rsp+148h+Size+4], 80070008h
0x180011da7  lea     rcx, [rsp+148h+var_88]; this
0x180011daf  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180011db4  mov     ebx, 80070008h
0x180011db9  jmp     loc_180011E41
0x180011dbe  mov     rcx, [rsp+148h]; this
0x180011dc6  mov     r9d, 80090027h; char *
0x180011dcc  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180011dd3  mov     edx, 63h ; 'c'; void *
0x180011dd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011ddd  nop
0x180011dde  lea     rcx, [rsp+148h+var_A0]; this
0x180011de6  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180011deb  mov     eax, 80090027h
0x180011df0  mov     rcx, [rsp+148h+var_48]
0x180011df8  xor     rcx, rsp; StackCookie
0x180011dfb  call    __security_check_cookie
0x180011e00  add     rsp, 118h
0x180011e07  pop     r15
0x180011e09  pop     r14
0x180011e0b  pop     r12
0x180011e0d  pop     rdi
0x180011e0e  pop     rsi
0x180011e0f  pop     rbx
0x180011e10  retn
0x180011e12  mov     rax, [r14]
0x180011e15  mov     rcx, r14
0x180011e18  mov     rax, [rax+468h]
0x180011e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e24  test    eax, eax
0x180011e26  js      loc_1800122D9
0x180011e2c  mov     rdi, rbx
0x180011e2f  mov     ebx, dword ptr [rsp+148h+Size+4]
0x180011e33  lea     rcx, [rsp+148h+var_88]; this
0x180011e3b  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180011e40  nop
0x180011e41  mov     rcx, [rsp+148h+var_100]
0x180011e46  mov     [rsp+148h+var_100], rdi
0x180011e4b  test    rcx, rcx
0x180011e4e  jz      short loc_180011E65
0x180011e50  mov     rax, [rcx]
0x180011e53  mov     edx, 1
0x180011e58  mov     rax, [rax]
0x180011e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e60  mov     rdi, [rsp+148h+var_100]
0x180011e65  test    ebx, ebx
0x180011e67  js      loc_180012325
0x180011e6d  mov     [rsp+148h+var_F8], rdi
0x180011e72  mov     [rsp+148h+var_100], r12
0x180011e77  lea     rcx, [rsp+148h+var_B8]; this
0x180011e7f  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180011e84  mov     dword ptr [rsp+148h+Size], r12d
0x180011e89  mov     rbx, [rsp+148h+var_F8]
0x180011e8e  mov     r8b, 1; bool
0x180011e91  lea     rdx, aProvidergetpro; "ProviderGetProperty"
0x180011e98  lea     rcx, [rsp+148h+var_B8]; this
0x180011ea0  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180011ea5  nop
0x180011ea6  mov     ecx, 4Ch ; 'L'
0x180011eab  call    ?EnumeratedFromStringProperty@@YAPEBGW4KspProp@@@Z; EnumeratedFromStringProperty(KspProp)
0x180011eb0  mov     rdx, rax
0x180011eb3  lea     rcx, aPropertyLs; "Property = %ls"
0x180011eba  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x180011ebf  mov     eax, [rbx+0Ch]
0x180011ec2  test    al, 1
0x180011ec4  jnz     short loc_180011ED6
0x180011ec6  lea     rcx, [rbx+10h]; lpCriticalSection
0x180011eca  call    cs:__imp_EnterCriticalSection
0x180011ed1  nop     dword ptr [rax+rax+00h]
0x180011ed6  mov     rax, [rbx]
0x180011ed9  mov     dword ptr [rsp+148h+var_120], r12d
0x180011ede  lea     rcx, [rsp+148h+Size]
0x180011ee3  mov     qword ptr [rsp+148h+var_128], rcx; int
0x180011ee8  xor     r9d, r9d
0x180011eeb  xor     r8d, r8d
0x180011eee  mov     edx, 4Ch ; 'L'
0x180011ef3  mov     rcx, rbx
0x180011ef6  mov     rax, [rax+458h]
0x180011efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f02  mov     r14d, eax
0x180011f05  mov     edx, [rbx+0Ch]
0x180011f08  test    dl, 1
0x180011f0b  jnz     short loc_180011F1D
0x180011f0d  lea     rcx, [rbx+10h]; lpCriticalSection
0x180011f11  call    cs:__imp_LeaveCriticalSection
0x180011f18  nop     dword ptr [rax+rax+00h]
0x180011f1d  mov     ecx, r14d; int
0x180011f20  call    ?PcpFromHResult@@YAJJ@Z; PcpFromHResult(long)
0x180011f25  mov     ebx, eax
0x180011f27  test    eax, eax
0x180011f29  js      loc_180012204
0x180011f2f  lea     rcx, [rsp+148h+var_B8]; this
0x180011f37  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180011f3c  mov     ebx, dword ptr [rsp+148h+Size]
0x180011f40  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011f47  mov     ecx, ebx; unsigned __int64
0x180011f49  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180011f4e  mov     r14, rax
0x180011f51  test    rax, rax
0x180011f54  jz      loc_1800121FC
0x180011f5a  mov     r8d, ebx; Size
0x180011f5d  xor     edx, edx; Val
0x180011f5f  mov     rcx, rax; void *
0x180011f62  call    memset_0
0x180011f67  mov     [rsp+148h+var_C0], r14
0x180011f6f  test    r14, r14
0x180011f72  jnz     short loc_180011F96
0x180011f74  lea     rcx, [rsp+148h+var_F0]
0x180011f79  call    wil__details__lambda_call__lambda_3fe9b03595c8f0fa011834c046571006_____reset
0x180011f7e  nop
0x180011f7f  lea     rcx, [rsp+148h+var_A0]; this
0x180011f87  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180011f8c  mov     eax, 80070008h
0x180011f91  jmp     loc_180011DF0
0x180011f96  mov     r15d, dword ptr [rsp+148h+Size]
0x180011f9b  mov     rbx, [rsp+148h+var_F8]
0x180011fa0  mov     r8b, 1; bool
0x180011fa3  lea     rdx, aProvidergetpro; "ProviderGetProperty"
0x180011faa  lea     rcx, [rsp+148h+var_B8]; this
0x180011fb2  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180011fb7  nop
0x180011fb8  mov     ecx, 4Ch ; 'L'
0x180011fbd  call    ?EnumeratedFromStringProperty@@YAPEBGW4KspProp@@@Z; EnumeratedFromStringProperty(KspProp)
0x180011fc2  mov     rdx, rax
0x180011fc5  lea     rcx, aPropertyLs; "Property = %ls"
0x180011fcc  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x180011fd1  mov     eax, [rbx+0Ch]
0x180011fd4  test    al, 1
0x180011fd6  jnz     short loc_180011FE8
0x180011fd8  lea     rcx, [rbx+10h]; lpCriticalSection
0x180011fdc  call    cs:__imp_EnterCriticalSection
0x180011fe3  nop     dword ptr [rax+rax+00h]
0x180011fe8  mov     rax, [rbx]
0x180011feb  mov     dword ptr [rsp+148h+var_120], r12d
0x180011ff0  lea     rcx, [rsp+148h+Size]
0x180011ff5  mov     qword ptr [rsp+148h+var_128], rcx; int
0x180011ffa  mov     r9d, r15d
0x180011ffd  mov     r8, r14
0x180012000  mov     edx, 4Ch ; 'L'
0x180012005  mov     rcx, rbx
0x180012008  mov     rax, [rax+458h]
0x18001200f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012014  mov     r15d, eax
0x180012017  mov     edx, [rbx+0Ch]
0x18001201a  test    dl, 1
0x18001201d  jnz     short loc_18001202F
0x18001201f  lea     rcx, [rbx+10h]; lpCriticalSection
0x180012023  call    cs:__imp_LeaveCriticalSection
0x18001202a  nop     dword ptr [rax+rax+00h]
0x18001202f  mov     ecx, r15d; int
0x180012032  call    ?PcpFromHResult@@YAJJ@Z; PcpFromHResult(long)
0x180012037  mov     ebx, eax
0x180012039  test    eax, eax
0x18001203b  js      loc_18001226A
0x180012041  lea     rcx, [rsp+148h+var_B8]; this
0x180012049  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18001204e  mov     [rsp+148h+var_E8], 0
0x180012053  mov     rcx, [rsp+148h+var_F8]; void *
0x180012058  call    ?ProviderCloseAlgorithmProvider@@YAJPEAX@Z; ProviderCloseAlgorithmProvider(void *)
0x18001205d  mov     ebx, [r14+0Ch]
0x180012061  mov     edi, [r14+8]
0x180012065  call    ?TpmAlgIDFromValue@HWSecurityBooster@@YA?AW4TpmAlgID@@G@Z; HWSecurityBooster::TpmAlgIDFromValue(ushort)
0x18001206a  mov     r9d, ebx
0x18001206d  lea     r8, [r14+18h]
0x180012071  add     r8, rdi
0x180012074  movzx   edx, ax
0x180012077  lea     rcx, [rsp+148h+var_E0]
0x18001207c  call    ?HashData@HWSecurityBooster@@YA?AV?$vector@EV?$allocator@E@std@@@std@@W4TpmAlgID@@PEBE_K@Z; HWSecurityBooster::HashData(TpmAlgID,uchar const *,unsigned __int64)
0x180012081  mov     edx, 2Ah ; '*'; unsigned __int64
0x180012086  mov     [rsp+148h+var_100], rdx
0x18001208b  mov     rbx, r12
0x18001208e  lea     r15, a02x; "%02x"
0x180012095  nop     word ptr [rax+rax+00000000h]
0x1800120a0  mov     rax, [rsp+148h+var_E0+8]
0x1800120a5  mov     rcx, [rsp+148h+var_E0]
0x1800120aa  sub     rax, rcx
0x1800120ad  cmp     rbx, rax
0x1800120b0  jnb     short loc_1800120F8
0x1800120b2  movzx   eax, byte ptr [rcx+rbx]
0x1800120b6  mov     [rsp+148h+var_118], eax
0x1800120ba  mov     [rsp+148h+var_120], r15; unsigned __int16 *
0x1800120bf  mov     [rsp+148h+var_128], 800h; int
0x1800120c7  lea     r9, [rsp+148h+var_100]; unsigned __int64 *
0x1800120cc  lea     r8, [rsp+148h+var_C8]; unsigned __int16 **
0x1800120d4  mov     rcx, rsi; pszDest
0x1800120d7  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800120dc  mov     edi, eax
0x1800120de  test    eax, eax
0x1800120e0  js      loc_180012181
0x1800120e6  inc     rbx
0x1800120e9  mov     rdx, [rsp+148h+var_100]
0x1800120ee  mov     rsi, [rsp+148h+var_C8]
0x1800120f6  jmp     short loc_1800120A0
0x1800120f8  test    rcx, rcx
0x1800120fb  jz      short loc_18001212B
0x1800120fd  mov     rdx, [rsp+148h+var_D0]
0x180012102  sub     rdx, rcx; struct std::nothrow_t *
0x180012105  cmp     rdx, 1000h
0x18001210c  jnb     loc_1800123B2
0x180012112  mov     rax, rcx
0x180012115  mov     rcx, rax; void *
0x180012118  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001211d  xorps   xmm0, xmm0
0x180012120  movdqu  xmmword ptr [rsp+148h+var_E0], xmm0
0x180012126  mov     [rsp+148h+var_D0], r12
0x18001212b  test    r14, r14
0x18001212e  jz      short loc_180012139
0x180012130  mov     rcx, r14; void *
0x180012133  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012138  nop
0x180012139  lea     rcx, [rsp+148h+var_A0]; this
0x180012141  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180012146  xor     eax, eax
0x180012148  jmp     loc_180011DF0
0x18001214d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012154  mov     ecx, 58h ; 'X'; unsigned __int64
0x180012159  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001215e  mov     rbx, rax
0x180012161  test    rax, rax
0x180012164  jz      loc_1800121F4
0x18001216a  mov     rcx, rax; this
0x18001216d  call    ??0TpmProvider@@IEAA@XZ; TpmProvider::TpmProvider(void)
0x180012172  lea     rax, ??_7TpmProvider12@@6B@; const TpmProvider12::`vftable'
0x180012179  mov     [rbx], rax
0x18001217c  jmp     loc_180011D8F
0x180012181  mov     rcx, [rsp+148h]; this
0x180012189  mov     r9d, edi; char *
0x18001218c  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180012193  mov     edx, 91h; void *
0x180012198  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001219d  mov     rax, [rsp+148h+var_E0]
0x1800121a2  test    rax, rax
0x1800121a5  jz      short loc_1800121D2
0x1800121a7  mov     rdx, [rsp+148h+var_D0]
  ... truncated ...
```
