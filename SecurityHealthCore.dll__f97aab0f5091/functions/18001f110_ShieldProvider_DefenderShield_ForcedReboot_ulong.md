# ShieldProvider::DefenderShield::ForcedReboot(ulong)

- ea: `0x18001f110`
- end: `0x18001f3e6`
- name: `?ForcedReboot@DefenderShield@ShieldProvider@@UEAAJK@Z`
- size: `726`
- prototype: `__int64 __fastcall(ShieldProvider::DefenderShield *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000ccd4`
- `0x18000d7fc`
- `0x180011730`
- `0x18001f110`
- `0x180028598`
- `0x1800ceb88`
- `0x1800def88`
- `0x1800df118`
- `0x1800e1690`
- `0x1800e7010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001f27f`
- `KERNEL32!CloseHandle` at `0x18001f29e`
- `KERNEL32!CloseHandle` at `0x18001f27f`
- `KERNEL32!CloseHandle` at `0x18001f29e`
- `KERNEL32!GetCurrentThread` at `0x18001f1b3`
- `KERNEL32!GetCurrentThread` at `0x18001f1b3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001f1c7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001f1c7`

## string_xrefs

- `0x18001f2ad`: `SeShutdownPrivilege`
- `0x18001f2f2`: `SeBackupPrivilege`
- `0x18001f32c`: `SeRestorePrivilege`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DefenderShield::ForcedReboot(ShieldProvider::DefenderShield *this, unsigned int a2)
{
  __int64 v4; // rcx
  int v6; // eax
  unsigned int v7; // edi
  HANDLE CurrentThread; // rax
  void *v9; // r8
  unsigned int v10; // r9d
  int LastFailure; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  const unsigned __int16 *v15; // rdx
  const unsigned __int16 *v16; // rdx
  PVOID *v17; // rcx
  __int64 v18; // rdx
  const unsigned __int16 *v19; // rdx
  int v20; // eax
  unsigned int v21[4]; // [rsp+20h] [rbp-10h] BYREF
  char v22; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF

  if ( !ShieldProvider::IsOSWcosHost(this) )
  {
    *(_QWORD *)v21 = 0;
    v6 = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(v21);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          159,
          WPP_9d32723207713b62a472f0d54196ae73_Traceguids,
          (unsigned int)v6);
LABEL_26:
      CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(v21);
      return v7;
    }
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle)
      || (LastFailure = HrGetLastFailure(), v7 = LastFailure, LastFailure >= 0) )
    {
      v22 = 0;
      LastFailure = CommonUtil::UtilCheckTokenMembershipByRid((CommonUtil *)&v22, (bool *)TokenHandle, v9, v10, v21[0]);
      v7 = LastFailure;
      if ( LastFailure >= 0 )
      {
        if ( v22 )
        {
          if ( TokenHandle )
            CloseHandle(TokenHandle);
          CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(v21);
          v7 = CommonUtil::UtilAcquirePrivilege(L"SeShutdownPrivilege", v15);
          if ( (v7 & 0x80000000) == 0 )
          {
            v7 = CommonUtil::UtilAcquirePrivilege(L"SeBackupPrivilege", v16);
            if ( (v7 & 0x80000000) == 0 )
            {
              v7 = CommonUtil::UtilAcquirePrivilege(L"SeRestorePrivilege", v19);
              if ( (v7 & 0x80000000) == 0 )
              {
                v20 = MpForcedReboot(*(_QWORD *)(*((_QWORD *)this + 6) + 16LL), a2);
                v7 = v20;
                if ( v20 >= 0 )
                  return 0;
                v17 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                  return v7;
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    139,
                    WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
                    (unsigned int)v20);
                  v17 = (PVOID *)WPP_GLOBAL_Control;
                }
                if ( v17 == &WPP_GLOBAL_Control || (*((_BYTE *)v17 + 28) & 1) == 0 )
                  return v7;
                v18 = 166;
              }
              else
              {
                v17 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  return v7;
                v18 = 165;
              }
            }
            else
            {
              v17 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                return v7;
              v18 = 164;
            }
          }
          else
          {
            v17 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              return v7;
            v18 = 163;
          }
          WPP_SF_d(v17[2], v18, WPP_9d32723207713b62a472f0d54196ae73_Traceguids, v7);
          return v7;
        }
        v12 = WPP_GLOBAL_Control;
        v7 = -2147024891;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_24;
        v13 = 162;
        v14 = 2147942405LL;
        goto LABEL_23;
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 161;
        goto LABEL_14;
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 160;
LABEL_14:
        v14 = (unsigned int)LastFailure;
LABEL_23:
        WPP_SF_d(v12[2], v13, WPP_9d32723207713b62a472f0d54196ae73_Traceguids, v14);
      }
    }
LABEL_24:
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    goto LABEL_26;
  }
  v4 = *((_QWORD *)this + 2);
  if ( v4 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 592LL))(v4, a2);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18001f110  mov     [rsp-18h+arg_0], rbx
