# Concurrency::details::_TaskProcThunk::_Bridge(void *)

- ea: `0x180011370`
- end: `0x1800113d0`
- name: `?_Bridge@_TaskProcThunk@details@Concurrency@@SAXPEAX@Z`
- size: `96`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x180012924`

## callees

- `0x180002054`
- `0x180011370`
- `0x180019010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180011387`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180011387`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Concurrency::details::_TaskProcThunk::_Bridge(_QWORD *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rdx
  _QWORD *v4; // rcx

  v2 = a1[7];
  if ( !v2 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v4 = (_QWORD *)a1[7];
  if ( v4 )
  {
    LOBYTE(v3) = v4 != a1;
    (*(void (__fastcall **)(_QWORD *, __int64))(*v4 + 32LL))(v4, v3);
    a1[7] = 0;
  }
  operator delete(a1);
}

```

## disassembly

```asm
0x180011370  push    rbx
0x180011372  sub     rsp, 20h
0x180011376  mov     rbx, rcx
0x180011379  mov     [rsp+28h+arg_0], rcx
0x18001137e  mov     rcx, [rcx+38h]
0x180011382  test    rcx, rcx
0x180011385  jnz     short loc_18001138E
0x180011387  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001138d  int     3; Trap to Debugger
0x18001138e  mov     rax, [rcx]
0x180011391  mov     rax, [rax+10h]
0x180011395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001139a  nop
0x18001139b  mov     rcx, [rbx+38h]
0x18001139f  test    rcx, rcx
0x1800113a2  jz      short loc_1800113BE
0x1800113a4  mov     rax, [rcx]
0x1800113a7  cmp     rcx, rbx
0x1800113aa  setnz   dl
0x1800113ad  mov     rax, [rax+20h]
0x1800113b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113b6  mov     qword ptr [rbx+38h], 0
0x1800113be  mov     edx, 40h ; '@'; unsigned __int64
0x1800113c3  mov     rcx, rbx; void *
0x1800113c6  add     rsp, 20h
0x1800113ca  pop     rbx
0x1800113cb  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
