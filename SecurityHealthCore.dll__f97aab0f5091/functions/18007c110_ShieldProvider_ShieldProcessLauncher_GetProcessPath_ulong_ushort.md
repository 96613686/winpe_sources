# ShieldProvider::ShieldProcessLauncher::GetProcessPath(ulong,ushort * *)

- ea: `0x18007c110`
- end: `0x18007c4f8`
- name: `?GetProcessPath@ShieldProcessLauncher@ShieldProvider@@UEAAJKPEAPEAG@Z`
- size: `1000`
- prototype: `int(ShieldProvider::ShieldProcessLauncher *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180004710`
- `0x18000ccd4`
- `0x18000d7fc`
- `0x180011730`
- `0x18007c110`
- `0x1800d1e1c`
- `0x1800db4f4`
- `0x1800db5b8`
- `0x1800e1690`
- `0x1800e1764`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18007c27e`
- `KERNEL32!CloseHandle` at `0x18007c357`
- `KERNEL32!CloseHandle` at `0x18007c3ba`
- `KERNEL32!CloseHandle` at `0x18007c42c`
- `KERNEL32!CloseHandle` at `0x18007c43a`
- `KERNEL32!CloseHandle` at `0x18007c4bb`
- `KERNEL32!CloseHandle` at `0x18007c4c9`
- `KERNEL32!CloseHandle` at `0x18007c27e`
- `KERNEL32!CloseHandle` at `0x18007c357`
- `KERNEL32!CloseHandle` at `0x18007c3ba`
- `KERNEL32!CloseHandle` at `0x18007c42c`
- `KERNEL32!CloseHandle` at `0x18007c43a`
- `KERNEL32!CloseHandle` at `0x18007c4bb`
- `KERNEL32!CloseHandle` at `0x18007c4c9`
- `KERNEL32!GetCurrentProcess` at `0x18007c224`
- `KERNEL32!GetCurrentProcess` at `0x18007c224`
- `KERNEL32!QueryFullProcessImageNameW` at `0x18007c3de`
- `KERNEL32!QueryFullProcessImageNameW` at `0x18007c3de`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18007c309`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18007c309`
- `ole32!CoTaskMemFree` at `0x18007c4a0`
- `ole32!CoTaskMemFree` at `0x18007c4a0`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18007c2ad`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18007c2ad`

## string_xrefs

- `0x18007c294`: `SeDebugPrivilege`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ShieldProcessLauncher::GetProcessPath(
        ShieldProvider::ShieldProcessLauncher *this,
        unsigned int a2,
        HANDLE *a3)
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
  HANDLE v16; // rbx
  unsigned int v17; // r8d
  unsigned int v18; // r9d
  int v19; // eax
  unsigned int v20; // edi
  int v21; // eax
  HANDLE v22; // rdi
  unsigned __int16 *v23; // r8
  int v24; // eax
  unsigned int v25; // esi
  int v26; // eax
  unsigned __int16 v27; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-C8h] BYREF
  DWORD dwSize; // [rsp+40h] [rbp-C0h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR ExeName[264]; // [rsp+60h] [rbp-A0h] BYREF

  hObject = 0;
  v5 = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(&hObject);
  LastFailure = v5;
  if ( v5 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    v9 = 89;
    goto LABEL_5;
  }
  LOBYTE(v27) = 0;
  v5 = ShieldProvider::CheckCallerIdentity(L"S-1-5-80-3232712927-1625117661-2590453128-1738570065-3637376297", &v27, v6);
  LastFailure = v5;
  if ( v5 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    v9 = 90;
LABEL_5:
    v10 = (unsigned int)v5;
LABEL_14:
    WPP_SF_d(v8[2], v9, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids, v10);
LABEL_15:
    CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&hObject);
    return (unsigned int)LastFailure;
  }
  if ( !(_BYTE)v27 )
  {
    v8 = WPP_GLOBAL_Control;
    LastFailure = -2147024891;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    v9 = 91;
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
      v15 = 92;
LABEL_21:
      WPP_SF_d(v14[2], v15, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids, (unsigned int)LastFailure);
      goto LABEL_22;
    }
    goto LABEL_22;
  }
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
        v15 = 93;
        goto LABEL_21;
      }
LABEL_22:
      if ( hObject )
        CloseHandle(hObject);
      return (unsigned int)LastFailure;
    }
  }
  v16 = hObject;
  if ( !AdjustTokenPrivileges(hObject, 0, &NewState, 0, 0, 0) )
  {
    v19 = HrGetLastFailure();
    v20 = v19;
    if ( v19 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          94,
          WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids,
          (unsigned int)v19);
LABEL_34:
      if ( v16 )
        CloseHandle(v16);
      return v20;
    }
  }
  hObject = 0;
  v21 = CommonUtil::UtilOpenProcess((CommonUtil *)&hObject, (void **)a2, v17, v18);
  v20 = v21;
  if ( v21 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        95,
        WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids,
        (unsigned int)v21);
    if ( hObject )
      CloseHandle(hObject);
    goto LABEL_34;
  }
  v22 = hObject;
  dwSize = 260;
  if ( !QueryFullProcessImageNameW(hObject, 0, ExeName, &dwSize) )
  {
    v24 = HrGetLastFailure();
    v25 = v24;
    if ( v24 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          96,
          WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids,
          (unsigned int)v24);
LABEL_48:
      if ( v22 )
        CloseHandle(v22);
      if ( v16 )
        CloseHandle(v16);
      return v25;
    }
  }
  hObject = 0;
  v26 = CommonUtil::UtilCoDuplicateString((CommonUtil *)&hObject, (unsigned __int16 **)ExeName, v23);
  v25 = v26;
  if ( v26 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        97,
        WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids,
        (unsigned int)v26);
    if ( hObject )
      CoTaskMemFree(hObject);
    goto LABEL_48;
  }
  *a3 = hObject;
  if ( v22 )
    CloseHandle(v22);
  if ( v16 )
    CloseHandle(v16);
  return 0;
}

```

