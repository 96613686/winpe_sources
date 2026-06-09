# NavigationPane::PaintClient(HDC__ *,tagRECT const &,bool)

- ea: `0x180070100`
- end: `0x1800701c7`
- name: `?PaintClient@NavigationPane@@AEAAXPEAUHDC__@@AEBUtagRECT@@_N@Z`
- size: `199`
- prototype: `void(NavigationPane *__hidden this, HDC, const struct tagRECT *, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007a10`
- `0x18007005c`

## callees

- `0x180029780`
- `0x18006fd80`
- `0x180070100`

## import_xrefs

- `GDI32!SelectObject` at `0x180070144`
- `GDI32!SelectObject` at `0x180070180`
- `GDI32!SelectObject` at `0x180070144`
- `GDI32!SelectObject` at `0x180070180`
- `GDI32!CreateSolidBrush` at `0x18007012c`
- `GDI32!CreateSolidBrush` at `0x18007012c`
- `GDI32!PatBlt` at `0x180070174`
- `GDI32!PatBlt` at `0x1800701b8`
- `GDI32!PatBlt` at `0x180070174`
- `GDI32!PatBlt` at `0x1800701b8`
- `GDI32!DeleteObject` at `0x180070189`
- `GDI32!DeleteObject` at `0x180070189`

## pseudocode

```c
void __fastcall NavigationPane::PaintClient(NavigationPane *this, HDC a2, const struct tagRECT *a3)
{
  NavigationPane *v5; // rdx
  __int64 v6; // r8
  char v7; // r9
  COLORREF PaneBackgroundColor; // eax
  HBRUSH SolidBrush; // rax
  HBRUSH v10; // rbx
  HGDIOBJ v11; // rbp

  if ( UIBase::ChildWindowCompositionHelper::IsCompositionEnabledForWindow((NavigationPane *)((char *)this + 208)) )
  {
    if ( v7 )
      PatBlt(a2, a3->left, *(_DWORD *)(v6 + 4), a3->right - a3->left, a3->bottom - *(_DWORD *)(v6 + 4), 0x42u);
  }
  else
  {
    PaneBackgroundColor = NavigationPane::GetPaneBackgroundColor(v5);
    SolidBrush = CreateSolidBrush(PaneBackgroundColor);
    v10 = SolidBrush;
    if ( SolidBrush )
    {
      v11 = SelectObject(a2, SolidBrush);
      if ( v11 )
      {
        PatBlt(a2, a3->left, a3->top, a3->right - a3->left, a3->bottom - a3->top, 0xF00021u);
        SelectObject(a2, v11);
      }
      DeleteObject(v10);
    }
  }
}

```

## disassembly

```asm
0x180070100  push    rbx
0x180070102  push    rbp
0x180070103  push    rsi
0x180070104  push    rdi
0x180070105  sub     rsp, 38h
0x180070109  mov     rsi, rdx
0x18007010c  mov     rdi, r8
0x18007010f  mov     rdx, rcx
0x180070112  add     rcx, 0D0h; this
0x180070119  call    ?IsCompositionEnabledForWindow@ChildWindowCompositionHelper@UIBase@@QEBA_NXZ; UIBase::ChildWindowCompositionHelper::IsCompositionEnabledForWindow(void)
0x18007011e  test    al, al
0x180070120  jnz     short loc_180070191
0x180070122  mov     rcx, rdx; this
0x180070125  call    ?GetPaneBackgroundColor@NavigationPane@@AEAAKXZ; NavigationPane::GetPaneBackgroundColor(void)
0x18007012a  mov     ecx, eax; color
0x18007012c  call    cs:__imp_CreateSolidBrush
0x180070132  mov     rbx, rax
0x180070135  test    rax, rax
0x180070138  jz      loc_1800701BE
0x18007013e  mov     rdx, rax; h
0x180070141  mov     rcx, rsi; hdc
0x180070144  call    cs:__imp_SelectObject
0x18007014a  mov     rbp, rax
0x18007014d  test    rax, rax
0x180070150  jz      short loc_180070186
0x180070152  mov     ecx, [rdi+0Ch]
0x180070155  mov     r8d, [rdi+4]; y
0x180070159  sub     ecx, r8d
0x18007015c  mov     r9d, [rdi+8]
0x180070160  sub     r9d, [rdi]; w
0x180070163  mov     edx, [rdi]; x
0x180070165  mov     [rsp+58h+rop], 0F00021h; rop
0x18007016d  mov     [rsp+58h+h], ecx; h
0x180070171  mov     rcx, rsi; hdc
0x180070174  call    cs:__imp_PatBlt
0x18007017a  mov     rdx, rbp; h
0x18007017d  mov     rcx, rsi; hdc
0x180070180  call    cs:__imp_SelectObject
0x180070186  mov     rcx, rbx; ho
0x180070189  call    cs:__imp_DeleteObject
0x18007018f  jmp     short loc_1800701BE
0x180070191  test    r9b, r9b
0x180070194  jz      short loc_1800701BE
0x180070196  mov     eax, [rdi+0Ch]
0x180070199  mov     rcx, rsi; hdc
0x18007019c  mov     r8d, [r8+4]; y
0x1800701a0  sub     eax, r8d
0x1800701a3  mov     r9d, [rdi+8]
0x1800701a7  sub     r9d, [rdi]; w
0x1800701aa  mov     edx, [rdi]; x
0x1800701ac  mov     [rsp+58h+rop], 42h ; 'B'; rop
0x1800701b4  mov     [rsp+58h+h], eax; h
0x1800701b8  call    cs:__imp_PatBlt
0x1800701be  add     rsp, 38h
0x1800701c2  pop     rdi
0x1800701c3  pop     rsi
0x1800701c4  pop     rbp
0x1800701c5  pop     rbx
0x1800701c6  retn
```
