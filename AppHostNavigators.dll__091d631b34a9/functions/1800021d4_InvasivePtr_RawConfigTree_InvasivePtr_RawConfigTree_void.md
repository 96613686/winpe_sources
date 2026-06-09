# InvasivePtr<RawConfigTree>::~InvasivePtr<RawConfigTree>(void)

- ea: `0x1800021d4`
- end: `0x1800021d9`
- name: `??1?$InvasivePtr@VRawConfigTree@@@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800135a2`
- `0x18001372d`
- `0x180013771`
- `0x180013809`
- `0x18001381b`
- `0x1800138c1`
- `0x180013c01`

## callees

- `0x180003a1c`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall InvasivePtr<RawConfigTree>::~InvasivePtr<RawConfigTree>(InvasivePtrObject **a1)
{
  return InvasivePtr<ConfigLocationsTree>::Reset(a1);
}

```

## disassembly

```asm
0x1800021d4  jmp     ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
```
