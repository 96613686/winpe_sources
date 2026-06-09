# ATL::CRBTree<_FILE_EXTENT_IDENTIFIER,_FILE_EXTENT_DATA *,ATL::CElementTraits<_FILE_EXTENT_IDENTIFIER>,ATL::CElementTraits<_FILE_EXTENT_DATA *>>::RemoveAll(void)

- ea: `0x140014ed0`
- end: `0x140014f2f`
- name: `?RemoveAll@?$CRBTree@U_FILE_EXTENT_IDENTIFIER@@PEAU_FILE_EXTENT_DATA@@V?$CElementTraits@U_FILE_EXTENT_IDENTIFIER@@@ATL@@V?$CElementTraits@PEAU_FILE_EXTENT_DATA@@@4@@ATL@@QEAAXXZ`
- size: `95`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000be9c`
- `0x14000c354`

## callees

- `0x140014ed0`
- `0x140014f38`

## import_xrefs

- `msvcrt!free` at `0x140014eff`
- `msvcrt!free` at `0x140014eff`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<_FILE_EXTENT_IDENTIFIER,_FILE_EXTENT_DATA *,ATL::CElementTraits<_FILE_EXTENT_IDENTIFIER>,ATL::CElementTraits<_FILE_EXTENT_DATA *>>::RemoveAll(
        _QWORD *a1)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rbx
  __int64 result; // rax

  if ( *a1 != a1[5] )
    ATL::CRBTree<_FILE_EXTENT_IDENTIFIER,_FILE_EXTENT_DATA *,ATL::CElementTraits<_FILE_EXTENT_IDENTIFIER>,ATL::CElementTraits<_FILE_EXTENT_DATA *>>::RemovePostOrder();
  v2 = (_QWORD *)a1[3];
  a1[1] = 0;
  if ( v2 )
  {
    do
    {
      v3 = (_QWORD *)*v2;
      free(v2);
      v2 = v3;
    }
    while ( v3 );
  }
  result = a1[5];
  *a1 = result;
  a1[3] = 0;
  a1[2] = 0;
  return result;
}

```

## disassembly

```asm
0x140014ed0  mov     [rsp+arg_0], rbx
0x140014ed5  push    rdi
0x140014ed6  sub     rsp, 20h
0x140014eda  mov     rdx, [rcx]
0x140014edd  mov     rdi, rcx
0x140014ee0  cmp     rdx, [rcx+28h]
0x140014ee4  jz      short loc_140014EEB
0x140014ee6  call    ?RemovePostOrder@?$CRBTree@U_FILE_EXTENT_IDENTIFIER@@PEAU_FILE_EXTENT_DATA@@V?$CElementTraits@U_FILE_EXTENT_IDENTIFIER@@@ATL@@V?$CElementTraits@PEAU_FILE_EXTENT_DATA@@@4@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CRBTree<_FILE_EXTENT_IDENTIFIER,_FILE_EXTENT_DATA *,ATL::CElementTraits<_FILE_EXTENT_IDENTIFIER>,ATL::CElementTraits<_FILE_EXTENT_DATA *>>::RemovePostOrder(ATL::CRBTree<_FILE_EXTENT_IDENTIFIER,_FILE_EXTENT_DATA *,ATL::CElementTraits<_FILE_EXTENT_IDENTIFIER>,ATL::CElementTraits<_FILE_EXTENT_DATA *>>::CNode *)
0x140014eeb  mov     rcx, [rdi+18h]; Block
0x140014eef  mov     qword ptr [rdi+8], 0
0x140014ef7  test    rcx, rcx
0x140014efa  jz      short loc_140014F0D
0x140014efc  mov     rbx, [rcx]
0x140014eff  call    cs:__imp_free
0x140014f05  mov     rcx, rbx
0x140014f08  test    rbx, rbx
0x140014f0b  jnz     short loc_140014EFC
0x140014f0d  mov     rax, [rdi+28h]
0x140014f11  mov     rbx, [rsp+28h+arg_0]
0x140014f16  mov     [rdi], rax
0x140014f19  mov     qword ptr [rdi+18h], 0
0x140014f21  mov     qword ptr [rdi+10h], 0
0x140014f29  add     rsp, 20h
0x140014f2d  pop     rdi
0x140014f2e  retn
```
