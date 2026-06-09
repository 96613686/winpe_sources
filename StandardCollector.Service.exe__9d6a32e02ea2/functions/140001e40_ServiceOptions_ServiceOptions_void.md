# ServiceOptions::~ServiceOptions(void)

- ea: `0x140001e40`
- end: `0x140001e49`
- name: `??1ServiceOptions@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(ServiceOptions *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140014c96`
- `0x140015090`

## callees

- `0x140003010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ServiceOptions::~ServiceOptions(ServiceOptions *this)
{
  std::wstring::~wstring((__int64)this + 8);
}

```

## disassembly

```asm
0x140001e40  add     rcx, 8
0x140001e44  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
