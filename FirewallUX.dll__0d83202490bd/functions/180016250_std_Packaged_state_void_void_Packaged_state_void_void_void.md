# std::_Packaged_state<void (void)>::~_Packaged_state<void (void)>(void)

- ea: `0x180016250`
- end: `0x1800162c2`
- name: `??1?$_Packaged_state@$$A6AXXZ@std@@UEAA@XZ`
- size: `114`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180016320`
- `0x180017250`
- `0x18002ad59`

## callees

- `0x180016250`
- `0x18002d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800162bb`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x1800162a7`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x1800162a7`

## pseudocode

```c
void __fastcall std::_Packaged_state<void (void)>::~_Packaged_state<void (void)>(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v4; // rcx
  bool v5; // zf

  v2 = a1 + 208;
  v4 = *(_QWORD *)(a1 + 264);
  if ( v4 )
  {
    LOBYTE(a2) = v4 != v2;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 32LL))(v4, a2);
    *(_QWORD *)(v2 + 56) = 0;
  }
  v5 = *(_BYTE *)(a1 + 193) == 0;
  *(_QWORD *)a1 = &std::_Associated_state<int>::`vftable';
  if ( !v5 && !*(_DWORD *)(a1 + 188) )
    _Cnd_unregister_at_thread_exit((_Mtx_t)(a1 + 32));
  __ExceptionPtrDestroy((void *)(a1 + 16));
}

```

## disassembly

```asm
0x180016250  mov     [rsp+arg_0], rbx
0x180016255  push    rdi
0x180016256  sub     rsp, 20h
0x18001625a  lea     rdi, [rcx+0D0h]
0x180016261  mov     rbx, rcx
0x180016264  mov     rcx, [rdi+38h]
0x180016268  test    rcx, rcx
0x18001626b  jz      short loc_180016287
0x18001626d  mov     rax, [rcx]
0x180016270  cmp     rcx, rdi
0x180016273  setnz   dl
0x180016276  mov     rax, [rax+20h]
0x18001627a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001627f  mov     qword ptr [rdi+38h], 0
0x180016287  cmp     byte ptr [rbx+0C1h], 0
0x18001628e  lea     rax, ??_7?$_Associated_state@H@std@@6B@; const std::_Associated_state<int>::`vftable'
0x180016295  mov     [rbx], rax
0x180016298  jz      short loc_1800162AD
0x18001629a  cmp     dword ptr [rbx+0BCh], 0
0x1800162a1  jnz     short loc_1800162AD
0x1800162a3  lea     rcx, [rbx+20h]; _Mtx_t
0x1800162a7  call    cs:__imp__Cnd_unregister_at_thread_exit
0x1800162ad  lea     rcx, [rbx+10h]
0x1800162b1  mov     rbx, [rsp+28h+arg_0]
0x1800162b6  add     rsp, 20h
0x1800162ba  pop     rdi
0x1800162bb  jmp     cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
```
