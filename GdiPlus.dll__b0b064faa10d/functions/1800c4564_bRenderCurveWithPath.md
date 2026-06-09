# bRenderCurveWithPath

- ea: `0x1800c4564`
- end: `0x1800c49df`
- name: `bRenderCurveWithPath`
- size: `1147`
- prototype: `__int64 __fastcall(int, int, int, int, int left, int top, int right, int y2, int width, int yr1, int x4, int y4, DWORD r, int, int, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800c447c`
- `0x180143c18`
- `0x1801440ec`

## callees

- `0x1800c3bb8`
- `0x1800c4564`
- `0x1800fe680`
- `0x180142c70`

## import_xrefs

- `GDI32!RoundRect` at `0x1800c47be`
- `GDI32!RoundRect` at `0x1800c47be`
- `GDI32!Pie` at `0x1800c48a2`
- `GDI32!Pie` at `0x1800c48a2`
- `GDI32!Chord` at `0x1800c48f1`
- `GDI32!Chord` at `0x1800c48f1`
- `GDI32!Arc` at `0x1800c493d`
- `GDI32!Arc` at `0x1800c493d`
- `GDI32!AngleArc` at `0x1800c4745`
- `GDI32!AngleArc` at `0x1800c4996`
- `GDI32!AngleArc` at `0x1800c4745`
- `GDI32!AngleArc` at `0x1800c4996`
- `GDI32!PolyDraw` at `0x1800c4830`
- `GDI32!PolyDraw` at `0x1800c4853`
- `GDI32!PolyDraw` at `0x1800c4830`
- `GDI32!PolyDraw` at `0x1800c4853`
- `GDI32!PolyBezier` at `0x1800c4783`
- `GDI32!PolyBezier` at `0x1800c4783`
- `GDI32!EndPath` at `0x1800c4955`
- `GDI32!EndPath` at `0x1800c4955`
- `GDI32!PolyBezierTo` at `0x1800c4764`
- `GDI32!PolyBezierTo` at `0x1800c49a9`
- `GDI32!PolyBezierTo` at `0x1800c4764`
- `GDI32!PolyBezierTo` at `0x1800c49a9`
- `GDI32!BeginPath` at `0x1800c468f`
- `GDI32!BeginPath` at `0x1800c468f`
- `GDI32!Rectangle` at `0x1800c46f1`
- `GDI32!Rectangle` at `0x1800c46f1`
- `GDI32!SaveDC` at `0x1800c467d`
- `GDI32!SaveDC` at `0x1800c467d`
- `GDI32!RestoreDC` at `0x1800c47f5`
- `GDI32!RestoreDC` at `0x1800c47f5`
- `GDI32!Ellipse` at `0x1800c4718`
- `GDI32!Ellipse` at `0x1800c4718`

## pseudocode

