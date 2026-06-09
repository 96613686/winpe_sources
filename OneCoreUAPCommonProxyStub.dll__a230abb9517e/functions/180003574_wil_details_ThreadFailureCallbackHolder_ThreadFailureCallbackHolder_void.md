# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x180003574`
- end: `0x180003589`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `21`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003518`

## callees

- `0x180003000`
- `0x180003574`

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
0x180003574  sub     rsp, 28h
0x180003578  cmp     dword ptr [rcx+18h], 0
0x18000357c  jz      short loc_180003584
0x18000357e  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180003583  nop
0x180003584  add     rsp, 28h
0x180003588  retn
```
