# CDropCaret::ShowCaret(void)

- ea: `0x18005a15c`
- end: `0x18005a1ef`
- name: `?ShowCaret@CDropCaret@@QEAAXXZ`
- size: `147`
- prototype: `void __fastcall(CDropCaret *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180059ab0`
- `0x18005a1f8`

## callees

- `0x18005a15c`

## import_xrefs

- `GDI32!LineTo` at `0x18005a1c3`
- `GDI32!LineTo` at `0x18005a1c3`
- `GDI32!MoveToEx` at `0x18005a1ae`
- `GDI32!MoveToEx` at `0x18005a1ae`
- `GDI32!CreatePen` at `0x18005a17d`
- `GDI32!CreatePen` at `0x18005a17d`
- `GDI32!DeleteObject` at `0x18005a1d9`
- `GDI32!DeleteObject` at `0x18005a1d9`
- `GDI32!SelectObject` at `0x18005a192`
- `GDI32!SelectObject` at `0x18005a1d0`
- `GDI32!SelectObject` at `0x18005a192`
- `GDI32!SelectObject` at `0x18005a1d0`

## pseudocode

```c
void __fastcall CDropCaret::ShowCaret(CDropCaret *this)
{
  HPEN Pen; // rax
  HPEN v3; // rdi
  HGDIOBJ v4; // rsi

  if ( *((_DWORD *)this + 5) != -1 )
  {
    Pen = CreatePen(0, 1, 0);
    v3 = Pen;
    if ( Pen )
    {
      v4 = SelectObject(*((HDC *)this + 1), Pen);
      if ( v4 )
      {
        MoveToEx(*((HDC *)this + 1), *((_DWORD *)this + 7), *((_DWORD *)this + 8), 0);
        LineTo(*((HDC *)this + 1), *((_DWORD *)this + 7), *((_DWORD *)this + 5) + *((_DWORD *)this + 8));
        SelectObject(*((HDC *)this + 1), v4);
      }
      DeleteObject(v3);
    }
  }
}

```

## disassembly

```asm
0x18005a15c  mov     [rsp+arg_0], rbx
0x18005a161  mov     [rsp+arg_8], rsi
0x18005a166  push    rdi
0x18005a167  sub     rsp, 20h
0x18005a16b  cmp     dword ptr [rcx+14h], 0FFFFFFFFh
0x18005a16f  mov     rbx, rcx
0x18005a172  jz      short loc_18005A1DF
0x18005a174  xor     r8d, r8d; color
0x18005a177  xor     ecx, ecx; iStyle
0x18005a179  lea     edx, [r8+1]; cWidth
0x18005a17d  call    cs:__imp_CreatePen
0x18005a183  mov     rdi, rax
0x18005a186  test    rax, rax
0x18005a189  jz      short loc_18005A1DF
0x18005a18b  mov     rcx, [rbx+8]; hdc
0x18005a18f  mov     rdx, rax; h
0x18005a192  call    cs:__imp_SelectObject
0x18005a198  mov     rsi, rax
0x18005a19b  test    rax, rax
0x18005a19e  jz      short loc_18005A1D6
0x18005a1a0  mov     r8d, [rbx+20h]; y
0x18005a1a4  xor     r9d, r9d; lppt
0x18005a1a7  mov     edx, [rbx+1Ch]; x
0x18005a1aa  mov     rcx, [rbx+8]; hdc
0x18005a1ae  call    cs:__imp_MoveToEx
0x18005a1b4  mov     r8d, [rbx+20h]
0x18005a1b8  add     r8d, [rbx+14h]; y
0x18005a1bc  mov     edx, [rbx+1Ch]; x
0x18005a1bf  mov     rcx, [rbx+8]; hdc
0x18005a1c3  call    cs:__imp_LineTo
0x18005a1c9  mov     rcx, [rbx+8]; hdc
0x18005a1cd  mov     rdx, rsi; h
0x18005a1d0  call    cs:__imp_SelectObject
0x18005a1d6  mov     rcx, rdi; ho
0x18005a1d9  call    cs:__imp_DeleteObject
0x18005a1df  mov     rbx, [rsp+28h+arg_0]
0x18005a1e4  mov     rsi, [rsp+28h+arg_8]
0x18005a1e9  add     rsp, 20h
0x18005a1ed  pop     rdi
0x18005a1ee  retn
```
