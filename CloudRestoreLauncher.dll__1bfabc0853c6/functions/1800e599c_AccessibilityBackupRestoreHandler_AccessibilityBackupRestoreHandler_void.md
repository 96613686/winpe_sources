# AccessibilityBackupRestoreHandler::AccessibilityBackupRestoreHandler(void)

- ea: `0x1800e599c`
- end: `0x1800e5bbb`
- name: `??0AccessibilityBackupRestoreHandler@@QEAA@XZ`
- size: `543`
- prototype: `AccessibilityBackupRestoreHandler *__fastcall(AccessibilityBackupRestoreHandler *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e5e00`

## callees

- `0x1800154e4`

## string_xrefs

- `0x1800e59da`: `Software\Microsoft\Accessibility`
- `0x1800e59b3`: `AccessibilitySettingsActivity`
- `0x1800e5aac`: `Control Panel\Accessibility\MouseKeys`
- `0x1800e5ad6`: `Control Panel\Accessibility\SoundSentry`
- `0x1800e5af2`: `Control Panel\Accessibility\Keyboard Preference`
- `0x1800e5a3c`: `Control Panel\Accessibility\ToggleKeys`
- `0x1800e5a4a`: `Control Panel\Accessibility\StickyKeys`
- `0x1800e5a58`: `Control Panel\Accessibility\Keyboard Response`
- `0x1800e5b38`: `Control Panel\Accessibility`

## pseudocode

```c
AccessibilityBackupRestoreHandler *__fastcall AccessibilityBackupRestoreHandler::AccessibilityBackupRestoreHandler(
        AccessibilityBackupRestoreHandler *this)
{
  AccessibilityBackupRestoreHandler *result; // rax

  *(_QWORD *)this = &AccessibilityBackupRestoreHandler::`vftable';
  wil::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((AccessibilityBackupRestoreHandler *)((char *)this + 8));
  *((_QWORD *)this + 1) = &CloudRestoreLauncherTelemetry::AccessibilitySettingsActivity::`vftable';
  *((_QWORD *)this + 45) = L"Software\\Microsoft\\Accessibility";
  *((_QWORD *)this + 46) = L"CursorSize";
  *((_QWORD *)this + 47) = L"CursorTypeMigration";
  *((_QWORD *)this + 48) = L"CursorType";
  *((_QWORD *)this + 49) = L"CursorColor";
  *((_QWORD *)this + 50) = L"Control Panel\\Desktop\\WindowMetrics";
  *((_QWORD *)this + 51) = L"MinAnimateMigration";
  *((_QWORD *)this + 52) = L"Control Panel\\Accessibility\\ToggleKeys";
  *((_QWORD *)this + 54) = L"Control Panel\\Accessibility\\StickyKeys";
  *((_QWORD *)this + 56) = L"Control Panel\\Accessibility\\Keyboard Response";
  *((_QWORD *)this + 58) = L"Software\\Microsoft\\Osk";
  *((_QWORD *)this + 59) = L"KeystrokeDelay";
  *((_QWORD *)this + 60) = L"BounceTime";
  *((_QWORD *)this + 61) = L"FirstRepeatDelay";
  *((_QWORD *)this + 62) = L"NextRepeatDelay";
  *((_QWORD *)this + 63) = L"Control Panel\\Accessibility\\MouseKeys";
  *((_QWORD *)this + 65) = L"MaximumSpeed";
  *((_QWORD *)this + 66) = L"TimeToMaximumSpeed";
  *((_QWORD *)this + 67) = L"Control Panel\\Accessibility\\SoundSentry";
  *((_QWORD *)this + 68) = L"WindowsEffect";
  *((_QWORD *)this + 70) = L"Control Panel\\Accessibility\\Keyboard Preference";
  *((_QWORD *)this + 71) = L"On";
  *((_QWORD *)this + 72) = L"Control Panel\\Cursors";
  *((_QWORD *)this + 73) = L"GestureVisualization";
  *((_QWORD *)this + 74) = L"ContactVisualization";
  *((_QWORD *)this + 75) = L"Control Panel\\Accessibility";
  *((_QWORD *)this + 76) = L"MessageDuration";
  *((_QWORD *)this + 77) = L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes";
  *((_QWORD *)this + 78) = L"Control Panel\\Appearance";
  result = this;
  *((_QWORD *)this + 43) = 0;
  *((_DWORD *)this + 88) = 32;
  *((_DWORD *)this + 89) = 2;
  *((_QWORD *)this + 53) = L"Flags";
  *((_QWORD *)this + 55) = L"Flags";
  *((_QWORD *)this + 57) = L"Flags";
  *((_QWORD *)this + 64) = L"Flags";
  *((_QWORD *)this + 69) = L"Flags";
  return result;
}

```

## disassembly

