# DpContext::CleanTheHdc(HDC__ *)

- ea: `0x18003d33c`
- end: `0x18003d4fb`
- name: `?CleanTheHdc@DpContext@@QEAAXPEAUHDC__@@@Z`
- size: `447`
- prototype: `void(DpContext *__hidden this, HDC)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e098`
- `0x180010258`
- `0x18003d260`
- `0x18003dbc0`

## callees

- `0x18003d33c`

## import_xrefs

- `GDI32!GetClipRgn` at `0x18003d495`
- `GDI32!GetClipRgn` at `0x18003d495`
- `GDI32!ModifyWorldTransform` at `0x18003d3bf`
- `GDI32!ModifyWorldTransform` at `0x18003d3bf`
- `GDI32!SetROP2` at `0x18003d3b1`
- `GDI32!SetROP2` at `0x18003d4f3`
- `GDI32!SetROP2` at `0x18003d3b1`
- `GDI32!SetROP2` at `0x18003d4f3`
- `GDI32!GetROP2` at `0x18003d449`
- `GDI32!GetROP2` at `0x18003d449`
- `GDI32!GetWindowOrgEx` at `0x18003d430`
- `GDI32!GetWindowOrgEx` at `0x18003d430`
- `GDI32!GetMapMode` at `0x18003d3e7`
- `GDI32!GetMapMode` at `0x18003d3e7`
- `GDI32!SelectClipRgn` at `0x18003d3ca`
- `GDI32!SelectClipRgn` at `0x18003d3ca`
- `GDI32!SetViewportOrgEx` at `0x18003d392`
- `GDI32!SetViewportOrgEx` at `0x18003d4d0`
- `GDI32!SetViewportOrgEx` at `0x18003d392`
- `GDI32!SetViewportOrgEx` at `0x18003d4d0`
- `GDI32!SetWindowOrgEx` at `0x18003d3a3`
- `GDI32!SetWindowOrgEx` at `0x18003d4e3`
- `GDI32!SetWindowOrgEx` at `0x18003d3a3`
- `GDI32!SetWindowOrgEx` at `0x18003d4e3`
- `GDI32!SetMapMode` at `0x18003d381`
- `GDI32!SetMapMode` at `0x18003d4bd`
- `GDI32!SetMapMode` at `0x18003d381`
- `GDI32!SetMapMode` at `0x18003d4bd`
- `GDI32!DeleteObject` at `0x18003d4a6`
- `GDI32!DeleteObject` at `0x18003d4a6`
- `GDI32!GetViewportOrgEx` at `0x18003d401`
- `GDI32!GetViewportOrgEx` at `0x18003d401`
- `GDI32!CreateRectRgn` at `0x18003d45c`
- `GDI32!CreateRectRgn` at `0x18003d45c`
- `GDI32!SetICMMode` at `0x18003d36d`
- `GDI32!SetICMMode` at `0x18003d36d`

## pseudocode

```c
void __fastcall DpContext::CleanTheHdc(DpContext *this, HDC a2)
{
  BOOL v2; // ebp
  bool v4; // zf
  int v7; // edx
  int MapMode; // eax
  int v9; // r15d
  BOOL v10; // esi
  BOOL v11; // edi
  int ROP2; // r12d
  HRGN RectRgn; // rax
  HRGN v14; // r14
  struct tagPOINT point; // [rsp+50h] [rbp+8h] BYREF

  v2 = 1;
  v4 = *((_DWORD *)this + 160) == 1;
  v7 = 2;
  if ( !v4 )
    v7 = 1;
  SetICMMode(a2, v7);
  if ( !*((_DWORD *)this + 161) )
  {
    SetMapMode(a2, 1);
    SetViewportOrgEx(a2, 0, 0, 0);
    SetWindowOrgEx(a2, 0, 0, 0);
    SetROP2(a2, 13);
    ModifyWorldTransform(a2, 0, 1u);
LABEL_5:
    SelectClipRgn(a2, 0);
    return;
  }
  MapMode = GetMapMode(a2);
  point = 0;
  v9 = MapMode;
  GetViewportOrgEx(a2, &point);
  v10 = point != 0;
  point = 0;
  GetWindowOrgEx(a2, &point);
  v11 = point != 0;
  ROP2 = GetROP2(a2);
  RectRgn = CreateRectRgn(0, 0, 0, 0);
  v14 = RectRgn;
  if ( RectRgn )
  {
    v2 = GetClipRgn(a2, RectRgn) != 0;
    DeleteObject(v14);
  }
  if ( v9 != 1 )
    SetMapMode(a2, 1);
  if ( v10 )
    SetViewportOrgEx(a2, 0, 0, 0);
  if ( v11 )
    SetWindowOrgEx(a2, 0, 0, 0);
  if ( ROP2 != 13 )
    SetROP2(a2, 13);
  if ( v2 )
    goto LABEL_5;
}

```

