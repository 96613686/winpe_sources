# std::_Associated_state<int>::`vector deleting destructor'(uint)

- ea: `0x1800170e0`
- end: `0x180017140`
- name: `??_E?$_Associated_state@H@std@@UEAAPEAXI@Z`
- size: `96`
- prototype: `char *__fastcall(char *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1800025f8`
- `0x1800170e0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180017119`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180017119`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x18001710f`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x18001710f`

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
0x1800170e0  mov     [rsp+arg_0], rbx
0x1800170e5  push    rdi
0x1800170e6  sub     rsp, 20h
0x1800170ea  cmp     byte ptr [rcx+0C1h], 0
0x1800170f1  lea     rax, ??_7?$_Associated_state@H@std@@6B@; const std::_Associated_state<int>::`vftable'
0x1800170f8  mov     [rcx], rax
0x1800170fb  mov     edi, edx
0x1800170fd  mov     rbx, rcx
0x180017100  jz      short loc_180017115
0x180017102  cmp     dword ptr [rcx+0BCh], 0
0x180017109  jnz     short loc_180017115
0x18001710b  add     rcx, 20h ; ' '; _Mtx_t
0x18001710f  call    cs:__imp__Cnd_unregister_at_thread_exit
0x180017115  lea     rcx, [rbx+10h]
0x180017119  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18001711f  test    dil, 1
0x180017123  jz      short loc_180017132
0x180017125  mov     edx, 0D0h; unsigned __int64
0x18001712a  mov     rcx, rbx; void *
0x18001712d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017132  mov     rax, rbx
0x180017135  mov     rbx, [rsp+28h+arg_0]
0x18001713a  add     rsp, 20h
0x18001713e  pop     rdi
0x18001713f  retn
```
