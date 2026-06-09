# Microsoft.EventViewer.SnapIn.EventViewerSnapIn::SetRegistryForHelpChmFiles

- ea: `0x3b0`
- end: `0x40b`
- name: `Microsoft.EventViewer.SnapIn.EventViewerSnapIn::SetRegistryForHelpChmFiles`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5f0`
- `0x13f0`

## callees

- `0x3b0`

## string_xrefs

- `0x3da`: `LinkedHelpTopics`
- `0x3fa`: `LinkedHelpTopics`

## pseudocode

```c

```

## disassembly

```asm
0x3b0  ldstr    aWindir// "windir"
0x3b5  call     string [mscorlib]System.Environment::GetEnvironmentVariable(string)
0x3ba  ldstr    aHelpEventviewe// "\\Help\\eventviewer.chm"
0x3bf  call     string [mscorlib]System.String::Concat(string, string)
0x3c4  stloc.0
0x3c5  ldstr    aHkeyLocalMachi// "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x3ca  ldstr    aHelptopic// "HelpTopic"
0x3cf  ldloc.0
0x3d0  call     void [mscorlib]Microsoft.Win32.Registry::SetValue(string, string, object)
0x3d5  ldstr    aHkeyLocalMachi// "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x3da  ldstr    aLinkedhelptopi// "LinkedHelpTopics"
0x3df  ldloc.0
0x3e0  call     void [mscorlib]Microsoft.Win32.Registry::SetValue(string, string, object)
0x3e5  ldstr    aHkeyLocalMachi_0// "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x3ea  ldstr    aHelptopic// "HelpTopic"
0x3ef  ldloc.0
0x3f0  call     void [mscorlib]Microsoft.Win32.Registry::SetValue(string, string, object)
0x3f5  ldstr    aHkeyLocalMachi_0// "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x3fa  ldstr    aLinkedhelptopi// "LinkedHelpTopics"
0x3ff  ldloc.0
0x400  call     void [mscorlib]Microsoft.Win32.Registry::SetValue(string, string, object)
0x405  leave.s  loc_40A
0x407  pop
0x408  leave.s  loc_40A
0x40a  ret
```
