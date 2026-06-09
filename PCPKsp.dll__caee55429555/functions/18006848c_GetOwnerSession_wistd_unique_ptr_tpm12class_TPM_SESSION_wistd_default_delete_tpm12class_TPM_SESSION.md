# GetOwnerSession(wistd::unique_ptr<tpm12class::TPM_SESSION,wistd::default_delete<tpm12class::TPM_SESSION>> &)

- ea: `0x18006848c`
- end: `0x180068a40`
- name: `?GetOwnerSession@@YAJAEAV?$unique_ptr@VTPM_SESSION@tpm12class@@U?$default_delete@VTPM_SESSION@tpm12class@@@wistd@@@wistd@@@Z`
- size: `1460`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x180085714`

## callees

- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180029a20`
- `0x18004f7fc`
- `0x180061bac`
- `0x18006848c`
- `0x180068a48`
- `0x180068a8c`
- `0x18006b964`
- `0x1800764d0`
- `0x1800768a0`
- `0x18007704c`
- `0x18009a56c`
- `0x1800a3ce8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006857d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800685d9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180068759`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006881a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180068912`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006899f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006857d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800685d9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180068759`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006881a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180068912`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006899f`
- `ntdll!RtlGetPersistedStateLocation` at `0x180068531`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800688b6`
- `ntdll!RtlGetPersistedStateLocation` at `0x180068531`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800688b6`

## string_xrefs

- `0x180068521`: `System\CurrentControlSet\Services\TPM\WMI\Admin`
- `0x1800688a6`: `System\CurrentControlSet\Services\TPM\WMI\User`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetOwnerSession(__int64 a1)
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
  tpm12class::TPM_SESSION *v16; // rbx
  int v17; // eax
  unsigned int v18; // eax
  unsigned int ValueW; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-E0h]
  int pdwTypec; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTyped; // [rsp+20h] [rbp-E0h]
  tpm12class::TPM_SESSION *v26; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v27; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+4Ch] [rbp-B4h] BYREF
  int v29; // [rsp+50h] [rbp-B0h]
  PVOID pvData; // [rsp+58h] [rbp-A8h] BYREF
  int *v31[3]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 v32[20]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v31, L"GetOwnerSession", 1);
  pcbData = 0;
  memset(v32, 0, sizeof(v32));
  v27 = 0;
  memset_0(SubKey, 0, 0x208u);
  v29 = 520;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"TpmRegDriverPersistedDataAdmin",
                             0,
                             L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Admin",
                             0);
  if ( PersistedStateLocation < 0 )
  {
    v3 = 191;
LABEL_35:
    v5 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v3,
           (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers12.cpp",
           (const char *)(unsigned int)PersistedStateLocation,
           (int)SubKey);
    goto LABEL_43;
  }
  if ( RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"OwnerAuthFull", 2u, 0, 0, &pcbData) )
  {
    v27 = 0;
    if ( RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"OwnerAuthAdmin", 8u, 0, 0, &v27) )
    {
      v29 = 520;
      memset_0(SubKey, 0, 0x208u);
      PersistedStateLocation = RtlGetPersistedStateLocation(
                                 L"TpmRegDriverPersistedDataUser",
                                 0,
                                 L"System\\CurrentControlSet\\Services\\TPM\\WMI\\User",
                                 0);
      if ( PersistedStateLocation < 0 )
      {
        v3 = 266;
        goto LABEL_35;
      }
      v27 = 0;
      if ( RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"OwnerAuthUser", 8u, 0, 0, &v27) )
      {
        v5 = -2144795647;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x127,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers12.cpp",
          (const char *)0x80290401LL,
          pdwTypec);
        goto LABEL_43;
      }
      wil::make_unique_nothrow<tpm12class::TPM_SESSION,>(&v26);
      v16 = v26;
      if ( !v26 )
        goto LABEL_25;
      *((_DWORD *)v26 + 51) = 1346458436;
      *((_WORD *)v16 + 108) = 7;
      *((_DWORD *)v16 + 55) = 0;
      DelegationValue = tpm12class::TPM_SESSION::AllocateDelegationValue(v16, v27);
      if ( DelegationValue < 0 )
      {
LABEL_28:
        wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v26, 0);
