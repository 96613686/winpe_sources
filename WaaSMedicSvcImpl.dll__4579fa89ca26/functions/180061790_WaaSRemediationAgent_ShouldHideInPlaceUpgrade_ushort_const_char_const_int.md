# WaaSRemediationAgent::ShouldHideInPlaceUpgrade(ushort const *,char const *,int *)

- ea: `0x180061790`
- end: `0x180061cf6`
- name: `?ShouldHideInPlaceUpgrade@WaaSRemediationAgent@@UEAAJPEBGPEBDPEAH@Z`
- size: `1382`
- prototype: `int(WaaSRemediationAgent *__hidden this, const unsigned __int16 *, const char *, int *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800050a0`
- `0x1800098f0`
- `0x180009cd0`
- `0x1800124c4`
- `0x180020d88`
- `0x1800268f4`
- `0x1800288a0`
- `0x18002d108`
- `0x18002e81c`
- `0x180061440`
- `0x180061790`
- `0x1800694dc`
- `0x1800697e8`
- `0x18006a240`
- `0x18006f010`

## string_xrefs

- `0x180061861`: `onecore\enduser\waasmedic\servicelib\waasremediationagent.cpp`
- `0x18006194b`: `onecore\enduser\waasmedic\servicelib\waasremediationagent.cpp`
- `0x1800619b0`: `onecore\enduser\waasmedic\servicelib\waasremediationagent.cpp`
- `0x180061a38`: `onecore\enduser\waasmedic\servicelib\waasremediationagent.cpp`
- `0x180061b1a`: `onecore\enduser\waasmedic\servicelib\waasremediationagent.cpp`
- `0x180061c25`: `onecore\enduser\waasmedic\servicelib\waasremediationagent.cpp`
- `0x180061c8e`: `onecore\enduser\waasmedic\servicelib\waasremediationagent.cpp`
- `0x1800619a1`: `'ShouldHideInPlaceUpgrade' Failed to get the User In-Place Upgrade registry value.`
- `0x180061a29`: `'ShouldHideInPlaceUpgrade' Unable to create instance of state provider.`
- `0x180061b6f`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WaaSRemediationAgent::ShouldHideInPlaceUpgrade(
        WaaSRemediationAgent *this,
        const unsigned __int16 *a2,
        const char *a3,
        int *a4)
{
  bool *v7; // rdx
  __int64 v8; // r8
  void **v9; // r9
  int IsProcessAdmin; // ebx
  const wchar_t *v12; // r8
  char v13; // bl
  struct WaasMedic::SettingsProvider *v14; // rdi
  __int64 (__fastcall *v15)(struct WaasMedic::SettingsProvider *, _OWORD *, _OWORD *, _DWORD *); // rbx
  __int64 v16; // rcx
  int v17; // eax
  char v18; // cl
  char *v19; // [rsp+28h] [rbp-71h]
  char v20; // [rsp+30h] [rbp-69h] BYREF
  bool v21; // [rsp+31h] [rbp-68h] BYREF
  __int128 v22; // [rsp+38h] [rbp-61h] BYREF
  __int64 v23; // [rsp+48h] [rbp-51h]
  unsigned int v24; // [rsp+50h] [rbp-49h] BYREF
  struct WaasMedic::SettingsProvider *v25; // [rsp+58h] [rbp-41h] BYREF
  _DWORD v26[2]; // [rsp+60h] [rbp-39h] BYREF
  char v27; // [rsp+68h] [rbp-31h]
  _BYTE v28[8]; // [rsp+70h] [rbp-29h] BYREF
  _OWORD v29[2]; // [rsp+78h] [rbp-21h] BYREF
  _OWORD v30[2]; // [rsp+98h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v20 = 0;
  v23 = 0;
  v22 = 0;
  v21 = 0;
  v25 = 0;
  v27 = 0;
  v26[0] = 3;
  v26[1] = 2;
  v24 = 0;
  LogLevelW(4u, L"'ShouldHideInPlaceUpgrade' called by '%s'", a2);
  if ( !a4 )
  {
    if ( *((_QWORD *)&v22 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v22 + 1) + 16LL))(*((_QWORD *)&v22 + 1));
    if ( (_QWORD)v22 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v22 + 16LL))(v22);
    return 2147500035LL;
  }
  *a4 = 0;
  IsProcessAdmin = WaasMedic::IsProcessAdmin((WaasMedic *)&v20, v7, v8, v9);
  if ( IsProcessAdmin < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x6CB,
      (unsigned int)"onecore\\enduser\\waasmedic\\servicelib\\waasremediationagent.cpp",
      (const char *)(unsigned int)IsProcessAdmin,
      (int)"Failed to determine if caller is Admin.",
      v19);
    if ( *((_QWORD *)&v22 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v22 + 1) + 16LL))(*((_QWORD *)&v22 + 1));
    if ( (_QWORD)v22 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v22 + 16LL))(v22);
    return (unsigned int)IsProcessAdmin;
  }
  v12 = &word_180073298;
  v13 = v20;
  if ( v20 != 1 )
    v12 = L"not";
  LogLevelW(5u, L"Caller is %s admin", v12);
  if ( !v13 )
  {
    LogLevelW(2u, L"Caller is not admin. ShouldHideInPlaceUpgrade will not be executed");
    if ( *((_QWORD *)&v22 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v22 + 1) + 16LL))(*((_QWORD *)&v22 + 1));
    if ( (_QWORD)v22 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v22 + 16LL))(v22);
    return 2147942405LL;
  }
  if ( a3 )
  {
    IsProcessAdmin = WaaSRemediationAgent::SetAndExtendCV((WaaSRemediationAgent *)((char *)this - 32), a3);
    if ( IsProcessAdmin < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x6D6,
        (unsigned int)"onecore\\enduser\\waasmedic\\servicelib\\waasremediationagent.cpp",
        (const char *)(unsigned int)IsProcessAdmin,
        (int)"Failed to set and extend CV for ShouldHideInPlaceUpgrade.",
        v19);
      if ( *((_QWORD *)&v22 + 1) )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v22 + 1) + 16LL))(*((_QWORD *)&v22 + 1));
      if ( (_QWORD)v22 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v22 + 16LL))(v22);
      return (unsigned int)IsProcessAdmin;
    }
  }
  IsProcessAdmin = WaasMedic::IpuHelper::GetAllowInPlaceUpgradeRegKeyValue(&v24);
  if ( IsProcessAdmin < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x6E1,
      (unsigned int)"onecore\\enduser\\waasmedic\\servicelib\\waasremediationagent.cpp",
      (const char *)(unsigned int)IsProcessAdmin,
      (int)"'ShouldHideInPlaceUpgrade' Failed to get the User In-Place Upgrade registry value.",
      v19);
    if ( *((_QWORD *)&v22 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v22 + 1) + 16LL))(*((_QWORD *)&v22 + 1));
    if ( (_QWORD)v22 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v22 + 16LL))(v22);
    return (unsigned int)IsProcessAdmin;
  }
  if ( v24 != 3 )
  {
    IsProcessAdmin = WaasMedic::SettingsProviderFactory::CreateSettingsProvider(
                       (WaasMedic::SettingsProviderFactory *)v28,
                       &v25);
    if ( IsProcessAdmin < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x6EB,
        (unsigned int)"onecore\\enduser\\waasmedic\\servicelib\\waasremediationagent.cpp",
        (const char *)(unsigned int)IsProcessAdmin,
        (int)"'ShouldHideInPlaceUpgrade' Unable to create instance of state provider.",
        v19);
      if ( *((_QWORD *)&v22 + 1) )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v22 + 1) + 16LL))(*((_QWORD *)&v22 + 1));
      if ( (_QWORD)v22 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v22 + 16LL))(v22);
      return (unsigned int)IsProcessAdmin;
    }
    v14 = v25;
    v15 = *(__int64 (__fastcall **)(struct WaasMedic::SettingsProvider *, _OWORD *, _OWORD *, _DWORD *))(*(_QWORD *)v25 + 8LL);
    memset(v30, 0, sizeof(v30));
    std::wstring::_Construct<1,unsigned short const *>(v30, L"InPlaceUpgradeLCUErrorCount", 27);
    memset(v29, 0, sizeof(v29));
    std::wstring::_Construct<1,unsigned short const *>(v29, &word_180073298, 0);
    IsProcessAdmin = v15(v14, v29, v30, v26);
    std::wstring::~wstring(v29);
    std::wstring::~wstring(v30);
    if ( IsProcessAdmin < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x6ED,
        (unsigned int)"onecore\\enduser\\waasmedic\\servicelib\\waasremediationagent.cpp",
        (const char *)(unsigned int)IsProcessAdmin,
        (int)"'ShouldHideInPlaceUpgrade' Unable to get OneSettings value for %ws.",
        L"InPlaceUpgradeLCUErrorCount");
      if ( *((_QWORD *)&v22 + 1) )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v22 + 1) + 16LL))(*((_QWORD *)&v22 + 1));
      if ( (_QWORD)v22 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v22 + 16LL))(v22);
      return (unsigned int)IsProcessAdmin;
    }
    LODWORD(v25) = 0;
    v17 = WaasMedic::RegQueryDwordValue(
            v16,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing",
            L"DeviceInfoGatherSuccessful",
            &v25);
    if ( v17 >= 0 )
    {
      if ( (_DWORD)v25 != 1 )
        goto LABEL_53;
    }
    else
    {
      v18 = 0;
      if ( v17 == -2147024894 )
      {
        if ( (int)WaasMedic::CbsUtil::FodEnumerationCheck() < 0 )
          goto LABEL_53;
        v18 = 1;
      }
      if ( !v18 )
      {
LABEL_53:
        *a4 = 1;
        LogLevelW(4u, L"'ShouldHideInPlaceUpgrade' fFodOCFailed = %d pbDisableIPU = '%d'", 1, 1);
        if ( *((_QWORD *)&v22 + 1) )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v22 + 1) + 16LL))(*((_QWORD *)&v22 + 1));
        goto LABEL_55;
      }
    }
    IsProcessAdmin = WaasMedic::UsoHelper::Initialize((WaasMedic::UsoHelper *)&v22);
    if ( IsProcessAdmin < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x6F6,
        (unsigned int)"onecore\\enduser\\waasmedic\\servicelib\\waasremediationagent.cpp",
        (const char *)(unsigned int)IsProcessAdmin,
        (int)"'ShouldHideInPlaceUpgrade' USO helper failed to initialize.",
        v19);
      if ( *((_QWORD *)&v22 + 1) )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v22 + 1) + 16LL))(*((_QWORD *)&v22 + 1));
      if ( (_QWORD)v22 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v22 + 16LL))(v22);
      return (unsigned int)IsProcessAdmin;
    }
    IsProcessAdmin = WaasMedic::UsoHelper::IsUpgradeInProgress((WaasMedic::UsoHelper *)&v22, &v21);
    if ( IsProcessAdmin < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x6F7,
        (unsigned int)"onecore\\enduser\\waasmedic\\servicelib\\waasremediationagent.cpp",
        (const char *)(unsigned int)IsProcessAdmin,
        (int)"'ShouldHideInPlaceUpgrade' UsoHelper::IsUpgradeInProgress failed.",
        v19);
      if ( *((_QWORD *)&v22 + 1) )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v22 + 1) + 16LL))(*((_QWORD *)&v22 + 1));
      if ( (_QWORD)v22 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v22 + 16LL))(v22);
      return (unsigned int)IsProcessAdmin;
    }
    if ( v21 )
      *a4 = 1;
    goto LABEL_73;
  }
  *a4 = 1;
  LogLevelW(4u, L"'ShouldHideInPlaceUpgrade' Off-ramp In-Place Upgrade is set, returning TRUE");
