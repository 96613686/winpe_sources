# System.Web.UI.Design.WebControls.SqlDataSourceDesigner::.cctor

- ea: `0x3efc0`
- end: `0x3f004`
- name: `System.Web.UI.Design.WebControls.SqlDataSourceDesigner::.cctor`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x3efc8`: `DeleteCommand`
- `0x3efd0`: `DeleteParameters`
- `0x3efd8`: `InsertCommand`
- `0x3eff0`: `UpdateCommand`
- `0x3eff8`: `UpdateParameters`

## pseudocode

```c

```

## disassembly

```asm
0x3efc0  ldc.i4.7
0x3efc1  newarr   [mscorlib]System.String
0x3efc6  dup
0x3efc7  ldc.i4.0
0x3efc8  ldstr    aDeletecommand// "DeleteCommand"
0x3efcd  stelem.ref
0x3efce  dup
0x3efcf  ldc.i4.1
0x3efd0  ldstr    aDeleteparamete_0// "DeleteParameters"
0x3efd5  stelem.ref
0x3efd6  dup
0x3efd7  ldc.i4.2
0x3efd8  ldstr    aInsertcommand// "InsertCommand"
0x3efdd  stelem.ref
0x3efde  dup
0x3efdf  ldc.i4.3
0x3efe0  ldstr    aInsertparamete// "InsertParameters"
0x3efe5  stelem.ref
0x3efe6  dup
0x3efe7  ldc.i4.4
0x3efe8  ldstr    aSelectparamete// "SelectParameters"
0x3efed  stelem.ref
0x3efee  dup
0x3efef  ldc.i4.5
0x3eff0  ldstr    aUpdatecommand// "UpdateCommand"
0x3eff5  stelem.ref
0x3eff6  dup
0x3eff7  ldc.i4.6
0x3eff8  ldstr    aUpdateparamete// "UpdateParameters"
0x3effd  stelem.ref
0x3effe  stsfld   string[] System.Web.UI.Design.WebControls.SqlDataSourceDesigner::_hiddenProperties
0x3f003  ret
```
