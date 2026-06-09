# PromptInternal(Windows::Internal::Shell::PlatformExtensions::ICredUX *,Windows::Internal::UI::Credentials::Controller::CredUIStyle,Windows::Internal::UI::Credentials::Controller::ICredUXExtension *,Windows::Internal::UI::Credentials::Controller::IConsentUXContext *,Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt *,ulong,_CREDUI_CONTEXT const *,CREDUI_INFO_INTERNAL *,ulong,ulong *,void const *,ulong,void * *,ulong *,int *,ulong,bool *)

- ea: `0x1400111ac`
- end: `0x1400115bb`
- name: `?PromptInternal@@YAJPEAUICredUX@PlatformExtensions@Shell@Internal@Windows@@W4CredUIStyle@Controller@Credentials@UI@45@PEAUICredUXExtension@78945@PEAUIConsentUXContext@78945@PEAUICredUXSecurePrompt@78945@KPEBU_CREDUI_CONTEXT@@PEAUCREDUI_INFO_INTERNAL@@KPEAKPEBXKPEAPEAX7PEAHKPEA_N@Z`
- size: `1039`
- prototype: `__int64 __fastcall(__int64 *, int, __int64, __int64, __int64, __int64, __int64, __int64, int, unsigned int *, __int64, int, void **, unsigned int *, int *, int, _BYTE *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001096c`

## callees

- `0x140003620`
- `0x140005128`
- `0x140006f50`
- `0x140007bd8`
- `0x140009228`
- `0x14000af00`
- `0x14000bb90`
- `0x14000e920`
- `0x1400111ac`
- `0x1400136fc`
- `0x140014578`
- `0x140014ac8`
- `0x14001f010`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x14001139a`
- `KERNEL32!OpenEventW` at `0x14001139a`

## string_xrefs

- `0x14001129e`: `shellcommon\internal\shell\inc\creduxparameters.h`
- `0x1400112e9`: `shellcommon\internal\shell\inc\creduxparameters.h`
- `0x1400113da`: `shellcommon\internal\shell\inc\creduxparameters.h`
- `0x14001144d`: `shellcommon\internal\shell\inc\creduxparameters.h`
- `0x140011555`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall PromptInternal(
        __int64 *a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        int a9,
        unsigned int *a10,
        __int64 a11,
        int a12,
        void **a13,
        unsigned int *a14,
        int *a15,
        int a16,
        _BYTE *a17)
{
  struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData *v19; // r15
  __int64 v20; // rdx
  __int64 v21; // rcx
  int v22; // eax
  HANDLE v23; // rsi
  int v24; // ebx
  __int64 v25; // rbx
  int v26; // edi
  __int64 v27; // rdx
  char v28; // al
  const WCHAR *v29; // r8
  __int64 v30; // rdx
  __int64 (__fastcall *v31)(__int64 *, __int64, struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData **); // rdi
  int v32; // eax
  struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData *v33; // rdi
  struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData *v34; // rbx
  __int64 (__fastcall *v35)(struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData *, GUID *, struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData **); // rdi
  int CredentialData; // eax
  __int64 v37; // rdx
  unsigned __int64 v38; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  __int64 v41; // [rsp+50h] [rbp-B0h]
  __int64 v42; // [rsp+58h] [rbp-A8h]
  __int64 v43; // [rsp+60h] [rbp-A0h]
  char v44; // [rsp+70h] [rbp-90h] BYREF
  char v45; // [rsp+71h] [rbp-8Fh] BYREF
  char v46; // [rsp+72h] [rbp-8Eh] BYREF
  char v47[5]; // [rsp+73h] [rbp-8Dh] BYREF
  struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData *v48; // [rsp+78h] [rbp-88h] BYREF
  struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData *v49; // [rsp+80h] [rbp-80h] BYREF
  struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData *v50; // [rsp+88h] [rbp-78h] BYREF
  __int64 v51; // [rsp+90h] [rbp-70h] BYREF
  char *v52; // [rsp+98h] [rbp-68h] BYREF
  int *v53; // [rsp+A0h] [rbp-60h]
  unsigned int *v54; // [rsp+A8h] [rbp-58h]
  void **v55; // [rsp+B0h] [rbp-50h]
  _QWORD v56[42]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v19 = (struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData *)a8;
  v55 = a13;
  v54 = a14;
  *a17 = 0;
  v53 = a15;
  wil::ActivityBase<CredUXLogging,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CredUXLogging,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v56);
  v56[0] = &CredUXTelemetry::AcceptCredentialsOrCancelActivity::`vftable';
  CredUXTelemetry::AcceptCredentialsOrCancelActivity::StartActivity((CredUXTelemetry::AcceptCredentialsOrCancelActivity *)v56);
  v51 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
  v22 = CreateCredUXParams(v21, v20, a8, a9, (__int64)a10, a11, a12, a15, a16, a2, v41, v42, v43, &v51);
  v23 = 0;
  v24 = v22;
  if ( v22 >= 0 )
  {
    v25 = v51;
    v45 = 0;
    v26 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v51 + 144LL))(v51, &v45);
    if ( v26 < 0 )
    {
      v27 = 868;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v27,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
        (const char *)(unsigned int)v26,
        v40);
      v24 = v26;
      goto LABEL_44;
    }
    v46 = 0;
    v26 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v25 + 152LL))(v25, &v46);
    if ( v26 < 0 )
    {
      v27 = 871;
      goto LABEL_5;
    }
    v44 = 0;
    v26 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v25 + 184LL))(v25, &v44);
    if ( v26 < 0 )
    {
      v27 = 874;
      goto LABEL_5;
    }
    if ( !v45 || (v28 = 1, v44) )
      v28 = 0;
    v47[0] = v28;
    CredUXTelemetry::AcceptCredentialsOrCancelActivity::CredUXTypeInvoke<bool,unsigned char &,unsigned char &>(
      v47,
      &v46,
      &v44);
    if ( a8 )
    {
      v29 = *(const WCHAR **)(a8 + 88);
      v19 = 0;
      if ( v29 )
      {
        if ( *v29 )
          v23 = OpenEventW(0x100000u, 0, v29);
      }
    }
    v30 = *a1;
    v48 = v19;
    v31 = *(__int64 (__fastcall **)(__int64 *, __int64, struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData **))(v30 + 48);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
    v32 = v31(a1, v25, &v48);
    v24 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37C,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
        (const char *)(unsigned int)v32,
        v40);
