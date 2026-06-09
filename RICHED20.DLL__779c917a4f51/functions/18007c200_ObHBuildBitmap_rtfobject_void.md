# ObHBuildBitmap(_rtfobject *,void * &)

- ea: `0x18007c200`
- end: `0x18007c26e`
- name: `?ObHBuildBitmap@@YAPEAXPEAU_rtfobject@@AEAPEAX@Z`
- size: `110`
- prototype: `HBITMAP __fastcall(struct _rtfobject *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18004a8fc`
- `0x18007c200`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x18007c21a`
- `KERNEL32!GlobalLock` at `0x18007c21a`
- `KERNEL32!GlobalUnlock` at `0x18007c246`
- `KERNEL32!GlobalUnlock` at `0x18007c246`
- `GDI32!CreateBitmap` at `0x18007c23a`
- `GDI32!CreateBitmap` at `0x18007c23a`

## pseudocode

```c
HBITMAP __fastcall ObHBuildBitmap(struct _rtfobject *a1, void **a2)
{
  HBITMAP Bitmap; // rsi
  const void *lpBits; // rax
  HBITMAP result; // rax

  Bitmap = 0;
  lpBits = GlobalLock(*a2);
  if ( lpBits )
    Bitmap = CreateBitmap(*((_DWORD *)a1 + 4), *((_DWORD *)a1 + 5), *((__int16 *)a1 + 3), *((__int16 *)a1 + 2), lpBits);
  GlobalUnlock(*a2);
  CW32System::GlobalFree(*a2);
  result = Bitmap;
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x18007c200  mov     [rsp+arg_0], rbx
0x18007c205  mov     [rsp+arg_8], rsi
0x18007c20a  push    rdi
0x18007c20b  sub     rsp, 30h
0x18007c20f  mov     rdi, rcx
0x18007c212  mov     rbx, rdx
0x18007c215  mov     rcx, [rdx]; hMem
0x18007c218  xor     esi, esi
0x18007c21a  call    cs:__imp_GlobalLock
0x18007c220  test    rax, rax
0x18007c223  jz      short loc_18007C243
0x18007c225  movsx   r9d, word ptr [rdi+4]; nBitCount
0x18007c22a  movsx   r8d, word ptr [rdi+6]; nPlanes
0x18007c22f  mov     edx, [rdi+14h]; nHeight
0x18007c232  mov     ecx, [rdi+10h]; nWidth
0x18007c235  mov     [rsp+38h+lpBits], rax; lpBits
0x18007c23a  call    cs:__imp_CreateBitmap
0x18007c240  mov     rsi, rax
0x18007c243  mov     rcx, [rbx]; hMem
0x18007c246  call    cs:__imp_GlobalUnlock
0x18007c24c  mov     rcx, [rbx]; void *
0x18007c24f  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18007c254  mov     rax, rsi
0x18007c257  mov     qword ptr [rbx], 0
0x18007c25e  mov     rsi, [rsp+38h+arg_8]
0x18007c263  mov     rbx, [rsp+38h+arg_0]
0x18007c268  add     rsp, 30h
0x18007c26c  pop     rdi
0x18007c26d  retn
```
