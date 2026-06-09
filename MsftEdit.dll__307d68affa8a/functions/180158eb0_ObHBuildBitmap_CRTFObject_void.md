# ObHBuildBitmap(CRTFObject *,void * &)

- ea: `0x180158eb0`
- end: `0x180158f1e`
- name: `?ObHBuildBitmap@@YAPEAXPEAVCRTFObject@@AEAPEAX@Z`
- size: `110`
- prototype: `void *__fastcall(struct CRTFObject *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800693d4`
- `0x180158eb0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180158ef6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180158ef6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180158eca`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180158eca`
- `ext-ms-win-gdi-draw-l1-1-0!CreateBitmap` at `0x180158eea`
- `ext-ms-win-gdi-draw-l1-1-0!CreateBitmap` at `0x180158eea`

## pseudocode

```c
HBITMAP __fastcall ObHBuildBitmap(struct CRTFObject *a1, void **a2)
{
  HBITMAP Bitmap; // rsi
  const void *lpBits; // rax
  HBITMAP result; // rax

  Bitmap = 0;
  lpBits = GlobalLock(*a2);
  if ( lpBits )
    Bitmap = CreateBitmap(*((_DWORD *)a1 + 5), *((_DWORD *)a1 + 6), *((__int16 *)a1 + 3), *((__int16 *)a1 + 2), lpBits);
  GlobalUnlock(*a2);
  CW32System::GlobalFree(*a2);
  result = Bitmap;
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x180158eb0  mov     [rsp+arg_0], rbx
0x180158eb5  mov     [rsp+arg_8], rsi
0x180158eba  push    rdi
0x180158ebb  sub     rsp, 30h
0x180158ebf  mov     rdi, rcx
0x180158ec2  mov     rbx, rdx
0x180158ec5  mov     rcx, [rdx]; hMem
0x180158ec8  xor     esi, esi
0x180158eca  call    cs:__imp_GlobalLock
0x180158ed0  test    rax, rax
0x180158ed3  jz      short loc_180158EF3
0x180158ed5  movsx   r9d, word ptr [rdi+4]; nBitCount
0x180158eda  movsx   r8d, word ptr [rdi+6]; nPlanes
0x180158edf  mov     edx, [rdi+18h]; nHeight
0x180158ee2  mov     ecx, [rdi+14h]; nWidth
0x180158ee5  mov     [rsp+38h+lpBits], rax; lpBits
0x180158eea  call    cs:__imp_CreateBitmap
0x180158ef0  mov     rsi, rax
0x180158ef3  mov     rcx, [rbx]; hMem
0x180158ef6  call    cs:__imp_GlobalUnlock
0x180158efc  mov     rcx, [rbx]; void *
0x180158eff  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x180158f04  mov     rax, rsi
0x180158f07  mov     qword ptr [rbx], 0
0x180158f0e  mov     rsi, [rsp+38h+arg_8]
0x180158f13  mov     rbx, [rsp+38h+arg_0]
0x180158f18  add     rsp, 30h
0x180158f1c  pop     rdi
0x180158f1d  retn
```