LABEL_73:
  if ( *((_QWORD *)&v22 + 1) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v22 + 1) + 16LL))(*((_QWORD *)&v22 + 1));
LABEL_55:
  if ( (_QWORD)v22 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v22 + 16LL))(v22);
  return 0;
}

```

## disassembly

```asm
0x180061790  push    rbp
0x180061792  push    rbx
0x180061793  push    rsi
0x180061794  push    rdi
0x180061795  push    r12
0x180061797  push    r14
0x180061799  lea     rbp, [rsp-2Fh]
0x18006179e  sub     rsp, 0C8h
0x1800617a5  mov     rax, cs:__security_cookie
0x1800617ac  xor     rax, rsp
0x1800617af  mov     [rbp+57h+var_38], rax
0x1800617b3  mov     rsi, r9
0x1800617b6  mov     rdi, r8
0x1800617b9  mov     r14, rcx
0x1800617bc  mov     [rbp+57h+var_C0], 0
0x1800617c0  xor     eax, eax
0x1800617c2  mov     [rbp+57h+var_A8], rax
0x1800617c6  xorps   xmm1, xmm1
0x1800617c9  movdqu  [rbp+57h+var_B8], xmm1
0x1800617ce  mov     byte ptr [rbp+57h+var_A8], al
0x1800617d1  mov     [rbp+57h+var_BF], al
0x1800617d4  mov     [rbp+57h+var_98], rax
0x1800617d8  mov     [rbp+57h+var_88], al
0x1800617db  mov     [rbp+57h+var_90], 3
0x1800617e2  mov     [rbp+57h+var_8C], 2
0x1800617e9  mov     [rbp+57h+var_A0], eax
0x1800617ec  mov     r8, rdx
0x1800617ef  lea     rdx, aShouldhideinpl_6; "'ShouldHideInPlaceUpgrade' called by '%"...
0x1800617f6  lea     ecx, [rax+4]; unsigned __int8
0x1800617f9  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800617fe  test    rsi, rsi
0x180061801  jnz     short loc_180061839
0x180061803  mov     rcx, qword ptr [rbp+57h+var_B8+8]
0x180061807  test    rcx, rcx
0x18006180a  jz      short loc_180061819
0x18006180c  mov     rax, [rcx]
0x18006180f  mov     rax, [rax+10h]
0x180061813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061818  nop
0x180061819  mov     rcx, qword ptr [rbp+57h+var_B8]
0x18006181d  test    rcx, rcx
0x180061820  jz      short loc_18006182F
0x180061822  mov     rax, [rcx]
0x180061825  mov     rax, [rax+10h]
0x180061829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006182e  nop
0x18006182f  mov     eax, 80004003h
0x180061834  jmp     loc_180061BE1
0x180061839  mov     dword ptr [rsi], 0
0x18006183f  lea     rcx, [rbp+57h+var_C0]; this
0x180061843  call    ?IsProcessAdmin@WaasMedic@@YAJAEA_N@Z; WaasMedic::IsProcessAdmin(bool &)
0x180061848  mov     ebx, eax
0x18006184a  test    eax, eax
0x18006184c  jns     short loc_1800618A6
0x18006184e  mov     rcx, [rbp+5Fh]; this
0x180061852  lea     rax, aFailedToDeterm_1; "Failed to determine if caller is Admin."
0x180061859  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x18006185e  mov     r9d, ebx; char *
0x180061861  lea     r8, aOnecoreEnduser_18; "onecore\\enduser\\waasmedic\\servicelib"...
0x180061868  mov     edx, 6CBh; void *
0x18006186d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180061872  nop
0x180061873  mov     rcx, qword ptr [rbp+57h+var_B8+8]
0x180061877  test    rcx, rcx
0x18006187a  jz      short loc_180061889
0x18006187c  mov     rax, [rcx]
0x18006187f  mov     rax, [rax+10h]
0x180061883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061888  nop
0x180061889  mov     rcx, qword ptr [rbp+57h+var_B8]
0x18006188d  test    rcx, rcx
0x180061890  jz      short loc_18006189F
0x180061892  mov     rax, [rcx]
0x180061895  mov     rax, [rax+10h]
0x180061899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006189e  nop
0x18006189f  mov     eax, ebx
0x1800618a1  jmp     loc_180061BE1
0x1800618a6  lea     r8, word_180073298
0x1800618ad  lea     rax, aNot; "not"
0x1800618b4  mov     bl, [rbp+57h+var_C0]
0x1800618b7  mov     r12d, 1
0x1800618bd  cmp     bl, r12b
0x1800618c0  cmovnz  r8, rax
0x1800618c4  lea     rdx, aCallerIsSAdmin; "Caller is %s admin"
0x1800618cb  lea     ecx, [r12+4]; unsigned __int8
0x1800618d0  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800618d5  test    bl, bl
0x1800618d7  jnz     short loc_180061921
0x1800618d9  lea     rdx, aCallerIsNotAdm_2; "Caller is not admin. ShouldHideInPlaceU"...
0x1800618e0  lea     ecx, [r12+1]; unsigned __int8
0x1800618e5  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800618ea  nop
0x1800618eb  mov     rcx, qword ptr [rbp+57h+var_B8+8]
0x1800618ef  test    rcx, rcx
0x1800618f2  jz      short loc_180061901
0x1800618f4  mov     rax, [rcx]
0x1800618f7  mov     rax, [rax+10h]
0x1800618fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061900  nop
0x180061901  mov     rcx, qword ptr [rbp+57h+var_B8]
0x180061905  test    rcx, rcx
0x180061908  jz      short loc_180061917
0x18006190a  mov     rax, [rcx]
0x18006190d  mov     rax, [rax+10h]
0x180061911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061916  nop
0x180061917  mov     eax, 80070005h
0x18006191c  jmp     loc_180061BE1
0x180061921  test    rdi, rdi
0x180061924  jz      short loc_18006198E
0x180061926  lea     rcx, [r14-20h]; this
0x18006192a  mov     rdx, rdi; char *
0x18006192d  call    ?SetAndExtendCV@WaaSRemediationAgent@@AEAAJPEBD@Z; WaaSRemediationAgent::SetAndExtendCV(char const *)
0x180061932  mov     ebx, eax
0x180061934  test    eax, eax
0x180061936  jns     short loc_18006198E
0x180061938  mov     rcx, [rbp+5Fh]; this
0x18006193c  lea     rax, aFailedToSetAnd_12; "Failed to set and extend CV for ShouldH"...
0x180061943  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180061948  mov     r9d, ebx; char *
0x18006194b  lea     r8, aOnecoreEnduser_18; "onecore\\enduser\\waasmedic\\servicelib"...
0x180061952  mov     edx, 6D6h; void *
0x180061957  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006195c  nop
0x18006195d  mov     rcx, qword ptr [rbp+57h+var_B8+8]
0x180061961  test    rcx, rcx
0x180061964  jz      short loc_180061973
0x180061966  mov     rax, [rcx]
0x180061969  mov     rax, [rax+10h]
0x18006196d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061972  nop
0x180061973  mov     rcx, qword ptr [rbp+57h+var_B8]
0x180061977  test    rcx, rcx
0x18006197a  jz      short loc_180061989
0x18006197c  mov     rax, [rcx]
0x18006197f  mov     rax, [rax+10h]
0x180061983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061988  nop
0x180061989  jmp     loc_18006189F
0x18006198e  lea     rcx, [rbp+57h+var_A0]; unsigned int *
0x180061992  call    ?GetAllowInPlaceUpgradeRegKeyValue@IpuHelper@WaasMedic@@SAJAEAK@Z; WaasMedic::IpuHelper::GetAllowInPlaceUpgradeRegKeyValue(ulong &)
0x180061997  mov     ebx, eax
0x180061999  test    eax, eax
0x18006199b  jns     short loc_1800619F3
0x18006199d  mov     rcx, [rbp+5Fh]; this
0x1800619a1  lea     rax, aShouldhideinpl_0; "'ShouldHideInPlaceUpgrade' Failed to ge"...
0x1800619a8  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x1800619ad  mov     r9d, ebx; char *
0x1800619b0  lea     r8, aOnecoreEnduser_18; "onecore\\enduser\\waasmedic\\servicelib"...
0x1800619b7  mov     edx, 6E1h; void *
0x1800619bc  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800619c1  nop
0x1800619c2  mov     rcx, qword ptr [rbp+57h+var_B8+8]
0x1800619c6  test    rcx, rcx
0x1800619c9  jz      short loc_1800619D8
0x1800619cb  mov     rax, [rcx]
0x1800619ce  mov     rax, [rax+10h]
0x1800619d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800619d7  nop
0x1800619d8  mov     rcx, qword ptr [rbp+57h+var_B8]
0x1800619dc  test    rcx, rcx
0x1800619df  jz      short loc_1800619EE
0x1800619e1  mov     rax, [rcx]
0x1800619e4  mov     rax, [rax+10h]
0x1800619e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800619ed  nop
0x1800619ee  jmp     loc_18006189F
0x1800619f3  cmp     [rbp+57h+var_A0], 3
0x1800619f7  jnz     short loc_180061A12
0x1800619f9  mov     [rsi], r12d
0x1800619fc  lea     rdx, aShouldhideinpl_4; "'ShouldHideInPlaceUpgrade' Off-ramp In-"...
0x180061a03  mov     ecx, 4; unsigned __int8
0x180061a08  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180061a0d  jmp     loc_180061CDA
0x180061a12  lea     rdx, [rbp+57h+var_98]; struct WaasMedic::SettingsProvider **
0x180061a16  lea     rcx, [rbp+57h+var_80]; this
0x180061a1a  call    ?CreateSettingsProvider@SettingsProviderFactory@WaasMedic@@UEAAJPEAPEAVSettingsProvider@2@@Z; WaasMedic::SettingsProviderFactory::CreateSettingsProvider(WaasMedic::SettingsProvider * *)
0x180061a1f  mov     ebx, eax
0x180061a21  test    eax, eax
0x180061a23  jns     short loc_180061A7B
0x180061a25  mov     rcx, [rbp+5Fh]; this
0x180061a29  lea     rax, aShouldhideinpl_3; "'ShouldHideInPlaceUpgrade' Unable to cr"...
0x180061a30  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180061a35  mov     r9d, ebx; char *
0x180061a38  lea     r8, aOnecoreEnduser_18; "onecore\\enduser\\waasmedic\\servicelib"...
0x180061a3f  mov     edx, 6EBh; void *
0x180061a44  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180061a49  nop
0x180061a4a  mov     rcx, qword ptr [rbp+57h+var_B8+8]
0x180061a4e  test    rcx, rcx
0x180061a51  jz      short loc_180061A60
0x180061a53  mov     rax, [rcx]
0x180061a56  mov     rax, [rax+10h]
0x180061a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061a5f  nop
0x180061a60  mov     rcx, qword ptr [rbp+57h+var_B8]
0x180061a64  test    rcx, rcx
0x180061a67  jz      short loc_180061A76
0x180061a69  mov     rax, [rcx]
0x180061a6c  mov     rax, [rax+10h]
0x180061a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061a75  nop
0x180061a76  jmp     loc_18006189F
0x180061a7b  mov     rdi, [rbp+57h+var_98]
0x180061a7f  mov     rax, [rdi]
0x180061a82  mov     rbx, [rax+8]
0x180061a86  xorps   xmm0, xmm0
0x180061a89  movups  [rbp+57h+var_58], xmm0
0x180061a8d  xorps   xmm1, xmm1
0x180061a90  movdqu  [rbp+57h+var_48], xmm1
0x180061a95  mov     r8d, 1Bh
0x180061a9b  lea     r14, aInplaceupgrade; "InPlaceUpgradeLCUErrorCount"
0x180061aa2  mov     rdx, r14
0x180061aa5  lea     rcx, [rbp+57h+var_58]
0x180061aa9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180061aae  nop
0x180061aaf  xorps   xmm0, xmm0
0x180061ab2  movups  [rbp+57h+var_78], xmm0
0x180061ab6  xorps   xmm1, xmm1
0x180061ab9  movdqu  [rbp+57h+var_68], xmm1
0x180061abe  xor     r8d, r8d
0x180061ac1  lea     rdx, word_180073298
0x180061ac8  lea     rcx, [rbp+57h+var_78]
0x180061acc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180061ad1  nop
0x180061ad2  lea     r9, [rbp+57h+var_90]
0x180061ad6  lea     r8, [rbp+57h+var_58]
0x180061ada  lea     rdx, [rbp+57h+var_78]
0x180061ade  mov     rcx, rdi
0x180061ae1  mov     rax, rbx
0x180061ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061ae9  mov     ebx, eax
0x180061aeb  lea     rcx, [rbp+57h+var_78]; void *
0x180061aef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180061af4  nop
0x180061af5  lea     rcx, [rbp+57h+var_58]; void *
0x180061af9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180061afe  test    ebx, ebx
0x180061b00  jns     short loc_180061B5D
0x180061b02  mov     rcx, [rbp+5Fh]; this
0x180061b06  mov     [rsp+0F0h+var_C8], r14; char *
0x180061b0b  lea     rax, aShouldhideinpl; "'ShouldHideInPlaceUpgrade' Unable to ge"...
0x180061b12  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180061b17  mov     r9d, ebx; char *
0x180061b1a  lea     r8, aOnecoreEnduser_18; "onecore\\enduser\\waasmedic\\servicelib"...
0x180061b21  mov     edx, 6EDh; void *
0x180061b26  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180061b2b  nop
0x180061b2c  mov     rcx, qword ptr [rbp+57h+var_B8+8]
0x180061b30  test    rcx, rcx
0x180061b33  jz      short loc_180061B42
0x180061b35  mov     rax, [rcx]
0x180061b38  mov     rax, [rax+10h]
0x180061b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061b41  nop
0x180061b42  mov     rcx, qword ptr [rbp+57h+var_B8]
0x180061b46  test    rcx, rcx
0x180061b49  jz      short loc_180061B58
0x180061b4b  mov     rax, [rcx]
0x180061b4e  mov     rax, [rax+10h]
0x180061b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061b57  nop
0x180061b58  jmp     loc_18006189F
0x180061b5d  mov     dword ptr [rbp+57h+var_98], 0
0x180061b64  lea     r9, [rbp+57h+var_98]
0x180061b68  lea     r8, aDeviceinfogath; "DeviceInfoGatherSuccessful"
0x180061b6f  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180061b76  call    ?RegQueryDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1PEAKW4RegistryHiveType@1@@Z; WaasMedic::RegQueryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *,WaasMedic::RegistryHiveType)
0x180061b7b  test    eax, eax
0x180061b7d  jns     short loc_180061BFD
0x180061b7f  xor     cl, cl
0x180061b81  cmp     eax, 80070002h
0x180061b86  jnz     short loc_180061B94
0x180061b88  call    ?FodEnumerationCheck@CbsUtil@WaasMedic@@CAJXZ; WaasMedic::CbsUtil::FodEnumerationCheck(void)
0x180061b8d  test    eax, eax
0x180061b8f  js      short loc_180061B98
0x180061b91  mov     cl, r12b
0x180061b94  test    cl, cl
0x180061b96  jnz     short loc_180061C03
0x180061b98  mov     [rsi], r12d
0x180061b9b  mov     r9d, r12d
0x180061b9e  mov     r8d, r12d
0x180061ba1  lea     rdx, aShouldhideinpl_2; "'ShouldHideInPlaceUpgrade' fFodOCFailed"...
0x180061ba8  mov     ecx, 4; unsigned __int8
0x180061bad  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180061bb2  nop
0x180061bb3  mov     rcx, qword ptr [rbp+57h+var_B8+8]
0x180061bb7  test    rcx, rcx
0x180061bba  jz      short loc_180061BC9
0x180061bbc  mov     rax, [rcx]
0x180061bbf  mov     rax, [rax+10h]
0x180061bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061bc8  nop
0x180061bc9  mov     rcx, qword ptr [rbp+57h+var_B8]
0x180061bcd  test    rcx, rcx
0x180061bd0  jz      short loc_180061BDF
0x180061bd2  mov     rax, [rcx]
0x180061bd5  mov     rax, [rax+10h]
0x180061bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
