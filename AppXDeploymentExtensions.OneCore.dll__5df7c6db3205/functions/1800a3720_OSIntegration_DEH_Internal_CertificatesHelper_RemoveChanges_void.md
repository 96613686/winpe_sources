# OSIntegration::DEH::Internal::CertificatesHelper::RemoveChanges(void)

- ea: `0x1800a3720`
- end: `0x1800a3a21`
- name: `?RemoveChanges@CertificatesHelper@Internal@DEH@OSIntegration@@UEAAJXZ`
- size: `769`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::CertificatesHelper *this)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18005ded4`
- `0x18006c4cc`
- `0x180084820`
- `0x180092c30`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800a3720`
- `0x1800b8300`
- `0x1800ce12c`
- `0x18013b8bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a3787`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a384d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a390d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a3787`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a384d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a390d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a37a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a3866`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a3926`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a37a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a3866`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a3926`
- `profapi!__imp_GetAppContainerRegistryHandle` at `0x1800a37fa`
- `profapi!__imp_GetAppContainerRegistryHandle` at `0x1800a37fa`

## string_xrefs

- `0x1800a37ad`: `onecore\admin\appmodel\OSIM\src\deh\appx\Common\AppContainerImpersonate.hpp`
- `0x1800a3877`: `onecore\admin\appmodel\OSIM\src\deh\appx\Common\AppContainerImpersonate.hpp`
- `0x1800a3937`: `onecore\admin\appmodel\OSIM\src\deh\appx\Common\AppContainerImpersonate.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OSIntegration::DEH::Internal::CertificatesHelper::RemoveChanges(
        OSIntegration::DEH::Internal::CertificatesHelper *this)
{
  const struct OSIntegration::Package *v2; // rdx
  int v3; // eax
  wil::details::in1diag3 *v4; // rcx
  HANDLE v5; // rbx
  int v6; // edi
  Common *v7; // rcx
  int AppContainerRegistryHandle; // eax
  unsigned int v10; // edi
  HANDLE v11; // rbx
  int HResultFromLastError; // esi
  Common *v13; // rcx
  int v14; // eax
  unsigned int v15; // esi
  HANDLE v16; // rbx
  int v17; // edi
  Common *v18; // rcx
  int v19; // eax
  int v20; // eax
  unsigned __int64 i; // rdi
  OSIntegration::DEH::Internal::CertificatesParsedCertificateElement *v22; // rcx
  int v23; // eax
  int savedregs; // [rsp+20h] [rbp+0h]
  int savedregsa; // [rsp+20h] [rbp+0h]
  int savedregsb; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  __int64 v28; // [rsp+40h] [rbp+20h] BYREF
  HANDLE Token; // [rsp+48h] [rbp+28h] BYREF
  __int64 v30; // [rsp+50h] [rbp+30h] BYREF

  v2 = (const struct OSIntegration::Package *)*((_QWORD *)this + 3);
  if ( *((_BYTE *)v2 + 400) && !*((_BYTE *)v2 + 368) )
    return 0;
  Token = (HANDLE)-1LL;
  v3 = OSIntegration::Tools::AppContainerImpersonate::DoImpersonation(
         (OSIntegration::Tools::AppContainerImpersonate *)&Token,
         v2);
  v4 = retaddr;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2DF,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\certificates\\certificates.cpp",
      (const char *)(unsigned int)v3,
      savedregs);
    goto LABEL_5;
  }
  if ( !*((_DWORD *)this + 24) && !*((_DWORD *)this + 25) )
  {
LABEL_44:
    for ( i = 0; i < *((_QWORD *)this + 10); ++i )
    {
      if ( !*(_QWORD *)(*((_QWORD *)this + 8) + 8 * i) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v4);
      if ( i < *((_QWORD *)this + 10) )
        v22 = *(OSIntegration::DEH::Internal::CertificatesParsedCertificateElement **)(*((_QWORD *)this + 8) + 8 * i);
      else
        v22 = 0;
      v23 = OSIntegration::DEH::Internal::CertificatesParsedCertificateElement::RemoveChanges(v22);
      v15 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x317,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\certificates\\certificates.cpp",
          (const char *)(unsigned int)v23,
          savedregs);
        goto LABEL_29;
      }
    }
    goto LABEL_5;
  }
  v30 = 0;
  v28 = 0;
  AppContainerRegistryHandle = GetAppContainerRegistryHandle(131097, &v30);
  v10 = AppContainerRegistryHandle;
  if ( AppContainerRegistryHandle < 0 )
  {
    if ( AppContainerRegistryHandle != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F3,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\certificates\\certificates.cpp",
        (const char *)(unsigned int)AppContainerRegistryHandle,
        savedregs);
      Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&v28);
      Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&v30);
      v11 = Token;
      if ( Token != (HANDLE)-1LL )
      {
        HResultFromLastError = 0;
        if ( !SetThreadToken(0, Token) )
          HResultFromLastError = Common::GetHResultFromLastError(v13);
        if ( v11 )
          CloseHandle(v11);
        if ( HResultFromLastError < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8F,
            (unsigned int)"onecore\\admin\\appmodel\\OSIM\\src\\deh\\appx\\Common\\AppContainerImpersonate.hpp",
            (const char *)(unsigned int)HResultFromLastError,
            savedregsa);
      }
      return v10;
    }
