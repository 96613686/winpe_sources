# InvasivePtr<AppHostConfigLocationsNavigator>::~InvasivePtr<AppHostConfigLocationsNavigator>(void)

- ea: `0x1800021c8`
- end: `0x1800021cd`
- name: `??1?$InvasivePtr@VAppHostConfigLocationsNavigator@@@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001355a`
- `0x18001356c`
- `0x180013590`
- `0x180013668`
- `0x1800137f7`
- `0x18001389d`
- `0x180013aa5`

## callees

- `0x1800039ec`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall InvasivePtr<AppHostConfigLocationsNavigator>::~InvasivePtr<AppHostConfigLocationsNavigator>(
        __int64 *a1)
{
  return InvasivePtr<AppHostConfigPathNavigator>::Reset(a1);
}

```

## disassembly

```asm
0x1800021c8  jmp     ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
```
