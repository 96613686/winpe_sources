# GetEndorsementSession(wistd::unique_ptr<tpm12class::TPM_SESSION,wistd::default_delete<tpm12class::TPM_SESSION>> &)

- ea: `0x18004f1dc`
- end: `0x18004f7f3`
- name: `?GetEndorsementSession@@YAJAEAV?$unique_ptr@VTPM_SESSION@tpm12class@@U?$default_delete@VTPM_SESSION@tpm12class@@@wistd@@@wistd@@@Z`
- size: `1559`
- prototype: ``
- caller_count: `4`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x18004f050`
- `0x180072c20`
- `0x180073810`
- `0x180086b10`

## callees

- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180029a20`
- `0x18004f1dc`
- `0x18004f7fc`
- `0x18005ad1c`
- `0x180061bac`
- `0x180068a48`
- `0x180068a8c`
- `0x18006b964`
- `0x1800764d0`
- `0x1800768a0`
- `0x1800769bc`
- `0x18007704c`
- `0x18009a56c`
- `0x1800a3ce8`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f2c0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f31c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f515`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f5da`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f6b9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f746`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f2c0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f31c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f515`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f5da`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f6b9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f746`
- `ntdll!RtlGetPersistedStateLocation` at `0x18004f26f`
- `ntdll!RtlGetPersistedStateLocation` at `0x18004f4b3`
- `ntdll!RtlGetPersistedStateLocation` at `0x18004f675`
- `ntdll!RtlGetPersistedStateLocation` at `0x18004f26f`
- `ntdll!RtlGetPersistedStateLocation` at `0x18004f4b3`
- `ntdll!RtlGetPersistedStateLocation` at `0x18004f675`

## string_xrefs

- `0x18004f25f`: `System\CurrentControlSet\Services\TPM\WMI\Admin`
- `0x18004f4a3`: `System\CurrentControlSet\Services\TPM\WMI\Endorsement`
- `0x18004f665`: `System\CurrentControlSet\Services\TPM\WMI\User`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetEndorsementSession(__int64 *a1)
{
  int PersistedStateLocation; // eax
  __int64 v3; // rdx
  unsigned __int16 *v4; // rbx
  unsigned int v5; // ebx
  unsigned int v6; // eax
  const struct std::nothrow_t *v7; // rdx
  int DelegationValue; // edi
  int v9; // eax
  tpm12class::TPM_SESSION *v10; // rdi
  const struct std::nothrow_t *v11; // rdx
  int v12; // eax
  unsigned int v13; // esi
  const struct std::nothrow_t *v14; // rdx
  const struct std::nothrow_t *v15; // rdx
  void *v16; // rax
  struct tpm12class::TPM_AUTH_PROVIDER *v17; // rdx
  __int64 v18; // rbx
  unsigned int v19; // eax
  void (__fastcall ***v20)(_QWORD, __int64); // rcx
  tpm12class::TPM_SESSION *v21; // rbx
  unsigned int ValueW; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-E0h]
  int pdwTypeb; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypec; // [rsp+20h] [rbp-E0h]
  tpm12class::TPM_SESSION *v28; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v29; // [rsp+48h] [rbp-B8h] BYREF
  int v30; // [rsp+4Ch] [rbp-B4h]
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  PVOID pvData; // [rsp+58h] [rbp-A8h] BYREF
  int *v33[3]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 v34[20]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v33, L"GetEndorsementSession", 1);
  v29 = 0;
  memset_0(SubKey, 0, 0x208u);
  v30 = 520;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"TpmRegDriverPersistedDataAdmin",
                             0,
                             L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Admin",
                             0);
  if ( PersistedStateLocation < 0 )
  {
    v3 = 315;
LABEL_25:
    v5 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v3,
           (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers12.cpp",
           (const char *)(unsigned int)PersistedStateLocation,
           (int)SubKey);
    goto LABEL_49;
  }
  pcbData = 0;
  if ( RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"OwnerAuthFull", 2u, 0, 0, &pcbData) )
  {
    v30 = 520;
    memset_0(SubKey, 0, 0x208u);
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"TpmRegDriverPersistedDataEndorsement",
                               0,
                               L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement",
                               0);
    if ( PersistedStateLocation < 0 )
    {
      v3 = 363;
      goto LABEL_25;
    }
    v29 = 0;
    if ( RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"OwnerAuthEndorsement", 8u, 0, 0, &v29) )
    {
      v30 = 520;
      memset_0(SubKey, 0, 0x208u);
      PersistedStateLocation = RtlGetPersistedStateLocation(
                                 L"TpmRegDriverPersistedDataUser",
                                 0,
                                 L"System\\CurrentControlSet\\Services\\TPM\\WMI\\User",
                                 0);
      if ( PersistedStateLocation < 0 )
      {
        v3 = 402;
        goto LABEL_25;
      }
      v29 = 0;
      if ( RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"OwnerAuthUser", 8u, 0, 0, &v29) )
      {
        v5 = -2144795647;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1AE,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers12.cpp",
          (const char *)0x80290401LL,
          pdwTypeb);
        goto LABEL_49;
      }
      wil::make_unique_nothrow<tpm12class::TPM_SESSION,>(&v28);
      v21 = v28;
      if ( !v28 )
        goto LABEL_31;
      *((_DWORD *)v28 + 51) = 1346458436;
      *((_WORD *)v21 + 108) = 7;
      *((_DWORD *)v21 + 55) = 0;
      DelegationValue = tpm12class::TPM_SESSION::AllocateDelegationValue(v21, v29);
      if ( DelegationValue < 0 )
        goto LABEL_33;
      ValueW = RegGetValueW(
                 HKEY_LOCAL_MACHINE,
                 SubKey,
                 L"OwnerAuthUser",
                 8u,
                 0,
                 *((PVOID *)v21 + 29),
                 (LPDWORD)v21 + 56);
      if ( !ValueW )
      {
        v28 = 0;
        wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(a1, v21);
        wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v28, 0);
