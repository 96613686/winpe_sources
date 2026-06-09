# AccessibilityBackupRestoreHandler::RestoreSoundSentrySetting(void)

- ea: `0x1800e6f84`
- end: `0x1800e706e`
- name: `?RestoreSoundSentrySetting@AccessibilityBackupRestoreHandler@@AEAAXXZ`
- size: `234`
- prototype: `void __fastcall(AccessibilityBackupRestoreHandler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800e6490`

## callees

- `0x18008cedc`
- `0x1800e5ce8`
- `0x1800e622c`
- `0x1800e6f84`
- `0x1800e787c`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x1800e700e`
- `USER32!SystemParametersInfoW` at `0x1800e700e`

## string_xrefs

- `0x1800e7054`: `pcshell\shell\cloudrestorelauncher\cloudbackuprestore\accessibilitybackuprestorehandler.cpp`

## pseudocode

```c
void __fastcall AccessibilityBackupRestoreHandler::RestoreSoundSentrySetting(AccessibilityBackupRestoreHandler *this)
{
  const unsigned __int16 *v1; // r8
  const unsigned __int16 *v2; // rdx
  int RegValue; // eax
  AccessibilityBackupRestoreHandler *v5; // rcx
  const unsigned __int16 *v6; // r8
  const unsigned __int16 *v7; // rdx
  int v8; // eax
  const char *v9; // r9
  __int64 v10; // rdx
  _OWORD pvParam[2]; // [rsp+20h] [rbp-40h] BYREF
  __int128 v12; // [rsp+40h] [rbp-20h]
  __int64 v13; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  AccessibilityBackupRestoreHandler *v15; // [rsp+70h] [rbp+10h] BYREF
  unsigned int v16; // [rsp+78h] [rbp+18h] BYREF

  v1 = (const unsigned __int16 *)*((_QWORD *)this + 68);
  v2 = (const unsigned __int16 *)*((_QWORD *)this + 67);
  v13 = 0;
  memset(pvParam, 0, sizeof(pvParam));
  LODWORD(pvParam[0]) = 56;
  v12 = 0;
  LODWORD(v12) = 0;
  v16 = 0;
  LODWORD(v15) = 0;
  RegValue = AccessibilityBackupRestoreHandler::GetRegValue(this, v2, v1, (unsigned int *)&v15);
  v5 = 0;
  v6 = (const unsigned __int16 *)*((_QWORD *)this + 69);
  v7 = (const unsigned __int16 *)*((_QWORD *)this + 67);
  if ( RegValue >= 0 )
    v5 = (AccessibilityBackupRestoreHandler *)(unsigned int)v15;
  LODWORD(v12) = (_DWORD)v5;
  v8 = AccessibilityBackupRestoreHandler::GetRegValue(v5, v7, v6, &v16);
  if ( v8 < 0 )
  {
    if ( v8 != -2147024894 )
    {
      v10 = 421;
      goto LABEL_9;
    }
LABEL_7:
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::data(
                            (char *)this + 344,
                            &v15)
             + 279LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>(&v15);
    return;
  }
  DWORD1(pvParam[0]) = v16;
  if ( SystemParametersInfoW(0x41u, 0x38u, pvParam, 3u) )
    goto LABEL_7;
  v10 = 411;
LABEL_9:
  wil::details::in1diag3::_Log_GetLastError(
    retaddr,
    (void *)v10,
    (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\accessibilitybackuprestorehandler.cpp",
    v9);
}

```

## disassembly

```asm
0x1800e6f84  mov     [rsp-8+arg_10], rbx
0x1800e6f89  push    rbp
0x1800e6f8a  mov     rbp, rsp
0x1800e6f8d  sub     rsp, 60h
0x1800e6f91  mov     r8, [rcx+220h]; unsigned __int16 *
0x1800e6f98  lea     r9, [rbp+arg_0]; unsigned int *
0x1800e6f9c  mov     rdx, [rcx+218h]; unsigned __int16 *
0x1800e6fa3  xor     eax, eax
0x1800e6fa5  xorps   xmm0, xmm0
0x1800e6fa8  mov     [rbp+var_10], rax
0x1800e6fac  movups  [rbp+pvParam], xmm0
0x1800e6fb0  mov     dword ptr [rbp+pvParam], 38h ; '8'
0x1800e6fb7  mov     rbx, rcx
0x1800e6fba  movups  [rbp+var_20], xmm0
0x1800e6fbe  mov     dword ptr [rbp+var_20], eax
0x1800e6fc1  movups  [rbp+var_30], xmm0
0x1800e6fc5  mov     [rbp+arg_8], eax
0x1800e6fc8  mov     dword ptr [rbp+arg_0], eax
0x1800e6fcb  call    ?GetRegValue@AccessibilityBackupRestoreHandler@@AEAAJPEBG0PEAK@Z; AccessibilityBackupRestoreHandler::GetRegValue(ushort const *,ushort const *,ulong *)
0x1800e6fd0  mov     ecx, dword ptr [rbp+var_20]
0x1800e6fd3  lea     r9, [rbp+arg_8]; unsigned int *
0x1800e6fd7  mov     r8, [rbx+228h]; unsigned __int16 *
0x1800e6fde  test    eax, eax
0x1800e6fe0  mov     rdx, [rbx+218h]; unsigned __int16 *
0x1800e6fe7  cmovns  ecx, dword ptr [rbp+arg_0]; this
0x1800e6feb  mov     dword ptr [rbp+var_20], ecx
0x1800e6fee  call    ?GetRegValue@AccessibilityBackupRestoreHandler@@AEAAJPEBG0PEAK@Z; AccessibilityBackupRestoreHandler::GetRegValue(ushort const *,ushort const *,ulong *)
0x1800e6ff3  test    eax, eax
0x1800e6ff5  js      short loc_1800E701F
0x1800e6ff7  mov     eax, [rbp+arg_8]
0x1800e6ffa  lea     r8, [rbp+pvParam]; pvParam
0x1800e6ffe  mov     r9d, 3; fWinIni
0x1800e7004  mov     dword ptr [rbp+pvParam+4], eax
0x1800e7007  lea     edx, [r9+35h]; uiParam
0x1800e700b  lea     ecx, [rdx+9]; uiAction
0x1800e700e  call    cs:__imp_SystemParametersInfoW
0x1800e7014  test    eax, eax
0x1800e7016  jnz     short loc_1800E7026
0x1800e7018  mov     edx, 19Bh
0x1800e701d  jmp     short loc_1800E7050
0x1800e701f  cmp     eax, 80070002h
0x1800e7024  jnz     short loc_1800E704B
0x1800e7026  lea     rcx, [rbx+158h]
0x1800e702d  lea     rdx, [rbp+arg_0]
0x1800e7031  call    ?data@?$tip_test@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::data(void)
0x1800e7036  mov     rcx, [rax]
0x1800e7039  mov     byte ptr [rcx+117h], 1
0x1800e7040  lea     rcx, [rbp+arg_0]
0x1800e7044  call    ??1?$test_data_control@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>(void)
0x1800e7049  jmp     short loc_1800E7060
0x1800e704b  mov     edx, 1A5h; void *
0x1800e7050  mov     rcx, [rbp+8]; this
0x1800e7054  lea     r8, aPcshellShellCl_32; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800e705b  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800e7060  mov     rbx, [rsp+60h+arg_10]
0x1800e7068  add     rsp, 60h
0x1800e706c  pop     rbp
0x1800e706d  retn
```
