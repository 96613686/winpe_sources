# ShieldProvider::ShieldProcessLauncher::IsProcessAMPPL(ulong,int *)

- ea: `0x18007c9d0`
- end: `0x18007cd51`
- name: `?IsProcessAMPPL@ShieldProcessLauncher@ShieldProvider@@UEAAJKPEAH@Z`
- size: `897`
- prototype: `int(ShieldProvider::ShieldProcessLauncher *__hidden this, unsigned int, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004710`
- `0x18000ccd4`
- `0x18000d7fc`
- `0x180011730`
- `0x18007c9d0`
- `0x1800d1e1c`
- `0x1800db4f4`
- `0x1800db5b8`
- `0x1800e1690`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18007cb34`
- `KERNEL32!CloseHandle` at `0x18007cc03`
- `KERNEL32!CloseHandle` at `0x18007cc64`
- `KERNEL32!CloseHandle` at `0x18007ccdf`
- `KERNEL32!CloseHandle` at `0x18007cced`
- `KERNEL32!CloseHandle` at `0x18007cd1b`
- `KERNEL32!CloseHandle` at `0x18007cd29`
- `KERNEL32!CloseHandle` at `0x18007cb34`
- `KERNEL32!CloseHandle` at `0x18007cc03`
- `KERNEL32!CloseHandle` at `0x18007cc64`
- `KERNEL32!CloseHandle` at `0x18007ccdf`
- `KERNEL32!CloseHandle` at `0x18007cced`
- `KERNEL32!CloseHandle` at `0x18007cd1b`
- `KERNEL32!CloseHandle` at `0x18007cd29`
- `KERNEL32!GetCurrentProcess` at `0x18007cad9`
- `KERNEL32!GetCurrentProcess` at `0x18007cad9`
- `ntdll!NtQueryInformationProcess` at `0x18007cc8c`
- `ntdll!NtQueryInformationProcess` at `0x18007cc8c`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18007cbb5`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18007cbb5`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18007cb60`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18007cb60`

## string_xrefs

- `0x18007cb50`: `SeDebugPrivilege`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ShieldProcessLauncher::IsProcessAMPPL(
        ShieldProvider::ShieldProcessLauncher *this,
        unsigned int a2,
        int *a3)
{
  int v5; // eax
  bool *v6; // r8
  int LastFailure; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  void **CurrentProcess; // rax
  unsigned int v13; // r9d
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  int v16; // esi
  HANDLE v17; // rbx
  unsigned int v18; // r8d
  unsigned int v19; // r9d
  int v20; // eax
  unsigned int v21; // edi
  int v22; // eax
  HANDLE v23; // rdi
  NTSTATUS InformationProcess; // eax
  int v25; // r14d
  unsigned __int16 v26; // [rsp+30h] [rbp-30h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-20h] BYREF

  hObject = 0;
  v5 = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(&hObject);
  LastFailure = v5;
  if ( v5 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    v9 = 81;
    goto LABEL_5;
  }
  LOBYTE(v26) = 0;
  v5 = ShieldProvider::CheckCallerIdentity(L"S-1-5-80-3232712927-1625117661-2590453128-1738570065-3637376297", &v26, v6);
  LastFailure = v5;
  if ( v5 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    v9 = 82;
LABEL_5:
    v10 = (unsigned int)v5;
LABEL_14:
    WPP_SF_d(v8[2], v9, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids, v10);
LABEL_15:
    CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&hObject);
    return (unsigned int)LastFailure;
  }
  if ( !(_BYTE)v26 )
  {
    v8 = WPP_GLOBAL_Control;
    LastFailure = -2147024891;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    v9 = 83;
    v10 = 2147942405LL;
    goto LABEL_14;
  }
  CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&hObject);
  hObject = 0;
  CurrentProcess = (void **)GetCurrentProcess();
  LastFailure = CommonUtil::UtilOpenProcessToken((CommonUtil *)&hObject, CurrentProcess, (void *)0x20, v13);
  if ( LastFailure < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 84;
LABEL_21:
      WPP_SF_d(v14[2], v15, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids, (unsigned int)LastFailure);
      goto LABEL_22;
    }
    goto LABEL_22;
  }
  v16 = 1;
  NewState.Privileges[0].Luid = 0;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Attributes = 2;
  if ( !LookupPrivilegeValueW(0, L"SeDebugPrivilege", &NewState.Privileges[0].Luid) )
  {
    LastFailure = HrGetLastFailure();
    if ( LastFailure < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 85;
        goto LABEL_21;
      }
LABEL_22:
      if ( hObject )
        CloseHandle(hObject);
      return (unsigned int)LastFailure;
    }
  }
  v17 = hObject;
  if ( !AdjustTokenPrivileges(hObject, 0, &NewState, 0, 0, 0) )
  {
    v20 = HrGetLastFailure();
    v21 = v20;
    if ( v20 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          86,
          WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids,
          (unsigned int)v20);
LABEL_34:
      if ( v17 )
        CloseHandle(v17);
      return v21;
    }
  }
  hObject = 0;
  v22 = CommonUtil::UtilOpenProcess((CommonUtil *)&hObject, (void **)a2, v18, v19);
  v21 = v22;
  if ( v22 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        87,
        WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids,
        (unsigned int)v22);
    if ( hObject )
      CloseHandle(hObject);
    goto LABEL_34;
  }
  v23 = hObject;
  HIBYTE(v26) = 0;
  InformationProcess = NtQueryInformationProcess(
                         hObject,
                         ProcessAffinityUpdateMode|ProcessUserModeIOPL,
                         (char *)&v26 + 1,
                         1u,
                         0);
  v25 = 0;
  if ( InformationProcess < 0 )
    v25 = InformationProcess | 0x10000000;
  if ( v25 >= 0 )
  {
    if ( (unsigned __int8)((HIBYTE(v26) & 7) - 1) > 1u || (HIBYTE(v26) & 0xF0) != 0x30 )
      v16 = 0;
    *a3 = v16;
    if ( v23 )
      CloseHandle(v23);
    if ( v17 )
      CloseHandle(v17);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        88,
        WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids,
        (unsigned int)v25);
    if ( v23 )
      CloseHandle(v23);
    if ( v17 )
      CloseHandle(v17);
    return (unsigned int)v25;
  }
}

```

