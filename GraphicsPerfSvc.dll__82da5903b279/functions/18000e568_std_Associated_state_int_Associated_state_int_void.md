# std::_Associated_state<int>::~_Associated_state<int>(void)

- ea: `0x18000e568`
- end: `0x18000e5a7`
- name: `??1?$_Associated_state@H@std@@UEAA@XZ`
- size: `63`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ea50`

## callees

- `0x18000e568`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18000e5a0`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x18000e591`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x18000e591`

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
0x18000e568  push    rbx
0x18000e56a  sub     rsp, 20h
0x18000e56e  cmp     byte ptr [rcx+0C1h], 0
0x18000e575  lea     rax, ??_7?$_Associated_state@H@std@@6B@; const std::_Associated_state<int>::`vftable'
0x18000e57c  mov     [rcx], rax
0x18000e57f  mov     rbx, rcx
0x18000e582  jz      short loc_18000E597
0x18000e584  cmp     dword ptr [rcx+0BCh], 0
0x18000e58b  jnz     short loc_18000E597
0x18000e58d  add     rcx, 20h ; ' '; _Mtx_t
0x18000e591  call    cs:__imp__Cnd_unregister_at_thread_exit
0x18000e597  lea     rcx, [rbx+10h]
0x18000e59b  add     rsp, 20h
0x18000e59f  pop     rbx
0x18000e5a0  jmp     cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
```
