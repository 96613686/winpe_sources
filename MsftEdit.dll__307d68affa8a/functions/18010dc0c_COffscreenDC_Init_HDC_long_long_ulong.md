# COffscreenDC::Init(HDC__ *,long,long,ulong)

- ea: `0x18010dc0c`
- end: `0x18010dca7`
- name: `?Init@COffscreenDC@@QEAAPEAUHDC__@@PEAU2@JJK@Z`
- size: `155`
- prototype: `HDC __fastcall(COffscreenDC *__hidden this, HDC hdc, int cx, int cy, COLORREF color)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800fdfa8`
- `0x1801304b4`

## callees

- `0x18006dd50`
- `0x18010dc0c`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18010dc3c`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18010dc3c`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18010dc68`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18010dc68`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkColor` at `0x18010dc7e`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkColor` at `0x18010dc7e`
- `ext-ms-win-gdi-draw-l1-1-0!CreateCompatibleBitmap` at `0x18010dc53`
- `ext-ms-win-gdi-draw-l1-1-0!CreateCompatibleBitmap` at `0x18010dc53`

## pseudocode

```c
HDC __fastcall COffscreenDC::Init(COffscreenDC *this, HDC hdc, int cx, int cy, COLORREF color)
{
  HDC result; // rax
  __int64 v10; // rdi
  HDC CompatibleDC; // rax
  __int64 v12; // rdx
  int v13; // r8d
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v15; // rax

  result = *(HDC *)this;
  if ( !*(_QWORD *)this )
  {
    v10 = 0;
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 3) = 0;
    CompatibleDC = CreateCompatibleDC(hdc);
    *(_QWORD *)this = CompatibleDC;
    if ( !CompatibleDC
      || (CompatibleBitmap = CreateCompatibleBitmap(hdc, cx, cy), (*((_QWORD *)this + 2) = CompatibleBitmap) == 0)
      || (v15 = SelectObject(*(HDC *)this, CompatibleBitmap), (*((_QWORD *)this + 1) = v15) == 0)
      || SetBkColor(*(HDC *)this, color) == -1
      || (v10 = *(_QWORD *)this) == 0 )
    {
      COffscreenDC::FreeData(this, v12, v13);
    }
    return (HDC)v10;
  }
  return result;
}

```

## disassembly

```asm
0x18010dc0c  push    rbx
0x18010dc0e  push    rbp
0x18010dc0f  push    rsi
0x18010dc10  push    rdi
0x18010dc11  push    r14
0x18010dc13  sub     rsp, 20h
0x18010dc17  mov     rax, [rcx]
0x18010dc1a  mov     ebp, r9d
0x18010dc1d  mov     r14d, r8d
0x18010dc20  mov     rsi, rdx
0x18010dc23  mov     rbx, rcx
0x18010dc26  test    rax, rax
0x18010dc29  jnz     short loc_18010DC9C
0x18010dc2b  xor     edi, edi
0x18010dc2d  mov     [rcx+8], rdi
0x18010dc31  mov     [rcx+10h], rdi
0x18010dc35  mov     [rcx+18h], rdi
0x18010dc39  mov     rcx, rdx; hdc
0x18010dc3c  call    cs:__imp_CreateCompatibleDC
0x18010dc42  mov     [rbx], rax
0x18010dc45  test    rax, rax
0x18010dc48  jz      short loc_18010DC91
0x18010dc4a  mov     r8d, ebp; cy
0x18010dc4d  mov     edx, r14d; cx
0x18010dc50  mov     rcx, rsi; hdc
0x18010dc53  call    cs:__imp_CreateCompatibleBitmap
0x18010dc59  mov     [rbx+10h], rax
0x18010dc5d  test    rax, rax
0x18010dc60  jz      short loc_18010DC91
0x18010dc62  mov     rcx, [rbx]; hdc
0x18010dc65  mov     rdx, rax; h
0x18010dc68  call    cs:__imp_SelectObject
0x18010dc6e  mov     [rbx+8], rax
0x18010dc72  test    rax, rax
0x18010dc75  jz      short loc_18010DC91
0x18010dc77  mov     edx, [rsp+48h+color]; color
0x18010dc7b  mov     rcx, [rbx]; hdc
0x18010dc7e  call    cs:__imp_SetBkColor
0x18010dc84  cmp     eax, 0FFFFFFFFh
0x18010dc87  jz      short loc_18010DC91
0x18010dc89  mov     rdi, [rbx]
0x18010dc8c  test    rdi, rdi
0x18010dc8f  jnz     short loc_18010DC99
0x18010dc91  mov     rcx, rbx; this
0x18010dc94  call    ?FreeData@COffscreenDC@@AEAAXXZ; COffscreenDC::FreeData(void)
0x18010dc99  mov     rax, rdi
0x18010dc9c  add     rsp, 20h
0x18010dca0  pop     r14
0x18010dca2  pop     rdi
0x18010dca3  pop     rsi
0x18010dca4  pop     rbp
0x18010dca5  pop     rbx
0x18010dca6  retn
```
