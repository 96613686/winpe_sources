# Fdo::GetRecorderLog(void)

- ea: `0x140001ca8`
- end: `0x140001cad`
- name: `?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ`
- size: `5`
- prototype: `struct RECORDER_LOG__ *__fastcall(Fdo *__hidden this)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x14001868c`
- `0x140018764`
- `0x140018910`
- `0x140018a70`
- `0x140018b00`
- `0x140018b90`
- `0x140018f10`
- `0x140019008`
- `0x14001946c`
- `0x140019764`
- `0x140019894`
- `0x14001a054`

## pseudocode

```c
struct RECORDER_LOG__ *__fastcall Fdo::GetRecorderLog(Fdo *this)
{
  return (struct RECORDER_LOG__ *)*((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x140001ca8  mov     rax, [rcx+8]
0x140001cac  retn
```
