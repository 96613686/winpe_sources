# WxDeleteElementGenericTableAvl(_WX_AVL_TABLE *,void *)

- ea: `0x18000a268`
- end: `0x18000a2e4`
- name: `?WxDeleteElementGenericTableAvl@@YAEPEAU_WX_AVL_TABLE@@PEAX@Z`
- size: `124`
- prototype: `unsigned __int8 __fastcall(struct _WX_AVL_TABLE *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180007490`
- `0x1800110b8`

## callees

- `0x180009f14`
- `0x18000a04c`
- `0x18000a11c`
- `0x18000a268`
- `0x180018010`

## pseudocode

```c
unsigned __int8 __fastcall WxDeleteElementGenericTableAvl(struct _WX_AVL_TABLE *a1, __int64 a2)
{
  struct _WX_BALANCED_LINKS *v4; // rdi
  void (__fastcall *v5)(struct _WX_AVL_TABLE *, struct _WX_BALANCED_LINKS *); // rax
  struct _WX_BALANCED_LINKS *v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 0;
  if ( (unsigned int)FindNodeOrParent((__int64)a1, a2, &v6) != 1 )
    return 0;
  v4 = v6;
  if ( v6 == *((struct _WX_BALANCED_LINKS **)a1 + 7) )
    *((_QWORD *)a1 + 7) = RealPredecessor(v6);
  ++*((_DWORD *)a1 + 16);
  DeleteNodeFromTree(a1, v4);
  v5 = (void (__fastcall *)(struct _WX_AVL_TABLE *, struct _WX_BALANCED_LINKS *))*((_QWORD *)a1 + 11);
  --*((_DWORD *)a1 + 11);
  *((_DWORD *)a1 + 10) = 0;
  *((_QWORD *)a1 + 4) = 0;
  v5(a1, v4);
  return 1;
}

```

## disassembly

```asm
0x18000a268  mov     [rsp+arg_0], rbx
0x18000a26d  push    rdi
0x18000a26e  sub     rsp, 20h
0x18000a272  lea     r8, [rsp+28h+arg_10]
0x18000a277  mov     [rsp+28h+arg_10], 0
0x18000a280  mov     rbx, rcx
0x18000a283  call    ?FindNodeOrParent@@YA?AW4_WX_TABLE_SEARCH_RESULT@@PEAU_WX_AVL_TABLE@@PEAXPEAPEAU_WX_BALANCED_LINKS@@@Z; FindNodeOrParent(_WX_AVL_TABLE *,void *,_WX_BALANCED_LINKS * *)
0x18000a288  cmp     eax, 1
0x18000a28b  jz      short loc_18000A291
0x18000a28d  xor     al, al
0x18000a28f  jmp     short loc_18000A2D9
0x18000a291  mov     rdi, [rsp+28h+arg_10]
0x18000a296  cmp     rdi, [rbx+38h]
0x18000a29a  jnz     short loc_18000A2A8
0x18000a29c  mov     rcx, rdi; struct _WX_BALANCED_LINKS *
0x18000a29f  call    ?RealPredecessor@@YAPEAU_WX_BALANCED_LINKS@@PEAU1@@Z; RealPredecessor(_WX_BALANCED_LINKS *)
0x18000a2a4  mov     [rbx+38h], rax
0x18000a2a8  inc     dword ptr [rbx+40h]
0x18000a2ab  mov     rdx, rdi; struct _WX_BALANCED_LINKS *
0x18000a2ae  mov     rcx, rbx; struct _WX_AVL_TABLE *
0x18000a2b1  call    ?DeleteNodeFromTree@@YAXPEAU_WX_AVL_TABLE@@PEAU_WX_BALANCED_LINKS@@@Z; DeleteNodeFromTree(_WX_AVL_TABLE *,_WX_BALANCED_LINKS *)
0x18000a2b6  mov     rax, [rbx+58h]
0x18000a2ba  mov     rdx, rdi
0x18000a2bd  dec     dword ptr [rbx+2Ch]
0x18000a2c0  mov     rcx, rbx
0x18000a2c3  mov     dword ptr [rbx+28h], 0
0x18000a2ca  mov     qword ptr [rbx+20h], 0
0x18000a2d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2d7  mov     al, 1
0x18000a2d9  mov     rbx, [rsp+28h+arg_0]
0x18000a2de  add     rsp, 20h
0x18000a2e2  pop     rdi
0x18000a2e3  retn
```
