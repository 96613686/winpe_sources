# std::_Associated_state<int>::`vector deleting destructor'(uint)

- ea: `0x18002d420`
- end: `0x18002d480`
- name: `??_E?$_Associated_state@H@std@@UEAAPEAXI@Z`
- size: `96`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180007dc0`
- `0x18002d420`

## import_xrefs

- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x18002d44f`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x18002d44f`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002d459`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002d459`

## pseudocode

```c
char *__fastcall std::_Associated_state<int>::`vector deleting destructor'(char *Block, char a2)
{
  bool v2; // zf

  v2 = Block[193] == 0;
  *(_QWORD *)Block = &std::_Associated_state<int>::`vftable';
  if ( !v2 && !*((_DWORD *)Block + 47) )
    _Cnd_unregister_at_thread_exit((_Mtx_t)(Block + 32));
  __ExceptionPtrDestroy(Block + 16);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18002d420  mov     [rsp+arg_0], rbx
0x18002d425  push    rdi
0x18002d426  sub     rsp, 20h
0x18002d42a  cmp     byte ptr [rcx+0C1h], 0
0x18002d431  lea     rax, ??_7?$_Associated_state@H@std@@6B@; const std::_Associated_state<int>::`vftable'
0x18002d438  mov     [rcx], rax
0x18002d43b  mov     edi, edx
0x18002d43d  mov     rbx, rcx
0x18002d440  jz      short loc_18002D455
0x18002d442  cmp     dword ptr [rcx+0BCh], 0
0x18002d449  jnz     short loc_18002D455
0x18002d44b  add     rcx, 20h ; ' '; _Mtx_t
0x18002d44f  call    cs:__imp__Cnd_unregister_at_thread_exit
0x18002d455  lea     rcx, [rbx+10h]
0x18002d459  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18002d45f  test    dil, 1
0x18002d463  jz      short loc_18002D472
0x18002d465  mov     edx, 0D0h
0x18002d46a  mov     rcx, rbx; Block
0x18002d46d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002d472  mov     rax, rbx
0x18002d475  mov     rbx, [rsp+28h+arg_0]
0x18002d47a  add     rsp, 20h
0x18002d47e  pop     rdi
0x18002d47f  retn
```
