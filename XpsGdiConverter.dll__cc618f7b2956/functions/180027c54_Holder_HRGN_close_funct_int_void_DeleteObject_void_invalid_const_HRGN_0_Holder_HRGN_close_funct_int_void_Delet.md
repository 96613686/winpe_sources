# Holder<HRGN__ *,close_funct<int (*)(void *),&DeleteObject(void *)>,invalid_const<HRGN__ *,0>>::~Holder<HRGN__ *,close_funct<int (*)(void *),&DeleteObject(void *)>,invalid_const<HRGN__ *,0>>(void)

- ea: `0x180027c54`
- end: `0x180027c78`
- name: `??1?$Holder@PEAUHRGN__@@U?$close_funct@P6AHPEAX@Z$1?DeleteObject@@YAH0@Z@@U?$invalid_const@PEAUHRGN__@@$0A@@@@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180024c38`
- `0x180024e40`
- `0x180027054`
- `0x180048a6c`

## callees

- `0x180027c54`

## import_xrefs

- `GDI32!DeleteObject` at `0x180027c65`
- `GDI32!DeleteObject` at `0x180027c65`

## pseudocode

```c
BOOL __fastcall Holder<HRGN__ *,close_funct<int (*)(void *),&int DeleteObject(void *)>,invalid_const<HRGN__ *,0>>::~Holder<HRGN__ *,close_funct<int (*)(void *),&int DeleteObject(void *)>,invalid_const<HRGN__ *,0>>(
        void **a1)
{
  void *v2; // rcx
  BOOL result; // eax

  v2 = *a1;
  if ( v2 )
  {
    result = DeleteObject(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180027c54  push    rbx
0x180027c56  sub     rsp, 20h
0x180027c5a  mov     rbx, rcx
0x180027c5d  mov     rcx, [rcx]; ho
0x180027c60  test    rcx, rcx
0x180027c63  jz      short loc_180027C72
0x180027c65  call    cs:__imp_DeleteObject
0x180027c6b  mov     qword ptr [rbx], 0
0x180027c72  add     rsp, 20h
0x180027c76  pop     rbx
0x180027c77  retn
```