LABEL_43:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
      goto LABEL_44;
    }
    v33 = v48;
    v49 = v19;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
    v24 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *>,Windows::Foundation::IAsyncOperation<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *>>(
            v33,
            24,
            v23);
    if ( v24 >= 0 )
      v24 = (*(__int64 (__fastcall **)(struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData *, struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData **))(*(_QWORD *)v33 + 64LL))(
              v33,
              &v49);
    if ( v24 == -2147023673 )
    {
      *a17 = 1;
LABEL_37:
      wil::ActivityBase<CredUXLogging,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(v56);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
      CredUXTelemetry::AcceptCredentialsOrCancelActivity::~AcceptCredentialsOrCancelActivity((CredUXTelemetry::AcceptCredentialsOrCancelActivity *)v56);
      return 0;
    }
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x386,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
        (const char *)(unsigned int)v24,
        v40);
LABEL_42:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
      goto LABEL_43;
    }
    v34 = v48;
    v50 = v19;
    v35 = **(__int64 (__fastcall ***)(struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData *, GUID *, struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData **))v48;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
    CredentialData = v35(v34, &GUID_00000036_0000_0000_c000_000000000046, &v50);
    v24 = CredentialData;
    if ( CredentialData < 0 )
    {
      v37 = 905;
LABEL_33:
      v38 = (unsigned int)CredentialData;
      goto LABEL_40;
    }
    LODWORD(v52) = (_DWORD)v19;
    CredentialData = (*(__int64 (__fastcall **)(struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData *, char **))(*(_QWORD *)v50 + 64LL))(
                       v50,
                       &v52);
    v24 = CredentialData;
    if ( CredentialData < 0 )
    {
      v37 = 907;
      goto LABEL_33;
    }
    v24 = (int)v52;
    if ( (_DWORD)v52 )
    {
      if ( (_DWORD)v52 == -2147023673 )
      {
        *a17 = 1;
        goto LABEL_36;
      }
    }
    else if ( v49 )
    {
      CredentialData = ExtractCredentialData(v49, a10, v55, v54, v53);
      v24 = CredentialData;
      if ( CredentialData < 0 )
      {
        v37 = 911;
        goto LABEL_33;
      }
LABEL_36:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
      goto LABEL_37;
    }
    if ( (int)v52 >= 0 )
    {
LABEL_41:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
      goto LABEL_42;
    }
    v38 = (unsigned int)v52;
    v37 = 919;
