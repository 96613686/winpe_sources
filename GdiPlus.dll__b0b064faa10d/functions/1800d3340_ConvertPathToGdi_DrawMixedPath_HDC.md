# ConvertPathToGdi::DrawMixedPath(HDC__ *)

- ea: `0x1800d3340`
- end: `0x1800d34d3`
- name: `?DrawMixedPath@ConvertPathToGdi@@IEAAHPEAUHDC__@@@Z`
- size: `403`
- prototype: `int(ConvertPathToGdi *__hidden this, HDC)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18004c514`
- `0x18004e87c`
- `0x18004ff64`
- `0x18013c488`

## callees

- `0x1800d3340`

## import_xrefs

- `GDI32!LineTo` at `0x1800d349e`
- `GDI32!LineTo` at `0x1800d349e`
- `GDI32!CloseFigure` at `0x1800d3455`
- `GDI32!CloseFigure` at `0x1800d34b9`
- `GDI32!CloseFigure` at `0x1800d3455`
- `GDI32!CloseFigure` at `0x1800d34b9`
- `GDI32!PolylineTo` at `0x1800d33da`
- `GDI32!PolylineTo` at `0x1800d33da`
- `GDI32!PolyBezierTo` at `0x1800d3404`
- `GDI32!PolyBezierTo` at `0x1800d3404`
- `GDI32!MoveToEx` at `0x1800d3474`
- `GDI32!MoveToEx` at `0x1800d3474`

## pseudocode

```c
__int64 __fastcall ConvertPathToGdi::DrawMixedPath(ConvertPathToGdi *this, HDC a2)
{
  __int64 v2; // r13
  __int64 *v3; // rsi
  int v4; // ebx
  unsigned int v7; // r8d
  int v8; // r15d
  __int64 v9; // r9
  __int64 v10; // rdi
  int v11; // edx
  int v12; // r10d
  const POINT *v13; // rdx
  BOOL v14; // eax

  v2 = *((int *)this + 106);
  v3 = (__int64 *)((char *)this + 416);
  v4 = 0;
  v7 = 1;
  v8 = v2 - 1;
  if ( (int)v2 - 1 >= 0 )
  {
    while ( 1 )
    {
      v9 = *v3;
      v10 = v4;
      v11 = *(_BYTE *)(*v3 + v4) & 7;
      if ( (*(_BYTE *)(*v3 + v4) & 7) == 0 )
        break;
      v12 = v4;
      do
        ++v4;
      while ( v4 <= v8 && (*(_BYTE *)(v4 + v9) & 7) == v11 );
      if ( v11 == 3 )
      {
        if ( !v7 )
          goto LABEL_28;
        v14 = PolyBezierTo(a2, (const POINT *)(*((_QWORD *)this + 51) + 8 * v10), v4 - v12);
      }
      else
      {
        v13 = (const POINT *)(*((_QWORD *)this + 51) + 8 * v10);
        if ( v4 - v12 == 1 )
        {
          if ( !v7 )
          {
LABEL_28:
            v7 = 0;
            goto LABEL_14;
          }
          v14 = LineTo(a2, v13->x, v13->y);
        }
        else
        {
          if ( !v7 )
            goto LABEL_28;
          v14 = PolylineTo(a2, v13, v4 - v12);
        }
      }
      if ( !v14 )
        goto LABEL_28;
      v7 = 1;
LABEL_14:
      if ( v4 > v8 )
        goto LABEL_15;
    }
    if ( v4 <= 0 || *(char *)(v9 + v4 - 1) >= 0 )
    {
      if ( !v7 )
        goto LABEL_24;
    }
    else if ( !v7 || !CloseFigure(a2) )
    {
      goto LABEL_24;
    }
    if ( MoveToEx(
           a2,
           *(_DWORD *)(*((_QWORD *)this + 51) + 8LL * v4),
           *(_DWORD *)(*((_QWORD *)this + 51) + 8LL * v4 + 4),
           0) )
    {
      v7 = 1;
LABEL_25:
      ++v4;
      goto LABEL_14;
    }
LABEL_24:
    v7 = 0;
    goto LABEL_25;
  }
LABEL_15:
  if ( *(char *)(v2 + *v3 - 1) < 0 )
    return v7 && CloseFigure(a2);
  return v7;
}

```

## disassembly