```c
int __fastcall bRenderCurveWithPath(
        __int64 a1,
        const POINT *a2,
        const BYTE *a3,
        DWORD a4,
        int left,
        int top,
        int right,
        int y2,
        int width,
        int yr1,
        int x4,
        int y4,
        DWORD r,
        int a14,
        int SweepAngle,
        unsigned int a16)
{
  int v17; // r14d
  int v18; // r15d
  int v19; // r13d
  int v20; // ebx
  int v21; // eax
  int result; // eax
  int v23; // edi
  BOOL v24; // eax
  const POINT *v25; // r13
  int v29; // [rsp+70h] [rbp-49h] BYREF
  int v30; // [rsp+74h] [rbp-45h]
  int v31; // [rsp+78h] [rbp-41h]
  int v32; // [rsp+7Ch] [rbp-3Dh]
  int v33; // [rsp+80h] [rbp-39h]
  int v34; // [rsp+84h] [rbp-35h]
  int v35; // [rsp+88h] [rbp-31h]
  int v36; // [rsp+8Ch] [rbp-2Dh]

  v17 = left;
  v18 = top;
  v19 = right;
  v32 = y2;
  v33 = width;
  v34 = yr1;
  v35 = x4;
  v36 = y4;
  v29 = left;
  v30 = top;
  v31 = right;
  if ( !pfnSetVirtualResolution )
  {
    v20 = 0;
    if ( !(unsigned int)bXformWorkhorse(a2, a4, a1 + 84) )
      goto LABEL_25;
    v21 = bXformWorkhorse(&v29, 4, a1 + 84);
    v18 = v30;
    v17 = v29;
    if ( !v21 )
      goto LABEL_25;
    v19 = v31;
    y4 = v36;
    x4 = v35;
    yr1 = v34;
    width = v33;
    y2 = v32;
  }
  result = SaveDC(*(HDC *)(a1 + 40));
  if ( !result )
    return result;
  v20 = BeginPath(*(HDC *)(a1 + 40));
  if ( !v20 )
    goto LABEL_25;
  if ( a16 <= 0x2C )
  {
    switch ( a16 )
    {
      case 0x2Cu:
        v23 = 63;
        v24 = RoundRect(*(HDC *)(a1 + 40), v17, v18, v19, y2, width, yr1);
        goto LABEL_35;
      case 2u:
        v25 = a2;
        v23 = 64;
        v24 = PolyBezier(*(HDC *)(a1 + 40), a2, a4);
        break;
      case 5u:
        v25 = a2;
        v23 = 64;
        v24 = PolyBezierTo(*(HDC *)(a1 + 40), a2, a4);
        break;
      case 0x29u:
        v23 = 64;
        v24 = AngleArc(*(HDC *)(a1 + 40), v17, v18, r, *(FLOAT *)&a14, *(FLOAT *)&SweepAngle);
        goto LABEL_35;
      case 0x2Au:
        v23 = 63;
        v24 = Ellipse(*(HDC *)(a1 + 40), v17, v18, v19, y2);
        goto LABEL_35;
      case 0x2Bu:
        v23 = 63;
        v24 = Rectangle(*(HDC *)(a1 + 40), v17, v18, v19, y2);
LABEL_35:
        v25 = a2;
        break;
      default:
        goto LABEL_24;
    }
LABEL_36:
    v20 = v24;
    if ( v24 )
    {
      v20 = EndPath(*(HDC *)(a1 + 40));
      if ( v20 )
        v20 = DoRenderPath(a1, v23, 0);
    }
    goto LABEL_26;
  }
  switch ( a16 )
  {
    case '-':
      v23 = 64;
      v24 = Arc(*(HDC *)(a1 + 40), v17, v18, v19, y2, width, yr1, x4, y4);
      goto LABEL_35;
    case '.':
      v23 = 63;
      v24 = Chord(*(HDC *)(a1 + 40), v17, v18, v19, y2, width, yr1, x4, y4);
      goto LABEL_35;
    case '/':
      v23 = 63;
      v24 = Pie(*(HDC *)(a1 + 40), v17, v18, v19, y2, width, yr1, x4, y4);
      goto LABEL_35;
    case '8':
      v25 = a2;
      v23 = 64;
      v24 = PolyDraw(*(HDC *)(a1 + 40), a2, a3, a4);
      goto LABEL_36;
  }
LABEL_24:
  v20 = 0;
LABEL_25:
  v25 = a2;
LABEL_26:
  RestoreDC(*(HDC *)(a1 + 40), -1);
  if ( v20 )
  {
    switch ( a16 )
    {
      case 5u:
        PolyBezierTo(*(HDC *)(a1 + 40), v25, a4);
        break;
      case 0x29u:
        AngleArc(*(HDC *)(a1 + 40), v17, v18, r, *(FLOAT *)&a14, *(FLOAT *)&SweepAngle);
        break;
      case 0x38u:
        PolyDraw(*(HDC *)(a1 + 40), v25, a3, a4);
        break;
    }
  }
  return v20;
}

```

## disassembly

