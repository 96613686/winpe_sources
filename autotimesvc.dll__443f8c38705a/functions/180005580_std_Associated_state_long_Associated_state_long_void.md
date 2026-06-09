# std::_Associated_state<long>::~_Associated_state<long>(void)

- ea: `0x180005580`
- end: `0x1800055bf`
- name: `??1?$_Associated_state@J@std@@UEAA@XZ`
- size: `63`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b40`

## callees

- `0x180005580`

## import_xrefs

- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x1800055a9`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x1800055a9`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800055b8`

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
0x180005580  push    rbx
0x180005582  sub     rsp, 20h
0x180005586  cmp     byte ptr [rcx+0C1h], 0
0x18000558d  lea     rax, ??_7?$_Associated_state@J@std@@6B@; const std::_Associated_state<long>::`vftable'
0x180005594  mov     [rcx], rax
0x180005597  mov     rbx, rcx
0x18000559a  jz      short loc_1800055AF
0x18000559c  cmp     dword ptr [rcx+0BCh], 0
0x1800055a3  jnz     short loc_1800055AF
0x1800055a5  add     rcx, 20h ; ' '; _Mtx_t
0x1800055a9  call    cs:__imp__Cnd_unregister_at_thread_exit
0x1800055af  lea     rcx, [rbx+10h]
0x1800055b3  add     rsp, 20h
0x1800055b7  pop     rbx
0x1800055b8  jmp     cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
```
