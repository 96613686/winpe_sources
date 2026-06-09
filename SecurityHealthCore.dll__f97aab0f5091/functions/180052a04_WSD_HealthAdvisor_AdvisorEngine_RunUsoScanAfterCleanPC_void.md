# WSD::HealthAdvisor::AdvisorEngine::RunUsoScanAfterCleanPC(void)

- ea: `0x180052a04`
- end: `0x180052d14`
- name: `?RunUsoScanAfterCleanPC@AdvisorEngine@HealthAdvisor@WSD@@AEAAJXZ`
- size: `784`
- prototype: `__int64 __fastcall(WSD::HealthAdvisor::AdvisorEngine *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800516c0`

## callees

- `0x180004ae0`
- `0x18000517c`
- `0x18000d7fc`
- `0x18000e288`
- `0x18000f02c`
- `0x18000f094`
- `0x18004ea54`
- `0x180052a04`
- `0x180052f0c`
- `0x1800dab80`
- `0x1800df798`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180052c5d`
- `KERNEL32!GetLastError` at `0x180052c5d`
- `KERNEL32!CloseHandle` at `0x180052b0a`
- `KERNEL32!CloseHandle` at `0x180052cf4`
- `KERNEL32!CloseHandle` at `0x180052b0a`
- `KERNEL32!CloseHandle` at `0x180052cf4`
- `KERNEL32!UnregisterWaitUntilOOBECompleted` at `0x180052a30`
- `KERNEL32!UnregisterWaitUntilOOBECompleted` at `0x180052a30`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180052c53`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180052c53`
- `USERENV!CreateEnvironmentBlock` at `0x180052b25`
- `USERENV!CreateEnvironmentBlock` at `0x180052b25`
- `USERENV!DestroyEnvironmentBlock` at `0x180052b74`
- `USERENV!DestroyEnvironmentBlock` at `0x180052ce5`
- `USERENV!DestroyEnvironmentBlock` at `0x180052b74`
- `USERENV!DestroyEnvironmentBlock` at `0x180052ce5`

## string_xrefs

- `0x180052a55`: `%windir%\system32\UsoClient.exe startscan`

## pseudocode

```c
__int64 __fastcall WSD::HealthAdvisor::AdvisorEngine::RunUsoScanAfterCleanPC(WSD::HealthAdvisor::AdvisorEngine *this)
{
  const unsigned __int16 *v2; // r8
  int v3; // eax
  void **v4; // rdx
  unsigned __int16 *v5; // r8
  unsigned __int16 *v6; // r9
  unsigned int v7; // ebx
  const struct std::nothrow_t *v8; // rdx
  int v10; // eax
  int LastError; // eax
  LPWSTR v12; // rbx
  unsigned int v13; // edx
  WSD::HealthAdvisor::AdvisorEngine *v14; // rcx
  signed int v15; // eax
  signed int v16; // edi
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  const struct std::nothrow_t *v19; // rdx
  unsigned __int16 *lpThreadAttributes; // [rsp+20h] [rbp-E0h]
  BOOL bInheritHandles; // [rsp+28h] [rbp-D8h]
  DWORD dwCreationFlags; // [rsp+30h] [rbp-D0h]
  int v23; // [rsp+5Ch] [rbp-A4h]
  const int *v24; // [rsp+60h] [rbp-A0h] BYREF
  int v25; // [rsp+68h] [rbp-98h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  int v27; // [rsp+8Ch] [rbp-74h]
  void **v28; // [rsp+90h] [rbp-70h]
  _BYTE v29[24]; // [rsp+98h] [rbp-68h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE hObject; // [rsp+140h] [rbp+40h] BYREF
  LPVOID Environment; // [rsp+148h] [rbp+48h] BYREF
  LPWSTR lpCommandLine; // [rsp+150h] [rbp+50h] BYREF

  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v29,
    (char *)this + 16);
  if ( *((_QWORD *)this + 39) )
  {
    UnregisterWaitUntilOOBECompleted();
    *((_QWORD *)this + 39) = 0;
  }
  *((_BYTE *)this + 320) = 1;
  v29[16] = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v29);
  lpCommandLine = 0;
  v3 = CommonUtil::UtilExpandEnvironmentStrings(
         (CommonUtil *)&lpCommandLine,
         (unsigned __int16 **)L"%windir%\\system32\\UsoClient.exe startscan",
         v2);
  v7 = v3;
  if ( v3 < 0 )
  {
    v8 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        142,
        &WPP_c72c2497aa103f1ab2c2d1c6f803c9ad_Traceguids,
        (unsigned int)v3);
