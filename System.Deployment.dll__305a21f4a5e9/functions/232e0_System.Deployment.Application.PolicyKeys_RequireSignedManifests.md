# System.Deployment.Application.PolicyKeys::RequireSignedManifests

- ea: `0x232e0`
- end: `0x232f2`
- name: `System.Deployment.Application.PolicyKeys::RequireSignedManifests`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x25a00`

## callees

- `0x232e0`
- `0x23570`

## string_xrefs

- `0x232e0`: `RequireSignedManifests`

## pseudocode

```c

```

## disassembly

```asm
0x232e0  ldstr    aRequiresignedm// "RequireSignedManifests"
0x232e5  ldc.i4.1
0x232e6  ldc.i4.0
0x232e7  call     bool System.Deployment.Application.PolicyKeys::CheckDeploymentBoolString(string keyName, bool compare, bool defaultIfNotSet)
0x232ec  brfalse.s loc_232F0
0x232ee  ldc.i4.1
0x232ef  ret
0x232f0  ldc.i4.0
0x232f1  ret
```