```asm
0x1800e599c  mov     [rsp+arg_0], rbx
0x1800e59a1  push    rdi
0x1800e59a2  sub     rsp, 20h
0x1800e59a6  lea     rax, ??_7AccessibilityBackupRestoreHandler@@6B@; const AccessibilityBackupRestoreHandler::`vftable'
0x1800e59ad  mov     rdi, rcx
0x1800e59b0  mov     [rcx], rax
0x1800e59b3  lea     rdx, aAccessibilitys_1; "AccessibilitySettingsActivity"
0x1800e59ba  add     rcx, 8; struct wil::details::IFailureCallback *
0x1800e59be  call    ??0?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800e59c3  mov     rbx, [rsp+28h+arg_0]
0x1800e59c8  lea     rcx, aFlags; "Flags"
0x1800e59cf  lea     rax, ??_7AccessibilitySettingsActivity@CloudRestoreLauncherTelemetry@@6B@; const CloudRestoreLauncherTelemetry::AccessibilitySettingsActivity::`vftable'
0x1800e59d6  mov     [rdi+8], rax
0x1800e59da  lea     rax, aSoftwareMicros_32; "Software\\Microsoft\\Accessibility"
0x1800e59e1  mov     [rdi+168h], rax
0x1800e59e8  lea     rax, aCursorsize; "CursorSize"
0x1800e59ef  mov     [rdi+170h], rax
0x1800e59f6  lea     rax, aCursortypemigr; "CursorTypeMigration"
0x1800e59fd  mov     [rdi+178h], rax
0x1800e5a04  lea     rax, aCursortype; "CursorType"
0x1800e5a0b  mov     [rdi+180h], rax
0x1800e5a12  lea     rax, aCursorcolor; "CursorColor"
0x1800e5a19  mov     [rdi+188h], rax
0x1800e5a20  lea     rax, aControlPanelDe; "Control Panel\\Desktop\\WindowMetrics"
0x1800e5a27  mov     [rdi+190h], rax
0x1800e5a2e  lea     rax, aMinanimatemigr; "MinAnimateMigration"
0x1800e5a35  mov     [rdi+198h], rax
0x1800e5a3c  lea     rax, aControlPanelAc_1; "Control Panel\\Accessibility\\ToggleKey"...
0x1800e5a43  mov     [rdi+1A0h], rax
0x1800e5a4a  lea     rax, aControlPanelAc_5; "Control Panel\\Accessibility\\StickyKey"...
0x1800e5a51  mov     [rdi+1B0h], rax
0x1800e5a58  lea     rax, aControlPanelAc_0; "Control Panel\\Accessibility\\Keyboard "...
0x1800e5a5f  mov     [rdi+1C0h], rax
0x1800e5a66  lea     rax, aSoftwareMicros_5; "Software\\Microsoft\\Osk"
0x1800e5a6d  mov     [rdi+1D0h], rax
0x1800e5a74  lea     rax, aKeystrokedelay; "KeystrokeDelay"
0x1800e5a7b  mov     [rdi+1D8h], rax
0x1800e5a82  lea     rax, aBouncetime; "BounceTime"
0x1800e5a89  mov     [rdi+1E0h], rax
0x1800e5a90  lea     rax, aFirstrepeatdel; "FirstRepeatDelay"
0x1800e5a97  mov     [rdi+1E8h], rax
0x1800e5a9e  lea     rax, aNextrepeatdela; "NextRepeatDelay"
0x1800e5aa5  mov     [rdi+1F0h], rax
0x1800e5aac  lea     rax, aControlPanelAc; "Control Panel\\Accessibility\\MouseKeys"
0x1800e5ab3  mov     [rdi+1F8h], rax
0x1800e5aba  lea     rax, aMaximumspeed; "MaximumSpeed"
0x1800e5ac1  mov     [rdi+208h], rax
0x1800e5ac8  lea     rax, aTimetomaximums; "TimeToMaximumSpeed"
0x1800e5acf  mov     [rdi+210h], rax
0x1800e5ad6  lea     rax, aControlPanelAc_6; "Control Panel\\Accessibility\\SoundSent"...
0x1800e5add  mov     [rdi+218h], rax
0x1800e5ae4  lea     rax, aWindowseffect; "WindowsEffect"
0x1800e5aeb  mov     [rdi+220h], rax
0x1800e5af2  lea     rax, aControlPanelAc_2; "Control Panel\\Accessibility\\Keyboard "...
0x1800e5af9  mov     [rdi+230h], rax
0x1800e5b00  lea     rax, aOn; "On"
0x1800e5b07  mov     [rdi+238h], rax
0x1800e5b0e  lea     rax, aControlPanelCu; "Control Panel\\Cursors"
0x1800e5b15  mov     [rdi+240h], rax
0x1800e5b1c  lea     rax, aGesturevisuali; "GestureVisualization"
0x1800e5b23  mov     [rdi+248h], rax
0x1800e5b2a  lea     rax, aContactvisuali; "ContactVisualization"
0x1800e5b31  mov     [rdi+250h], rax
0x1800e5b38  lea     rax, aControlPanelAc_4; "Control Panel\\Accessibility"
0x1800e5b3f  mov     [rdi+258h], rax
0x1800e5b46  lea     rax, aMessageduratio; "MessageDuration"
0x1800e5b4d  mov     [rdi+260h], rax
0x1800e5b54  lea     rax, aSoftwareMicros_19; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800e5b5b  mov     [rdi+268h], rax
0x1800e5b62  lea     rax, aControlPanelAp; "Control Panel\\Appearance"
0x1800e5b69  mov     [rdi+270h], rax
0x1800e5b70  mov     rax, rdi
0x1800e5b73  mov     qword ptr [rdi+158h], 0
0x1800e5b7e  mov     dword ptr [rdi+160h], 20h ; ' '
0x1800e5b88  mov     dword ptr [rdi+164h], 2
0x1800e5b92  mov     [rdi+1A8h], rcx
0x1800e5b99  mov     [rdi+1B8h], rcx
0x1800e5ba0  mov     [rdi+1C8h], rcx
0x1800e5ba7  mov     [rdi+200h], rcx
0x1800e5bae  mov     [rdi+228h], rcx
0x1800e5bb5  add     rsp, 20h
0x1800e5bb9  pop     rdi
0x1800e5bba  retn
```
