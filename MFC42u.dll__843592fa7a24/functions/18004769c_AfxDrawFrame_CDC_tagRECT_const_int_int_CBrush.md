# _AfxDrawFrame(CDC *,tagRECT const *,int,int,CBrush &)

- ea: `0x18004769c`
- end: `0x18004779c`
- name: `?_AfxDrawFrame@@YAXPEAVCDC@@PEBUtagRECT@@HHAEAVCBrush@@@Z`
- size: `256`
- prototype: `void(struct CDC *, const struct tagRECT *, int, int, struct CBrush *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180046e80`

## callees

- `0x18004769c`
- `0x1800d1fe0`

## import_xrefs

- `USER32!CopyRect` at `0x1800476ce`
- `USER32!CopyRect` at `0x180047728`
- `USER32!CopyRect` at `0x1800476ce`
- `USER32!CopyRect` at `0x180047728`
- `USER32!FillRect` at `0x1800476f3`
- `USER32!FillRect` at `0x18004771b`
- `USER32!FillRect` at `0x180047755`
- `USER32!FillRect` at `0x18004777d`
- `USER32!FillRect` at `0x1800476f3`
- `USER32!FillRect` at `0x18004771b`
- `USER32!FillRect` at `0x180047755`
- `USER32!FillRect` at `0x18004777d`

## pseudocode

```c
void __fastcall _AfxDrawFrame(HDC *a1, const struct tagRECT *a2, int a3, int a4, struct CBrush *a5)
{
  HBRUSH v9; // r8
  HBRUSH v10; // r8
  HBRUSH v11; // r8
  HBRUSH v12; // r8
  struct tagRECT rcDst; // [rsp+20h] [rbp-28h] BYREF

  CopyRect(&rcDst, a2);
  rcDst.right = a3 + rcDst.left;
  if ( a5 )
    v9 = (HBRUSH)*((_QWORD *)a5 + 1);
  else
    v9 = 0;
  FillRect(a1[1], &rcDst, v9);
  rcDst.right = a2->right;
  rcDst.left = rcDst.right - a3;
  if ( a5 )
    v10 = (HBRUSH)*((_QWORD *)a5 + 1);
  else
    v10 = 0;
  FillRect(a1[1], &rcDst, v10);
  CopyRect(&rcDst, a2);
  rcDst.left += a3;
  rcDst.right -= a3;
  rcDst.bottom = a4 + rcDst.top;
  if ( a5 )
    v11 = (HBRUSH)*((_QWORD *)a5 + 1);
  else
    v11 = 0;
  FillRect(a1[1], &rcDst, v11);
  rcDst.bottom = a2->bottom;
  rcDst.top = rcDst.bottom - a4;
  if ( a5 )
    v12 = (HBRUSH)*((_QWORD *)a5 + 1);
  else
    v12 = 0;
  FillRect(a1[1], &rcDst, v12);
}

```

## disassembly

```asm
0x18004769c  push    rbp
0x18004769e  push    rbx
0x18004769f  push    rsi
0x1800476a0  push    rdi
0x1800476a1  push    r14
0x1800476a3  push    r15
0x1800476a5  mov     rbp, rsp
0x1800476a8  sub     rsp, 48h
0x1800476ac  mov     rax, cs:__security_cookie
0x1800476b3  xor     rax, rsp
0x1800476b6  mov     [rbp+var_18], rax
0x1800476ba  mov     rbx, [rbp+arg_20]
0x1800476be  mov     rdi, rcx
0x1800476c1  lea     rcx, [rbp+rcDst]; lprcDst
0x1800476c5  mov     r15d, r9d
0x1800476c8  mov     r14d, r8d
0x1800476cb  mov     rsi, rdx
0x1800476ce  call    cs:__imp_CopyRect
0x1800476d4  mov     ecx, [rbp+rcDst.left]
0x1800476d7  add     ecx, r14d
0x1800476da  mov     [rbp+rcDst.right], ecx
0x1800476dd  test    rbx, rbx
0x1800476e0  jnz     short loc_1800476E7
0x1800476e2  xor     r8d, r8d
0x1800476e5  jmp     short loc_1800476EB
0x1800476e7  mov     r8, [rbx+8]; hbr
0x1800476eb  mov     rcx, [rdi+8]; hDC
0x1800476ef  lea     rdx, [rbp+rcDst]; lprc
0x1800476f3  call    cs:__imp_FillRect
0x1800476f9  mov     eax, [rsi+8]
0x1800476fc  mov     [rbp+rcDst.right], eax
0x1800476ff  sub     eax, r14d
0x180047702  mov     [rbp+rcDst.left], eax
0x180047705  test    rbx, rbx
0x180047708  jnz     short loc_18004770F
0x18004770a  xor     r8d, r8d
0x18004770d  jmp     short loc_180047713
0x18004770f  mov     r8, [rbx+8]; hbr
0x180047713  mov     rcx, [rdi+8]; hDC
0x180047717  lea     rdx, [rbp+rcDst]; lprc
0x18004771b  call    cs:__imp_FillRect
0x180047721  mov     rdx, rsi; lprcSrc
0x180047724  lea     rcx, [rbp+rcDst]; lprcDst
0x180047728  call    cs:__imp_CopyRect
0x18004772e  mov     ecx, [rbp+rcDst.top]
0x180047731  add     [rbp+rcDst.left], r14d
0x180047735  add     ecx, r15d
0x180047738  sub     [rbp+rcDst.right], r14d
0x18004773c  mov     [rbp+rcDst.bottom], ecx
0x18004773f  test    rbx, rbx
0x180047742  jnz     short loc_180047749
0x180047744  xor     r8d, r8d
0x180047747  jmp     short loc_18004774D
0x180047749  mov     r8, [rbx+8]; hbr
0x18004774d  mov     rcx, [rdi+8]; hDC
0x180047751  lea     rdx, [rbp+rcDst]; lprc
0x180047755  call    cs:__imp_FillRect
0x18004775b  mov     eax, [rsi+0Ch]
0x18004775e  mov     [rbp+rcDst.bottom], eax
0x180047761  sub     eax, r15d
0x180047764  mov     [rbp+rcDst.top], eax
0x180047767  test    rbx, rbx
0x18004776a  jnz     short loc_180047771
0x18004776c  xor     r8d, r8d
0x18004776f  jmp     short loc_180047775
0x180047771  mov     r8, [rbx+8]; hbr
0x180047775  mov     rcx, [rdi+8]; hDC
0x180047779  lea     rdx, [rbp+rcDst]; lprc
0x18004777d  call    cs:__imp_FillRect
0x180047783  mov     rcx, [rbp+var_18]
0x180047787  xor     rcx, rsp; StackCookie
0x18004778a  call    __security_check_cookie
0x18004778f  add     rsp, 48h
0x180047793  pop     r15
0x180047795  pop     r14
0x180047797  pop     rdi
0x180047798  pop     rsi
0x180047799  pop     rbx
0x18004779a  pop     rbp
0x18004779b  retn
```
