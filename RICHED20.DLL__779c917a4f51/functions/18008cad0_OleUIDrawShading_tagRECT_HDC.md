# OleUIDrawShading(tagRECT *,HDC__ *)

- ea: `0x18008cad0`
- end: `0x18008cc20`
- name: `?OleUIDrawShading@@YAXPEAUtagRECT@@PEAUHDC__@@@Z`
- size: `336`
- prototype: `void(struct tagRECT *, HDC)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18004a23c`

## callees

- `0x180091140`

## import_xrefs

- `USER32!GetSysColor` at `0x18008cb71`
- `USER32!GetSysColor` at `0x18008cb89`
- `USER32!GetSysColor` at `0x18008cb71`
- `USER32!GetSysColor` at `0x18008cb89`
- `GDI32!DeleteObject` at `0x18008cbea`
- `GDI32!DeleteObject` at `0x18008cbf5`
- `GDI32!DeleteObject` at `0x18008cbea`
- `GDI32!DeleteObject` at `0x18008cbf5`
- `GDI32!SelectObject` at `0x18008cb56`
- `GDI32!SelectObject` at `0x18008cbe1`
- `GDI32!SelectObject` at `0x18008cb56`
- `GDI32!SelectObject` at `0x18008cbe1`
- `GDI32!SetTextColor` at `0x18008cb7c`
- `GDI32!SetTextColor` at `0x18008cbca`
- `GDI32!SetTextColor` at `0x18008cb7c`
- `GDI32!SetTextColor` at `0x18008cbca`
- `GDI32!SetBkColor` at `0x18008cb94`
- `GDI32!SetBkColor` at `0x18008cbd5`
- `GDI32!SetBkColor` at `0x18008cb94`
- `GDI32!SetBkColor` at `0x18008cbd5`
- `GDI32!PatBlt` at `0x18008cbbf`
- `GDI32!PatBlt` at `0x18008cbbf`
- `GDI32!CreateBitmap` at `0x18008cb39`
- `GDI32!CreateBitmap` at `0x18008cb39`
- `GDI32!CreatePatternBrush` at `0x18008cb47`
- `GDI32!CreatePatternBrush` at `0x18008cb47`

## pseudocode

```c
void __fastcall OleUIDrawShading(struct tagRECT *a1, HDC a2)
{
  HDC v2; // rbx
  HBRUSH PatternBrush; // r13
  HGDIOBJ v5; // rax
  LONG left; // r15d
  LONG top; // r14d
  void *v8; // r12
  LONG right; // ebp
  COLORREF SysColor; // eax
  COLORREF v11; // edi
  COLORREF v12; // eax
  HBITMAP ho; // [rsp+38h] [rbp-60h]
  _DWORD Bits[4]; // [rsp+40h] [rbp-58h] BYREF

  Bits[0] = 2228241;
  v2 = a2;
  Bits[1] = 8912964;
  Bits[2] = 2228241;
  Bits[3] = 8912964;
  ho = CreateBitmap(8, 8, 1u, 1u, Bits);
  PatternBrush = CreatePatternBrush(ho);
  v5 = SelectObject(v2, PatternBrush);
  left = a1->left;
  top = a1->top;
  v8 = v5;
  right = a1->right;
  LODWORD(a1) = a1->bottom;
  SysColor = GetSysColor(5);
  v11 = SetTextColor(v2, SysColor);
  v12 = GetSysColor(8);
  LODWORD(v2) = SetBkColor(v2, v12);
  PatBlt(a2, left, top, right - left, (_DWORD)a1 - top, 0xA000C9u);
  SetTextColor(a2, v11);
  SetBkColor(a2, (COLORREF)v2);
  SelectObject(a2, v8);
  DeleteObject(PatternBrush);
  DeleteObject(ho);
}

```

## disassembly

