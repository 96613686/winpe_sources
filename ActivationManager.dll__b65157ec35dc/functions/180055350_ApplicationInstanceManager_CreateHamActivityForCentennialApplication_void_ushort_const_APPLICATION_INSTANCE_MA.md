# ApplicationInstanceManager::CreateHamActivityForCentennialApplication(void *,ushort const *,APPLICATION_INSTANCE_MANAGER_ACTIVITY_OPTIONS,IUnknown * *)

- ea: `0x180055350`
- end: `0x1800556da`
- name: `?CreateHamActivityForCentennialApplication@ApplicationInstanceManager@@UEAAJPEAXPEBGW4APPLICATION_INSTANCE_MANAGER_ACTIVITY_OPTIONS@@PEAPEAUIUnknown@@@Z`
- size: `906`
- prototype: `int __high(void *, const unsigned __int16 *, enum APPLICATION_INSTANCE_MANAGER_ACTIVITY_OPTIONS, struct IUnknown **)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18002c428`
- `0x180031720`
- `0x180037a80`
- `0x180038f10`
- `0x1800463dc`
- `0x18004953c`
- `0x180055350`
- `0x1800556e0`
- `0x180056208`
- `0x18005ae90`
- `0x18005ba40`
- `0x1800745e0`
- `0x1800763a8`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180055434`
- `ntdll!NtQueryInformationToken` at `0x180055434`
- `ntdll!NtQueryInformationProcess` at `0x180055485`
- `ntdll!NtQueryInformationProcess` at `0x180055485`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdFindOrCreate` at `0x180055523`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdFindOrCreate` at `0x180055523`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdInitializeKey` at `0x1800554e7`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdInitializeKey` at `0x1800554e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ApplicationInstanceManager::CreateHamActivityForCentennialApplication(
        union _RTL_RUN_ONCE *a1,
        void *a2,
        __int64 a3,
        char a4,
        _QWORD *a5)
{
  NTSTATUS v9; // eax
  __int64 v10; // rsi
  NTSTATUS v11; // eax
  unsigned int v12; // r15d
  int v13; // eax
  int v14; // eax
  unsigned int v15; // edx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rbx
  int started; // eax
  int v20; // eax
  const char *v21; // r9
  __int64 result; // rax
  int ReturnLength; // [rsp+20h] [rbp-8A8h]
  int ReturnLengtha; // [rsp+20h] [rbp-8A8h]
  int ReturnLengthb; // [rsp+20h] [rbp-8A8h]
  int ReturnLengthc; // [rsp+20h] [rbp-8A8h]
  ULONG v27; // [rsp+30h] [rbp-898h] BYREF
  unsigned int ProcessInformation; // [rsp+34h] [rbp-894h] BYREF
  __int64 v29; // [rsp+38h] [rbp-890h] BYREF
  int v30[2]; // [rsp+40h] [rbp-888h] BYREF
  union _RTL_RUN_ONCE v31; // [rsp+48h] [rbp-880h] BYREF
  _BYTE v32[400]; // [rsp+50h] [rbp-878h] BYREF
  _BYTE v33[560]; // [rsp+1E0h] [rbp-6E8h] BYREF
  _BYTE v34[1056]; // [rsp+410h] [rbp-4B8h] BYREF
  _QWORD TokenInformation[12]; // [rsp+830h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8C8h] [rbp+0h]

  try
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
        (const char *)0x80070057LL,
        ReturnLength);
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
        (const char *)0x80070057LL,
        ReturnLength);
    *a5 = 0;
    _lambda_d1bd32268257bad6c31a192902f222b7_::_lambda_d1bd32268257bad6c31a192902f222b7_(
      (_lambda_d1bd32268257bad6c31a192902f222b7_ *)v30,
      (struct ExtendedLaunchContext *)&a1[-18]);
    wil::init_once__lambda_5b1ddfb2c89310d1fe76830ba67713cf___(a1 + 20);
    memset_0(TokenInformation, 0, 0x54u);
    v27 = 84;
    v9 = NtQueryInformationToken(a2, TokenUser, TokenInformation, 0x54u, &v27);
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x8E,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
        (const char *)(unsigned int)v9,
        ReturnLengtha);
    v10 = TokenInformation[0];
    ProcessInformation = 0;
    v11 = NtQueryInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessSessionInformation, &ProcessInformation, 4u, 0);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x94,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
        (const char *)(unsigned int)v11,
        ReturnLengthb);
    v12 = ProcessInformation;
    memset_0(v34, 0, 0x418u);
    v13 = HamHostIdInitializeKey(a3, v10, v12, 0);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x99,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
        (const char *)(unsigned int)v13,
        0);
    *(_QWORD *)v30 = 0;
    v14 = HamHostIdFindOrCreate(v34, v30);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x9C,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
        (const char *)(unsigned int)v14,
        0);
    memset_0(v33, 0, 0x228u);
    CempHostInfoInitialize(a3, v10, v12, 2, *(_QWORD *)v30, v33);
    memset_0(v32, 0, 0x188u);
    v15 = ((a4 & 1) << 25) | 0x1000;
    if ( (a4 & 2) == 0 )
      v15 = (a4 & 1) << 25;
    v16 = AAMHamPopulateActivityPropertiesForActivation(L"Activation", v15, (struct _HAM_ACTIVITY_PROPERTIES *)v32);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAC,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
        (const char *)(unsigned int)v16,
        ReturnLengthc);
    v31.Ptr = a1[21].Ptr;
    v29 = 0;
    v17 = Microsoft::WRL::Details::MakeAndInitialize<AutoCloseHamActivity,AutoCloseHamActivity,void *>(&v29, &v31);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAF,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
        (const char *)(unsigned int)v17,
        ReturnLengthc);
    v18 = v29;
    started = HamActivityWrapper::StartAsync(*(_QWORD *)(v29 + 48), v33, v32, 0);
    if ( started < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0xB0,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
        (const char *)(unsigned int)started,
        ReturnLengthc);
    v20 = HamActivityWrapper::WaitForStarted(*(HamActivityWrapper **)(v18 + 48), 0x1D4C0u);
    if ( v20 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0xB1,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
        (const char *)(unsigned int)v20,
        ReturnLengthc);
    v29 = 0;
    *a5 = v18;
    wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>::~com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>(&v29);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xB6,
                           (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationin"
                                         "stancemanager.cpp",
                           v21);
  }
  return result;
}

