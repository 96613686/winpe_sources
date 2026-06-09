# _BriCreateEvent2

- ea: `0x18003c580`
- end: `0x18003cb79`
- name: `_BriCreateEvent2`
- size: `1529`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003a60`
- `0x180003a90`
- `0x180003f50`
- `0x18000498c`
- `0x18000659c`
- `0x1800069f0`
- `0x180006c84`
- `0x18002643c`
- `0x180026f00`
- `0x1800272e4`
- `0x180027368`
- `0x180027468`
- `0x180039cb4`
- `0x180039fa0`
- `0x18003c580`
- `0x180051420`
- `0x1800692a0`
- `0x1800693e4`
- `0x180069520`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003c780`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003c780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c6e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c6e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c795`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c795`
- `ntdll!RtlLengthSid` at `0x18003c667`
- `ntdll!RtlLengthSid` at `0x18003c667`
- `ntdll!RtlValidSid` at `0x18003c653`
- `ntdll!RtlValidSid` at `0x18003c653`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003c6de`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003c6de`

## string_xrefs

- `0x18003c6a0`: `_BriCreateEvent2`
- `0x18003c7ae`: `_BriCreateEvent2`
- `0x18003c85f`: `_BriCreateEvent2`
- `0x18003c994`: `_BriCreateEvent2`
- `0x18003ca0f`: `_BriCreateEvent2`
- `0x18003cad5`: `_BriCreateEvent2`
- `0x18003c691`: `Unable to parse broker parameters.`
- `0x18003c83a`: `Unable to obtain AppName for call RegistrationName=%S, AppName=%S, UserSid=%S.`
- `0x18003c79f`: `Invalid UserSid.`
- `0x18003c968`: `Failed to create client context RegistrationName=%S, AppName=%S, UserSid=%S.`
- `0x18003caa9`: `Registration failed RegistrationName=%S, AppName=%S, UserSid=%S.`

## pseudocode

