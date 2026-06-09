# std::_Associated_state<int>::~_Associated_state<int>(void)

- ea: `0x180046ab8`
- end: `0x180046af7`
- name: `??1?$_Associated_state@H@std@@UEAA@XZ`
- size: `63`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180046b78`
- `0x180047270`

## callees

- `0x180046ab8`

## import_xrefs

- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x180046ae1`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x180046ae1`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180046af0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180046ab8  push    rbx
0x180046aba  sub     rsp, 20h
0x180046abe  cmp     byte ptr [rcx+0C1h], 0
0x180046ac5  lea     rax, ??_7?$_Associated_state@H@std@@6B@; const std::_Associated_state<int>::`vftable'
0x180046acc  mov     [rcx], rax
0x180046acf  mov     rbx, rcx
0x180046ad2  jz      short loc_180046AE7
0x180046ad4  cmp     dword ptr [rcx+0BCh], 0
0x180046adb  jnz     short loc_180046AE7
0x180046add  add     rcx, 20h ; ' '; _Mtx_t
0x180046ae1  call    cs:__imp__Cnd_unregister_at_thread_exit
0x180046ae7  lea     rcx, [rbx+10h]
0x180046aeb  add     rsp, 20h
0x180046aef  pop     rbx
0x180046af0  jmp     cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
```
