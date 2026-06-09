# AccessibilityBackupRestoreHandler::RestoreDismissNotificationDurationSetting(void)

- ea: `0x1800e6934`
- end: `0x1800e69d7`
- name: `?RestoreDismissNotificationDurationSetting@AccessibilityBackupRestoreHandler@@AEAAXXZ`
- size: `163`
- prototype: `void __fastcall(AccessibilityBackupRestoreHandler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800e6490`

## callees

- `0x18001ac54`
- `0x18008cedc`
- `0x1800e5ce8`
- `0x1800e6934`
- `0x1800e787c`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x1800e6985`
- `USER32!SystemParametersInfoW` at `0x1800e6985`

## string_xrefs

- `0x1800e69bb`: `pcshell\shell\cloudrestorelauncher\cloudbackuprestore\accessibilitybackuprestorehandler.cpp`

## pseudocode

```c
void __fastcall AccessibilityBackupRestoreHandler::RestoreDismissNotificationDurationSetting(
        AccessibilityBackupRestoreHandler *this)
{
  const unsigned __int16 *v1; // r8
  const unsigned __int16 *v2; // rdx
  unsigned int v4; // ebx
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v7; // [rsp+30h] [rbp+8h] BYREF
  char v8; // [rsp+38h] [rbp+10h] BYREF

  v1 = (const unsigned __int16 *)*((_QWORD *)this + 76);
  v2 = (const unsigned __int16 *)*((_QWORD *)this + 75);
  v4 = 5;
  v7 = 5;
  if ( (unsigned int)SHRegGetDWORD(HKEY_CURRENT_USER, v2, v1, &v7) )
    v7 = 5;
  else
    v4 = v7;
  if ( SystemParametersInfoW(0x2017u, 0, (PVOID)v4, 3u) )
  {
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::data(
                            (char *)this + 344,
                            &v8)
             + 282LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>(&v8);
  }
  else
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x1D8,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\accessibilitybackuprestorehandler.cpp",
      v5);
  }
}

```

## disassembly

```asm
0x1800e6934  mov     [rsp+arg_10], rbx
0x1800e6939  push    rdi
0x1800e693a  sub     rsp, 20h
0x1800e693e  mov     r8, [rcx+260h]; unsigned __int16 *
0x1800e6945  lea     r9, [rsp+28h+arg_0]; unsigned int *
0x1800e694a  mov     rdx, [rcx+258h]; unsigned __int16 *
0x1800e6951  mov     rdi, rcx
0x1800e6954  mov     ebx, 5
0x1800e6959  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800e6960  mov     [rsp+28h+arg_0], ebx
0x1800e6964  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800e6969  test    eax, eax
0x1800e696b  jz      short loc_1800E6973
0x1800e696d  mov     [rsp+28h+arg_0], ebx
0x1800e6971  jmp     short loc_1800E6977
0x1800e6973  mov     ebx, [rsp+28h+arg_0]
0x1800e6977  xor     edx, edx; uiParam
0x1800e6979  mov     r8d, ebx; pvParam
0x1800e697c  mov     ecx, 2017h; uiAction
0x1800e6981  lea     r9d, [rdx+3]; fWinIni
0x1800e6985  call    cs:__imp_SystemParametersInfoW
0x1800e698b  test    eax, eax
0x1800e698d  jz      short loc_1800E69B6
0x1800e698f  lea     rcx, [rdi+158h]
0x1800e6996  lea     rdx, [rsp+28h+arg_8]
0x1800e699b  call    ?data@?$tip_test@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::data(void)
0x1800e69a0  mov     rcx, [rax]
0x1800e69a3  mov     byte ptr [rcx+11Ah], 1
0x1800e69aa  lea     rcx, [rsp+28h+arg_8]
0x1800e69af  call    ??1?$test_data_control@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>(void)
0x1800e69b4  jmp     short loc_1800E69CC
0x1800e69b6  mov     rcx, [rsp+28h]; this
0x1800e69bb  lea     r8, aPcshellShellCl_32; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800e69c2  mov     edx, 1D8h; void *
0x1800e69c7  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800e69cc  mov     rbx, [rsp+28h+arg_10]
0x1800e69d1  add     rsp, 20h
0x1800e69d5  pop     rdi
0x1800e69d6  retn
```
