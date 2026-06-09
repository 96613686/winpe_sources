# wil::details::RecordException(long)

- ea: `0x18000449c`
- end: `0x1800044b2`
- name: `?RecordException@details@wil@@YAHJ@Z`
- size: `22`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180003f64`
- `0x180005824`

## pseudocode

```c
__int64 __fastcall wil::details::RecordException(wil::details *this)
{
  `wil::details::RecordException'::`2'::s_hrErrorLast = (int)this;
  return (unsigned int)_InterlockedIncrement(&`wil::details::RecordException'::`2'::s_cErrorCount);
}

```

## disassembly

```asm
0x18000449c  mov     cs:?s_hrErrorLast@?1??RecordException@details@wil@@YAHJ@Z@4JC, ecx; long volatile `wil::details::RecordException(long)'::`2'::s_hrErrorLast
0x1800044a2  mov     eax, 1
0x1800044a7  lock xadd cs:?s_cErrorCount@?1??RecordException@details@wil@@YAHJ@Z@4JC, eax; long volatile `wil::details::RecordException(long)'::`2'::s_cErrorCount
0x1800044af  inc     eax
0x1800044b1  retn
```
