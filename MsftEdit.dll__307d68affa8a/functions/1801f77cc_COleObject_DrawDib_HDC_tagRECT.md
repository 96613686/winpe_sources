# COleObject::DrawDib(HDC__ *,tagRECT *)

- ea: `0x1801f77cc`
- end: `0x1801f788d`
- name: `?DrawDib@COleObject@@AEAAXPEAUHDC__@@PEAUtagRECT@@@Z`
- size: `193`
- prototype: `void(COleObject *__hidden this, HDC, struct tagRECT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1801f7894`

## callees

- `0x1801f7650`
- `0x1801f77cc`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801f7873`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801f7873`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1801f780c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1801f780c`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801f787c`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801f787c`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1801f77fa`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1801f77fa`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801f781c`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801f781c`
- `ext-ms-win-gdi-draw-l1-1-0!StretchBlt` at `0x1801f786a`
- `ext-ms-win-gdi-draw-l1-1-0!StretchBlt` at `0x1801f786a`

## pseudocode

```c
void __fastcall COleObject::DrawDib(HGLOBAL *this, HDC a2, struct tagRECT *a3)
{
  HDC hdcSrc; // rbp
  int *v7; // rbx

  if ( !this[15] )
    COleObject::CreateDib((COleObject *)this, a2);
  if ( this[15] )
  {
    hdcSrc = CreateCompatibleDC(a2);
    if ( hdcSrc )
    {
      v7 = (int *)GlobalLock(this[14]);
      SelectObject(hdcSrc, this[15]);
      StretchBlt(
        a2,
        a3->left,
        a3->top,
        a3->right - a3->left,
        a3->bottom - a3->top,
        hdcSrc,
        0,
        0,
        v7[1],
        v7[2],
        0xCC0020u);
      GlobalUnlock(v7);
      DeleteDC(hdcSrc);
    }
  }
}

```

## disassembly

```asm
0x1801f77cc  push    rbx
0x1801f77ce  push    rbp
0x1801f77cf  push    rsi
0x1801f77d0  push    rdi
0x1801f77d1  push    r14
0x1801f77d3  sub     rsp, 60h
0x1801f77d7  cmp     qword ptr [rcx+78h], 0
0x1801f77dc  mov     r14, r8
0x1801f77df  mov     rsi, rdx
0x1801f77e2  mov     rdi, rcx
0x1801f77e5  jnz     short loc_1801F77EC
0x1801f77e7  call    ?CreateDib@COleObject@@AEAAXPEAUHDC__@@@Z; COleObject::CreateDib(HDC__ *)
0x1801f77ec  cmp     qword ptr [rdi+78h], 0
0x1801f77f1  jz      loc_1801F7882
0x1801f77f7  mov     rcx, rsi; hdc
0x1801f77fa  call    cs:__imp_CreateCompatibleDC
0x1801f7800  mov     rbp, rax
0x1801f7803  test    rax, rax
0x1801f7806  jz      short loc_1801F7882
0x1801f7808  mov     rcx, [rdi+70h]; hMem
0x1801f780c  call    cs:__imp_GlobalLock
0x1801f7812  mov     rdx, [rdi+78h]; h
0x1801f7816  mov     rcx, rbp; hdc
0x1801f7819  mov     rbx, rax
0x1801f781c  call    cs:__imp_SelectObject
0x1801f7822  mov     ecx, [rbx+8]
0x1801f7825  mov     r10d, [r14+0Ch]
0x1801f7829  mov     r8d, [r14+4]; yDest
0x1801f782d  sub     r10d, r8d
0x1801f7830  mov     r9d, [r14+8]
0x1801f7834  sub     r9d, [r14]; wDest
0x1801f7837  mov     edx, [r14]; xDest
0x1801f783a  mov     [rsp+88h+rop], 0CC0020h; rop
0x1801f7842  mov     [rsp+88h+hSrc], ecx; hSrc
0x1801f7846  mov     ecx, [rbx+4]
0x1801f7849  mov     [rsp+88h+wSrc], ecx; wSrc
0x1801f784d  mov     rcx, rsi; hdcDest
0x1801f7850  mov     [rsp+88h+ySrc], 0; ySrc
0x1801f7858  mov     [rsp+88h+xSrc], 0; xSrc
0x1801f7860  mov     [rsp+88h+hdcSrc], rbp; hdcSrc
0x1801f7865  mov     [rsp+88h+hDest], r10d; hDest
0x1801f786a  call    cs:__imp_StretchBlt
0x1801f7870  mov     rcx, rbx; hMem
0x1801f7873  call    cs:__imp_GlobalUnlock
0x1801f7879  mov     rcx, rbp; hdc
0x1801f787c  call    cs:__imp_DeleteDC
0x1801f7882  add     rsp, 60h
0x1801f7886  pop     r14
0x1801f7888  pop     rdi
0x1801f7889  pop     rsi
0x1801f788a  pop     rbp
0x1801f788b  pop     rbx
0x1801f788c  retn
```
