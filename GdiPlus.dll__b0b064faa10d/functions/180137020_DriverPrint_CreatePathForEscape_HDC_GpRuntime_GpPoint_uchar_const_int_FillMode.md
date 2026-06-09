# DriverPrint::CreatePathForEscape(HDC__ *,GpRuntime::GpPoint *,uchar const *,int,FillMode)

- ea: `0x180137020`
- end: `0x18013724c`
- name: `?CreatePathForEscape@DriverPrint@@IEAAXPEAUHDC__@@PEAVGpPoint@GpRuntime@@PEBEHW4FillMode@@@Z`
- size: `556`
- prototype: `void __high(HDC, struct GpRuntime::GpPoint *, const unsigned __int8 *, int, enum FillMode)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180138950`
- `0x180138f70`

## callees

- `0x1800fe680`
- `0x180137020`

## import_xrefs

- `GDI32!StrokePath` at `0x180137205`
- `GDI32!StrokePath` at `0x180137205`
- `GDI32!EndPath` at `0x1801371fc`
- `GDI32!EndPath` at `0x1801371fc`
- `GDI32!CloseFigure` at `0x1801371de`
- `GDI32!CloseFigure` at `0x1801371de`
- `GDI32!PolylineTo` at `0x1801370fb`
- `GDI32!PolylineTo` at `0x1801371cb`
- `GDI32!PolylineTo` at `0x1801370fb`
- `GDI32!PolylineTo` at `0x1801371cb`
- `GDI32!PolyBezierTo` at `0x18013713d`
- `GDI32!PolyBezierTo` at `0x1801371ba`
- `GDI32!PolyBezierTo` at `0x18013713d`
- `GDI32!PolyBezierTo` at `0x1801371ba`
- `GDI32!MoveToEx` at `0x18013715f`
- `GDI32!MoveToEx` at `0x18013715f`
- `GDI32!BeginPath` at `0x1801370be`
- `GDI32!BeginPath` at `0x1801370be`
- `GDI32!Escape` at `0x1801370b2`
- `GDI32!Escape` at `0x180137222`
- `GDI32!Escape` at `0x1801370b2`
- `GDI32!Escape` at `0x180137222`

## pseudocode

