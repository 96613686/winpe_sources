# ConvertPathToGdi::Draw(HDC__ *,HPEN__ *,int)

- ea: `0x18004c514`
- end: `0x18004c9d4`
- name: `?Draw@ConvertPathToGdi@@QEAAHPEAUHDC__@@PEAUHPEN__@@H@Z`
- size: `1216`
- prototype: `__int64 __fastcall(ConvertPathToGdi *__hidden this, HDC, HPEN h, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18004a970`
- `0x18004b0f0`

## callees

- `0x18004c514`
- `0x18004d544`
- `0x18004d608`
- `0x1800d3340`

## import_xrefs

- `GDI32!PolyPolyline` at `0x18004c6e4`
- `GDI32!PolyPolyline` at `0x18004c6e4`
- `GDI32!Polyline` at `0x18004c5fe`
- `GDI32!Polyline` at `0x18004c8a3`
- `GDI32!Polyline` at `0x18004c5fe`
- `GDI32!Polyline` at `0x18004c8a3`
- `GDI32!PolyBezier` at `0x18004c6a0`
- `GDI32!PolyBezier` at `0x18004c6a0`
- `GDI32!LineTo` at `0x18004c781`
- `GDI32!LineTo` at `0x18004c80c`
- `GDI32!LineTo` at `0x18004c902`
- `GDI32!LineTo` at `0x18004c781`
- `GDI32!LineTo` at `0x18004c80c`
- `GDI32!LineTo` at `0x18004c902`
- `GDI32!StrokePath` at `0x18004c9bf`
- `GDI32!StrokePath` at `0x18004c9bf`
- `GDI32!EndPath` at `0x18004c9b2`
- `GDI32!EndPath` at `0x18004c9b2`
- `GDI32!MoveToEx` at `0x18004c746`
- `GDI32!MoveToEx` at `0x18004c7d7`
- `GDI32!MoveToEx` at `0x18004c8dc`
- `GDI32!MoveToEx` at `0x18004c746`
- `GDI32!MoveToEx` at `0x18004c7d7`
- `GDI32!MoveToEx` at `0x18004c8dc`
- `GDI32!BeginPath` at `0x18004c996`
- `GDI32!BeginPath` at `0x18004c996`
- `GDI32!PolyPolygon` at `0x18004c950`
- `GDI32!PolyPolygon` at `0x18004c950`
- `GDI32!Polygon` at `0x18004c797`
- `GDI32!Polygon` at `0x18004c88e`
- `GDI32!Polygon` at `0x18004c797`
- `GDI32!Polygon` at `0x18004c88e`
- `GDI32!GetStockObject` at `0x18004c587`
- `GDI32!GetStockObject` at `0x18004c587`
- `GDI32!SelectObject` at `0x18004c576`
- `GDI32!SelectObject` at `0x18004c593`
- `GDI32!SelectObject` at `0x18004c627`
- `GDI32!SelectObject` at `0x18004c633`
- `GDI32!SelectObject` at `0x18004c576`
- `GDI32!SelectObject` at `0x18004c593`
- `GDI32!SelectObject` at `0x18004c627`
- `GDI32!SelectObject` at `0x18004c633`

## pseudocode