LABEL_7:
    if ( lpCommandLine )
      operator delete(lpCommandLine, v8);
    return v7;
  }
  hObject = 0;
  v10 = CommonUtil::UtilLogonUser(
          (CommonUtil *)&hObject,
          v4,
          v5,
          v6,
          lpThreadAttributes,
          bInheritHandles,
          dwCreationFlags);
  v7 = v10;
  if ( v10 < 0 )
  {
    v8 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        143,
        &WPP_c72c2497aa103f1ab2c2d1c6f803c9ad_Traceguids,
        (unsigned int)v10);
LABEL_14:
    if ( hObject )
      CloseHandle(hObject);
    goto LABEL_7;
  }
  Environment = 0;
  if ( !CreateEnvironmentBlock(&Environment, hObject, 0) )
  {
    LastError = HrGetLastError();
    v7 = LastError;
    if ( LastError < 0 )
    {
      v8 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          144,
          &WPP_c72c2497aa103f1ab2c2d1c6f803c9ad_Traceguids,
          (unsigned int)LastError);
      if ( Environment )
        DestroyEnvironmentBlock(Environment);
      goto LABEL_14;
    }
  }
  v27 = 24;
  v24 = &WSD::HealthAdvisor::CAutoProcessInformation::`vbtable';
  v28 = &CRefCountedBaseX::`vftable';
  v25 = 0;
  *(const int **)((char *)&v24 + *(&WSD::HealthAdvisor::CAutoProcessInformation::`vbtable' + 1)) = (const int *)&CRefCountedBase::`vftable';
  *(int *)((char *)&v23 + v24[1]) = v24[1] - 24;
  *(const int **)((char *)&v24 + v24[1]) = (const int *)&WSD::HealthAdvisor::CAutoProcessInformation::`vftable';
  *(int *)((char *)&v23 + v24[1]) = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  v12 = lpCommandLine;
  if ( CreateProcessAsUserW(
         hObject,
         0,
         lpCommandLine,
         0,
         0,
         0,
         0x428u,
         Environment,
         0,
         &StartupInfo,
         &ProcessInformation) )
  {
    goto LABEL_30;
  }
  v15 = GetLastError();
  v16 = v15;
  if ( v15 > 0 )
    v16 = (unsigned __int16)v15 | 0x80070000;
  if ( v16 >= 0 )
  {
LABEL_30:
    v16 = WSD::HealthAdvisor::AdvisorEngine::SetBootAfterCleanPCRegistry(v14, v13);
    if ( v16 >= 0 )
      goto LABEL_35;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_35;
    v18 = 146;
  }
  else
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_35;
    v18 = 145;
  }
  WPP_SF_d(v17[2], v18, &WPP_c72c2497aa103f1ab2c2d1c6f803c9ad_Traceguids, (unsigned int)v16);
LABEL_35:
  WSD::HealthAdvisor::CAutoProcessInformation::`vbase destructor'((WSD::HealthAdvisor::CAutoProcessInformation *)&v24);
  if ( Environment )
    DestroyEnvironmentBlock(Environment);
  if ( hObject )
    CloseHandle(hObject);
  if ( v12 )
    operator delete(v12, v19);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180052a04  push    rbp
0x180052a06  push    rbx
0x180052a07  push    rdi
0x180052a08  lea     rbp, [rsp-20h]
0x180052a0d  sub     rsp, 120h
0x180052a14  mov     rbx, rcx
0x180052a17  lea     rdx, [rcx+10h]
0x180052a1b  lea     rcx, [rbp+30h+var_98]
0x180052a1f  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x180052a24  mov     rcx, [rbx+138h]
0x180052a2b  test    rcx, rcx
0x180052a2e  jz      short loc_180052A41
0x180052a30  call    cs:__imp_UnregisterWaitUntilOOBECompleted
0x180052a36  mov     qword ptr [rbx+138h], 0
0x180052a41  lea     rcx, [rbp+30h+var_98]
0x180052a45  mov     byte ptr [rbx+140h], 1
0x180052a4c  mov     [rbp+30h+var_88], 0
0x180052a50  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x180052a55  lea     rdx, aWindirSystem32; "%windir%\\system32\\UsoClient.exe start"...
0x180052a5c  mov     [rbp+30h+lpCommandLine], 0
0x180052a64  lea     rcx, [rbp+30h+lpCommandLine]; this
0x180052a68  call    ?UtilExpandEnvironmentStrings@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::UtilExpandEnvironmentStrings(ushort * *,ushort const *)
0x180052a6d  mov     ebx, eax
0x180052a6f  test    eax, eax
0x180052a71  jns     short loc_180052AB9
0x180052a73  mov     rcx, cs:WPP_GLOBAL_Control
0x180052a7a  lea     rdx, WPP_GLOBAL_Control
0x180052a81  cmp     rcx, rdx
0x180052a84  jz      short loc_180052AA4
0x180052a86  test    byte ptr [rcx+1Ch], 1
0x180052a8a  jz      short loc_180052AA4
0x180052a8c  mov     rcx, [rcx+10h]
0x180052a90  lea     r8, WPP_c72c2497aa103f1ab2c2d1c6f803c9ad_Traceguids
0x180052a97  mov     edx, 8Eh
0x180052a9c  mov     r9d, eax
0x180052a9f  call    WPP_SF_d
0x180052aa4  mov     rcx, [rbp+30h+lpCommandLine]; void *
0x180052aa8  test    rcx, rcx
0x180052aab  jz      short loc_180052AB2
0x180052aad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180052ab2  mov     eax, ebx
0x180052ab4  jmp     loc_180052D09
0x180052ab9  lea     rcx, [rbp+30h+hObject]; this
0x180052abd  mov     [rbp+30h+hObject], 0
0x180052ac5  call    ?UtilLogonUser@CommonUtil@@YAJPEAPEAXPEAG11KK@Z; CommonUtil::UtilLogonUser(void * *,ushort *,ushort *,ushort *,ulong,ulong)
0x180052aca  mov     ebx, eax
0x180052acc  test    eax, eax
0x180052ace  jns     short loc_180052B12
0x180052ad0  mov     rcx, cs:WPP_GLOBAL_Control
0x180052ad7  lea     rdx, WPP_GLOBAL_Control
0x180052ade  cmp     rcx, rdx
0x180052ae1  jz      short loc_180052B01
0x180052ae3  test    byte ptr [rcx+1Ch], 1
0x180052ae7  jz      short loc_180052B01
0x180052ae9  mov     rcx, [rcx+10h]
0x180052aed  lea     r8, WPP_c72c2497aa103f1ab2c2d1c6f803c9ad_Traceguids
0x180052af4  mov     edx, 8Fh
0x180052af9  mov     r9d, eax
0x180052afc  call    WPP_SF_d
0x180052b01  mov     rcx, [rbp+30h+hObject]; hObject
0x180052b05  test    rcx, rcx
0x180052b08  jz      short loc_180052AA4
0x180052b0a  call    cs:__imp_CloseHandle
0x180052b10  jmp     short loc_180052AA4
0x180052b12  mov     rdx, [rbp+30h+hObject]; hToken
0x180052b16  lea     rcx, [rbp+30h+Environment]; lpEnvironment
0x180052b1a  xor     r8d, r8d; bInherit
0x180052b1d  mov     [rbp+30h+Environment], 0
0x180052b25  call    cs:__imp_CreateEnvironmentBlock
0x180052b2b  test    eax, eax
0x180052b2d  jnz     short loc_180052B7C
0x180052b2f  call    HrGetLastError
0x180052b34  mov     ebx, eax
0x180052b36  test    eax, eax
0x180052b38  jns     short loc_180052B7C
0x180052b3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180052b41  lea     rdx, WPP_GLOBAL_Control
0x180052b48  cmp     rcx, rdx
0x180052b4b  jz      short loc_180052B6B
0x180052b4d  test    byte ptr [rcx+1Ch], 1
0x180052b51  jz      short loc_180052B6B
0x180052b53  mov     rcx, [rcx+10h]
0x180052b57  lea     r8, WPP_c72c2497aa103f1ab2c2d1c6f803c9ad_Traceguids
0x180052b5e  mov     edx, 90h
0x180052b63  mov     r9d, eax
0x180052b66  call    WPP_SF_d
0x180052b6b  mov     rcx, [rbp+30h+Environment]; lpEnvironment
0x180052b6f  test    rcx, rcx
0x180052b72  jz      short loc_180052B01
0x180052b74  call    cs:__imp_DestroyEnvironmentBlock
0x180052b7a  jmp     short loc_180052B01
0x180052b7c  mov     [rbp+30h+var_A4], 18h
0x180052b83  lea     rcx, ??_8CAutoProcessInformation@HealthAdvisor@WSD@@7B@; const WSD::HealthAdvisor::CAutoProcessInformation::`vbtable'
0x180052b8a  mov     [rsp+130h+var_D0], rcx
0x180052b8f  lea     rax, ??_7CRefCountedBaseX@@6B@; const CRefCountedBaseX::`vftable'
0x180052b96  mov     [rbp+30h+var_A0], rax
0x180052b9a  xorps   xmm0, xmm0
0x180052b9d  mov     [rsp+130h+var_C8], 0
0x180052ba5  movsxd  rax, dword ptr [rcx+4]
0x180052ba9  lea     rcx, ??_7CRefCountedBase@@6B@; const CRefCountedBase::`vftable'
0x180052bb0  mov     [rsp+rax+130h+var_D0], rcx
0x180052bb5  mov     rax, [rsp+130h+var_D0]
0x180052bba  movsxd  rcx, dword ptr [rax+4]
0x180052bbe  lea     edx, [rcx-18h]
0x180052bc1  mov     [rsp+rcx+130h+var_D4], edx
0x180052bc5  xor     edx, edx; Val
0x180052bc7  mov     rax, [rsp+130h+var_D0]
0x180052bcc  movsxd  rcx, dword ptr [rax+4]
0x180052bd0  lea     rax, ??_7CAutoProcessInformation@HealthAdvisor@WSD@@6B@; const WSD::HealthAdvisor::CAutoProcessInformation::`vftable'
0x180052bd7  mov     [rsp+rcx+130h+var_D0], rax
0x180052bdc  mov     rax, [rsp+130h+var_D0]
0x180052be1  movsxd  rcx, dword ptr [rax+4]
0x180052be5  xor     eax, eax
0x180052be7  mov     [rsp+rcx+130h+var_D4], 0
0x180052bef  lea     r8d, [rax+68h]; Size
0x180052bf3  lea     rcx, [rbp+30h+StartupInfo]; void *
0x180052bf7  mov     qword ptr [rbp+30h+ProcessInformation.dwProcessId], rax
0x180052bfb  movups  xmmword ptr [rsp+130h+ProcessInformation.hProcess], xmm0
0x180052c00  call    memset_0
0x180052c05  mov     rax, [rbp+30h+Environment]
0x180052c09  lea     rcx, [rsp+130h+ProcessInformation]
0x180052c0e  mov     rbx, [rbp+30h+lpCommandLine]
0x180052c12  xor     r9d, r9d; lpProcessAttributes
0x180052c15  mov     [rsp+130h+lpProcessInformation], rcx; lpProcessInformation
0x180052c1a  mov     r8, rbx; lpCommandLine
0x180052c1d  lea     rcx, [rbp+30h+StartupInfo]
0x180052c21  xor     edx, edx; lpApplicationName
0x180052c23  mov     [rsp+130h+lpStartupInfo], rcx; lpStartupInfo
0x180052c28  mov     rcx, [rbp+30h+hObject]; hToken
0x180052c2c  mov     [rsp+130h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180052c35  mov     [rsp+130h+lpEnvironment], rax; lpEnvironment
0x180052c3a  mov     [rsp+130h+dwCreationFlags], 428h; dwCreationFlags
0x180052c42  mov     [rsp+130h+bInheritHandles], 0; bInheritHandles
0x180052c4a  mov     [rsp+130h+lpThreadAttributes], 0; lpThreadAttributes
0x180052c53  call    cs:__imp_CreateProcessAsUserW
0x180052c59  test    eax, eax
0x180052c5b  jnz     short loc_180052C96
0x180052c5d  call    cs:__imp_GetLastError
0x180052c63  mov     edi, eax
0x180052c65  test    eax, eax
0x180052c67  jle     short loc_180052C72
0x180052c69  movzx   edi, ax
0x180052c6c  or      edi, 80070000h
0x180052c72  test    edi, edi
0x180052c74  jns     short loc_180052C96
0x180052c76  mov     rcx, cs:WPP_GLOBAL_Control
0x180052c7d  lea     rdx, WPP_GLOBAL_Control
0x180052c84  cmp     rcx, rdx
0x180052c87  jz      short loc_180052CD2
0x180052c89  test    byte ptr [rcx+1Ch], 1
0x180052c8d  jz      short loc_180052CD2
0x180052c8f  mov     edx, 91h
0x180052c94  jmp     short loc_180052CBF
0x180052c96  call    ?SetBootAfterCleanPCRegistry@AdvisorEngine@HealthAdvisor@WSD@@AEAAJK@Z; WSD::HealthAdvisor::AdvisorEngine::SetBootAfterCleanPCRegistry(ulong)
0x180052c9b  mov     edi, eax
0x180052c9d  test    eax, eax
0x180052c9f  jns     short loc_180052CD2
0x180052ca1  mov     rcx, cs:WPP_GLOBAL_Control
0x180052ca8  lea     rdx, WPP_GLOBAL_Control
0x180052caf  cmp     rcx, rdx
0x180052cb2  jz      short loc_180052CD2
0x180052cb4  test    byte ptr [rcx+1Ch], 1
0x180052cb8  jz      short loc_180052CD2
0x180052cba  mov     edx, 92h
0x180052cbf  mov     rcx, [rcx+10h]
0x180052cc3  lea     r8, WPP_c72c2497aa103f1ab2c2d1c6f803c9ad_Traceguids
0x180052cca  mov     r9d, edi
0x180052ccd  call    WPP_SF_d
0x180052cd2  lea     rcx, [rsp+130h+var_D0]; this
0x180052cd7  call    ??_DCAutoProcessInformation@HealthAdvisor@WSD@@QEAAXXZ; WSD::HealthAdvisor::CAutoProcessInformation::`vbase destructor'(void)
0x180052cdc  mov     rcx, [rbp+30h+Environment]; lpEnvironment
0x180052ce0  test    rcx, rcx
0x180052ce3  jz      short loc_180052CEB
0x180052ce5  call    cs:__imp_DestroyEnvironmentBlock
0x180052ceb  mov     rcx, [rbp+30h+hObject]; hObject
0x180052cef  test    rcx, rcx
0x180052cf2  jz      short loc_180052CFA
0x180052cf4  call    cs:__imp_CloseHandle
0x180052cfa  test    rbx, rbx
0x180052cfd  jz      short loc_180052D07
0x180052cff  mov     rcx, rbx; void *
0x180052d02  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180052d07  mov     eax, edi
0x180052d09  add     rsp, 120h
0x180052d10  pop     rdi
0x180052d11  pop     rbx
0x180052d12  pop     rbp
0x180052d13  retn
```
