# std::_Associated_state<int>::~_Associated_state<int>(void)

- ea: `0x180018a70`
- end: `0x180018aaf`
- name: `??1?$_Associated_state@H@std@@UEAA@XZ`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800194a0`

## callees

- `0x180018a70`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180018aa8`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x180018a99`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x180018a99`

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
0x180018a70  push    rbx
0x180018a72  sub     rsp, 20h
0x180018a76  cmp     byte ptr [rcx+0C1h], 0
0x180018a7d  lea     rax, ??_7?$_Associated_state@H@std@@6B@; const std::_Associated_state<int>::`vftable'
0x180018a84  mov     [rcx], rax
0x180018a87  mov     rbx, rcx
0x180018a8a  jz      short loc_180018A9F
0x180018a8c  cmp     dword ptr [rcx+0BCh], 0
0x180018a93  jnz     short loc_180018A9F
0x180018a95  add     rcx, 20h ; ' '; _Mtx_t
0x180018a99  call    cs:__imp__Cnd_unregister_at_thread_exit
0x180018a9f  lea     rcx, [rbx+10h]
0x180018aa3  add     rsp, 20h
0x180018aa7  pop     rbx
0x180018aa8  jmp     cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
```