```c
int __fastcall DriverPrint::CreatePathForEscape(__int64 a1, HDC a2, const POINT *a3, char *a4, int a5, int a6)
{
  char *v6; // r15
  const POINT *v7; // rdi
  signed int v9; // ebx
  char v10; // r14
  char v12; // r13
  char v13; // cl
  int v14; // ecx
  int v15; // ecx
  int v16; // edx
  __int64 v17; // rax
  __int64 v18; // rax
  int result; // eax
  int v20; // [rsp+30h] [rbp-30h]
  CHAR pvIn[2]; // [rsp+38h] [rbp-28h] BYREF
  char v22; // [rsp+3Ah] [rbp-26h]
  char v23; // [rsp+3Bh] [rbp-25h]
  int v24; // [rsp+3Ch] [rbp-24h]
  __int16 v25; // [rsp+40h] [rbp-20h]
  int v26; // [rsp+42h] [rbp-1Eh]
  __int16 v27; // [rsp+46h] [rbp-1Ah]
  int v28; // [rsp+48h] [rbp-18h]
  __int16 v29; // [rsp+4Ch] [rbp-14h]
  __int64 v30; // [rsp+4Eh] [rbp-12h]

  if ( a3 )
  {
    v6 = a4;
    v7 = a3;
    if ( a4 )
    {
      v23 = 1;
      v27 = 1;
      *(_WORD *)pvIn = 0;
      v22 = (a6 != 0) + 1;
      v24 = 5;
      v25 = 0;
      v26 = 0;
      v9 = 0;
      v28 = 0;
      v29 = 0;
      v30 = 0;
      Escape(a2, 4096, 0, 0, 0);
      v10 = 0;
      BeginPath(a2);
LABEL_25:
      v16 = 1;
      v20 = 1;
      while ( 1 )
      {
        if ( a5 <= 0 )
        {
          EndPath(a2);
          StrokePath(a2);
          return Escape(a2, 4098, 30, pvIn, 0);
        }
        v12 = *v6;
        --a5;
        v13 = *v6++;
        v14 = v13 & 7;
        if ( v14 )
        {
          v15 = v14 - 1;
          if ( v15 )
          {
            if ( v15 != 2 )
              goto LABEL_16;
            if ( v10 == 1 )
            {
              PolylineTo(a2, v7, v9);
              v10 = 3;
LABEL_9:
              v16 = v20;
              v17 = v9;
              v9 = 1;
              v7 += v17;
              goto LABEL_16;
            }
          }
          else if ( v10 == 3 )
          {
            if ( v9 == 3 * (v9 / 3) )
              PolyBezierTo(a2, v7, v9);
            v10 = 1;
            goto LABEL_9;
          }
          ++v9;
        }
        else
        {
          MoveToEx(a2, v7->x, v7->y, 0);
          v9 = 0;
          v10 = *v6 & 7;
          ++v7;
          v16 = 0;
          v20 = 0;
        }
LABEL_16:
        if ( v12 < 0 || !a5 || !*v6 && !v16 )
        {
          if ( v10 == 3 )
          {
            if ( v9 == 3 * (v9 / 3) )
              PolyBezierTo(a2, v7, v9);
          }
          else
          {
            PolylineTo(a2, v7, v9);
          }
          v18 = v9;
          v9 = 0;
          v7 += v18;
          CloseFigure(a2);
          goto LABEL_25;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180137020  test    r8, r8
0x180137023  jz      locret_18013724B
0x180137029  mov     [rsp-38h+arg_0], rbx
0x18013702e  push    rbp
0x18013702f  push    rsi
0x180137030  push    rdi
0x180137031  push    r12
0x180137033  push    r13
0x180137035  push    r14
0x180137037  push    r15
0x180137039  mov     rbp, rsp
0x18013703c  sub     rsp, 60h
0x180137040  mov     rax, cs:__security_cookie
0x180137047  xor     rax, rsp
0x18013704a  mov     [rbp+var_8], rax
0x18013704e  xor     r13d, r13d
0x180137051  mov     r15, r9
0x180137054  mov     rdi, r8
0x180137057  mov     rsi, rdx
0x18013705a  test    r9, r9
0x18013705d  jz      loc_180137228
0x180137063  cmp     [rbp+arg_28], r13d
0x180137067  lea     ecx, [r13+1]
0x18013706b  mov     [rbp+var_25], cl
0x18013706e  mov     edx, 1000h; iEscape
0x180137073  setnz   al
0x180137076  mov     [rbp+var_1A], cx
0x18013707a  add     al, cl
0x18013707c  mov     word ptr [rbp+pvIn], r13w
0x180137081  mov     rcx, rsi; hdc
0x180137084  mov     [rbp+var_26], al
0x180137087  xor     r9d, r9d; pvIn
0x18013708a  mov     [rbp+var_24], 5
0x180137091  xor     r8d, r8d; cjIn
0x180137094  mov     [rbp+var_20], r13w
0x180137099  mov     [rbp+var_1E], r13d
0x18013709d  mov     ebx, r13d
0x1801370a0  mov     [rbp+var_18], r13d
0x1801370a4  mov     [rbp+var_14], r13w
0x1801370a9  mov     [rbp+var_12], r13
0x1801370ad  mov     [rsp+60h+pvOut], r13; pvOut
0x1801370b2  call    cs:__imp_Escape
0x1801370b8  mov     rcx, rsi; hdc
0x1801370bb  mov     r14b, r13b
0x1801370be  call    cs:__imp_BeginPath
0x1801370c4  mov     r12d, [rbp+arg_20]
0x1801370c8  jmp     loc_1801371E4
0x1801370cd  movzx   r13d, byte ptr [r15]
0x1801370d1  sub     r12d, r8d
0x1801370d4  mov     ecx, r13d
0x1801370d7  add     r15, r8
0x1801370da  and     ecx, 7
0x1801370dd  jz      short loc_180137153
0x1801370df  sub     ecx, 1
0x1801370e2  jz      short loc_180137119
0x1801370e4  cmp     ecx, 2
0x1801370e7  jnz     loc_18013717B
0x1801370ed  cmp     r14b, r8b
0x1801370f0  jnz     short loc_18013714E
0x1801370f2  mov     r8d, ebx; cpt
0x1801370f5  mov     rdx, rdi; apt
0x1801370f8  mov     rcx, rsi; hdc
0x1801370fb  call    cs:__imp_PolylineTo
0x180137101  mov     r8d, 1
0x180137107  mov     r14b, 3
0x18013710a  mov     edx, [rbp+var_30]
0x18013710d  movsxd  rax, ebx
0x180137110  mov     ebx, r8d
0x180137113  lea     rdi, [rdi+rax*8]
0x180137117  jmp     short loc_18013717B
0x180137119  cmp     r14b, 3
0x18013711d  jnz     short loc_18013714E
0x18013711f  mov     eax, 55555556h
0x180137124  imul    ebx
0x180137126  mov     eax, edx
0x180137128  shr     eax, 1Fh
0x18013712b  add     edx, eax
0x18013712d  lea     ecx, [rdx+rdx*2]
0x180137130  cmp     ebx, ecx
0x180137132  jnz     short loc_180137149
0x180137134  mov     r8d, ebx; cpt
0x180137137  mov     rdx, rdi; apt
0x18013713a  mov     rcx, rsi; hdc
0x18013713d  call    cs:__imp_PolyBezierTo
0x180137143  mov     r8d, 1
0x180137149  mov     r14b, r8b
0x18013714c  jmp     short loc_18013710A
0x18013714e  add     ebx, r8d
0x180137151  jmp     short loc_18013717B
0x180137153  mov     r8d, [rdi+4]; y
0x180137157  xor     r9d, r9d; lppt
0x18013715a  mov     edx, [rdi]; x
0x18013715c  mov     rcx, rsi; hdc
0x18013715f  call    cs:__imp_MoveToEx
0x180137165  mov     r14b, [r15]
0x180137168  xor     ebx, ebx
0x18013716a  and     r14b, 7
0x18013716e  add     rdi, 8
0x180137172  xor     edx, edx
0x180137174  mov     [rbp+var_30], edx
0x180137177  lea     r8d, [rbx+1]
0x18013717b  test    r13b, r13b
0x18013717e  js      short loc_180137193
0x180137180  xor     r13d, r13d
0x180137183  test    r12d, r12d
0x180137186  jz      short loc_180137196
0x180137188  cmp     [r15], r13b
0x18013718b  jnz     short loc_1801371F0
0x18013718d  test    edx, edx
0x18013718f  jnz     short loc_1801371F0
0x180137191  jmp     short loc_180137196
0x180137193  xor     r13d, r13d
0x180137196  cmp     r14b, 3
0x18013719a  jnz     short loc_1801371C2
0x18013719c  mov     eax, 55555556h
0x1801371a1  imul    ebx
0x1801371a3  mov     eax, edx
0x1801371a5  shr     eax, 1Fh
0x1801371a8  add     edx, eax
0x1801371aa  lea     ecx, [rdx+rdx*2]
0x1801371ad  cmp     ebx, ecx
0x1801371af  jnz     short loc_1801371D1
0x1801371b1  mov     r8d, ebx; cpt
0x1801371b4  mov     rdx, rdi; apt
0x1801371b7  mov     rcx, rsi; hdc
0x1801371ba  call    cs:__imp_PolyBezierTo
0x1801371c0  jmp     short loc_1801371D1
0x1801371c2  mov     r8d, ebx; cpt
0x1801371c5  mov     rdx, rdi; apt
0x1801371c8  mov     rcx, rsi; hdc
0x1801371cb  call    cs:__imp_PolylineTo
0x1801371d1  movsxd  rax, ebx
0x1801371d4  mov     rcx, rsi; hdc
0x1801371d7  mov     ebx, r13d
0x1801371da  lea     rdi, [rdi+rax*8]
0x1801371de  call    cs:__imp_CloseFigure
0x1801371e4  mov     r8d, 1
0x1801371ea  mov     edx, r8d
0x1801371ed  mov     [rbp+var_30], edx
0x1801371f0  test    r12d, r12d
0x1801371f3  jg      loc_1801370CD
0x1801371f9  mov     rcx, rsi; hdc
0x1801371fc  call    cs:__imp_EndPath
0x180137202  mov     rcx, rsi; hdc
0x180137205  call    cs:__imp_StrokePath
0x18013720b  lea     r9, [rbp+pvIn]; pvIn
0x18013720f  mov     [rsp+60h+pvOut], r13; pvOut
0x180137214  mov     edx, 1002h; iEscape
0x180137219  mov     r8d, 1Eh; cjIn
0x18013721f  mov     rcx, rsi; hdc
0x180137222  call    cs:__imp_Escape
0x180137228  mov     rcx, [rbp+var_8]
0x18013722c  xor     rcx, rsp; StackCookie
0x18013722f  call    __security_check_cookie
0x180137234  mov     rbx, [rsp+60h+arg_0]
0x18013723c  add     rsp, 60h
0x180137240  pop     r15
0x180137242  pop     r14
0x180137244  pop     r13
0x180137246  pop     r12
0x180137248  pop     rdi
0x180137249  pop     rsi
0x18013724a  pop     rbp
0x18013724b  retn
```
