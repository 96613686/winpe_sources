# wil::details::RecordException(long)

- ea: `0x180006cd4`
- end: `0x180006cea`
- name: `?RecordException@details@wil@@YAHJ@Z`
- size: `22`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000249c`
- `0x180005ee8`

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
0x180006cd4  mov     cs:?s_hrErrorLast@?1??RecordException@details@wil@@YAHJ@Z@4JC, ecx; long volatile `wil::details::RecordException(long)'::`2'::s_hrErrorLast
0x180006cda  mov     eax, 1
0x180006cdf  lock xadd cs:?s_cErrorCount@?1??RecordException@details@wil@@YAHJ@Z@4JC, eax; long volatile `wil::details::RecordException(long)'::`2'::s_cErrorCount
0x180006ce7  inc     eax
0x180006ce9  retn
```
