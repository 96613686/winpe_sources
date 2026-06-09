# wil::details::RecordFailFast(long)

- ea: `0x180002c10`
- end: `0x180002c1c`
- name: `?RecordFailFast@details@wil@@YAHJ@Z`
- size: `12`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d60`

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
0x180002c10  mov     cs:?s_hrErrorLast@?1??RecordFailFast@details@wil@@YAHJ@Z@4JC, ecx; long volatile `wil::details::RecordFailFast(long)'::`2'::s_hrErrorLast
0x180002c16  mov     eax, 1
0x180002c1b  retn
```