LABEL_25:
    Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&v28);
    Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&v30);
LABEL_5:
    v5 = Token;
    if ( Token != (HANDLE)-1LL )
    {
      v6 = 0;
      if ( !SetThreadToken(0, Token) )
        v6 = Common::GetHResultFromLastError(v7);
      if ( v5 )
        CloseHandle(v5);
      if ( v6 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8F,
          (unsigned int)"onecore\\admin\\appmodel\\OSIM\\src\\deh\\appx\\Common\\AppContainerImpersonate.hpp",
          (const char *)(unsigned int)v6,
          savedregs);
    }
    return 0;
  }
  v14 = Common::RegistryKey::OpenSubKey(
          (Common::RegistryKey *)&v30,
          L"Software\\Microsoft\\SystemCertificates",
          0x2001Fu,
          (struct Common::AutoHandleHKEY *)&v28);
  v15 = v14;
  if ( v14 >= 0 )
  {
    if ( *((_DWORD *)this + 24) )
    {
      v19 = Common::RegistryKey::DeleteValue((Common::RegistryKey *)&v28, L"TrustFlags");
      if ( v19 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x306,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\certificates\\certificates.cpp",
          (const char *)(unsigned int)v19,
          savedregs);
    }
    if ( *((_DWORD *)this + 25) )
    {
      v20 = Common::RegistryKey::DeleteValue((Common::RegistryKey *)&v28, L"SelectionFlags");
      if ( v20 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x30E,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\certificates\\certificates.cpp",
          (const char *)(unsigned int)v20,
          savedregs);
    }
    Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&v28);
    Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&v30);
    goto LABEL_44;
  }
  if ( v14 == -2147024894 )
    goto LABEL_25;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2FD,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\certificates\\certificates.cpp",
    (const char *)(unsigned int)v14,
    savedregs);
  Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&v28);
  Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&v30);
LABEL_29:
  v16 = Token;
  if ( Token != (HANDLE)-1LL )
  {
    v17 = 0;
    if ( !SetThreadToken(0, Token) )
      v17 = Common::GetHResultFromLastError(v18);
    if ( v16 )
      CloseHandle(v16);
    if ( v17 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecore\\admin\\appmodel\\OSIM\\src\\deh\\appx\\Common\\AppContainerImpersonate.hpp",
        (const char *)(unsigned int)v17,
        savedregsb);
  }
  return v15;
}