```c
__int64 __fastcall ConvertPathToGdi::Draw(ConvertPathToGdi *this, HDC a2, HPEN h, int a4)
{
  unsigned int v8; // esi
  int v9; // r15d
  int v10; // ebx
  void *v11; // r14
  HGDIOBJ StockObject; // rax
  void *v13; // r12
  int v14; // ebx
  int v15; // r8d
  const POINT *v16; // rdx
  BOOL v17; // eax
  __int64 v19; // r15
  int i; // r14d
  BOOL v21; // eax
  const POINT *v22; // r15
  int v23; // r12d
  __int64 v24; // r14
  _DWORD *v25; // rcx
  BOOL v26; // eax
  __int64 v27; // rcx
  HGDIOBJ v28; // [rsp+28h] [rbp-60h]
  HGDIOBJ v29; // [rsp+30h] [rbp-58h]
  int v30; // [rsp+90h] [rbp+8h]
  unsigned int v31; // [rsp+90h] [rbp+8h]

  v8 = 1;
  if ( *((int *)this + 106) > 0 )
  {
    v9 = SetupForIncreasedResolution(*((_DWORD *)this + 111), a2);
    v30 = v9;
    v10 = _mm_getcsr();
    _mm_setcsr(v10 & 0xFFFFFFC0);
    v28 = SelectObject(a2, h);
    v11 = v28;
    StockObject = GetStockObject(5);
    v29 = SelectObject(a2, StockObject);
    v13 = v29;
    _mm_setcsr(v10 & 0xFFFFFFC0);
    if ( (*((_BYTE *)this + 436) & 1) == 0 )
    {
      if ( (*((_BYTE *)this + 436) & 0x10) != 0 )
      {
        v31 = _mm_getcsr() & 0xFFFFFFC0;
        _mm_setcsr(v31);
        v8 = PolyBezier(a2, *((const POINT **)this + 51), *((_DWORD *)this + 106));
        _mm_setcsr(v31);
      }
      else if ( !BeginPath(a2) || !ConvertPathToGdi::DrawMixedPath(this, a2) || !EndPath(a2) || !StrokePath(a2) )
      {
        v8 = 0;
      }
      goto LABEL_7;
    }
    v14 = _mm_getcsr();
    _mm_setcsr(v14 & 0xFFFFFFC0);
    if ( *((_DWORD *)this + 107) == 1 )
    {
      v15 = *((_DWORD *)this + 106);
      v16 = (const POINT *)*((_QWORD *)this + 51);
      if ( (*((_BYTE *)this + 436) & 0x20) == 0 )
      {
        v17 = Polyline(a2, v16, v15);
        v8 = v17;
        if ( a4 )
        {
          if ( !v17
            || (v8 = 1,
                !MoveToEx(
                   a2,
                   *(_DWORD *)(*((_QWORD *)this + 51) + 8LL * (*((_DWORD *)this + 106) - 1)),
                   *(_DWORD *)(*((_QWORD *)this + 51) + 8LL * (*((_DWORD *)this + 106) - 1) + 4),
                   0))
            || !LineTo(
                  a2,
                  *(_DWORD *)(*((_QWORD *)this + 51) + 8LL * (*((_DWORD *)this + 106) - 1)) + 1,
                  *(_DWORD *)(*((_QWORD *)this + 51) + 8LL * (*((_DWORD *)this + 106) - 1) + 4)) )
          {
            v8 = 0;
          }
        }
        goto LABEL_6;
      }
      v21 = Polygon(a2, v16, v15);
      goto LABEL_44;
    }
    if ( (*((_BYTE *)this + 436) & 0x20) == 0 )
    {
      v8 = PolyPolyline(a2, *((const POINT **)this + 51), *((const DWORD **)this + 52), *((_DWORD *)this + 107));
      if ( !a4 )
      {
LABEL_6:
        _mm_setcsr(v14 & 0xFFFFFFC0);
LABEL_7:
        SelectObject(a2, v11);
        SelectObject(a2, v13);
        CleanupForIncreasedResolution(*((_DWORD *)this + 111), v9, a2);
        return v8;
      }
      v19 = *((_QWORD *)this + 51);
      for ( i = 0; i < *((_DWORD *)this + 107); v19 += 8LL * *(int *)(*((_QWORD *)this + 52) + 4 * v27) )
      {
        v8 = v8
          && MoveToEx(
               a2,
               *(_DWORD *)(v19 + 8LL * (*(_DWORD *)(*((_QWORD *)this + 52) + 4LL * i) - 1)),
               *(_DWORD *)(v19 + 8LL * (*(_DWORD *)(*((_QWORD *)this + 52) + 4LL * i) - 1) + 4),
               0)
          && LineTo(
               a2,
               *(_DWORD *)(v19 + 8LL * (*(_DWORD *)(*((_QWORD *)this + 52) + 4LL * i) - 1)) + 1,
               *(_DWORD *)(v19 + 8LL * (*(_DWORD *)(*((_QWORD *)this + 52) + 4LL * i) - 1) + 4));
        v27 = i++;
      }
LABEL_47:
      v11 = v28;
LABEL_48:
      v9 = v30;
      goto LABEL_6;
    }
    if ( (*((_BYTE *)this + 436) & 0x40) == 0 )
    {
      v21 = PolyPolygon(a2, *((const POINT **)this + 51), *((const INT **)this + 52), *((_DWORD *)this + 107));
LABEL_44:
      v8 = v21;
      goto LABEL_6;
    }
    v22 = (const POINT *)*((_QWORD *)this + 51);
    v23 = 0;
    if ( *((int *)this + 107) <= 0 )
    {
      v13 = v29;
      goto LABEL_48;
    }
    while ( 1 )
    {
      v24 = **((int **)this + 52);
      v25 = (_DWORD *)*((_QWORD *)this + 51);
      if ( *v25 == v25[2 * (int)v24 - 2] && v25[1] == v25[2 * (int)v24 - 1] )
      {
        if ( !v8 )
          goto LABEL_40;
        v26 = Polygon(a2, v22, v24);
      }
      else
      {
        v8 = v8 && Polyline(a2, v22, v24);
        if ( !a4 )
          goto LABEL_41;
        if ( !v8 || !MoveToEx(a2, v22[(int)v24 - 1].x, v22[(int)v24 - 1].y, 0) )
        {
LABEL_40:
          v8 = 0;
          goto LABEL_41;
        }
        v26 = LineTo(a2, v22[(int)v24 - 1].x + 1, v22[(int)v24 - 1].y);
      }
      if ( !v26 )
        goto LABEL_40;
      v8 = 1;
LABEL_41:
      *((_QWORD *)this + 52) += 4LL;
      v22 += v24;
      if ( ++v23 >= *((_DWORD *)this + 107) )
      {
        v13 = v29;
        goto LABEL_47;
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18004c514  push    rbx
0x18004c516  push    rbp
0x18004c517  push    rsi
0x18004c518  push    rdi
0x18004c519  push    r12
0x18004c51b  push    r13
0x18004c51d  push    r14
0x18004c51f  push    r15
0x18004c521  sub     rsp, 48h
0x18004c525  xor     ebx, ebx
0x18004c527  mov     r13d, r9d
0x18004c52a  mov     r14, r8
0x18004c52d  mov     rbp, rdx
0x18004c530  mov     rdi, rcx
0x18004c533  mov     esi, 1
0x18004c538  cmp     [rcx+1A8h], ebx
0x18004c53e  jle     loc_18004C64A
0x18004c544  mov     ecx, [rcx+1BCh]; int
0x18004c54a  call    ?SetupForIncreasedResolution@@YAHHPEAUHDC__@@@Z; SetupForIncreasedResolution(int,HDC__ *)
0x18004c54f  mov     r15d, eax
0x18004c552  mov     [rsp+88h+arg_0], eax
0x18004c559  stmxcsr [rsp+88h+var_68]
0x18004c55e  mov     ebx, [rsp+88h+var_68]
0x18004c562  mov     rdx, r14; h
0x18004c565  mov     eax, ebx
0x18004c567  mov     rcx, rbp; hdc
0x18004c56a  and     eax, 0FFFFFFC0h
0x18004c56d  mov     [rsp+88h+var_68], eax
0x18004c571  ldmxcsr [rsp+88h+var_68]
0x18004c576  call    cs:__imp_SelectObject
0x18004c57c  lea     ecx, [rsi+4]; i
0x18004c57f  mov     [rsp+88h+var_60], rax
0x18004c584  mov     r14, rax
0x18004c587  call    cs:__imp_GetStockObject
0x18004c58d  mov     rdx, rax; h
0x18004c590  mov     rcx, rbp; hdc
0x18004c593  call    cs:__imp_SelectObject
0x18004c599  mov     ecx, 0FFFFFFC0h
0x18004c59e  mov     [rsp+88h+var_58], rax
0x18004c5a3  and     ebx, ecx
0x18004c5a5  mov     r12, rax
0x18004c5a8  mov     [rsp+88h+var_68], ebx
0x18004c5ac  ldmxcsr [rsp+88h+var_68]
0x18004c5b1  test    [rdi+1B4h], sil
0x18004c5b8  jz      loc_18004C65D
0x18004c5be  stmxcsr [rsp+88h+var_68]
0x18004c5c3  mov     ebx, [rsp+88h+var_68]
0x18004c5c7  mov     eax, ebx
0x18004c5c9  and     eax, ecx
0x18004c5cb  mov     [rsp+88h+var_68], eax
0x18004c5cf  ldmxcsr [rsp+88h+var_68]
0x18004c5d4  cmp     [rdi+1ACh], esi
0x18004c5da  jnz     loc_18004C6BF
0x18004c5e0  test    byte ptr [rdi+1B4h], 20h
0x18004c5e7  mov     rcx, rbp; hdc
0x18004c5ea  mov     r8d, [rdi+1A8h]; cpt
0x18004c5f1  mov     rdx, [rdi+198h]; apt
0x18004c5f8  jnz     loc_18004C797
0x18004c5fe  call    cs:__imp_Polyline
0x18004c604  mov     esi, eax
0x18004c606  test    r13d, r13d
0x18004c609  jnz     loc_18004C7A2
0x18004c60f  and     ebx, 0FFFFFFC0h
0x18004c612  mov     [rsp+88h+arg_0], ebx
0x18004c619  ldmxcsr [rsp+88h+arg_0]
0x18004c621  mov     rdx, r14; h
0x18004c624  mov     rcx, rbp; hdc
0x18004c627  call    cs:__imp_SelectObject
0x18004c62d  mov     rdx, r12; h
0x18004c630  mov     rcx, rbp; hdc
0x18004c633  call    cs:__imp_SelectObject
0x18004c639  mov     ecx, [rdi+1BCh]; int
0x18004c63f  mov     r8, rbp; HDC
0x18004c642  mov     edx, r15d; int
0x18004c645  call    ?CleanupForIncreasedResolution@@YAXHHPEAUHDC__@@@Z; CleanupForIncreasedResolution(int,int,HDC__ *)
0x18004c64a  mov     eax, esi
0x18004c64c  add     rsp, 48h
0x18004c650  pop     r15
0x18004c652  pop     r14
0x18004c654  pop     r13
0x18004c656  pop     r12
0x18004c658  pop     rdi
0x18004c659  pop     rsi
0x18004c65a  pop     rbp
0x18004c65b  pop     rbx
0x18004c65c  retn
0x18004c65d  test    byte ptr [rdi+1B4h], 10h
0x18004c664  jz      loc_18004C993
0x18004c66a  stmxcsr [rsp+88h+arg_0]
0x18004c672  mov     ebx, [rsp+88h+arg_0]
0x18004c679  mov     r13d, ecx
0x18004c67c  mov     r8d, [rdi+1A8h]; cpt
0x18004c683  mov     eax, ebx
0x18004c685  mov     rdx, [rdi+198h]; apt
0x18004c68c  and     eax, ecx
0x18004c68e  mov     [rsp+88h+arg_0], eax
0x18004c695  mov     rcx, rbp; hdc
0x18004c698  ldmxcsr [rsp+88h+arg_0]
0x18004c6a0  call    cs:__imp_PolyBezier
0x18004c6a6  and     ebx, r13d
0x18004c6a9  mov     esi, eax
0x18004c6ab  mov     [rsp+88h+arg_0], ebx
0x18004c6b2  ldmxcsr [rsp+88h+arg_0]
0x18004c6ba  jmp     loc_18004C621
0x18004c6bf  test    byte ptr [rdi+1B4h], 20h
0x18004c6c6  jnz     loc_18004C821
0x18004c6cc  mov     r9d, [rdi+1ACh]; csz
0x18004c6d3  mov     rcx, rbp; hdc
0x18004c6d6  mov     r8, [rdi+1A0h]; asz
0x18004c6dd  mov     rdx, [rdi+198h]; apt
0x18004c6e4  call    cs:__imp_PolyPolyline
0x18004c6ea  mov     esi, eax
0x18004c6ec  test    r13d, r13d
0x18004c6ef  jz      loc_18004C60F
0x18004c6f5  mov     r15, [rdi+198h]
0x18004c6fc  xor     r14d, r14d
0x18004c6ff  cmp     [rdi+1ACh], r14d
0x18004c706  jle     loc_18004C981
0x18004c70c  lea     r13d, [r14+1]
0x18004c710  test    esi, esi
0x18004c712  jz      loc_18004C95D
0x18004c718  mov     rax, [rdi+1A0h]
0x18004c71f  xor     r9d, r9d; lppt
0x18004c722  movsxd  rcx, r14d
0x18004c725  mov     edx, [rax+rcx*4]
0x18004c728  sub     edx, r13d
0x18004c72b  movsxd  rcx, r14d
0x18004c72e  movsxd  r8, edx
0x18004c731  mov     edx, [rax+rcx*4]
0x18004c734  mov     rcx, rbp; hdc
0x18004c737  mov     r8d, [r15+r8*8+4]; y
0x18004c73c  sub     edx, r13d
0x18004c73f  movsxd  rdx, edx
0x18004c742  mov     edx, [r15+rdx*8]; x
0x18004c746  call    cs:__imp_MoveToEx
0x18004c74c  test    eax, eax
0x18004c74e  jz      loc_18004C95D
0x18004c754  mov     rax, [rdi+1A0h]
0x18004c75b  movsxd  rcx, r14d
0x18004c75e  mov     edx, [rax+rcx*4]
0x18004c761  sub     edx, r13d
0x18004c764  movsxd  rcx, r14d
0x18004c767  movsxd  r8, edx
0x18004c76a  mov     eax, [rax+rcx*4]
0x18004c76d  mov     rcx, rbp; hdc
0x18004c770  mov     r8d, [r15+r8*8+4]; y
0x18004c775  sub     eax, r13d
0x18004c778  cdqe
0x18004c77a  mov     edx, [r15+rax*8]
0x18004c77e  add     edx, r13d; x
0x18004c781  call    cs:__imp_LineTo
0x18004c787  test    eax, eax
0x18004c789  jz      loc_18004C95D
0x18004c78f  mov     esi, r13d
0x18004c792  jmp     loc_18004C95F
0x18004c797  call    cs:__imp_Polygon
0x18004c79d  jmp     loc_18004C956
0x18004c7a2  test    eax, eax
0x18004c7a4  jz      short loc_18004C81A
0x18004c7a6  mov     r8, [rdi+198h]
0x18004c7ad  mov     esi, 1
0x18004c7b2  mov     eax, [rdi+1A8h]
0x18004c7b8  xor     r9d, r9d; lppt
0x18004c7bb  sub     eax, esi
0x18004c7bd  movsxd  r10, eax
0x18004c7c0  mov     eax, [rdi+1A8h]
0x18004c7c6  sub     eax, esi
0x18004c7c8  movsxd  rcx, eax
0x18004c7cb  mov     edx, [r8+rcx*8]; x
0x18004c7cf  mov     rcx, rbp; hdc
0x18004c7d2  mov     r8d, [r8+r10*8+4]; y
0x18004c7d7  call    cs:__imp_MoveToEx
0x18004c7dd  test    eax, eax
0x18004c7df  jz      short loc_18004C81A
0x18004c7e1  mov     r8, [rdi+198h]
0x18004c7e8  mov     eax, [rdi+1A8h]
0x18004c7ee  sub     eax, esi
0x18004c7f0  movsxd  r9, eax
0x18004c7f3  mov     eax, [rdi+1A8h]
0x18004c7f9  sub     eax, esi
0x18004c7fb  movsxd  rcx, eax
0x18004c7fe  mov     edx, [r8+rcx*8]
0x18004c802  mov     rcx, rbp; hdc
0x18004c805  mov     r8d, [r8+r9*8+4]; y
0x18004c80a  add     edx, esi; x
0x18004c80c  call    cs:__imp_LineTo
0x18004c812  test    eax, eax
0x18004c814  jnz     loc_18004C60F
0x18004c81a  xor     esi, esi
0x18004c81c  jmp     loc_18004C60F
0x18004c821  test    byte ptr [rdi+1B4h], 40h
0x18004c828  jz      loc_18004C938
0x18004c82e  mov     r15, [rdi+198h]
0x18004c835  xor     r12d, r12d
0x18004c838  cmp     [rdi+1ACh], r12d
0x18004c83f  jg      short loc_18004C84B
0x18004c841  mov     r12, [rsp+88h+var_58]
0x18004c846  jmp     loc_18004C986
0x18004c84b  mov     rax, [rdi+1A0h]
0x18004c852  movsxd  r14, dword ptr [rax]
0x18004c855  lea     eax, [r14-1]
0x18004c859  movsxd  rdx, eax
0x18004c85c  mov     rax, [rdi+198h]
0x18004c863  mov     rcx, rax
0x18004c866  mov     eax, [rax+rdx*8]
0x18004c869  cmp     [rcx], eax
0x18004c86b  jnz     short loc_18004C896
0x18004c86d  lea     eax, [r14-1]
0x18004c871  movsxd  rdx, eax
0x18004c874  mov     eax, [rcx+rdx*8+4]
0x18004c878  cmp     [rcx+4], eax
0x18004c87b  jnz     short loc_18004C896
0x18004c87d  test    esi, esi
0x18004c87f  jz      loc_18004C913
0x18004c885  mov     r8d, r14d; cpt
0x18004c888  mov     rdx, r15; apt
0x18004c88b  mov     rcx, rbp; hdc
0x18004c88e  call    cs:__imp_Polygon
0x18004c894  jmp     short loc_18004C908
0x18004c896  test    esi, esi
0x18004c898  jz      short loc_18004C8B4
0x18004c89a  mov     r8d, r14d; cpt
0x18004c89d  mov     rdx, r15; apt
0x18004c8a0  mov     rcx, rbp; hdc
0x18004c8a3  call    cs:__imp_Polyline
0x18004c8a9  test    eax, eax
0x18004c8ab  jz      short loc_18004C8B4
0x18004c8ad  mov     esi, 1
0x18004c8b2  jmp     short loc_18004C8B6
0x18004c8b4  xor     esi, esi
0x18004c8b6  test    r13d, r13d
0x18004c8b9  jz      short loc_18004C915
0x18004c8bb  test    esi, esi
0x18004c8bd  jz      short loc_18004C913
0x18004c8bf  lea     eax, [r14-1]
0x18004c8c3  xor     r9d, r9d; lppt
0x18004c8c6  movsxd  r8, eax
0x18004c8c9  mov     rcx, rbp; hdc
0x18004c8cc  lea     eax, [r14-1]
0x18004c8d0  movsxd  rdx, eax
0x18004c8d3  mov     r8d, [r15+r8*8+4]; y
0x18004c8d8  mov     edx, [r15+rdx*8]; x
0x18004c8dc  call    cs:__imp_MoveToEx
0x18004c8e2  test    eax, eax
0x18004c8e4  jz      short loc_18004C913
0x18004c8e6  lea     eax, [r14-1]
0x18004c8ea  movsxd  r8, eax
0x18004c8ed  lea     eax, [r14-1]
0x18004c8f1  movsxd  rcx, eax
0x18004c8f4  mov     r8d, [r15+r8*8+4]; y
0x18004c8f9  mov     edx, [r15+rcx*8]
0x18004c8fd  mov     rcx, rbp; hdc
0x18004c900  inc     edx; x
0x18004c902  call    cs:__imp_LineTo
0x18004c908  test    eax, eax
0x18004c90a  jz      short loc_18004C913
0x18004c90c  mov     esi, 1
0x18004c911  jmp     short loc_18004C915
0x18004c913  xor     esi, esi
0x18004c915  add     qword ptr [rdi+1A0h], 4
0x18004c91d  lea     r15, [r15+r14*8]
0x18004c921  inc     r12d
0x18004c924  cmp     r12d, [rdi+1ACh]
0x18004c92b  jl      loc_18004C84B
0x18004c931  mov     r12, [rsp+88h+var_58]
0x18004c936  jmp     short loc_18004C981
0x18004c938  mov     r9d, [rdi+1ACh]; csz
0x18004c93f  mov     rcx, rbp; hdc
0x18004c942  mov     r8, [rdi+1A0h]; asz
0x18004c949  mov     rdx, [rdi+198h]; apt
0x18004c950  call    cs:__imp_PolyPolygon
0x18004c956  mov     esi, eax
0x18004c958  jmp     loc_18004C60F
0x18004c95d  xor     esi, esi
0x18004c95f  mov     rax, [rdi+1A0h]
0x18004c966  movsxd  rcx, r14d
0x18004c969  add     r14d, r13d
0x18004c96c  movsxd  rcx, dword ptr [rax+rcx*4]
0x18004c970  lea     r15, [r15+rcx*8]
0x18004c974  cmp     r14d, [rdi+1ACh]
0x18004c97b  jl      loc_18004C710
0x18004c981  mov     r14, [rsp+88h+var_60]
0x18004c986  mov     r15d, [rsp+88h+arg_0]
0x18004c98e  jmp     loc_18004C60F
0x18004c993  mov     rcx, rbp; hdc
0x18004c996  call    cs:__imp_BeginPath
0x18004c99c  test    eax, eax
0x18004c99e  jz      short loc_18004C9CD
0x18004c9a0  mov     rdx, rbp; HDC
0x18004c9a3  mov     rcx, rdi; this
0x18004c9a6  call    ?DrawMixedPath@ConvertPathToGdi@@IEAAHPEAUHDC__@@@Z; ConvertPathToGdi::DrawMixedPath(HDC__ *)
0x18004c9ab  test    eax, eax
0x18004c9ad  jz      short loc_18004C9CD
0x18004c9af  mov     rcx, rbp; hdc
0x18004c9b2  call    cs:__imp_EndPath
0x18004c9b8  test    eax, eax
0x18004c9ba  jz      short loc_18004C9CD
0x18004c9bc  mov     rcx, rbp; hdc
0x18004c9bf  call    cs:__imp_StrokePath
0x18004c9c5  test    eax, eax
  ... truncated ...
```
