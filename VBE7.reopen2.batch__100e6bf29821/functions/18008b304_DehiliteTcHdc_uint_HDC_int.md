# DehiliteTcHdc(uint,HDC__ *,int)

- ea: `0x18008b304`
- end: `0x18008b49c`
- name: `?DehiliteTcHdc@@YAXIPEAUHDC__@@H@Z`
- size: `408`
- prototype: `void __fastcall(unsigned int, HDC, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18008b7cc`
- `0x18008c4a8`
- `0x18008c758`

## callees

- `0x1800012c8`
- `0x18008b304`
- `0x18008b738`
- `0x180379380`

## import_xrefs

- `GDI32!LineTo` at `0x18008b39e`
- `GDI32!LineTo` at `0x18008b3c6`
- `GDI32!LineTo` at `0x18008b3e8`
- `GDI32!LineTo` at `0x18008b40b`
- `GDI32!LineTo` at `0x18008b39e`
- `GDI32!LineTo` at `0x18008b3c6`
- `GDI32!LineTo` at `0x18008b3e8`
- `GDI32!LineTo` at `0x18008b40b`
- `GDI32!Rectangle` at `0x18008b478`
- `GDI32!Rectangle` at `0x18008b478`
- `GDI32!MoveToEx` at `0x18008b388`
- `GDI32!MoveToEx` at `0x18008b3b3`
- `GDI32!MoveToEx` at `0x18008b3d8`
- `GDI32!MoveToEx` at `0x18008b3fb`
- `GDI32!MoveToEx` at `0x18008b388`
- `GDI32!MoveToEx` at `0x18008b3b3`
- `GDI32!MoveToEx` at `0x18008b3d8`
- `GDI32!MoveToEx` at `0x18008b3fb`
- `GDI32!SelectObject` at `0x18008b369`
- `GDI32!SelectObject` at `0x18008b41b`
- `GDI32!SelectObject` at `0x18008b42b`
- `GDI32!SelectObject` at `0x18008b369`
- `GDI32!SelectObject` at `0x18008b41b`
- `GDI32!SelectObject` at `0x18008b42b`

## pseudocode

```c
void __fastcall DehiliteTcHdc(unsigned int a1, HDC a2, int a3)
{
  HPEN v4; // rax
  int v5; // edi
  int v6; // esi
  int v7; // r15d
  int v8; // r13d
  int v9; // ebx
  int v10; // edi
  LONG bottom; // eax
  LONG right; // r9d
  LONG top; // r8d
  LONG left; // edx
  int y[4]; // [rsp+30h] [rbp-38h] BYREF

  if ( a1 != 255 )
  {
    *(struct tagRECT *)y = *RctGetTc((struct tagRECT *)y, a1, a3);
    v4 = BrHpenCreate(0, 1, 0x808080u);
    SelectObject(a2, v4);
    v5 = y[0];
    v6 = y[1];
    v7 = y[0] - 2;
    MoveToEx(a2, y[0] - 2, y[1] - 1, 0);
    v8 = y[2];
    LineTo(a2, y[2] + 2, v6 - 1);
    v9 = v5 - 1;
    MoveToEx(a2, v5 - 1, v6 - 2, 0);
    v10 = y[3];
    LineTo(a2, v9, y[3] + 2);
    MoveToEx(a2, v7, v10, 0);
    LineTo(a2, v8 + 2, v10);
    MoveToEx(a2, v8, v6 - 2, 0);
    LineTo(a2, v8, v10 + 2);
    SelectObject(a2, Sys_hpenBlack);
    SelectObject(a2, Sys_hbrNull);
    if ( a3 )
    {
      bottom = rctPopup.bottom;
      right = rctPopup.right;
      top = rctPopup.top;
      left = rctPopup.left;
    }
    else
    {
      bottom = rc.bottom;
      right = rc.right;
      top = rc.top;
      left = rc.left;
    }
    Rectangle(a2, left, top, right, bottom);
  }
}

```

## disassembly

