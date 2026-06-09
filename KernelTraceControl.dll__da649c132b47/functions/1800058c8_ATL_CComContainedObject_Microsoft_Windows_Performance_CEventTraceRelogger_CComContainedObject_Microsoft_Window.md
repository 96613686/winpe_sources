# ATL::CComContainedObject<Microsoft::Windows::Performance::CEventTraceRelogger>::~CComContainedObject<Microsoft::Windows::Performance::CEventTraceRelogger>(void)

- ea: `0x1800058c8`
- end: `0x1800058cd`
- name: `??1?$CComContainedObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180027b85`
- `0x180027c0d`

## callees

- `0x1800029e4`

## pseudocode

```c
// attributes: thunk
void __fastcall ATL::CComContainedObject<Microsoft::Windows::Performance::CEventTraceRelogger>::~CComContainedObject<Microsoft::Windows::Performance::CEventTraceRelogger>(
        Microsoft::Windows::Performance::CEventTraceRelogger *a1)
{
  Microsoft::Windows::Performance::CEventTraceRelogger::~CEventTraceRelogger(a1);
}

```

## disassembly

```asm
0x1800058c8  jmp     ??1CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventTraceRelogger::~CEventTraceRelogger(void)
```
