# std::_Associated_state<int>::~_Associated_state<int>(void)

- ea: `0x1800123a8`
- end: `0x1800123e7`
- name: `??1?$_Associated_state@H@std@@UEAA@XZ`
- size: `63`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180012598`
- `0x1800135f0`

## callees

- `0x1800123a8`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800123e0`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x1800123d1`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x1800123d1`

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
0x1800123a8  push    rbx
0x1800123aa  sub     rsp, 20h
0x1800123ae  cmp     byte ptr [rcx+0C1h], 0
0x1800123b5  lea     rax, ??_7?$_Associated_state@H@std@@6B@; const std::_Associated_state<int>::`vftable'
0x1800123bc  mov     [rcx], rax
0x1800123bf  mov     rbx, rcx
0x1800123c2  jz      short loc_1800123D7
0x1800123c4  cmp     dword ptr [rcx+0BCh], 0
0x1800123cb  jnz     short loc_1800123D7
0x1800123cd  add     rcx, 20h ; ' '; _Mtx_t
0x1800123d1  call    cs:__imp__Cnd_unregister_at_thread_exit
0x1800123d7  lea     rcx, [rbx+10h]
0x1800123db  add     rsp, 20h
0x1800123df  pop     rbx
0x1800123e0  jmp     cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
```