```asm
0x18008cad0  mov     [rsp+arg_10], rbx
0x18008cad5  push    rbp
0x18008cad6  push    rsi
0x18008cad7  push    rdi
0x18008cad8  push    r12
0x18008cada  push    r13
0x18008cadc  push    r14
0x18008cade  push    r15
0x18008cae0  sub     rsp, 60h
0x18008cae4  mov     rax, cs:__security_cookie
0x18008caeb  xor     rax, rsp
0x18008caee  mov     [rsp+98h+var_48], rax
0x18008caf3  mov     r8d, 1; nPlanes
0x18008caf9  mov     [rsp+98h+hdc], rdx
0x18008cafe  lea     rax, [rsp+98h+Bits]
0x18008cb03  mov     [rsp+98h+Bits], 220011h
0x18008cb0b  mov     [rsp+98h+lpBits], rax; lpBits
0x18008cb10  mov     rbx, rdx
0x18008cb13  mov     rsi, rcx
0x18008cb16  mov     [rsp+98h+var_54], 880044h
0x18008cb1e  lea     eax, [r8+7]
0x18008cb22  mov     [rsp+98h+var_50], 220011h
0x18008cb2a  mov     edx, eax; nHeight
0x18008cb2c  mov     [rsp+98h+var_4C], 880044h
0x18008cb34  mov     ecx, eax; nWidth
0x18008cb36  mov     r9d, r8d; nBitCount
0x18008cb39  call    cs:__imp_CreateBitmap
0x18008cb3f  mov     rcx, rax; hbm
0x18008cb42  mov     [rsp+98h+ho], rax
0x18008cb47  call    cs:__imp_CreatePatternBrush
0x18008cb4d  mov     rdx, rax; h
0x18008cb50  mov     rcx, rbx; hdc
0x18008cb53  mov     r13, rax
0x18008cb56  call    cs:__imp_SelectObject
0x18008cb5c  mov     r15d, [rsi]
0x18008cb5f  mov     ecx, 5; nIndex
0x18008cb64  mov     r14d, [rsi+4]
0x18008cb68  mov     r12, rax
0x18008cb6b  mov     ebp, [rsi+8]
0x18008cb6e  mov     esi, [rsi+0Ch]
0x18008cb71  call    cs:__imp_GetSysColor
0x18008cb77  mov     edx, eax; color
0x18008cb79  mov     rcx, rbx; hdc
0x18008cb7c  call    cs:__imp_SetTextColor
0x18008cb82  mov     ecx, 8; nIndex
0x18008cb87  mov     edi, eax
0x18008cb89  call    cs:__imp_GetSysColor
0x18008cb8f  mov     edx, eax; color
0x18008cb91  mov     rcx, rbx; hdc
0x18008cb94  call    cs:__imp_SetBkColor
0x18008cb9a  sub     esi, r14d
0x18008cb9d  mov     [rsp+98h+rop], 0A000C9h; rop
0x18008cba5  mov     dword ptr [rsp+98h+lpBits], esi; h
0x18008cba9  sub     ebp, r15d
0x18008cbac  mov     rsi, [rsp+98h+hdc]
0x18008cbb1  mov     r9d, ebp; w
0x18008cbb4  mov     rcx, rsi; hdc
0x18008cbb7  mov     r8d, r14d; y
0x18008cbba  mov     edx, r15d; x
0x18008cbbd  mov     ebx, eax
0x18008cbbf  call    cs:__imp_PatBlt
0x18008cbc5  mov     edx, edi; color
0x18008cbc7  mov     rcx, rsi; hdc
0x18008cbca  call    cs:__imp_SetTextColor
0x18008cbd0  mov     edx, ebx; color
0x18008cbd2  mov     rcx, rsi; hdc
0x18008cbd5  call    cs:__imp_SetBkColor
0x18008cbdb  mov     rdx, r12; h
0x18008cbde  mov     rcx, rsi; hdc
0x18008cbe1  call    cs:__imp_SelectObject
0x18008cbe7  mov     rcx, r13; ho
0x18008cbea  call    cs:__imp_DeleteObject
0x18008cbf0  mov     rcx, [rsp+98h+ho]; ho
0x18008cbf5  call    cs:__imp_DeleteObject
0x18008cbfb  mov     rcx, [rsp+98h+var_48]
0x18008cc00  xor     rcx, rsp; StackCookie
0x18008cc03  call    __security_check_cookie
0x18008cc08  mov     rbx, [rsp+98h+arg_10]
0x18008cc10  add     rsp, 60h
0x18008cc14  pop     r15
0x18008cc16  pop     r14
0x18008cc18  pop     r13
0x18008cc1a  pop     r12
0x18008cc1c  pop     rdi
0x18008cc1d  pop     rsi
0x18008cc1e  pop     rbp
0x18008cc1f  retn
```
