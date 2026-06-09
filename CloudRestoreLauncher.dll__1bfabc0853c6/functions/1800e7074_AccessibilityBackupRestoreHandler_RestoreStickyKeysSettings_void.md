# AccessibilityBackupRestoreHandler::RestoreStickyKeysSettings(void)

- ea: `0x1800e7074`
- end: `0x1800e7125`
- name: `?RestoreStickyKeysSettings@AccessibilityBackupRestoreHandler@@AEAAXXZ`
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
- `0x1800e7074`
- `0x1800e787c`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x1800e70ca`
- `USER32!SystemParametersInfoW` at `0x1800e70ca`

## string_xrefs

- `0x1800e7113`: `pcshell\shell\cloudrestorelauncher\cloudbackuprestore\accessibilitybackuprestorehandler.cpp`

## pseudocode

```c
void __fastcall AccessibilityBackupRestoreHandler::RestoreStickyKeysSettings(AccessibilityBackupRestoreHandler *this)
{
  const unsigned __int16 *v1; // r8
  const unsigned __int16 *v2; // rdx
  int RegValue; // eax
  const char *v5; // r9
  __int64 v6; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v8; // [rsp+30h] [rbp+8h] BYREF
  __int64 pvParam; // [rsp+38h] [rbp+10h] BYREF

  v1 = (const unsigned __int16 *)*((_QWORD *)this + 55);
  v2 = (const unsigned __int16 *)*((_QWORD *)this + 54);
  pvParam = 8;
  v8 = 0;
  RegValue = AccessibilityBackupRestoreHandler::GetRegValue(this, v2, v1, &v8);
  if ( RegValue < 0 )
  {
    if ( RegValue != -2147024894 )
    {
      v6 = 270;
      goto LABEL_7;
    }
LABEL_5:
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::data(
                            (char *)this + 344,
                            &v8)
             + 275LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>(&v8);
    return;
  }
  HIDWORD(pvParam) = v8;
  if ( SystemParametersInfoW(0x3Bu, 8u, &pvParam, 3u) )
    goto LABEL_5;
  v6 = 260;
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
0x1800e7074  mov     rax, rsp
0x1800e7077  push    rbx
0x1800e7078  sub     rsp, 20h
0x1800e707c  mov     r8, [rcx+1B8h]; unsigned __int16 *
0x1800e7083  lea     r9, [rax+8]; unsigned int *
0x1800e7087  mov     rdx, [rcx+1B0h]; unsigned __int16 *
0x1800e708e  mov     rbx, rcx
0x1800e7091  mov     qword ptr [rax+10h], 0
0x1800e7099  mov     dword ptr [rax+10h], 8
0x1800e70a0  mov     dword ptr [rax+8], 0
0x1800e70a7  call    ?GetRegValue@AccessibilityBackupRestoreHandler@@AEAAJPEBG0PEAK@Z; AccessibilityBackupRestoreHandler::GetRegValue(ushort const *,ushort const *,ulong *)
0x1800e70ac  test    eax, eax
0x1800e70ae  js      short loc_1800E70DB
0x1800e70b0  mov     eax, [rsp+28h+arg_0]
0x1800e70b4  lea     r8, [rsp+28h+pvParam]; pvParam
0x1800e70b9  mov     r9d, 3; fWinIni
0x1800e70bf  mov     [rsp+28h+arg_C], eax
0x1800e70c3  lea     edx, [r9+5]; uiParam
0x1800e70c7  lea     ecx, [rdx+33h]; uiAction
0x1800e70ca  call    cs:__imp_SystemParametersInfoW
0x1800e70d0  test    eax, eax
0x1800e70d2  jnz     short loc_1800E70E2
0x1800e70d4  mov     edx, 104h
0x1800e70d9  jmp     short loc_1800E710E
0x1800e70db  cmp     eax, 80070002h
0x1800e70e0  jnz     short loc_1800E7109
0x1800e70e2  lea     rcx, [rbx+158h]
0x1800e70e9  lea     rdx, [rsp+28h+arg_0]
0x1800e70ee  call    ?data@?$tip_test@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::data(void)
0x1800e70f3  mov     rcx, [rax]
0x1800e70f6  mov     byte ptr [rcx+113h], 1
0x1800e70fd  lea     rcx, [rsp+28h+arg_0]
0x1800e7102  call    ??1?$test_data_control@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>(void)
0x1800e7107  jmp     short loc_1800E711F
0x1800e7109  mov     edx, 10Eh; void *
0x1800e710e  mov     rcx, [rsp+28h]; this
0x1800e7113  lea     r8, aPcshellShellCl_32; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800e711a  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800e711f  add     rsp, 20h
0x1800e7123  pop     rbx
0x1800e7124  retn
```
