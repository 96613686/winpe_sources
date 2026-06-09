# AccessibilityBackupRestoreHandler::RestoreKeyboardPreferenceSettings(void)

- ea: `0x1800e6b70`
- end: `0x1800e6c26`
- name: `?RestoreKeyboardPreferenceSettings@AccessibilityBackupRestoreHandler@@AEAAXXZ`
- size: `182`
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
- `0x1800e6b70`
- `0x1800e787c`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x1800e6bae`
- `USER32!SystemParametersInfoW` at `0x1800e6bc8`
- `USER32!SystemParametersInfoW` at `0x1800e6bae`
- `USER32!SystemParametersInfoW` at `0x1800e6bc8`

## string_xrefs

- `0x1800e6c15`: `pcshell\shell\cloudrestorelauncher\cloudbackuprestore\accessibilitybackuprestorehandler.cpp`

## pseudocode

```c
void __fastcall AccessibilityBackupRestoreHandler::RestoreKeyboardPreferenceSettings(
        AccessibilityBackupRestoreHandler *this)
{
  const unsigned __int16 *v1; // r8
  const unsigned __int16 *v2; // rdx
  int RegValue; // eax
  const char *v5; // r9
  __int64 v6; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  UINT uiParam; // [rsp+30h] [rbp+8h] BYREF

  v1 = (const unsigned __int16 *)*((_QWORD *)this + 71);
  v2 = (const unsigned __int16 *)*((_QWORD *)this + 70);
  uiParam = 0;
  RegValue = AccessibilityBackupRestoreHandler::GetRegValue(this, v2, v1, &uiParam);
  if ( RegValue < 0 )
  {
    if ( RegValue != -2147024894 )
    {
      v6 = 200;
      goto LABEL_8;
    }
LABEL_6:
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::data(
                            (char *)this + 344,
                            &uiParam)
             + 277LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>(&uiParam);
    return;
  }
  if ( SystemParametersInfoW(0x45u, uiParam, 0, 3u) && SystemParametersInfoW(0x100Bu, 0, (PVOID)uiParam, 3u) )
    goto LABEL_6;
  v6 = 190;
LABEL_8:
  wil::details::in1diag3::_Log_GetLastError(
    retaddr,
    (void *)v6,
    (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\accessibilitybackuprestorehandler.cpp",
    v5);
}

```

## disassembly

```asm
0x1800e6b70  push    rbx
0x1800e6b72  sub     rsp, 20h
0x1800e6b76  mov     r8, [rcx+238h]; unsigned __int16 *
0x1800e6b7d  lea     r9, [rsp+28h+uiParam]; unsigned int *
0x1800e6b82  mov     rdx, [rcx+230h]; unsigned __int16 *
0x1800e6b89  mov     rbx, rcx
0x1800e6b8c  mov     [rsp+28h+uiParam], 0
0x1800e6b94  call    ?GetRegValue@AccessibilityBackupRestoreHandler@@AEAAJPEBG0PEAK@Z; AccessibilityBackupRestoreHandler::GetRegValue(ushort const *,ushort const *,ulong *)
0x1800e6b99  test    eax, eax
0x1800e6b9b  js      short loc_1800E6BD9
0x1800e6b9d  mov     edx, [rsp+28h+uiParam]; uiParam
0x1800e6ba1  mov     r9d, 3; fWinIni
0x1800e6ba7  xor     r8d, r8d; pvParam
0x1800e6baa  lea     ecx, [r9+42h]; uiAction
0x1800e6bae  call    cs:__imp_SystemParametersInfoW
0x1800e6bb4  test    eax, eax
0x1800e6bb6  jz      short loc_1800E6BD2
0x1800e6bb8  mov     r8d, [rsp+28h+uiParam]; pvParam
0x1800e6bbd  xor     edx, edx; uiParam
0x1800e6bbf  mov     ecx, 100Bh; uiAction
0x1800e6bc4  lea     r9d, [rdx+3]; fWinIni
0x1800e6bc8  call    cs:__imp_SystemParametersInfoW
0x1800e6bce  test    eax, eax
0x1800e6bd0  jnz     short loc_1800E6BE0
0x1800e6bd2  mov     edx, 0BEh
0x1800e6bd7  jmp     short loc_1800E6C10
0x1800e6bd9  cmp     eax, 80070002h
0x1800e6bde  jnz     short loc_1800E6C0B
0x1800e6be0  lea     rcx, [rbx+158h]
0x1800e6be7  lea     rdx, [rsp+28h+uiParam]
0x1800e6bec  call    ?data@?$tip_test@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::data(void)
0x1800e6bf1  mov     rcx, [rax]
0x1800e6bf4  mov     byte ptr [rcx+115h], 1
0x1800e6bfb  lea     rcx, [rsp+28h+uiParam]
0x1800e6c00  call    ??1?$test_data_control@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>(void)
0x1800e6c05  add     rsp, 20h
0x1800e6c09  pop     rbx
0x1800e6c0a  retn
0x1800e6c0b  mov     edx, 0C8h; void *
0x1800e6c10  mov     rcx, [rsp+28h]; this
0x1800e6c15  lea     r8, aPcshellShellCl_32; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800e6c1c  add     rsp, 20h
0x1800e6c20  pop     rbx
0x1800e6c21  jmp     ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
```