```asm
0x1800d3340  push    rbx
0x1800d3342  push    rbp
0x1800d3343  push    rsi
0x1800d3344  push    rdi
0x1800d3345  push    r12
0x1800d3347  push    r13
0x1800d3349  push    r14
0x1800d334b  push    r15
0x1800d334d  sub     rsp, 28h
0x1800d3351  movsxd  r13, dword ptr [rcx+1A8h]
0x1800d3358  lea     rsi, [rcx+1A0h]
0x1800d335f  xor     ebx, ebx
0x1800d3361  mov     r12d, 1
0x1800d3367  mov     rbp, rdx
0x1800d336a  mov     r14, rcx
0x1800d336d  mov     r8d, r12d
0x1800d3370  lea     r15d, [r13-1]
0x1800d3374  test    r15d, r15d
0x1800d3377  js      loc_1800D341E
0x1800d337d  mov     r9, [rsi]
0x1800d3380  movsxd  rdi, ebx
0x1800d3383  movzx   edx, byte ptr [r9+rdi]
0x1800d3388  and     edx, 7
0x1800d338b  jz      loc_1800D3441
0x1800d3391  mov     r10d, ebx
0x1800d3394  jmp     short loc_1800D33A5
0x1800d3396  movsxd  rax, ebx
0x1800d3399  movzx   ecx, byte ptr [rax+r9]
0x1800d339e  and     ecx, 7
0x1800d33a1  cmp     ecx, edx
0x1800d33a3  jnz     short loc_1800D33AD
0x1800d33a5  add     ebx, r12d
0x1800d33a8  cmp     ebx, r15d
0x1800d33ab  jle     short loc_1800D3396
0x1800d33ad  sub     edx, r12d
0x1800d33b0  jnz     short loc_1800D33E2
0x1800d33b2  mov     rax, [r14+198h]
0x1800d33b9  lea     rdx, [rax+rdi*8]; apt
0x1800d33bd  mov     eax, ebx
0x1800d33bf  sub     eax, r10d
0x1800d33c2  cmp     eax, r12d
0x1800d33c5  jz      loc_1800D3490
0x1800d33cb  test    r8d, r8d
0x1800d33ce  jz      loc_1800D34A9
0x1800d33d4  mov     r8d, eax; cpt
0x1800d33d7  mov     rcx, rbp; hdc
0x1800d33da  call    cs:__imp_PolylineTo
0x1800d33e0  jmp     short loc_1800D340A
0x1800d33e2  cmp     edx, 2
0x1800d33e5  jnz     short loc_1800D33B2
0x1800d33e7  test    r8d, r8d
0x1800d33ea  jz      loc_1800D34A9
0x1800d33f0  mov     rax, [r14+198h]
0x1800d33f7  mov     r8d, ebx
0x1800d33fa  sub     r8d, r10d; cpt
0x1800d33fd  mov     rcx, rbp; hdc
0x1800d3400  lea     rdx, [rax+rdi*8]; apt
0x1800d3404  call    cs:__imp_PolyBezierTo
0x1800d340a  test    eax, eax
0x1800d340c  jz      loc_1800D34A9
0x1800d3412  mov     r8d, r12d
0x1800d3415  cmp     ebx, r15d
0x1800d3418  jle     loc_1800D337D
0x1800d341e  mov     rax, [rsi]
0x1800d3421  cmp     byte ptr [r13+rax-1], 0
0x1800d3427  jl      loc_1800D34B1
0x1800d342d  mov     eax, r8d
0x1800d3430  add     rsp, 28h
0x1800d3434  pop     r15
0x1800d3436  pop     r14
0x1800d3438  pop     r13
0x1800d343a  pop     r12
0x1800d343c  pop     rdi
0x1800d343d  pop     rsi
0x1800d343e  pop     rbp
0x1800d343f  pop     rbx
0x1800d3440  retn
0x1800d3441  test    ebx, ebx
0x1800d3443  jle     short loc_1800D3483
0x1800d3445  cmp     byte ptr [r9+rdi-1], 0
0x1800d344b  jge     short loc_1800D3483
0x1800d344d  test    r8d, r8d
0x1800d3450  jz      short loc_1800D3488
0x1800d3452  mov     rcx, rbp; hdc
0x1800d3455  call    cs:__imp_CloseFigure
0x1800d345b  test    eax, eax
0x1800d345d  jz      short loc_1800D3488
0x1800d345f  mov     rdx, [r14+198h]
0x1800d3466  xor     r9d, r9d; lppt
0x1800d3469  mov     rcx, rbp; hdc
0x1800d346c  mov     r8d, [rdx+rdi*8+4]; y
0x1800d3471  mov     edx, [rdx+rdi*8]; x
0x1800d3474  call    cs:__imp_MoveToEx
0x1800d347a  test    eax, eax
0x1800d347c  jz      short loc_1800D3488
0x1800d347e  mov     r8d, r12d
0x1800d3481  jmp     short loc_1800D348B
0x1800d3483  test    r8d, r8d
0x1800d3486  jnz     short loc_1800D345F
0x1800d3488  xor     r8d, r8d
0x1800d348b  add     ebx, r12d
0x1800d348e  jmp     short loc_1800D3415
0x1800d3490  test    r8d, r8d
0x1800d3493  jz      short loc_1800D34A9
0x1800d3495  mov     r8d, [rdx+4]; y
0x1800d3499  mov     rcx, rbp; hdc
0x1800d349c  mov     edx, [rdx]; x
0x1800d349e  call    cs:__imp_LineTo
0x1800d34a4  jmp     loc_1800D340A
0x1800d34a9  xor     r8d, r8d
0x1800d34ac  jmp     loc_1800D3415
0x1800d34b1  test    r8d, r8d
0x1800d34b4  jz      short loc_1800D34CB
0x1800d34b6  mov     rcx, rbp; hdc
0x1800d34b9  call    cs:__imp_CloseFigure
0x1800d34bf  test    eax, eax
0x1800d34c1  jz      short loc_1800D34CB
0x1800d34c3  mov     r8d, r12d
0x1800d34c6  jmp     loc_1800D342D
0x1800d34cb  xor     r8d, r8d
0x1800d34ce  jmp     loc_1800D342D
```
