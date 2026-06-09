# CReBar::CalcFixedLayout(int,int)

- ea: `0x180050fa0`
- end: `0x1800511ca`
- name: `?CalcFixedLayout@CReBar@@UEAA?AVCSize@@HH@Z`
- size: `554`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180012d60`
- `0x18001cd40`
- `0x180024b80`
- `0x180050fa0`
- `0x1800d1f92`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `USER32!GetWindowLongW` at `0x18005107b`
- `USER32!GetWindowLongW` at `0x18005107b`
- `USER32!SetRectEmpty` at `0x1800510c2`
- `USER32!SetRectEmpty` at `0x180051140`
- `USER32!SetRectEmpty` at `0x1800510c2`
- `USER32!SetRectEmpty` at `0x180051140`
- `USER32!IsRectEmpty` at `0x180051132`
- `USER32!IsRectEmpty` at `0x180051132`
- `USER32!UnionRect` at `0x180051124`
- `USER32!UnionRect` at `0x180051124`

## pseudocode

```c
int *__fastcall CReBar::CalcFixedLayout(CControlBar *a1, int *a2, int a3, int a4)
{
  int v8; // edi
  int v9; // r15d
  __int64 v10; // rax
  struct CObject *v11; // rax
  struct CObject *v12; // rax
  signed int v13; // ecx
  __int64 v14; // rax
  LONG right; // edx
  LONG bottom; // ecx
  int v17; // ecx
  int v18; // eax
  int *result; // rax
  int v20; // [rsp+30h] [rbp-79h] BYREF
  int v21; // [rsp+34h] [rbp-75h] BYREF
  int v22; // [rsp+38h] [rbp-71h]
  HWND hWnd; // [rsp+58h] [rbp-51h]
  struct tagRECT rc; // [rsp+A0h] [rbp-9h] BYREF
  RECT rcSrc2; // [rsp+B0h] [rbp+7h] BYREF

  v8 = (*(__int64 (__fastcall **)(CControlBar *, __int64, _QWORD, _QWORD))(*(_QWORD *)a1 + 336LL))(a1, 1036, 0, 0);
  memset_0(&v21, 0, 0x6Cu);
  v20 = 112;
  v9 = v8;
  while ( v9 )
  {
    v10 = *(_QWORD *)a1;
    --v9;
    v21 = 17;
    (*(void (__fastcall **)(CControlBar *, __int64, _QWORD, int *))(v10 + 336))(a1, 1052, v9, &v20);
    v11 = CWnd::FromHandlePermanent(hWnd);
    v12 = AfxDynamicDownCast((struct CRuntimeClass *)&CControlBar::classCControlBar, v11);
    if ( v12 )
      v13 = (*(__int64 (__fastcall **)(struct CObject *))(*(_QWORD *)v12 + 416LL))(v12);
    else
      v13 = ((unsigned int)GetWindowLongW(hWnd, -16) >> 28) & 1;
    if ( v13 != ((v22 & 8) == 0) )
      (*(void (__fastcall **)(CControlBar *, __int64, _QWORD, _QWORD))(*(_QWORD *)a1 + 336LL))(a1, 1059, v9, v13);
  }
  SetRectEmpty(&rc);
  while ( v8 )
  {
    v14 = *(_QWORD *)a1;
    --v8;
    v21 = 1;
    (*(void (__fastcall **)(CControlBar *, __int64, _QWORD, int *))(v14 + 336))(a1, 1052, v8, &v20);
    if ( (v22 & 8) == 0 )
    {
      (*(void (__fastcall **)(CControlBar *, __int64, _QWORD, RECT *))(*(_QWORD *)a1 + 336LL))(a1, 1033, v8, &rcSrc2);
      UnionRect(&rc, &rc, &rcSrc2);
    }
  }
  if ( IsRectEmpty(&rc) )
  {
    bottom = rc.bottom;
    right = rc.right;
  }
  else
  {
    SetRectEmpty(&rcSrc2);
    CControlBar::CalcInsideRect(a1, (struct CRect *)&rcSrc2, a4);
    right = rcSrc2.left - rcSrc2.right + rc.right;
    bottom = rcSrc2.top - rcSrc2.bottom + rc.bottom;
  }
  if ( a4 || !a3 )
  {
    v17 = bottom - rc.top;
    if ( a4 && a3 )
    {
      v18 = 0x7FFF;
      goto LABEL_19;
    }
  }
  else
  {
    v17 = 0x7FFF;
  }
  v18 = right - rc.left;
LABEL_19:
  *a2 = v18;
  result = a2;
  a2[1] = v17;
  return result;
}

