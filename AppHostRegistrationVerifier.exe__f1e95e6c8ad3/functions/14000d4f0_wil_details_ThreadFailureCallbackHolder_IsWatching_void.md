# wil::details::ThreadFailureCallbackHolder::IsWatching(void)

- ea: `0x14000d4f0`
- end: `0x14000d4f8`
- name: `?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ`
- size: `8`
- prototype: `bool __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000b0f0`
- `0x14000d438`

## pseudocode

```c
bool __fastcall wil::details::ThreadFailureCallbackHolder::IsWatching(wil::details::ThreadFailureCallbackHolder *this)
{
  return *((_DWORD *)this + 6) != 0;
}

```

## disassembly

```asm
0x14000d4f0  cmp     dword ptr [rcx+18h], 0
0x14000d4f4  setnz   al
0x14000d4f7  retn
```
