# AccessibilityBackupRestoreHandler::RestoreFilterKeysSettings(void)

- ea: `0x1800e69e0`
- end: `0x1800e6b69`
- name: `?RestoreFilterKeysSettings@AccessibilityBackupRestoreHandler@@AEAAXXZ`
- size: `393`
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
- `0x1800e69e0`
- `0x1800e787c`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x1800e6a2e`
- `USER32!SystemParametersInfoW` at `0x1800e6b00`
- `USER32!SystemParametersInfoW` at `0x1800e6a2e`
- `USER32!SystemParametersInfoW` at `0x1800e6b00`

## string_xrefs

- `0x1800e6b46`: `pcshell\shell\cloudrestorelauncher\cloudbackuprestore\accessibilitybackuprestorehandler.cpp`

## pseudocode

```c
void __fastcall AccessibilityBackupRestoreHandler::RestoreFilterKeysSettings(const unsigned __int16 **this)
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
  unsigned __int64 v14; // rcx
  const unsigned __int16 *v15; // r8
  const unsigned __int16 *v16; // rdx
  int v17; // eax
  AccessibilityBackupRestoreHandler *v18; // rcx
  const unsigned __int16 *v19; // r8
  const unsigned __int16 *v20; // rdx
  int v21; // eax
  unsigned int v22; // [rsp+20h] [rbp-40h] BYREF
  AccessibilityBackupRestoreHandler *v23; // [rsp+28h] [rbp-38h] BYREF
  AccessibilityBackupRestoreHandler *v24; // [rsp+30h] [rbp-30h] BYREF
  __int128 pvParam; // [rsp+38h] [rbp-28h] BYREF
  __int64 v26; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v26 = 0;
  v22 = 0;
  pvParam = 0;
  v23 = 0;
  v24 = 0;
  LODWORD(pvParam) = 24;
  if ( SystemParametersInfoW(0x32u, 0x18u, &pvParam, 0) )
  {
    RegValue = AccessibilityBackupRestoreHandler::GetRegValue(v2, this[58], this[59], (unsigned int *)&v23);
    v6 = DWORD2(pvParam);
    v7 = this[60];
    v8 = this[58];
    if ( RegValue >= 0 )
      v6 = (unsigned int)v23;
    DWORD2(pvParam) = v6;
    v9 = AccessibilityBackupRestoreHandler::GetRegValue(
           (AccessibilityBackupRestoreHandler *)v6,
           v8,
           v7,
           (unsigned int *)&v23 + 1);
    v10 = (AccessibilityBackupRestoreHandler *)HIDWORD(pvParam);
    v11 = this[61];
    v12 = this[58];
    if ( v9 >= 0 )
      v10 = (AccessibilityBackupRestoreHandler *)HIDWORD(v23);
    HIDWORD(pvParam) = (_DWORD)v10;
    v13 = AccessibilityBackupRestoreHandler::GetRegValue(v10, v12, v11, (unsigned int *)&v24);
    v14 = (unsigned int)v26;
    v15 = this[62];
    v16 = this[58];
    if ( v13 >= 0 )
      v14 = (unsigned int)v24;
    LODWORD(v26) = v14;
    v17 = AccessibilityBackupRestoreHandler::GetRegValue(
            (AccessibilityBackupRestoreHandler *)v14,
            v16,
            v15,
            (unsigned int *)&v24 + 1);
    v18 = (AccessibilityBackupRestoreHandler *)HIDWORD(v26);
    v19 = this[57];
    v20 = this[56];
    if ( v17 >= 0 )
      v18 = (AccessibilityBackupRestoreHandler *)HIDWORD(v24);
    HIDWORD(v26) = (_DWORD)v18;
    v21 = AccessibilityBackupRestoreHandler::GetRegValue(v18, v20, v19, &v22);
    if ( v21 < 0 )
    {
      if ( v21 != -2147024894 )
      {
        v4 = 329;
        goto LABEL_17;
      }
    }
    else
    {
      DWORD1(pvParam) = v22;
      if ( !SystemParametersInfoW(0x33u, 0x18u, &pvParam, 3u) )
      {
        v4 = 319;
        goto LABEL_17;
      }
    }
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::data(
                            this + 43,
                            &v22)
             + 276LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>(&v22);
    return;
  }
  v4 = 285;
