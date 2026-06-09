# std::_Associated_state<long>::~_Associated_state<long>(void)

- ea: `0x180036df4`
- end: `0x180036e33`
- name: `??1?$_Associated_state@J@std@@UEAA@XZ`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180037e30`

## callees

- `0x180036df4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180036e2c`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x180036e1d`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x180036e1d`

## pseudocode

```c
void __fastcall std::_Associated_state<long>::~_Associated_state<long>(__int64 a1)
{
  bool v1; // zf

  v1 = *(_BYTE *)(a1 + 193) == 0;
  *(_QWORD *)a1 = &std::_Associated_state<long>::`vftable';
  if ( !v1 && !*(_DWORD *)(a1 + 188) )
    _Cnd_unregister_at_thread_exit((_Mtx_t)(a1 + 32));
  __ExceptionPtrDestroy((void *)(a1 + 16));
}

```

## disassembly

```asm
0x180036df4  push    rbx
0x180036df6  sub     rsp, 20h
0x180036dfa  cmp     byte ptr [rcx+0C1h], 0
0x180036e01  lea     rax, ??_7?$_Associated_state@J@std@@6B@; const std::_Associated_state<long>::`vftable'
0x180036e08  mov     [rcx], rax
0x180036e0b  mov     rbx, rcx
0x180036e0e  jz      short loc_180036E23
0x180036e10  cmp     dword ptr [rcx+0BCh], 0
0x180036e17  jnz     short loc_180036E23
0x180036e19  add     rcx, 20h ; ' '; _Mtx_t
0x180036e1d  call    cs:__imp__Cnd_unregister_at_thread_exit
0x180036e23  lea     rcx, [rbx+10h]
0x180036e27  add     rsp, 20h
0x180036e2b  pop     rbx
0x180036e2c  jmp     cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
```
