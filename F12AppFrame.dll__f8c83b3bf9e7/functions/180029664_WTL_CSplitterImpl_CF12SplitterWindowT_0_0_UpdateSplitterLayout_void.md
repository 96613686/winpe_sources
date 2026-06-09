# WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::UpdateSplitterLayout(void)

- ea: `0x180029664`
- end: `0x180029834`
- name: `?UpdateSplitterLayout@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAAXXZ`
- size: `464`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180023660`
- `0x180027544`
- `0x180027910`
- `0x1800288a0`
- `0x180028d38`
- `0x1800290f4`

## callees

- `0x180001800`
- `0x180029664`

## import_xrefs

- `USER32!InvalidateRect` at `0x1800296eb`
- `USER32!InvalidateRect` at `0x1800297ad`
- `USER32!InvalidateRect` at `0x180029814`
- `USER32!InvalidateRect` at `0x1800296eb`
- `USER32!InvalidateRect` at `0x1800297ad`
- `USER32!InvalidateRect` at `0x180029814`
- `USER32!SetWindowPos` at `0x180029797`
- `USER32!SetWindowPos` at `0x1800297fe`
- `USER32!SetWindowPos` at `0x180029797`
- `USER32!SetWindowPos` at `0x1800297fe`

## pseudocode

```c
BOOL __fastcall WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::UpdateSplitterLayout(RECT *a1)
{
  RECT *v1; // rdi
  bool v3; // zf
  LONG left; // edx
  LONG *p_top; // r15
  LONG v6; // eax
  LONG *p_right; // r12
  LONG v8; // ecx
  int v9; // eax
  HWND v10; // rcx
  BOOL result; // eax
  __int64 v12; // r14
  RECT v13; // xmm2
  LONG right; // edx
  LONG v15; // r8d
  LONG bottom; // ecx
  LONG v17; // r9d
  __int64 v18; // rax
  HWND v19; // rcx
  RECT Rect; // [rsp+40h] [rbp-28h] BYREF

  v1 = a1 + 2;
  if ( a1[4].right != -1 || v1->left != -1 )
  {
    v3 = a1[4].right == -1;
    Rect = 0;
    if ( v3 )
    {
      left = v1->left;
      p_top = &a1[1].top;
      if ( v1->left == -1 )
      {
        p_right = &a1[1].right;
      }
      else
      {
        v6 = a1[1].left;
        p_right = &a1[1].right;
        v8 = *p_top;
        Rect.left = v6;
        Rect.top = v8 + left;
        Rect.right = a1[1].right;
        v9 = v8 + a1[2].right + a1[3].left;
        v10 = *(HWND *)&a1[-4].left;
        Rect.bottom = left + v9;
        result = InvalidateRect(v10, &Rect, 1);
      }
      v12 = 0;
      while ( 1 )
      {
        if ( a1[4].right == -1 )
        {
          if ( !(_DWORD)v12 )
          {
            v17 = *p_top;
            bottom = *p_top + v1->left;
            goto LABEL_15;
          }
          if ( (_DWORD)v12 == 1 )
          {
            v17 = *p_top + v1->left + a1[2].right + a1[3].left;
            bottom = a1[1].bottom;
LABEL_15:
            right = *p_right;
            v15 = a1[1].left;
            Rect.right = *p_right;
            Rect.left = v15;
            Rect.bottom = bottom;
            Rect.top = v17;
LABEL_16:
            if ( *((_QWORD *)&a1->left + v12) )
              result = SetWindowPos(*((HWND *)&a1->left + v12), 0, v15, v17, right - v15, bottom - v17, 4u);
            else
              result = InvalidateRect(*(HWND *)&a1[-4].left, &Rect, 1);
          }
        }
        else if ( (_DWORD)v12 == a1[4].right )
        {
          v13 = a1[1];
          right = a1[1].right;
          v15 = _mm_cvtsi128_si32((__m128i)v13);
          bottom = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v13, 12));
          v17 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v13, 4));
          Rect = v13;
          goto LABEL_16;
        }
        v12 = (unsigned int)(v12 + 1);
        if ( (int)v12 >= 2 )
          return result;
      }
    }
    v18 = a1[4].right;
    Rect = a1[1];
    v19 = (HWND)*((_QWORD *)&a1->left + v18);
    if ( v19 )
      return SetWindowPos(v19, 0, Rect.left, Rect.top, Rect.right - Rect.left, Rect.bottom - Rect.top, 4u);
    else
      return InvalidateRect(*(HWND *)&a1[-4].left, &Rect, 1);
  }
  return result;
}