```

## disassembly

```asm
0x1800a3720  mov     [rsp-18h+arg_18], rbx
0x1800a3725  push    rbp
0x1800a3726  push    rsi
0x1800a3727  push    rdi; int
0x1800a3728  mov     rbp, rsp
0x1800a372b  sub     rsp, 20h
0x1800a372f  mov     rbx, rcx
0x1800a3732  mov     rdx, [rcx+18h]; struct OSIntegration::Package *
0x1800a3736  cmp     byte ptr [rdx+190h], 0
0x1800a373d  jz      short loc_1800A3748
0x1800a373f  cmp     byte ptr [rdx+170h], 0
0x1800a3746  jz      short loc_1800A37C2
0x1800a3748  mov     [rbp+Token], 0FFFFFFFFFFFFFFFFh
0x1800a3750  lea     rcx, [rbp+Token]; this
0x1800a3754  call    ?DoImpersonation@AppContainerImpersonate@Tools@OSIntegration@@QEAAJPEBVPackage@3@@Z; OSIntegration::Tools::AppContainerImpersonate::DoImpersonation(OSIntegration::Package const *)
0x1800a3759  mov     rcx, [rbp+18h]; this
0x1800a375d  test    eax, eax
0x1800a375f  jns     short loc_1800A37D1
0x1800a3761  mov     r9d, eax; char *
0x1800a3764  lea     r8, aOnecoreAdminAp_131; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800a376b  mov     edx, 2DFh; void *
0x1800a3770  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a3775  nop
0x1800a3776  mov     rbx, [rbp+Token]
0x1800a377a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800a377e  jz      short loc_1800A37C2
0x1800a3780  xor     edi, edi
0x1800a3782  mov     rdx, rbx; Token
0x1800a3785  xor     ecx, ecx; Thread
0x1800a3787  call    cs:__imp_SetThreadToken
0x1800a378d  test    eax, eax
0x1800a378f  jnz     short loc_1800A3798
0x1800a3791  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x1800a3796  mov     edi, eax
0x1800a3798  test    rbx, rbx
0x1800a379b  jz      short loc_1800A37A6
0x1800a379d  mov     rcx, rbx; hObject
0x1800a37a0  call    cs:__imp_CloseHandle
0x1800a37a6  test    edi, edi
0x1800a37a8  jns     short loc_1800A37C2
0x1800a37aa  mov     r9d, edi; char *
0x1800a37ad  lea     r8, aOnecoreAdminAp_143; "onecore\\admin\\appmodel\\OSIM\\src\\de"...
0x1800a37b4  mov     edx, 8Fh; void *
0x1800a37b9  mov     rcx, [rbp+18h]; this
0x1800a37bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a37c2  xor     eax, eax
0x1800a37c4  mov     rbx, [rsp+20h+arg_18]
0x1800a37c9  add     rsp, 20h
0x1800a37cd  pop     rdi
0x1800a37ce  pop     rsi
0x1800a37cf  pop     rbp
0x1800a37d0  retn
0x1800a37d1  cmp     dword ptr [rbx+60h], 0
0x1800a37d5  jnz     short loc_1800A37E1
0x1800a37d7  cmp     dword ptr [rbx+64h], 0
0x1800a37db  jz      loc_1800A39C5
0x1800a37e1  mov     [rbp+arg_10], 0
0x1800a37e9  mov     [rbp+arg_0], 0
0x1800a37f1  lea     rdx, [rbp+arg_10]
0x1800a37f5  mov     ecx, 20019h
0x1800a37fa  call    cs:__imp_GetAppContainerRegistryHandle
0x1800a3800  mov     edi, eax
0x1800a3802  test    eax, eax
0x1800a3804  jns     loc_1800A38A6
0x1800a380a  cmp     eax, 80070002h
0x1800a380f  jz      short loc_1800A388F
0x1800a3811  mov     rcx, [rbp+18h]; this
0x1800a3815  mov     r9d, eax; char *
0x1800a3818  lea     r8, aOnecoreAdminAp_131; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800a381f  mov     edx, 2F3h; void *
0x1800a3824  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3829  lea     rcx, [rbp+arg_0]; this
0x1800a382d  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x1800a3832  lea     rcx, [rbp+arg_10]; this
0x1800a3836  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x1800a383b  nop
0x1800a383c  mov     rbx, [rbp+Token]
0x1800a3840  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800a3844  jz      short loc_1800A3888
0x1800a3846  xor     esi, esi
0x1800a3848  mov     rdx, rbx; Token
0x1800a384b  xor     ecx, ecx; Thread
0x1800a384d  call    cs:__imp_SetThreadToken
0x1800a3853  test    eax, eax
0x1800a3855  jnz     short loc_1800A385E
0x1800a3857  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x1800a385c  mov     esi, eax
0x1800a385e  test    rbx, rbx
0x1800a3861  jz      short loc_1800A386C
0x1800a3863  mov     rcx, rbx; hObject
0x1800a3866  call    cs:__imp_CloseHandle
0x1800a386c  test    esi, esi
0x1800a386e  jns     short loc_1800A3888
0x1800a3870  mov     rcx, [rbp+18h]; this
0x1800a3874  mov     r9d, esi; char *
0x1800a3877  lea     r8, aOnecoreAdminAp_143; "onecore\\admin\\appmodel\\OSIM\\src\\de"...
0x1800a387e  mov     edx, 8Fh; void *
0x1800a3883  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3888  mov     eax, edi
0x1800a388a  jmp     loc_1800A37C4
0x1800a388f  lea     rcx, [rbp+arg_0]; this
0x1800a3893  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x1800a3898  lea     rcx, [rbp+arg_10]; this
0x1800a389c  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x1800a38a1  jmp     loc_1800A3776
0x1800a38a6  lea     r9, [rbp+arg_0]; struct Common::AutoHandleHKEY *
0x1800a38aa  mov     r8d, 2001Fh; unsigned int
0x1800a38b0  lea     rdx, aSoftwareMicros_27; "Software\\Microsoft\\SystemCertificates"
0x1800a38b7  lea     rcx, [rbp+arg_10]; this
0x1800a38bb  call    ?OpenSubKey@RegistryKey@Common@@QEAAJPEBGKAEAVAutoHandleHKEY@2@@Z; Common::RegistryKey::OpenSubKey(ushort const *,ulong,Common::AutoHandleHKEY &)
0x1800a38c0  mov     esi, eax
0x1800a38c2  test    eax, eax
0x1800a38c4  jns     loc_1800A394F
0x1800a38ca  cmp     eax, 80070002h
0x1800a38cf  jz      short loc_1800A388F
0x1800a38d1  mov     rcx, [rbp+18h]; this
0x1800a38d5  mov     r9d, eax; char *
0x1800a38d8  lea     r8, aOnecoreAdminAp_131; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800a38df  mov     edx, 2FDh; void *
0x1800a38e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a38e9  lea     rcx, [rbp+arg_0]; this
0x1800a38ed  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x1800a38f2  lea     rcx, [rbp+arg_10]; this
0x1800a38f6  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x1800a38fb  nop
0x1800a38fc  mov     rbx, [rbp+Token]
0x1800a3900  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800a3904  jz      short loc_1800A3948
0x1800a3906  xor     edi, edi
0x1800a3908  mov     rdx, rbx; Token
0x1800a390b  xor     ecx, ecx; Thread
0x1800a390d  call    cs:__imp_SetThreadToken
0x1800a3913  test    eax, eax
0x1800a3915  jnz     short loc_1800A391E
0x1800a3917  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x1800a391c  mov     edi, eax
0x1800a391e  test    rbx, rbx
0x1800a3921  jz      short loc_1800A392C
0x1800a3923  mov     rcx, rbx; hObject
0x1800a3926  call    cs:__imp_CloseHandle
0x1800a392c  test    edi, edi
0x1800a392e  jns     short loc_1800A3948
0x1800a3930  mov     rcx, [rbp+18h]; this
0x1800a3934  mov     r9d, edi; char *
0x1800a3937  lea     r8, aOnecoreAdminAp_143; "onecore\\admin\\appmodel\\OSIM\\src\\de"...
0x1800a393e  mov     edx, 8Fh; void *
0x1800a3943  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3948  mov     eax, esi
0x1800a394a  jmp     loc_1800A37C4
0x1800a394f  cmp     dword ptr [rbx+60h], 0
0x1800a3953  jz      short loc_1800A3981
0x1800a3955  lea     rdx, aTrustflags; "TrustFlags"
0x1800a395c  lea     rcx, [rbp+arg_0]; this
0x1800a3960  call    ?DeleteValue@RegistryKey@Common@@QEAAJPEBG@Z; Common::RegistryKey::DeleteValue(ushort const *)
0x1800a3965  mov     rcx, [rbp+18h]; this
0x1800a3969  test    eax, eax
0x1800a396b  jns     short loc_1800A3981
0x1800a396d  mov     r9d, eax; char *
0x1800a3970  lea     r8, aOnecoreAdminAp_131; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800a3977  mov     edx, 306h; void *
0x1800a397c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a3981  cmp     dword ptr [rbx+64h], 0
0x1800a3985  jz      short loc_1800A39B3
0x1800a3987  lea     rdx, aSelectionflags; "SelectionFlags"
0x1800a398e  lea     rcx, [rbp+arg_0]; this
0x1800a3992  call    ?DeleteValue@RegistryKey@Common@@QEAAJPEBG@Z; Common::RegistryKey::DeleteValue(ushort const *)
0x1800a3997  mov     rcx, [rbp+18h]; this
0x1800a399b  test    eax, eax
0x1800a399d  jns     short loc_1800A39B3
0x1800a399f  mov     r9d, eax; char *
0x1800a39a2  lea     r8, aOnecoreAdminAp_131; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800a39a9  mov     edx, 30Eh; void *
0x1800a39ae  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a39b3  lea     rcx, [rbp+arg_0]; this
0x1800a39b7  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x1800a39bc  lea     rcx, [rbp+arg_10]; this
0x1800a39c0  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x1800a39c5  xor     edi, edi
0x1800a39c7  cmp     rdi, [rbx+50h]
0x1800a39cb  jnb     loc_1800A3776
0x1800a39d1  mov     rax, [rbx+40h]
0x1800a39d5  cmp     qword ptr [rax+rdi*8], 0
0x1800a39da  jnz     short loc_1800A39E1
0x1800a39dc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a39e1  cmp     rdi, [rbx+50h]
0x1800a39e5  jb      short loc_1800A39EB
0x1800a39e7  xor     ecx, ecx
0x1800a39e9  jmp     short loc_1800A39F3
0x1800a39eb  mov     rax, [rbx+40h]
0x1800a39ef  mov     rcx, [rax+rdi*8]; this
0x1800a39f3  call    ?RemoveChanges@CertificatesParsedCertificateElement@Internal@DEH@OSIntegration@@QEAAJXZ; OSIntegration::DEH::Internal::CertificatesParsedCertificateElement::RemoveChanges(void)
0x1800a39f8  mov     esi, eax
0x1800a39fa  test    eax, eax
0x1800a39fc  js      short loc_1800A3A03
0x1800a39fe  inc     rdi
0x1800a3a01  jmp     short loc_1800A39C7
0x1800a3a03  mov     rcx, [rbp+18h]; this
0x1800a3a07  mov     r9d, esi; char *
0x1800a3a0a  lea     r8, aOnecoreAdminAp_131; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800a3a11  mov     edx, 317h; void *
0x1800a3a16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3a1b  jmp     loc_1800A38FC
```
