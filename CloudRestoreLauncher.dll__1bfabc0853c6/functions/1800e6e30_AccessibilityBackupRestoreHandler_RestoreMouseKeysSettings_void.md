# AccessibilityBackupRestoreHandler::RestoreMouseKeysSettings(void)

- ea: `0x1800e6e30`
- end: `0x1800e6f7d`
- name: `?RestoreMouseKeysSettings@AccessibilityBackupRestoreHandler@@AEAAXXZ`
- size: `333`
- prototype: `void __fastcall(AccessibilityBackupRestoreHandler *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800e6490`

## callees

- `0x18000c6e0`
- `0x18008cedc`
- `0x1800e5ce8`
- `0x1800e622c`
- `0x1800e6e30`
- `0x1800e787c`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x1800e6e88`
- `USER32!SystemParametersInfoW` at `0x1800e6f14`
- `USER32!SystemParametersInfoW` at `0x1800e6e88`
- `USER32!SystemParametersInfoW` at `0x1800e6f14`

## string_xrefs

- `0x1800e6f5a`: `pcshell\shell\cloudrestorelauncher\cloudbackuprestore\accessibilitybackuprestorehandler.cpp`

## pseudocode

```c
void __fastcall AccessibilityBackupRestoreHandler::RestoreMouseKeysSettings(const unsigned __int16 **this)
{
  AccessibilityBackupRestoreHandler *v2; // rcx
  const char *v3; // r9
  __int64 v4; // rdx
  int RegValue; // eax
  unsigned __int64 v6; // rcx
  const unsigned __int16 *v7; // r8
  const unsigned __int16 *v8; // rdx
  int v9; // eax
  AccessibilityBackupRestoreHandler *v10; // rcx
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // rdx
  int v13; // eax
  unsigned int v14; // [rsp+20h] [rbp-40h] BYREF
  AccessibilityBackupRestoreHandler *v15; // [rsp+28h] [rbp-38h] BYREF
  int pvParam; // [rsp+30h] [rbp-30h] BYREF
  __int128 v17; // [rsp+34h] [rbp-2Ch]
  __int64 v18; // [rsp+44h] [rbp-1Ch]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v18 = 0;
  v14 = 0;
  v15 = 0;
  pvParam = 28;
  v17 = 0;
  if ( SystemParametersInfoW(0x36u, 0x1Cu, &pvParam, 0) )
  {
    RegValue = AccessibilityBackupRestoreHandler::GetRegValue(v2, this[63], this[65], (unsigned int *)&v15);
    v6 = DWORD1(v17);
    v7 = this[66];
    v8 = this[63];
    if ( RegValue >= 0 )
      v6 = (unsigned int)v15;
    DWORD1(v17) = v6;
    v9 = AccessibilityBackupRestoreHandler::GetRegValue(
           (AccessibilityBackupRestoreHandler *)v6,
           v8,
           v7,
           (unsigned int *)&v15 + 1);
    v10 = (AccessibilityBackupRestoreHandler *)DWORD2(v17);
    v11 = this[64];
    v12 = this[63];
    if ( v9 >= 0 )
      v10 = (AccessibilityBackupRestoreHandler *)HIDWORD(v15);
    DWORD2(v17) = (_DWORD)v10;
    v13 = AccessibilityBackupRestoreHandler::GetRegValue(v10, v12, v11, &v14);
    if ( v13 < 0 )
    {
      if ( v13 != -2147024894 )
      {
        v4 = 379;
        goto LABEL_13;
      }
    }
    else
    {
      LODWORD(v17) = v14;
      if ( !SystemParametersInfoW(0x37u, 0x1Cu, &pvParam, 3u) )
      {
        v4 = 369;
        goto LABEL_13;
      }
    }
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::data(
                            this + 43,
                            &v14)
             + 278LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>(&v14);
    return;
  }
  v4 = 344;
LABEL_13:
  wil::details::in1diag3::_Log_GetLastError(
    retaddr,
    (void *)v4,
    (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\accessibilitybackuprestorehandler.cpp",
    v3);
}

```

## disassembly

```asm
0x1800e6e30  mov     [rsp-8+arg_8], rbx
0x1800e6e35  push    rbp
0x1800e6e36  mov     rbp, rsp
0x1800e6e39  sub     rsp, 60h
0x1800e6e3d  mov     rax, cs:__security_cookie
0x1800e6e44  xor     rax, rsp
0x1800e6e47  mov     [rbp+var_10], rax
0x1800e6e4b  xor     r9d, r9d; fWinIni
0x1800e6e4e  mov     [rbp+var_1C], 0
0x1800e6e56  mov     rbx, rcx
0x1800e6e59  mov     [rbp+var_40], 0
0x1800e6e60  xorps   xmm0, xmm0
0x1800e6e63  mov     dword ptr [rbp+var_38], 0
0x1800e6e6a  lea     r8, [rbp+pvParam]; pvParam
0x1800e6e6e  mov     dword ptr [rbp+var_38+4], 0
0x1800e6e75  lea     edx, [r9+1Ch]; uiParam
0x1800e6e79  mov     [rbp+pvParam], 1Ch
0x1800e6e80  lea     ecx, [rdx+1Ah]; uiAction
0x1800e6e83  movdqu  [rbp+var_2C], xmm0
0x1800e6e88  call    cs:__imp_SystemParametersInfoW
0x1800e6e8e  test    eax, eax
0x1800e6e90  jnz     short loc_1800E6E9C
0x1800e6e92  mov     edx, 158h
0x1800e6e97  jmp     loc_1800E6F56
0x1800e6e9c  mov     r8, [rbx+208h]; unsigned __int16 *
0x1800e6ea3  lea     r9, [rbp+var_38]; unsigned int *
0x1800e6ea7  mov     rdx, [rbx+1F8h]; unsigned __int16 *
0x1800e6eae  call    ?GetRegValue@AccessibilityBackupRestoreHandler@@AEAAJPEBG0PEAK@Z; AccessibilityBackupRestoreHandler::GetRegValue(ushort const *,ushort const *,ulong *)
0x1800e6eb3  mov     ecx, dword ptr [rbp+var_2C+4]
0x1800e6eb6  lea     r9, [rbp+var_38+4]; unsigned int *
0x1800e6eba  mov     r8, [rbx+210h]; unsigned __int16 *
0x1800e6ec1  test    eax, eax
0x1800e6ec3  mov     rdx, [rbx+1F8h]; unsigned __int16 *
0x1800e6eca  cmovns  ecx, dword ptr [rbp+var_38]; this
0x1800e6ece  mov     dword ptr [rbp+var_2C+4], ecx
0x1800e6ed1  call    ?GetRegValue@AccessibilityBackupRestoreHandler@@AEAAJPEBG0PEAK@Z; AccessibilityBackupRestoreHandler::GetRegValue(ushort const *,ushort const *,ulong *)
0x1800e6ed6  mov     ecx, dword ptr [rbp+var_2C+8]
0x1800e6ed9  lea     r9, [rbp+var_40]; unsigned int *
0x1800e6edd  mov     r8, [rbx+200h]; unsigned __int16 *
0x1800e6ee4  test    eax, eax
0x1800e6ee6  mov     rdx, [rbx+1F8h]; unsigned __int16 *
0x1800e6eed  cmovns  ecx, dword ptr [rbp+var_38+4]; this
0x1800e6ef1  mov     dword ptr [rbp+var_2C+8], ecx
0x1800e6ef4  call    ?GetRegValue@AccessibilityBackupRestoreHandler@@AEAAJPEBG0PEAK@Z; AccessibilityBackupRestoreHandler::GetRegValue(ushort const *,ushort const *,ulong *)
0x1800e6ef9  test    eax, eax
0x1800e6efb  js      short loc_1800E6F25
0x1800e6efd  mov     eax, [rbp+var_40]
0x1800e6f00  lea     r8, [rbp+pvParam]; pvParam
0x1800e6f04  mov     r9d, 3; fWinIni
0x1800e6f0a  mov     dword ptr [rbp+var_2C], eax
0x1800e6f0d  lea     edx, [r9+19h]; uiParam
0x1800e6f11  lea     ecx, [rdx+1Bh]; uiAction
0x1800e6f14  call    cs:__imp_SystemParametersInfoW
0x1800e6f1a  test    eax, eax
0x1800e6f1c  jnz     short loc_1800E6F2C
0x1800e6f1e  mov     edx, 171h
0x1800e6f23  jmp     short loc_1800E6F56
0x1800e6f25  cmp     eax, 80070002h
0x1800e6f2a  jnz     short loc_1800E6F51
0x1800e6f2c  lea     rcx, [rbx+158h]
0x1800e6f33  lea     rdx, [rbp+var_40]
0x1800e6f37  call    ?data@?$tip_test@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::data(void)
0x1800e6f3c  mov     rcx, [rax]
0x1800e6f3f  mov     byte ptr [rcx+116h], 1
0x1800e6f46  lea     rcx, [rbp+var_40]
0x1800e6f4a  call    ??1?$test_data_control@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>(void)
0x1800e6f4f  jmp     short loc_1800E6F66
0x1800e6f51  mov     edx, 17Bh; void *
0x1800e6f56  mov     rcx, [rbp+8]; this
0x1800e6f5a  lea     r8, aPcshellShellCl_32; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800e6f61  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800e6f66  mov     rcx, [rbp+var_10]
0x1800e6f6a  xor     rcx, rsp; StackCookie
0x1800e6f6d  call    __security_check_cookie
0x1800e6f72  mov     rbx, [rsp+60h+arg_8]
0x1800e6f77  add     rsp, 60h
0x1800e6f7b  pop     rbp
0x1800e6f7c  retn
```
