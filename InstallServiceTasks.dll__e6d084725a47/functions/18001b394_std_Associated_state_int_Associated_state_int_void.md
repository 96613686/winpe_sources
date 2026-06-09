# std::_Associated_state<int>::~_Associated_state<int>(void)

- ea: `0x18001b394`
- end: `0x18001b3d3`
- name: `??1?$_Associated_state@H@std@@UEAA@XZ`
- size: `63`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b454`
- `0x18001be00`

## callees

- `0x18001b394`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001b3cc`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x18001b3bd`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x18001b3bd`

## pseudocode

```c
void __fastcall std::_Associated_state<int>::~_Associated_state<int>(__int64 a1)
{
  bool v1; // zf

  v1 = *(_BYTE *)(a1 + 193) == 0;
  *(_QWORD *)a1 = &std::_Associated_state<int>::`vftable';
  if ( !v1 && !*(_DWORD *)(a1 + 188) )
    _Cnd_unregister_at_thread_exit((_Mtx_t)(a1 + 32));
  __ExceptionPtrDestroy((void *)(a1 + 16));
}

```

## disassembly

```asm
0x18001b394  push    rbx
0x18001b396  sub     rsp, 20h
0x18001b39a  cmp     byte ptr [rcx+0C1h], 0
0x18001b3a1  lea     rax, ??_7?$_Associated_state@H@std@@6B@; const std::_Associated_state<int>::`vftable'
0x18001b3a8  mov     [rcx], rax
0x18001b3ab  mov     rbx, rcx
0x18001b3ae  jz      short loc_18001B3C3
0x18001b3b0  cmp     dword ptr [rcx+0BCh], 0
0x18001b3b7  jnz     short loc_18001B3C3
0x18001b3b9  add     rcx, 20h ; ' '; _Mtx_t
0x18001b3bd  call    cs:__imp__Cnd_unregister_at_thread_exit
0x18001b3c3  lea     rcx, [rbx+10h]
0x18001b3c7  add     rsp, 20h
0x18001b3cb  pop     rbx
0x18001b3cc  jmp     cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
```
