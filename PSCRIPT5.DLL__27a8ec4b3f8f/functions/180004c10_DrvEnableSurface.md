# DrvEnableSurface

- ea: `0x180004c10`
- end: `0x180004cc5`
- name: `DrvEnableSurface`
- size: `181`
- prototype: `HSURF __stdcall(DHPDEV dhpdev)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004c10`
- `0x180012e18`

## import_xrefs

- `KERNEL32!MulDiv` at `0x180004c2b`
- `KERNEL32!MulDiv` at `0x180004c4d`
- `KERNEL32!MulDiv` at `0x180004c2b`
- `KERNEL32!MulDiv` at `0x180004c4d`
- `GDI32!EngAssociateSurface` at `0x180004ca1`
- `GDI32!EngAssociateSurface` at `0x180004ca1`
- `GDI32!EngCreateDeviceSurface` at `0x180004c6b`
- `GDI32!EngCreateDeviceSurface` at `0x180004c6b`

## pseudocode

```c
HSURF __stdcall DrvEnableSurface(DHPDEV dhpdev)
{
  HSURF DeviceSurface; // rax
  FLONG v3; // r8d
  SIZEL sizl; // [rsp+30h] [rbp+8h]

  sizl.cx = MulDiv(*((_DWORD *)dhpdev + 580), *((_DWORD *)dhpdev + 178), 25400);
  sizl.cy = MulDiv(*((_DWORD *)dhpdev + 581), *((_DWORD *)dhpdev + 178), 25400);
  DeviceSurface = EngCreateDeviceSurface((DHSURF)dhpdev, sizl, 5u);
  *((_QWORD *)dhpdev + 14) = DeviceSurface;
  if ( DeviceSurface )
  {
    v3 = 238831;
    if ( *(int *)(*((_QWORD *)dhpdev + 12) + 140LL) < 3 )
      v3 = 74991;
    EngAssociateSurface(DeviceSurface, *((HDEV *)dhpdev + 2), v3);
    SMChangeState((__int64)dhpdev, 2);
  }
  return (HSURF)*((_QWORD *)dhpdev + 14);
}

```

## disassembly

```asm
0x180004c10  push    rbx
0x180004c12  sub     rsp, 20h
0x180004c16  mov     edx, [rcx+2C8h]; nNumerator
0x180004c1c  mov     rbx, rcx
0x180004c1f  mov     ecx, [rcx+910h]; nNumber
0x180004c25  mov     r8d, 6338h; nDenominator
0x180004c2b  call    cs:__imp_MulDiv
0x180004c32  nop     dword ptr [rax+rax+00h]
0x180004c37  mov     edx, [rbx+2C8h]; nNumerator
0x180004c3d  mov     r8d, 6338h; nDenominator
0x180004c43  mov     ecx, [rbx+914h]; nNumber
0x180004c49  mov     [rsp+28h+sizl.cx], eax
0x180004c4d  call    cs:__imp_MulDiv
0x180004c54  nop     dword ptr [rax+rax+00h]
0x180004c59  mov     [rsp+28h+sizl.cy], eax
0x180004c5d  mov     r8d, 5; iFormatCompat
0x180004c63  mov     rdx, qword ptr [rsp+28h+sizl.cx]; sizl
0x180004c68  mov     rcx, rbx; dhsurf
0x180004c6b  call    cs:__imp_EngCreateDeviceSurface
0x180004c72  nop     dword ptr [rax+rax+00h]
0x180004c77  mov     [rbx+70h], rax
0x180004c7b  test    rax, rax
0x180004c7e  jz      short loc_180004CBA
0x180004c80  mov     rcx, [rbx+60h]
0x180004c84  mov     edx, 124EFh
0x180004c89  mov     r8d, 3A4EFh
0x180004c8f  cmp     dword ptr [rcx+8Ch], 3
0x180004c96  mov     rcx, rax; hsurf
0x180004c99  cmovl   r8d, edx; flHooks
0x180004c9d  mov     rdx, [rbx+10h]; hdev
0x180004ca1  call    cs:__imp_EngAssociateSurface
0x180004ca8  nop     dword ptr [rax+rax+00h]
0x180004cad  mov     edx, 2
0x180004cb2  mov     rcx, rbx
0x180004cb5  call    SMChangeState
0x180004cba  mov     rax, [rbx+70h]
0x180004cbe  add     rsp, 20h
0x180004cc2  pop     rbx
0x180004cc3  retn
```
