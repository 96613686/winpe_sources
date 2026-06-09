# GenericCallPackageHelper::AadWamNotification(AadContextFunctions *,PluginState &,DiagnosticContext &,CSecureString &,void *)

- ea: `0x180042960`
- end: `0x180042de7`
- name: `?AadWamNotification@GenericCallPackageHelper@@CAJPEAVAadContextFunctions@@AEAVPluginState@@AEAVDiagnosticContext@@AEAVCSecureString@@PEAX@Z`
- size: `1159`
- prototype: `__int64 __fastcall(struct AadContextFunctions *, struct PluginState *, struct DiagnosticContext *, const wchar_t **, HANDLE hToken)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800477bc`

## callees

- `0x180003c20`
- `0x180004a24`
- `0x1800069c0`
- `0x180006ac4`
- `0x1800090d0`
- `0x18000a300`
- `0x18000a5f4`
- `0x180024f54`
- `0x180032b14`
- `0x180040648`
- `0x180042960`
- `0x180071e14`
- `0x1800779bc`
- `0x1800a3520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a96`
- `ntdll!NtQueryInformationToken` at `0x180042b2f`
- `ntdll!NtQueryInformationToken` at `0x180042c7f`
- `ntdll!NtQueryInformationToken` at `0x180042b2f`
- `ntdll!NtQueryInformationToken` at `0x180042c7f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180042a88`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180042a88`

## string_xrefs

- `0x180042c4b`: `remove_wpj`
- `0x180042bab`: `userSid`
- `0x180042cfb`: `userSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GenericCallPackageHelper::AadWamNotification(
        struct AadContextFunctions *a1,
        struct PluginState *a2,
        struct DiagnosticContext *a3,
        const wchar_t **a4,
        HANDLE hToken)
{
  int v8; // eax
  const WCHAR *v9; // rax
  signed int LastError; // eax
  signed int v11; // ebx
  NTSTATUS updated; // eax
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rbx
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rbx
  unsigned int v17; // ebx
  PULONG ReturnLength; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+30h] [rbp-D0h]
  unsigned int v21; // [rsp+50h] [rbp-B0h] BYREF
  ULONG v22; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 *v23; // [rsp+58h] [rbp-A8h] BYREF
  BOOL v24; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+68h] [rbp-98h]
  struct DiagnosticContext *v26; // [rsp+70h] [rbp-90h]
  _BYTE v27[56]; // [rsp+78h] [rbp-88h] BYREF
  PSID TokenInformation[12]; // [rsp+B0h] [rbp-50h] BYREF

  v26 = a3;
  v21 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v23);
  v22 = 0;
  memset_0(TokenInformation, 0, 0x58u);
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    v27,
    "genericcallpackagehelper.cpp",
    "GenericCallPackageHelper::AadWamNotification",
    &v21);
  v8 = CheckPackageSidIsWam(a1, hToken);
  v21 = v8;
  if ( v8 >= 0 )
  {
    v9 = &base;
    if ( *a4 )
      v9 = *a4;
    WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "genericcallpackagehelper.cpp", 860, "payload", v9);
    v25 = 0;
    v24 = ImpersonateLoggedOnUser(hToken);
    if ( !v24 )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( v11 < 0 )
      {
        LODWORD(v20) = 866;
LABEL_10:
        LODWORD(ReturnLength) = v11;
        WPPTraceLogA(
          2,
          0,
          "%x 0x%08x %s:%u : %s:%ws",
          2,
          ReturnLength,
          "genericcallpackagehelper.cpp",
          v20,
          "HRESULT",
          &base);
        v21 = v11 & 0xAFFFFFFF | 0x40000000;
LABEL_33:
        ImpersonateLoggedOnUserHelper::~ImpersonateLoggedOnUserHelper((ImpersonateLoggedOnUserHelper *)&v24);
        goto LABEL_34;
      }
    }
    if ( !wcscmp_0(*a4, L"add_wpj") )
    {
      updated = NtQueryInformationToken(hToken, TokenUser, TokenInformation, 0x58u, &v22);
      v21 = updated;
      if ( updated >= 0 )
      {
        v11 = StringUtility::SidToString(TokenInformation[0]);
        if ( v11 < 0 )
        {
          LODWORD(v20) = 873;
          goto LABEL_10;
        }
        v13 = (unsigned __int16 *)&base;
        v14 = v23;
        if ( v23 )
          v13 = v23;
        LODWORD(v20) = 874;
        WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "genericcallpackagehelper.cpp", v20, "userSid", v13);
        updated = TokenBindingHelper::UpdateJoinInfo(a1, a2, v14);
        v21 = updated;
        if ( updated >= 0 )
        {
          updated = UpdateWorkPlaceP2PCertificates(a1, *(void **)a2, v26);
          v21 = updated;
          if ( updated >= 0 )
            goto LABEL_33;
          LODWORD(v20) = 878;
        }
        else
        {
          LODWORD(v20) = 875;
        }
      }
      else
      {
        LODWORD(v20) = 872;
      }
    }
    else if ( !wcscmp_0(*a4, L"remove_wpj") )
    {
      updated = NtQueryInformationToken(hToken, TokenUser, TokenInformation, 0x58u, &v22);
      v21 = updated;
      if ( updated >= 0 )
      {
        v11 = StringUtility::SidToString(TokenInformation[0]);
        if ( v11 < 0 )
        {
          LODWORD(v20) = 884;
          goto LABEL_10;
        }
        v15 = (unsigned __int16 *)&base;
        v16 = v23;
        if ( v23 )
          v15 = v23;
        LODWORD(v20) = 885;
        WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "genericcallpackagehelper.cpp", v20, "userSid", v15);
        updated = TokenBindingHelper::UpdateJoinInfo(a1, a2, v16);
        v21 = updated;
        if ( updated >= 0 )
          goto LABEL_33;
        LODWORD(v20) = 886;
      }
      else
      {
        LODWORD(v20) = 883;
      }
    }
    else
    {
      updated = -1073741811;
      v21 = -1073741811;
      LODWORD(v20) = 890;
    }
    LODWORD(ReturnLength) = updated;
    WPPTraceLogA(
      2,
      0,
      "%x 0x%08x %s:%u : %s:%ws",
      2,
      ReturnLength,
      "genericcallpackagehelper.cpp",
      v20,
      "NTSTATUS",
      &base);
    goto LABEL_33;
  }
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v8, "genericcallpackagehelper.cpp", 858, "NTSTATUS", &base);
LABEL_34:
  v17 = v21;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v27);
  CSecureString::~CSecureString((CSecureString *)&v23);
  return v17;
}

