# std::_Associated_state<int>::`vector deleting destructor'(uint)

- ea: `0x180010450`
- end: `0x1800104b0`
- name: `??_E?$_Associated_state@H@std@@UEAAPEAXI@Z`
- size: `96`
- prototype: `char *__fastcall(char *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180002054`
- `0x180010450`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180010489`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180010489`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x18001047f`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x18001047f`

## pseudocode

```c
char *__fastcall std::_Associated_state<int>::`vector deleting destructor'(char *a1, char a2)
{
  bool v2; // zf

  v2 = a1[193] == 0;
  *(_QWORD *)a1 = &std::_Associated_state<int>::`vftable';
  if ( !v2 && !*((_DWORD *)a1 + 47) )
    _Cnd_unregister_at_thread_exit((_Mtx_t)(a1 + 32));
  __ExceptionPtrDestroy(a1 + 16);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180010450  mov     [rsp+arg_0], rbx
0x180010455  push    rdi
0x180010456  sub     rsp, 20h
0x18001045a  cmp     byte ptr [rcx+0C1h], 0
0x180010461  lea     rax, ??_7?$_Associated_state@H@std@@6B@; const std::_Associated_state<int>::`vftable'
0x180010468  mov     [rcx], rax
0x18001046b  mov     edi, edx
0x18001046d  mov     rbx, rcx
0x180010470  jz      short loc_180010485
0x180010472  cmp     dword ptr [rcx+0BCh], 0
0x180010479  jnz     short loc_180010485
0x18001047b  add     rcx, 20h ; ' '; _Mtx_t
0x18001047f  call    cs:__imp__Cnd_unregister_at_thread_exit
0x180010485  lea     rcx, [rbx+10h]
0x180010489  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18001048f  test    dil, 1
0x180010493  jz      short loc_1800104A2
0x180010495  mov     edx, 0D0h; unsigned __int64
0x18001049a  mov     rcx, rbx; void *
0x18001049d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800104a2  mov     rax, rbx
0x1800104a5  mov     rbx, [rsp+28h+arg_0]
0x1800104aa  add     rsp, 20h
0x1800104ae  pop     rdi
0x1800104af  retn
```
