# Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsConstants::.cctor

- ea: `0x49000`
- end: `0x49060`
- name: `Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsConstants::.cctor`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x49000`: `VS Installer`
- `0x49019`: `vs\installer\surveyactions`
- `0x49023`: `vs\installer\notices`
- `0x4902d`: `vs\installer\commonerroractions`
- `0x49037`: `vs\installer\workloadoverrides`
- `0x49041`: `vs\installer\helplink`
- `0x4904b`: `vs\installer\releasenotes`
- `0x49055`: `vs\installer\bulletins`

## pseudocode

```c

```

## disassembly

```asm
0x49000  ldstr    aVsInstaller_0// "VS Installer"
0x49005  stsfld   string Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsConstants::ProductName
0x4900a  ldstr    a42123b4554714b// "42123B45-5471-4B16-81E7-5404CD93BCF1"
0x4900f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x49014  stsfld   valuetype [mscorlib]System.Guid Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsConstants::AppId
0x49019  ldstr    aVsInstallerSur// "vs\\installer\\surveyactions"
0x4901e  stsfld   string Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsConstants::SurveyActionsPath
0x49023  ldstr    aVsInstallerNot// "vs\\installer\\notices"
0x49028  stsfld   string Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsConstants::NoticeActionsPath
0x4902d  ldstr    aVsInstallerCom// "vs\\installer\\commonerroractions"
0x49032  stsfld   string Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsConstants::CommonErrorActionsPath
0x49037  ldstr    aVsInstallerWor// "vs\\installer\\workloadoverrides"
0x4903c  stsfld   string Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsConstants::WorkloadOverridesActionsPath
0x49041  ldstr    aVsInstallerHel// "vs\\installer\\helplink"
0x49046  stsfld   string Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsConstants::HelpLinkActionsPath
0x4904b  ldstr    aVsInstallerRel// "vs\\installer\\releasenotes"
0x49050  stsfld   string Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsConstants::ReleaseNotesActionPath
0x49055  ldstr    aVsInstallerBul// "vs\\installer\\bulletins"
0x4905a  stsfld   string Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsConstants::BulletinActionsPath
0x4905f  ret
```
