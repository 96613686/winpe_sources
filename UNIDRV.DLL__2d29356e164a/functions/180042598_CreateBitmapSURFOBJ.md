# CreateBitmapSURFOBJ

- ea: `0x180042598`
- end: `0x180042661`
- name: `CreateBitmapSURFOBJ`
- size: `201`
- prototype: `SURFOBJ *__fastcall(__int64, HSURF *, unsigned int, unsigned int, ULONG iFormat)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fde0`
- `0x180016870`
- `0x180040a70`
- `0x18005fb90`
- `0x180060060`
- `0x18006d230`
- `0x18006dfb0`

## callees

- `0x180042598`

## import_xrefs

- `GDI32!EngDeleteSurface` at `0x180042647`
- `GDI32!EngDeleteSurface` at `0x180042647`
- `GDI32!EngCreateBitmap` at `0x18004260f`
- `GDI32!EngCreateBitmap` at `0x18004260f`
- `GDI32!EngLockSurface` at `0x180042634`
- `GDI32!EngLockSurface` at `0x180042634`
- `GDI32!EngAssociateSurface` at `0x180042627`
- `GDI32!EngAssociateSurface` at `0x180042627`

## pseudocode

```c
SURFOBJ *__fastcall CreateBitmapSURFOBJ(__int64 a1, HSURF *a2, unsigned int a3, unsigned int a4, ULONG iFormat)
{
  HBITMAP Bitmap; // rax
  SURFOBJ *result; // rax
  SIZEL sizl; // [rsp+48h] [rbp+10h]

  sizl = (SIZEL)__PAIR64__(a4, a3);
  switch ( iFormat )
  {
    case 2u:
      a3 *= 4;
      break;
    case 3u:
      goto LABEL_8;
    case 4u:
      a3 *= 16;
      break;
    case 5u:
      a3 *= 3;
LABEL_8:
      a3 *= 8;
      break;
    case 6u:
      a3 *= 32;
      break;
  }
  Bitmap = EngCreateBitmap(sizl, (((a3 + 7) >> 3) + 3) & 0xFFFFFFFC, iFormat, 3u, 0);
  *a2 = (HSURF)Bitmap;
  if ( !Bitmap || !EngAssociateSurface((HSURF)Bitmap, *(HDEV *)(a1 + 16), 0) || (result = EngLockSurface(*a2)) == 0 )
  {
    if ( *a2 )
    {
      EngDeleteSurface(*a2);
      *a2 = 0;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180042598  mov     [rsp+arg_0], rbx
0x18004259d  push    rdi
0x18004259e  sub     rsp, 30h
0x1800425a2  mov     eax, [rsp+38h+iFormat]
0x1800425a6  mov     rbx, rdx
0x1800425a9  mov     [rsp+38h+sizl.cx], r8d
0x1800425ae  mov     rdi, rcx
0x1800425b1  mov     [rsp+38h+sizl.cy], r9d
0x1800425b6  sub     eax, 2
0x1800425b9  jz      short loc_1800425E5
0x1800425bb  sub     eax, 1
0x1800425be  jz      short loc_1800425D9
0x1800425c0  sub     eax, 1
0x1800425c3  jz      short loc_1800425DF
0x1800425c5  sub     eax, 1
0x1800425c8  jz      short loc_1800425D5
0x1800425ca  cmp     eax, 1
0x1800425cd  jnz     short loc_1800425E9
0x1800425cf  shl     r8d, 5
0x1800425d3  jmp     short loc_1800425E9
0x1800425d5  lea     r8d, [r8+r8*2]
0x1800425d9  shl     r8d, 3
0x1800425dd  jmp     short loc_1800425E9
0x1800425df  shl     r8d, 4
0x1800425e3  jmp     short loc_1800425E9
0x1800425e5  shl     r8d, 2
0x1800425e9  mov     rcx, qword ptr [rsp+38h+sizl.cx]; sizl
0x1800425ee  lea     edx, [r8+7]
0x1800425f2  mov     r8d, [rsp+38h+iFormat]; iFormat
0x1800425f7  mov     r9d, 3; fl
0x1800425fd  shr     edx, 3
0x180042600  add     edx, r9d
0x180042603  mov     [rsp+38h+pvBits], 0; pvBits
0x18004260c  and     edx, 0FFFFFFFCh; lWidth
0x18004260f  call    cs:__imp_EngCreateBitmap
0x180042615  mov     [rbx], rax
0x180042618  test    rax, rax
0x18004261b  jz      short loc_18004263F
0x18004261d  mov     rdx, [rdi+10h]; hdev
0x180042621  xor     r8d, r8d; flHooks
0x180042624  mov     rcx, rax; hsurf
0x180042627  call    cs:__imp_EngAssociateSurface
0x18004262d  test    eax, eax
0x18004262f  jz      short loc_18004263F
0x180042631  mov     rcx, [rbx]; hsurf
0x180042634  call    cs:__imp_EngLockSurface
0x18004263a  test    rax, rax
0x18004263d  jnz     short loc_180042656
0x18004263f  mov     rcx, [rbx]; hsurf
0x180042642  test    rcx, rcx
0x180042645  jz      short loc_180042654
0x180042647  call    cs:__imp_EngDeleteSurface
0x18004264d  mov     qword ptr [rbx], 0
0x180042654  xor     eax, eax
0x180042656  mov     rbx, [rsp+38h+arg_0]
0x18004265b  add     rsp, 30h
0x18004265f  pop     rdi
0x180042660  retn
```
