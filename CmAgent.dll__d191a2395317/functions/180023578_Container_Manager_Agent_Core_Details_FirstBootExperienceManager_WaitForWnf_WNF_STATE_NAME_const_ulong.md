# Container::Manager::Agent::Core::Details::FirstBootExperienceManager::WaitForWnf(_WNF_STATE_NAME const &,ulong &)

- ea: `0x180023578`
- end: `0x180023779`
- name: `?WaitForWnf@FirstBootExperienceManager@Details@Core@Agent@Manager@Container@@AEAAJAEBU_WNF_STATE_NAME@@AEAK@Z`
- size: `513`
- prototype: `__int64 __fastcall(Container::Manager::Agent::Core::Details::FirstBootExperienceManager *__hidden this, const struct _WNF_STATE_NAME *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180023090`

## callees

- `0x1800045e4`
- `0x18000a768`
- `0x180011ea4`
- `0x180022cf4`
- `0x180023578`

## import_xrefs

- `ntdll!NtQueryWnfStateData` at `0x1800235c1`
- `ntdll!NtQueryWnfStateData` at `0x1800235c1`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800236aa`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800236aa`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800236e1`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180023735`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800236e1`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180023735`

## string_xrefs

- `0x180023603`: `onecore\base\gendrv\silos\clem\agent\core\lib\firstbootexperience.cpp`
- `0x1800236be`: `onecore\base\gendrv\silos\clem\agent\core\lib\firstbootexperience.cpp`
- `0x180023765`: `onecore\base\gendrv\silos\clem\agent\core\lib\firstbootexperience.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Agent::Core::Details::FirstBootExperienceManager::WaitForWnf(
        Container::Manager::Agent::Core::Details::FirstBootExperienceManager *this,
        const struct _WNF_STATE_NAME *a2,
        unsigned int *a3)
{
  unsigned int v6; // ebx
  char v8; // bl
  bool v9; // al
  __int64 v10; // r8
  struct _WNF_STATE_NAME v11; // rdx
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rdx
  int v15; // [rsp+20h] [rbp-30h]
  const char *v16; // [rsp+30h] [rbp-20h]
  _DWORD v17[4]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 v19; // [rsp+88h] [rbp+38h] BYREF

  v17[0] = 0;
  LODWORD(v19) = 0;
  v6 = NtQueryWnfStateData(a2, 0, 0, &v19, 0, v17) | 0x10000000;
  if ( (int)(v6 + 0x80000000) >= 0 && v6 != -805306333 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2AA,
      (int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)v6);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17A,
      (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\firstbootexperience.cpp",
      (const char *)v6);
    return v6;
  }
  v8 = 1;
  v9 = (_DWORD)v19 && v17[0];
  LOBYTE(v15) = v9;
  wil::details::in1diag3::Log_HrIfMsg(
    retaddr,
    (void *)0x2AC,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
    (const char *)0x8000FFFFLL,
    v15,
    (bool)"Inconsistent state data size in wnf_query",
    v16);
  v10 = (unsigned int)v19;
  if ( !(_DWORD)v19 || v17[0] )
    v8 = 0;
  if ( !v8 )
  {
    v11 = *a2;
    v19 = 0;
    v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))RtlSubscribeWnfStateChangeNotification)(
            &v19,
            v11,
            v10,
            Container::Manager::Agent::Core::Details::FirstBootExperienceManager::WnfCallback,
            this,
            0,
            0,
            0);
    if ( v12 < 0 )
    {
      v6 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x189,
             (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\firstbootexperience.cpp",
             (const char *)(unsigned int)v12);
      goto LABEL_15;
    }
    if ( *a2 == WNF_SHEL_OOBE_USER_LOGON_COMPLETE )
    {
      v13 = 24;
    }
    else
    {
      if ( *a2 != WNF_SHEL_LOGON_COMPLETE )
      {
        v6 = -2147467259;
        v14 = 407;
        goto LABEL_27;
      }
      v13 = 28;
    }
    v6 = Container::Manager::Agent::Core::Details::WaitOnEventAndUpdateTimeout<wil::slim_event_t<1>>(
           (char *)this + v13,
           a3);
    if ( (v6 & 0x80000000) != 0 )
    {
      v14 = 411;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\firstbootexperience.cpp",
        (const char *)v6);
LABEL_15:
      if ( v19 )
        RtlUnsubscribeWnfStateChangeNotification();
      return v6;
    }
    if ( v19 )
      RtlUnsubscribeWnfStateChangeNotification();
  }
  return 0;
}

```

## disassembly

