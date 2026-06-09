# CGdiGraphicContext::DrawRect(tagRECT const &,ulong *)

- ea: `0x1802071b0`
- end: `0x180207260`
- name: `?DrawRect@CGdiGraphicContext@@EEBA_NAEBUtagRECT@@PEAK@Z`
- size: `176`
- prototype: `bool __fastcall(CGdiGraphicContext *__hidden this, const struct tagRECT *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1802071b0`
- `0x18027a010`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1802071e3`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180207204`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180207237`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180207244`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1802071e3`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180207204`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180207237`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180207244`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18020724d`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18020724d`

## pseudocode

```c
bool __fastcall CGdiGraphicContext::DrawRect(HDC *this, const struct tagRECT *a2, unsigned int *a3)
{
  void *v5; // rax
  void *v6; // rsi
  HGDIOBJ v7; // rdi
  void *v8; // rax
  HGDIOBJ v9; // rbx

  v5 = (void *)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))pfnCreatePen)(0, 0, *a3);
  v6 = v5;
  if ( v5 )
  {
    v7 = SelectObject(this[3], v5);
    v8 = (void *)((__int64 (__fastcall *)(__int64))pfnGetStockObject)(5);
    v9 = SelectObject(this[3], v8);
    ((void (__fastcall *)(HDC, _QWORD, _QWORD, _QWORD, LONG))pfnRectangle)(
      this[3],
      (unsigned int)a2->left,
      (unsigned int)a2->top,
      (unsigned int)a2->right,
      a2->bottom);
    SelectObject(this[3], v9);
    SelectObject(this[3], v7);
    DeleteObject(v6);
    LOBYTE(v5) = 1;
  }
  return (char)v5;
}

```

## disassembly

```asm
0x1802071b0  push    rbx
0x1802071b2  push    rbp
0x1802071b3  push    rsi
0x1802071b4  push    rdi
0x1802071b5  push    r14
0x1802071b7  sub     rsp, 30h
0x1802071bb  mov     r8d, [r8]
0x1802071be  mov     r14, rdx
0x1802071c1  mov     rax, cs:?pfnCreatePen@@3P6A_JXZEA; __int64 (*pfnCreatePen)(void)
0x1802071c8  mov     rbp, rcx
0x1802071cb  xor     edx, edx
0x1802071cd  xor     ecx, ecx
0x1802071cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802071d4  mov     rsi, rax
0x1802071d7  test    rax, rax
0x1802071da  jz      short loc_180207255
0x1802071dc  mov     rcx, [rbp+18h]; hdc
0x1802071e0  mov     rdx, rax; h
0x1802071e3  call    cs:__imp_SelectObject
0x1802071e9  mov     rdi, rax
0x1802071ec  mov     ecx, 5
0x1802071f1  mov     rax, cs:?pfnGetStockObject@@3P6A_JXZEA; __int64 (*pfnGetStockObject)(void)
0x1802071f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802071fd  mov     rcx, [rbp+18h]; hdc
0x180207201  mov     rdx, rax; h
0x180207204  call    cs:__imp_SelectObject
0x18020720a  mov     ecx, [r14+0Ch]
0x18020720e  mov     rbx, rax
0x180207211  mov     rax, cs:?pfnRectangle@@3P6A_JXZEA; __int64 (*pfnRectangle)(void)
0x180207218  mov     r9d, [r14+8]
0x18020721c  mov     r8d, [r14+4]
0x180207220  mov     edx, [r14]
0x180207223  mov     [rsp+58h+var_38], ecx
0x180207227  mov     rcx, [rbp+18h]
0x18020722b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180207230  mov     rcx, [rbp+18h]; hdc
0x180207234  mov     rdx, rbx; h
0x180207237  call    cs:__imp_SelectObject
0x18020723d  mov     rcx, [rbp+18h]; hdc
0x180207241  mov     rdx, rdi; h
0x180207244  call    cs:__imp_SelectObject
0x18020724a  mov     rcx, rsi; ho
0x18020724d  call    cs:__imp_DeleteObject
0x180207253  mov     al, 1
0x180207255  add     rsp, 30h
0x180207259  pop     r14
0x18020725b  pop     rdi
0x18020725c  pop     rsi
0x18020725d  pop     rbp
0x18020725e  pop     rbx
0x18020725f  retn
```
