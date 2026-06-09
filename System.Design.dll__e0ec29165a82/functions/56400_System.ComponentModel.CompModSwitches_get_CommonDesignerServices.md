# System.ComponentModel.CompModSwitches::get_CommonDesignerServices

- ea: `0x56400`
- end: `0x56421`
- name: `System.ComponentModel.CompModSwitches::get_CommonDesignerServices`
- size: `33`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9d1d0`
- `0x9dac0`
- `0x9db40`
- `0x9ded0`
- `0x9e0e0`
- `0x1156b0`
- `0x115910`
- `0x1159a0`
- `0x115b50`
- `0x116290`

## callees

- `0x56400`

## string_xrefs

- `0x56407`: `CommonDesignerServices`
- `0x5640c`: `Assert if any common designer service is not found.`

## pseudocode

```c

```

## disassembly

```asm
0x56400  ldsfld   class [System]System.Diagnostics.BooleanSwitch System.ComponentModel.CompModSwitches::commonDesignerServices
0x56405  brtrue.s loc_5641B
0x56407  ldstr    aCommondesigner// "CommonDesignerServices"
0x5640c  ldstr    aAssertIfAnyCom// "Assert if any common designer service i"...
0x56411  newobj   instance void [System]System.Diagnostics.BooleanSwitch::.ctor(string, string)
0x56416  stsfld   class [System]System.Diagnostics.BooleanSwitch System.ComponentModel.CompModSwitches::commonDesignerServices
0x5641b  ldsfld   class [System]System.Diagnostics.BooleanSwitch System.ComponentModel.CompModSwitches::commonDesignerServices
0x56420  ret
```