LABEL_10:
        v5 = DelegationValue;
        goto LABEL_43;
      }
      ValueW = RegGetValueW(
                 HKEY_LOCAL_MACHINE,
                 SubKey,
                 L"OwnerAuthUser",
                 8u,
                 0,
                 *((PVOID *)v16 + 29),
                 (LPDWORD)v16 + 56);
      if ( ValueW )
      {
        v5 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x120,
               (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers12.cpp",
               (const char *)ValueW,
               pdwTyped);
        goto LABEL_31;
      }
    }
    else
    {
      wil::make_unique_nothrow<tpm12class::TPM_SESSION,>(&v26);
      v16 = v26;
      if ( !v26 )
      {
LABEL_25:
        wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v26, 0);
        goto LABEL_5;
      }
      *((_DWORD *)v26 + 51) = 1346458436;
      *((_WORD *)v16 + 108) = 7;
      *((_DWORD *)v16 + 55) = 0;
      v17 = tpm12class::TPM_SESSION::AllocateDelegationValue(v16, v27);
      DelegationValue = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF2,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers12.cpp",
          (const char *)(unsigned int)v17,
          pdwTypea);
        goto LABEL_28;
      }
      v18 = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"OwnerAuthAdmin", 8u, 0, *((PVOID *)v16 + 29), (LPDWORD)v16 + 56);
      if ( v18 )
      {
        v5 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xF9,
               (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers12.cpp",
               (const char *)v18,
               pdwTypeb);
LABEL_31:
        wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v26, 0);
        goto LABEL_43;
      }
    }
    v26 = 0;
    wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(a1, v16);
    wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v26, 0);
LABEL_22:
    v5 = 0;
    goto LABEL_43;
  }
  wil::make_unique_nothrow<unsigned char [0]>(&pvData, pcbData);
  v4 = (unsigned __int16 *)pvData;
  if ( !pvData )
  {
LABEL_5:
    v5 = -2147024888;
    goto LABEL_43;
  }
  v6 = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"OwnerAuthFull", 2u, 0, pvData, &pcbData);
  if ( v6 )
  {
    DelegationValue = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0xD3,
                        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers12.cpp",
                        (const char *)v6,
                        pdwType);
    goto LABEL_8;
  }
  v9 = base64decodeW(v4, v32, 0x14u, &v27);
  DelegationValue = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers12.cpp",
      (const char *)(unsigned int)v9,
      pdwType);
LABEL_8:
    if ( v4 )
      operator delete(v4, v7);
    goto LABEL_10;
  }
  wil::make_unique_nothrow<tpm12class::TPM_SESSION,>(&v26);
  v10 = v26;
  if ( !v26 )
  {
    wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v26, 0);
    if ( v4 )
      operator delete(v4, v11);
    goto LABEL_5;
  }
  v12 = tpm12class::TPM_SESSION::SetAuthProvider(v26, (const unsigned __int8 (*)[20])v32);
  v13 = v12;
  if ( v12 >= 0 )
  {
    *((_DWORD *)v10 + 51) = 1346458447;
    *((_WORD *)v10 + 108) = 2;
    *((_DWORD *)v10 + 55) = 0;
    v26 = 0;
    wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(a1, v10);
    wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v26, 0);
    if ( v4 )
      operator delete(v4, v15);
    goto LABEL_22;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xDB,
    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers12.cpp",
    (const char *)(unsigned int)v12,
    pdwType);
  wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v26, 0);
  if ( v4 )
    operator delete(v4, v14);
  v5 = v13;
LABEL_43:
  KspFunctionLogger::~KspFunctionLogger(v31);
  return v5;
}

