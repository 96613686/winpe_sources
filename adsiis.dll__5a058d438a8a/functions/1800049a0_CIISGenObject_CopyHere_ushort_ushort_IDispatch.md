# CIISGenObject::CopyHere(ushort *,ushort *,IDispatch * *)

- ea: `0x1800049a0`
- end: `0x1800049ba`
- name: `?CopyHere@CIISGenObject@@UEAAJPEAG0PEAPEAUIDispatch@@@Z`
- size: `26`
- prototype: `int(CIISGenObject *__hidden this, unsigned __int16 *, unsigned __int16 *, struct IDispatch **)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800049c0`

## pseudocode

```c
__int64 __fastcall CIISGenObject::CopyHere(
        CIISGenObject *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IDispatch **a4)
{
  return CIISGenObject::CopyMoveHere((CIISGenObject *)((char *)this - 72), a2, a3, 0, a4);
}

```

## disassembly

```asm
0x1800049a0  sub     rsp, 38h
0x1800049a4  mov     [rsp+38h+var_18], r9; struct IDispatch **
0x1800049a9  add     rcx, 0FFFFFFFFFFFFFFB8h; this
0x1800049ad  xor     r9d, r9d; int
0x1800049b0  call    ?CopyMoveHere@CIISGenObject@@IEAAJPEAG0HPEAPEAUIDispatch@@@Z; CIISGenObject::CopyMoveHere(ushort *,ushort *,int,IDispatch * *)
0x1800049b5  add     rsp, 38h
0x1800049b9  retn
```
