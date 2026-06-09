# CCmbBxWinHost::SetDropSize(tagRECT *)

- ea: `0x1800503fc`
- end: `0x18005048b`
- name: `?SetDropSize@CCmbBxWinHost@@IEAAXPEAUtagRECT@@@Z`
- size: `143`
- prototype: `void __fastcall(CCmbBxWinHost *__hidden this, struct tagRECT *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18004e640`
- `0x18004f540`

## callees

- `0x18004de00`

## import_xrefs

- `USER32!MoveWindow` at `0x18005047a`
- `USER32!MoveWindow` at `0x18005047a`
- `USER32!ClientToScreen` at `0x180050439`
- `USER32!ClientToScreen` at `0x180050448`
- `USER32!ClientToScreen` at `0x180050439`
- `USER32!ClientToScreen` at `0x180050448`

## pseudocode

```c
void __fastcall CCmbBxWinHost::SetDropSize(CCmbBxWinHost *this, struct tagRECT *a2)
{
  HWND v4; // rcx
  struct tagPOINT v5; // [rsp+40h] [rbp+8h] BYREF
  struct tagPOINT Point; // [rsp+48h] [rbp+10h] BYREF

  *((_DWORD *)this + 30) |= 2u;
  CCmbBxWinHost::HideListBox(this, 0, 0);
  v4 = (HWND)*((_QWORD *)this + 2);
  Point = *(struct tagPOINT *)&a2->left;
  v5 = *(struct tagPOINT *)&a2->right;
  ClientToScreen(v4, &Point);
  ClientToScreen(*((HWND *)this + 2), &v5);
  MoveWindow(*((HWND *)this + 16), Point.x, Point.y, v5.x - Point.x, v5.y - Point.y, 0);
}

```

## disassembly

```asm
0x1800503fc  mov     [rsp+arg_10], rbx
0x180050401  push    rdi
0x180050402  sub     rsp, 30h
0x180050406  or      dword ptr [rcx+78h], 2
0x18005040a  mov     rbx, rdx
0x18005040d  xor     edx, edx; int
0x18005040f  xor     r8d, r8d; int
0x180050412  mov     rdi, rcx
0x180050415  call    ?HideListBox@CCmbBxWinHost@@QEAAHHH@Z; CCmbBxWinHost::HideListBox(int,int)
0x18005041a  mov     rax, [rbx]
0x18005041d  lea     rdx, [rsp+38h+Point]; lpPoint
0x180050422  mov     rcx, [rdi+10h]; hWnd
0x180050426  mov     qword ptr [rsp+38h+Point.x], rax
0x18005042b  mov     eax, [rbx+8]
0x18005042e  mov     [rsp+38h+arg_0.x], eax
0x180050432  mov     eax, [rbx+0Ch]
0x180050435  mov     [rsp+38h+arg_0.y], eax
0x180050439  call    cs:__imp_ClientToScreen
0x18005043f  mov     rcx, [rdi+10h]; hWnd
0x180050443  lea     rdx, [rsp+38h+arg_0]; lpPoint
0x180050448  call    cs:__imp_ClientToScreen
0x18005044e  mov     eax, [rsp+38h+arg_0.y]
0x180050452  mov     r8d, [rsp+38h+Point.y]; Y
0x180050457  sub     eax, r8d
0x18005045a  mov     r9d, [rsp+38h+arg_0.x]
0x18005045f  mov     rdx, qword ptr [rsp+38h+Point.x]; X
0x180050464  mov     rcx, [rdi+80h]; hWnd
0x18005046b  sub     r9d, edx; nWidth
0x18005046e  mov     [rsp+38h+bRepaint], 0; bRepaint
0x180050476  mov     [rsp+38h+nHeight], eax; nHeight
0x18005047a  call    cs:__imp_MoveWindow
0x180050480  mov     rbx, [rsp+38h+arg_10]
0x180050485  add     rsp, 30h
0x180050489  pop     rdi
0x18005048a  retn
```
