# DsvInfoBinary::Microsoft.ReportingServices.Modeling.DataSourceView.IDsvInfo.WriteTo

- ea: `0x2fb20`
- end: `0x2fb2b`
- name: `DsvInfoBinary::Microsoft.ReportingServices.Modeling.DataSourceView.IDsvInfo.WriteTo`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x97d0`

## string_xrefs

- `0x2fb20`: `WriteTo(XmlWriter) is not supported.`

## pseudocode

```c

```

## disassembly

```asm
0x2fb20  ldstr    aWritetoXmlwrit// "WriteTo(XmlWriter) is not supported."
0x2fb25  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x2fb2a  throw
```