0x18001f115  push    rbp
0x18001f116  push    rsi
0x18001f117  push    rdi
0x18001f118  mov     rbp, rsp
0x18001f11b  sub     rsp, 30h
0x18001f11f  mov     esi, edx
0x18001f121  mov     rbx, rcx
0x18001f124  call    ?IsOSWcosHost@ShieldProvider@@YA_NXZ; ShieldProvider::IsOSWcosHost(void)
0x18001f129  test    al, al
0x18001f12b  jz      short loc_18001F156
0x18001f12d  mov     rcx, [rbx+10h]
0x18001f131  test    rcx, rcx
0x18001f134  jz      short loc_18001F14C
0x18001f136  mov     rax, [rcx]
0x18001f139  mov     edx, esi
0x18001f13b  mov     rax, [rax+250h]
0x18001f142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f147  jmp     loc_18001F3D9
0x18001f14c  mov     eax, 80004005h
0x18001f151  jmp     loc_18001F3D9
0x18001f156  lea     rcx, [rbp+var_10]
0x18001f15a  mov     qword ptr [rbp+var_10], 0
0x18001f162  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x18001f167  mov     edi, eax
0x18001f169  test    eax, eax
0x18001f16b  jns     short loc_18001F1AB
0x18001f16d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f174  lea     rbx, WPP_GLOBAL_Control
0x18001f17b  cmp     rcx, rbx
0x18001f17e  jz      loc_18001F285
0x18001f184  test    byte ptr [rcx+1Ch], 1
0x18001f188  jz      loc_18001F285
0x18001f18e  mov     rcx, [rcx+10h]
0x18001f192  lea     r8, WPP_9d32723207713b62a472f0d54196ae73_Traceguids
0x18001f199  mov     edx, 9Fh
0x18001f19e  mov     r9d, eax
0x18001f1a1  call    WPP_SF_d
0x18001f1a6  jmp     loc_18001F285
0x18001f1ab  mov     [rbp+TokenHandle], 0
0x18001f1b3  call    cs:__imp_GetCurrentThread
0x18001f1b9  xor     r8d, r8d; OpenAsSelf
0x18001f1bc  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001f1c0  mov     rcx, rax; ThreadHandle
0x18001f1c3  lea     edx, [r8+8]; DesiredAccess
0x18001f1c7  call    cs:__imp_OpenThreadToken
0x18001f1cd  test    eax, eax
0x18001f1cf  jnz     short loc_18001F203
0x18001f1d1  call    HrGetLastFailure
0x18001f1d6  mov     edi, eax
0x18001f1d8  test    eax, eax
0x18001f1da  jns     short loc_18001F203
0x18001f1dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1e3  lea     rbx, WPP_GLOBAL_Control
0x18001f1ea  cmp     rcx, rbx
0x18001f1ed  jz      loc_18001F276
0x18001f1f3  test    byte ptr [rcx+1Ch], 1
0x18001f1f7  jz      short loc_18001F276
0x18001f1f9  mov     edx, 0A0h
0x18001f1fe  mov     r9d, eax
0x18001f201  jmp     short loc_18001F266
0x18001f203  mov     rdx, [rbp+TokenHandle]; bool *
0x18001f207  lea     rcx, [rbp+arg_10]; this
0x18001f20b  mov     [rbp+arg_10], 0
0x18001f20f  call    ?UtilCheckTokenMembershipByRid@CommonUtil@@YAJPEA_NPEAXKK@Z; CommonUtil::UtilCheckTokenMembershipByRid(bool *,void *,ulong,ulong)
0x18001f214  mov     edi, eax
0x18001f216  test    eax, eax
0x18001f218  jns     short loc_18001F23A
0x18001f21a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f221  lea     rbx, WPP_GLOBAL_Control
0x18001f228  cmp     rcx, rbx
0x18001f22b  jz      short loc_18001F276
0x18001f22d  test    byte ptr [rcx+1Ch], 1
0x18001f231  jz      short loc_18001F276
0x18001f233  mov     edx, 0A1h
0x18001f238  jmp     short loc_18001F1FE
0x18001f23a  cmp     [rbp+arg_10], 0
0x18001f23e  jnz     short loc_18001F295
0x18001f240  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f247  lea     rbx, WPP_GLOBAL_Control
0x18001f24e  mov     edi, 80070005h
0x18001f253  cmp     rcx, rbx
0x18001f256  jz      short loc_18001F276
0x18001f258  test    byte ptr [rcx+1Ch], 1
0x18001f25c  jz      short loc_18001F276
0x18001f25e  mov     edx, 0A2h
0x18001f263  mov     r9d, edi
0x18001f266  mov     rcx, [rcx+10h]
0x18001f26a  lea     r8, WPP_9d32723207713b62a472f0d54196ae73_Traceguids
0x18001f271  call    WPP_SF_d
0x18001f276  mov     rcx, [rbp+TokenHandle]; hObject
0x18001f27a  test    rcx, rcx
0x18001f27d  jz      short loc_18001F285
0x18001f27f  call    cs:__imp_CloseHandle
0x18001f285  lea     rcx, [rbp+var_10]
0x18001f289  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x18001f28e  mov     eax, edi
0x18001f290  jmp     loc_18001F3D9
0x18001f295  mov     rcx, [rbp+TokenHandle]; hObject
0x18001f299  test    rcx, rcx
0x18001f29c  jz      short loc_18001F2A4
0x18001f29e  call    cs:__imp_CloseHandle
0x18001f2a4  lea     rcx, [rbp+var_10]
0x18001f2a8  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x18001f2ad  lea     rcx, aSeshutdownpriv; "SeShutdownPrivilege"
0x18001f2b4  call    ?UtilAcquirePrivilege@CommonUtil@@YAJPEBG@Z; CommonUtil::UtilAcquirePrivilege(ushort const *)
0x18001f2b9  mov     edi, eax
0x18001f2bb  test    eax, eax
0x18001f2bd  jns     short loc_18001F2F2
0x18001f2bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f2c6  lea     rbx, WPP_GLOBAL_Control
0x18001f2cd  cmp     rcx, rbx
0x18001f2d0  jz      short loc_18001F28E
0x18001f2d2  test    byte ptr [rcx+1Ch], 1
0x18001f2d6  jz      short loc_18001F28E
0x18001f2d8  mov     edx, 0A3h
0x18001f2dd  mov     rcx, [rcx+10h]
0x18001f2e1  lea     r8, WPP_9d32723207713b62a472f0d54196ae73_Traceguids
0x18001f2e8  mov     r9d, edi
0x18001f2eb  call    WPP_SF_d
0x18001f2f0  jmp     short loc_18001F28E
0x18001f2f2  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x18001f2f9  call    ?UtilAcquirePrivilege@CommonUtil@@YAJPEBG@Z; CommonUtil::UtilAcquirePrivilege(ushort const *)
0x18001f2fe  mov     edi, eax
0x18001f300  test    eax, eax
0x18001f302  jns     short loc_18001F32C
0x18001f304  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f30b  lea     rbx, WPP_GLOBAL_Control
0x18001f312  cmp     rcx, rbx
0x18001f315  jz      loc_18001F28E
0x18001f31b  test    byte ptr [rcx+1Ch], 1
0x18001f31f  jz      loc_18001F28E
0x18001f325  mov     edx, 0A4h
0x18001f32a  jmp     short loc_18001F2DD
0x18001f32c  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x18001f333  call    ?UtilAcquirePrivilege@CommonUtil@@YAJPEBG@Z; CommonUtil::UtilAcquirePrivilege(ushort const *)
0x18001f338  mov     edi, eax
0x18001f33a  test    eax, eax
0x18001f33c  jns     short loc_18001F369
0x18001f33e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f345  lea     rbx, WPP_GLOBAL_Control
0x18001f34c  cmp     rcx, rbx
0x18001f34f  jz      loc_18001F28E
0x18001f355  test    byte ptr [rcx+1Ch], 1
0x18001f359  jz      loc_18001F28E
0x18001f35f  mov     edx, 0A5h
0x18001f364  jmp     loc_18001F2DD
0x18001f369  mov     rcx, [rbx+30h]
0x18001f36d  mov     edx, esi
0x18001f36f  mov     rcx, [rcx+10h]
0x18001f373  call    MpForcedReboot
0x18001f378  mov     edi, eax
0x18001f37a  test    eax, eax
0x18001f37c  jns     short loc_18001F3D7
0x18001f37e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f385  lea     rbx, WPP_GLOBAL_Control
0x18001f38c  cmp     rcx, rbx
0x18001f38f  jz      loc_18001F28E
0x18001f395  test    byte ptr [rcx+1Ch], 1
0x18001f399  jz      short loc_18001F3BA
0x18001f39b  mov     rcx, [rcx+10h]
0x18001f39f  lea     r8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x18001f3a6  mov     edx, 8Bh
0x18001f3ab  mov     r9d, eax
0x18001f3ae  call    WPP_SF_d
0x18001f3b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f3ba  cmp     rcx, rbx
0x18001f3bd  jz      loc_18001F28E
0x18001f3c3  test    byte ptr [rcx+1Ch], 1
0x18001f3c7  jz      loc_18001F28E
0x18001f3cd  mov     edx, 0A6h
0x18001f3d2  jmp     loc_18001F2DD
0x18001f3d7  xor     eax, eax
0x18001f3d9  mov     rbx, [rsp+30h+arg_0]
0x18001f3de  add     rsp, 30h
0x18001f3e2  pop     rdi
0x18001f3e3  pop     rsi
0x18001f3e4  pop     rbp
0x18001f3e5  retn
```