```

## disassembly

```asm
0x180055350  mov     [rsp+arg_18], rbx
0x180055355  push    rsi
0x180055356  push    rdi
0x180055357  push    r12
0x180055359  push    r14
0x18005535b  push    r15
0x18005535d  sub     rsp, 8A0h
0x180055364  mov     rax, cs:__security_cookie
0x18005536b  xor     rax, rsp
0x18005536e  mov     [rsp+8C8h+var_38], rax
0x180055376  mov     r12d, r9d
0x180055379  mov     rbx, r8
0x18005537c  mov     rsi, rdx
0x18005537f  mov     rdi, rcx
0x180055382  mov     r14, [rsp+8C8h+arg_20]
0x18005538a  mov     rcx, [rsp+8C8h]; this
0x180055392  test    rdx, rdx
0x180055395  jnz     short loc_1800553AE
0x180055397  mov     r9d, 80070057h; char *
0x18005539d  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800553a4  mov     edx, 81h; void *
0x1800553a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800553ae  mov     rcx, [rsp+8C8h]; this
0x1800553b6  test    rbx, rbx
0x1800553b9  jnz     short loc_1800553D2
0x1800553bb  mov     r9d, 80070057h; char *
0x1800553c1  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800553c8  mov     edx, 82h; void *
0x1800553cd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800553d2  mov     qword ptr [r14], 0
0x1800553d9  lea     rdx, [rdi-90h]; struct ExtendedLaunchContext *
0x1800553e0  lea     rcx, [rsp+8C8h+var_888]; this
0x1800553e5  call    ??0_lambda_d1bd32268257bad6c31a192902f222b7_@@QEAA@PEAVExtendedLaunchContext@@@Z; _lambda_d1bd32268257bad6c31a192902f222b7_::_lambda_d1bd32268257bad6c31a192902f222b7_(ExtendedLaunchContext *)
0x1800553ea  lea     rcx, [rdi+0A0h]; lpInitOnce
0x1800553f1  mov     rdx, qword ptr [rsp+8C8h+var_888]
0x1800553f6  call    wil__init_once__lambda_5b1ddfb2c89310d1fe76830ba67713cf___
0x1800553fb  mov     r15d, 54h ; 'T'
0x180055401  mov     r8d, r15d; Size
0x180055404  xor     edx, edx; Val
0x180055406  lea     rcx, [rsp+8C8h+TokenInformation]; void *
0x18005540e  call    memset_0
0x180055413  mov     [rsp+8C8h+var_898], r15d
0x180055418  lea     rax, [rsp+8C8h+var_898]
0x18005541d  mov     [rsp+8C8h+ReturnLength], rax; int
0x180055422  mov     r9d, r15d; TokenInformationLength
0x180055425  lea     r8, [rsp+8C8h+TokenInformation]; TokenInformation
0x18005542d  lea     edx, [r15-53h]; TokenInformationClass
0x180055431  mov     rcx, rsi; TokenHandle
0x180055434  call    cs:__imp_NtQueryInformationToken
0x18005543a  mov     rcx, [rsp+8C8h]; this
0x180055442  test    eax, eax
0x180055444  jns     short loc_180055459
0x180055446  mov     r9d, eax; char *
0x180055449  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180055450  lea     edx, [r15+3Ah]; void *
0x180055454  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180055459  mov     rsi, [rsp+8C8h+TokenInformation]
0x180055461  mov     [rsp+8C8h+ProcessInformation], 0
0x180055469  mov     [rsp+8C8h+ReturnLength], 0; int
0x180055472  mov     r9d, 4; ProcessInformationLength
0x180055478  lea     r8, [rsp+8C8h+ProcessInformation]; ProcessInformation
0x18005547d  lea     edx, [r9+14h]; ProcessInformationClass
0x180055481  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180055485  call    cs:__imp_NtQueryInformationProcess
0x18005548b  mov     rcx, [rsp+8C8h]; this
0x180055493  test    eax, eax
0x180055495  jns     short loc_1800554AB
0x180055497  mov     r9d, eax; char *
0x18005549a  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800554a1  mov     edx, 94h; void *
0x1800554a6  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1800554ab  mov     r15d, [rsp+8C8h+ProcessInformation]
0x1800554b0  xor     edx, edx; Val
0x1800554b2  mov     r8d, 418h; Size
0x1800554b8  lea     rcx, [rsp+8C8h+var_4B8]; void *
0x1800554c0  call    memset_0
0x1800554c5  lea     rax, [rsp+8C8h+var_4B8]
0x1800554cd  mov     [rsp+8C8h+var_8A0], rax
0x1800554d2  mov     [rsp+8C8h+ReturnLength], 0; int
0x1800554db  xor     r9d, r9d
0x1800554de  mov     r8d, r15d
0x1800554e1  mov     rdx, rsi
0x1800554e4  mov     rcx, rbx
0x1800554e7  call    cs:__imp_HamHostIdInitializeKey
0x1800554ed  mov     rcx, [rsp+8C8h]; this
0x1800554f5  test    eax, eax
0x1800554f7  jns     short loc_18005550D
0x1800554f9  mov     r9d, eax; char *
0x1800554fc  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180055503  mov     edx, 99h; void *
0x180055508  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18005550d  mov     qword ptr [rsp+8C8h+var_888], 0
0x180055516  lea     rdx, [rsp+8C8h+var_888]
0x18005551b  lea     rcx, [rsp+8C8h+var_4B8]
0x180055523  call    cs:__imp_HamHostIdFindOrCreate
0x180055529  mov     rcx, [rsp+8C8h]; this
0x180055531  test    eax, eax
0x180055533  jns     short loc_180055549
0x180055535  mov     r9d, eax; char *
0x180055538  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18005553f  mov     edx, 9Ch; void *
0x180055544  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180055549  xor     edx, edx; Val
0x18005554b  mov     r8d, 228h; Size
0x180055551  lea     rcx, [rsp+8C8h+var_6E8]; void *
0x180055559  call    memset_0
0x18005555e  lea     rax, [rsp+8C8h+var_6E8]
0x180055566  mov     [rsp+8C8h+var_8A0], rax
0x18005556b  mov     rax, qword ptr [rsp+8C8h+var_888]
0x180055570  mov     [rsp+8C8h+ReturnLength], rax; int
0x180055575  mov     r9d, 2
0x18005557b  mov     r8d, r15d
0x18005557e  mov     rdx, rsi
0x180055581  mov     rcx, rbx
0x180055584  call    CempHostInfoInitialize
0x180055589  mov     ebx, r12d
0x18005558c  and     ebx, 1
0x18005558f  shl     ebx, 19h
0x180055592  xor     edx, edx; Val
0x180055594  mov     r8d, 188h; Size
0x18005559a  lea     rcx, [rsp+8C8h+var_878]; void *
0x18005559f  call    memset_0
0x1800555a4  mov     edx, ebx
0x1800555a6  bts     edx, 0Ch
0x1800555aa  test    r12b, 2
0x1800555ae  cmovz   edx, ebx; unsigned int
0x1800555b1  lea     r8, [rsp+8C8h+var_878]; struct _HAM_ACTIVITY_PROPERTIES *
0x1800555b6  lea     rcx, aActivation; "Activation"
0x1800555bd  call    ?AAMHamPopulateActivityPropertiesForActivation@@YAJPEBGKPEAU_HAM_ACTIVITY_PROPERTIES@@@Z; AAMHamPopulateActivityPropertiesForActivation(ushort const *,ulong,_HAM_ACTIVITY_PROPERTIES *)
0x1800555c2  mov     rcx, [rsp+8C8h]; this
0x1800555ca  test    eax, eax
0x1800555cc  jns     short loc_1800555E3
0x1800555ce  mov     r9d, eax; char *
0x1800555d1  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800555d8  mov     edx, 0ACh; void *
0x1800555dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800555e3  mov     rax, [rdi+0A8h]
0x1800555ea  mov     [rsp+8C8h+var_880], rax
0x1800555ef  mov     [rsp+8C8h+var_890], 0
0x1800555f8  lea     rdx, [rsp+8C8h+var_880]
0x1800555fd  lea     rcx, [rsp+8C8h+var_890]
0x180055602  call    ??$MakeAndInitialize@VAutoCloseHamActivity@@V1@PEAX@Details@WRL@Microsoft@@YAJPEAPEAVAutoCloseHamActivity@@$$QEAPEAX@Z; Microsoft::WRL::Details::MakeAndInitialize<AutoCloseHamActivity,AutoCloseHamActivity,void *>(AutoCloseHamActivity * *,void * &&)
0x180055607  mov     rcx, [rsp+8C8h]; this
0x18005560f  test    eax, eax
0x180055611  jns     short loc_180055627
0x180055613  mov     r9d, eax; char *
0x180055616  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18005561d  mov     edx, 0AFh; void *
0x180055622  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180055627  mov     rbx, [rsp+8C8h+var_890]
0x18005562c  xor     r9d, r9d
0x18005562f  lea     r8, [rsp+8C8h+var_878]
0x180055634  lea     rdx, [rsp+8C8h+var_6E8]
0x18005563c  mov     rcx, [rbx+30h]
0x180055640  call    ?StartAsync@HamActivityWrapper@@QEAAJPEAU_RM_PSM_HOST_INFO@@PEAU_HAM_ACTIVITY_PROPERTIES@@W4_HAM_ACTIVITY_START_TYPE@@@Z; HamActivityWrapper::StartAsync(_RM_PSM_HOST_INFO *,_HAM_ACTIVITY_PROPERTIES *,_HAM_ACTIVITY_START_TYPE)
0x180055645  mov     rcx, [rsp+8C8h]; this
0x18005564d  test    eax, eax
0x18005564f  jns     short loc_180055665
0x180055651  mov     r9d, eax; char *
0x180055654  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18005565b  mov     edx, 0B0h; void *
0x180055660  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180055665  mov     edx, 1D4C0h; unsigned int
0x18005566a  mov     rcx, [rbx+30h]; this
0x18005566e  call    ?WaitForStarted@HamActivityWrapper@@QEAAJK@Z; HamActivityWrapper::WaitForStarted(ulong)
0x180055673  mov     rcx, [rsp+8C8h]; this
0x18005567b  test    eax, eax
0x18005567d  jns     short loc_180055693
0x18005567f  mov     r9d, eax; char *
0x180055682  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180055689  mov     edx, 0B1h; void *
0x18005568e  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180055693  mov     [rsp+8C8h+var_890], 0
0x18005569c  mov     [r14], rbx
0x18005569f  lea     rcx, [rsp+8C8h+var_890]
0x1800556a4  call    ??1?$com_ptr_t@VAutoCloseHamActivity@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>::~com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>(void)
0x1800556a9  xor     eax, eax
0x1800556ab  jmp     short loc_1800556B1
0x1800556ad  mov     eax, [rsp+8C8h+var_898]
0x1800556b1  mov     rcx, [rsp+8C8h+var_38]
0x1800556b9  xor     rcx, rsp; StackCookie
0x1800556bc  call    __security_check_cookie
0x1800556c1  mov     rbx, [rsp+8C8h+arg_18]
0x1800556c9  add     rsp, 8A0h
0x1800556d0  pop     r15
0x1800556d2  pop     r14
0x1800556d4  pop     r12
0x1800556d6  pop     rdi
0x1800556d7  pop     rsi
0x1800556d8  retn
```
