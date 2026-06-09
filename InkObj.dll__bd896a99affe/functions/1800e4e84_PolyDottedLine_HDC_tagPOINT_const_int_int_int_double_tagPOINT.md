# PolyDottedLine(HDC__ *,tagPOINT const *,int,int,int,double *,tagPOINT *)

- ea: `0x1800e4e84`
- end: `0x1800e5157`
- name: `?PolyDottedLine@@YAHPEAUHDC__@@PEBUtagPOINT@@HHHPEANPEAU2@@Z`
- size: `723`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, const struct tagPOINT *@<rdx>, int@<r8d>, int@<r9d>, int, double *, struct tagPOINT *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18003c5e4`
- `0x18003c7f4`

## callees

- `0x1800e4e84`
- `0x180104e86`
- `0x180104eaa`
- `0x180104eda`
- `0x180104ee6`

## import_xrefs

- `USER32!GetSysColor` at `0x1800e4f07`
- `USER32!GetSysColor` at `0x1800e4f07`
- `GDI32!Ellipse` at `0x1800e5079`
- `GDI32!Ellipse` at `0x1800e5079`
- `GDI32!CreateSolidBrush` at `0x1800e4f0f`
- `GDI32!CreateSolidBrush` at `0x1800e4f0f`
- `GDI32!CreatePen` at `0x1800e4ef2`
- `GDI32!CreatePen` at `0x1800e4ef2`
- `GDI32!SelectObject` at `0x1800e4f26`
- `GDI32!SelectObject` at `0x1800e4f37`
- `GDI32!SelectObject` at `0x1800e50f1`
- `GDI32!SelectObject` at `0x1800e50ff`
- `GDI32!SelectObject` at `0x1800e4f26`
- `GDI32!SelectObject` at `0x1800e4f37`
- `GDI32!SelectObject` at `0x1800e50f1`
- `GDI32!SelectObject` at `0x1800e50ff`
- `GDI32!DeleteObject` at `0x1800e5108`
- `GDI32!DeleteObject` at `0x1800e5111`
- `GDI32!DeleteObject` at `0x1800e5108`
- `GDI32!DeleteObject` at `0x1800e5111`

## pseudocode

```c
__int64 __fastcall PolyDottedLine(HDC hdc, const struct tagPOINT *a2, int a3, int a4, int a5, double *a6)
{
  unsigned int v9; // r15d
  HPEN v10; // rsi
  COLORREF SysColor; // eax
  HBRUSH SolidBrush; // rbp
  int v13; // edi
  int v14; // r12d
  double *v15; // r15
  __int64 v16; // rbp
  int v17; // eax
  int v18; // esi
  int v19; // edi
  double v20; // xmm0_8
  double v21; // xmm8_8
  double v22; // xmm7_8
  double v23; // xmm6_8
  double v24; // xmm10_8
  double v25; // xmm11_8
  double v26; // xmm0_8
  double v27; // xmm10_8
  int v28; // edi
  int v29; // esi
  int v30; // edx
  int v31; // r8d
  HGDIOBJ h; // [rsp+30h] [rbp-A8h]
  HGDIOBJ v34; // [rsp+38h] [rbp-A0h]
  int v35; // [rsp+E0h] [rbp+8h]
  HPEN Pen; // [rsp+E8h] [rbp+10h]
  int v38; // [rsp+100h] [rbp+28h]
  struct tagPOINT *v40; // [rsp+110h] [rbp+38h]

  if ( !hdc || a3 < 2 )
    return 0;
  v9 = 0;
  v35 = 0;
  Pen = CreatePen(0, 1, 0xFFFFFFu);
  v10 = Pen;
  SysColor = GetSysColor(13);
  SolidBrush = CreateSolidBrush(SysColor);
  v40 = (struct tagPOINT *)SolidBrush;
  h = SelectObject(hdc, Pen);
  v13 = a3 - 1;
  v14 = 0;
  v34 = SelectObject(hdc, SolidBrush);
  v38 = v13;
  if ( v13 > 0 )
  {
    v15 = a6;
    v16 = 0;
    v17 = v13;
    do
    {
      v18 = a2[v16 + 1].x - a2[v16].x;
      v19 = a2[v16 + 1].y - a2[v16].y;
      if ( a2[v16 + 1].x != a2[v16].x || v19 )
      {
        v20 = sqrt_0((double)(v18 * v18 + v19 * v19));
        v21 = *v15;
        v22 = v20;
        if ( *v15 <= v20 )
        {
          v23 = atan2_0((double)v19, (double)v18);
          v24 = cos_0(v23);
          v25 = v24 * v21;
          v26 = sin_0(v23);
          v27 = v24 * 7.0;
          v28 = 0;
          v29 = (int)((v22 - v21) / 7.0);
          if ( v14 >= a4 )
          {
            while ( v28 < v29 + 1 )
            {
              v30 = (int)((double)v28 * v27 + v25) - 3 + a2[v16].x;
              v31 = (int)((double)v28 * (v26 * 7.0) + v26 * v21) - 3 + a2[v16].y;
              Ellipse(hdc, v30, v31, v30 + 6, v31 + 6);
              ++v28;
              v35 = 1;
            }
            v15 = a6;
          }
          *v15 = 7.0 - (v22 - (double)(7 * v29) - *v15);
        }
        else
        {
          *v15 = v21 - v20;
        }
        v17 = v38;
      }
      ++v14;
      ++v16;
    }
    while ( v14 < v17 );
    v10 = Pen;
    SolidBrush = (HBRUSH)v40;
    v9 = v35;
  }
  SelectObject(hdc, h);
  SelectObject(hdc, v34);
  DeleteObject(v10);
  DeleteObject(SolidBrush);
  return v9;
}