## disassembly

```asm
0x18007c110  mov     [rsp-8+arg_0], rbx
0x18007c115  mov     [rsp-8+arg_18], rsi
0x18007c11a  push    rbp
0x18007c11b  push    rdi
0x18007c11c  push    r14
0x18007c11e  lea     rbp, [rsp-180h]
0x18007c126  sub     rsp, 280h
0x18007c12d  mov     rax, cs:__security_cookie
0x18007c134  xor     rax, rsp
0x18007c137  mov     [rbp+190h+var_20], rax
0x18007c13e  lea     rcx, [rsp+290h+hObject]
0x18007c143  mov     [rsp+290h+hObject], 0
0x18007c14c  mov     r14, r8
0x18007c14f  mov     esi, edx
0x18007c151  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x18007c156  mov     ebx, eax
0x18007c158  test    eax, eax
0x18007c15a  jns     short loc_18007C187
0x18007c15c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c163  lea     rdx, WPP_GLOBAL_Control
0x18007c16a  cmp     rcx, rdx
0x18007c16d  jz      loc_18007C200
0x18007c173  test    byte ptr [rcx+1Ch], 1
0x18007c177  jz      loc_18007C200
0x18007c17d  mov     edx, 59h ; 'Y'
0x18007c182  mov     r9d, eax
0x18007c185  jmp     short loc_18007C1F0
0x18007c187  lea     rdx, [rsp+290h+var_260]; unsigned __int16 *
0x18007c18c  mov     byte ptr [rsp+290h+var_260], 0
0x18007c191  lea     rcx, aS1580323271292; "S-1-5-80-3232712927-1625117661-25904531"...
0x18007c198  call    ?CheckCallerIdentity@ShieldProvider@@YAJPEBGPEA_N@Z; ShieldProvider::CheckCallerIdentity(ushort const *,bool *)
0x18007c19d  mov     ebx, eax
0x18007c19f  test    eax, eax
0x18007c1a1  jns     short loc_18007C1C3
0x18007c1a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c1aa  lea     rdx, WPP_GLOBAL_Control
0x18007c1b1  cmp     rcx, rdx
0x18007c1b4  jz      short loc_18007C200
0x18007c1b6  test    byte ptr [rcx+1Ch], 1
0x18007c1ba  jz      short loc_18007C200
0x18007c1bc  mov     edx, 5Ah ; 'Z'
0x18007c1c1  jmp     short loc_18007C182
0x18007c1c3  cmp     byte ptr [rsp+290h+var_260], 0
0x18007c1c8  jnz     short loc_18007C211
0x18007c1ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c1d1  lea     rdx, WPP_GLOBAL_Control
0x18007c1d8  mov     ebx, 80070005h
0x18007c1dd  cmp     rcx, rdx
0x18007c1e0  jz      short loc_18007C200
0x18007c1e2  test    byte ptr [rcx+1Ch], 1
0x18007c1e6  jz      short loc_18007C200
0x18007c1e8  mov     edx, 5Bh ; '['
0x18007c1ed  mov     r9d, ebx
0x18007c1f0  mov     rcx, [rcx+10h]
0x18007c1f4  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007c1fb  call    WPP_SF_d
0x18007c200  lea     rcx, [rsp+290h+hObject]
0x18007c205  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x18007c20a  mov     eax, ebx
0x18007c20c  jmp     loc_18007C4D1
0x18007c211  lea     rcx, [rsp+290h+hObject]
0x18007c216  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x18007c21b  mov     [rsp+290h+hObject], 0
0x18007c224  call    cs:__imp_GetCurrentProcess
0x18007c22a  mov     r8d, 20h ; ' '; void *
0x18007c230  lea     rcx, [rsp+290h+hObject]; this
0x18007c235  mov     rdx, rax; void **
0x18007c238  call    ?UtilOpenProcessToken@CommonUtil@@YAJPEAPEAXPEAXK@Z; CommonUtil::UtilOpenProcessToken(void * *,void *,ulong)
0x18007c23d  mov     ebx, eax
0x18007c23f  test    eax, eax
0x18007c241  jns     short loc_18007C286
0x18007c243  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c24a  lea     rdx, WPP_GLOBAL_Control
0x18007c251  cmp     rcx, rdx
0x18007c254  jz      short loc_18007C274
0x18007c256  test    byte ptr [rcx+1Ch], 1
0x18007c25a  jz      short loc_18007C274
0x18007c25c  mov     edx, 5Ch ; '\'
0x18007c261  mov     rcx, [rcx+10h]
0x18007c265  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007c26c  mov     r9d, ebx
0x18007c26f  call    WPP_SF_d
0x18007c274  mov     rcx, [rsp+290h+hObject]; hObject
0x18007c279  test    rcx, rcx
0x18007c27c  jz      short loc_18007C20A
0x18007c27e  call    cs:__imp_CloseHandle
0x18007c284  jmp     short loc_18007C20A
0x18007c286  lea     r8, [rsp+290h+NewState.Privileges]; lpLuid
0x18007c28b  mov     qword ptr [rsp+290h+NewState.Privileges.Luid.LowPart], 0
0x18007c294  lea     rdx, Name; "SeDebugPrivilege"
0x18007c29b  mov     [rsp+290h+NewState.PrivilegeCount], 1
0x18007c2a3  xor     ecx, ecx; lpSystemName
0x18007c2a5  mov     [rsp+290h+NewState.Privileges.Attributes], 2
0x18007c2ad  call    cs:__imp_LookupPrivilegeValueW
0x18007c2b3  test    eax, eax
0x18007c2b5  jnz     short loc_18007C2E5
0x18007c2b7  call    HrGetLastFailure
0x18007c2bc  mov     ebx, eax
0x18007c2be  test    eax, eax
0x18007c2c0  jns     short loc_18007C2E5
0x18007c2c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c2c9  lea     rdx, WPP_GLOBAL_Control
0x18007c2d0  cmp     rcx, rdx
0x18007c2d3  jz      short loc_18007C274
0x18007c2d5  test    byte ptr [rcx+1Ch], 1
0x18007c2d9  jz      short loc_18007C274
0x18007c2db  mov     edx, 5Dh ; ']'
0x18007c2e0  jmp     loc_18007C261
0x18007c2e5  mov     rbx, [rsp+290h+hObject]
0x18007c2ea  lea     r8, [rsp+290h+NewState]; NewState
0x18007c2ef  mov     rcx, rbx; TokenHandle
0x18007c2f2  mov     [rsp+290h+ReturnLength], 0; ReturnLength
0x18007c2fb  xor     r9d, r9d; BufferLength
0x18007c2fe  mov     [rsp+290h+PreviousState], 0; PreviousState
0x18007c307  xor     edx, edx; DisableAllPrivileges
0x18007c309  call    cs:__imp_AdjustTokenPrivileges
0x18007c30f  test    eax, eax
0x18007c311  jnz     short loc_18007C364
0x18007c313  call    HrGetLastFailure
0x18007c318  mov     edi, eax
0x18007c31a  test    eax, eax
0x18007c31c  jns     short loc_18007C364
0x18007c31e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c325  lea     rdx, WPP_GLOBAL_Control
0x18007c32c  cmp     rcx, rdx
0x18007c32f  jz      short loc_18007C34F
0x18007c331  test    byte ptr [rcx+1Ch], 1
0x18007c335  jz      short loc_18007C34F
0x18007c337  mov     rcx, [rcx+10h]
0x18007c33b  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007c342  mov     edx, 5Eh ; '^'
0x18007c347  mov     r9d, eax
0x18007c34a  call    WPP_SF_d
0x18007c34f  test    rbx, rbx
0x18007c352  jz      short loc_18007C35D
0x18007c354  mov     rcx, rbx; hObject
0x18007c357  call    cs:__imp_CloseHandle
0x18007c35d  mov     eax, edi
0x18007c35f  jmp     loc_18007C4D1
0x18007c364  mov     edx, esi; void **
0x18007c366  mov     [rsp+290h+hObject], 0
0x18007c36f  lea     rcx, [rsp+290h+hObject]; this
0x18007c374  call    ?UtilOpenProcess@CommonUtil@@YAJPEAPEAXKK@Z; CommonUtil::UtilOpenProcess(void * *,ulong,ulong)
0x18007c379  mov     edi, eax
0x18007c37b  test    eax, eax
0x18007c37d  jns     short loc_18007C3C2
0x18007c37f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c386  lea     rdx, WPP_GLOBAL_Control
0x18007c38d  cmp     rcx, rdx
0x18007c390  jz      short loc_18007C3B0
0x18007c392  test    byte ptr [rcx+1Ch], 1
0x18007c396  jz      short loc_18007C3B0
0x18007c398  mov     rcx, [rcx+10h]
0x18007c39c  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007c3a3  mov     edx, 5Fh ; '_'
0x18007c3a8  mov     r9d, eax
0x18007c3ab  call    WPP_SF_d
0x18007c3b0  mov     rcx, [rsp+290h+hObject]; hObject
0x18007c3b5  test    rcx, rcx
0x18007c3b8  jz      short loc_18007C34F
0x18007c3ba  call    cs:__imp_CloseHandle
0x18007c3c0  jmp     short loc_18007C34F
0x18007c3c2  mov     rdi, [rsp+290h+hObject]
0x18007c3c7  lea     r9, [rsp+290h+dwSize]; lpdwSize
0x18007c3cc  mov     rcx, rdi; hProcess
0x18007c3cf  mov     [rsp+290h+dwSize], 104h
0x18007c3d7  lea     r8, [rsp+290h+ExeName]; lpExeName
0x18007c3dc  xor     edx, edx; dwFlags
0x18007c3de  call    cs:__imp_QueryFullProcessImageNameW
0x18007c3e4  test    eax, eax
0x18007c3e6  jnz     short loc_18007C447
0x18007c3e8  call    HrGetLastFailure
0x18007c3ed  mov     esi, eax
0x18007c3ef  test    eax, eax
0x18007c3f1  jns     short loc_18007C447
0x18007c3f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c3fa  lea     rdx, WPP_GLOBAL_Control
0x18007c401  cmp     rcx, rdx
0x18007c404  jz      short loc_18007C424
0x18007c406  test    byte ptr [rcx+1Ch], 1
0x18007c40a  jz      short loc_18007C424
0x18007c40c  mov     rcx, [rcx+10h]
0x18007c410  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007c417  mov     edx, 60h ; '`'
0x18007c41c  mov     r9d, eax
0x18007c41f  call    WPP_SF_d
0x18007c424  test    rdi, rdi
0x18007c427  jz      short loc_18007C432
0x18007c429  mov     rcx, rdi; hObject
0x18007c42c  call    cs:__imp_CloseHandle
0x18007c432  test    rbx, rbx
0x18007c435  jz      short loc_18007C440
0x18007c437  mov     rcx, rbx; hObject
0x18007c43a  call    cs:__imp_CloseHandle
0x18007c440  mov     eax, esi
0x18007c442  jmp     loc_18007C4D1
0x18007c447  lea     rdx, [rsp+290h+ExeName]; unsigned __int16 **
0x18007c44c  mov     [rsp+290h+hObject], 0
0x18007c455  lea     rcx, [rsp+290h+hObject]; this
0x18007c45a  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x18007c45f  mov     esi, eax
0x18007c461  test    eax, eax
0x18007c463  jns     short loc_18007C4AB
0x18007c465  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c46c  lea     rdx, WPP_GLOBAL_Control
0x18007c473  cmp     rcx, rdx
0x18007c476  jz      short loc_18007C496
0x18007c478  test    byte ptr [rcx+1Ch], 1
0x18007c47c  jz      short loc_18007C496
0x18007c47e  mov     rcx, [rcx+10h]
0x18007c482  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007c489  mov     edx, 61h ; 'a'
0x18007c48e  mov     r9d, eax
0x18007c491  call    WPP_SF_d
0x18007c496  mov     rcx, [rsp+290h+hObject]; pv
0x18007c49b  test    rcx, rcx
0x18007c49e  jz      short loc_18007C424
0x18007c4a0  call    cs:__imp_CoTaskMemFree
0x18007c4a6  jmp     loc_18007C424
0x18007c4ab  mov     rax, [rsp+290h+hObject]
0x18007c4b0  mov     [r14], rax
0x18007c4b3  test    rdi, rdi
0x18007c4b6  jz      short loc_18007C4C1
0x18007c4b8  mov     rcx, rdi; hObject
0x18007c4bb  call    cs:__imp_CloseHandle
0x18007c4c1  test    rbx, rbx
0x18007c4c4  jz      short loc_18007C4CF
0x18007c4c6  mov     rcx, rbx; hObject
0x18007c4c9  call    cs:__imp_CloseHandle
0x18007c4cf  xor     eax, eax
0x18007c4d1  mov     rcx, [rbp+190h+var_20]
0x18007c4d8  xor     rcx, rsp; StackCookie
0x18007c4db  call    __security_check_cookie
0x18007c4e0  lea     r11, [rsp+290h+var_10]
0x18007c4e8  mov     rbx, [r11+20h]
0x18007c4ec  mov     rsi, [r11+38h]
0x18007c4f0  mov     rsp, r11
0x18007c4f3  pop     r14
0x18007c4f5  pop     rdi
0x18007c4f6  pop     rbp
0x18007c4f7  retn
```
