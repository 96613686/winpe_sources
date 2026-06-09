# ?PopVecCallback@CrashDetails@Mso@@YAP6AXI@_EXZ

- ea: `0x140002dfc`
- end: `0x140002e0f`
- name: `?PopVecCallback@CrashDetails@Mso@@YAP6AXI@_EXZ`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140002970`

## pseudocode

```c
__int64 Mso::CrashDetails::PopVecCallback()
{
  __int64 result; // rax

  result = Mso::CrashDetails::s_verifyElseCrash_Callback;
  Mso::CrashDetails::s_verifyElseCrash_Callback = 0;
  return result;
}

```

## disassembly

```asm
0x140002dfc  mov     rax, cs:?s_verifyElseCrash_Callback@CrashDetails@Mso@@3P6AXI@_EEA
0x140002e03  mov     cs:?s_verifyElseCrash_Callback@CrashDetails@Mso@@3P6AXI@_EEA, 0
0x140002e0e  retn
```
