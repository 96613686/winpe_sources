# Holder<HDC__ *,close_funct<int (*)(HDC__ *),&DeleteDC(HDC__ *)>,invalid_const<HDC__ *,0>>::reset(void)

- ea: `0x180027c80`
- end: `0x180027ca4`
- name: `?reset@?$Holder@PEAUHDC__@@U?$close_funct@P6AHPEAUHDC__@@@Z$1?DeleteDC@@YAH0@Z@@U?$invalid_const@PEAUHDC__@@$0A@@@@@QEAAXXZ`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180024c44`
- `0x180024e40`

## callees

- `0x180027c80`

## import_xrefs

- `GDI32!DeleteDC` at `0x180027c91`
- `GDI32!DeleteDC` at `0x180027c91`

## pseudocode

```c
BOOL __fastcall Holder<HDC__ *,close_funct<int (*)(HDC__ *),&int DeleteDC(HDC__ *)>,invalid_const<HDC__ *,0>>::reset(
        HDC *a1)
{
  HDC v2; // rcx
  BOOL result; // eax

  v2 = *a1;
  if ( v2 )
  {
    result = DeleteDC(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180027c80  push    rbx
0x180027c82  sub     rsp, 20h
0x180027c86  mov     rbx, rcx
0x180027c89  mov     rcx, [rcx]; hdc
0x180027c8c  test    rcx, rcx
0x180027c8f  jz      short loc_180027C9E
0x180027c91  call    cs:__imp_DeleteDC
0x180027c97  mov     qword ptr [rbx], 0
0x180027c9e  add     rsp, 20h
0x180027ca2  pop     rbx
0x180027ca3  retn
```