```asm
0x180023578  mov     r11, rsp
0x18002357b  mov     [r11+8], rbx
0x18002357f  mov     [r11+10h], rsi
0x180023583  push    rbp
0x180023584  push    rdi
0x180023585  push    r14
0x180023587  mov     rbp, rsp
0x18002358a  sub     rsp, 50h
0x18002358e  mov     rdi, rdx
0x180023591  mov     [rbp+var_10], 0
0x180023598  lea     rax, [rbp+var_10]
0x18002359c  mov     dword ptr [rbp+arg_18], 0
0x1800235a3  mov     r14, r8
0x1800235a6  mov     [r11-40h], rax
0x1800235aa  mov     rsi, rcx
0x1800235ad  mov     qword ptr [r11-48h], 0
0x1800235b5  mov     rcx, rdi
0x1800235b8  lea     r9, [rbp+arg_18]
0x1800235bc  xor     r8d, r8d
0x1800235bf  xor     edx, edx
0x1800235c1  call    cs:__imp_NtQueryWnfStateData
0x1800235c8  nop     dword ptr [rax+rax+00h]
0x1800235cd  mov     ebx, eax
0x1800235cf  mov     ecx, 80000000h
0x1800235d4  bts     ebx, 1Ch
0x1800235d8  lea     eax, [rbx+rcx]
0x1800235db  test    ecx, eax
0x1800235dd  jnz     short loc_18002361E
0x1800235df  cmp     ebx, 0D0000023h
0x1800235e5  jz      short loc_18002361E
0x1800235e7  mov     rcx, [rbp+18h]; this
0x1800235eb  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x1800235f2  mov     r9d, ebx; char *
0x1800235f5  mov     edx, 2AAh; void *
0x1800235fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800235ff  mov     rcx, [rbp+18h]; this
0x180023603  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18002360a  mov     r9d, ebx; char *
0x18002360d  mov     edx, 17Ah; void *
0x180023612  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023617  mov     eax, ebx
0x180023619  jmp     loc_180023743
0x18002361e  cmp     dword ptr [rbp+arg_18], 0
0x180023622  mov     bl, 1
0x180023624  jz      short loc_180023630
0x180023626  cmp     [rbp+var_10], 0
0x18002362a  jz      short loc_180023630
0x18002362c  mov     al, bl
0x18002362e  jmp     short loc_180023632
0x180023630  xor     eax, eax
0x180023632  mov     rcx, [rbp+18h]; this
0x180023636  lea     rdx, aInconsistentSt; "Inconsistent state data size in wnf_que"...
0x18002363d  mov     qword ptr [rsp+50h+var_28], rdx; bool
0x180023642  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x180023649  mov     edx, 2ACh; void *
0x18002364e  mov     byte ptr [rsp+50h+var_30], al; int
0x180023652  mov     r9d, 8000FFFFh; char *
0x180023658  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18002365d  mov     r8d, dword ptr [rbp+arg_18]
0x180023661  test    r8d, r8d
0x180023664  jz      short loc_18002366C
0x180023666  cmp     [rbp+var_10], 0
0x18002366a  jz      short loc_18002366E
0x18002366c  xor     bl, bl
0x18002366e  test    bl, bl
0x180023670  jnz     loc_180023741
0x180023676  mov     rdx, [rdi]
0x180023679  lea     r9, ?WnfCallback@FirstBootExperienceManager@Details@Core@Agent@Manager@Container@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; Container::Manager::Agent::Core::Details::FirstBootExperienceManager::WnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180023680  mov     [rsp+50h+var_18], 0
0x180023688  lea     rcx, [rbp+arg_18]
0x18002368c  mov     dword ptr [rsp+50h+var_20], 0
0x180023694  mov     qword ptr [rsp+50h+var_28], 0
0x18002369d  mov     qword ptr [rsp+50h+var_30], rsi; int
0x1800236a2  mov     [rbp+arg_18], 0
0x1800236aa  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800236b1  nop     dword ptr [rax+rax+00h]
0x1800236b6  test    eax, eax
0x1800236b8  jns     short loc_1800236F2
0x1800236ba  mov     rcx, [rbp+18h]; this
0x1800236be  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x1800236c5  mov     r9d, eax; char *
0x1800236c8  mov     edx, 189h; void *
0x1800236cd  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800236d2  mov     ebx, eax
0x1800236d4  mov     rcx, [rbp+arg_18]
0x1800236d8  test    rcx, rcx
0x1800236db  jz      loc_180023617
0x1800236e1  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x1800236e8  nop     dword ptr [rax+rax+00h]
0x1800236ed  jmp     loc_180023617
0x1800236f2  mov     rax, [rdi]
0x1800236f5  cmp     rax, qword ptr cs:WNF_SHEL_OOBE_USER_LOGON_COMPLETE.Data
0x1800236fc  jnz     short loc_180023705
0x1800236fe  mov     eax, 18h
0x180023703  jmp     short loc_180023713
0x180023705  cmp     rax, qword ptr cs:WNF_SHEL_LOGON_COMPLETE.Data
0x18002370c  jnz     short loc_180023757
0x18002370e  mov     eax, 1Ch
0x180023713  lea     rcx, [rax+rsi]; Address
0x180023717  mov     rdx, r14
0x18002371a  call    ??$WaitOnEventAndUpdateTimeout@V?$slim_event_t@$00@wil@@@Details@Core@Agent@Manager@Container@@YAJAEAV?$slim_event_t@$00@wil@@AEAK@Z; Container::Manager::Agent::Core::Details::WaitOnEventAndUpdateTimeout<wil::slim_event_t<1>>(wil::slim_event_t<1> &,ulong &)
0x18002371f  mov     ebx, eax
0x180023721  test    eax, eax
0x180023723  jns     short loc_18002372C
0x180023725  mov     edx, 19Bh
0x18002372a  jmp     short loc_180023761
0x18002372c  mov     rcx, [rbp+arg_18]
0x180023730  test    rcx, rcx
0x180023733  jz      short loc_180023741
0x180023735  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x18002373c  nop     dword ptr [rax+rax+00h]
0x180023741  xor     eax, eax
0x180023743  mov     rbx, [rsp+50h+arg_0]
0x180023748  mov     rsi, [rsp+50h+arg_8]
0x18002374d  add     rsp, 50h
0x180023751  pop     r14
0x180023753  pop     rdi
0x180023754  pop     rbp
0x180023755  retn
0x180023757  mov     ebx, 80004005h
0x18002375c  mov     edx, 197h; void *
0x180023761  mov     rcx, [rbp+18h]; this
0x180023765  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18002376c  mov     r9d, ebx; char *
0x18002376f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023774  jmp     loc_1800236D4
```
