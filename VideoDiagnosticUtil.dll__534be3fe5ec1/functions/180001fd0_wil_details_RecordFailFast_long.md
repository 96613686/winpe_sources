# wil::details::RecordFailFast(long)

- ea: `0x180001fd0`
- end: `0x180001fdc`
- name: `?RecordFailFast@details@wil@@YAHJ@Z`
- size: `12`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800026b4`
- `0x180004c50`

## pseudocode

```c
__int64 __fastcall wil::details::RecordFailFast(wil::details *this)
{
  `wil::details::RecordFailFast'::`2'::s_hrErrorLast = (int)this;
  return 1;
}

```

## disassembly

```asm
0x180001fd0  mov     cs:?s_hrErrorLast@?1??RecordFailFast@details@wil@@YAHJ@Z@4JC, ecx; long volatile `wil::details::RecordFailFast(long)'::`2'::s_hrErrorLast
0x180001fd6  mov     eax, 1
0x180001fdb  retn
```