```

## disassembly

```asm
0x180029664  push    rbp
0x180029666  push    rbx
0x180029667  push    rdi
0x180029668  push    r12
0x18002966a  push    r14
0x18002966c  push    r15
0x18002966e  mov     rbp, rsp
0x180029671  sub     rsp, 68h
0x180029675  mov     rax, cs:__security_cookie
0x18002967c  xor     rax, rsp
0x18002967f  mov     [rbp+var_18], rax
0x180029683  cmp     dword ptr [rcx+48h], 0FFFFFFFFh
0x180029687  lea     rdi, [rcx+20h]
0x18002968b  mov     rbx, rcx
0x18002968e  jnz     short loc_180029699
0x180029690  cmp     dword ptr [rdi], 0FFFFFFFFh
0x180029693  jz      loc_18002981A
0x180029699  cmp     dword ptr [rcx+48h], 0FFFFFFFFh
0x18002969d  xorps   xmm0, xmm0
0x1800296a0  movdqu  xmmword ptr [rbp+Rect.left], xmm0
0x1800296a5  jnz     loc_1800297C2
0x1800296ab  mov     edx, [rdi]
0x1800296ad  lea     r15, [rcx+14h]
0x1800296b1  cmp     edx, 0FFFFFFFFh
0x1800296b4  jz      short loc_1800296F3
0x1800296b6  mov     eax, [rcx+10h]
0x1800296b9  lea     r12, [rbx+18h]
0x1800296bd  mov     ecx, [r15]
0x1800296c0  mov     r8d, 1; bErase
0x1800296c6  mov     [rbp+Rect.left], eax
0x1800296c9  lea     eax, [rcx+rdx]
0x1800296cc  mov     [rbp+Rect.top], eax
0x1800296cf  mov     eax, [r12]
0x1800296d3  mov     [rbp+Rect.right], eax
0x1800296d6  mov     eax, [rbx+30h]
0x1800296d9  add     eax, [rbx+28h]
0x1800296dc  add     eax, ecx
0x1800296de  mov     rcx, [rbx-40h]; hWnd
0x1800296e2  add     eax, edx
0x1800296e4  lea     rdx, [rbp+Rect]; lpRect
0x1800296e8  mov     [rbp+Rect.bottom], eax
0x1800296eb  call    cs:__imp_InvalidateRect
0x1800296f1  jmp     short loc_1800296F7
0x1800296f3  lea     r12, [rcx+18h]
0x1800296f7  xor     r14d, r14d
0x1800296fa  cmp     dword ptr [rbx+48h], 0FFFFFFFFh
0x1800296fe  jz      short loc_180029738
0x180029700  cmp     r14d, [rbx+48h]
0x180029704  jnz     loc_1800297B3
0x18002970a  movups  xmm2, xmmword ptr [rbx+10h]
0x18002970e  mov     edx, [rbx+18h]
0x180029711  movdqa  xmm0, xmm2
0x180029715  movd    r8d, xmm2
0x18002971a  psrldq  xmm0, 0Ch
0x18002971f  movd    ecx, xmm0
0x180029723  movdqa  xmm0, xmm2
0x180029727  psrldq  xmm0, 4
0x18002972c  movd    r9d, xmm0
0x180029731  movdqu  xmmword ptr [rbp+Rect.left], xmm2
0x180029736  jmp     short loc_180029774
0x180029738  test    r14d, r14d
0x18002973b  jnz     short loc_180029747
0x18002973d  mov     ecx, [rdi]
0x18002973f  mov     r9d, [r15]
0x180029742  add     ecx, r9d
0x180029745  jmp     short loc_18002975E
0x180029747  cmp     r14d, 1
0x18002974b  jnz     short loc_1800297B3
0x18002974d  mov     r9d, [rbx+30h]
0x180029751  add     r9d, [rbx+28h]
0x180029755  add     r9d, [rdi]
0x180029758  add     r9d, [r15]; Y
0x18002975b  mov     ecx, [rbx+1Ch]
0x18002975e  mov     edx, [r12]
0x180029762  mov     r8d, [rbx+10h]; X
0x180029766  mov     [rbp+Rect.right], edx
0x180029769  mov     [rbp+Rect.left], r8d
0x18002976d  mov     [rbp+Rect.bottom], ecx
0x180029770  mov     [rbp+Rect.top], r9d
0x180029774  cmp     qword ptr [rbx+r14*8], 0
0x180029779  jz      short loc_18002979F
0x18002977b  sub     ecx, r9d
0x18002977e  mov     [rsp+68h+uFlags], 4; uFlags
0x180029786  sub     edx, r8d
0x180029789  mov     [rsp+68h+cy], ecx; cy
0x18002978d  mov     rcx, [rbx+r14*8]; hWnd
0x180029791  mov     [rsp+68h+var_48], edx; cx
0x180029795  xor     edx, edx; hWndInsertAfter
0x180029797  call    cs:__imp_SetWindowPos
0x18002979d  jmp     short loc_1800297B3
0x18002979f  mov     rcx, [rbx-40h]; hWnd
0x1800297a3  lea     rdx, [rbp+Rect]; lpRect
0x1800297a7  mov     r8d, 1; bErase
0x1800297ad  call    cs:__imp_InvalidateRect
0x1800297b3  inc     r14d
0x1800297b6  cmp     r14d, 2
0x1800297ba  jl      loc_1800296FA
0x1800297c0  jmp     short loc_18002981A
0x1800297c2  movups  xmm0, xmmword ptr [rcx+10h]
0x1800297c6  movsxd  rax, dword ptr [rcx+48h]
0x1800297ca  movdqu  xmmword ptr [rbp+Rect.left], xmm0
0x1800297cf  mov     rcx, [rcx+rax*8]; hWnd
0x1800297d3  test    rcx, rcx
0x1800297d6  jz      short loc_180029806
0x1800297d8  mov     edx, [rbp+Rect.bottom]
0x1800297db  mov     r9d, [rbp+Rect.top]; Y
0x1800297df  sub     edx, r9d
0x1800297e2  mov     eax, [rbp+Rect.right]
0x1800297e5  mov     r8d, [rbp+Rect.left]; X
0x1800297e9  sub     eax, r8d
0x1800297ec  mov     [rsp+68h+uFlags], 4; uFlags
0x1800297f4  mov     [rsp+68h+cy], edx; cy
0x1800297f8  xor     edx, edx; hWndInsertAfter
0x1800297fa  mov     [rsp+68h+var_48], eax; cx
0x1800297fe  call    cs:__imp_SetWindowPos
0x180029804  jmp     short loc_18002981A
0x180029806  mov     rcx, [rbx-40h]; hWnd
0x18002980a  lea     rdx, [rbp+Rect]; lpRect
0x18002980e  mov     r8d, 1; bErase
0x180029814  call    cs:__imp_InvalidateRect
0x18002981a  mov     rcx, [rbp+var_18]
0x18002981e  xor     rcx, rsp; StackCookie
0x180029821  call    __security_check_cookie
0x180029826  add     rsp, 68h
0x18002982a  pop     r15
0x18002982c  pop     r14
0x18002982e  pop     r12
0x180029830  pop     rdi
0x180029831  pop     rbx
0x180029832  pop     rbp
0x180029833  retn
```
