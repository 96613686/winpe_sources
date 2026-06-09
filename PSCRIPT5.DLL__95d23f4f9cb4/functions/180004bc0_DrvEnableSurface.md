# DrvEnableSurface

- ea: `0x180004bc0`
- end: `0x180004c5c`
- name: `DrvEnableSurface`
- size: `156`
- prototype: `HSURF __stdcall(DHPDEV dhpdev)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004bc0`
- `0x18001283c`

## import_xrefs

- `KERNEL32!MulDiv` at `0x180004bdb`
- `KERNEL32!MulDiv` at `0x180004bf7`
- `KERNEL32!MulDiv` at `0x180004bdb`
- `KERNEL32!MulDiv` at `0x180004bf7`
- `GDI32!EngAssociateSurface` at `0x180004c3f`
- `GDI32!EngAssociateSurface` at `0x180004c3f`
- `GDI32!EngCreateDeviceSurface` at `0x180004c0f`
- `GDI32!EngCreateDeviceSurface` at `0x180004c0f`

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
    SMChangeState(dhpdev, 2);
  }
  return (HSURF)*((_QWORD *)dhpdev + 14);
}

```

## disassembly

```asm
0x180004bc0  push    rbx
0x180004bc2  sub     rsp, 20h
0x180004bc6  mov     edx, [rcx+2C8h]; nNumerator
0x180004bcc  mov     rbx, rcx
0x180004bcf  mov     ecx, [rcx+910h]; nNumber
0x180004bd5  mov     r8d, 6338h; nDenominator
0x180004bdb  call    cs:__imp_MulDiv
0x180004be1  mov     edx, [rbx+2C8h]; nNumerator
0x180004be7  mov     r8d, 6338h; nDenominator
0x180004bed  mov     ecx, [rbx+914h]; nNumber
0x180004bf3  mov     [rsp+28h+sizl.cx], eax
0x180004bf7  call    cs:__imp_MulDiv
0x180004bfd  mov     [rsp+28h+sizl.cy], eax
0x180004c01  mov     r8d, 5; iFormatCompat
0x180004c07  mov     rdx, qword ptr [rsp+28h+sizl.cx]; sizl
0x180004c0c  mov     rcx, rbx; dhsurf
0x180004c0f  call    cs:__imp_EngCreateDeviceSurface
0x180004c15  mov     [rbx+70h], rax
0x180004c19  test    rax, rax
0x180004c1c  jz      short loc_180004C52
0x180004c1e  mov     rcx, [rbx+60h]
0x180004c22  mov     edx, 124EFh
0x180004c27  mov     r8d, 3A4EFh
0x180004c2d  cmp     dword ptr [rcx+8Ch], 3
0x180004c34  mov     rcx, rax; hsurf
0x180004c37  cmovl   r8d, edx; flHooks
0x180004c3b  mov     rdx, [rbx+10h]; hdev
0x180004c3f  call    cs:__imp_EngAssociateSurface
0x180004c45  mov     edx, 2
0x180004c4a  mov     rcx, rbx
0x180004c4d  call    SMChangeState
0x180004c52  mov     rax, [rbx+70h]
0x180004c56  add     rsp, 20h
0x180004c5a  pop     rbx
0x180004c5b  retn
```
