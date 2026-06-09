# wil::details::ThreadFailureCallbackHolder::IsWatching(void)

- ea: `0x140009908`
- end: `0x140009910`
- name: `?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ`
- size: `8`
- prototype: `bool __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140008ba0`
- `0x140009730`

## pseudocode

```c
bool __fastcall wil::details::ThreadFailureCallbackHolder::IsWatching(wil::details::ThreadFailureCallbackHolder *this)
{
  return *((_DWORD *)this + 6) != 0;
}

```

## disassembly

```asm
0x140009908  cmp     dword ptr [rcx+18h], 0
0x14000990c  setnz   al
0x14000990f  retn
```
