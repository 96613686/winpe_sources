# AccessibilityBackupRestoreHandler::RestoreToggleKeysSettings(void)

- ea: `0x1800e712c`
- end: `0x1800e71dd`
- name: `?RestoreToggleKeysSettings@AccessibilityBackupRestoreHandler@@AEAAXXZ`
- size: `177`
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
- `0x1800e712c`
- `0x1800e787c`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x1800e7182`
- `USER32!SystemParametersInfoW` at `0x1800e7182`

## string_xrefs

- `0x1800e71cb`: `pcshell\shell\cloudrestorelauncher\cloudbackuprestore\accessibilitybackuprestorehandler.cpp`

## pseudocode

```c
void __fastcall AccessibilityBackupRestoreHandler::RestoreToggleKeysSettings(AccessibilityBackupRestoreHandler *this)
{
  const unsigned __int16 *v1; // r8
  const unsigned __int16 *v2; // rdx
  int RegValue; // eax
  const char *v5; // r9
  __int64 v6; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v8; // [rsp+30h] [rbp+8h] BYREF
  __int64 pvParam; // [rsp+38h] [rbp+10h] BYREF

  v1 = (const unsigned __int16 *)*((_QWORD *)this + 53);
  v2 = (const unsigned __int16 *)*((_QWORD *)this + 52);
  pvParam = 8;
  v8 = 0;
  RegValue = AccessibilityBackupRestoreHandler::GetRegValue(this, v2, v1, &v8);
  if ( RegValue < 0 )
  {
    if ( RegValue != -2147024894 )
    {
      v6 = 235;
      goto LABEL_7;
    }
LABEL_5:
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::data(
                            (char *)this + 344,
                            &v8)
             + 274LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>(&v8);
    return;
  }
  HIDWORD(pvParam) = v8;
  if ( SystemParametersInfoW(0x35u, 8u, &pvParam, 3u) )
    goto LABEL_5;
  v6 = 225;
LABEL_7:
  wil::details::in1diag3::_Log_GetLastError(
    retaddr,
    (void *)v6,
    (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\accessibilitybackuprestorehandler.cpp",
    v5);
}

```

## disassembly

```asm
0x1800e712c  mov     rax, rsp
0x1800e712f  push    rbx
0x1800e7130  sub     rsp, 20h
0x1800e7134  mov     r8, [rcx+1A8h]; unsigned __int16 *
0x1800e713b  lea     r9, [rax+8]; unsigned int *
0x1800e713f  mov     rdx, [rcx+1A0h]; unsigned __int16 *
0x1800e7146  mov     rbx, rcx
0x1800e7149  mov     qword ptr [rax+10h], 0
0x1800e7151  mov     dword ptr [rax+10h], 8
0x1800e7158  mov     dword ptr [rax+8], 0
0x1800e715f  call    ?GetRegValue@AccessibilityBackupRestoreHandler@@AEAAJPEBG0PEAK@Z; AccessibilityBackupRestoreHandler::GetRegValue(ushort const *,ushort const *,ulong *)
0x1800e7164  test    eax, eax
0x1800e7166  js      short loc_1800E7193
0x1800e7168  mov     eax, [rsp+28h+arg_0]
0x1800e716c  lea     r8, [rsp+28h+pvParam]; pvParam
0x1800e7171  mov     r9d, 3; fWinIni
0x1800e7177  mov     [rsp+28h+arg_C], eax
0x1800e717b  lea     edx, [r9+5]; uiParam
0x1800e717f  lea     ecx, [rdx+2Dh]; uiAction
0x1800e7182  call    cs:__imp_SystemParametersInfoW
0x1800e7188  test    eax, eax
0x1800e718a  jnz     short loc_1800E719A
0x1800e718c  mov     edx, 0E1h
0x1800e7191  jmp     short loc_1800E71C6
0x1800e7193  cmp     eax, 80070002h
0x1800e7198  jnz     short loc_1800E71C1
0x1800e719a  lea     rcx, [rbx+158h]
0x1800e71a1  lea     rdx, [rsp+28h+arg_0]
0x1800e71a6  call    ?data@?$tip_test@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::data(void)
0x1800e71ab  mov     rcx, [rax]
0x1800e71ae  mov     byte ptr [rcx+112h], 1
0x1800e71b5  lea     rcx, [rsp+28h+arg_0]
0x1800e71ba  call    ??1?$test_data_control@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>(void)
0x1800e71bf  jmp     short loc_1800E71D7
0x1800e71c1  mov     edx, 0EBh; void *
0x1800e71c6  mov     rcx, [rsp+28h]; this
0x1800e71cb  lea     r8, aPcshellShellCl_32; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800e71d2  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800e71d7  add     rsp, 20h
0x1800e71db  pop     rbx
0x1800e71dc  retn
```
