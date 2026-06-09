# CreateBitmapSURFOBJ(_DEVOBJ *,HBITMAP__ * *,long,long,ulong,void *)

- ea: `0x180069874`
- end: `0x18006995b`
- name: `?CreateBitmapSURFOBJ@@YAPEAU_SURFOBJ@@PEAU_DEVOBJ@@PEAPEAUHBITMAP__@@JJKPEAX@Z`
- size: `231`
- prototype: `struct _SURFOBJ *__fastcall(HDEV *, HSURF *, unsigned int, unsigned int, ULONG iFormat, struct _SURFOBJ *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180063700`
- `0x180063e10`
- `0x180069760`

## callees

- `0x180062e04`
- `0x180069874`

## import_xrefs

- `GDI32!EngCreateBitmap` at `0x1800698f9`
- `GDI32!EngCreateBitmap` at `0x1800698f9`
- `GDI32!EngLockSurface` at `0x18006992a`
- `GDI32!EngLockSurface` at `0x18006992a`
- `GDI32!EngAssociateSurface` at `0x180069917`
- `GDI32!EngAssociateSurface` at `0x180069917`

## pseudocode

```c
struct _SURFOBJ *__fastcall CreateBitmapSURFOBJ(
        HDEV *a1,
        HSURF *a2,
        unsigned int a3,
        unsigned int a4,
        ULONG iFormat,
        struct _SURFOBJ *a6)
{
  HSURF Bitmap; // rax
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
  Bitmap = (HSURF)EngCreateBitmap(sizl, (((a3 + 7) >> 3) + 3) & 0xFFFFFFFC, iFormat, 3u, 0);
  *a2 = Bitmap;
  if ( !Bitmap || !EngAssociateSurface(Bitmap, a1[2], 0) || (result = EngLockSurface(*a2), (a6 = result) == 0) )
  {
    DELETE_SURFOBJ(&a6, a2);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180069874  mov     [rsp+arg_0], rbx
0x180069879  push    rdi
0x18006987a  sub     rsp, 30h
0x18006987e  mov     eax, [rsp+38h+iFormat]
0x180069882  mov     rbx, rdx
0x180069885  mov     [rsp+38h+arg_28], 0
0x18006988e  mov     rdi, rcx
0x180069891  mov     [rsp+38h+sizl.cx], r8d
0x180069896  mov     [rsp+38h+sizl.cy], r9d
0x18006989b  sub     eax, 1
0x18006989e  jz      short loc_1800698D3
0x1800698a0  sub     eax, 1
0x1800698a3  jz      short loc_1800698CF
0x1800698a5  sub     eax, 1
0x1800698a8  jz      short loc_1800698C3
0x1800698aa  sub     eax, 1
0x1800698ad  jz      short loc_1800698C9
0x1800698af  sub     eax, 1
0x1800698b2  jz      short loc_1800698BF
0x1800698b4  cmp     eax, 1
0x1800698b7  jnz     short loc_1800698D3
0x1800698b9  shl     r8d, 5
0x1800698bd  jmp     short loc_1800698D3
0x1800698bf  lea     r8d, [r8+r8*2]
0x1800698c3  shl     r8d, 3
0x1800698c7  jmp     short loc_1800698D3
0x1800698c9  shl     r8d, 4
0x1800698cd  jmp     short loc_1800698D3
0x1800698cf  shl     r8d, 2
0x1800698d3  mov     rcx, qword ptr [rsp+38h+sizl.cx]; sizl
0x1800698d8  lea     edx, [r8+7]
0x1800698dc  mov     r8d, [rsp+38h+iFormat]; iFormat
0x1800698e1  mov     r9d, 3; fl
0x1800698e7  shr     edx, 3
0x1800698ea  add     edx, r9d
0x1800698ed  mov     [rsp+38h+pvBits], 0; pvBits
0x1800698f6  and     edx, 0FFFFFFFCh; lWidth
0x1800698f9  call    cs:__imp_EngCreateBitmap
0x180069900  nop     dword ptr [rax+rax+00h]
0x180069905  mov     [rbx], rax
0x180069908  test    rax, rax
0x18006990b  jz      short loc_180069940
0x18006990d  mov     rdx, [rdi+10h]; hdev
0x180069911  xor     r8d, r8d; flHooks
0x180069914  mov     rcx, rax; hsurf
0x180069917  call    cs:__imp_EngAssociateSurface
0x18006991e  nop     dword ptr [rax+rax+00h]
0x180069923  test    eax, eax
0x180069925  jz      short loc_180069940
0x180069927  mov     rcx, [rbx]; hsurf
0x18006992a  call    cs:__imp_EngLockSurface
0x180069931  nop     dword ptr [rax+rax+00h]
0x180069936  mov     [rsp+38h+arg_28], rax
0x18006993b  test    rax, rax
0x18006993e  jnz     short loc_18006994F
0x180069940  mov     rdx, rbx; HBITMAP *
0x180069943  lea     rcx, [rsp+38h+arg_28]; struct _SURFOBJ **
0x180069948  call    ?DELETE_SURFOBJ@@YAXPEAPEAU_SURFOBJ@@PEAPEAUHBITMAP__@@@Z; DELETE_SURFOBJ(_SURFOBJ * *,HBITMAP__ * *)
0x18006994d  xor     eax, eax
0x18006994f  mov     rbx, [rsp+38h+arg_0]
0x180069954  add     rsp, 30h
0x180069958  pop     rdi
0x180069959  retn
```
