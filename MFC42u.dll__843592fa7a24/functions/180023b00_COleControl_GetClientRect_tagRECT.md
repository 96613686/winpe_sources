# COleControl::GetClientRect(tagRECT *)

- ea: `0x180023b00`
- end: `0x180023baf`
- name: `?GetClientRect@COleControl@@UEBAXPEAUtagRECT@@@Z`
- size: `175`
- prototype: `void(COleControl *__hidden this, struct tagRECT *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180023b00`
- `0x1800d7010`

## import_xrefs

- `USER32!OffsetRect` at `0x180023ba7`
- `USER32!OffsetRect` at `0x180023ba7`
- `USER32!GetClientRect` at `0x180023b2a`
- `USER32!GetClientRect` at `0x180023b2a`
- `USER32!CopyRect` at `0x180023b7c`
- `USER32!CopyRect` at `0x180023b7c`
- `USER32!SetRectEmpty` at `0x180023b3e`
- `USER32!SetRectEmpty` at `0x180023b3e`
- `USER32!InflateRect` at `0x180023b93`
- `USER32!InflateRect` at `0x180023b93`

## pseudocode

```c
void __fastcall COleControl::GetClientRect(COleControl *this, struct tagRECT *a2)
{
  HWND v4; // rcx
  __int64 v5; // rax
  int v6; // [rsp+30h] [rbp+8h] BYREF
  int v7; // [rsp+40h] [rbp+18h] BYREF

  if ( (*((_DWORD *)this + 62) & 0x400400) == 0x400400 )
  {
    v5 = *(_QWORD *)this;
    v7 = 0;
    v6 = 0;
    (*(void (__fastcall **)(COleControl *, int *, int *))(v5 + 848))(this, &v7, &v6);
    CopyRect(a2, (const RECT *)((char *)this + 184));
    InflateRect(a2, -v7, -v6);
    OffsetRect(a2, -a2->left, -a2->top);
  }
  else
  {
    v4 = (HWND)*((_QWORD *)this + 8);
    if ( v4 )
      GetClientRect(v4, a2);
    else
      SetRectEmpty(a2);
  }
}

```

## disassembly

```asm
0x180023b00  mov     [rsp+arg_8], rbx
0x180023b05  push    rdi
0x180023b06  sub     rsp, 20h
0x180023b0a  mov     eax, [rcx+0F8h]
0x180023b10  mov     rdi, rcx
0x180023b13  mov     ecx, 400400h
0x180023b18  mov     rbx, rdx
0x180023b1b  and     eax, ecx
0x180023b1d  cmp     eax, ecx
0x180023b1f  jz      short loc_180023B46
0x180023b21  mov     rcx, [rdi+40h]; hWnd
0x180023b25  test    rcx, rcx
0x180023b28  jz      short loc_180023B3B
0x180023b2a  call    cs:__imp_GetClientRect
0x180023b30  mov     rbx, [rsp+28h+arg_8]
0x180023b35  add     rsp, 20h
0x180023b39  pop     rdi
0x180023b3a  retn
0x180023b3b  mov     rcx, rbx; lprc
0x180023b3e  call    cs:__imp_SetRectEmpty
0x180023b44  jmp     short loc_180023B30
0x180023b46  mov     rax, [rdi]
0x180023b49  lea     r8, [rsp+28h+arg_0]
0x180023b4e  lea     rdx, [rsp+28h+arg_10]
0x180023b53  mov     [rsp+28h+arg_10], 0
0x180023b5b  mov     rcx, rdi
0x180023b5e  mov     [rsp+28h+arg_0], 0
0x180023b66  mov     rax, [rax+350h]
0x180023b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b72  lea     rdx, [rdi+0B8h]; lprcSrc
0x180023b79  mov     rcx, rbx; lprcDst
0x180023b7c  call    cs:__imp_CopyRect
0x180023b82  mov     r8d, [rsp+28h+arg_0]
0x180023b87  mov     rcx, rbx; lprc
0x180023b8a  mov     edx, [rsp+28h+arg_10]
0x180023b8e  neg     r8d; dy
0x180023b91  neg     edx; dx
0x180023b93  call    cs:__imp_InflateRect
0x180023b99  mov     r8d, [rbx+4]
0x180023b9d  mov     rcx, rbx; lprc
0x180023ba0  mov     edx, [rbx]
0x180023ba2  neg     r8d; dy
0x180023ba5  neg     edx; dx
0x180023ba7  call    cs:__imp_OffsetRect
0x180023bad  jmp     short loc_180023B30
```
