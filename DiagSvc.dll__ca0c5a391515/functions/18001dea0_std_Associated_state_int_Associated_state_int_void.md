# std::_Associated_state<int>::~_Associated_state<int>(void)

- ea: `0x18001dea0`
- end: `0x18001dedf`
- name: `??1?$_Associated_state@H@std@@UEAA@XZ`
- size: `63`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001dff0`
- `0x18001e790`

## callees

- `0x18001dea0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001ded8`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x18001dec9`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x18001dec9`

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
0x18001dea0  push    rbx
0x18001dea2  sub     rsp, 20h
0x18001dea6  cmp     byte ptr [rcx+0C1h], 0
0x18001dead  lea     rax, ??_7?$_Associated_state@H@std@@6B@; const std::_Associated_state<int>::`vftable'
0x18001deb4  mov     [rcx], rax
0x18001deb7  mov     rbx, rcx
0x18001deba  jz      short loc_18001DECF
0x18001debc  cmp     dword ptr [rcx+0BCh], 0
0x18001dec3  jnz     short loc_18001DECF
0x18001dec5  add     rcx, 20h ; ' '; _Mtx_t
0x18001dec9  call    cs:__imp__Cnd_unregister_at_thread_exit
0x18001decf  lea     rcx, [rbx+10h]
0x18001ded3  add     rsp, 20h
0x18001ded7  pop     rbx
0x18001ded8  jmp     cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
```
