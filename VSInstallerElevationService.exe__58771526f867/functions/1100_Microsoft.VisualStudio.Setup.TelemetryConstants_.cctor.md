# Microsoft.VisualStudio.Setup.TelemetryConstants::.cctor

- ea: `0x1100`
- end: `0x11dd`
- name: `Microsoft.VisualStudio.Setup.TelemetryConstants::.cctor`
- size: `221`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x1100`: `vs/setup/elevationservice/`
- `0x110a`: `vs.setup.elevationservice.`
- `0x1119`: `run-service`
- `0x11b9`: `validate-installerservice-error`
- `0x11cd`: `create-pipe-error`

## pseudocode

```c

```

## disassembly

```asm
0x1100  ldstr    aVsSetupElevati// "vs/setup/elevationservice/"
0x1105  stsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::BaseEventName
0x110a  ldstr    aVsSetupElevati_0// "vs.setup.elevationservice."
0x110f  stsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::BasePropertyName
0x1114  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::BaseEventName
0x1119  ldstr    aRunService// "run-service"
0x111e  call     string [mscorlib]System.String::Concat(string, string)
0x1123  stsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationServiceRunOperationName
0x1128  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::BasePropertyName
0x112d  ldstr    aIsrundisabledb// "IsRunDisabledByPolicy"
0x1132  call     string [mscorlib]System.String::Concat(string, string)
0x1137  stsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationServiceRunDisabledByPolicyPropertyName
0x113c  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::BasePropertyName
0x1141  ldstr    aIsrundisabledb_0// "IsRunDisabledByRemoteSettings"
0x1146  call     string [mscorlib]System.String::Concat(string, string)
0x114b  stsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationServiceRunDisabledByRemoteSettingsPropertyName
0x1150  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::BaseEventName
0x1155  ldstr    aConnectClient// "connect-client"
0x115a  call     string [mscorlib]System.String::Concat(string, string)
0x115f  stsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationServiceManagerWaitingForConnectionEventName
0x1164  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::BaseEventName
0x1169  ldstr    aGetClientpidEr// "get-clientpid-error"
0x116e  call     string [mscorlib]System.String::Concat(string, string)
0x1173  stsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationServiceManagerGetClientPidFailure
0x1178  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::BaseEventName
0x117d  ldstr    aValidateClient// "validate-client-error"
0x1182  call     string [mscorlib]System.String::Concat(string, string)
0x1187  stsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationServiceManagerInvalidClientFailure
0x118c  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::BaseEventName
0x1191  ldstr    aWaitClientdisc// "wait-clientdisconnect"
0x1196  call     string [mscorlib]System.String::Concat(string, string)
0x119b  stsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationServiceManagerClientConnectionEventName
0x11a0  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::BaseEventName
0x11a5  ldstr    aRequestElevati// "request-elevation"
0x11aa  call     string [mscorlib]System.String::Concat(string, string)
0x11af  stsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationRequestEventName
0x11b4  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::BaseEventName
0x11b9  ldstr    aValidateInstal// "validate-installerservice-error"
0x11be  call     string [mscorlib]System.String::Concat(string, string)
0x11c3  stsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationRequestServiceValidateServiceFailure
0x11c8  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::BaseEventName
0x11cd  ldstr    aCreatePipeErro// "create-pipe-error"
0x11d2  call     string [mscorlib]System.String::Concat(string, string)
0x11d7  stsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationServiceManagerPipeCreationFailure
0x11dc  ret
```