LABEL_17:
  wil::details::in1diag3::_Log_GetLastError(
    retaddr,
    (void *)v4,
    (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\accessibilitybackuprestorehandler.cpp",
    v3);
}

```

## disassembly

```asm
0x1800e69e0  mov     [rsp-8+arg_8], rbx
0x1800e69e5  push    rbp
0x1800e69e6  mov     rbp, rsp
0x1800e69e9  sub     rsp, 60h
0x1800e69ed  mov     rax, cs:__security_cookie
0x1800e69f4  xor     rax, rsp
0x1800e69f7  mov     [rbp+var_10], rax
0x1800e69fb  xor     eax, eax
0x1800e69fd  lea     r8, [rbp+pvParam]; pvParam
0x1800e6a01  xorps   xmm0, xmm0
0x1800e6a04  mov     [rbp+var_18], rax
0x1800e6a08  mov     rbx, rcx
0x1800e6a0b  mov     [rbp+var_40], eax
0x1800e6a0e  movups  [rbp+pvParam], xmm0
0x1800e6a12  lea     edx, [rax+18h]; uiParam
0x1800e6a15  mov     dword ptr [rbp+var_38], eax
0x1800e6a18  lea     ecx, [rax+32h]; uiAction
0x1800e6a1b  mov     dword ptr [rbp+var_38+4], eax
0x1800e6a1e  xor     r9d, r9d; fWinIni
0x1800e6a21  mov     dword ptr [rbp+var_30], eax
0x1800e6a24  mov     dword ptr [rbp+var_30+4], eax
0x1800e6a27  mov     dword ptr [rbp+pvParam], 18h
0x1800e6a2e  call    cs:__imp_SystemParametersInfoW
0x1800e6a34  test    eax, eax
0x1800e6a36  jnz     short loc_1800E6A42
0x1800e6a38  mov     edx, 11Dh
0x1800e6a3d  jmp     loc_1800E6B42
0x1800e6a42  mov     r8, [rbx+1D8h]; unsigned __int16 *
0x1800e6a49  lea     r9, [rbp+var_38]; unsigned int *
0x1800e6a4d  mov     rdx, [rbx+1D0h]; unsigned __int16 *
0x1800e6a54  call    ?GetRegValue@AccessibilityBackupRestoreHandler@@AEAAJPEBG0PEAK@Z; AccessibilityBackupRestoreHandler::GetRegValue(ushort const *,ushort const *,ulong *)
0x1800e6a59  mov     ecx, dword ptr [rbp+pvParam+8]
0x1800e6a5c  lea     r9, [rbp+var_38+4]; unsigned int *
0x1800e6a60  mov     r8, [rbx+1E0h]; unsigned __int16 *
0x1800e6a67  test    eax, eax
0x1800e6a69  mov     rdx, [rbx+1D0h]; unsigned __int16 *
0x1800e6a70  cmovns  ecx, dword ptr [rbp+var_38]; this
0x1800e6a74  mov     dword ptr [rbp+pvParam+8], ecx
0x1800e6a77  call    ?GetRegValue@AccessibilityBackupRestoreHandler@@AEAAJPEBG0PEAK@Z; AccessibilityBackupRestoreHandler::GetRegValue(ushort const *,ushort const *,ulong *)
0x1800e6a7c  mov     ecx, dword ptr [rbp+pvParam+0Ch]
0x1800e6a7f  lea     r9, [rbp+var_30]; unsigned int *
0x1800e6a83  mov     r8, [rbx+1E8h]; unsigned __int16 *
0x1800e6a8a  test    eax, eax
0x1800e6a8c  mov     rdx, [rbx+1D0h]; unsigned __int16 *
0x1800e6a93  cmovns  ecx, dword ptr [rbp+var_38+4]; this
0x1800e6a97  mov     dword ptr [rbp+pvParam+0Ch], ecx
0x1800e6a9a  call    ?GetRegValue@AccessibilityBackupRestoreHandler@@AEAAJPEBG0PEAK@Z; AccessibilityBackupRestoreHandler::GetRegValue(ushort const *,ushort const *,ulong *)
0x1800e6a9f  mov     ecx, dword ptr [rbp+var_18]
0x1800e6aa2  lea     r9, [rbp+var_30+4]; unsigned int *
0x1800e6aa6  mov     r8, [rbx+1F0h]; unsigned __int16 *
0x1800e6aad  test    eax, eax
0x1800e6aaf  mov     rdx, [rbx+1D0h]; unsigned __int16 *
0x1800e6ab6  cmovns  ecx, dword ptr [rbp+var_30]; this
0x1800e6aba  mov     dword ptr [rbp+var_18], ecx
0x1800e6abd  call    ?GetRegValue@AccessibilityBackupRestoreHandler@@AEAAJPEBG0PEAK@Z; AccessibilityBackupRestoreHandler::GetRegValue(ushort const *,ushort const *,ulong *)
0x1800e6ac2  mov     ecx, dword ptr [rbp+var_18+4]
0x1800e6ac5  lea     r9, [rbp+var_40]; unsigned int *
0x1800e6ac9  mov     r8, [rbx+1C8h]; unsigned __int16 *
0x1800e6ad0  test    eax, eax
0x1800e6ad2  mov     rdx, [rbx+1C0h]; unsigned __int16 *
0x1800e6ad9  cmovns  ecx, dword ptr [rbp+var_30+4]; this
0x1800e6add  mov     dword ptr [rbp+var_18+4], ecx
0x1800e6ae0  call    ?GetRegValue@AccessibilityBackupRestoreHandler@@AEAAJPEBG0PEAK@Z; AccessibilityBackupRestoreHandler::GetRegValue(ushort const *,ushort const *,ulong *)
0x1800e6ae5  test    eax, eax
0x1800e6ae7  js      short loc_1800E6B11
0x1800e6ae9  mov     eax, [rbp+var_40]
0x1800e6aec  lea     r8, [rbp+pvParam]; pvParam
0x1800e6af0  mov     r9d, 3; fWinIni
0x1800e6af6  mov     dword ptr [rbp+pvParam+4], eax
0x1800e6af9  lea     edx, [r9+15h]; uiParam
0x1800e6afd  lea     ecx, [rdx+1Bh]; uiAction
0x1800e6b00  call    cs:__imp_SystemParametersInfoW
0x1800e6b06  test    eax, eax
0x1800e6b08  jnz     short loc_1800E6B18
0x1800e6b0a  mov     edx, 13Fh
0x1800e6b0f  jmp     short loc_1800E6B42
0x1800e6b11  cmp     eax, 80070002h
0x1800e6b16  jnz     short loc_1800E6B3D
0x1800e6b18  lea     rcx, [rbx+158h]
0x1800e6b1f  lea     rdx, [rbp+var_40]
0x1800e6b23  call    ?data@?$tip_test@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::data(void)
0x1800e6b28  mov     rcx, [rax]
0x1800e6b2b  mov     byte ptr [rcx+114h], 1
0x1800e6b32  lea     rcx, [rbp+var_40]
0x1800e6b36  call    ??1?$test_data_control@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>(void)
0x1800e6b3b  jmp     short loc_1800E6B52
0x1800e6b3d  mov     edx, 149h; void *
0x1800e6b42  mov     rcx, [rbp+8]; this
0x1800e6b46  lea     r8, aPcshellShellCl_32; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800e6b4d  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800e6b52  mov     rcx, [rbp+var_10]
0x1800e6b56  xor     rcx, rsp; StackCookie
0x1800e6b59  call    __security_check_cookie
0x1800e6b5e  mov     rbx, [rsp+60h+arg_8]
0x1800e6b63  add     rsp, 60h
0x1800e6b67  pop     rbp
0x1800e6b68  retn
```
