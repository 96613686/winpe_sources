# _Windows::Globalization::Spelling::ReadWordsFromFileMapping_::_1_::dtor$4

- ea: `0x140012567`
- end: `0x140012573`
- name: `_Windows::Globalization::Spelling::ReadWordsFromFileMapping_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140010b38`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::ReadWordsFromFileMapping_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(
           (__int64 *)(a2 + 208),
           a2);
}

```

## disassembly

```asm
0x140012567  lea     rcx, [rdx+0D0h]
0x14001256e  jmp     ??1?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@XZ; std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(void)
```
