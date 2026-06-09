# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x14000a3ac`
- end: `0x14000a3c1`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `21`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009da8`

## callees

- `0x14000a3ac`
- `0x14000eab8`

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
0x14000a3ac  sub     rsp, 28h
0x14000a3b0  cmp     dword ptr [rcx+18h], 0
0x14000a3b4  jz      short loc_14000A3BC
0x14000a3b6  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14000a3bb  nop
0x14000a3bc  add     rsp, 28h
0x14000a3c0  retn
```
