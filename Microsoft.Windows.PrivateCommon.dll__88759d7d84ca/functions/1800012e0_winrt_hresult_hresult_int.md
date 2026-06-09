# winrt::hresult::hresult(int)

- ea: `0x1800012e0`
- end: `0x1800012e6`
- name: `??0hresult@winrt@@QEAA@H@Z`
- size: `6`
- prototype: `winrt::hresult *__fastcall(winrt::hresult *this, int)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d90`
- `0x180005d90`
- `0x180005e50`
- `0x180006630`

## pseudocode

```c
winrt::hresult *__fastcall winrt::hresult::hresult(winrt::hresult *this, int a2)
{
  *(_DWORD *)this = a2;
  return this;
}

```

## disassembly

```asm
0x1800012e0  mov     [rcx], edx
0x1800012e2  mov     rax, rcx
0x1800012e5  retn
```
