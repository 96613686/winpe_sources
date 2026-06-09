# ShieldProvider::RestartDevice(ulong)

- ea: `0x1800d3350`
- end: `0x1800d3564`
- name: `?RestartDevice@ShieldProvider@@YAJK@Z`
- size: `532`
- prototype: `__int64 __fastcall(ShieldProvider *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180094a90`
- `0x1800b9220`
- `0x1800cb390`

## callees

- `0x18000ccd4`
- `0x18000d7fc`
- `0x180011730`
- `0x1800d3350`
- `0x1800def88`
- `0x1800df118`
- `0x1800e1690`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800d348a`
- `KERNEL32!CloseHandle` at `0x1800d34a9`
- `KERNEL32!CloseHandle` at `0x1800d348a`
- `KERNEL32!CloseHandle` at `0x1800d34a9`
- `KERNEL32!GetCurrentThread` at `0x1800d33be`
- `KERNEL32!GetCurrentThread` at `0x1800d33be`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d33d2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d33d2`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x1800d351a`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x1800d351a`

## string_xrefs

- `0x1800d34b8`: `SeShutdownPrivilege`

## pseudocode

```c
__int64 __fastcall ShieldProvider::RestartDevice(ShieldProvider *this)
{
  int v1; // eax
  unsigned int v2; // ebx
  HANDLE CurrentThread; // rax
  void *v4; // r8
  unsigned int v5; // r9d
  int LastFailure; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  const unsigned __int16 *v11; // rdx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  BOOL bRebootAfterShutdown; // [rsp+20h] [rbp-10h]
  int v15; // [rsp+40h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+18h] BYREF
  __int64 v17; // [rsp+50h] [rbp+20h] BYREF

  v15 = (int)this;
  v17 = 0;
  v1 = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(&v17);
  v2 = v1;
  if ( v1 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids,
        (unsigned int)v1);
LABEL_22:
    CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&v17);
    return v2;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    LastFailure = HrGetLastFailure();
    v2 = LastFailure;
    if ( LastFailure < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 44;
LABEL_10:
        v9 = (unsigned int)LastFailure;
LABEL_19:
        WPP_SF_d(v7[2], v8, WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids, v9);
        goto LABEL_20;
      }
      goto LABEL_20;
    }
  }
  LOBYTE(v15) = 0;
  LastFailure = CommonUtil::UtilCheckTokenMembershipByRid(
                  (CommonUtil *)&v15,
                  (bool *)TokenHandle,
                  v4,
                  v5,
                  bRebootAfterShutdown);
  v2 = LastFailure;
  if ( LastFailure < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 45;
      goto LABEL_10;
    }
LABEL_20:
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    goto LABEL_22;
  }
  if ( !(_BYTE)v15 )
  {
    v7 = WPP_GLOBAL_Control;
    v2 = -2147024891;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 46;
      v9 = 2147942405LL;
      goto LABEL_19;
    }
    goto LABEL_20;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&v17);
  v2 = CommonUtil::UtilAcquirePrivilege(L"SeShutdownPrivilege", v11);
  if ( (v2 & 0x80000000) != 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v2;
    v13 = 47;
    goto LABEL_30;
  }
  if ( !InitiateSystemShutdownExW(0, 0, 0, 1, 1, 0x50013u) )
  {
    v2 = HrGetLastFailure();
    if ( (v2 & 0x80000000) != 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v2;
      v13 = 48;
LABEL_30:
      WPP_SF_d(v12[2], v13, WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids, v2);
      return v2;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800d3350  mov     [rsp-8+arg_18], rbx
0x1800d3355  mov     [rsp-8+arg_0], ecx
0x1800d3359  push    rbp
0x1800d335a  mov     rbp, rsp
0x1800d335d  sub     rsp, 30h
0x1800d3361  lea     rcx, [rbp+arg_10]
0x1800d3365  mov     [rbp+arg_10], 0
0x1800d336d  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x1800d3372  mov     ebx, eax
0x1800d3374  test    eax, eax
0x1800d3376  jns     short loc_1800D33B6
0x1800d3378  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d337f  lea     rdx, WPP_GLOBAL_Control
0x1800d3386  cmp     rcx, rdx
0x1800d3389  jz      loc_1800D3490
0x1800d338f  test    byte ptr [rcx+1Ch], 1
0x1800d3393  jz      loc_1800D3490
0x1800d3399  mov     rcx, [rcx+10h]
0x1800d339d  lea     r8, WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids
0x1800d33a4  mov     edx, 2Bh ; '+'
0x1800d33a9  mov     r9d, eax
0x1800d33ac  call    WPP_SF_d
0x1800d33b1  jmp     loc_1800D3490
0x1800d33b6  mov     [rbp+TokenHandle], 0
0x1800d33be  call    cs:__imp_GetCurrentThread
0x1800d33c4  xor     r8d, r8d; OpenAsSelf
0x1800d33c7  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800d33cb  mov     rcx, rax; ThreadHandle
0x1800d33ce  lea     edx, [r8+8]; DesiredAccess
0x1800d33d2  call    cs:__imp_OpenThreadToken
0x1800d33d8  test    eax, eax
0x1800d33da  jnz     short loc_1800D340E
0x1800d33dc  call    HrGetLastFailure
0x1800d33e1  mov     ebx, eax
0x1800d33e3  test    eax, eax
0x1800d33e5  jns     short loc_1800D340E
0x1800d33e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d33ee  lea     rdx, WPP_GLOBAL_Control
0x1800d33f5  cmp     rcx, rdx
0x1800d33f8  jz      loc_1800D3481
0x1800d33fe  test    byte ptr [rcx+1Ch], 1
0x1800d3402  jz      short loc_1800D3481
0x1800d3404  mov     edx, 2Ch ; ','
0x1800d3409  mov     r9d, eax
0x1800d340c  jmp     short loc_1800D3471
0x1800d340e  mov     rdx, [rbp+TokenHandle]; bool *
0x1800d3412  lea     rcx, [rbp+arg_0]; this
0x1800d3416  mov     byte ptr [rbp+arg_0], 0
0x1800d341a  call    ?UtilCheckTokenMembershipByRid@CommonUtil@@YAJPEA_NPEAXKK@Z; CommonUtil::UtilCheckTokenMembershipByRid(bool *,void *,ulong,ulong)
0x1800d341f  mov     ebx, eax
0x1800d3421  test    eax, eax
0x1800d3423  jns     short loc_1800D3445
0x1800d3425  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d342c  lea     rdx, WPP_GLOBAL_Control
0x1800d3433  cmp     rcx, rdx
0x1800d3436  jz      short loc_1800D3481
0x1800d3438  test    byte ptr [rcx+1Ch], 1
0x1800d343c  jz      short loc_1800D3481
0x1800d343e  mov     edx, 2Dh ; '-'
0x1800d3443  jmp     short loc_1800D3409
0x1800d3445  cmp     byte ptr [rbp+arg_0], 0
0x1800d3449  jnz     short loc_1800D34A0
0x1800d344b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d3452  lea     rdx, WPP_GLOBAL_Control
0x1800d3459  mov     ebx, 80070005h
0x1800d345e  cmp     rcx, rdx
0x1800d3461  jz      short loc_1800D3481
0x1800d3463  test    byte ptr [rcx+1Ch], 1
0x1800d3467  jz      short loc_1800D3481
0x1800d3469  mov     edx, 2Eh ; '.'
0x1800d346e  mov     r9d, ebx
0x1800d3471  mov     rcx, [rcx+10h]
0x1800d3475  lea     r8, WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids
0x1800d347c  call    WPP_SF_d
0x1800d3481  mov     rcx, [rbp+TokenHandle]; hObject
0x1800d3485  test    rcx, rcx
0x1800d3488  jz      short loc_1800D3490
0x1800d348a  call    cs:__imp_CloseHandle
0x1800d3490  lea     rcx, [rbp+arg_10]
0x1800d3494  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x1800d3499  mov     eax, ebx
0x1800d349b  jmp     loc_1800D3559
0x1800d34a0  mov     rcx, [rbp+TokenHandle]; hObject
0x1800d34a4  test    rcx, rcx
0x1800d34a7  jz      short loc_1800D34AF
0x1800d34a9  call    cs:__imp_CloseHandle
0x1800d34af  lea     rcx, [rbp+arg_10]
0x1800d34b3  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x1800d34b8  lea     rcx, aSeshutdownpriv; "SeShutdownPrivilege"
0x1800d34bf  call    ?UtilAcquirePrivilege@CommonUtil@@YAJPEBG@Z; CommonUtil::UtilAcquirePrivilege(ushort const *)
0x1800d34c4  mov     ebx, eax
0x1800d34c6  test    eax, eax
0x1800d34c8  jns     short loc_1800D34FD
0x1800d34ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d34d1  lea     rdx, WPP_GLOBAL_Control
0x1800d34d8  cmp     rcx, rdx
0x1800d34db  jz      short loc_1800D3499
0x1800d34dd  test    byte ptr [rcx+1Ch], 1
0x1800d34e1  jz      short loc_1800D3499
0x1800d34e3  mov     edx, 2Fh ; '/'
0x1800d34e8  mov     rcx, [rcx+10h]
0x1800d34ec  lea     r8, WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids
0x1800d34f3  mov     r9d, ebx
0x1800d34f6  call    WPP_SF_d
0x1800d34fb  jmp     short loc_1800D3499
0x1800d34fd  mov     [rsp+30h+dwReason], 50013h; dwReason
0x1800d3505  mov     r9d, 1; bForceAppsClosed
0x1800d350b  xor     r8d, r8d; dwTimeout
0x1800d350e  mov     [rsp+30h+bRebootAfterShutdown], 1; bRebootAfterShutdown
0x1800d3516  xor     edx, edx; lpMessage
0x1800d3518  xor     ecx, ecx; lpMachineName
0x1800d351a  call    cs:__imp_InitiateSystemShutdownExW
0x1800d3520  test    eax, eax
0x1800d3522  jnz     short loc_1800D3557
0x1800d3524  call    HrGetLastFailure
0x1800d3529  mov     ebx, eax
0x1800d352b  test    eax, eax
0x1800d352d  jns     short loc_1800D3557
0x1800d352f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d3536  lea     rdx, WPP_GLOBAL_Control
0x1800d353d  cmp     rcx, rdx
0x1800d3540  jz      loc_1800D3499
0x1800d3546  test    byte ptr [rcx+1Ch], 1
0x1800d354a  jz      loc_1800D3499
0x1800d3550  mov     edx, 30h ; '0'
0x1800d3555  jmp     short loc_1800D34E8
0x1800d3557  xor     eax, eax
0x1800d3559  mov     rbx, [rsp+30h+arg_18]
0x1800d355e  add     rsp, 30h
0x1800d3562  pop     rbp
0x1800d3563  retn
```
