# COleControl::ScrollWindow(int,int,tagRECT const *,tagRECT const *)

- ea: `0x1800c9e10`
- end: `0x1800c9f1c`
- name: `?ScrollWindow@COleControl@@QEAAXHHPEBUtagRECT@@0@Z`
- size: `268`
- prototype: `void __usercall(COleControl *__hidden this@<rcx>, int@<edx>, int@<r8d>, const struct tagRECT *@<r9>, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180040aa0`
- `0x1800c9e10`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `USER32!OffsetRect` at `0x1800c9e9f`
- `USER32!OffsetRect` at `0x1800c9ec6`
- `USER32!OffsetRect` at `0x1800c9e9f`
- `USER32!OffsetRect` at `0x1800c9ec6`
- `USER32!CopyRect` at `0x1800c9e8e`
- `USER32!CopyRect` at `0x1800c9eb5`
- `USER32!CopyRect` at `0x1800c9e8e`
- `USER32!CopyRect` at `0x1800c9eb5`

## pseudocode

```c
void __fastcall COleControl::ScrollWindow(
        COleControl *this,
        unsigned int a2,
        unsigned int a3,
        struct tagRECT *a4,
        struct tagRECT *lprcSrc)
{
  struct tagRECT *p_rc; // rbx
  struct tagRECT *p_rcDst; // rdi
  _QWORD *v10; // rax
  int dy[2]; // [rsp+30h] [rbp-38h] BYREF
  struct tagRECT rcDst; // [rsp+38h] [rbp-30h] BYREF
  struct tagRECT rc; // [rsp+48h] [rbp-20h] BYREF

  p_rc = lprcSrc;
  p_rcDst = a4;
  if ( (*((_DWORD *)this + 62) & 0x400400) == 0x400400 )
  {
    if ( a4 || lprcSrc )
    {
      v10 = *(_QWORD **)this;
      *(_QWORD *)dy = 0;
      ((void (__fastcall *)(COleControl *, char *, int *))v10[108])(this, (char *)this + 184, dy);
      if ( p_rcDst )
      {
        CopyRect(&rcDst, p_rcDst);
        OffsetRect(&rcDst, dy[0], dy[1]);
        p_rcDst = &rcDst;
      }
      if ( lprcSrc )
      {
        CopyRect(&rc, lprcSrc);
        OffsetRect(&rc, dy[0], dy[1]);
        p_rc = &rc;
      }
    }
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, struct tagRECT *, struct tagRECT *))(**((_QWORD **)this + 47) + 216LL))(
      *((_QWORD *)this + 47),
      a2,
      a3,
      p_rcDst,
      p_rc);
  }
  else
  {
    CWnd::ScrollWindow(this, a2, a3, a4, lprcSrc);
  }
}

```

## disassembly

```asm
0x1800c9e10  push    rbp
0x1800c9e12  push    rbx
0x1800c9e13  push    rsi
0x1800c9e14  push    rdi
0x1800c9e15  push    r14
0x1800c9e17  push    r15
0x1800c9e19  mov     rbp, rsp
0x1800c9e1c  sub     rsp, 68h
0x1800c9e20  mov     rax, cs:__security_cookie
0x1800c9e27  xor     rax, rsp
0x1800c9e2a  mov     [rbp+var_10], rax
0x1800c9e2e  mov     eax, [rcx+0F8h]
0x1800c9e34  mov     rsi, rcx
0x1800c9e37  mov     rbx, [rbp+lprcSrc]
0x1800c9e3b  mov     ecx, 400400h
0x1800c9e40  and     eax, ecx
0x1800c9e42  mov     rdi, r9
0x1800c9e45  mov     r15d, r8d
0x1800c9e48  mov     r14d, edx
0x1800c9e4b  cmp     eax, ecx
0x1800c9e4d  jnz     loc_1800C9EF6
0x1800c9e53  test    r9, r9
0x1800c9e56  jnz     short loc_1800C9E5D
0x1800c9e58  test    rbx, rbx
0x1800c9e5b  jz      short loc_1800C9ED0
0x1800c9e5d  mov     rax, [rsi]
0x1800c9e60  lea     rdx, [rsi+0B8h]
0x1800c9e67  lea     r8, [rbp+dy]
0x1800c9e6b  mov     qword ptr [rbp+dy], 0
0x1800c9e73  mov     rcx, rsi
0x1800c9e76  mov     rax, [rax+360h]
0x1800c9e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9e82  test    rdi, rdi
0x1800c9e85  jz      short loc_1800C9EA9
0x1800c9e87  mov     rdx, rdi; lprcSrc
0x1800c9e8a  lea     rcx, [rbp+rcDst]; lprcDst
0x1800c9e8e  call    cs:__imp_CopyRect
0x1800c9e94  mov     r8d, [rbp+dy+4]; dy
0x1800c9e98  lea     rcx, [rbp+rcDst]; lprc
0x1800c9e9c  mov     edx, [rbp+dy]; dx
0x1800c9e9f  call    cs:__imp_OffsetRect
0x1800c9ea5  lea     rdi, [rbp+rcDst]
0x1800c9ea9  test    rbx, rbx
0x1800c9eac  jz      short loc_1800C9ED0
0x1800c9eae  mov     rdx, rbx; lprcSrc
0x1800c9eb1  lea     rcx, [rbp+rc]; lprcDst
0x1800c9eb5  call    cs:__imp_CopyRect
0x1800c9ebb  mov     r8d, [rbp+dy+4]; dy
0x1800c9ebf  lea     rcx, [rbp+rc]; lprc
0x1800c9ec3  mov     edx, [rbp+dy]; dx
0x1800c9ec6  call    cs:__imp_OffsetRect
0x1800c9ecc  lea     rbx, [rbp+rc]
0x1800c9ed0  mov     rcx, [rsi+178h]
0x1800c9ed7  mov     r9, rdi
0x1800c9eda  mov     r8d, r15d
0x1800c9edd  mov     [rsp+68h+var_48], rbx
0x1800c9ee2  mov     edx, r14d
0x1800c9ee5  mov     rax, [rcx]
0x1800c9ee8  mov     rax, [rax+0D8h]
0x1800c9eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9ef4  jmp     short loc_1800C9F03
0x1800c9ef6  mov     rcx, rsi; this
0x1800c9ef9  mov     [rsp+68h+var_48], rbx; RECT *
0x1800c9efe  call    ?ScrollWindow@CWnd@@QEAAXHHPEBUtagRECT@@0@Z; CWnd::ScrollWindow(int,int,tagRECT const *,tagRECT const *)
0x1800c9f03  mov     rcx, [rbp+var_10]
0x1800c9f07  xor     rcx, rsp; StackCookie
0x1800c9f0a  call    __security_check_cookie
0x1800c9f0f  add     rsp, 68h
0x1800c9f13  pop     r15
0x1800c9f15  pop     r14
0x1800c9f17  pop     rdi
0x1800c9f18  pop     rsi
0x1800c9f19  pop     rbx
0x1800c9f1a  pop     rbp
0x1800c9f1b  retn
```
