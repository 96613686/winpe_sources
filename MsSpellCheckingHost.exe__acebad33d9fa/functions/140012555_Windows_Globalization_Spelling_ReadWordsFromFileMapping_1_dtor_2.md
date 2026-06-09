# _Windows::Globalization::Spelling::ReadWordsFromFileMapping_::_1_::dtor$2

- ea: `0x140012555`
- end: `0x140012561`
- name: `_Windows::Globalization::Spelling::ReadWordsFromFileMapping_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140010b38`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::ReadWordsFromFileMapping_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(
           (__int64 *)(a2 + 248),
           a2);
}

```

## disassembly

```asm
0x140012555  lea     rcx, [rdx+0F8h]
0x14001255c  jmp     ??1?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@XZ; std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(void)
```
