# AccessibilityBackupRestoreHandler::RestoreTouchIndicatorSetting(void)

- ea: `0x1800e71e4`
- end: `0x1800e72ef`
- name: `?RestoreTouchIndicatorSetting@AccessibilityBackupRestoreHandler@@AEAAXXZ`
- size: `267`
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
- `0x1800e71e4`
- `0x1800e787c`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x1800e7239`
- `USER32!SystemParametersInfoW` at `0x1800e729d`
- `USER32!SystemParametersInfoW` at `0x1800e7239`
- `USER32!SystemParametersInfoW` at `0x1800e729d`

## string_xrefs

- `0x1800e7248`: `pcshell\shell\cloudrestorelauncher\cloudbackuprestore\accessibilitybackuprestorehandler.cpp`
- `0x1800e72d3`: `pcshell\shell\cloudrestorelauncher\cloudbackuprestore\accessibilitybackuprestorehandler.cpp`

## pseudocode

```c
void __fastcall AccessibilityBackupRestoreHandler::RestoreTouchIndicatorSetting(
        AccessibilityBackupRestoreHandler *this)
{
  const unsigned __int16 *v1; // r8
  const unsigned __int16 *v2; // rdx
  unsigned int v4; // eax
  const char *v5; // r9
  const unsigned __int16 *v6; // r8
  const unsigned __int16 *v7; // rdx
  unsigned int v8; // ebx
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v11; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v12; // [rsp+38h] [rbp+10h] BYREF
  char v13; // [rsp+40h] [rbp+18h] BYREF

  v1 = (const unsigned __int16 *)*((_QWORD *)this + 74);
  v2 = (const unsigned __int16 *)*((_QWORD *)this + 72);
  v11 = 1;
  if ( (unsigned int)SHRegGetDWORD(HKEY_CURRENT_USER, v2, v1, &v11) )
  {
    v4 = 1;
    v11 = 1;
  }
  else
  {
    v4 = v11;
  }
  if ( !SystemParametersInfoW(0x2019u, 0, (PVOID)v4, 3u) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x1B5,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\accessibilitybackuprestorehandler.cpp",
      v5);
  v6 = (const unsigned __int16 *)*((_QWORD *)this + 73);
  v7 = (const unsigned __int16 *)*((_QWORD *)this + 72);
  v8 = 31;
  v12 = 31;
  if ( (unsigned int)SHRegGetDWORD(HKEY_CURRENT_USER, v7, v6, &v12) )
    v12 = 31;
  else
    v8 = v12;
  if ( SystemParametersInfoW(0x201Bu, 0, (PVOID)v8, 3u) )
  {
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::data(
                            (char *)this + 344,
                            &v13)
             + 281LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>(&v13);
  }
  else
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x1C4,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\accessibilitybackuprestorehandler.cpp",
      v9);
  }
}

```

## disassembly

```asm
0x1800e71e4  mov     [rsp+arg_18], rbx
0x1800e71e9  push    rdi
0x1800e71ea  sub     rsp, 20h
0x1800e71ee  mov     r8, [rcx+250h]; unsigned __int16 *
0x1800e71f5  lea     r9, [rsp+28h+arg_0]; unsigned int *
0x1800e71fa  mov     rdx, [rcx+240h]; unsigned __int16 *
0x1800e7201  mov     rdi, rcx
0x1800e7204  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800e720b  mov     [rsp+28h+arg_0], 1
0x1800e7213  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800e7218  test    eax, eax
0x1800e721a  jz      short loc_1800E7227
0x1800e721c  mov     eax, 1
0x1800e7221  mov     [rsp+28h+arg_0], eax
0x1800e7225  jmp     short loc_1800E722B
0x1800e7227  mov     eax, [rsp+28h+arg_0]
0x1800e722b  xor     edx, edx; uiParam
0x1800e722d  mov     r8d, eax; pvParam
0x1800e7230  mov     ecx, 2019h; uiAction
0x1800e7235  lea     r9d, [rdx+3]; fWinIni
0x1800e7239  call    cs:__imp_SystemParametersInfoW
0x1800e723f  test    eax, eax
0x1800e7241  jnz     short loc_1800E7259
0x1800e7243  mov     rcx, [rsp+28h]; this
0x1800e7248  lea     r8, aPcshellShellCl_32; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800e724f  mov     edx, 1B5h; void *
0x1800e7254  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800e7259  mov     r8, [rdi+248h]; unsigned __int16 *
0x1800e7260  lea     r9, [rsp+28h+arg_8]; unsigned int *
0x1800e7265  mov     rdx, [rdi+240h]; unsigned __int16 *
0x1800e726c  mov     ebx, 1Fh
0x1800e7271  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800e7278  mov     [rsp+28h+arg_8], ebx
0x1800e727c  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800e7281  test    eax, eax
0x1800e7283  jz      short loc_1800E728B
0x1800e7285  mov     [rsp+28h+arg_8], ebx
0x1800e7289  jmp     short loc_1800E728F
0x1800e728b  mov     ebx, [rsp+28h+arg_8]
0x1800e728f  xor     edx, edx; uiParam
0x1800e7291  mov     r8d, ebx; pvParam
0x1800e7294  mov     ecx, 201Bh; uiAction
0x1800e7299  lea     r9d, [rdx+3]; fWinIni
0x1800e729d  call    cs:__imp_SystemParametersInfoW
0x1800e72a3  test    eax, eax
0x1800e72a5  jz      short loc_1800E72CE
0x1800e72a7  lea     rcx, [rdi+158h]
0x1800e72ae  lea     rdx, [rsp+28h+arg_10]
0x1800e72b3  call    ?data@?$tip_test@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::data(void)
0x1800e72b8  mov     rcx, [rax]
0x1800e72bb  mov     byte ptr [rcx+119h], 1
0x1800e72c2  lea     rcx, [rsp+28h+arg_10]
0x1800e72c7  call    ??1?$test_data_control@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>(void)
0x1800e72cc  jmp     short loc_1800E72E4
0x1800e72ce  mov     rcx, [rsp+28h]; this
0x1800e72d3  lea     r8, aPcshellShellCl_32; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800e72da  mov     edx, 1C4h; void *
0x1800e72df  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800e72e4  mov     rbx, [rsp+28h+arg_18]
0x1800e72e9  add     rsp, 20h
0x1800e72ed  pop     rdi
0x1800e72ee  retn
```
