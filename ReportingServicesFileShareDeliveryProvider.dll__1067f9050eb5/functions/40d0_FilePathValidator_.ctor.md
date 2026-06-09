# FilePathValidator::.ctor

- ea: `0x40d0`
- end: `0x40f4`
- name: `FilePathValidator::.ctor`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x28d0`

## string_xrefs

- `0x40d7`: `ValidateUNCPath`

## pseudocode

```c

```

## disassembly

```asm
0x40d0  ldarg.0
0x40d1  call     instance void [System.Web]System.Web.UI.WebControls.CustomValidator::.ctor()
0x40d6  ldarg.0
0x40d7  ldstr    aValidateuncpat// "ValidateUNCPath"
0x40dc  call     instance void [System.Web]System.Web.UI.WebControls.CustomValidator::set_ClientValidationFunction(string)
0x40e1  ldarg.0
0x40e2  ldarg.0
0x40e3  ldftn    instance void FilePathValidator::Validate_Path(object source, class [System.Web]System.Web.UI.WebControls.ServerValidateEventArgs args)
0x40e9  newobj   instance void [System.Web]System.Web.UI.WebControls.ServerValidateEventHandler::.ctor(object, native int)
0x40ee  call     instance void [System.Web]System.Web.UI.WebControls.CustomValidator::add_ServerValidate(class [System.Web]System.Web.UI.WebControls.ServerValidateEventHandler)
0x40f3  ret
```