```

## disassembly

```asm
0x18006848c  mov     [rsp-8+arg_8], rbx
0x180068491  mov     [rsp-8+arg_10], rsi
0x180068496  push    rbp
0x180068497  push    rdi
0x180068498  push    r12
0x18006849a  push    r14
0x18006849c  push    r15
0x18006849e  lea     rbp, [rsp-1B0h]
0x1800684a6  sub     rsp, 2B0h
0x1800684ad  mov     rax, cs:__security_cookie
0x1800684b4  xor     rax, rsp
0x1800684b7  mov     [rbp+1D0h+var_30], rax
0x1800684be  mov     r14, rcx
0x1800684c1  mov     r8b, 1; bool
0x1800684c4  lea     rdx, aGetownersessio; "GetOwnerSession"
0x1800684cb  lea     rcx, [rsp+2D0h+var_270]; this
0x1800684d0  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x1800684d5  nop
0x1800684d6  xor     r15d, r15d
0x1800684d9  mov     [rsp+2D0h+var_284], r15d
0x1800684de  xorps   xmm0, xmm0
0x1800684e1  xor     eax, eax
0x1800684e3  movups  xmmword ptr [rsp+2D0h+var_258], xmm0
0x1800684e8  mov     dword ptr [rbp+1D0h+var_258+10h], eax
0x1800684eb  mov     [rsp+2D0h+var_288], r15d
0x1800684f0  mov     ebx, 208h
0x1800684f5  mov     r8d, ebx; Size
0x1800684f8  xor     edx, edx; Val
0x1800684fa  lea     rcx, [rbp+1D0h+SubKey]; void *
0x1800684fe  call    memset_0
0x180068503  mov     [rsp+2D0h+var_280], ebx
0x180068507  lea     rax, [rsp+2D0h+var_280]
0x18006850c  mov     [rsp+2D0h+pcbData], rax
0x180068511  mov     dword ptr [rsp+2D0h+pvData], ebx
0x180068515  lea     rax, [rbp+1D0h+SubKey]
0x180068519  mov     [rsp+2D0h+pdwType], rax
0x18006851e  xor     r9d, r9d
0x180068521  lea     r8, aSystemCurrentc_19; "System\\CurrentControlSet\\Services\\TP"...
0x180068528  xor     edx, edx
0x18006852a  lea     rcx, aTpmregdriverpe_0; "TpmRegDriverPersistedDataAdmin"
0x180068531  call    cs:__imp_RtlGetPersistedStateLocation
0x180068538  nop     dword ptr [rax+rax+00h]
0x18006853d  test    eax, eax
0x18006853f  jns     short loc_18006854B
0x180068541  mov     edx, 0BFh
0x180068546  jmp     loc_1800688CB
0x18006854b  lea     rax, [rsp+2D0h+var_284]
0x180068550  mov     [rsp+2D0h+pcbData], rax; pcbData
0x180068555  mov     [rsp+2D0h+pvData], r15; pvData
0x18006855a  mov     [rsp+2D0h+pdwType], r15; pdwType
0x18006855f  mov     r12d, 2
0x180068565  mov     r9d, r12d; dwFlags
0x180068568  lea     r8, aOwnerauthfull_0; "OwnerAuthFull"
0x18006856f  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x180068573  mov     rsi, 0FFFFFFFF80000002h
0x18006857a  mov     rcx, rsi; hkey
0x18006857d  call    cs:__imp_RegGetValueW
0x180068584  nop     dword ptr [rax+rax+00h]
0x180068589  test    eax, eax
0x18006858b  jnz     loc_180068729
0x180068591  mov     edx, [rsp+2D0h+var_284]
0x180068595  lea     rcx, [rsp+2D0h+var_278]
0x18006859a  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18006859f  nop
0x1800685a0  mov     rbx, [rsp+2D0h+var_278]
0x1800685a5  test    rbx, rbx
0x1800685a8  jnz     short loc_1800685B4
0x1800685aa  mov     ebx, 80070008h
0x1800685af  jmp     loc_180068A08
0x1800685b4  lea     rax, [rsp+2D0h+var_284]
0x1800685b9  mov     [rsp+2D0h+pcbData], rax; pcbData
0x1800685be  mov     [rsp+2D0h+pvData], rbx; pvData
0x1800685c3  mov     [rsp+2D0h+pdwType], r15; int
0x1800685c8  mov     r9d, r12d; dwFlags
0x1800685cb  lea     r8, aOwnerauthfull_0; "OwnerAuthFull"
0x1800685d2  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x1800685d6  mov     rcx, rsi; hkey
0x1800685d9  call    cs:__imp_RegGetValueW
0x1800685e0  nop     dword ptr [rax+rax+00h]
0x1800685e5  test    eax, eax
0x1800685e7  jz      short loc_18006861A
0x1800685e9  mov     rcx, [rbp+1D8h]; this
0x1800685f0  mov     r9d, eax; char *
0x1800685f3  lea     r8, aOnecoreBaseNgs_24; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800685fa  mov     edx, 0D3h; void *
0x1800685ff  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180068604  mov     edi, eax
0x180068606  test    rbx, rbx
0x180068609  jz      short loc_180068613
0x18006860b  mov     rcx, rbx; void *
0x18006860e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068613  mov     ebx, edi
0x180068615  jmp     loc_180068A08
0x18006861a  lea     r9, [rsp+2D0h+var_288]; unsigned int *
0x18006861f  mov     r8d, 14h; unsigned int
0x180068625  lea     rdx, [rsp+2D0h+var_258]; void *
0x18006862a  mov     rcx, rbx; unsigned __int16 *
0x18006862d  call    ?base64decodeW@@YAJPEBGPEAXKPEAK@Z; base64decodeW(ushort const *,void *,ulong,ulong *)
0x180068632  mov     edi, eax
0x180068634  test    eax, eax
0x180068636  jns     short loc_180068655
0x180068638  mov     rcx, [rbp+1D8h]; this
0x18006863f  mov     r9d, eax; char *
0x180068642  lea     r8, aOnecoreBaseNgs_24; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180068649  mov     edx, 0D9h; void *
0x18006864e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068653  jmp     short loc_180068606
0x180068655  lea     rcx, [rsp+2D0h+var_290]
0x18006865a  call    ??$make_unique_nothrow@VTPM_SESSION@tpm12class@@$$V@wil@@YA?AV?$unique_ptr@VTPM_SESSION@tpm12class@@U?$default_delete@VTPM_SESSION@tpm12class@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<tpm12class::TPM_SESSION,>(void)
0x18006865f  nop
0x180068660  mov     rdi, [rsp+2D0h+var_290]
0x180068665  test    rdi, rdi
0x180068668  jnz     short loc_18006868D
0x18006866a  xor     edx, edx
0x18006866c  lea     rcx, [rsp+2D0h+var_290]
0x180068671  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x180068676  nop
0x180068677  test    rbx, rbx
0x18006867a  jz      loc_1800685AA
0x180068680  mov     rcx, rbx; void *
0x180068683  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068688  jmp     loc_1800685AA
0x18006868d  lea     rdx, [rsp+2D0h+var_258]; unsigned __int8 (*)[20]
0x180068692  mov     rcx, rdi; this
0x180068695  call    ?SetAuthProvider@TPM_SESSION@tpm12class@@QEAAJAEAY0BE@$$CBE@Z; tpm12class::TPM_SESSION::SetAuthProvider(uchar const (&)[20])
0x18006869a  mov     esi, eax
0x18006869c  test    eax, eax
0x18006869e  jns     short loc_1800686DD
0x1800686a0  mov     rcx, [rbp+1D8h]; this
0x1800686a7  mov     r9d, eax; char *
0x1800686aa  lea     r8, aOnecoreBaseNgs_24; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800686b1  mov     edx, 0DBh; void *
0x1800686b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800686bb  nop
0x1800686bc  xor     edx, edx
0x1800686be  lea     rcx, [rsp+2D0h+var_290]
0x1800686c3  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x1800686c8  nop
0x1800686c9  test    rbx, rbx
0x1800686cc  jz      short loc_1800686D6
0x1800686ce  mov     rcx, rbx; void *
0x1800686d1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800686d6  mov     ebx, esi
0x1800686d8  jmp     loc_180068A08
0x1800686dd  mov     dword ptr [rdi+0CCh], 5041534Fh
0x1800686e7  mov     [rdi+0D8h], r12w
0x1800686ef  mov     [rdi+0DCh], r15d
0x1800686f6  mov     [rsp+2D0h+var_290], r15
0x1800686fb  mov     rdx, rdi
0x1800686fe  mov     rcx, r14
0x180068701  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x180068706  nop
0x180068707  xor     edx, edx
0x180068709  lea     rcx, [rsp+2D0h+var_290]
0x18006870e  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x180068713  nop
0x180068714  test    rbx, rbx
0x180068717  jz      short loc_180068721
0x180068719  mov     rcx, rbx; void *
0x18006871c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068721  mov     ebx, r15d
0x180068724  jmp     loc_180068A08
0x180068729  mov     [rsp+2D0h+var_288], r15d
0x18006872e  lea     rax, [rsp+2D0h+var_288]
0x180068733  mov     [rsp+2D0h+pcbData], rax; pcbData
0x180068738  mov     [rsp+2D0h+pvData], r15; pvData
0x18006873d  mov     [rsp+2D0h+pdwType], r15; int
0x180068742  mov     r12d, 8
0x180068748  mov     r9d, r12d; dwFlags
0x18006874b  lea     r8, aOwnerauthadmin; "OwnerAuthAdmin"
0x180068752  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x180068756  mov     rcx, rsi; hkey
0x180068759  call    cs:__imp_RegGetValueW
0x180068760  nop     dword ptr [rax+rax+00h]
0x180068765  test    eax, eax
0x180068767  jnz     loc_18006887A
0x18006876d  lea     rcx, [rsp+2D0h+var_290]
0x180068772  call    ??$make_unique_nothrow@VTPM_SESSION@tpm12class@@$$V@wil@@YA?AV?$unique_ptr@VTPM_SESSION@tpm12class@@U?$default_delete@VTPM_SESSION@tpm12class@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<tpm12class::TPM_SESSION,>(void)
0x180068777  nop
0x180068778  mov     rbx, [rsp+2D0h+var_290]
0x18006877d  test    rbx, rbx
0x180068780  jnz     short loc_180068793
0x180068782  xor     edx, edx
0x180068784  lea     rcx, [rsp+2D0h+var_290]
0x180068789  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x18006878e  jmp     loc_1800685AA
0x180068793  mov     dword ptr [rbx+0CCh], 50415344h
0x18006879d  mov     word ptr [rbx+0D8h], 7
0x1800687a6  mov     [rbx+0DCh], r15d
0x1800687ad  mov     edx, [rsp+2D0h+var_288]; unsigned int
0x1800687b1  mov     rcx, rbx; this
0x1800687b4  call    ?AllocateDelegationValue@TPM_SESSION@tpm12class@@QEAAJI@Z; tpm12class::TPM_SESSION::AllocateDelegationValue(uint)
0x1800687b9  mov     edi, eax
0x1800687bb  test    eax, eax
0x1800687bd  jns     short loc_1800687EC
0x1800687bf  mov     rcx, [rbp+1D8h]; this
0x1800687c6  mov     r9d, eax; char *
0x1800687c9  lea     r8, aOnecoreBaseNgs_24; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800687d0  mov     edx, 0F2h; void *
0x1800687d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800687da  nop
0x1800687db  xor     edx, edx
0x1800687dd  lea     rcx, [rsp+2D0h+var_290]
0x1800687e2  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x1800687e7  jmp     loc_180068613
0x1800687ec  lea     rax, [rbx+0E0h]
0x1800687f3  mov     [rsp+2D0h+pcbData], rax; pcbData
0x1800687f8  mov     rax, [rbx+0E8h]
0x1800687ff  mov     [rsp+2D0h+pvData], rax; pvData
0x180068804  mov     [rsp+2D0h+pdwType], r15; unsigned int
0x180068809  mov     r9d, r12d; dwFlags
0x18006880c  lea     r8, aOwnerauthadmin; "OwnerAuthAdmin"
0x180068813  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x180068817  mov     rcx, rsi; hkey
0x18006881a  call    cs:__imp_RegGetValueW
0x180068821  nop     dword ptr [rax+rax+00h]
0x180068826  test    eax, eax
0x180068828  jz      short loc_180068858
0x18006882a  mov     rcx, [rbp+1D8h]; this
0x180068831  mov     r9d, eax; char *
0x180068834  lea     r8, aOnecoreBaseNgs_24; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18006883b  mov     edx, 0F9h; void *
0x180068840  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180068845  mov     ebx, eax
0x180068847  xor     edx, edx
0x180068849  lea     rcx, [rsp+2D0h+var_290]
0x18006884e  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x180068853  jmp     loc_180068A08
0x180068858  mov     [rsp+2D0h+var_290], r15
0x18006885d  mov     rdx, rbx
0x180068860  mov     rcx, r14
0x180068863  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x180068868  nop
0x180068869  xor     edx, edx
0x18006886b  lea     rcx, [rsp+2D0h+var_290]
0x180068870  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x180068875  jmp     loc_180068721
0x18006887a  mov     [rsp+2D0h+var_280], ebx
0x18006887e  mov     r8, rbx; Size
0x180068881  xor     edx, edx; Val
0x180068883  lea     rcx, [rbp+1D0h+SubKey]; void *
0x180068887  call    memset_0
0x18006888c  lea     rax, [rsp+2D0h+var_280]
0x180068891  mov     [rsp+2D0h+pcbData], rax
0x180068896  mov     dword ptr [rsp+2D0h+pvData], ebx
0x18006889a  lea     rax, [rbp+1D0h+SubKey]
0x18006889e  mov     [rsp+2D0h+pdwType], rax; int
0x1800688a3  xor     r9d, r9d
0x1800688a6  lea     r8, aSystemCurrentc_21; "System\\CurrentControlSet\\Services\\TP"...
0x1800688ad  xor     edx, edx
0x1800688af  lea     rcx, aTpmregdriverpe; "TpmRegDriverPersistedDataUser"
0x1800688b6  call    cs:__imp_RtlGetPersistedStateLocation
0x1800688bd  nop     dword ptr [rax+rax+00h]
0x1800688c2  test    eax, eax
0x1800688c4  jns     short loc_1800688E8
0x1800688c6  mov     edx, 10Ah; void *
0x1800688cb  lea     r8, aOnecoreBaseNgs_24; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800688d2  mov     r9d, eax; char *
0x1800688d5  mov     rcx, [rbp+1D8h]; this
0x1800688dc  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800688e1  mov     ebx, eax
0x1800688e3  jmp     loc_180068A08
0x1800688e8  mov     [rsp+2D0h+var_288], r15d
0x1800688ed  lea     rax, [rsp+2D0h+var_288]
0x1800688f2  mov     [rsp+2D0h+pcbData], rax; pcbData
0x1800688f7  mov     [rsp+2D0h+pvData], r15; pvData
0x1800688fc  mov     [rsp+2D0h+pdwType], r15; int
0x180068901  mov     r9d, r12d; dwFlags
0x180068904  lea     r8, aOwnerauthuser; "OwnerAuthUser"
0x18006890b  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x18006890f  mov     rcx, rsi; hkey
0x180068912  call    cs:__imp_RegGetValueW
0x180068919  nop     dword ptr [rax+rax+00h]
0x18006891e  test    eax, eax
0x180068920  jnz     loc_1800689E7
0x180068926  lea     rcx, [rsp+2D0h+var_290]
0x18006892b  call    ??$make_unique_nothrow@VTPM_SESSION@tpm12class@@$$V@wil@@YA?AV?$unique_ptr@VTPM_SESSION@tpm12class@@U?$default_delete@VTPM_SESSION@tpm12class@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<tpm12class::TPM_SESSION,>(void)
0x180068930  nop
0x180068931  mov     rbx, [rsp+2D0h+var_290]
0x180068936  test    rbx, rbx
0x180068939  jnz     short loc_180068940
0x18006893b  jmp     loc_180068782
0x180068940  mov     dword ptr [rbx+0CCh], 50415344h
0x18006894a  mov     word ptr [rbx+0D8h], 7
0x180068953  mov     [rbx+0DCh], r15d
0x18006895a  mov     edx, [rsp+2D0h+var_288]; unsigned int
0x18006895e  mov     rcx, rbx; this
0x180068961  call    ?AllocateDelegationValue@TPM_SESSION@tpm12class@@QEAAJI@Z; tpm12class::TPM_SESSION::AllocateDelegationValue(uint)
0x180068966  mov     edi, eax
0x180068968  test    eax, eax
0x18006896a  jns     short loc_180068971
0x18006896c  jmp     loc_1800687DB
0x180068971  lea     rax, [rbx+0E0h]
0x180068978  mov     [rsp+2D0h+pcbData], rax; pcbData
0x18006897d  mov     rax, [rbx+0E8h]
0x180068984  mov     [rsp+2D0h+pvData], rax; pvData
0x180068989  mov     [rsp+2D0h+pdwType], r15; unsigned int
0x18006898e  mov     r9d, r12d; dwFlags
0x180068991  lea     r8, aOwnerauthuser; "OwnerAuthUser"
0x180068998  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
  ... truncated ...
```
