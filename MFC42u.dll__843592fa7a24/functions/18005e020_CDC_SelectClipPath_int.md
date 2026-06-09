# CDC::SelectClipPath(int)

- ea: `0x18005e020`
- end: `0x18005e0a1`
- name: `?SelectClipPath@CDC@@QEAAHH@Z`
- size: `129`
- prototype: `__int64 __fastcall(CDC *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18005e020`

## import_xrefs

- `GDI32!DeleteObject` at `0x18005e089`
- `GDI32!DeleteObject` at `0x18005e089`
- `GDI32!SelectClipRgn` at `0x18005e07a`
- `GDI32!SelectClipRgn` at `0x18005e07a`
- `GDI32!SelectClipPath` at `0x18005e036`
- `GDI32!SelectClipPath` at `0x18005e036`
- `GDI32!CreateRectRgn` at `0x18005e059`
- `GDI32!CreateRectRgn` at `0x18005e059`
- `GDI32!GetClipRgn` at `0x18005e069`
- `GDI32!GetClipRgn` at `0x18005e069`

## pseudocode

```c
BOOL __fastcall CDC::SelectClipPath(HDC *this, int a2)
{
  BOOL result; // eax
  int v4; // edi
  HRGN RectRgn; // rsi

  result = SelectClipPath(this[1], a2);
  if ( result )
  {
    v4 = 1;
    if ( this[1] != this[2] )
    {
      RectRgn = CreateRectRgn(0, 0, 0, 0);
      if ( GetClipRgn(this[1], RectRgn) < 0 || !SelectClipRgn(this[2], RectRgn) )
        v4 = 0;
      DeleteObject(RectRgn);
    }
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x18005e020  mov     [rsp+arg_0], rbx
0x18005e025  mov     [rsp+arg_8], rsi
0x18005e02a  push    rdi
0x18005e02b  sub     rsp, 20h
0x18005e02f  mov     rbx, rcx
0x18005e032  mov     rcx, [rcx+8]; hdc
0x18005e036  call    cs:__imp_SelectClipPath
0x18005e03c  test    eax, eax
0x18005e03e  jz      short loc_18005E091
0x18005e040  mov     rax, [rbx+10h]
0x18005e044  mov     edi, 1
0x18005e049  cmp     [rbx+8], rax
0x18005e04d  jz      short loc_18005E08F
0x18005e04f  xor     r9d, r9d; y2
0x18005e052  xor     r8d, r8d; x2
0x18005e055  xor     edx, edx; y1
0x18005e057  xor     ecx, ecx; x1
0x18005e059  call    cs:__imp_CreateRectRgn
0x18005e05f  mov     rcx, [rbx+8]; hdc
0x18005e063  mov     rdx, rax; hrgn
0x18005e066  mov     rsi, rax
0x18005e069  call    cs:__imp_GetClipRgn
0x18005e06f  test    eax, eax
0x18005e071  js      short loc_18005E084
0x18005e073  mov     rcx, [rbx+10h]; hdc
0x18005e077  mov     rdx, rsi; hrgn
0x18005e07a  call    cs:__imp_SelectClipRgn
0x18005e080  test    eax, eax
0x18005e082  jnz     short loc_18005E086
0x18005e084  xor     edi, edi
0x18005e086  mov     rcx, rsi; ho
0x18005e089  call    cs:__imp_DeleteObject
0x18005e08f  mov     eax, edi
0x18005e091  mov     rbx, [rsp+28h+arg_0]
0x18005e096  mov     rsi, [rsp+28h+arg_8]
0x18005e09b  add     rsp, 20h
0x18005e09f  pop     rdi
0x18005e0a0  retn
```