```

## disassembly

```asm
0x1800e4e84  mov     rax, rsp
0x1800e4e87  mov     [rax+18h], rbx
0x1800e4e8b  mov     [rax+20h], r9d
0x1800e4e8f  push    rbp
0x1800e4e90  push    rsi
0x1800e4e91  push    rdi
0x1800e4e92  push    r12
0x1800e4e94  push    r13
0x1800e4e96  push    r14
0x1800e4e98  push    r15
0x1800e4e9a  sub     rsp, 0A0h
0x1800e4ea1  movaps  xmmword ptr [rax-48h], xmm6
0x1800e4ea5  mov     edi, r8d
0x1800e4ea8  movaps  xmmword ptr [rax-58h], xmm7
0x1800e4eac  mov     r14, rdx
0x1800e4eaf  movaps  xmmword ptr [rax-68h], xmm8
0x1800e4eb4  mov     rbx, rcx
0x1800e4eb7  movaps  xmmword ptr [rax-78h], xmm10
0x1800e4ebc  movaps  [rsp+0D8h+var_88], xmm11
0x1800e4ec2  movaps  [rsp+0D8h+var_98], xmm12
0x1800e4ec8  test    rcx, rcx
0x1800e4ecb  jz      loc_1800E511C
0x1800e4ed1  cmp     r8d, 2
0x1800e4ed5  jl      loc_1800E511C
0x1800e4edb  xor     r15d, r15d
0x1800e4ede  xor     ecx, ecx; iStyle
0x1800e4ee0  mov     r8d, 0FFFFFFh; color
0x1800e4ee6  mov     [rsp+0D8h+arg_0], r15d
0x1800e4eee  lea     edx, [r15+1]; cWidth
0x1800e4ef2  call    cs:__imp_CreatePen
0x1800e4ef8  lea     ecx, [r15+0Dh]; nIndex
0x1800e4efc  mov     [rsp+0D8h+arg_8], rax
0x1800e4f04  mov     rsi, rax
0x1800e4f07  call    cs:__imp_GetSysColor
0x1800e4f0d  mov     ecx, eax; color
0x1800e4f0f  call    cs:__imp_CreateSolidBrush
0x1800e4f15  mov     rdx, rsi; h
0x1800e4f18  mov     rcx, rbx; hdc
0x1800e4f1b  mov     rbp, rax
0x1800e4f1e  mov     [rsp+0D8h+arg_30], rax
0x1800e4f26  call    cs:__imp_SelectObject
0x1800e4f2c  mov     rdx, rbp; h
0x1800e4f2f  mov     rcx, rbx; hdc
0x1800e4f32  mov     [rsp+0D8h+h], rax
0x1800e4f37  call    cs:__imp_SelectObject
0x1800e4f3d  dec     edi
0x1800e4f3f  xor     r12d, r12d
0x1800e4f42  mov     [rsp+0D8h+var_A0], rax
0x1800e4f47  mov     [rsp+0D8h+arg_20], edi
0x1800e4f4e  test    edi, edi
0x1800e4f50  jle     loc_1800E50E9
0x1800e4f56  mov     r15, [rsp+0D8h+arg_28]
0x1800e4f5e  xor     ebp, ebp
0x1800e4f60  mov     eax, edi
0x1800e4f62  mov     esi, [r14+rbp*8+8]
0x1800e4f67  mov     edi, [r14+rbp*8+0Ch]
0x1800e4f6c  sub     esi, [r14+rbp*8]
0x1800e4f70  sub     edi, [r14+rbp*8+4]
0x1800e4f75  test    esi, esi
0x1800e4f77  jnz     short loc_1800E4F81
0x1800e4f79  test    edi, edi
0x1800e4f7b  jz      loc_1800E50C2
0x1800e4f81  mov     ecx, edi
0x1800e4f83  mov     eax, esi
0x1800e4f85  imul    ecx, edi
0x1800e4f88  imul    eax, esi
0x1800e4f8b  add     ecx, eax
0x1800e4f8d  movd    xmm0, ecx
0x1800e4f91  cvtdq2pd xmm0, xmm0; X
0x1800e4f95  call    sqrt_0
0x1800e4f9a  movsd   xmm8, qword ptr [r15]
0x1800e4f9f  movaps  xmm7, xmm0
0x1800e4fa2  comisd  xmm8, xmm0
0x1800e4fa7  jbe     short loc_1800E4FB8
0x1800e4fa9  subsd   xmm8, xmm0
0x1800e4fae  movsd   qword ptr [r15], xmm8
0x1800e4fb3  jmp     loc_1800E50BB
0x1800e4fb8  movd    xmm1, esi
0x1800e4fbc  movd    xmm0, edi
0x1800e4fc0  cvtdq2pd xmm0, xmm0; Y
0x1800e4fc4  cvtdq2pd xmm1, xmm1; X
0x1800e4fc8  call    atan2_0
0x1800e4fcd  movaps  xmm6, xmm0
0x1800e4fd0  call    cos_0
0x1800e4fd5  movaps  xmm11, xmm0
0x1800e4fd9  movaps  xmm10, xmm0
0x1800e4fdd  movaps  xmm0, xmm6; X
0x1800e4fe0  mulsd   xmm11, xmm8
0x1800e4fe5  call    sin_0
0x1800e4fea  mulsd   xmm10, cs:__real@401c000000000000
0x1800e4ff3  movaps  xmm1, xmm7
0x1800e4ff6  xor     edi, edi
0x1800e4ff8  subsd   xmm1, xmm8
0x1800e4ffd  movaps  xmm6, xmm0
0x1800e5000  movaps  xmm12, xmm0
0x1800e5004  mulsd   xmm6, cs:__real@401c000000000000
0x1800e500c  mulsd   xmm12, xmm8
0x1800e5011  divsd   xmm1, cs:__real@401c000000000000
0x1800e5019  cvttsd2si esi, xmm1
0x1800e501d  cmp     r12d, [rsp+0D8h+arg_18]
0x1800e5025  jl      short loc_1800E5096
0x1800e5027  lea     r15d, [rsi+1]
0x1800e502b  cmp     edi, r15d
0x1800e502e  jge     short loc_1800E508E
0x1800e5030  mov     edx, [r14+rbp*8]
0x1800e5034  mov     r8d, [r14+rbp*8+4]
0x1800e5039  movd    xmm1, edi
0x1800e503d  cvtdq2pd xmm1, xmm1
0x1800e5041  movaps  xmm0, xmm1
0x1800e5044  mulsd   xmm1, xmm6
0x1800e5048  mulsd   xmm0, xmm10
0x1800e504d  addsd   xmm1, xmm12
0x1800e5052  addsd   xmm0, xmm11
0x1800e5057  cvttsd2si ecx, xmm0
0x1800e505b  add     ecx, 0FFFFFFFDh
0x1800e505e  add     edx, ecx; left
0x1800e5060  cvttsd2si ecx, xmm1
0x1800e5064  lea     r9d, [rdx+6]; right
0x1800e5068  add     ecx, 0FFFFFFFDh
0x1800e506b  add     r8d, ecx; top
0x1800e506e  mov     rcx, rbx; hdc
0x1800e5071  lea     eax, [r8+6]
0x1800e5075  mov     [rsp+0D8h+bottom], eax; bottom
0x1800e5079  call    cs:__imp_Ellipse
0x1800e507f  inc     edi
0x1800e5081  mov     [rsp+0D8h+arg_0], 1
0x1800e508c  jmp     short loc_1800E502B
0x1800e508e  mov     r15, [rsp+0D8h+arg_28]
0x1800e5096  imul    eax, esi, 7
0x1800e5099  movd    xmm0, eax
0x1800e509d  cvtdq2pd xmm0, xmm0
0x1800e50a1  subsd   xmm7, xmm0
0x1800e50a5  movsd   xmm0, cs:__real@401c000000000000
0x1800e50ad  subsd   xmm7, qword ptr [r15]
0x1800e50b2  subsd   xmm0, xmm7
0x1800e50b6  movsd   qword ptr [r15], xmm0
0x1800e50bb  mov     eax, [rsp+0D8h+arg_20]
0x1800e50c2  inc     r12d
0x1800e50c5  inc     rbp
0x1800e50c8  cmp     r12d, eax
0x1800e50cb  jl      loc_1800E4F62
0x1800e50d1  mov     rsi, [rsp+0D8h+arg_8]
0x1800e50d9  mov     rbp, [rsp+0D8h+arg_30]
0x1800e50e1  mov     r15d, [rsp+0D8h+arg_0]
0x1800e50e9  mov     rdx, [rsp+0D8h+h]; h
0x1800e50ee  mov     rcx, rbx; hdc
0x1800e50f1  call    cs:__imp_SelectObject
0x1800e50f7  mov     rdx, [rsp+0D8h+var_A0]; h
0x1800e50fc  mov     rcx, rbx; hdc
0x1800e50ff  call    cs:__imp_SelectObject
0x1800e5105  mov     rcx, rsi; ho
0x1800e5108  call    cs:__imp_DeleteObject
0x1800e510e  mov     rcx, rbp; ho
0x1800e5111  call    cs:__imp_DeleteObject
0x1800e5117  mov     eax, r15d
0x1800e511a  jmp     short loc_1800E511E
0x1800e511c  xor     eax, eax
0x1800e511e  lea     r11, [rsp+0D8h+var_38]
0x1800e5126  mov     rbx, [r11+50h]
0x1800e512a  movaps  xmm6, xmmword ptr [r11-10h]
0x1800e512f  movaps  xmm7, xmmword ptr [r11-20h]
0x1800e5134  movaps  xmm8, xmmword ptr [r11-30h]
0x1800e5139  movaps  xmm10, xmmword ptr [r11-40h]
0x1800e513e  movaps  xmm11, xmmword ptr [r11-50h]
0x1800e5143  movaps  xmm12, xmmword ptr [r11-60h]
0x1800e5148  mov     rsp, r11
0x1800e514b  pop     r15
0x1800e514d  pop     r14
0x1800e514f  pop     r13
0x1800e5151  pop     r12
0x1800e5153  pop     rdi
0x1800e5154  pop     rsi
0x1800e5155  pop     rbp
0x1800e5156  retn
```
