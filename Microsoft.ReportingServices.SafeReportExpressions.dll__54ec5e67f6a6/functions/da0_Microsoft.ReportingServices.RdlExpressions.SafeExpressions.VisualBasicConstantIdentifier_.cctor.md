# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasicConstantIdentifier::.cctor

- ea: `0xda0`
- end: `0xdcf`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasicConstantIdentifier::.cctor`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xda0  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0xda5  dup
0xda6  ldstr    aVbcr// "VBCR"
0xdab  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xdb0  pop
0xdb1  dup
0xdb2  ldstr    aVblf// "VBLF"
0xdb7  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xdbc  pop
0xdbd  dup
0xdbe  ldstr    aVbcrlf// "VBCRLF"
0xdc3  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xdc8  pop
0xdc9  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasicConstantIdentifier::VisualBasicConstants
0xdce  ret
```
