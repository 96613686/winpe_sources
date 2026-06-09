# std::_Packaged_state<void (void)>::~_Packaged_state<void (void)>(void)

- ea: `0x18000fa18`
- end: `0x18000fa8a`
- name: `??1?$_Packaged_state@$$A6AXXZ@std@@UEAA@XZ`
- size: `114`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fae8`
- `0x1800105c0`
- `0x180017ebc`

## callees

- `0x18000fa18`
- `0x180019010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18000fa83`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x18000fa6f`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x18000fa6f`

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
0x18000fa18  mov     [rsp+arg_0], rbx
0x18000fa1d  push    rdi
0x18000fa1e  sub     rsp, 20h
0x18000fa22  lea     rdi, [rcx+0D0h]
0x18000fa29  mov     rbx, rcx
0x18000fa2c  mov     rcx, [rdi+38h]
0x18000fa30  test    rcx, rcx
0x18000fa33  jz      short loc_18000FA4F
0x18000fa35  mov     rax, [rcx]
0x18000fa38  cmp     rcx, rdi
0x18000fa3b  setnz   dl
0x18000fa3e  mov     rax, [rax+20h]
0x18000fa42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa47  mov     qword ptr [rdi+38h], 0
0x18000fa4f  cmp     byte ptr [rbx+0C1h], 0
0x18000fa56  lea     rax, ??_7?$_Associated_state@H@std@@6B@; const std::_Associated_state<int>::`vftable'
0x18000fa5d  mov     [rbx], rax
0x18000fa60  jz      short loc_18000FA75
0x18000fa62  cmp     dword ptr [rbx+0BCh], 0
0x18000fa69  jnz     short loc_18000FA75
0x18000fa6b  lea     rcx, [rbx+20h]; _Mtx_t
0x18000fa6f  call    cs:__imp__Cnd_unregister_at_thread_exit
0x18000fa75  lea     rcx, [rbx+10h]
0x18000fa79  mov     rbx, [rsp+28h+arg_0]
0x18000fa7e  add     rsp, 20h
0x18000fa82  pop     rdi
0x18000fa83  jmp     cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
```