```c
__int64 __fastcall BriCreateEvent2(
        __int64 a1,
        void *a2,
        unsigned int a3,
        void *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        struct _WNF_STATE_NAME *a9,
        __int64 a10,
        unsigned __int64 *a11)
{
  void *v12; // rcx
  ULONG v13; // ebx
  int v14; // eax
  signed int v15; // esi
  int IsCallerLocalSystem; // eax
  void *v17; // rcx
  int v18; // r15d
  __int64 v19; // r8
  signed int LastError; // eax
  unsigned __int64 v21; // rdx
  __int64 v22; // rbx
  LPCWSTR *v23; // rdi
  LPCWSTR *v24; // rcx
  unsigned int v25; // ebx
  int v27; // eax
  LPCWSTR *v28; // rdx
  unsigned __int16 **v29; // rcx
  int IsAppInstalled; // r14d
  const WCHAR *v31; // rdx
  const WCHAR *v32; // rcx
  WCHAR *v33; // rdi
  __int64 v34; // r8
  __int64 v35; // r8
  unsigned __int64 v36; // rdx
  void (__high *v37)(unsigned __int64, void *, enum _BR_EVENT_CALL_REASON); // r9
  unsigned int v38; // edi
  LPCWSTR *v39; // r8
  PCWSTR *v40; // rdx
  unsigned __int16 **v41; // rcx
  char **v42; // rbx
  const WCHAR *v43; // rcx
  PCWSTR *v44; // rax
  const unsigned __int16 *v45; // rax
  const unsigned __int16 *v46; // r9
  const unsigned __int16 *v47; // r8
  const unsigned __int16 *v48; // rdx
  int v49; // eax
  LPCWSTR *v50; // r8
  PCWSTR *v51; // rdx
  unsigned __int16 **v52; // rcx
  struct _BR_RPC_CONTEXT_ENTRY *v53; // rax
  LPWSTR StringSid; // [rsp+40h] [rbp-A9h] BYREF
  unsigned int v55; // [rsp+48h] [rbp-A1h]
  unsigned __int64 v56; // [rsp+50h] [rbp-99h] BYREF
  HANDLE ProcessHandle; // [rsp+58h] [rbp-91h]
  LPCWSTR v58[2]; // [rsp+60h] [rbp-89h] BYREF
  unsigned __int64 v59; // [rsp+70h] [rbp-79h]
  unsigned __int64 v60; // [rsp+78h] [rbp-71h]
  PCWSTR packageFullName[2]; // [rsp+80h] [rbp-69h] BYREF
  __int64 v62; // [rsp+90h] [rbp-59h]
  unsigned __int64 v63; // [rsp+98h] [rbp-51h]
  unsigned __int16 *v64[2]; // [rsp+A0h] [rbp-49h] BYREF
  __int64 v65; // [rsp+B0h] [rbp-39h]
  unsigned __int64 v66; // [rsp+B8h] [rbp-31h]
  struct _WNF_STATE_NAME v67; // [rsp+C0h] [rbp-29h] BYREF
  unsigned __int16 *v68[2]; // [rsp+C8h] [rbp-21h] BYREF
  __int64 v69; // [rsp+D8h] [rbp-11h]
  unsigned __int64 v70; // [rsp+E0h] [rbp-9h]

  v55 = a3;
  *(_OWORD *)v64 = 0;
  v66 = 7;
  *(_OWORD *)v68 = 0;
  v70 = 7;
  *(_OWORD *)v58 = 0;
  v60 = 7;
  ProcessHandle = a2;
  v65 = 0;
  LOWORD(v64[0]) = 0;
  v69 = 0;
  LOWORD(v68[0]) = 0;
  v67 = 0;
  v59 = 0;
  LOWORD(v58[0]) = 0;
  v56 = 0;
  if ( !a9
    || !a6
    || !a11
    || !a4
    || !a5
    || (v12 = *(void **)(a5 + 8)) == 0
    || *(_DWORD *)a5 < 2u
    || !RtlValidSid(v12)
    || (v13 = *(_DWORD *)a5, v13 < RtlLengthSid(*(PSID *)(a5 + 8))) )
  {
    v15 = 13;
    goto LABEL_85;
  }
  v14 = ParseBrokerEventParameters(a6, v64, v68, &v67);
  v15 = v14;
  if ( v14 < 0 )
  {
    LogSmsRouterError("_BriCreateEvent2", 0x181u, v14, "Unable to parse broker parameters.");
    if ( (v15 & 0x1FFF0000) == 0x70000 )
      v15 = (unsigned __int16)v15;
    goto LABEL_85;
  }
  IsCallerLocalSystem = CSmsRpcUtils::IsCallerLocalSystem();
  v17 = *(void **)(a5 + 8);
  v18 = IsCallerLocalSystem;
  StringSid = 0;
  if ( !ConvertSidToStringSidW(v17, &StringSid) )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( v18 )
  {
    v21 = -1;
    do
      ++v21;
    while ( StringSid[v21] );
    if ( v21 > v60 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v58,
        v21,
        v19,
        StringSid);
    }
    else
    {
      v22 = 2 * v21;
      v59 = v21;
      v23 = v58;
      if ( v60 > 7 )
        v23 = (LPCWSTR *)v58[0];
      memmove_0(v23, StringSid, 2 * v21);
      *(_WORD *)((char *)v23 + v22) = 0;
    }
  }
  else
  {
    CSmsRpcUtils::GetUserSid(v58);
    v24 = v58;
    if ( v60 > 7 )
      v24 = (LPCWSTR *)v58[0];
    if ( (unsigned int)_o__wcsicmp(v24, StringSid) )
      v15 = -2147024891;
  }
  if ( StringSid )
    LocalFree(StringSid);
  if ( v15 >= 0 )
  {
    v62 = 0;
    *(_OWORD *)packageFullName = 0;
    LOWORD(packageFullName[0]) = 0;
    v63 = 7;
    LODWORD(StringSid) = 0;
    v27 = CSmsRpcUtils::CalculateAppName(a4);
    v15 = v27;
    if ( v27 >= 0 )
    {
      IsAppInstalled = (int)StringSid;
      if ( (_DWORD)StringSid )
        goto LABEL_88;
      if ( v18 )
      {
        v31 = (const WCHAR *)v58;
        v32 = (const WCHAR *)packageFullName;
        if ( v60 > 7 )
          v31 = v58[0];
        if ( v63 > 7 )
          v32 = packageFullName[0];
        IsAppInstalled = CSmsRpcUtils::IsAppInstalled(v32, v31, 0);
        if ( IsAppInstalled )
        {
LABEL_88:
          v43 = (const WCHAR *)packageFullName;
          if ( v63 > 7 )
            v43 = packageFullName[0];
          if ( !(unsigned int)CSmsRpcUtils::IsMessagingCapableApp(v43) )
          {
            v44 = packageFullName;
            if ( v63 > 7 )
              v44 = (PCWSTR *)packageFullName[0];
            LogSmsRouterError(
              "_BriCreateEvent2",
              0x1BFu,
              -2147024891,
              "AppName %S does not contain messaging capability.",
              v44);
            v15 = 5;
            goto LABEL_83;
          }
        }
      }
      v33 = (WCHAR *)operator new(0x60u);
      StringSid = v33;
      *(_OWORD *)v33 = 0;
      *((_QWORD *)v33 + 2) = 0;
      *((_QWORD *)v33 + 3) = 7;
      *v33 = 0;
      *((_OWORD *)v33 + 2) = 0;
      *((_QWORD *)v33 + 6) = 0;
      *((_QWORD *)v33 + 7) = 7;
      v33[16] = 0;
      *((_OWORD *)v33 + 4) = 0;
      *((_QWORD *)v33 + 10) = 0;
      *((_QWORD *)v33 + 11) = 7;
      v33[32] = 0;
      std::wstring::operator=((__int64)(v33 + 16), packageFullName, (__int64)(v33 + 16));
      std::wstring::operator=((__int64)v33, v64, v34);
      std::wstring::operator=((__int64)(v33 + 32), v58, v35);
      v38 = BrpRpcContextCreate(ProcessHandle, v36, &StringSid, v37, &v56);
      if ( v38 )
      {
        v39 = v58;
        v40 = packageFullName;
        if ( v60 > 7 )
          v39 = (LPCWSTR *)v58[0];
        v41 = v64;
        if ( v63 > 7 )
          v40 = (PCWSTR *)packageFullName[0];
        if ( v66 > 7 )
          v41 = (unsigned __int16 **)v64[0];
        LogSmsRouterError(
          "_BriCreateEvent2",
          0x1E2u,
          v15,
          "Failed to create client context RegistrationName=%S, AppName=%S, UserSid=%S.",
          v41,
          v40,
          v39);
        v42 = (char **)StringSid;
        if ( StringSid )
        {
          std::wstring::~wstring((char **)StringSid + 8);
          std::wstring::~wstring(v42 + 4);
          std::wstring::~wstring(v42);
          operator delete(v42);
        }
        v15 = v38;
        goto LABEL_83;
      }
      v45 = (const unsigned __int16 *)v68;
      if ( v70 > 7 )
        v45 = v68[0];
      v46 = (const unsigned __int16 *)v58;
      v47 = (const unsigned __int16 *)packageFullName;
      v48 = (const unsigned __int16 *)v64;
      if ( v60 > 7 )
        v46 = v58[0];
      if ( v63 > 7 )
        v47 = packageFullName[0];
      if ( v66 > 7 )
        v48 = v64[0];
      v49 = CSmsBrokerHandler::OnCreateEvent(
              (CSmsBrokerHandler *)&CSmsBrokerHandler::s_instance,
              v48,
              v47,
              v46,
              v45,
              &v67,
              IsAppInstalled);
      v15 = v49;
      if ( v49 >= 0 )
      {
        v15 = 0;
        *a9 = v67;
        *a11 = v56;
LABEL_83:
        std::wstring::~wstring((char **)packageFullName);
LABEL_85:
        std::wstring::~wstring((char **)v58);
        std::wstring::~wstring((char **)v68);
        std::wstring::~wstring((char **)v64);
        return (unsigned int)v15;
      }
      v50 = v58;
      v51 = packageFullName;
      if ( v60 > 7 )
        v50 = (LPCWSTR *)v58[0];
      v52 = v64;
      if ( v63 > 7 )
        v51 = (PCWSTR *)packageFullName[0];
      if ( v66 > 7 )
        v52 = (unsigned __int16 **)v64[0];
      LogSmsRouterError(
        "_BriCreateEvent2",
        0x1F3u,
        v49,
        "Registration failed RegistrationName=%S, AppName=%S, UserSid=%S.",
        v52,
        v51,
        v50);
      v53 = BrpRpcContextFindAndRemove(v56, 0);
      if ( v53 )
        BrpRpcContextEntryDestroy(v53, v55);
    }
    else
    {
      v28 = v58;
      v29 = v64;
      if ( v60 > 7 )
        v28 = (LPCWSTR *)v58[0];
      if ( v66 > 7 )
        v29 = (unsigned __int16 **)v64[0];
      LogSmsRouterError(
        "_BriCreateEvent2",
        0x1ADu,
        v27,
        "Unable to obtain AppName for call RegistrationName=%S, AppName=%S, UserSid=%S.",
        v29,
        a4,
        v28);
    }
    if ( (v15 & 0x1FFF0000) == 0x70000 )
      v15 = (unsigned __int16)v15;
    goto LABEL_83;
  }
  LogSmsRouterError("_BriCreateEvent2", 0x1A3u, v15, "Invalid UserSid.");
  v25 = (unsigned __int16)v15;
  if ( (v15 & 0x1FFF0000) != 0x70000 )
    v25 = v15;
  std::wstring::~wstring((char **)v58);
  std::wstring::~wstring((char **)v68);
  std::wstring::~wstring((char **)v64);
  return v25;
}

```

