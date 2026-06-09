# Gdiplus::Brush::Clone(void)

- ea: `0x18001d990`
- end: `0x18001da0f`
- name: `?Clone@Brush@Gdiplus@@UEBAPEAV12@XZ`
- size: `127`
- prototype: `struct Gdiplus::Brush *__fastcall(Gdiplus::Brush *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001d990`

## import_xrefs

- `gdiplus!GdipDeleteBrush` at `0x18001d9f4`
- `gdiplus!GdipDeleteBrush` at `0x18001d9f4`
- `gdiplus!GdipAlloc` at `0x18001d9c4`
- `gdiplus!GdipAlloc` at `0x18001d9c4`
- `gdiplus!GdipCloneBrush` at `0x18001d9ad`
- `gdiplus!GdipCloneBrush` at `0x18001d9ad`

## pseudocode

```c
struct Gdiplus::Brush *__fastcall Gdiplus::Brush::Clone(Gdiplus::Brush *this)
{
  int *v1; // rdi
  int v2; // eax
  __int64 v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rbx
  int v6; // eax
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = 0;
  v1 = (int *)((char *)this + 16);
  v2 = GdipCloneBrush(*((_QWORD *)this + 1), &v8);
  if ( v2 )
    *v1 = v2;
  v3 = GdipAlloc(24);
  v4 = v8;
  v5 = v3;
  if ( v3 )
  {
    v6 = *v1;
    *(_QWORD *)v5 = &Gdiplus::SolidBrush::`vftable';
    *(_DWORD *)(v5 + 16) = v6;
    *(_QWORD *)(v5 + 8) = v4;
  }
  else
  {
    v5 = 0;
    GdipDeleteBrush(v8);
  }
  return (struct Gdiplus::Brush *)v5;
}

```

## disassembly

```asm
0x18001d990  mov     [rsp+arg_8], rbx
0x18001d995  push    rdi
0x18001d996  sub     rsp, 20h
0x18001d99a  and     [rsp+28h+arg_0], 0
0x18001d9a0  lea     rdi, [rcx+10h]
0x18001d9a4  mov     rcx, [rcx+8]
0x18001d9a8  lea     rdx, [rsp+28h+arg_0]
0x18001d9ad  call    cs:__imp_GdipCloneBrush
0x18001d9b4  nop     dword ptr [rax+rax+00h]
0x18001d9b9  test    eax, eax
0x18001d9bb  jz      short loc_18001D9BF
0x18001d9bd  mov     [rdi], eax
0x18001d9bf  mov     ecx, 18h
0x18001d9c4  call    cs:__imp_GdipAlloc
0x18001d9cb  nop     dword ptr [rax+rax+00h]
0x18001d9d0  mov     rcx, [rsp+28h+arg_0]
0x18001d9d5  mov     rbx, rax
0x18001d9d8  test    rax, rax
0x18001d9db  jz      short loc_18001D9F2
0x18001d9dd  mov     eax, [rdi]
0x18001d9df  lea     rdx, ??_7SolidBrush@Gdiplus@@6B@; const Gdiplus::SolidBrush::`vftable'
0x18001d9e6  mov     [rbx], rdx
0x18001d9e9  mov     [rbx+10h], eax
0x18001d9ec  mov     [rbx+8], rcx
0x18001d9f0  jmp     short loc_18001DA00
0x18001d9f2  xor     ebx, ebx
0x18001d9f4  call    cs:__imp_GdipDeleteBrush
0x18001d9fb  nop     dword ptr [rax+rax+00h]
0x18001da00  mov     rax, rbx
0x18001da03  mov     rbx, [rsp+28h+arg_8]
0x18001da08  add     rsp, 20h
0x18001da0c  pop     rdi
0x18001da0d  retn
```
