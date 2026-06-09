# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x140012ab8`
- end: `0x140012acd`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `21`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400128dc`

## callees

- `0x140012ab8`
- `0x140017344`

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
0x140012ab8  sub     rsp, 28h
0x140012abc  cmp     dword ptr [rcx+18h], 0
0x140012ac0  jz      short loc_140012AC8
0x140012ac2  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x140012ac7  nop
0x140012ac8  add     rsp, 28h
0x140012acc  retn
```