LABEL_22:
        v5 = 0;
        goto LABEL_49;
      }
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1A8,
             (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers12.cpp",
             (const char *)ValueW,
             pdwTypec);
    }
    else
    {
      v16 = operator new(0xF8u, (const struct std::nothrow_t *)&std::nothrow);
      pvData = v16;
      if ( v16 )
        v18 = tpm12class::TPM_SESSION::TPM_SESSION((tpm12class::TPM_SESSION *)v16, v17);
      else
        v18 = 0;
      v28 = (tpm12class::TPM_SESSION *)v18;
      if ( !v18 )
      {
LABEL_31:
        wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v28, 0);
        goto LABEL_5;
      }
      *(_DWORD *)(v18 + 204) = 1346458436;
      *(_WORD *)(v18 + 216) = 7;
      *(_DWORD *)(v18 + 220) = 0;
      DelegationValue = tpm12class::TPM_SESSION::AllocateDelegationValue((tpm12class::TPM_SESSION *)v18, v29);
      if ( DelegationValue < 0 )
      {
LABEL_33:
        wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v28, 0);
LABEL_10:
        v5 = DelegationValue;
        goto LABEL_49;
      }
      v19 = RegGetValueW(
              HKEY_LOCAL_MACHINE,
              SubKey,
              L"OwnerAuthEndorsement",
              8u,
              0,
              *(PVOID *)(v18 + 232),
              (LPDWORD)(v18 + 224));
      if ( !v19 )
      {
        v20 = (void (__fastcall ***)(_QWORD, __int64))*a1;
        *a1 = v18;
        if ( v20 )
          (**v20)(v20, 1);
        goto LABEL_22;
      }
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x181,
             (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers12.cpp",
             (const char *)v19,
             pdwTypea);
    }
    wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v28, 0);
    goto LABEL_49;
  }
  wil::make_unique_nothrow<unsigned char [0]>(&pvData, pcbData);
  v4 = (unsigned __int16 *)pvData;
  if ( !pvData )
  {
LABEL_5:
    v5 = -2147024888;
    goto LABEL_49;
  }
  v6 = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"OwnerAuthFull", 2u, 0, pvData, &pcbData);
  if ( v6 )
  {
    DelegationValue = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x14E,
                        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers12.cpp",
                        (const char *)v6,
                        pdwType);
    goto LABEL_8;
  }
  memset(v34, 0, sizeof(v34));
  v9 = base64decodeW(v4, v34, 0x14u, &v29);
  DelegationValue = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x155,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers12.cpp",
      (const char *)(unsigned int)v9,
      pdwType);
