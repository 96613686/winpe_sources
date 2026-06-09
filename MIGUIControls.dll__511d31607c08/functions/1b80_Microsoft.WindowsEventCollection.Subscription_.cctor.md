# Microsoft.WindowsEventCollection.Subscription::.cctor

- ea: `0x1b80`
- end: `0x1bc2`
- name: `Microsoft.WindowsEventCollection.Subscription::.cctor`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x1b80`: `http://schemas.microsoft.com/wbem/wsman/1/windows/EventLog`
- `0x1ba3`: `<QueryList><Query Path="Application"><Select>*</Select></Query></QueryList>`
- `0x1bad`: `SOFTWARE\Microsoft\Windows\CurrentVersion\EventCollector\ConfigurationModes\`

## pseudocode

```c

```

## disassembly

```asm
0x1b80  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/wbem/wsman"...
0x1b85  newobj   instance void [System]System.Uri::.ctor(string)
0x1b8a  stsfld   class [System]System.Uri Microsoft.WindowsEventCollection.Subscription::EventLogEventsUri
0x1b8f  ldsfld   class [System]System.Uri Microsoft.WindowsEventCollection.Subscription::EventLogEventsUri
0x1b94  stsfld   class [System]System.Uri Microsoft.WindowsEventCollection.Subscription::DefaultUri
0x1b99  ldstr    aMicrosoftWindo// "Microsoft-Windows-EventCollector"
0x1b9e  stsfld   string Microsoft.WindowsEventCollection.Subscription::DefaultPublisherName
0x1ba3  ldstr    aQuerylistQuery// "<QueryList><Query Path=\"Application\">"...
0x1ba8  stsfld   string Microsoft.WindowsEventCollection.Subscription::EventLogSampleQuery
0x1bad  ldstr    aSoftwareMicros// "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1bb2  stsfld   string Microsoft.WindowsEventCollection.Subscription::keyNameBase
0x1bb7  ldstr    aDeliverymode// "DeliveryMode"
0x1bbc  stsfld   string Microsoft.WindowsEventCollection.Subscription::valueName
0x1bc1  ret
```