```asm
0x1800c4564  mov     rax, rsp
0x1800c4567  push    rbp
0x1800c4568  push    rbx
0x1800c4569  push    rsi
0x1800c456a  push    rdi
0x1800c456b  push    r12
0x1800c456d  push    r13
0x1800c456f  push    r14
0x1800c4571  push    r15
0x1800c4573  lea     rbp, [rax-47h]
0x1800c4577  sub     rsp, 0B8h
0x1800c457e  movaps  xmmword ptr [rax-58h], xmm6
0x1800c4582  movaps  xmmword ptr [rax-68h], xmm7
0x1800c4586  mov     rax, cs:__security_cookie
0x1800c458d  xor     rax, rsp
0x1800c4590  mov     [rbp+3Fh+var_68], rax
0x1800c4594  cmp     cs:pfnSetVirtualResolution, 0
0x1800c459c  mov     r10d, r9d
0x1800c459f  mov     eax, [rbp+3Fh+y2]
0x1800c45a5  mov     rsi, rcx
0x1800c45a8  mov     r14d, [rbp+3Fh+left]
0x1800c45ac  mov     r15d, [rbp+3Fh+top]
0x1800c45b0  mov     r13d, [rbp+3Fh+right]
0x1800c45b4  mov     r12d, [rbp+3Fh+arg_78]
0x1800c45bb  movss   xmm6, [rbp+3Fh+arg_70]
0x1800c45c3  movss   xmm7, [rbp+3Fh+arg_68]
0x1800c45cb  mov     [rbp+3Fh+var_7C], eax
0x1800c45ce  mov     eax, [rbp+3Fh+width]
0x1800c45d4  mov     [rbp+3Fh+var_78], eax
0x1800c45d7  mov     eax, [rbp+3Fh+yr1]
0x1800c45dd  mov     [rbp+3Fh+var_74], eax
0x1800c45e0  mov     eax, [rbp+3Fh+x4]
0x1800c45e6  mov     [rbp+3Fh+var_70], eax
0x1800c45e9  mov     eax, [rbp+3Fh+y4]
0x1800c45ef  mov     [rbp+3Fh+cpt], r9d
0x1800c45f3  mov     r9, rdx
0x1800c45f6  mov     [rbp+3Fh+var_6C], eax
0x1800c45f9  mov     [rbp+3Fh+aj], r8
0x1800c45fd  mov     [rbp+3Fh+apt], rdx
0x1800c4601  mov     [rbp+3Fh+var_88], r14d
0x1800c4605  mov     [rbp+3Fh+var_84], r15d
0x1800c4609  mov     [rbp+3Fh+var_80], r13d
0x1800c460d  jnz     short loc_1800C4679
0x1800c460f  lea     r8, [rcx+54h]
0x1800c4613  mov     edx, r10d
0x1800c4616  mov     rcx, r9
0x1800c4619  xor     ebx, ebx
0x1800c461b  call    bXformWorkhorse
0x1800c4620  test    eax, eax
0x1800c4622  jz      loc_1800C47EA
0x1800c4628  lea     r8, [rsi+54h]
0x1800c462c  lea     edx, [rbx+4]
0x1800c462f  lea     rcx, [rbp+3Fh+var_88]
0x1800c4633  call    bXformWorkhorse
0x1800c4638  mov     r15d, [rbp+3Fh+var_84]
0x1800c463c  mov     r14d, [rbp+3Fh+var_88]
0x1800c4640  test    eax, eax
0x1800c4642  jz      loc_1800C47EA
0x1800c4648  mov     eax, [rbp+3Fh+var_6C]
0x1800c464b  mov     r13d, [rbp+3Fh+var_80]
0x1800c464f  mov     [rbp+3Fh+y4], eax
0x1800c4655  mov     eax, [rbp+3Fh+var_70]
0x1800c4658  mov     [rbp+3Fh+x4], eax
0x1800c465e  mov     eax, [rbp+3Fh+var_74]
0x1800c4661  mov     [rbp+3Fh+yr1], eax
0x1800c4667  mov     eax, [rbp+3Fh+var_78]
0x1800c466a  mov     [rbp+3Fh+width], eax
0x1800c4670  mov     eax, [rbp+3Fh+var_7C]
0x1800c4673  mov     [rbp+3Fh+y2], eax
0x1800c4679  mov     rcx, [rsi+28h]; hdc
0x1800c467d  call    cs:__imp_SaveDC
0x1800c4683  test    eax, eax
0x1800c4685  jz      loc_1800C49B1
0x1800c468b  mov     rcx, [rsi+28h]; hdc
0x1800c468f  call    cs:__imp_BeginPath
0x1800c4695  mov     ebx, eax
0x1800c4697  test    eax, eax
0x1800c4699  jz      loc_1800C47EA
0x1800c469f  cmp     r12d, 2Ch ; ','
0x1800c46a3  ja      loc_1800C47C9
0x1800c46a9  jz      loc_1800C478E
0x1800c46af  mov     eax, r12d
0x1800c46b2  sub     eax, 2
0x1800c46b5  jz      loc_1800C476F
0x1800c46bb  sub     eax, 3
0x1800c46be  jz      loc_1800C4750
0x1800c46c4  sub     eax, 24h ; '$'
0x1800c46c7  jz      short loc_1800C4723
0x1800c46c9  sub     eax, 1
0x1800c46cc  jz      short loc_1800C46FC
0x1800c46ce  cmp     eax, 1
0x1800c46d1  jnz     loc_1800C47E8
0x1800c46d7  mov     rcx, [rsi+28h]; hdc
0x1800c46db  lea     edi, [rax+3Eh]
0x1800c46de  mov     eax, [rbp+3Fh+y2]
0x1800c46e4  mov     r9d, r13d; right
0x1800c46e7  mov     r8d, r15d; top
0x1800c46ea  mov     [rsp+0F0h+bottom], eax; bottom
0x1800c46ee  mov     edx, r14d; left
0x1800c46f1  call    cs:__imp_Rectangle
0x1800c46f7  jmp     loc_1800C4943
0x1800c46fc  mov     eax, [rbp+3Fh+y2]
0x1800c4702  mov     r9d, r13d; right
0x1800c4705  mov     rcx, [rsi+28h]; hdc
0x1800c4709  mov     r8d, r15d; top
0x1800c470c  mov     edx, r14d; left
0x1800c470f  mov     [rsp+0F0h+bottom], eax; bottom
0x1800c4713  mov     edi, 3Fh ; '?'
0x1800c4718  call    cs:__imp_Ellipse
0x1800c471e  jmp     loc_1800C4943
0x1800c4723  mov     r9d, [rbp+3Fh+r]; r
0x1800c472a  mov     r8d, r15d; y
0x1800c472d  mov     rcx, [rsi+28h]; hdc
0x1800c4731  mov     edx, r14d; x
0x1800c4734  movss   [rsp+0F0h+SweepAngle], xmm6; SweepAngle
0x1800c473a  mov     edi, 40h ; '@'
0x1800c473f  movss   [rsp+0F0h+bottom], xmm7; StartAngle
0x1800c4745  call    cs:__imp_AngleArc
0x1800c474b  jmp     loc_1800C4943
0x1800c4750  mov     r13, [rbp+3Fh+apt]
0x1800c4754  mov     edi, 40h ; '@'
0x1800c4759  mov     r8d, [rbp+3Fh+cpt]; cpt
0x1800c475d  mov     rdx, r13; apt
0x1800c4760  mov     rcx, [rsi+28h]; hdc
0x1800c4764  call    cs:__imp_PolyBezierTo
0x1800c476a  jmp     loc_1800C4947
0x1800c476f  mov     r13, [rbp+3Fh+apt]
0x1800c4773  mov     edi, 40h ; '@'
0x1800c4778  mov     r8d, [rbp+3Fh+cpt]; cpt
0x1800c477c  mov     rdx, r13; apt
0x1800c477f  mov     rcx, [rsi+28h]; hdc
0x1800c4783  call    cs:__imp_PolyBezier
0x1800c4789  jmp     loc_1800C4947
0x1800c478e  mov     eax, [rbp+3Fh+yr1]
0x1800c4794  mov     r9d, r13d; right
0x1800c4797  mov     rcx, [rsi+28h]; hdc
0x1800c479b  mov     r8d, r15d; top
0x1800c479e  mov     [rsp+0F0h+height], eax; height
0x1800c47a2  mov     edx, r14d; left
0x1800c47a5  mov     eax, [rbp+3Fh+width]
0x1800c47ab  mov     edi, 3Fh ; '?'
0x1800c47b0  mov     [rsp+0F0h+SweepAngle], eax; width
0x1800c47b4  mov     eax, [rbp+3Fh+y2]
0x1800c47ba  mov     [rsp+0F0h+bottom], eax; bottom
0x1800c47be  call    cs:__imp_RoundRect
0x1800c47c4  jmp     loc_1800C4943
0x1800c47c9  mov     eax, r12d
0x1800c47cc  sub     eax, 2Dh ; '-'
0x1800c47cf  jz      loc_1800C48F9
0x1800c47d5  sub     eax, 1
0x1800c47d8  jz      loc_1800C48AD
0x1800c47de  sub     eax, 1
0x1800c47e1  jz      short loc_1800C485E
0x1800c47e3  cmp     eax, 9
0x1800c47e6  jz      short loc_1800C483B
0x1800c47e8  xor     ebx, ebx
0x1800c47ea  mov     r13, [rbp+3Fh+apt]
0x1800c47ee  mov     rcx, [rsi+28h]; hdc
0x1800c47f2  or      edx, 0FFFFFFFFh; nSavedDC
0x1800c47f5  call    cs:__imp_RestoreDC
0x1800c47fb  test    ebx, ebx
0x1800c47fd  jz      loc_1800C49AF
0x1800c4803  cmp     r12d, 5
0x1800c4807  jz      loc_1800C499E
0x1800c480d  cmp     r12d, 29h ; ')'
0x1800c4811  jz      loc_1800C4979
0x1800c4817  cmp     r12d, 38h ; '8'
0x1800c481b  jnz     loc_1800C49AF
0x1800c4821  mov     r9d, [rbp+3Fh+cpt]; cpt
0x1800c4825  mov     rdx, r13; apt
0x1800c4828  mov     r8, [rbp+3Fh+aj]; aj
0x1800c482c  mov     rcx, [rsi+28h]; hdc
0x1800c4830  call    cs:__imp_PolyDraw
0x1800c4836  jmp     loc_1800C49AF
0x1800c483b  mov     r13, [rbp+3Fh+apt]
0x1800c483f  mov     edi, 40h ; '@'
0x1800c4844  mov     r9d, [rbp+3Fh+cpt]; cpt
0x1800c4848  mov     rdx, r13; apt
0x1800c484b  mov     r8, [rbp+3Fh+aj]; aj
0x1800c484f  mov     rcx, [rsi+28h]; hdc
0x1800c4853  call    cs:__imp_PolyDraw
0x1800c4859  jmp     loc_1800C4947
0x1800c485e  mov     eax, [rbp+3Fh+y4]
0x1800c4864  mov     r9d, r13d; right
0x1800c4867  mov     rcx, [rsi+28h]; hdc
0x1800c486b  mov     r8d, r15d; top
0x1800c486e  mov     [rsp+0F0h+yr2], eax; yr2
0x1800c4872  mov     edx, r14d; left
0x1800c4875  mov     eax, [rbp+3Fh+x4]
0x1800c487b  mov     edi, 3Fh ; '?'
0x1800c4880  mov     [rsp+0F0h+xr2], eax; xr2
0x1800c4884  mov     eax, [rbp+3Fh+yr1]
0x1800c488a  mov     [rsp+0F0h+height], eax; yr1
0x1800c488e  mov     eax, [rbp+3Fh+width]
0x1800c4894  mov     [rsp+0F0h+SweepAngle], eax; xr1
0x1800c4898  mov     eax, [rbp+3Fh+y2]
0x1800c489e  mov     [rsp+0F0h+bottom], eax; bottom
0x1800c48a2  call    cs:__imp_Pie
0x1800c48a8  jmp     loc_1800C4943
0x1800c48ad  mov     eax, [rbp+3Fh+y4]
0x1800c48b3  mov     r9d, r13d; x2
0x1800c48b6  mov     rcx, [rsi+28h]; hdc
0x1800c48ba  mov     r8d, r15d; y1
0x1800c48bd  mov     [rsp+0F0h+yr2], eax; y4
0x1800c48c1  mov     edx, r14d; x1
0x1800c48c4  mov     eax, [rbp+3Fh+x4]
0x1800c48ca  mov     edi, 3Fh ; '?'
0x1800c48cf  mov     [rsp+0F0h+xr2], eax; x4
0x1800c48d3  mov     eax, [rbp+3Fh+yr1]
0x1800c48d9  mov     [rsp+0F0h+height], eax; y3
0x1800c48dd  mov     eax, [rbp+3Fh+width]
0x1800c48e3  mov     [rsp+0F0h+SweepAngle], eax; x3
0x1800c48e7  mov     eax, [rbp+3Fh+y2]
0x1800c48ed  mov     [rsp+0F0h+bottom], eax; y2
0x1800c48f1  call    cs:__imp_Chord
0x1800c48f7  jmp     short loc_1800C4943
0x1800c48f9  mov     eax, [rbp+3Fh+y4]
0x1800c48ff  mov     r9d, r13d; x2
0x1800c4902  mov     rcx, [rsi+28h]; hdc
0x1800c4906  mov     r8d, r15d; y1
0x1800c4909  mov     [rsp+0F0h+yr2], eax; y4
0x1800c490d  mov     edx, r14d; x1
0x1800c4910  mov     eax, [rbp+3Fh+x4]
0x1800c4916  mov     edi, 40h ; '@'
0x1800c491b  mov     [rsp+0F0h+xr2], eax; x4
0x1800c491f  mov     eax, [rbp+3Fh+yr1]
0x1800c4925  mov     [rsp+0F0h+height], eax; y3
0x1800c4929  mov     eax, [rbp+3Fh+width]
0x1800c492f  mov     [rsp+0F0h+SweepAngle], eax; x3
0x1800c4933  mov     eax, [rbp+3Fh+y2]
0x1800c4939  mov     [rsp+0F0h+bottom], eax; y2
0x1800c493d  call    cs:__imp_Arc
0x1800c4943  mov     r13, [rbp+3Fh+apt]
0x1800c4947  mov     ebx, eax
0x1800c4949  test    eax, eax
0x1800c494b  jz      loc_1800C47EE
0x1800c4951  mov     rcx, [rsi+28h]; hdc
0x1800c4955  call    cs:__imp_EndPath
0x1800c495b  mov     ebx, eax
0x1800c495d  test    eax, eax
0x1800c495f  jz      loc_1800C47EE
0x1800c4965  xor     r8d, r8d
0x1800c4968  mov     edx, edi
0x1800c496a  mov     rcx, rsi
0x1800c496d  call    DoRenderPath
0x1800c4972  mov     ebx, eax
0x1800c4974  jmp     loc_1800C47EE
0x1800c4979  mov     r9d, [rbp+3Fh+r]; r
0x1800c4980  mov     r8d, r15d; y
0x1800c4983  mov     rcx, [rsi+28h]; hdc
0x1800c4987  mov     edx, r14d; x
0x1800c498a  movss   [rsp+0F0h+SweepAngle], xmm6; SweepAngle
0x1800c4990  movss   [rsp+0F0h+bottom], xmm7; StartAngle
0x1800c4996  call    cs:__imp_AngleArc
0x1800c499c  jmp     short loc_1800C49AF
0x1800c499e  mov     r8d, [rbp+3Fh+cpt]; cpt
0x1800c49a2  mov     rdx, r13; apt
0x1800c49a5  mov     rcx, [rsi+28h]; hdc
0x1800c49a9  call    cs:__imp_PolyBezierTo
0x1800c49af  mov     eax, ebx
0x1800c49b1  mov     rcx, [rbp+3Fh+var_68]
0x1800c49b5  xor     rcx, rsp; StackCookie
0x1800c49b8  call    __security_check_cookie
0x1800c49bd  lea     r11, [rsp+0F0h+var_38]
0x1800c49c5  movaps  xmm6, xmmword ptr [r11-18h]
0x1800c49ca  movaps  xmm7, xmmword ptr [r11-28h]
0x1800c49cf  mov     rsp, r11
0x1800c49d2  pop     r15
0x1800c49d4  pop     r14
0x1800c49d6  pop     r13
0x1800c49d8  pop     r12
0x1800c49da  pop     rdi
0x1800c49db  pop     rsi
0x1800c49dc  pop     rbx
0x1800c49dd  pop     rbp
0x1800c49de  retn
```
