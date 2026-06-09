# Microsoft.Reporting.WebForms.ServerReport::get_ReportUrlNoScript

- ea: `0x243e0`
- end: `0x243fb`
- name: `Microsoft.Reporting.WebForms.ServerReport::get_ReportUrlNoScript`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14e00`

## callees

- `0x24380`
- `0x24400`

## string_xrefs

- `0x243f0`: `&rs:Command=Render&rs:Format=HTML5&rc:LinkTarget=_top&rc:Javascript=false&rc:Toolbar=false`

## pseudocode

```c

```

## disassembly

```asm
0x243e0  call     string Microsoft.Reporting.WebForms.ServerReport::get_RequestVirtualRoot()
0x243e5  ldstr    asc_4D44A// "?"
0x243ea  ldarg.0
0x243eb  call     string Microsoft.Reporting.WebForms.ServerReport::CreateReportIdentityUrlQuery(class Microsoft.Reporting.WebForms.ServerReport report)
0x243f0  ldstr    aRsCommandRende// "&rs:Command=Render&rs:Format=HTML5&rc:L"...
0x243f5  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x243fa  ret
```
