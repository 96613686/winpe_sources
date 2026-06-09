# OobeEasyConnectTask::OnESimServiceStateChanged(_GUID const &,SimSlot,ESimSettingServiceState,ESimSettingServiceStateDetail)

- ea: `0x180022800`
- end: `0x180022a09`
- name: `?OnESimServiceStateChanged@OobeEasyConnectTask@@UEAAJAEBU_GUID@@W4SimSlot@@W4ESimSettingServiceState@@W4ESimSettingServiceStateDetail@@@Z`
- size: `521`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000ad20`
- `0x180022800`
- `0x180022a1c`
- `0x180022a3c`
- `0x180022c1c`
- `0x180022e9c`
- `0x1800482b4`
- `0x180048440`
- `0x180059010`

## string_xrefs

- `0x180022837`: `OobeEasyConnectTask::OnESimServiceStateChanged`
- `0x18002290f`: `OobeEasyConnectTask::OnESimServiceStateChanged`
- `0x180022966`: `OobeEasyConnectTask::OnESimServiceStateChanged`
- `0x18002298f`: `OobeEasyConnectTask::OnESimServiceStateChanged`
- `0x180022903`: `Confirm profile installation`
- `0x180022865`: `serviceState=%d, serviceStateDetail=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OobeEasyConnectTask::OnESimServiceStateChanged(__int64 a1, _QWORD *a2, int a3, int a4, int a5)
{
  __int64 v7; // rax
  __int64 result; // rax
  int v9; // r14d
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  __int64 v16; // r9
  _QWORD *v17; // rdx
  _QWORD *v18; // rdx
  const char *v19; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v21; // [rsp+40h] [rbp+8h] BYREF

  v7 = *(_QWORD *)(a1 + 80) - *a2;
  if ( !v7 )
    v7 = *(_QWORD *)(a1 + 88) - a2[1];
  if ( v7 )
    return 0;
  if ( *(_DWORD *)(a1 + 116) != a3 )
  {
    MBSettingUXLogging::Info(
      "OobeEasyConnectTask::OnESimServiceStateChanged",
      134,
      "Discarding notification for slot %d",
      a3);
    return 0;
  }
  v9 = a5;
  MBSettingUXLogging::Info(
    "OobeEasyConnectTask::OnESimServiceStateChanged",
    138,
    "serviceState=%d, serviceStateDetail=%d",
    a4,
    a5);
  wil::EnterCriticalSection(&v21, a1 + 24);
  try
  {
    *(_DWORD *)(a1 + 164) = a4;
    v12 = *(_DWORD *)(a1 + 96);
    if ( !v12 )
    {
      if ( a4 == 1 )
      {
        LOBYTE(v10) = v21;
        OobeEasyConnectTask::AttemptDiscovery(a1, v10);
      }
      goto LABEL_30;
    }
    v13 = v12 - 1;
    if ( !v13 || (v14 = v13 - 1) == 0 )
    {
      if ( v9 == 9 )
      {
        if ( *(_BYTE *)(a1 + 1137) || (*(_BYTE *)(a1 + 1140) & 3) != 0 )
        {
          MBSettingUXLogging::Info("OobeEasyConnectTask::OnESimServiceStateChanged", 160, "Reject profile");
          v18 = (_QWORD *)(a1 + 216);
          if ( *(_QWORD *)(a1 + 240) > 7u )
            v18 = (_QWORD *)*v18;
          (*(void (__fastcall **)(_QWORD, _QWORD *, const WCHAR *, _QWORD, _DWORD))(**(_QWORD **)(a1 + 72) + 48LL))(
            *(_QWORD *)(a1 + 72),
            v18,
            &sourceString,
            0,
            0);
        }
        else
        {
          MBSettingUXLogging::Info(
            "OobeEasyConnectTask::OnESimServiceStateChanged",
            165,
            "Confirm profile installation");
          *(_BYTE *)(a1 + 112) = 1;
          v17 = (_QWORD *)(a1 + 216);
          if ( *(_QWORD *)(a1 + 240) > 7u )
            v17 = (_QWORD *)*v17;
          LOBYTE(v16) = 1;
          if ( (*(int (__fastcall **)(_QWORD, _QWORD *, const WCHAR *, __int64, _DWORD))(**(_QWORD **)(a1 + 72) + 48LL))(
                 *(_QWORD *)(a1 + 72),
                 v17,
                 &sourceString,
                 v16,
                 0) >= 0 )
          {
            MBSettingUXLogging::Info(
              "OobeEasyConnectTask::OnESimServiceStateChanged",
              170,
              "Changing state to 'Downloading'");
            *(_DWORD *)(a1 + 96) = 2;
            OobeEasyConnectTask::PublishCurrentTaskStateWnf(a1);
          }
        }
      }
      goto LABEL_30;
    }
    v15 = v14 - 1;
    if ( v15 )
    {
      if ( v15 != 1 )
      {
LABEL_30:
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v21);
        return 0;
      }
    }
    else if ( a4 == 1 )
    {
      OobeEasyConnectTask::AttemptDeleteBootstrapProfile(a1, v21);
    }
    if ( *(_DWORD *)(a1 + 164) == 1 )
    {
      LOBYTE(v10) = v21;
      OobeEasyConnectTask::AttemptEnableDownloadedProfile(a1, v10, v11);
    }
    goto LABEL_30;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xBF,
                           (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
                           v19);
  }
  return result;
}

