# DsvInfoBinary::Microsoft.ReportingServices.Modeling.DataSourceView.IDsvInfo.Load

- ea: `0x2fb10`
- end: `0x2fb1b`
- name: `DsvInfoBinary::Microsoft.ReportingServices.Modeling.DataSourceView.IDsvInfo.Load`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x97d0`

## string_xrefs

- `0x2fb10`: `Load(XmlReader) is not supported.`

## pseudocode

```c

```

## disassembly

```asm
0x2fb10  ldstr    aLoadXmlreaderI// "Load(XmlReader) is not supported."
0x2fb15  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x2fb1a  throw
```