LABEL_8:
    if ( v4 )
      operator delete(v4, v7);
    goto LABEL_10;
  }
  wil::make_unique_nothrow<tpm12class::TPM_SESSION,>(&v28);
  v10 = v28;
  if ( !v28 )
  {
    wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v28, 0);
    if ( v4 )
      operator delete(v4, v11);
    goto LABEL_5;
  }
  v12 = tpm12class::TPM_SESSION::SetAuthProvider(v28, (const unsigned __int8 (*)[20])v34);
  v13 = v12;
  if ( v12 >= 0 )
  {
    *((_DWORD *)v10 + 51) = 1346458447;
    *((_WORD *)v10 + 108) = 2;
    *((_DWORD *)v10 + 55) = 0;
    v28 = 0;
    wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(a1, v10);
    wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v28, 0);
    if ( v4 )
      operator delete(v4, v15);
    goto LABEL_22;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x157,
    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers12.cpp",
    (const char *)(unsigned int)v12,
    pdwType);
  wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v28, 0);
  if ( v4 )
    operator delete(v4, v14);
  v5 = v13;
LABEL_49:
  KspFunctionLogger::~KspFunctionLogger(v33);
  return v5;
}

```

## disassembly

```asm
0x18004f1dc  mov     [rsp-8+arg_8], rbx
0x18004f1e1  mov     [rsp-8+arg_10], rsi
0x18004f1e6  push    rbp
0x18004f1e7  push    rdi
0x18004f1e8  push    r12
0x18004f1ea  push    r14
0x18004f1ec  push    r15
0x18004f1ee  lea     rbp, [rsp-1B0h]
0x18004f1f6  sub     rsp, 2B0h
0x18004f1fd  mov     rax, cs:__security_cookie
0x18004f204  xor     rax, rsp
0x18004f207  mov     [rbp+1D0h+var_30], rax
0x18004f20e  mov     r14, rcx
0x18004f211  xor     r15d, r15d
0x18004f214  mov     r8b, 1; bool
0x18004f217  lea     rdx, aGetendorsement; "GetEndorsementSession"
0x18004f21e  lea     rcx, [rsp+2D0h+var_270]; this
0x18004f223  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18004f228  nop
0x18004f229  mov     [rsp+2D0h+var_288], r15d
0x18004f22e  mov     ebx, 208h
0x18004f233  mov     r8d, ebx; Size
0x18004f236  xor     edx, edx; Val
0x18004f238  lea     rcx, [rbp+1D0h+SubKey]; void *
0x18004f23c  call    memset_0
0x18004f241  mov     [rsp+2D0h+var_284], ebx
0x18004f245  lea     rax, [rsp+2D0h+var_284]
0x18004f24a  mov     [rsp+2D0h+pcbData], rax
0x18004f24f  mov     dword ptr [rsp+2D0h+pvData], ebx
0x18004f253  lea     rax, [rbp+1D0h+SubKey]
0x18004f257  mov     [rsp+2D0h+pdwType], rax
0x18004f25c  xor     r9d, r9d
0x18004f25f  lea     r8, aSystemCurrentc_19; "System\\CurrentControlSet\\Services\\TP"...
0x18004f266  xor     edx, edx
0x18004f268  lea     rcx, aTpmregdriverpe_0; "TpmRegDriverPersistedDataAdmin"
0x18004f26f  call    cs:__imp_RtlGetPersistedStateLocation
0x18004f276  nop     dword ptr [rax+rax+00h]
0x18004f27b  test    eax, eax
0x18004f27d  jns     short loc_18004F289
0x18004f27f  mov     edx, 13Bh
0x18004f284  jmp     loc_18004F4C8
0x18004f289  mov     [rsp+2D0h+var_280], r15d
0x18004f28e  lea     rax, [rsp+2D0h+var_280]
0x18004f293  mov     [rsp+2D0h+pcbData], rax; pcbData
0x18004f298  mov     [rsp+2D0h+pvData], r15; pvData
0x18004f29d  mov     [rsp+2D0h+pdwType], r15; pdwType
0x18004f2a2  mov     r12d, 2
0x18004f2a8  mov     r9d, r12d; dwFlags
0x18004f2ab  lea     r8, aOwnerauthfull_0; "OwnerAuthFull"
0x18004f2b2  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x18004f2b6  mov     rsi, 0FFFFFFFF80000002h
0x18004f2bd  mov     rcx, rsi; hkey
0x18004f2c0  call    cs:__imp_RegGetValueW
0x18004f2c7  nop     dword ptr [rax+rax+00h]
0x18004f2cc  test    eax, eax
0x18004f2ce  jnz     loc_18004F477
0x18004f2d4  mov     edx, [rsp+2D0h+var_280]
0x18004f2d8  lea     rcx, [rsp+2D0h+var_278]
0x18004f2dd  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18004f2e2  nop
0x18004f2e3  mov     rbx, [rsp+2D0h+var_278]
0x18004f2e8  test    rbx, rbx
0x18004f2eb  jnz     short loc_18004F2F7
0x18004f2ed  mov     ebx, 80070008h
0x18004f2f2  jmp     loc_18004F7BB
0x18004f2f7  lea     rax, [rsp+2D0h+var_280]
0x18004f2fc  mov     [rsp+2D0h+pcbData], rax; pcbData
0x18004f301  mov     [rsp+2D0h+pvData], rbx; pvData
0x18004f306  mov     [rsp+2D0h+pdwType], r15; int
0x18004f30b  mov     r9d, r12d; dwFlags
0x18004f30e  lea     r8, aOwnerauthfull_0; "OwnerAuthFull"
0x18004f315  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x18004f319  mov     rcx, rsi; hkey
0x18004f31c  call    cs:__imp_RegGetValueW
0x18004f323  nop     dword ptr [rax+rax+00h]
0x18004f328  test    eax, eax
0x18004f32a  jz      short loc_18004F35D
0x18004f32c  mov     rcx, [rbp+1D8h]; this
0x18004f333  mov     r9d, eax; char *
0x18004f336  lea     r8, aOnecoreBaseNgs_24; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18004f33d  mov     edx, 14Eh; void *
0x18004f342  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004f347  mov     edi, eax
0x18004f349  test    rbx, rbx
0x18004f34c  jz      short loc_18004F356
0x18004f34e  mov     rcx, rbx; void *
0x18004f351  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004f356  mov     ebx, edi
0x18004f358  jmp     loc_18004F7BB
0x18004f35d  xorps   xmm0, xmm0
0x18004f360  xor     eax, eax
0x18004f362  movups  xmmword ptr [rsp+2D0h+var_258], xmm0
0x18004f367  mov     dword ptr [rbp+1D0h+var_258+10h], eax
0x18004f36a  lea     r9, [rsp+2D0h+var_288]; unsigned int *
0x18004f36f  lea     r8d, [rax+14h]; unsigned int
0x18004f373  lea     rdx, [rsp+2D0h+var_258]; void *
0x18004f378  mov     rcx, rbx; unsigned __int16 *
0x18004f37b  call    ?base64decodeW@@YAJPEBGPEAXKPEAK@Z; base64decodeW(ushort const *,void *,ulong,ulong *)
0x18004f380  mov     edi, eax
0x18004f382  test    eax, eax
0x18004f384  jns     short loc_18004F3A3
0x18004f386  mov     rcx, [rbp+1D8h]; this
0x18004f38d  mov     r9d, eax; char *
0x18004f390  lea     r8, aOnecoreBaseNgs_24; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18004f397  mov     edx, 155h; void *
0x18004f39c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f3a1  jmp     short loc_18004F349
0x18004f3a3  lea     rcx, [rsp+2D0h+var_290]
0x18004f3a8  call    ??$make_unique_nothrow@VTPM_SESSION@tpm12class@@$$V@wil@@YA?AV?$unique_ptr@VTPM_SESSION@tpm12class@@U?$default_delete@VTPM_SESSION@tpm12class@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<tpm12class::TPM_SESSION,>(void)
0x18004f3ad  nop
0x18004f3ae  mov     rdi, [rsp+2D0h+var_290]
0x18004f3b3  test    rdi, rdi
0x18004f3b6  jnz     short loc_18004F3DB
0x18004f3b8  xor     edx, edx
0x18004f3ba  lea     rcx, [rsp+2D0h+var_290]
0x18004f3bf  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x18004f3c4  nop
0x18004f3c5  test    rbx, rbx
0x18004f3c8  jz      loc_18004F2ED
0x18004f3ce  mov     rcx, rbx; void *
0x18004f3d1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004f3d6  jmp     loc_18004F2ED
0x18004f3db  lea     rdx, [rsp+2D0h+var_258]; unsigned __int8 (*)[20]
0x18004f3e0  mov     rcx, rdi; this
0x18004f3e3  call    ?SetAuthProvider@TPM_SESSION@tpm12class@@QEAAJAEAY0BE@$$CBE@Z; tpm12class::TPM_SESSION::SetAuthProvider(uchar const (&)[20])
0x18004f3e8  mov     esi, eax
0x18004f3ea  test    eax, eax
0x18004f3ec  jns     short loc_18004F42B
0x18004f3ee  mov     rcx, [rbp+1D8h]; this
0x18004f3f5  mov     r9d, eax; char *
0x18004f3f8  lea     r8, aOnecoreBaseNgs_24; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18004f3ff  mov     edx, 157h; void *
0x18004f404  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f409  nop
0x18004f40a  xor     edx, edx
0x18004f40c  lea     rcx, [rsp+2D0h+var_290]
0x18004f411  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x18004f416  nop
0x18004f417  test    rbx, rbx
0x18004f41a  jz      short loc_18004F424
0x18004f41c  mov     rcx, rbx; void *
0x18004f41f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004f424  mov     ebx, esi
0x18004f426  jmp     loc_18004F7BB
0x18004f42b  mov     dword ptr [rdi+0CCh], 5041534Fh
0x18004f435  mov     [rdi+0D8h], r12w
0x18004f43d  mov     [rdi+0DCh], r15d
0x18004f444  mov     [rsp+2D0h+var_290], r15
0x18004f449  mov     rdx, rdi
0x18004f44c  mov     rcx, r14
0x18004f44f  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x18004f454  nop
0x18004f455  xor     edx, edx
0x18004f457  lea     rcx, [rsp+2D0h+var_290]
0x18004f45c  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x18004f461  nop
0x18004f462  test    rbx, rbx
0x18004f465  jz      short loc_18004F46F
0x18004f467  mov     rcx, rbx; void *
0x18004f46a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004f46f  mov     ebx, r15d
0x18004f472  jmp     loc_18004F7BB
0x18004f477  mov     [rsp+2D0h+var_284], ebx
0x18004f47b  mov     r8, rbx; Size
0x18004f47e  xor     edx, edx; Val
0x18004f480  lea     rcx, [rbp+1D0h+SubKey]; void *
0x18004f484  call    memset_0
0x18004f489  lea     rax, [rsp+2D0h+var_284]
0x18004f48e  mov     [rsp+2D0h+pcbData], rax
0x18004f493  mov     dword ptr [rsp+2D0h+pvData], ebx
0x18004f497  lea     rax, [rbp+1D0h+SubKey]
0x18004f49b  mov     [rsp+2D0h+pdwType], rax; int
0x18004f4a0  xor     r9d, r9d
0x18004f4a3  lea     r8, aSystemCurrentc_20; "System\\CurrentControlSet\\Services\\TP"...
0x18004f4aa  xor     edx, edx
0x18004f4ac  lea     rcx, aTpmregdriverpe_2; "TpmRegDriverPersistedDataEndorsement"
0x18004f4b3  call    cs:__imp_RtlGetPersistedStateLocation
0x18004f4ba  nop     dword ptr [rax+rax+00h]
0x18004f4bf  test    eax, eax
0x18004f4c1  jns     short loc_18004F4E5
0x18004f4c3  mov     edx, 16Bh; void *
0x18004f4c8  mov     rcx, [rbp+1D8h]; this
0x18004f4cf  mov     r9d, eax; char *
0x18004f4d2  lea     r8, aOnecoreBaseNgs_24; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18004f4d9  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004f4de  mov     ebx, eax
0x18004f4e0  jmp     loc_18004F7BB
0x18004f4e5  mov     [rsp+2D0h+var_288], r15d
0x18004f4ea  lea     rax, [rsp+2D0h+var_288]
0x18004f4ef  mov     [rsp+2D0h+pcbData], rax; pcbData
0x18004f4f4  mov     [rsp+2D0h+pvData], r15; pvData
0x18004f4f9  mov     [rsp+2D0h+pdwType], r15; pdwType
0x18004f4fe  mov     r12d, 8
0x18004f504  mov     r9d, r12d; dwFlags
0x18004f507  lea     r8, aOwnerauthendor_0; "OwnerAuthEndorsement"
0x18004f50e  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x18004f512  mov     rcx, rsi; hkey
0x18004f515  call    cs:__imp_RegGetValueW
0x18004f51c  nop     dword ptr [rax+rax+00h]
0x18004f521  test    eax, eax
0x18004f523  jnz     loc_18004F639
0x18004f529  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004f530  mov     ecx, 0F8h; unsigned __int64
0x18004f535  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004f53a  mov     [rsp+2D0h+var_278], rax
0x18004f53f  test    rax, rax
0x18004f542  jz      short loc_18004F551
0x18004f544  mov     rcx, rax; this
0x18004f547  call    ??0TPM_SESSION@tpm12class@@QEAA@PEAVTPM_AUTH_PROVIDER@1@@Z; tpm12class::TPM_SESSION::TPM_SESSION(tpm12class::TPM_AUTH_PROVIDER *)
0x18004f54c  mov     rbx, rax
0x18004f54f  jmp     short loc_18004F554
0x18004f551  mov     rbx, r15
0x18004f554  mov     [rsp+2D0h+var_290], rbx
0x18004f559  test    rbx, rbx
0x18004f55c  jnz     short loc_18004F56F
0x18004f55e  xor     edx, edx
0x18004f560  lea     rcx, [rsp+2D0h+var_290]
0x18004f565  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x18004f56a  jmp     loc_18004F2ED
0x18004f56f  mov     dword ptr [rbx+0CCh], 50415344h
0x18004f579  mov     word ptr [rbx+0D8h], 7
0x18004f582  mov     [rbx+0DCh], r15d
0x18004f589  mov     edx, [rsp+2D0h+var_288]; unsigned int
0x18004f58d  mov     rcx, rbx; this
0x18004f590  call    ?AllocateDelegationValue@TPM_SESSION@tpm12class@@QEAAJI@Z; tpm12class::TPM_SESSION::AllocateDelegationValue(uint)
0x18004f595  mov     edi, eax
0x18004f597  test    eax, eax
0x18004f599  jns     short loc_18004F5AC
0x18004f59b  xor     edx, edx
0x18004f59d  lea     rcx, [rsp+2D0h+var_290]
0x18004f5a2  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x18004f5a7  jmp     loc_18004F356
0x18004f5ac  lea     rax, [rbx+0E0h]
0x18004f5b3  mov     [rsp+2D0h+pcbData], rax; pcbData
0x18004f5b8  mov     rax, [rbx+0E8h]
0x18004f5bf  mov     [rsp+2D0h+pvData], rax; pvData
0x18004f5c4  mov     [rsp+2D0h+pdwType], r15; unsigned int
0x18004f5c9  mov     r9d, r12d; dwFlags
0x18004f5cc  lea     r8, aOwnerauthendor_0; "OwnerAuthEndorsement"
0x18004f5d3  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x18004f5d7  mov     rcx, rsi; hkey
0x18004f5da  call    cs:__imp_RegGetValueW
0x18004f5e1  nop     dword ptr [rax+rax+00h]
0x18004f5e6  test    eax, eax
0x18004f5e8  jz      short loc_18004F618
0x18004f5ea  mov     rcx, [rbp+1D8h]; this
0x18004f5f1  mov     r9d, eax; char *
0x18004f5f4  lea     r8, aOnecoreBaseNgs_24; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18004f5fb  mov     edx, 181h; void *
0x18004f600  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004f605  mov     ebx, eax
0x18004f607  xor     edx, edx
0x18004f609  lea     rcx, [rsp+2D0h+var_290]
0x18004f60e  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x18004f613  jmp     loc_18004F7BB
0x18004f618  mov     rcx, [r14]
0x18004f61b  mov     [r14], rbx
0x18004f61e  test    rcx, rcx
0x18004f621  jz      short loc_18004F634
0x18004f623  mov     rax, [rcx]
0x18004f626  mov     edx, 1
0x18004f62b  mov     rax, [rax]
0x18004f62e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f633  nop
0x18004f634  jmp     loc_18004F46F
0x18004f639  mov     [rsp+2D0h+var_284], ebx
0x18004f63d  mov     r8, rbx; Size
0x18004f640  xor     edx, edx; Val
0x18004f642  lea     rcx, [rbp+1D0h+SubKey]; void *
0x18004f646  call    memset_0
0x18004f64b  lea     rax, [rsp+2D0h+var_284]
0x18004f650  mov     [rsp+2D0h+pcbData], rax
0x18004f655  mov     dword ptr [rsp+2D0h+pvData], ebx
0x18004f659  lea     rax, [rbp+1D0h+SubKey]
0x18004f65d  mov     [rsp+2D0h+pdwType], rax
0x18004f662  xor     r9d, r9d
0x18004f665  lea     r8, aSystemCurrentc_21; "System\\CurrentControlSet\\Services\\TP"...
0x18004f66c  xor     edx, edx
0x18004f66e  lea     rcx, aTpmregdriverpe; "TpmRegDriverPersistedDataUser"
0x18004f675  call    cs:__imp_RtlGetPersistedStateLocation
0x18004f67c  nop     dword ptr [rax+rax+00h]
0x18004f681  test    eax, eax
0x18004f683  jns     short loc_18004F68F
0x18004f685  mov     edx, 192h
0x18004f68a  jmp     loc_18004F4C8
0x18004f68f  mov     [rsp+2D0h+var_288], r15d
0x18004f694  lea     rax, [rsp+2D0h+var_288]
0x18004f699  mov     [rsp+2D0h+pcbData], rax; pcbData
0x18004f69e  mov     [rsp+2D0h+pvData], r15; pvData
0x18004f6a3  mov     [rsp+2D0h+pdwType], r15; int
0x18004f6a8  mov     r9d, r12d; dwFlags
0x18004f6ab  lea     r8, aOwnerauthuser; "OwnerAuthUser"
0x18004f6b2  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x18004f6b6  mov     rcx, rsi; hkey
0x18004f6b9  call    cs:__imp_RegGetValueW
0x18004f6c0  nop     dword ptr [rax+rax+00h]
0x18004f6c5  test    eax, eax
0x18004f6c7  jnz     loc_18004F79A
0x18004f6cd  lea     rcx, [rsp+2D0h+var_290]
0x18004f6d2  call    ??$make_unique_nothrow@VTPM_SESSION@tpm12class@@$$V@wil@@YA?AV?$unique_ptr@VTPM_SESSION@tpm12class@@U?$default_delete@VTPM_SESSION@tpm12class@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<tpm12class::TPM_SESSION,>(void)
  ... truncated ...
```