```

## disassembly

```asm
0x180022800  mov     [rsp+arg_8], rbx
0x180022805  mov     [rsp+arg_10], rsi
0x18002280a  push    r14
0x18002280c  sub     rsp, 30h
0x180022810  mov     esi, r9d
0x180022813  mov     rbx, rcx
0x180022816  mov     rax, [rcx+50h]
0x18002281a  sub     rax, [rdx]
0x18002281d  jnz     short loc_180022827
0x18002281f  mov     rax, [rcx+58h]
0x180022823  sub     rax, [rdx+8]
0x180022827  test    rax, rax
0x18002282a  jz      short loc_180022833
0x18002282c  xor     eax, eax
0x18002282e  jmp     loc_1800229F7
0x180022833  cmp     [rcx+74h], r8d
0x180022837  lea     rcx, aOobeeasyconnec_1; "OobeEasyConnectTask::OnESimServiceState"...
0x18002283e  jz      short loc_18002285B
0x180022840  mov     r9d, r8d
0x180022843  lea     r8, aDiscardingNoti; "Discarding notification for slot %d"
0x18002284a  mov     edx, 86h; unsigned int
0x18002284f  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180022854  xor     eax, eax
0x180022856  jmp     loc_1800229F7
0x18002285b  mov     r14d, [rsp+38h+arg_20]
0x180022860  mov     [rsp+38h+var_18], r14d
0x180022865  lea     r8, aServicestateDS; "serviceState=%d, serviceStateDetail=%d"
0x18002286c  mov     edx, 8Ah; unsigned int
0x180022871  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180022876  lea     rdx, [rbx+18h]
0x18002287a  lea     rcx, [rsp+38h+arg_0]
0x18002287f  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180022884  nop
0x180022885  mov     [rbx+0A4h], esi
0x18002288b  mov     ecx, [rbx+60h]
0x18002288e  test    ecx, ecx
0x180022890  jz      loc_1800229D3
0x180022896  sub     ecx, 1
0x180022899  jz      short loc_1800228DF
0x18002289b  sub     ecx, 1
0x18002289e  jz      short loc_1800228DF
0x1800228a0  sub     ecx, 1
0x1800228a3  jz      short loc_1800228B0
0x1800228a5  cmp     ecx, 1
0x1800228a8  jnz     loc_1800229E5
0x1800228ae  jmp     short loc_1800228C1
0x1800228b0  cmp     esi, 1
0x1800228b3  jnz     short loc_1800228C1
0x1800228b5  mov     dl, byte ptr [rsp+38h+arg_0]
0x1800228b9  mov     rcx, rbx
0x1800228bc  call    ?AttemptDeleteBootstrapProfile@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::AttemptDeleteBootstrapProfile(wil::write_lock_required)
0x1800228c1  cmp     dword ptr [rbx+0A4h], 1
0x1800228c8  jnz     loc_1800229E5
0x1800228ce  mov     dl, byte ptr [rsp+38h+arg_0]
0x1800228d2  mov     rcx, rbx
0x1800228d5  call    ?AttemptEnableDownloadedProfile@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::AttemptEnableDownloadedProfile(wil::write_lock_required)
0x1800228da  jmp     loc_1800229E5
0x1800228df  cmp     r14d, 9
0x1800228e3  jnz     loc_1800229E5
0x1800228e9  cmp     byte ptr [rbx+471h], 0
0x1800228f0  jnz     loc_180022983
0x1800228f6  test    byte ptr [rbx+474h], 3
0x1800228fd  jnz     loc_180022983
0x180022903  lea     r8, aConfirmProfile; "Confirm profile installation"
0x18002290a  mov     edx, 0A5h; unsigned int
0x18002290f  lea     rcx, aOobeeasyconnec_1; "OobeEasyConnectTask::OnESimServiceState"...
0x180022916  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18002291b  mov     byte ptr [rbx+70h], 1
0x18002291f  mov     rcx, [rbx+48h]
0x180022923  mov     rax, [rcx]
0x180022926  lea     rdx, [rbx+0D8h]
0x18002292d  cmp     qword ptr [rdx+18h], 7
0x180022932  jbe     short loc_180022937
0x180022934  mov     rdx, [rdx]
0x180022937  mov     [rsp+38h+var_18], 0
0x18002293f  mov     r9b, 1
0x180022942  lea     r8, sourceString
0x180022949  mov     rax, [rax+30h]
0x18002294d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022952  test    eax, eax
0x180022954  js      loc_1800229E5
0x18002295a  lea     r8, aChangingStateT_3; "Changing state to 'Downloading'"
0x180022961  mov     edx, 0AAh; unsigned int
0x180022966  lea     rcx, aOobeeasyconnec_1; "OobeEasyConnectTask::OnESimServiceState"...
0x18002296d  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180022972  mov     dword ptr [rbx+60h], 2
0x180022979  mov     rcx, rbx
0x18002297c  call    ?PublishCurrentTaskStateWnf@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::PublishCurrentTaskStateWnf(wil::write_lock_required)
0x180022981  jmp     short loc_1800229E5
0x180022983  lea     r8, aRejectProfile; "Reject profile"
0x18002298a  mov     edx, 0A0h; unsigned int
0x18002298f  lea     rcx, aOobeeasyconnec_1; "OobeEasyConnectTask::OnESimServiceState"...
0x180022996  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18002299b  mov     rcx, [rbx+48h]
0x18002299f  mov     rax, [rcx]
0x1800229a2  lea     rdx, [rbx+0D8h]
0x1800229a9  cmp     qword ptr [rdx+18h], 7
0x1800229ae  jbe     short loc_1800229B3
0x1800229b0  mov     rdx, [rdx]
0x1800229b3  mov     [rsp+38h+var_18], 0
0x1800229bb  xor     r9d, r9d
0x1800229be  lea     r8, sourceString
0x1800229c5  mov     rax, [rax+30h]
0x1800229c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229ce  jmp     loc_1800228DA
0x1800229d3  cmp     esi, 1
0x1800229d6  jnz     short loc_1800229E5
0x1800229d8  mov     dl, byte ptr [rsp+38h+arg_0]
0x1800229dc  mov     rcx, rbx
0x1800229df  call    ?AttemptDiscovery@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::AttemptDiscovery(wil::write_lock_required)
0x1800229e4  nop
0x1800229e5  lea     rcx, [rsp+38h+arg_0]
0x1800229ea  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800229ef  xor     eax, eax
0x1800229f1  jmp     short loc_1800229F7
0x1800229f3  mov     eax, [rsp+38h+arg_0]
0x1800229f7  mov     rbx, [rsp+38h+arg_8]
0x1800229fc  mov     rsi, [rsp+38h+arg_10]
0x180022a01  add     rsp, 30h
0x180022a05  pop     r14
0x180022a07  retn
```
