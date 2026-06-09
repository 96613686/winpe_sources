# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x1400133f0`
- end: `0x140013406`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400131f8`

## callees

- `0x1400133f0`
- `0x140018008`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(
        wil::details::ThreadFailureCallbackHolder *this)
{
  if ( *((_DWORD *)this + 6) )
    wil::details::ThreadFailureCallbackHolder::StopWatching(this);
}

```

## disassembly

```asm
0x1400133f0  sub     rsp, 28h
0x1400133f4  cmp     dword ptr [rcx+18h], 0
0x1400133f8  jz      short loc_140013400
0x1400133fa  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1400133ff  nop
0x140013400  add     rsp, 28h
0x140013404  retn
```
