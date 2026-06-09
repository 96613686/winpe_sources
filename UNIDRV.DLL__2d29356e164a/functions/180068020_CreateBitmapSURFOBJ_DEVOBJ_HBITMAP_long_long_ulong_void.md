# CreateBitmapSURFOBJ(_DEVOBJ *,HBITMAP__ * *,long,long,ulong,void *)

- ea: `0x180068020`
- end: `0x1800680f4`
- name: `?CreateBitmapSURFOBJ@@YAPEAU_SURFOBJ@@PEAU_DEVOBJ@@PEAPEAUHBITMAP__@@JJKPEAX@Z`
- size: `212`
- prototype: `struct _SURFOBJ *__fastcall(HDEV *, HBITMAP *, unsigned int, unsigned int, ULONG iFormat, struct _SURFOBJ *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180062160`
- `0x180062830`
- `0x180067f0c`

## callees

- `0x1800618bc`
- `0x180068020`

## import_xrefs

- `GDI32!EngCreateBitmap` at `0x1800680a5`
- `GDI32!EngCreateBitmap` at `0x1800680a5`
- `GDI32!EngLockSurface` at `0x1800680ca`
- `GDI32!EngLockSurface` at `0x1800680ca`
- `GDI32!EngAssociateSurface` at `0x1800680bd`
- `GDI32!EngAssociateSurface` at `0x1800680bd`

## pseudocode

```c
struct _SURFOBJ *__fastcall CreateBitmapSURFOBJ(
        HDEV *a1,
        HBITMAP *a2,
        unsigned int a3,
        unsigned int a4,
        ULONG iFormat,
        struct _SURFOBJ *a6)
{
  HBITMAP Bitmap; // rax
  struct _SURFOBJ *result; // rax
  SIZEL sizl; // [rsp+48h] [rbp+10h]

  a6 = 0;
  sizl = (SIZEL)__PAIR64__(a4, a3);
  switch ( iFormat )
  {
    case 1u:
      break;
    case 2u:
      a3 *= 4;
      break;
    case 3u:
LABEL_9:
      a3 *= 8;
      break;
    case 4u:
      a3 *= 16;
      break;
    case 5u:
      a3 *= 3;
      goto LABEL_9;
    case 6u:
      a3 *= 32;
      break;
  }
  Bitmap = EngCreateBitmap(sizl, (((a3 + 7) >> 3) + 3) & 0xFFFFFFFC, iFormat, 3u, 0);
  *a2 = Bitmap;
  if ( !Bitmap
    || !EngAssociateSurface((HSURF)Bitmap, a1[2], 0)
    || (result = EngLockSurface((HSURF)*a2), (a6 = result) == 0) )
  {
    DELETE_SURFOBJ(&a6, a2);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180068020  mov     [rsp+arg_0], rbx
0x180068025  push    rdi
0x180068026  sub     rsp, 30h
0x18006802a  mov     eax, [rsp+38h+iFormat]
0x18006802e  mov     rbx, rdx
0x180068031  mov     [rsp+38h+arg_28], 0
0x18006803a  mov     rdi, rcx
0x18006803d  mov     [rsp+38h+sizl.cx], r8d
0x180068042  mov     [rsp+38h+sizl.cy], r9d
0x180068047  sub     eax, 1
0x18006804a  jz      short loc_18006807F
0x18006804c  sub     eax, 1
0x18006804f  jz      short loc_18006807B
0x180068051  sub     eax, 1
0x180068054  jz      short loc_18006806F
0x180068056  sub     eax, 1
0x180068059  jz      short loc_180068075
0x18006805b  sub     eax, 1
0x18006805e  jz      short loc_18006806B
0x180068060  cmp     eax, 1
0x180068063  jnz     short loc_18006807F
0x180068065  shl     r8d, 5
0x180068069  jmp     short loc_18006807F
0x18006806b  lea     r8d, [r8+r8*2]
0x18006806f  shl     r8d, 3
0x180068073  jmp     short loc_18006807F
0x180068075  shl     r8d, 4
0x180068079  jmp     short loc_18006807F
0x18006807b  shl     r8d, 2
0x18006807f  mov     rcx, qword ptr [rsp+38h+sizl.cx]; sizl
0x180068084  lea     edx, [r8+7]
0x180068088  mov     r8d, [rsp+38h+iFormat]; iFormat
0x18006808d  mov     r9d, 3; fl
0x180068093  shr     edx, 3
0x180068096  add     edx, r9d
0x180068099  mov     [rsp+38h+pvBits], 0; pvBits
0x1800680a2  and     edx, 0FFFFFFFCh; lWidth
0x1800680a5  call    cs:__imp_EngCreateBitmap
0x1800680ab  mov     [rbx], rax
0x1800680ae  test    rax, rax
0x1800680b1  jz      short loc_1800680DA
0x1800680b3  mov     rdx, [rdi+10h]; hdev
0x1800680b7  xor     r8d, r8d; flHooks
0x1800680ba  mov     rcx, rax; hsurf
0x1800680bd  call    cs:__imp_EngAssociateSurface
0x1800680c3  test    eax, eax
0x1800680c5  jz      short loc_1800680DA
0x1800680c7  mov     rcx, [rbx]; hsurf
0x1800680ca  call    cs:__imp_EngLockSurface
0x1800680d0  mov     [rsp+38h+arg_28], rax
0x1800680d5  test    rax, rax
0x1800680d8  jnz     short loc_1800680E9
0x1800680da  mov     rdx, rbx; HBITMAP *
0x1800680dd  lea     rcx, [rsp+38h+arg_28]; struct _SURFOBJ **
0x1800680e2  call    ?DELETE_SURFOBJ@@YAXPEAPEAU_SURFOBJ@@PEAPEAUHBITMAP__@@@Z; DELETE_SURFOBJ(_SURFOBJ * *,HBITMAP__ * *)
0x1800680e7  xor     eax, eax
0x1800680e9  mov     rbx, [rsp+38h+arg_0]
0x1800680ee  add     rsp, 30h
0x1800680f2  pop     rdi
0x1800680f3  retn
```
