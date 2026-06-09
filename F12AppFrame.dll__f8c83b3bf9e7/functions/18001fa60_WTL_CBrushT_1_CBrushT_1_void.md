# WTL::CBrushT<1>::~CBrushT<1>(void)

- ea: `0x18001fa60`
- end: `0x18001fa88`
- name: `??1?$CBrushT@$00@WTL@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800337e4`
- `0x1800337fd`
- `0x180033816`

## callees

- `0x18001fa60`

## import_xrefs

- `GDI32!DeleteObject` at `0x18001fa71`
- `GDI32!DeleteObject` at `0x18001fa71`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WTL::CBrushT<1>::~CBrushT<1>(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    if ( DeleteObject(v2) )
      *a1 = 0;
  }
}

```

## disassembly

```asm
0x18001fa60  push    rbx
0x18001fa62  sub     rsp, 20h
0x18001fa66  mov     rbx, rcx
0x18001fa69  mov     rcx, [rcx]; ho
0x18001fa6c  test    rcx, rcx
0x18001fa6f  jz      short loc_18001FA82
0x18001fa71  call    cs:__imp_DeleteObject
0x18001fa77  test    eax, eax
0x18001fa79  jz      short loc_18001FA82
0x18001fa7b  mov     qword ptr [rbx], 0
0x18001fa82  add     rsp, 20h
0x18001fa86  pop     rbx
0x18001fa87  retn
```