## disassembly

```asm
0x18007c9d0  mov     [rsp-28h+arg_0], rbx
0x18007c9d5  push    rbp
0x18007c9d6  push    rsi
0x18007c9d7  push    rdi
0x18007c9d8  push    r14
0x18007c9da  push    r15
0x18007c9dc  mov     rbp, rsp
0x18007c9df  sub     rsp, 60h
0x18007c9e3  mov     rax, cs:__security_cookie
0x18007c9ea  xor     rax, rsp
0x18007c9ed  mov     [rbp+var_10], rax
0x18007c9f1  lea     rcx, [rbp+hObject]
0x18007c9f5  mov     [rbp+hObject], 0
0x18007c9fd  mov     r15, r8
0x18007ca00  mov     r14d, edx
0x18007ca03  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x18007ca08  mov     ebx, eax
0x18007ca0a  test    eax, eax
0x18007ca0c  jns     short loc_18007CA3C
0x18007ca0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ca15  lea     rdx, WPP_GLOBAL_Control
0x18007ca1c  cmp     rcx, rdx
0x18007ca1f  jz      loc_18007CAB8
0x18007ca25  mov     esi, 1
0x18007ca2a  test    [rcx+1Ch], sil
0x18007ca2e  jz      loc_18007CAB8
0x18007ca34  lea     edx, [rsi+50h]
0x18007ca37  mov     r9d, eax
0x18007ca3a  jmp     short loc_18007CAA8
0x18007ca3c  lea     rdx, [rbp+var_30]; unsigned __int16 *
0x18007ca40  mov     byte ptr [rbp+var_30], 0
0x18007ca44  lea     rcx, aS1580323271292; "S-1-5-80-3232712927-1625117661-25904531"...
0x18007ca4b  call    ?CheckCallerIdentity@ShieldProvider@@YAJPEBGPEA_N@Z; ShieldProvider::CheckCallerIdentity(ushort const *,bool *)
0x18007ca50  mov     ebx, eax
0x18007ca52  test    eax, eax
0x18007ca54  jns     short loc_18007CA79
0x18007ca56  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ca5d  lea     rdx, WPP_GLOBAL_Control
0x18007ca64  cmp     rcx, rdx
0x18007ca67  jz      short loc_18007CAB8
0x18007ca69  mov     esi, 1
0x18007ca6e  test    [rcx+1Ch], sil
0x18007ca72  jz      short loc_18007CAB8
0x18007ca74  lea     edx, [rsi+51h]
0x18007ca77  jmp     short loc_18007CA37
0x18007ca79  cmp     byte ptr [rbp+var_30], 0
0x18007ca7d  jnz     short loc_18007CAC8
0x18007ca7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ca86  lea     rdx, WPP_GLOBAL_Control
0x18007ca8d  mov     ebx, 80070005h
0x18007ca92  cmp     rcx, rdx
0x18007ca95  jz      short loc_18007CAB8
0x18007ca97  mov     esi, 1
0x18007ca9c  test    [rcx+1Ch], sil
0x18007caa0  jz      short loc_18007CAB8
0x18007caa2  lea     edx, [rsi+52h]
0x18007caa5  mov     r9d, ebx
0x18007caa8  mov     rcx, [rcx+10h]
0x18007caac  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007cab3  call    WPP_SF_d
0x18007cab8  lea     rcx, [rbp+hObject]
0x18007cabc  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x18007cac1  mov     eax, ebx
0x18007cac3  jmp     loc_18007CD31
0x18007cac8  lea     rcx, [rbp+hObject]
0x18007cacc  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x18007cad1  mov     [rbp+hObject], 0
0x18007cad9  call    cs:__imp_GetCurrentProcess
0x18007cadf  mov     r8d, 20h ; ' '; void *
0x18007cae5  lea     rcx, [rbp+hObject]; this
0x18007cae9  mov     rdx, rax; void **
0x18007caec  call    ?UtilOpenProcessToken@CommonUtil@@YAJPEAPEAXPEAXK@Z; CommonUtil::UtilOpenProcessToken(void * *,void *,ulong)
0x18007caf1  mov     ebx, eax
0x18007caf3  test    eax, eax
0x18007caf5  jns     short loc_18007CB3C
0x18007caf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cafe  lea     rdx, WPP_GLOBAL_Control
0x18007cb05  cmp     rcx, rdx
0x18007cb08  jz      short loc_18007CB2B
0x18007cb0a  mov     esi, 1
0x18007cb0f  test    [rcx+1Ch], sil
0x18007cb13  jz      short loc_18007CB2B
0x18007cb15  lea     edx, [rsi+53h]
0x18007cb18  mov     rcx, [rcx+10h]
0x18007cb1c  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007cb23  mov     r9d, ebx
0x18007cb26  call    WPP_SF_d
0x18007cb2b  mov     rcx, [rbp+hObject]; hObject
0x18007cb2f  test    rcx, rcx
0x18007cb32  jz      short loc_18007CAC1
0x18007cb34  call    cs:__imp_CloseHandle
0x18007cb3a  jmp     short loc_18007CAC1
0x18007cb3c  mov     esi, 1
0x18007cb41  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 0
0x18007cb49  lea     r8, [rbp+NewState.Privileges]; lpLuid
0x18007cb4d  mov     [rbp+NewState.PrivilegeCount], esi
0x18007cb50  lea     rdx, Name; "SeDebugPrivilege"
0x18007cb57  mov     [rbp+NewState.Privileges.Attributes], 2
0x18007cb5e  xor     ecx, ecx; lpSystemName
0x18007cb60  call    cs:__imp_LookupPrivilegeValueW
0x18007cb66  test    eax, eax
0x18007cb68  jnz     short loc_18007CB93
0x18007cb6a  call    HrGetLastFailure
0x18007cb6f  mov     ebx, eax
0x18007cb71  test    eax, eax
0x18007cb73  jns     short loc_18007CB93
0x18007cb75  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cb7c  lea     rdx, WPP_GLOBAL_Control
0x18007cb83  cmp     rcx, rdx
0x18007cb86  jz      short loc_18007CB2B
0x18007cb88  test    [rcx+1Ch], sil
0x18007cb8c  jz      short loc_18007CB2B
0x18007cb8e  lea     edx, [rsi+54h]
0x18007cb91  jmp     short loc_18007CB18
0x18007cb93  mov     rbx, [rbp+hObject]
0x18007cb97  lea     r8, [rbp+NewState]; NewState
0x18007cb9b  mov     rcx, rbx; TokenHandle
0x18007cb9e  mov     [rsp+60h+ReturnLength], 0; ReturnLength
0x18007cba7  xor     r9d, r9d; BufferLength
0x18007cbaa  mov     [rsp+60h+PreviousState], 0; PreviousState
0x18007cbb3  xor     edx, edx; DisableAllPrivileges
0x18007cbb5  call    cs:__imp_AdjustTokenPrivileges
0x18007cbbb  test    eax, eax
0x18007cbbd  jnz     short loc_18007CC10
0x18007cbbf  call    HrGetLastFailure
0x18007cbc4  mov     edi, eax
0x18007cbc6  test    eax, eax
0x18007cbc8  jns     short loc_18007CC10
0x18007cbca  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cbd1  lea     rdx, WPP_GLOBAL_Control
0x18007cbd8  cmp     rcx, rdx
0x18007cbdb  jz      short loc_18007CBFB
0x18007cbdd  test    [rcx+1Ch], sil
0x18007cbe1  jz      short loc_18007CBFB
0x18007cbe3  mov     rcx, [rcx+10h]
0x18007cbe7  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007cbee  mov     edx, 56h ; 'V'
0x18007cbf3  mov     r9d, eax
0x18007cbf6  call    WPP_SF_d
0x18007cbfb  test    rbx, rbx
0x18007cbfe  jz      short loc_18007CC09
0x18007cc00  mov     rcx, rbx; hObject
0x18007cc03  call    cs:__imp_CloseHandle
0x18007cc09  mov     eax, edi
0x18007cc0b  jmp     loc_18007CD31
0x18007cc10  mov     edx, r14d; void **
0x18007cc13  mov     [rbp+hObject], 0
0x18007cc1b  lea     rcx, [rbp+hObject]; this
0x18007cc1f  call    ?UtilOpenProcess@CommonUtil@@YAJPEAPEAXKK@Z; CommonUtil::UtilOpenProcess(void * *,ulong,ulong)
0x18007cc24  mov     edi, eax
0x18007cc26  test    eax, eax
0x18007cc28  jns     short loc_18007CC6C
0x18007cc2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cc31  lea     rdx, WPP_GLOBAL_Control
0x18007cc38  cmp     rcx, rdx
0x18007cc3b  jz      short loc_18007CC5B
0x18007cc3d  test    [rcx+1Ch], sil
0x18007cc41  jz      short loc_18007CC5B
0x18007cc43  mov     rcx, [rcx+10h]
0x18007cc47  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007cc4e  mov     edx, 57h ; 'W'
0x18007cc53  mov     r9d, eax
0x18007cc56  call    WPP_SF_d
0x18007cc5b  mov     rcx, [rbp+hObject]; hObject
0x18007cc5f  test    rcx, rcx
0x18007cc62  jz      short loc_18007CBFB
0x18007cc64  call    cs:__imp_CloseHandle
0x18007cc6a  jmp     short loc_18007CBFB
0x18007cc6c  mov     rdi, [rbp+hObject]
0x18007cc70  lea     r8, [rbp+var_30+1]; ProcessInformation
0x18007cc74  mov     rcx, rdi; ProcessHandle
0x18007cc77  mov     byte ptr [rbp+var_30+1], 0
0x18007cc7b  mov     r9d, esi; ProcessInformationLength
0x18007cc7e  mov     [rsp+60h+PreviousState], 0; ReturnLength
0x18007cc87  mov     edx, 3Dh ; '='; ProcessInformationClass
0x18007cc8c  call    cs:__imp_NtQueryInformationProcess
0x18007cc92  xor     r14d, r14d
0x18007cc95  mov     ecx, eax
0x18007cc97  bts     ecx, 1Ch
0x18007cc9b  test    eax, eax
0x18007cc9d  cmovs   r14d, ecx
0x18007cca1  test    r14d, r14d
0x18007cca4  jns     short loc_18007CCF8
0x18007cca6  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ccad  lea     rdx, WPP_GLOBAL_Control
0x18007ccb4  cmp     rcx, rdx
0x18007ccb7  jz      short loc_18007CCD7
0x18007ccb9  test    [rcx+1Ch], sil
0x18007ccbd  jz      short loc_18007CCD7
0x18007ccbf  mov     rcx, [rcx+10h]
0x18007ccc3  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007ccca  mov     edx, 58h ; 'X'
0x18007cccf  mov     r9d, r14d
0x18007ccd2  call    WPP_SF_d
0x18007ccd7  test    rdi, rdi
0x18007ccda  jz      short loc_18007CCE5
0x18007ccdc  mov     rcx, rdi; hObject
0x18007ccdf  call    cs:__imp_CloseHandle
0x18007cce5  test    rbx, rbx
0x18007cce8  jz      short loc_18007CCF3
0x18007ccea  mov     rcx, rbx; hObject
0x18007cced  call    cs:__imp_CloseHandle
0x18007ccf3  mov     eax, r14d
0x18007ccf6  jmp     short loc_18007CD31
0x18007ccf8  mov     al, byte ptr [rbp+var_30+1]
0x18007ccfb  mov     cl, al
0x18007ccfd  and     cl, 7
0x18007cd00  sub     cl, sil
0x18007cd03  cmp     cl, sil
0x18007cd06  ja      short loc_18007CD0E
0x18007cd08  and     al, 0F0h
0x18007cd0a  cmp     al, 30h ; '0'
0x18007cd0c  jz      short loc_18007CD10
0x18007cd0e  xor     esi, esi
0x18007cd10  mov     [r15], esi
0x18007cd13  test    rdi, rdi
0x18007cd16  jz      short loc_18007CD21
0x18007cd18  mov     rcx, rdi; hObject
0x18007cd1b  call    cs:__imp_CloseHandle
0x18007cd21  test    rbx, rbx
0x18007cd24  jz      short loc_18007CD2F
0x18007cd26  mov     rcx, rbx; hObject
0x18007cd29  call    cs:__imp_CloseHandle
0x18007cd2f  xor     eax, eax
0x18007cd31  mov     rcx, [rbp+var_10]
0x18007cd35  xor     rcx, rsp; StackCookie
0x18007cd38  call    __security_check_cookie
0x18007cd3d  mov     rbx, [rsp+60h+arg_0]
0x18007cd45  add     rsp, 60h
0x18007cd49  pop     r15
0x18007cd4b  pop     r14
0x18007cd4d  pop     rdi
0x18007cd4e  pop     rsi
0x18007cd4f  pop     rbp
0x18007cd50  retn
```
