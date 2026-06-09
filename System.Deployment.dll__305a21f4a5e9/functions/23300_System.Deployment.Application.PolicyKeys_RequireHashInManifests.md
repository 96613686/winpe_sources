# System.Deployment.Application.PolicyKeys::RequireHashInManifests

- ea: `0x23300`
- end: `0x23312`
- name: `System.Deployment.Application.PolicyKeys::RequireHashInManifests`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x10240`

## callees

- `0x23300`
- `0x23570`

## string_xrefs

- `0x23300`: `RequireHashInManifests`

## pseudocode

```c

```

## disassembly

```asm
0x23300  ldstr    aRequirehashinm// "RequireHashInManifests"
0x23305  ldc.i4.1
0x23306  ldc.i4.0
0x23307  call     bool System.Deployment.Application.PolicyKeys::CheckDeploymentBoolString(string keyName, bool compare, bool defaultIfNotSet)
0x2330c  brfalse.s loc_23310
0x2330e  ldc.i4.1
0x2330f  ret
0x23310  ldc.i4.0
0x23311  ret
```
