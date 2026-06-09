# BipTaskClsidActivateWorker(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1800536bc`
- end: `0x180053a2c`
- name: `?BipTaskClsidActivateWorker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `880`
- prototype: `void(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180075404`

## callees

- `0x180034dbc`
- `0x18004305c`
- `0x180053100`
- `0x1800534f8`
- `0x1800536bc`
- `0x180053a34`
- `0x18006d364`
- `0x18007078c`
- `0x1800708c8`
- `0x1800946a0`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800537bb`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800537bb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800539fe`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800539fe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800538d7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800538d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053895`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005388b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005388b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800539a6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800539a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800539f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800539f3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18005381d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18005381d`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18005384c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18005384c`

## pseudocode

```c
void __fastcall BipTaskClsidActivateWorker(struct _TP_CALLBACK_INSTANCE *a1, char *a2, struct _TP_WORK *a3)
{
  __int64 *v3; // rcx
  __int64 v5; // rax
  struct Windows::ApplicationModel::Background::IBackgroundTaskInstance *v6; // rdi
  char v7; // r15
  char v8; // r12
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // ebx
  char v13; // r14
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  int v18; // ebx
  void *v19; // rcx
  signed int LastError; // eax
  signed int v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // r9
  void *phToken; // [rsp+40h] [rbp-29h] BYREF
  struct Windows::ApplicationModel::Background::IBackgroundTaskInstance *v26; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int64 v27; // [rsp+50h] [rbp-19h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-11h] BYREF
  struct _GUID *v29; // [rsp+60h] [rbp-9h] BYREF
  struct _GUID *v30; // [rsp+68h] [rbp-1h] BYREF
  struct _GUID *v31; // [rsp+70h] [rbp+7h] BYREF
  struct _GUID v32; // [rsp+78h] [rbp+Fh] BYREF
  struct _GUID v33; // [rsp+88h] [rbp+1Fh] BYREF

  v3 = (__int64 *)*((_QWORD *)a2 + 5);
  phToken = 0;
  v33 = 0;
  ppv = 0;
  v32 = 0;
  v5 = *v3;
  v6 = 0;
  v27 = 0;
  v26 = 0;
  v7 = 0;
  v8 = 0;
  (*(void (__fastcall **)(__int64 *, struct _GUID *, struct _TP_WORK *))(v5 + 32))(v3, &v33, a3);
  (*(void (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)a2 + 5) + 24LL))(*((_QWORD *)a2 + 5), &v32);
  if ( (unsigned int)dword_1800C3098 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 2, v9) )
  {
    v30 = 0;
    v31 = &v32;
    v29 = &v33;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
      (__int64)&dword_1800C3098,
      (unsigned __int8 *)&dword_1800AE66C,
      v10,
      v11,
      (const unsigned __int16 **)&v30,
      (__int64 *)&v29,
      (__int64 *)&v31);
  }
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a2 + 5) + 112LL))(*((_QWORD *)a2 + 5), 0);
  v12 = CoInitializeEx(0, 0);
  if ( v12 < 0 )
  {
    v13 = 0;
    v14 = 1000;
    goto LABEL_33;
  }
  v13 = 1;
  v12 = BipTaskActResolveUserContextIds((struct _BI_ACTIVATION_CALLBACK_CONTEXT *)a2, &v27);
  if ( v12 < 0 )
  {
    v14 = 1500;
    goto LABEL_33;
  }
  if ( !(unsigned __int8)IsUMgrQueryUserContextFromSidPresent() && !(unsigned __int8)IsWTSQueryUserTokenPresent() )
    MicrosoftTelemetryAssertTriggeredNoArgs(v16, v15, v17);
  if ( (unsigned __int8)IsUMgrQueryUserContextFromSidPresent() )
  {
    v18 = UMgrQueryUserToken(v27, &phToken);
    if ( v18 < 0 )
      goto LABEL_16;
    v19 = phToken;
  }
  else
  {
    v19 = 0;
    phToken = 0;
    v18 = 0;
  }
  if ( v19 )
    goto LABEL_23;
LABEL_16:
  if ( (unsigned __int8)IsWTSQueryUserTokenPresent() )
  {
    if ( !WTSQueryUserToken(*((_DWORD *)a2 + 18), &phToken) )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      v14 = 2000;
      goto LABEL_33;
    }
  }
  else if ( v18 < 0 )
  {
LABEL_32:
    v12 = -2147023587;
    v14 = 3000;
    goto LABEL_33;
  }
  v19 = phToken;
  if ( !phToken )
    goto LABEL_32;
LABEL_23:
  if ( ImpersonateLoggedOnUser(v19) )
  {
    v7 = 1;
    v12 = CoCreateInstance((const IID *const)(a2 + 212), 0, 0x110004u, &GUID_7d13d534_fd12_43ce_8c22_ea1ff13c06df, &ppv);
    if ( v12 >= 0 )
    {
      v22 = BipTaskClsidCreateClientTaskInstance(
              &v26,
              &v33,
              &v32,
              *((struct IBackgroundWorkItemInstanceRemote **)a2 + 4));
      v6 = v26;
      v12 = v22;
      if ( v22 >= 0 )
      {
        v12 = (*(__int64 (__fastcall **)(LPVOID, struct Windows::ApplicationModel::Background::IBackgroundTaskInstance *))(*(_QWORD *)ppv + 48LL))(
                ppv,
                v26);
        v14 = 0;
        v8 = 1;
      }
      else
      {
        v14 = 7000;
      }
    }
    else
    {
      v14 = 5000;
    }
  }
  else
  {
    v21 = GetLastError();
    v12 = v21;
    if ( v21 > 0 )
      v12 = (unsigned __int16)v21 | 0x80070000;
    v14 = 4000;
  }
LABEL_33:
  if ( (unsigned int)dword_1800C3098 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 2, v14) )
  {
    LODWORD(v27) = v14;
    v30 = &v32;
    LODWORD(v26) = v12;
    v29 = &v33;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      v23,
      (unsigned __int8 *)&word_1800AE30E,
      v14,
      v24,
      (__int64)&v26,
      (__int64 *)&v29,
      (__int64 *)&v30,
      (__int64)&v27);
  }
  if ( v7 )
    RevertToSelf();
  LOBYTE(v14) = v8;
  (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)a2 + 5) + 80LL))(
    *((_QWORD *)a2 + 5),
    (unsigned int)v12,
    v14);
  if ( v6 )
    (*(void (__fastcall **)(struct Windows::ApplicationModel::Background::IBackgroundTaskInstance *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( phToken )
    CloseHandle(phToken);
  if ( v13 )
    CoUninitialize();
}

```

## disassembly

```asm
0x1800536bc  mov     [rsp-8+arg_0], rbx
0x1800536c1  mov     [rsp-8+arg_10], rsi
0x1800536c6  push    rbp
0x1800536c7  push    rdi
0x1800536c8  push    r12
0x1800536ca  push    r14
0x1800536cc  push    r15
0x1800536ce  lea     rbp, [rsp-37h]
0x1800536d3  sub     rsp, 0A0h
0x1800536da  mov     rax, cs:__security_cookie
0x1800536e1  xor     rax, rsp
0x1800536e4  mov     [rbp+57h+var_28], rax
0x1800536e8  mov     rcx, [rdx+28h]
0x1800536ec  xorps   xmm0, xmm0
0x1800536ef  xorps   xmm1, xmm1
0x1800536f2  mov     [rbp+57h+phToken], 0
0x1800536fa  movups  xmmword ptr [rbp+57h+var_38.Data1], xmm0
0x1800536fe  mov     [rbp+57h+var_68], 0
0x180053706  mov     rsi, rdx
0x180053709  movups  xmmword ptr [rbp+57h+var_48.Data1], xmm1
0x18005370d  mov     rax, [rcx]
0x180053710  lea     rdx, [rbp+57h+var_38]
0x180053714  xor     edi, edi
0x180053716  mov     [rbp+57h+var_70], 0
0x18005371e  mov     [rbp+57h+var_78], rdi
0x180053722  xor     r15b, r15b
0x180053725  xor     r12b, r12b
0x180053728  mov     rax, [rax+20h]
0x18005372c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053731  mov     rcx, [rsi+28h]
0x180053735  lea     rdx, [rbp+57h+var_48]
0x180053739  mov     rax, [rcx]
0x18005373c  mov     rax, [rax+18h]
0x180053740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053745  mov     eax, cs:dword_1800C3098
0x18005374b  cmp     eax, 5
0x18005374e  jbe     short loc_1800537A5
0x180053750  lea     edx, [rdi+2]
0x180053753  lea     rcx, dword_1800C3098
0x18005375a  call    _tlgKeywordOn
0x18005375f  test    al, al
0x180053761  jz      short loc_1800537A5
0x180053763  lea     rax, [rbp+57h+var_48]
0x180053767  mov     [rbp+57h+var_58], rdi
0x18005376b  mov     [rbp+57h+var_50], rax
0x18005376f  lea     rdx, dword_1800AE66C
0x180053776  lea     rax, [rbp+57h+var_38]
0x18005377a  mov     [rbp+57h+var_60], rax
0x18005377e  lea     rcx, dword_1800C3098
0x180053785  lea     rax, [rbp+57h+var_50]
0x180053789  mov     [rsp+0C0h+var_90], rax
0x18005378e  lea     rax, [rbp+57h+var_60]
0x180053792  mov     [rsp+0C0h+var_98], rax
0x180053797  lea     rax, [rbp+57h+var_58]
0x18005379b  mov     [rsp+0C0h+ppv], rax
0x1800537a0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &)
0x1800537a5  mov     rcx, [rsi+28h]
0x1800537a9  xor     edx, edx
0x1800537ab  mov     rax, [rcx]
0x1800537ae  mov     rax, [rax+70h]
0x1800537b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800537b7  xor     edx, edx; dwCoInit
0x1800537b9  xor     ecx, ecx; pvReserved
0x1800537bb  call    cs:__imp_CoInitializeEx
0x1800537c1  mov     ebx, eax
0x1800537c3  test    eax, eax
0x1800537c5  jns     short loc_1800537D5
0x1800537c7  xor     r14b, r14b
0x1800537ca  mov     r8d, 3E8h
0x1800537d0  jmp     loc_18005393A
0x1800537d5  lea     rdx, [rbp+57h+var_70]; unsigned __int64 *
0x1800537d9  mov     rcx, rsi; struct _BI_ACTIVATION_CALLBACK_CONTEXT *
0x1800537dc  mov     r14b, 1
0x1800537df  call    ?BipTaskActResolveUserContextIds@@YAJPEAU_BI_ACTIVATION_CALLBACK_CONTEXT@@PEA_K@Z; BipTaskActResolveUserContextIds(_BI_ACTIVATION_CALLBACK_CONTEXT *,unsigned __int64 *)
0x1800537e4  mov     ebx, eax
0x1800537e6  test    eax, eax
0x1800537e8  jns     short loc_1800537F5
0x1800537ea  mov     r8d, 5DCh
0x1800537f0  jmp     loc_18005393A
0x1800537f5  call    IsUMgrQueryUserContextFromSidPresent
0x1800537fa  test    al, al
0x1800537fc  jnz     short loc_18005380C
0x1800537fe  call    IsWTSQueryUserTokenPresent
0x180053803  test    al, al
0x180053805  jnz     short loc_18005380C
0x180053807  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005380c  call    IsUMgrQueryUserContextFromSidPresent
0x180053811  test    al, al
0x180053813  jz      short loc_18005382F
0x180053815  mov     rcx, [rbp+57h+var_70]
0x180053819  lea     rdx, [rbp+57h+phToken]
0x18005381d  call    cs:__imp_UMgrQueryUserToken
0x180053823  mov     ebx, eax
0x180053825  test    eax, eax
0x180053827  js      short loc_18005383C
0x180053829  mov     rcx, [rbp+57h+phToken]
0x18005382d  jmp     short loc_180053837
0x18005382f  xor     ecx, ecx
0x180053831  mov     [rbp+57h+phToken], rcx
0x180053835  xor     ebx, ebx
0x180053837  test    rcx, rcx
0x18005383a  jnz     short loc_18005388B
0x18005383c  call    IsWTSQueryUserTokenPresent
0x180053841  test    al, al
0x180053843  jz      short loc_180053876
0x180053845  mov     ecx, [rsi+48h]; SessionId
0x180053848  lea     rdx, [rbp+57h+phToken]; phToken
0x18005384c  call    cs:__imp_WTSQueryUserToken
0x180053852  test    eax, eax
0x180053854  jnz     short loc_18005387E
0x180053856  call    cs:__imp_GetLastError
0x18005385c  mov     ebx, eax
0x18005385e  test    eax, eax
0x180053860  jle     short loc_18005386B
0x180053862  movzx   ebx, ax
0x180053865  or      ebx, 80070000h
0x18005386b  mov     r8d, 7D0h
0x180053871  jmp     loc_18005393A
0x180053876  test    ebx, ebx
0x180053878  js      loc_18005392F
0x18005387e  mov     rcx, [rbp+57h+phToken]; hToken
0x180053882  test    rcx, rcx
0x180053885  jz      loc_18005392F
0x18005388b  call    cs:__imp_ImpersonateLoggedOnUser
0x180053891  test    eax, eax
0x180053893  jnz     short loc_1800538B5
0x180053895  call    cs:__imp_GetLastError
0x18005389b  mov     ebx, eax
0x18005389d  test    eax, eax
0x18005389f  jle     short loc_1800538AA
0x1800538a1  movzx   ebx, ax
0x1800538a4  or      ebx, 80070000h
0x1800538aa  mov     r8d, 0FA0h
0x1800538b0  jmp     loc_18005393A
0x1800538b5  lea     rax, [rbp+57h+var_68]
0x1800538b9  xor     edx, edx; pUnkOuter
0x1800538bb  lea     rcx, [rsi+0D4h]; rclsid
0x1800538c2  mov     [rsp+0C0h+ppv], rax; ppv
0x1800538c7  lea     r9, _GUID_7d13d534_fd12_43ce_8c22_ea1ff13c06df; riid
0x1800538ce  mov     r8d, 110004h; dwClsContext
0x1800538d4  mov     r15b, r14b
0x1800538d7  call    cs:__imp_CoCreateInstance
0x1800538dd  mov     ebx, eax
0x1800538df  test    eax, eax
0x1800538e1  jns     short loc_1800538EB
0x1800538e3  mov     r8d, 1388h
0x1800538e9  jmp     short loc_18005393A
0x1800538eb  mov     r9, [rsi+20h]; struct IBackgroundWorkItemInstanceRemote *
0x1800538ef  lea     r8, [rbp+57h+var_48]; struct _GUID *
0x1800538f3  lea     rdx, [rbp+57h+var_38]; struct _GUID *
0x1800538f7  lea     rcx, [rbp+57h+var_78]; struct Windows::ApplicationModel::Background::IBackgroundTaskInstance **
0x1800538fb  call    ?BipTaskClsidCreateClientTaskInstance@@YAJPEAPEAUIBackgroundTaskInstance@Background@ApplicationModel@Windows@@PEBU_GUID@@1PEAUIBackgroundWorkItemInstanceRemote@@@Z; BipTaskClsidCreateClientTaskInstance(Windows::ApplicationModel::Background::IBackgroundTaskInstance * *,_GUID const *,_GUID const *,IBackgroundWorkItemInstanceRemote *)
0x180053900  mov     rdi, [rbp+57h+var_78]
0x180053904  mov     ebx, eax
0x180053906  test    eax, eax
0x180053908  jns     short loc_180053912
0x18005390a  mov     r8d, 1B58h
0x180053910  jmp     short loc_18005393A
0x180053912  mov     rcx, [rbp+57h+var_68]
0x180053916  mov     rdx, rdi
0x180053919  mov     rax, [rcx]
0x18005391c  mov     rax, [rax+30h]
0x180053920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053925  mov     ebx, eax
0x180053927  xor     r8d, r8d
0x18005392a  mov     r12b, r14b
0x18005392d  jmp     short loc_18005393A
0x18005392f  mov     ebx, 8007051Dh
0x180053934  mov     r8d, 0BB8h
0x18005393a  mov     eax, cs:dword_1800C3098
0x180053940  cmp     eax, 5
0x180053943  jbe     short loc_1800539A1
0x180053945  mov     edx, 2
0x18005394a  lea     rcx, dword_1800C3098
0x180053951  call    _tlgKeywordOn
0x180053956  test    al, al
0x180053958  jz      short loc_1800539A1
0x18005395a  lea     rax, [rbp+57h+var_48]
0x18005395e  mov     dword ptr [rbp+57h+var_70], r8d
0x180053962  mov     [rbp+57h+var_58], rax
0x180053966  lea     rdx, word_1800AE30E
0x18005396d  lea     rax, [rbp+57h+var_38]
0x180053971  mov     dword ptr [rbp+57h+var_78], ebx
0x180053974  mov     [rbp+57h+var_60], rax
0x180053978  lea     rax, [rbp+57h+var_70]
0x18005397c  mov     [rsp+0C0h+var_88], rax
0x180053981  lea     rax, [rbp+57h+var_58]
0x180053985  mov     [rsp+0C0h+var_90], rax
0x18005398a  lea     rax, [rbp+57h+var_60]
0x18005398e  mov     [rsp+0C0h+var_98], rax
0x180053993  lea     rax, [rbp+57h+var_78]
0x180053997  mov     [rsp+0C0h+ppv], rax
0x18005399c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800539a1  test    r15b, r15b
0x1800539a4  jz      short loc_1800539AC
0x1800539a6  call    cs:__imp_RevertToSelf
0x1800539ac  mov     rcx, [rsi+28h]
0x1800539b0  mov     r8b, r12b
0x1800539b3  mov     edx, ebx
0x1800539b5  mov     rax, [rcx]
0x1800539b8  mov     rax, [rax+50h]
0x1800539bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800539c1  test    rdi, rdi
0x1800539c4  jz      short loc_1800539D5
0x1800539c6  mov     rax, [rdi]
0x1800539c9  mov     rcx, rdi
0x1800539cc  mov     rax, [rax+10h]
0x1800539d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800539d5  mov     rcx, [rbp+57h+var_68]
0x1800539d9  test    rcx, rcx
0x1800539dc  jz      short loc_1800539EA
0x1800539de  mov     rax, [rcx]
0x1800539e1  mov     rax, [rax+10h]
0x1800539e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800539ea  mov     rcx, [rbp+57h+phToken]; hObject
0x1800539ee  test    rcx, rcx
0x1800539f1  jz      short loc_1800539F9
0x1800539f3  call    cs:__imp_CloseHandle
0x1800539f9  test    r14b, r14b
0x1800539fc  jz      short loc_180053A04
0x1800539fe  call    cs:__imp_CoUninitialize
0x180053a04  mov     rcx, [rbp+57h+var_28]
0x180053a08  xor     rcx, rsp; StackCookie
0x180053a0b  call    __security_check_cookie
0x180053a10  lea     r11, [rsp+0C0h+var_20]
0x180053a18  mov     rbx, [r11+30h]
0x180053a1c  mov     rsi, [r11+40h]
0x180053a20  mov     rsp, r11
0x180053a23  pop     r15
0x180053a25  pop     r14
0x180053a27  pop     r12
0x180053a29  pop     rdi
0x180053a2a  pop     rbp
0x180053a2b  retn
```