LABEL_40:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v37,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
      (const char *)v38,
      v40);
    goto LABEL_41;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x361,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
    (const char *)(unsigned int)v22,
    v40);
LABEL_44:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
  CredUXTelemetry::AcceptCredentialsOrCancelActivity::~AcceptCredentialsOrCancelActivity((CredUXTelemetry::AcceptCredentialsOrCancelActivity *)v56);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x1400111ac  mov     [rsp-8+arg_10], rbx
0x1400111b1  push    rbp
0x1400111b2  push    rsi
0x1400111b3  push    rdi
0x1400111b4  push    r12
0x1400111b6  push    r13
0x1400111b8  push    r14
0x1400111ba  push    r15
0x1400111bc  lea     rbp, [rsp-120h]
0x1400111c4  sub     rsp, 220h
0x1400111cb  mov     rax, cs:__security_cookie
0x1400111d2  xor     rax, rsp
0x1400111d5  mov     [rbp+150h+var_40], rax
0x1400111dc  mov     rax, [rbp+150h+arg_60]
0x1400111e3  mov     r12, rcx
0x1400111e6  mov     r14, [rbp+150h+arg_80]
0x1400111ed  lea     rcx, [rbp+150h+var_190]; struct wil::details::IFailureCallback *
0x1400111f1  mov     rsi, [rbp+150h+arg_70]
0x1400111f8  mov     edi, edx
0x1400111fa  mov     r15, [rbp+150h+arg_38]
0x140011201  mov     r13, [rbp+150h+arg_48]
0x140011208  mov     rbx, [rbp+150h+arg_50]
0x14001120f  mov     [rbp+150h+var_1A0], rax
0x140011213  mov     rax, [rbp+150h+arg_68]
0x14001121a  mov     [rbp+150h+var_1A8], rax
0x14001121e  mov     byte ptr [r14], 0
0x140011222  mov     [rbp+150h+var_1B0], rsi
0x140011226  call    ??0?$ActivityBase@VCredUXLogging@@$00$0CAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CredUXLogging,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CredUXLogging,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14001122b  lea     rax, ??_7AcceptCredentialsOrCancelActivity@CredUXTelemetry@@6B@; const CredUXTelemetry::AcceptCredentialsOrCancelActivity::`vftable'
0x140011232  lea     rcx, [rbp+150h+var_190]; this
0x140011236  mov     [rbp+150h+var_190], rax
0x14001123a  call    ?StartActivity@AcceptCredentialsOrCancelActivity@CredUXTelemetry@@QEAAXXZ; CredUXTelemetry::AcceptCredentialsOrCancelActivity::StartActivity(void)
0x14001123f  lea     rcx, [rbp+150h+var_1C0]
0x140011243  mov     [rbp+150h+var_1C0], 0
0x14001124b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140011250  mov     r9d, [rbp+150h+arg_40]
0x140011257  lea     rax, [rbp+150h+var_1C0]
0x14001125b  mov     [rsp+250h+var_1E8], rax
0x140011260  mov     r8, r15
0x140011263  mov     eax, [rbp+150h+arg_78]
0x140011269  mov     [rsp+250h+var_208], edi
0x14001126d  mov     [rsp+250h+var_210], eax
0x140011271  mov     eax, [rbp+150h+arg_58]
0x140011277  mov     [rsp+250h+var_218], rsi
0x14001127c  mov     [rsp+250h+var_220], eax
0x140011280  mov     [rsp+250h+var_228], rbx
0x140011285  mov     [rsp+250h+var_230], r13; int
0x14001128a  call    ?CreateCredUXParams@@YAJKPEBU_CREDUI_CONTEXT@@PEAUCREDUI_INFO_INTERNAL@@KPEAKPEBXKPEAHKW4CredUIStyle@Controller@Credentials@UI@Internal@Windows@@PEAUICredUXExtension@45678@PEAUIConsentUXContext@45678@PEAUICredUXSecurePrompt@45678@PEAPEAUICredUXParameters@45678@@Z; CreateCredUXParams(ulong,_CREDUI_CONTEXT const *,CREDUI_INFO_INTERNAL *,ulong,ulong *,void const *,ulong,int *,ulong,Windows::Internal::UI::Credentials::Controller::CredUIStyle,Windows::Internal::UI::Credentials::Controller::ICredUXExtension *,Windows::Internal::UI::Credentials::Controller::IConsentUXContext *,Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt *,Windows::Internal::UI::Credentials::Controller::ICredUXParameters * *)
0x14001128f  xor     esi, esi
0x140011291  mov     ebx, eax
0x140011293  test    eax, eax
0x140011295  jns     short loc_1400112B7
0x140011297  mov     rcx, [rbp+158h]; this
0x14001129e  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x1400112a5  mov     r9d, eax; char *
0x1400112a8  mov     edx, 361h; void *
0x1400112ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400112b2  jmp     loc_14001157D
0x1400112b7  mov     rbx, [rbp+150h+var_1C0]
0x1400112bb  lea     rdx, [rsp+250h+var_1DF]
0x1400112c0  mov     [rsp+250h+var_1DF], sil
0x1400112c5  mov     rcx, rbx
0x1400112c8  mov     rax, [rbx]
0x1400112cb  mov     rax, [rax+90h]
0x1400112d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400112d7  mov     edi, eax
0x1400112d9  test    eax, eax
0x1400112db  jns     short loc_1400112FF
0x1400112dd  mov     edx, 364h; void *
0x1400112e2  mov     rcx, [rbp+158h]; this
0x1400112e9  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x1400112f0  mov     r9d, edi; char *
0x1400112f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400112f8  mov     ebx, edi
0x1400112fa  jmp     loc_14001157D
0x1400112ff  mov     [rsp+250h+var_1DE], sil
0x140011304  lea     rdx, [rsp+250h+var_1DE]
0x140011309  mov     rax, [rbx]
0x14001130c  mov     rcx, rbx
0x14001130f  mov     rax, [rax+98h]
0x140011316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001131b  mov     edi, eax
0x14001131d  test    eax, eax
0x14001131f  jns     short loc_140011328
0x140011321  mov     edx, 367h
0x140011326  jmp     short loc_1400112E2
0x140011328  mov     [rsp+250h+var_1E0], sil
0x14001132d  lea     rdx, [rsp+250h+var_1E0]
0x140011332  mov     rax, [rbx]
0x140011335  mov     rcx, rbx
0x140011338  mov     rax, [rax+0B8h]
0x14001133f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011344  mov     edi, eax
0x140011346  test    eax, eax
0x140011348  jns     short loc_140011351
0x14001134a  mov     edx, 36Ah
0x14001134f  jmp     short loc_1400112E2
0x140011351  cmp     [rsp+250h+var_1DF], sil
0x140011356  jz      short loc_140011361
0x140011358  mov     al, 1
0x14001135a  cmp     [rsp+250h+var_1E0], sil
0x14001135f  jz      short loc_140011364
0x140011361  mov     al, sil
0x140011364  lea     r8, [rsp+250h+var_1E0]
0x140011369  mov     [rsp+250h+var_1DD], al
0x14001136d  lea     rdx, [rsp+250h+var_1DE]
0x140011372  lea     rcx, [rsp+250h+var_1DD]
0x140011377  call    ??$CredUXTypeInvoke@_NAEAEAEAE@AcceptCredentialsOrCancelActivity@CredUXTelemetry@@SAX$$QEA_NAEAE1@Z; CredUXTelemetry::AcceptCredentialsOrCancelActivity::CredUXTypeInvoke<bool,uchar &,uchar &>(bool &&,uchar &,uchar &)
0x14001137c  test    r15, r15
0x14001137f  jz      short loc_1400113A3
0x140011381  mov     r8, [r15+58h]; lpName
0x140011385  xor     r15d, r15d
0x140011388  test    r8, r8
0x14001138b  jz      short loc_1400113A3
0x14001138d  cmp     [r8], r15w
0x140011391  jz      short loc_1400113A3
0x140011393  xor     edx, edx; bInheritHandle
0x140011395  mov     ecx, 100000h; dwDesiredAccess
0x14001139a  call    cs:__imp_OpenEventW
0x1400113a0  mov     rsi, rax
0x1400113a3  mov     rdx, [r12]
0x1400113a7  lea     rcx, [rsp+250h+var_1D8]
0x1400113ac  mov     [rsp+250h+var_1D8], r15
0x1400113b1  mov     rdi, [rdx+30h]
0x1400113b5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400113ba  lea     r8, [rsp+250h+var_1D8]
0x1400113bf  mov     rdx, rbx
0x1400113c2  mov     rcx, r12
0x1400113c5  mov     rax, rdi
0x1400113c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400113cd  mov     ebx, eax
0x1400113cf  test    eax, eax
0x1400113d1  jns     short loc_1400113F3
0x1400113d3  mov     rcx, [rbp+158h]; this
0x1400113da  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x1400113e1  mov     r9d, eax; char *
0x1400113e4  mov     edx, 37Ch; void *
0x1400113e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400113ee  jmp     loc_140011573
0x1400113f3  mov     rdi, [rsp+250h+var_1D8]
0x1400113f8  lea     rcx, [rbp+150h+var_1D0]
0x1400113fc  mov     [rbp+150h+var_1D0], r15
0x140011400  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140011405  mov     r8, rsi
0x140011408  mov     edx, 18h
0x14001140d  mov     rcx, rdi
0x140011410  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVRequestCredentialsData@Controller@Credentials@UI@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVRequestCredentialsData@Controller@Credentials@UI@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVRequestCredentialsData@Controller@Credentials@UI@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *>,Windows::Foundation::IAsyncOperation<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *> *,tagCOWAIT_FLAGS,void *)
0x140011415  mov     ebx, eax
0x140011417  test    eax, eax
0x140011419  js      short loc_140011430
0x14001141b  mov     rax, [rdi]
0x14001141e  lea     rdx, [rbp+150h+var_1D0]
0x140011422  mov     rcx, rdi
0x140011425  mov     rax, [rax+40h]
0x140011429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001142e  mov     ebx, eax
0x140011430  mov     esi, 800704C7h
0x140011435  cmp     ebx, esi
0x140011437  jnz     short loc_140011442
0x140011439  mov     byte ptr [r14], 1
0x14001143d  jmp     loc_140011510
0x140011442  test    ebx, ebx
0x140011444  jns     short loc_140011466
0x140011446  mov     rcx, [rbp+158h]; this
0x14001144d  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x140011454  mov     r9d, ebx; char *
0x140011457  mov     edx, 386h; void *
0x14001145c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011461  jmp     loc_14001156A
0x140011466  mov     rbx, [rsp+250h+var_1D8]
0x14001146b  lea     rcx, [rbp+150h+var_1C8]
0x14001146f  mov     [rbp+150h+var_1C8], r15
0x140011473  mov     rax, [rbx]
0x140011476  mov     rdi, [rax]
0x140011479  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001147e  lea     r8, [rbp+150h+var_1C8]
0x140011482  mov     rcx, rbx
0x140011485  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x14001148c  mov     rax, rdi
0x14001148f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011494  mov     ebx, eax
0x140011496  test    eax, eax
0x140011498  jns     short loc_1400114A1
0x14001149a  mov     edx, 389h
0x14001149f  jmp     short loc_1400114FA
0x1400114a1  mov     rcx, [rbp+150h+var_1C8]
0x1400114a5  lea     rdx, [rbp+150h+var_1B8]
0x1400114a9  mov     dword ptr [rbp+150h+var_1B8], r15d
0x1400114ad  mov     rax, [rcx]
0x1400114b0  mov     rax, [rax+40h]
0x1400114b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400114b9  mov     ebx, eax
0x1400114bb  test    eax, eax
0x1400114bd  jns     short loc_1400114C6
0x1400114bf  mov     edx, 38Bh
0x1400114c4  jmp     short loc_1400114FA
0x1400114c6  mov     ebx, dword ptr [rbp+150h+var_1B8]
0x1400114c9  test    ebx, ebx
0x1400114cb  jnz     short loc_1400114FF
0x1400114cd  mov     rcx, [rbp+150h+var_1D0]; struct Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData *
0x1400114d1  test    rcx, rcx
0x1400114d4  jz      short loc_140011542
0x1400114d6  mov     rax, [rbp+150h+var_1B0]
0x1400114da  mov     rdx, r13; unsigned int *
0x1400114dd  mov     r9, [rbp+150h+var_1A8]; unsigned int *
0x1400114e1  mov     r8, [rbp+150h+var_1A0]; void **
0x1400114e5  mov     [rsp+250h+var_230], rax; int *
0x1400114ea  call    ?ExtractCredentialData@@YAJPEAUIRequestCredentialsData@Controller@Credentials@UI@Internal@Windows@@PEAKPEAPEAX1PEAH@Z; ExtractCredentialData(Windows::Internal::UI::Credentials::Controller::IRequestCredentialsData *,ulong *,void * *,ulong *,int *)
0x1400114ef  mov     ebx, eax
0x1400114f1  test    eax, eax
0x1400114f3  jns     short loc_140011507
0x1400114f5  mov     edx, 38Fh
0x1400114fa  mov     r9d, eax
0x1400114fd  jmp     short loc_14001154E
0x1400114ff  cmp     ebx, esi
0x140011501  jnz     short loc_140011542
0x140011503  mov     byte ptr [r14], 1
0x140011507  lea     rcx, [rbp+150h+var_1C8]
0x14001150b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140011510  lea     rcx, [rbp+150h+var_190]
0x140011514  call    ?Stop@?$ActivityBase@VCredUXLogging@@$00$0CAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CredUXLogging,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140011519  lea     rcx, [rbp+150h+var_1D0]
0x14001151d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140011522  lea     rcx, [rsp+250h+var_1D8]
0x140011527  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001152c  lea     rcx, [rbp+150h+var_1C0]
0x140011530  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140011535  lea     rcx, [rbp+150h+var_190]; this
0x140011539  call    ??1AcceptCredentialsOrCancelActivity@CredUXTelemetry@@QEAA@XZ; CredUXTelemetry::AcceptCredentialsOrCancelActivity::~AcceptCredentialsOrCancelActivity(void)
0x14001153e  xor     eax, eax
0x140011540  jmp     short loc_140011591
0x140011542  test    ebx, ebx
0x140011544  jns     short loc_140011561
0x140011546  mov     r9d, ebx; char *
0x140011549  mov     edx, 397h; void *
0x14001154e  mov     rcx, [rbp+158h]; this
0x140011555  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x14001155c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011561  lea     rcx, [rbp+150h+var_1C8]
0x140011565  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001156a  lea     rcx, [rbp+150h+var_1D0]
0x14001156e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140011573  lea     rcx, [rsp+250h+var_1D8]
0x140011578  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001157d  lea     rcx, [rbp+150h+var_1C0]
0x140011581  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140011586  lea     rcx, [rbp+150h+var_190]; this
0x14001158a  call    ??1AcceptCredentialsOrCancelActivity@CredUXTelemetry@@QEAA@XZ; CredUXTelemetry::AcceptCredentialsOrCancelActivity::~AcceptCredentialsOrCancelActivity(void)
0x14001158f  mov     eax, ebx
0x140011591  mov     rcx, [rbp+150h+var_40]
0x140011598  xor     rcx, rsp; StackCookie
0x14001159b  call    __security_check_cookie
0x1400115a0  mov     rbx, [rsp+250h+arg_10]
0x1400115a8  add     rsp, 220h
0x1400115af  pop     r15
0x1400115b1  pop     r14
0x1400115b3  pop     r13
0x1400115b5  pop     r12
0x1400115b7  pop     rdi
0x1400115b8  pop     rsi
0x1400115b9  pop     rbp
0x1400115ba  retn
```