```asm
0x18008b304  cmp     ecx, 0FFh
0x18008b30a  jz      locret_18008B49B
0x18008b310  mov     rax, rsp
0x18008b313  mov     [rax+8], rbx
0x18008b317  mov     [rax+10h], rbp
0x18008b31b  mov     [rax+20h], rsi
0x18008b31f  mov     [rax+18h], r8d
0x18008b323  push    rdi
0x18008b324  push    r12
0x18008b326  push    r13
0x18008b328  push    r14
0x18008b32a  push    r15
0x18008b32c  mov     eax, 40h
0x18008b331  call    _alloca_probe
0x18008b336  sub     rsp, rax
0x18008b339  mov     r12, rdx
0x18008b33c  mov     edx, ecx; unsigned int
0x18008b33e  lea     rcx, [rsp+68h+y]; retstr
0x18008b343  call    ?RctGetTc@@YA?AUtagRECT@@IH@Z; RctGetTc(uint,int)
0x18008b348  mov     edx, 1; int
0x18008b34d  xor     ecx, ecx; int
0x18008b34f  mov     r8d, 808080h; unsigned int
0x18008b355  movups  xmm0, xmmword ptr [rax]
0x18008b358  movdqu  xmmword ptr [rsp+68h+y], xmm0
0x18008b35e  call    ?BrHpenCreate@@YAPEAUHPEN__@@HHK@Z; BrHpenCreate(int,int,ulong)
0x18008b363  mov     rcx, r12; hdc
0x18008b366  mov     rdx, rax; h
0x18008b369  call    cs:__imp_SelectObject
0x18008b36f  mov     edi, [rsp+68h+y]
0x18008b373  mov     esi, [rsp+68h+y+4]
0x18008b377  lea     r15d, [rdi-2]
0x18008b37b  lea     r8d, [rsi-1]; y
0x18008b37f  xor     r9d, r9d; lppt
0x18008b382  mov     edx, r15d; x
0x18008b385  mov     rcx, r12; hdc
0x18008b388  call    cs:__imp_MoveToEx
0x18008b38e  mov     r13d, [rsp+68h+y+8]
0x18008b393  lea     r8d, [rsi-1]; y
0x18008b397  lea     edx, [r13+2]; x
0x18008b39b  mov     rcx, r12; hdc
0x18008b39e  call    cs:__imp_LineTo
0x18008b3a4  lea     ebx, [rdi-1]
0x18008b3a7  lea     r8d, [rsi-2]; y
0x18008b3ab  mov     edx, ebx; x
0x18008b3ad  xor     r9d, r9d; lppt
0x18008b3b0  mov     rcx, r12; hdc
0x18008b3b3  call    cs:__imp_MoveToEx
0x18008b3b9  mov     edi, [rsp+68h+y+0Ch]
0x18008b3bd  mov     edx, ebx; x
0x18008b3bf  lea     r8d, [rdi+2]; y
0x18008b3c3  mov     rcx, r12; hdc
0x18008b3c6  call    cs:__imp_LineTo
0x18008b3cc  xor     r9d, r9d; lppt
0x18008b3cf  mov     r8d, edi; y
0x18008b3d2  mov     edx, r15d; x
0x18008b3d5  mov     rcx, r12; hdc
0x18008b3d8  call    cs:__imp_MoveToEx
0x18008b3de  lea     edx, [r13+2]; x
0x18008b3e2  mov     r8d, edi; y
0x18008b3e5  mov     rcx, r12; hdc
0x18008b3e8  call    cs:__imp_LineTo
0x18008b3ee  lea     r8d, [rsi-2]; y
0x18008b3f2  xor     r9d, r9d; lppt
0x18008b3f5  mov     edx, r13d; x
0x18008b3f8  mov     rcx, r12; hdc
0x18008b3fb  call    cs:__imp_MoveToEx
0x18008b401  lea     r8d, [rdi+2]; y
0x18008b405  mov     edx, r13d; x
0x18008b408  mov     rcx, r12; hdc
0x18008b40b  call    cs:__imp_LineTo
0x18008b411  mov     rdx, cs:?Sys_hpenBlack@@3PEAUHPEN__@@EA; h
0x18008b418  mov     rcx, r12; hdc
0x18008b41b  call    cs:__imp_SelectObject
0x18008b421  mov     rdx, cs:?Sys_hbrNull@@3PEAUHBRUSH__@@EA; h
0x18008b428  mov     rcx, r12; hdc
0x18008b42b  call    cs:__imp_SelectObject
0x18008b431  cmp     [rsp+68h+arg_10], 0
0x18008b439  mov     rcx, r12; hdc
0x18008b43c  jz      short loc_18008B45A
0x18008b43e  mov     eax, cs:?rctPopup@@3UtagRECT@@A.bottom; tagRECT rctPopup ...
0x18008b444  mov     r9d, cs:?rctPopup@@3UtagRECT@@A.right; tagRECT rctPopup ...
0x18008b44b  mov     r8d, cs:?rctPopup@@3UtagRECT@@A.top; tagRECT rctPopup ...
0x18008b452  mov     edx, cs:?rctPopup@@3UtagRECT@@A.left; tagRECT rctPopup ...
0x18008b458  jmp     short loc_18008B474
0x18008b45a  mov     eax, cs:rc.bottom
0x18008b460  mov     r9d, cs:rc.right; right
0x18008b467  mov     r8d, cs:rc.top; top
0x18008b46e  mov     edx, cs:rc.left; left
0x18008b474  mov     [rsp+68h+bottom], eax; bottom
0x18008b478  call    cs:__imp_Rectangle
0x18008b47e  lea     r11, [rsp+68h+var_28]
0x18008b483  mov     rbx, [r11+30h]
0x18008b487  mov     rbp, [r11+38h]
0x18008b48b  mov     rsi, [r11+48h]
0x18008b48f  mov     rsp, r11
0x18008b492  pop     r15
0x18008b494  pop     r14
0x18008b496  pop     r13
0x18008b498  pop     r12
0x18008b49a  pop     rdi
0x18008b49b  retn
```
