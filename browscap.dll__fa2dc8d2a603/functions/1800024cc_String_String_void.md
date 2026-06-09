# String::~String(void)

- ea: `0x1800024cc`
- end: `0x1800024d1`
- name: `??1String@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(String *__hidden this)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bd91`
- `0x18000bda3`
- `0x18000bdc7`
- `0x18000bdf4`
- `0x18000be3c`
- `0x18000be60`
- `0x18000bf02`
- `0x18000bfc8`
- `0x18000bfda`
- `0x18000c014`
- `0x18000c052`
- `0x18000c064`
- `0x18000c0f8`
- `0x18000c136`
- `0x18000c148`

## callees

- `0x180002498`

## pseudocode

```c
// attributes: thunk
void __fastcall String::~String(__int64 *this)
{
  TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(this);
}

```

## disassembly

```asm
0x1800024cc  jmp     ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
```
