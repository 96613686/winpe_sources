# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x1400085bc`
- end: `0x1400085d1`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `21`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000824c`

## callees

- `0x1400085bc`
- `0x14000b738`

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
0x1400085bc  sub     rsp, 28h
0x1400085c0  cmp     dword ptr [rcx+18h], 0
0x1400085c4  jz      short loc_1400085CC
0x1400085c6  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1400085cb  nop
0x1400085cc  add     rsp, 28h
0x1400085d0  retn
```