## disassembly

```asm
0x18003d33c  mov     [rsp+arg_8], rbx
0x18003d341  mov     [rsp+arg_10], rbp
0x18003d346  push    rsi
0x18003d347  push    rdi
0x18003d348  push    r12
0x18003d34a  push    r14
0x18003d34c  push    r15
0x18003d34e  sub     rsp, 20h
0x18003d352  mov     ebp, 1
0x18003d357  mov     rdi, rcx
0x18003d35a  cmp     [rcx+280h], ebp
0x18003d360  mov     rbx, rdx
0x18003d363  mov     rcx, rdx; hdc
0x18003d366  lea     edx, [rbp+1]
0x18003d369  jz      short loc_18003D36D
0x18003d36b  mov     edx, ebp; mode
0x18003d36d  call    cs:__imp_SetICMMode
0x18003d373  cmp     dword ptr [rdi+284h], 0
0x18003d37a  mov     rcx, rbx; hdc
0x18003d37d  jnz     short loc_18003D3E7
0x18003d37f  mov     edx, ebp; iMode
0x18003d381  call    cs:__imp_SetMapMode
0x18003d387  xor     r9d, r9d; lppt
0x18003d38a  xor     r8d, r8d; y
0x18003d38d  xor     edx, edx; x
0x18003d38f  mov     rcx, rbx; hdc
0x18003d392  call    cs:__imp_SetViewportOrgEx
0x18003d398  xor     r9d, r9d; lppt
0x18003d39b  xor     r8d, r8d; y
0x18003d39e  xor     edx, edx; x
0x18003d3a0  mov     rcx, rbx; hdc
0x18003d3a3  call    cs:__imp_SetWindowOrgEx
0x18003d3a9  mov     edx, 0Dh; rop2
0x18003d3ae  mov     rcx, rbx; hdc
0x18003d3b1  call    cs:__imp_SetROP2
0x18003d3b7  mov     r8d, ebp; mode
0x18003d3ba  xor     edx, edx; lpxf
0x18003d3bc  mov     rcx, rbx; hdc
0x18003d3bf  call    cs:__imp_ModifyWorldTransform
0x18003d3c5  xor     edx, edx; hrgn
0x18003d3c7  mov     rcx, rbx; hdc
0x18003d3ca  call    cs:__imp_SelectClipRgn
0x18003d3d0  mov     rbx, [rsp+48h+arg_8]
0x18003d3d5  mov     rbp, [rsp+48h+arg_10]
0x18003d3da  add     rsp, 20h
0x18003d3de  pop     r15
0x18003d3e0  pop     r14
0x18003d3e2  pop     r12
0x18003d3e4  pop     rdi
0x18003d3e5  pop     rsi
0x18003d3e6  retn
0x18003d3e7  call    cs:__imp_GetMapMode
0x18003d3ed  lea     rdx, [rsp+48h+point]; lppoint
0x18003d3f2  mov     qword ptr [rsp+48h+point.x], 0
0x18003d3fb  mov     rcx, rbx; hdc
0x18003d3fe  mov     r15d, eax
0x18003d401  call    cs:__imp_GetViewportOrgEx
0x18003d407  cmp     [rsp+48h+point.x], 0
0x18003d40c  jnz     loc_18003D4AE
0x18003d412  cmp     [rsp+48h+point.y], 0
0x18003d417  jnz     loc_18003D4AE
0x18003d41d  xor     esi, esi
0x18003d41f  lea     rdx, [rsp+48h+point]; lppoint
0x18003d424  mov     qword ptr [rsp+48h+point.x], 0
0x18003d42d  mov     rcx, rbx; hdc
0x18003d430  call    cs:__imp_GetWindowOrgEx
0x18003d436  cmp     [rsp+48h+point.x], 0
0x18003d43b  jnz     short loc_18003D48B
0x18003d43d  cmp     [rsp+48h+point.y], 0
0x18003d442  jnz     short loc_18003D48B
0x18003d444  xor     edi, edi
0x18003d446  mov     rcx, rbx; hdc
0x18003d449  call    cs:__imp_GetROP2
0x18003d44f  xor     r9d, r9d; y2
0x18003d452  xor     r8d, r8d; x2
0x18003d455  xor     edx, edx; y1
0x18003d457  xor     ecx, ecx; x1
0x18003d459  mov     r12d, eax
0x18003d45c  call    cs:__imp_CreateRectRgn
0x18003d462  mov     r14, rax
0x18003d465  test    rax, rax
0x18003d468  jnz     short loc_18003D48F
0x18003d46a  cmp     r15d, 1
0x18003d46e  jnz     short loc_18003D4B5
0x18003d470  test    esi, esi
0x18003d472  jnz     short loc_18003D4C5
0x18003d474  test    edi, edi
0x18003d476  jnz     short loc_18003D4D8
0x18003d478  cmp     r12d, 0Dh
0x18003d47c  jnz     short loc_18003D4EB
0x18003d47e  test    ebp, ebp
0x18003d480  jnz     loc_18003D3C5
0x18003d486  jmp     loc_18003D3D0
0x18003d48b  mov     edi, ebp
0x18003d48d  jmp     short loc_18003D446
0x18003d48f  mov     rdx, r14; hrgn
0x18003d492  mov     rcx, rbx; hdc
0x18003d495  call    cs:__imp_GetClipRgn
0x18003d49b  xor     ebp, ebp
0x18003d49d  mov     rcx, r14; ho
0x18003d4a0  test    eax, eax
0x18003d4a2  setnz   bpl
0x18003d4a6  call    cs:__imp_DeleteObject
0x18003d4ac  jmp     short loc_18003D46A
0x18003d4ae  mov     esi, ebp
0x18003d4b0  jmp     loc_18003D41F
0x18003d4b5  mov     edx, 1; iMode
0x18003d4ba  mov     rcx, rbx; hdc
0x18003d4bd  call    cs:__imp_SetMapMode
0x18003d4c3  jmp     short loc_18003D470
0x18003d4c5  xor     r9d, r9d; lppt
0x18003d4c8  xor     r8d, r8d; y
0x18003d4cb  xor     edx, edx; x
0x18003d4cd  mov     rcx, rbx; hdc
0x18003d4d0  call    cs:__imp_SetViewportOrgEx
0x18003d4d6  jmp     short loc_18003D474
0x18003d4d8  xor     r9d, r9d; lppt
0x18003d4db  xor     r8d, r8d; y
0x18003d4de  xor     edx, edx; x
0x18003d4e0  mov     rcx, rbx; hdc
0x18003d4e3  call    cs:__imp_SetWindowOrgEx
0x18003d4e9  jmp     short loc_18003D478
0x18003d4eb  mov     edx, 0Dh; rop2
0x18003d4f0  mov     rcx, rbx; hdc
0x18003d4f3  call    cs:__imp_SetROP2
0x18003d4f9  jmp     short loc_18003D47E
```
