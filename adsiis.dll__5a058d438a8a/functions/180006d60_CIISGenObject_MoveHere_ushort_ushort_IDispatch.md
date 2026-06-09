# CIISGenObject::MoveHere(ushort *,ushort *,IDispatch * *)

- ea: `0x180006d60`
- end: `0x180006d7d`
- name: `?MoveHere@CIISGenObject@@UEAAJPEAG0PEAPEAUIDispatch@@@Z`
- size: `29`
- prototype: `int(CIISGenObject *__hidden this, unsigned __int16 *, unsigned __int16 *, struct IDispatch **)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800049c0`

## pseudocode

```c
__int64 __fastcall CIISGenObject::MoveHere(
        CIISGenObject *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IDispatch **a4)
{
  return CIISGenObject::CopyMoveHere((CIISGenObject *)((char *)this - 72), a2, a3, 1, a4);
}

```

## disassembly

```asm
0x180006d60  sub     rsp, 38h
0x180006d64  mov     [rsp+38h+var_18], r9; struct IDispatch **
0x180006d69  add     rcx, 0FFFFFFFFFFFFFFB8h; this
0x180006d6d  mov     r9d, 1; int
0x180006d73  call    ?CopyMoveHere@CIISGenObject@@IEAAJPEAG0HPEAPEAUIDispatch@@@Z; CIISGenObject::CopyMoveHere(ushort *,ushort *,int,IDispatch * *)
0x180006d78  add     rsp, 38h
0x180006d7c  retn
```
