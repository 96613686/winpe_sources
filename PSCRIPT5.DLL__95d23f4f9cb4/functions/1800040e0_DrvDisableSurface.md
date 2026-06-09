# DrvDisableSurface

- ea: `0x1800040e0`
- end: `0x180004112`
- name: `DrvDisableSurface`
- size: `50`
- prototype: `void __stdcall(DHPDEV dhpdev)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800040e0`
- `0x18001283c`

## import_xrefs

- `GDI32!EngDeleteSurface` at `0x1800040f2`
- `GDI32!EngDeleteSurface` at `0x1800040f2`

## pseudocode

```c
void __stdcall DrvDisableSurface(DHPDEV dhpdev)
{
  HSURF v2; // rcx

  v2 = (HSURF)*((_QWORD *)dhpdev + 14);
  if ( v2 )
  {
    EngDeleteSurface(v2);
    *((_QWORD *)dhpdev + 14) = 0;
  }
  SMChangeState(dhpdev, 1);
}

```

## disassembly

```asm
0x1800040e0  push    rbx
0x1800040e2  sub     rsp, 20h
0x1800040e6  mov     rbx, rcx
0x1800040e9  mov     rcx, [rcx+70h]; hsurf
0x1800040ed  test    rcx, rcx
0x1800040f0  jz      short loc_180004100
0x1800040f2  call    cs:__imp_EngDeleteSurface
0x1800040f8  mov     qword ptr [rbx+70h], 0
0x180004100  mov     edx, 1
0x180004105  mov     rcx, rbx
0x180004108  add     rsp, 20h
0x18000410c  pop     rbx
0x18000410d  jmp     SMChangeState
```
