# DrawXORLine(HDC__ *,tagPOINT *,tagPOINT *)

- ea: `0x18003ca04`
- end: `0x18003ca98`
- name: `?DrawXORLine@@YAXPEAUHDC__@@PEAUtagPOINT@@1@Z`
- size: `148`
- prototype: `void __fastcall(HDC hdc, struct tagPOINT *, struct tagPOINT *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18003c5e4`
- `0x18003c7f4`

## import_xrefs

- `GDI32!SetROP2` at `0x18003ca1f`
- `GDI32!SetROP2` at `0x18003ca1f`
- `GDI32!SetROP2` at `0x18003ca91`
- `GDI32!CreatePen` at `0x18003ca31`
- `GDI32!CreatePen` at `0x18003ca31`
- `GDI32!SelectObject` at `0x18003ca40`
- `GDI32!SelectObject` at `0x18003ca71`
- `GDI32!SelectObject` at `0x18003ca40`
- `GDI32!SelectObject` at `0x18003ca71`
- `GDI32!DeleteObject` at `0x18003ca7a`
- `GDI32!DeleteObject` at `0x18003ca7a`
- `GDI32!MoveToEx` at `0x18003ca55`
- `GDI32!MoveToEx` at `0x18003ca55`
- `GDI32!LineTo` at `0x18003ca65`
- `GDI32!LineTo` at `0x18003ca65`

## pseudocode

```c
void __fastcall DrawXORLine(HDC hdc, struct tagPOINT *a2, struct tagPOINT *a3)
{
  int v6; // ebp
  HPEN Pen; // rdi
  HGDIOBJ v8; // rbx

  v6 = SetROP2(hdc, 7);
  Pen = CreatePen(2, 1, 0);
  v8 = SelectObject(hdc, Pen);
  MoveToEx(hdc, a2->x, a2->y, 0);
  LineTo(hdc, a3->x, a3->y);
  SelectObject(hdc, v8);
  DeleteObject(Pen);
  SetROP2(hdc, v6);
}

```

## disassembly

```asm
0x18003ca04  push    rbx
0x18003ca06  push    rbp
0x18003ca07  push    rsi
0x18003ca08  push    rdi
0x18003ca09  push    r14
0x18003ca0b  push    r15
0x18003ca0d  sub     rsp, 28h
0x18003ca11  mov     rsi, rdx
0x18003ca14  mov     r14, r8
0x18003ca17  mov     edx, 7; rop2
0x18003ca1c  mov     r15, rcx
0x18003ca1f  call    cs:__imp_SetROP2
0x18003ca25  xor     r8d, r8d; color
0x18003ca28  mov     ebp, eax
0x18003ca2a  lea     edx, [r8+1]; cWidth
0x18003ca2e  lea     ecx, [rdx+1]; iStyle
0x18003ca31  call    cs:__imp_CreatePen
0x18003ca37  mov     rdx, rax; h
0x18003ca3a  mov     rcx, r15; hdc
0x18003ca3d  mov     rdi, rax
0x18003ca40  call    cs:__imp_SelectObject
0x18003ca46  mov     r8d, [rsi+4]; y
0x18003ca4a  xor     r9d, r9d; lppt
0x18003ca4d  mov     edx, [rsi]; x
0x18003ca4f  mov     rcx, r15; hdc
0x18003ca52  mov     rbx, rax
0x18003ca55  call    cs:__imp_MoveToEx
0x18003ca5b  mov     r8d, [r14+4]; y
0x18003ca5f  mov     rcx, r15; hdc
0x18003ca62  mov     edx, [r14]; x
0x18003ca65  call    cs:__imp_LineTo
0x18003ca6b  mov     rdx, rbx; h
0x18003ca6e  mov     rcx, r15; hdc
0x18003ca71  call    cs:__imp_SelectObject
0x18003ca77  mov     rcx, rdi; ho
0x18003ca7a  call    cs:__imp_DeleteObject
0x18003ca80  mov     edx, ebp
0x18003ca82  mov     rcx, r15
0x18003ca85  add     rsp, 28h
0x18003ca89  pop     r15
0x18003ca8b  pop     r14
0x18003ca8d  pop     rdi
0x18003ca8e  pop     rsi
0x18003ca8f  pop     rbp
0x18003ca90  pop     rbx
0x18003ca91  jmp     cs:__imp_SetROP2
```
