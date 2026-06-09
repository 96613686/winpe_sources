# CreateBitmapSURFOBJ

- ea: `0x18004375c`
- end: `0x18004383e`
- name: `CreateBitmapSURFOBJ`
- size: `226`
- prototype: `SURFOBJ *__fastcall(__int64, HSURF *, unsigned int, unsigned int, ULONG iFormat)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fe80`
- `0x180016b20`
- `0x180041bf0`
- `0x180060fe0`
- `0x1800614f0`
- `0x18006f090`
- `0x18006fed0`

## callees

- `0x18004375c`

## import_xrefs

- `GDI32!EngDeleteSurface` at `0x18004381d`
- `GDI32!EngDeleteSurface` at `0x18004381d`
- `GDI32!EngCreateBitmap` at `0x1800437d3`
- `GDI32!EngCreateBitmap` at `0x1800437d3`
- `GDI32!EngLockSurface` at `0x180043804`
- `GDI32!EngLockSurface` at `0x180043804`
- `GDI32!EngAssociateSurface` at `0x1800437f1`
- `GDI32!EngAssociateSurface` at `0x1800437f1`

## pseudocode

```c
SURFOBJ *__fastcall CreateBitmapSURFOBJ(__int64 a1, HSURF *a2, unsigned int a3, unsigned int a4, ULONG iFormat)
{
  HSURF Bitmap; // rax
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
  Bitmap = (HSURF)EngCreateBitmap(sizl, (((a3 + 7) >> 3) + 3) & 0xFFFFFFFC, iFormat, 3u, 0);
  *a2 = Bitmap;
  if ( !Bitmap || !EngAssociateSurface(Bitmap, *(HDEV *)(a1 + 16), 0) || (result = EngLockSurface(*a2)) == 0 )
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
0x18004375c  mov     [rsp+arg_0], rbx
0x180043761  push    rdi
0x180043762  sub     rsp, 30h
0x180043766  mov     eax, [rsp+38h+iFormat]
0x18004376a  mov     rbx, rdx
0x18004376d  mov     [rsp+38h+sizl.cx], r8d
0x180043772  mov     rdi, rcx
0x180043775  mov     [rsp+38h+sizl.cy], r9d
0x18004377a  sub     eax, 2
0x18004377d  jz      short loc_1800437A9
0x18004377f  sub     eax, 1
0x180043782  jz      short loc_18004379D
0x180043784  sub     eax, 1
0x180043787  jz      short loc_1800437A3
0x180043789  sub     eax, 1
0x18004378c  jz      short loc_180043799
0x18004378e  cmp     eax, 1
0x180043791  jnz     short loc_1800437AD
0x180043793  shl     r8d, 5
0x180043797  jmp     short loc_1800437AD
0x180043799  lea     r8d, [r8+r8*2]
0x18004379d  shl     r8d, 3
0x1800437a1  jmp     short loc_1800437AD
0x1800437a3  shl     r8d, 4
0x1800437a7  jmp     short loc_1800437AD
0x1800437a9  shl     r8d, 2
0x1800437ad  mov     rcx, qword ptr [rsp+38h+sizl.cx]; sizl
0x1800437b2  lea     edx, [r8+7]
0x1800437b6  mov     r8d, [rsp+38h+iFormat]; iFormat
0x1800437bb  mov     r9d, 3; fl
0x1800437c1  shr     edx, 3
0x1800437c4  add     edx, r9d
0x1800437c7  mov     [rsp+38h+pvBits], 0; pvBits
0x1800437d0  and     edx, 0FFFFFFFCh; lWidth
0x1800437d3  call    cs:__imp_EngCreateBitmap
0x1800437da  nop     dword ptr [rax+rax+00h]
0x1800437df  mov     [rbx], rax
0x1800437e2  test    rax, rax
0x1800437e5  jz      short loc_180043815
0x1800437e7  mov     rdx, [rdi+10h]; hdev
0x1800437eb  xor     r8d, r8d; flHooks
0x1800437ee  mov     rcx, rax; hsurf
0x1800437f1  call    cs:__imp_EngAssociateSurface
0x1800437f8  nop     dword ptr [rax+rax+00h]
0x1800437fd  test    eax, eax
0x1800437ff  jz      short loc_180043815
0x180043801  mov     rcx, [rbx]; hsurf
0x180043804  call    cs:__imp_EngLockSurface
0x18004380b  nop     dword ptr [rax+rax+00h]
0x180043810  test    rax, rax
0x180043813  jnz     short loc_180043832
0x180043815  mov     rcx, [rbx]; hsurf
0x180043818  test    rcx, rcx
0x18004381b  jz      short loc_180043830
0x18004381d  call    cs:__imp_EngDeleteSurface
0x180043824  nop     dword ptr [rax+rax+00h]
0x180043829  mov     qword ptr [rbx], 0
0x180043830  xor     eax, eax
0x180043832  mov     rbx, [rsp+38h+arg_0]
0x180043837  add     rsp, 30h
0x18004383b  pop     rdi
0x18004383c  retn
```
