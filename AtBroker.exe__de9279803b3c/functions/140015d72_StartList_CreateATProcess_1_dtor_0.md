# _StartList::CreateATProcess_::_1_::dtor$0

- ea: `0x140015d72`
- end: `0x140015d7e`
- name: `_StartList::CreateATProcess_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000c2bc`

## pseudocode

```c
void __fastcall StartList::CreateATProcess_::_1_::dtor_0(__int64 a1, __int64 a2, int a3)
{
  _Trace::~_Trace((_Trace *)(a2 + 80), a2, a3);
}

```

## disassembly

```asm
0x140015d72  lea     rcx, [rdx+50h]; this
0x140015d79  jmp     ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
```