```

## disassembly

```asm
0x180050fa0  mov     [rsp-8+arg_10], rbx
0x180050fa5  push    rbp
0x180050fa6  push    rsi
0x180050fa7  push    rdi
0x180050fa8  push    r12
0x180050faa  push    r13
0x180050fac  push    r14
0x180050fae  push    r15
0x180050fb0  lea     rbp, [rsp-27h]
0x180050fb5  sub     rsp, 0D0h
0x180050fbc  mov     rax, cs:__security_cookie
0x180050fc3  xor     rax, rsp
0x180050fc6  mov     [rbp+57h+var_40], rax
0x180050fca  mov     rax, [rcx]
0x180050fcd  mov     r14d, r9d
0x180050fd0  mov     r12d, r8d
0x180050fd3  mov     rsi, rdx
0x180050fd6  xor     r9d, r9d
0x180050fd9  xor     r8d, r8d
0x180050fdc  mov     edx, 40Ch
0x180050fe1  mov     rbx, rcx
0x180050fe4  mov     rax, [rax+150h]
0x180050feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ff0  xor     edx, edx; Val
0x180050ff2  lea     rcx, [rbp+57h+var_CC]; void *
0x180050ff6  mov     rdi, rax
0x180050ff9  lea     r8d, [rdx+6Ch]; Size
0x180050ffd  call    memset_0
0x180051002  mov     [rbp+57h+var_D0], 70h ; 'p'
0x180051009  mov     r15d, edi
0x18005100c  test    edi, edi
0x18005100e  jz      loc_1800510BE
0x180051014  mov     rax, [rbx]
0x180051017  lea     r9, [rbp+57h+var_D0]
0x18005101b  dec     r15d
0x18005101e  mov     [rbp+57h+var_CC], 11h
0x180051025  movsxd  r13, r15d
0x180051028  mov     edx, 41Ch
0x18005102d  mov     r8, r13
0x180051030  mov     rcx, rbx
0x180051033  mov     rax, [rax+150h]
0x18005103a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005103f  mov     rcx, [rbp+57h+hWnd]; HWND
0x180051043  call    ?FromHandlePermanent@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandlePermanent(HWND__ *)
0x180051048  mov     rdx, rax; struct CObject *
0x18005104b  lea     rcx, ?classCControlBar@CControlBar@@2UCRuntimeClass@@B; struct CRuntimeClass *
0x180051052  call    ?AfxDynamicDownCast@@YAPEAVCObject@@PEAUCRuntimeClass@@PEAV1@@Z; AfxDynamicDownCast(CRuntimeClass *,CObject *)
0x180051057  mov     rcx, rax
0x18005105a  test    rax, rax
0x18005105d  jz      short loc_180051072
0x18005105f  mov     rax, [rax]
0x180051062  mov     rax, [rax+1A0h]
0x180051069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005106e  mov     ecx, eax
0x180051070  jmp     short loc_180051089
0x180051072  mov     rcx, [rbp+57h+hWnd]; hWnd
0x180051076  mov     edx, 0FFFFFFF0h; nIndex
0x18005107b  call    cs:__imp_GetWindowLongW
0x180051081  mov     ecx, eax
0x180051083  shr     ecx, 1Ch
0x180051086  and     ecx, 1
0x180051089  mov     eax, [rbp+57h+var_C8]
0x18005108c  shr     eax, 3
0x18005108f  not     eax
0x180051091  and     eax, 1
0x180051094  cmp     ecx, eax
0x180051096  jz      short loc_1800510B5
0x180051098  mov     rax, [rbx]
0x18005109b  mov     r8, r13
0x18005109e  movsxd  r9, ecx
0x1800510a1  mov     edx, 423h
0x1800510a6  mov     rcx, rbx
0x1800510a9  mov     rax, [rax+150h]
0x1800510b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510b5  test    r15d, r15d
0x1800510b8  jnz     loc_180051014
0x1800510be  lea     rcx, [rbp+57h+rc]; lprc
0x1800510c2  call    cs:__imp_SetRectEmpty
0x1800510c8  jmp     short loc_18005112A
0x1800510ca  mov     rax, [rbx]
0x1800510cd  lea     r9, [rbp+57h+var_D0]
0x1800510d1  dec     edi
0x1800510d3  mov     [rbp+57h+var_CC], 1
0x1800510da  movsxd  r15, edi
0x1800510dd  mov     edx, 41Ch
0x1800510e2  mov     r8, r15
0x1800510e5  mov     rcx, rbx
0x1800510e8  mov     rax, [rax+150h]
0x1800510ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510f4  test    byte ptr [rbp+57h+var_C8], 8
0x1800510f8  jnz     short loc_18005112A
0x1800510fa  mov     rax, [rbx]
0x1800510fd  lea     r9, [rbp+57h+rcSrc2]
0x180051101  mov     r8, r15
0x180051104  mov     edx, 409h
0x180051109  mov     rcx, rbx
0x18005110c  mov     rax, [rax+150h]
0x180051113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051118  lea     r8, [rbp+57h+rcSrc2]; lprcSrc2
0x18005111c  lea     rdx, [rbp+57h+rc]; lprcSrc1
0x180051120  lea     rcx, [rbp+57h+rc]; lprcDst
0x180051124  call    cs:__imp_UnionRect
0x18005112a  test    edi, edi
0x18005112c  jnz     short loc_1800510CA
0x18005112e  lea     rcx, [rbp+57h+rc]; lprc
0x180051132  call    cs:__imp_IsRectEmpty
0x180051138  test    eax, eax
0x18005113a  jnz     short loc_18005116D
0x18005113c  lea     rcx, [rbp+57h+rcSrc2]; lprc
0x180051140  call    cs:__imp_SetRectEmpty
0x180051146  mov     r8d, r14d; int
0x180051149  lea     rdx, [rbp+57h+rcSrc2]; struct CRect *
0x18005114d  mov     rcx, rbx; this
0x180051150  call    ?CalcInsideRect@CControlBar@@QEBAXAEAVCRect@@H@Z; CControlBar::CalcInsideRect(CRect &,int)
0x180051155  mov     eax, [rbp+57h+rcSrc2.left]
0x180051158  sub     eax, [rbp+57h+rcSrc2.right]
0x18005115b  mov     edx, [rbp+57h+rc.right]
0x18005115e  mov     ecx, [rbp+57h+rc.bottom]
0x180051161  add     edx, eax
0x180051163  mov     eax, [rbp+57h+rcSrc2.top]
0x180051166  sub     eax, [rbp+57h+rcSrc2.bottom]
0x180051169  add     ecx, eax
0x18005116b  jmp     short loc_180051173
0x18005116d  mov     ecx, [rbp+57h+rc.bottom]
0x180051170  mov     edx, [rbp+57h+rc.right]
0x180051173  test    r14d, r14d
0x180051176  jnz     short loc_1800511B6
0x180051178  test    r12d, r12d
0x18005117b  jz      short loc_1800511B6
0x18005117d  mov     ecx, 7FFFh
0x180051182  mov     eax, edx
0x180051184  sub     eax, [rbp+57h+rc.left]
0x180051187  mov     [rsi], eax
0x180051189  mov     rax, rsi
0x18005118c  mov     [rsi+4], ecx
0x18005118f  mov     rcx, [rbp+57h+var_40]
0x180051193  xor     rcx, rsp; StackCookie
0x180051196  call    __security_check_cookie
0x18005119b  mov     rbx, [rsp+100h+arg_10]
0x1800511a3  add     rsp, 0D0h
0x1800511aa  pop     r15
0x1800511ac  pop     r14
0x1800511ae  pop     r13
0x1800511b0  pop     r12
0x1800511b2  pop     rdi
0x1800511b3  pop     rsi
0x1800511b4  pop     rbp
0x1800511b5  retn
0x1800511b6  sub     ecx, [rbp+57h+rc.top]
0x1800511b9  test    r14d, r14d
0x1800511bc  jz      short loc_180051182
0x1800511be  test    r12d, r12d
0x1800511c1  jz      short loc_180051182
0x1800511c3  mov     eax, 7FFFh
0x1800511c8  jmp     short loc_180051187
```