## disassembly

```asm
0x18003c580  mov     [rsp-8+arg_0], rbx
0x18003c585  push    rbp
0x18003c586  push    rsi
0x18003c587  push    rdi
0x18003c588  push    r12
0x18003c58a  push    r13
0x18003c58c  push    r14
0x18003c58e  push    r15
0x18003c590  lea     rbp, [rsp-7]
0x18003c595  sub     rsp, 0F0h
0x18003c59c  mov     rax, cs:__security_cookie
0x18003c5a3  xor     rax, rsp
0x18003c5a6  mov     [rbp+37h+var_38], rax
0x18003c5aa  mov     rdi, [rbp+37h+arg_20]
0x18003c5ae  xor     ebx, ebx
0x18003c5b0  mov     rsi, [rbp+37h+arg_28]
0x18003c5b4  xorps   xmm0, xmm0
0x18003c5b7  mov     r13, [rbp+37h+arg_40]
0x18003c5be  mov     r14, r9
0x18003c5c1  mov     r12, [rbp+37h+arg_50]
0x18003c5c8  lea     ecx, [rbx+7]
0x18003c5cb  mov     [rsp+120h+var_D8], r8d
0x18003c5d0  movups  xmmword ptr [rbp+37h+var_80], xmm0
0x18003c5d4  mov     [rbp+37h+var_68], rcx
0x18003c5d8  movups  xmmword ptr [rbp+37h+var_58], xmm0
0x18003c5dc  mov     [rbp+37h+var_40], rcx
0x18003c5e0  movups  xmmword ptr [rsp+120h+var_C0], xmm0
0x18003c5e5  mov     [rbp+37h+var_A8], rcx
0x18003c5e9  mov     [rsp+120h+ProcessHandle], rdx
0x18003c5ee  mov     [rbp+37h+var_70], rbx
0x18003c5f2  mov     word ptr [rbp+37h+var_80], bx
0x18003c5f6  mov     [rbp+37h+var_48], rbx
0x18003c5fa  mov     word ptr [rbp+37h+var_58], bx
0x18003c5fe  mov     qword ptr [rbp+37h+var_60.Data], rbx
0x18003c602  mov     [rbp+37h+var_B0], rbx
0x18003c606  mov     word ptr [rsp+120h+var_C0], bx
0x18003c60b  mov     [rsp+120h+var_D0], rbx
0x18003c610  test    r13, r13
0x18003c613  jz      loc_18003CB2F
0x18003c619  test    rsi, rsi
0x18003c61c  jz      loc_18003CB2F
0x18003c622  test    r12, r12
0x18003c625  jz      loc_18003CB2F
0x18003c62b  test    r9, r9
0x18003c62e  jz      loc_18003CB2F
0x18003c634  test    rdi, rdi
0x18003c637  jz      loc_18003CB2F
0x18003c63d  mov     rcx, [rdi+8]; Sid
0x18003c641  test    rcx, rcx
0x18003c644  jz      loc_18003CB2F
0x18003c64a  cmp     dword ptr [rdi], 2
0x18003c64d  jb      loc_18003CB2F
0x18003c653  call    cs:__imp_RtlValidSid
0x18003c659  test    al, al
0x18003c65b  jz      loc_18003CB2F
0x18003c661  mov     rcx, [rdi+8]; Sid
0x18003c665  mov     ebx, [rdi]
0x18003c667  call    cs:__imp_RtlLengthSid
0x18003c66d  cmp     ebx, eax
0x18003c66f  jb      loc_18003CB2F
0x18003c675  lea     r9, [rbp+37h+var_60]
0x18003c679  mov     rcx, rsi
0x18003c67c  lea     r8, [rbp+37h+var_58]
0x18003c680  lea     rdx, [rbp+37h+var_80]
0x18003c684  call    ?ParseBrokerEventParameters@@YAJPEAU_BR_EVENT_PARAMETERS@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1AEAU_WNF_STATE_NAME@@@Z; ParseBrokerEventParameters(_BR_EVENT_PARAMETERS *,std::wstring &,std::wstring &,_WNF_STATE_NAME &)
0x18003c689  xor     ebx, ebx
0x18003c68b  mov     esi, eax
0x18003c68d  test    eax, eax
0x18003c68f  jns     short loc_18003C6C8
0x18003c691  lea     r9, aUnableToParseB; "Unable to parse broker parameters."
0x18003c698  mov     r8d, eax; int
0x18003c69b  mov     edx, 181h; unsigned int
0x18003c6a0  lea     rcx, aBricreateevent; "_BriCreateEvent2"
0x18003c6a7  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003c6ac  mov     ecx, esi
0x18003c6ae  and     ecx, 1FFF0000h
0x18003c6b4  cmp     ecx, 70000h
0x18003c6ba  jnz     loc_18003CB34
0x18003c6c0  movzx   esi, si
0x18003c6c3  jmp     loc_18003CB34
0x18003c6c8  call    ?IsCallerLocalSystem@CSmsRpcUtils@@SAHXZ; CSmsRpcUtils::IsCallerLocalSystem(void)
0x18003c6cd  mov     rcx, [rdi+8]; Sid
0x18003c6d1  lea     rdx, [rsp+120h+StringSid]; StringSid
0x18003c6d6  mov     r15d, eax
0x18003c6d9  mov     [rsp+120h+StringSid], rbx
0x18003c6de  call    cs:__imp_ConvertSidToStringSidW
0x18003c6e4  test    eax, eax
0x18003c6e6  jnz     short loc_18003C6FD
0x18003c6e8  call    cs:__imp_GetLastError
0x18003c6ee  mov     esi, eax
0x18003c6f0  test    eax, eax
0x18003c6f2  jle     short loc_18003C6FD
0x18003c6f4  movzx   esi, ax
0x18003c6f7  or      esi, 80070000h
0x18003c6fd  mov     edi, 80070005h
0x18003c702  test    r15d, r15d
0x18003c705  jz      short loc_18003C761
0x18003c707  mov     r9, [rsp+120h+StringSid]
0x18003c70c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003c710  inc     rdx
0x18003c713  cmp     [r9+rdx*2], bx
0x18003c718  jnz     short loc_18003C710
0x18003c71a  cmp     rdx, [rbp+37h+var_A8]
0x18003c71e  ja      short loc_18003C755
0x18003c720  cmp     [rbp+37h+var_A8], 7
0x18003c725  lea     rbx, [rdx+rdx]
0x18003c729  mov     [rbp+37h+var_B0], rdx
0x18003c72d  lea     rdi, [rsp+120h+var_C0]
0x18003c732  cmova   rdi, [rsp+120h+var_C0]
0x18003c738  mov     r8, rbx; Size
0x18003c73b  mov     rcx, rdi; void *
0x18003c73e  mov     rdx, r9; Src
0x18003c741  call    memmove_0
0x18003c746  xor     eax, eax
0x18003c748  mov     [rbx+rdi], ax
0x18003c74c  xor     ebx, ebx
0x18003c74e  mov     edi, 80070005h
0x18003c753  jmp     short loc_18003C78B
0x18003c755  lea     rcx, [rsp+120h+var_C0]
0x18003c75a  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18003c75f  jmp     short loc_18003C78B
0x18003c761  lea     rcx, [rsp+120h+var_C0]
0x18003c766  call    ?GetUserSid@CSmsRpcUtils@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CSmsRpcUtils::GetUserSid(std::wstring &)
0x18003c76b  cmp     [rbp+37h+var_A8], 7
0x18003c770  lea     rcx, [rsp+120h+var_C0]
0x18003c775  mov     rdx, [rsp+120h+StringSid]
0x18003c77a  cmova   rcx, [rsp+120h+var_C0]
0x18003c780  call    cs:__imp__o__wcsicmp
0x18003c786  test    eax, eax
0x18003c788  cmovnz  esi, edi
0x18003c78b  mov     rcx, [rsp+120h+StringSid]; hMem
0x18003c790  test    rcx, rcx
0x18003c793  jz      short loc_18003C79B
0x18003c795  call    cs:__imp_LocalFree
0x18003c79b  test    esi, esi
0x18003c79d  jns     short loc_18003C7F1
0x18003c79f  lea     r9, aInvalidUsersid; "Invalid UserSid."
0x18003c7a6  mov     r8d, esi; int
0x18003c7a9  mov     edx, 1A3h; unsigned int
0x18003c7ae  lea     rcx, aBricreateevent; "_BriCreateEvent2"
0x18003c7b5  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003c7ba  mov     ecx, esi
0x18003c7bc  movzx   ebx, si
0x18003c7bf  and     ecx, 1FFF0000h
0x18003c7c5  cmp     ecx, 70000h
0x18003c7cb  lea     rcx, [rsp+120h+var_C0]; void *
0x18003c7d0  cmovnz  ebx, esi
0x18003c7d3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c7d8  lea     rcx, [rbp+37h+var_58]; void *
0x18003c7dc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c7e1  lea     rcx, [rbp+37h+var_80]; void *
0x18003c7e5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c7ea  mov     eax, ebx
0x18003c7ec  jmp     loc_18003CB52
0x18003c7f1  xorps   xmm0, xmm0
0x18003c7f4  mov     [rbp+37h+var_90], rbx
0x18003c7f8  movups  xmmword ptr [rbp+37h+packageFullName], xmm0
0x18003c7fc  lea     r8, [rsp+120h+StringSid]
0x18003c801  mov     word ptr [rbp+37h+packageFullName], bx
0x18003c805  lea     rdx, [rbp+37h+packageFullName]
0x18003c809  mov     [rbp+37h+var_88], 7
0x18003c811  mov     rcx, r14; Src
0x18003c814  mov     dword ptr [rsp+120h+StringSid], ebx
0x18003c818  call    ?CalculateAppName@CSmsRpcUtils@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAH@Z; CSmsRpcUtils::CalculateAppName(ushort const *,std::wstring &,int &)
0x18003c81d  mov     esi, eax
0x18003c81f  test    eax, eax
0x18003c821  jns     short loc_18003C870
0x18003c823  cmp     [rbp+37h+var_A8], 7
0x18003c828  lea     rdx, [rsp+120h+var_C0]
0x18003c82d  lea     rcx, [rbp+37h+var_80]
0x18003c831  mov     r8d, eax; int
0x18003c834  cmova   rdx, [rsp+120h+var_C0]
0x18003c83a  lea     r9, aUnableToObtain; "Unable to obtain AppName for call Regis"...
0x18003c841  cmp     [rbp+37h+var_68], 7
0x18003c846  mov     qword ptr [rsp+120h+var_F0], rdx
0x18003c84b  mov     edx, 1ADh; unsigned int
0x18003c850  cmova   rcx, [rbp+37h+var_80]
0x18003c855  mov     [rsp+120h+var_F8], r14
0x18003c85a  mov     [rsp+120h+var_100], rcx
0x18003c85f  lea     rcx, aBricreateevent; "_BriCreateEvent2"
0x18003c866  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003c86b  jmp     loc_18003CAFE
0x18003c870  mov     r14d, dword ptr [rsp+120h+StringSid]
0x18003c875  test    r14d, r14d
0x18003c878  jnz     loc_18003C9D8
0x18003c87e  test    r15d, r15d
0x18003c881  lea     r15d, [r14+7]
0x18003c885  jz      short loc_18003C8B6
0x18003c887  cmp     [rbp+37h+var_A8], r15
0x18003c88b  lea     rdx, [rsp+120h+var_C0]
0x18003c890  lea     rcx, [rbp+37h+packageFullName]
0x18003c894  cmova   rdx, [rsp+120h+var_C0]; StringSid
0x18003c89a  cmp     [rbp+37h+var_88], r15
0x18003c89e  cmova   rcx, [rbp+37h+packageFullName]; packageFullName
0x18003c8a3  xor     r8d, r8d; int
0x18003c8a6  call    ?IsAppInstalled@CSmsRpcUtils@@SAHPEBG0H@Z; CSmsRpcUtils::IsAppInstalled(ushort const *,ushort const *,int)
0x18003c8ab  mov     r14d, eax
0x18003c8ae  test    eax, eax
0x18003c8b0  jnz     loc_18003C9DE
0x18003c8b6  mov     ecx, 60h ; '`'; Size
0x18003c8bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c8c0  xorps   xmm0, xmm0
0x18003c8c3  lea     rdx, [rbp+37h+packageFullName]
0x18003c8c7  mov     rdi, rax
0x18003c8ca  mov     [rsp+120h+StringSid], rdi
0x18003c8cf  movups  xmmword ptr [rax], xmm0
0x18003c8d2  mov     [rax+10h], rbx
0x18003c8d6  lea     r8, [rax+20h]
0x18003c8da  mov     [rax+18h], r15
0x18003c8de  mov     rcx, r8
0x18003c8e1  mov     [rax], bx
0x18003c8e4  movups  xmmword ptr [r8], xmm0
0x18003c8e8  mov     [r8+10h], rbx
0x18003c8ec  mov     [r8+18h], r15
0x18003c8f0  mov     [r8], bx
0x18003c8f4  lea     rbx, [rax+40h]
0x18003c8f8  movups  xmmword ptr [rbx], xmm0
0x18003c8fb  xor     eax, eax
0x18003c8fd  mov     qword ptr [rbx+10h], 0
0x18003c905  mov     [rbx+18h], r15
0x18003c909  mov     [rbx], ax
0x18003c90c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003c911  lea     rdx, [rbp+37h+var_80]
0x18003c915  mov     rcx, rdi
0x18003c918  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003c91d  lea     rdx, [rsp+120h+var_C0]
0x18003c922  mov     rcx, rbx
0x18003c925  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003c92a  mov     rcx, [rsp+120h+ProcessHandle]; ProcessHandle
0x18003c92f  lea     rax, [rsp+120h+var_D0]
0x18003c934  lea     r8, [rsp+120h+StringSid]; void *
0x18003c939  mov     [rsp+120h+var_100], rax; unsigned __int64 *
0x18003c93e  call    ?BrpRpcContextCreate@@YAKPEAX_K0P6AX10W4_BR_EVENT_CALL_REASON@@@ZPEA_K@Z; BrpRpcContextCreate(void *,unsigned __int64,void *,void (*)(unsigned __int64,void *,_BR_EVENT_CALL_REASON),unsigned __int64 *)
0x18003c943  mov     edi, eax
0x18003c945  test    eax, eax
0x18003c947  jz      loc_18003CA2F
0x18003c94d  cmp     [rbp+37h+var_A8], r15
0x18003c951  lea     r8, [rsp+120h+var_C0]
0x18003c956  lea     rdx, [rbp+37h+packageFullName]
0x18003c95a  cmova   r8, [rsp+120h+var_C0]
0x18003c960  lea     rcx, [rbp+37h+var_80]
0x18003c964  cmp     [rbp+37h+var_88], r15
0x18003c968  lea     r9, aFailedToCreate; "Failed to create client context Registr"...
0x18003c96f  mov     qword ptr [rsp+120h+var_F0], r8
0x18003c974  mov     r8d, esi; int
0x18003c977  cmova   rdx, [rbp+37h+packageFullName]
0x18003c97c  cmp     [rbp+37h+var_68], r15
0x18003c980  mov     [rsp+120h+var_F8], rdx
0x18003c985  mov     edx, 1E2h; unsigned int
0x18003c98a  cmova   rcx, [rbp+37h+var_80]
0x18003c98f  mov     [rsp+120h+var_100], rcx
0x18003c994  lea     rcx, aBricreateevent; "_BriCreateEvent2"
0x18003c99b  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003c9a0  mov     rbx, [rsp+120h+StringSid]
0x18003c9a5  test    rbx, rbx
0x18003c9a8  jz      short loc_18003C9D1
0x18003c9aa  lea     rcx, [rbx+40h]; void *
0x18003c9ae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c9b3  lea     rcx, [rbx+20h]; void *
0x18003c9b7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c9bc  mov     rcx, rbx; void *
0x18003c9bf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c9c4  mov     edx, 60h ; '`'
0x18003c9c9  mov     rcx, rbx; Block
0x18003c9cc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003c9d1  mov     esi, edi
0x18003c9d3  jmp     loc_18003CB24
0x18003c9d8  mov     r15d, 7
0x18003c9de  cmp     [rbp+37h+var_88], r15
0x18003c9e2  lea     rcx, [rbp+37h+packageFullName]
0x18003c9e6  cmova   rcx, [rbp+37h+packageFullName]; packageFullName
0x18003c9eb  call    ?IsMessagingCapableApp@CSmsRpcUtils@@SAHPEBG@Z; CSmsRpcUtils::IsMessagingCapableApp(ushort const *)
0x18003c9f0  test    eax, eax
0x18003c9f2  jnz     loc_18003C8B6
0x18003c9f8  cmp     [rbp+37h+var_88], r15
0x18003c9fc  lea     rax, [rbp+37h+packageFullName]
0x18003ca00  lea     r9, aAppnameSDoesNo; "AppName %S does not contain messaging c"...
0x18003ca07  mov     r8d, edi; int
0x18003ca0a  cmova   rax, [rbp+37h+packageFullName]
0x18003ca0f  lea     rcx, aBricreateevent; "_BriCreateEvent2"
0x18003ca16  mov     edx, 1BFh; unsigned int
0x18003ca1b  mov     [rsp+120h+var_100], rax
0x18003ca20  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003ca25  mov     esi, 5
0x18003ca2a  jmp     loc_18003CB24
0x18003ca2f  cmp     [rbp+37h+var_40], r15
0x18003ca33  lea     rcx, [rbp+37h+var_60]
0x18003ca37  mov     [rsp+120h+var_F0], r14d; int
0x18003ca3c  lea     rax, [rbp+37h+var_58]
0x18003ca40  cmova   rax, [rbp+37h+var_58]
0x18003ca45  lea     r9, [rsp+120h+var_C0]
0x18003ca4a  cmp     [rbp+37h+var_A8], r15
0x18003ca4e  lea     r8, [rbp+37h+packageFullName]
0x18003ca52  mov     [rsp+120h+var_F8], rcx; struct _WNF_STATE_NAME *
0x18003ca57  lea     rdx, [rbp+37h+var_80]
0x18003ca5b  cmova   r9, [rsp+120h+var_C0]; unsigned __int16 *
0x18003ca61  lea     rcx, ?s_instance@CSmsBrokerHandler@@0V1@A; this
0x18003ca68  cmp     [rbp+37h+var_88], r15
0x18003ca6c  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x18003ca71  cmova   r8, [rbp+37h+packageFullName]; unsigned __int16 *
  ... truncated ...
```
