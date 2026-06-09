# wil::details::RecordException(long)

- ea: `0x140004564`
- end: `0x14000457a`
- name: `?RecordException@details@wil@@YAHJ@Z`
- size: `22`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140003fd8`
- `0x140005a64`

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
0x140004564  mov     cs:?s_hrErrorLast@?1??RecordException@details@wil@@YAHJ@Z@4JC, ecx; long volatile `wil::details::RecordException(long)'::`2'::s_hrErrorLast
0x14000456a  mov     eax, 1
0x14000456f  lock xadd cs:?s_cErrorCount@?1??RecordException@details@wil@@YAHJ@Z@4JC, eax; long volatile `wil::details::RecordException(long)'::`2'::s_cErrorCount
0x140004577  inc     eax
0x140004579  retn
```
