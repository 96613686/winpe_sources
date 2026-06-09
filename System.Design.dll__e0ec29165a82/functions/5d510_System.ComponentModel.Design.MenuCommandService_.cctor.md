# System.ComponentModel.Design.MenuCommandService::.cctor

- ea: `0x5d510`
- end: `0x5d525`
- name: `System.ComponentModel.Design.MenuCommandService::.cctor`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x5d510`: `MENUSERVICE`
- `0x5d515`: `MenuCommandService: Track menu command routing`

## pseudocode

```c

```

## disassembly

```asm
0x5d510  ldstr    aMenuservice// "MENUSERVICE"
0x5d515  ldstr    aMenucommandser_0// "MenuCommandService: Track menu command "...
0x5d51a  newobj   instance void [System]System.Diagnostics.TraceSwitch::.ctor(string, string)
0x5d51f  stsfld   class [System]System.Diagnostics.TraceSwitch System.ComponentModel.Design.MenuCommandService::MENUSERVICE
0x5d524  ret
```
