# DrvDisableSurface

- ea: `0x180004170`
- end: `0x1800041a8`
- name: `DrvDisableSurface`
- size: `56`
- prototype: `void __stdcall(DHPDEV dhpdev)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004170`
- `0x180012e18`

## import_xrefs

- `GDI32!EngDeleteSurface` at `0x180004182`
- `GDI32!EngDeleteSurface` at `0x180004182`

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
  SMChangeState((__int64)dhpdev, 1);
}

```

## disassembly

```asm
0x180004170  push    rbx
0x180004172  sub     rsp, 20h
0x180004176  mov     rbx, rcx
0x180004179  mov     rcx, [rcx+70h]; hsurf
0x18000417d  test    rcx, rcx
0x180004180  jz      short loc_180004196
0x180004182  call    cs:__imp_EngDeleteSurface
0x180004189  nop     dword ptr [rax+rax+00h]
0x18000418e  mov     qword ptr [rbx+70h], 0
0x180004196  mov     edx, 1
0x18000419b  mov     rcx, rbx
0x18000419e  add     rsp, 20h
0x1800041a2  pop     rbx
0x1800041a3  jmp     SMChangeState
```