```

## disassembly

```asm
0x180042960  push    rbp
0x180042962  push    rbx
0x180042963  push    rsi
0x180042964  push    rdi
0x180042965  push    r12
0x180042967  push    r13
0x180042969  push    r14
0x18004296b  push    r15
0x18004296d  lea     rbp, [rsp-28h]
0x180042972  sub     rsp, 128h
0x180042979  mov     rax, cs:__security_cookie
0x180042980  xor     rax, rsp
0x180042983  mov     [rbp+60h+var_50], rax
0x180042987  mov     r12, r9
0x18004298a  mov     [rsp+160h+var_F0], r8
0x18004298f  mov     r13, rdx
0x180042992  mov     r15, rcx
0x180042995  mov     r14, [rbp+60h+hToken]
0x18004299c  xor     ebx, ebx
0x18004299e  mov     [rsp+160h+var_110], ebx
0x1800429a2  lea     rcx, [rsp+160h+var_108]; void *
0x1800429a7  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800429ac  nop
0x1800429ad  mov     [rsp+160h+var_10C], ebx
0x1800429b1  xor     edx, edx; Val
0x1800429b3  lea     r8d, [rbx+58h]; Size
0x1800429b7  lea     rcx, [rbp+60h+TokenInformation]; void *
0x1800429bb  call    memset_0
0x1800429c0  lea     r9, [rsp+160h+var_110]
0x1800429c5  lea     r8, aGenericcallpac_6; "GenericCallPackageHelper::AadWamNotific"...
0x1800429cc  lea     rdi, aOnecoreuapDsEx_30+21h; "genericcallpackagehelper.cpp"
0x1800429d3  mov     rdx, rdi
0x1800429d6  lea     rcx, [rsp+160h+var_E8]
0x1800429db  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x1800429e0  nop
0x1800429e1  mov     rdx, r14; void *
0x1800429e4  mov     rcx, r15; struct AadContextFunctions *
0x1800429e7  call    ?CheckPackageSidIsWam@@YAJPEAVAadContextFunctions@@PEAX@Z; CheckPackageSidIsWam(AadContextFunctions *,void *)
0x1800429ec  mov     [rsp+160h+var_110], eax
0x1800429f0  lea     rsi, base
0x1800429f7  test    eax, eax
0x1800429f9  jns     short loc_180042A36
0x1800429fb  mov     [rsp+160h+var_120], rsi
0x180042a00  lea     rcx, aNtstatus; "NTSTATUS"
0x180042a07  mov     [rsp+160h+var_128], rcx
0x180042a0c  mov     dword ptr [rsp+160h+var_130], 35Ah
0x180042a14  mov     [rsp+160h+var_138], rdi
0x180042a19  mov     dword ptr [rsp+160h+ReturnLength], eax
0x180042a1d  lea     ecx, [rbx+2]
0x180042a20  mov     r9d, ecx
0x180042a23  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180042a2a  xor     edx, edx
0x180042a2c  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180042a31  jmp     loc_180042DAC
0x180042a36  mov     rax, rsi
0x180042a39  cmp     [r12], rbx
0x180042a3d  cmovnz  rax, [r12]
0x180042a42  mov     [rsp+160h+var_120], rax
0x180042a47  lea     rax, aPayload; "payload"
0x180042a4e  mov     [rsp+160h+var_128], rax
0x180042a53  mov     dword ptr [rsp+160h+var_130], 35Ch
0x180042a5b  mov     [rsp+160h+var_138], rdi
0x180042a60  mov     [rsp+160h+ReturnLength], rbx
0x180042a65  mov     eax, 4
0x180042a6a  mov     r9d, eax
0x180042a6d  lea     rdi, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180042a74  mov     r8, rdi
0x180042a77  xor     edx, edx
0x180042a79  mov     ecx, eax
0x180042a7b  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180042a80  mov     [rsp+160h+var_F8], rbx
0x180042a85  mov     rcx, r14; hToken
0x180042a88  call    cs:__imp_ImpersonateLoggedOnUser
0x180042a8e  mov     [rsp+160h+var_100], eax
0x180042a92  test    eax, eax
0x180042a94  jnz     short loc_180042AFB
0x180042a96  call    cs:__imp_GetLastError
0x180042a9c  mov     ebx, eax
0x180042a9e  test    eax, eax
0x180042aa0  jle     short loc_180042AAB
0x180042aa2  movzx   ebx, ax
0x180042aa5  or      ebx, 80070000h
0x180042aab  test    ebx, ebx
0x180042aad  jns     short loc_180042AFB
0x180042aaf  mov     [rsp+160h+var_120], rsi
0x180042ab4  lea     rax, aHresult; "HRESULT"
0x180042abb  mov     [rsp+160h+var_128], rax
0x180042ac0  mov     dword ptr [rsp+160h+var_130], 362h
0x180042ac8  lea     r14, aOnecoreuapDsEx_30+21h; "genericcallpackagehelper.cpp"
0x180042acf  mov     r8, rdi
0x180042ad2  mov     ecx, 2
0x180042ad7  mov     [rsp+160h+var_138], r14
0x180042adc  mov     r9d, ecx
0x180042adf  mov     dword ptr [rsp+160h+ReturnLength], ebx
0x180042ae3  xor     edx, edx
0x180042ae5  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180042aea  btr     ebx, 1Ch
0x180042aee  bts     ebx, 1Eh
0x180042af2  mov     [rsp+160h+var_110], ebx
0x180042af6  jmp     loc_180042DA2
0x180042afb  lea     rdx, aAddWpj; "add_wpj"
0x180042b02  mov     rcx, [r12]; String1
0x180042b06  call    wcscmp_0
0x180042b0b  nop
0x180042b0c  test    eax, eax
0x180042b0e  jnz     loc_180042C4B
0x180042b14  lea     rax, [rsp+160h+var_10C]
0x180042b19  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x180042b1e  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180042b24  lea     r8, [rbp+60h+TokenInformation]; TokenInformation
0x180042b28  lea     edx, [r9-57h]; TokenInformationClass
0x180042b2c  mov     rcx, r14; TokenHandle
0x180042b2f  call    cs:__imp_NtQueryInformationToken
0x180042b35  mov     [rsp+160h+var_110], eax
0x180042b39  test    eax, eax
0x180042b3b  jns     short loc_180042B5B
0x180042b3d  mov     [rsp+160h+var_120], rsi
0x180042b42  lea     rcx, aNtstatus; "NTSTATUS"
0x180042b49  mov     [rsp+160h+var_128], rcx
0x180042b4e  mov     dword ptr [rsp+160h+var_130], 368h
0x180042b56  jmp     loc_180042D7F
0x180042b5b  lea     rdx, [rsp+160h+var_108]
0x180042b60  mov     rcx, [rbp+60h+TokenInformation]; Sid
0x180042b64  call    ?SidToString@StringUtility@@SAJPEAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; StringUtility::SidToString(void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180042b69  mov     ebx, eax
0x180042b6b  lea     r14, aOnecoreuapDsEx_30+21h; "genericcallpackagehelper.cpp"
0x180042b72  mov     r8, rdi
0x180042b75  test    eax, eax
0x180042b77  jns     short loc_180042B97
0x180042b79  mov     [rsp+160h+var_120], rsi
0x180042b7e  lea     rax, aHresult; "HRESULT"
0x180042b85  mov     [rsp+160h+var_128], rax
0x180042b8a  mov     dword ptr [rsp+160h+var_130], 369h
0x180042b92  jmp     loc_180042AD2
0x180042b97  mov     rax, rsi
0x180042b9a  mov     rbx, [rsp+160h+var_108]
0x180042b9f  test    rbx, rbx
0x180042ba2  cmovnz  rax, rbx
0x180042ba6  mov     [rsp+160h+var_120], rax
0x180042bab  lea     rax, aUsersid_0; "userSid"
0x180042bb2  mov     [rsp+160h+var_128], rax
0x180042bb7  mov     dword ptr [rsp+160h+var_130], 36Ah
0x180042bbf  mov     [rsp+160h+var_138], r14
0x180042bc4  mov     [rsp+160h+ReturnLength], 0
0x180042bcd  mov     ecx, 4
0x180042bd2  mov     r9d, ecx
0x180042bd5  xor     edx, edx
0x180042bd7  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180042bdc  mov     r8, rbx; unsigned __int16 *
0x180042bdf  mov     rdx, r13; struct PluginState *
0x180042be2  mov     rcx, r15; struct AadContextFunctions *
0x180042be5  call    ?UpdateJoinInfo@TokenBindingHelper@@SAJPEAVAadContextFunctions@@AEAVPluginState@@PEBG@Z; TokenBindingHelper::UpdateJoinInfo(AadContextFunctions *,PluginState &,ushort const *)
0x180042bea  mov     [rsp+160h+var_110], eax
0x180042bee  test    eax, eax
0x180042bf0  jns     short loc_180042C10
0x180042bf2  mov     [rsp+160h+var_120], rsi
0x180042bf7  lea     rcx, aNtstatus; "NTSTATUS"
0x180042bfe  mov     [rsp+160h+var_128], rcx
0x180042c03  mov     dword ptr [rsp+160h+var_130], 36Bh
0x180042c0b  jmp     loc_180042D86
0x180042c10  mov     r8, [rsp+160h+var_F0]; struct DiagnosticContext *
0x180042c15  mov     rdx, [r13+0]; void *
0x180042c19  mov     rcx, r15; struct AadContextFunctions *
0x180042c1c  call    ?UpdateWorkPlaceP2PCertificates@@YAJPEAVAadContextFunctions@@PEAXAEAVDiagnosticContext@@@Z; UpdateWorkPlaceP2PCertificates(AadContextFunctions *,void *,DiagnosticContext &)
0x180042c21  mov     [rsp+160h+var_110], eax
0x180042c25  test    eax, eax
0x180042c27  jns     loc_180042DA2
0x180042c2d  mov     [rsp+160h+var_120], rsi
0x180042c32  lea     rcx, aNtstatus; "NTSTATUS"
0x180042c39  mov     [rsp+160h+var_128], rcx
0x180042c3e  mov     dword ptr [rsp+160h+var_130], 36Eh
0x180042c46  jmp     loc_180042D86
0x180042c4b  lea     rdx, aRemoveWpj; "remove_wpj"
0x180042c52  mov     rcx, [r12]; String1
0x180042c56  call    wcscmp_0
0x180042c5b  nop
0x180042c5c  test    eax, eax
0x180042c5e  jnz     loc_180042D5D
0x180042c64  lea     rax, [rsp+160h+var_10C]
0x180042c69  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x180042c6e  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180042c74  lea     r8, [rbp+60h+TokenInformation]; TokenInformation
0x180042c78  lea     edx, [r9-57h]; TokenInformationClass
0x180042c7c  mov     rcx, r14; TokenHandle
0x180042c7f  call    cs:__imp_NtQueryInformationToken
0x180042c85  mov     [rsp+160h+var_110], eax
0x180042c89  test    eax, eax
0x180042c8b  jns     short loc_180042CAB
0x180042c8d  mov     [rsp+160h+var_120], rsi
0x180042c92  lea     rcx, aNtstatus; "NTSTATUS"
0x180042c99  mov     [rsp+160h+var_128], rcx
0x180042c9e  mov     dword ptr [rsp+160h+var_130], 373h
0x180042ca6  jmp     loc_180042D7F
0x180042cab  lea     rdx, [rsp+160h+var_108]
0x180042cb0  mov     rcx, [rbp+60h+TokenInformation]; Sid
0x180042cb4  call    ?SidToString@StringUtility@@SAJPEAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; StringUtility::SidToString(void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180042cb9  mov     ebx, eax
0x180042cbb  lea     r14, aOnecoreuapDsEx_30+21h; "genericcallpackagehelper.cpp"
0x180042cc2  mov     r8, rdi
0x180042cc5  test    eax, eax
0x180042cc7  jns     short loc_180042CE7
0x180042cc9  mov     [rsp+160h+var_120], rsi
0x180042cce  lea     rax, aHresult; "HRESULT"
0x180042cd5  mov     [rsp+160h+var_128], rax
0x180042cda  mov     dword ptr [rsp+160h+var_130], 374h
0x180042ce2  jmp     loc_180042AD2
0x180042ce7  mov     rax, rsi
0x180042cea  mov     rbx, [rsp+160h+var_108]
0x180042cef  test    rbx, rbx
0x180042cf2  cmovnz  rax, rbx
0x180042cf6  mov     [rsp+160h+var_120], rax
0x180042cfb  lea     rax, aUsersid_0; "userSid"
0x180042d02  mov     [rsp+160h+var_128], rax
0x180042d07  mov     dword ptr [rsp+160h+var_130], 375h
0x180042d0f  mov     [rsp+160h+var_138], r14
0x180042d14  mov     [rsp+160h+ReturnLength], 0
0x180042d1d  mov     ecx, 4
0x180042d22  mov     r9d, ecx
0x180042d25  xor     edx, edx
0x180042d27  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180042d2c  mov     r8, rbx; unsigned __int16 *
0x180042d2f  mov     rdx, r13; struct PluginState *
0x180042d32  mov     rcx, r15; struct AadContextFunctions *
0x180042d35  call    ?UpdateJoinInfo@TokenBindingHelper@@SAJPEAVAadContextFunctions@@AEAVPluginState@@PEBG@Z; TokenBindingHelper::UpdateJoinInfo(AadContextFunctions *,PluginState &,ushort const *)
0x180042d3a  mov     [rsp+160h+var_110], eax
0x180042d3e  test    eax, eax
0x180042d40  jns     short loc_180042DA2
0x180042d42  mov     [rsp+160h+var_120], rsi
0x180042d47  lea     rcx, aNtstatus; "NTSTATUS"
0x180042d4e  mov     [rsp+160h+var_128], rcx
0x180042d53  mov     dword ptr [rsp+160h+var_130], 376h
0x180042d5b  jmp     short loc_180042D86
0x180042d5d  mov     eax, 0C000000Dh
0x180042d62  mov     [rsp+160h+var_110], eax
0x180042d66  mov     [rsp+160h+var_120], rsi
0x180042d6b  lea     rcx, aNtstatus; "NTSTATUS"
0x180042d72  mov     [rsp+160h+var_128], rcx
0x180042d77  mov     dword ptr [rsp+160h+var_130], 37Ah
0x180042d7f  lea     r14, aOnecoreuapDsEx_30+21h; "genericcallpackagehelper.cpp"
0x180042d86  mov     [rsp+160h+var_138], r14
0x180042d8b  mov     ecx, 2
0x180042d90  mov     dword ptr [rsp+160h+ReturnLength], eax
0x180042d94  mov     r9d, ecx
0x180042d97  mov     r8, rdi
0x180042d9a  xor     edx, edx
0x180042d9c  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180042da1  nop
0x180042da2  lea     rcx, [rsp+160h+var_100]; this
0x180042da7  call    ??1ImpersonateLoggedOnUserHelper@@QEAA@XZ; ImpersonateLoggedOnUserHelper::~ImpersonateLoggedOnUserHelper(void)
0x180042dac  mov     ebx, [rsp+160h+var_110]
0x180042db0  lea     rcx, [rsp+160h+var_E8]
0x180042db5  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x180042dba  nop
0x180042dbb  lea     rcx, [rsp+160h+var_108]; this
0x180042dc0  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x180042dc5  mov     eax, ebx
0x180042dc7  mov     rcx, [rbp+60h+var_50]
0x180042dcb  xor     rcx, rsp; StackCookie
0x180042dce  call    __security_check_cookie
0x180042dd3  add     rsp, 128h
0x180042dda  pop     r15
0x180042ddc  pop     r14
0x180042dde  pop     r13
0x180042de0  pop     r12
0x180042de2  pop     rdi
0x180042de3  pop     rsi
0x180042de4  pop     rbx
0x180042de5  pop     rbp
0x180042de6  retn
```
