# sub_1800BF6DC

- ea: `0x1800bf6dc`
- end: `0x1800bf7bd`
- name: `sub_1800BF6DC`
- size: `225`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800bf7c0`
- `0x1800bf7f0`
- `0x1800bf800`

## callees

- `0x180002a40`
- `0x1800bf6dc`
- `0x1804c6020`

## import_xrefs

- `GDI32!CreatePen` at `0x1800bf736`
- `GDI32!CreatePen` at `0x1800bf736`
- `GDI32!ExtCreatePen` at `0x1800bf769`
- `GDI32!ExtCreatePen` at `0x1800bf769`
- `GDI32!SelectObject` at `0x1800bf780`
- `GDI32!SelectObject` at `0x1800bf780`
- `GDI32!DeleteObject` at `0x1800bf78f`
- `GDI32!DeleteObject` at `0x1800bf78f`

## pseudocode

```c
char __fastcall sub_1800BF6DC(__int64 a1, COLORREF a2, int a3, int a4)
{
  int v8; // ecx
  HPEN Pen; // rax
  HPEN v10; // rbp
  HDC v11; // rax
  void *v12; // rcx
  LOGBRUSH plbrush; // [rsp+30h] [rbp-48h] BYREF

  if ( a2 != *(_DWORD *)(a1 + 16) || a3 != *(_DWORD *)(a1 + 20) || a4 != *(_DWORD *)(a1 + 24) )
  {
    if ( a4 == 2 )
      v8 = 2;
    else
      v8 = 0;
    if ( a3 > 1 )
    {
      plbrush.lbStyle = 0;
      plbrush.lbColor = a2;
      plbrush.lbHatch = 0;
      Pen = ExtCreatePen(v8 | 0x10000u, a3, &plbrush, 0, 0);
    }
    else
    {
      Pen = CreatePen(v8, a3, a2);
    }
    v10 = Pen;
    v11 = (HDC)sub_180002A40(a1);
    SelectObject(v11, v10);
    v12 = *(void **)(a1 + 40);
    if ( v12 )
      DeleteObject(v12);
    *(_QWORD *)(a1 + 40) = v10;
    *(_DWORD *)(a1 + 16) = a2;
    *(_DWORD *)(a1 + 20) = a3;
    *(_DWORD *)(a1 + 24) = a4;
  }
  return 1;
}

```

## disassembly

```asm
0x1800bf6dc  push    rbx
0x1800bf6de  push    rbp
0x1800bf6df  push    rsi
0x1800bf6e0  push    rdi
0x1800bf6e1  push    r14
0x1800bf6e3  sub     rsp, 50h
0x1800bf6e7  mov     rax, cs:__security_cookie
0x1800bf6ee  xor     rax, rsp
0x1800bf6f1  mov     [rsp+78h+var_38], rax
0x1800bf6f6  mov     esi, r9d
0x1800bf6f9  mov     edi, r8d
0x1800bf6fc  mov     r14d, edx
0x1800bf6ff  mov     rbx, rcx
0x1800bf702  cmp     edx, [rcx+10h]
0x1800bf705  jnz     short loc_1800BF717
0x1800bf707  cmp     r8d, [rcx+14h]
0x1800bf70b  jnz     short loc_1800BF717
0x1800bf70d  cmp     r9d, [rcx+18h]
0x1800bf711  jz      loc_1800BF7A3
0x1800bf717  mov     ecx, esi
0x1800bf719  sub     ecx, 1
0x1800bf71c  jz      short loc_1800BF72A
0x1800bf71e  cmp     ecx, 1
0x1800bf721  jnz     short loc_1800BF72A
0x1800bf723  mov     ecx, 2
0x1800bf728  jmp     short loc_1800BF72C
0x1800bf72a  xor     ecx, ecx; iStyle
0x1800bf72c  mov     edx, edi; cWidth
0x1800bf72e  cmp     edi, 1
0x1800bf731  jg      short loc_1800BF73E
0x1800bf733  mov     r8d, r14d; color
0x1800bf736  call    cs:CreatePen
0x1800bf73c  jmp     short loc_1800BF76F
0x1800bf73e  bts     ecx, 10h; iPenStyle
0x1800bf742  mov     [rsp+78h+plbrush.lbStyle], 0
0x1800bf74a  xor     r9d, r9d; cStyle
0x1800bf74d  mov     [rsp+78h+plbrush.lbColor], r14d
0x1800bf752  lea     r8, [rsp+78h+plbrush]; plbrush
0x1800bf757  mov     [rsp+78h+plbrush.lbHatch], 0
0x1800bf760  mov     [rsp+78h+pstyle], 0; pstyle
0x1800bf769  call    cs:ExtCreatePen
0x1800bf76f  mov     rcx, rbx
0x1800bf772  mov     rbp, rax
0x1800bf775  call    sub_180002A40
0x1800bf77a  mov     rcx, rax; hdc
0x1800bf77d  mov     rdx, rbp; h
0x1800bf780  call    cs:SelectObject
0x1800bf786  mov     rcx, [rbx+28h]; ho
0x1800bf78a  test    rcx, rcx
0x1800bf78d  jz      short loc_1800BF795
0x1800bf78f  call    cs:DeleteObject
0x1800bf795  mov     [rbx+28h], rbp
0x1800bf799  mov     [rbx+10h], r14d
0x1800bf79d  mov     [rbx+14h], edi
0x1800bf7a0  mov     [rbx+18h], esi
0x1800bf7a3  mov     al, 1
0x1800bf7a5  mov     rcx, [rsp+78h+var_38]
0x1800bf7aa  xor     rcx, rsp; StackCookie
0x1800bf7ad  call    __security_check_cookie
0x1800bf7b2  add     rsp, 50h
0x1800bf7b6  pop     r14
0x1800bf7b8  pop     rdi
0x1800bf7b9  pop     rsi
0x1800bf7ba  pop     rbp
0x1800bf7bb  pop     rbx
0x1800bf7bc  retn
```
