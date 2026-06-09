# CRenderer::EndRenderLine(HDC__ *,long,long,long)

- ea: `0x180020334`
- end: `0x1800205a3`
- name: `?EndRenderLine@CRenderer@@QEAAXPEAUHDC__@@JJJ@Z`
- size: `623`
- prototype: `void __usercall(CRenderer *__hidden this@<rcx>, HDC hdc@<rdx>, int@<r8d>, int@<r9d>, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001f0c0`
- `0x18001fc90`

## callees

- `0x180020334`
- `0x1800208d8`
- `0x180039ecc`
- `0x180044ee0`

## import_xrefs

- `GDI32!LineTo` at `0x18002047f`
- `GDI32!LineTo` at `0x1800204af`
- `GDI32!LineTo` at `0x1800204f2`
- `GDI32!LineTo` at `0x18002047f`
- `GDI32!LineTo` at `0x1800204af`
- `GDI32!LineTo` at `0x1800204f2`
- `GDI32!MoveToEx` at `0x180020468`
- `GDI32!MoveToEx` at `0x18002049c`
- `GDI32!MoveToEx` at `0x1800204e0`
- `GDI32!MoveToEx` at `0x180020468`
- `GDI32!MoveToEx` at `0x18002049c`
- `GDI32!MoveToEx` at `0x1800204e0`
- `GDI32!CreatePen` at `0x1800203b9`
- `GDI32!CreatePen` at `0x1800203b9`
- `GDI32!DeleteObject` at `0x180020543`
- `GDI32!DeleteObject` at `0x180020543`
- `GDI32!SelectObject` at `0x180020448`
- `GDI32!SelectObject` at `0x180020538`
- `GDI32!SelectObject` at `0x180020448`
- `GDI32!SelectObject` at `0x180020538`
- `GDI32!SetBkColor` at `0x180020580`
- `GDI32!SetBkColor` at `0x180020580`

## pseudocode

```c
void __fastcall CRenderer::EndRenderLine(CRenderer *this, HDC hdc, int a3, int a4, int a5)
{
  __int64 v5; // r10
  int v7; // eax
  HDC v8; // r14
  __int64 v9; // r10
  const int *v10; // r15
  __int64 v11; // rdx
  COLORREF v12; // r8d
  HPEN Pen; // rsi
  int v14; // ebx
  int v15; // ebp
  int v16; // eax
  int v17; // r13d
  int v18; // ebp
  int v19; // ebx
  int v20; // esi
  int i; // ebp
  int v22; // edx
  COLORREF v23; // edx
  int v24; // [rsp+24h] [rbp-64h]
  HGDIOBJ h; // [rsp+28h] [rbp-60h]
  HPEN ho; // [rsp+30h] [rbp-58h]
  int y; // [rsp+90h] [rbp+8h]
  int x; // [rsp+A0h] [rbp+18h]

  x = a3;
  v5 = *((_QWORD *)this + 18);
  v7 = a4;
  v8 = hdc;
  if ( (*(_WORD *)(v5 + 2) & 0x4000) != 0 && (*((_BYTE *)this + 101) & 0x10) != 0 )
  {
    v10 = CTabsArray::Deref(qword_1800A41E0, *(__int16 *)(v5 + 18));
    v11 = *(_DWORD *)(v9 + 52) & 0x1F;
    if ( (unsigned int)(v11 - 1) > 0xF )
      v12 = *((_DWORD *)this + 59);
    else
      v12 = *((_DWORD *)&g_Colors + v11 - 1);
    Pen = CreatePen(0, 0, v12);
    ho = Pen;
    v14 = CMeasurer::LXtoDX(this, *(_DWORD *)(*((_QWORD *)this + 18) + 12LL));
    v15 = CMeasurer::LXtoDX(this, *(_DWORD *)(*((_QWORD *)this + 18) + 4LL));
    v24 = v15;
    v16 = CMeasurer::LXtoDX(this, v10[*(unsigned __int8 *)(*((_QWORD *)this + 18) + 17LL) - 1] & 0xFFFFFF);
    if ( Pen )
    {
      v17 = a5 - v14;
      v18 = v16 - v15 + a5 - v14;
      y = *((_DWORD *)this + 77);
      v19 = y + *((__int16 *)this + 46);
      h = SelectObject(*((HDC *)this + 35), Pen);
      MoveToEx(*((HDC *)this + 35), v17, y, 0);
      LineTo(*((HDC *)this + 35), v18, y);
      if ( (*((_BYTE *)this + 103) & 0x20) == 0 )
      {
        MoveToEx(*((HDC *)this + 35), v17, v19 - 1, 0);
        LineTo(*((HDC *)this + 35), v18, v19 - 1);
      }
      v20 = 0;
      for ( i = *(unsigned __int8 *)(*((_QWORD *)this + 18) + 17LL); i >= 0; --i )
      {
        MoveToEx(*((HDC *)this + 35), v20 + v17, y, 0);
        LineTo(*((HDC *)this + 35), v20 + v17, v19);
        if ( i )
        {
          v22 = *v10++ & 0xFFFFFF;
          v20 = CMeasurer::LXtoDX(this, v22) - v24;
        }
      }
      v8 = hdc;
      if ( h )
        SelectObject(*((HDC *)this + 35), h);
      DeleteObject(ho);
    }
    a3 = x;
    v7 = a4;
  }
  if ( v8 )
    CRenderer::RenderOffScreenBitmap(this, v8, a3, v7);
  v23 = *((_DWORD *)this + 56);
  if ( v23 != *((_DWORD *)this + 60) )
  {
    SetBkColor(*((HDC *)this + 35), v23);
    *((_DWORD *)this + 60) = *((_DWORD *)this + 56);
  }
}

```

## disassembly

```asm
0x180020334  mov     [rsp+arg_18], r9d
0x180020339  mov     [rsp+x], r8d
0x18002033e  mov     [rsp+arg_8], rdx
0x180020343  push    rbx
0x180020344  push    rbp
0x180020345  push    rsi
0x180020346  push    rdi
0x180020347  push    r12
0x180020349  push    r13
0x18002034b  push    r14
0x18002034d  push    r15
0x18002034f  sub     rsp, 48h
0x180020353  mov     r10, [rcx+90h]
0x18002035a  mov     rdi, rcx
0x18002035d  mov     ecx, 4000h
0x180020362  mov     eax, r9d
0x180020365  mov     r14, rdx
0x180020368  test    [r10+2], cx
0x18002036d  jz      loc_180020558
0x180020373  test    byte ptr [rdi+65h], 10h
0x180020377  jz      loc_180020558
0x18002037d  movsx   edx, word ptr [r10+12h]; int
0x180020382  mov     rcx, cs:qword_1800A41E0; this
0x180020389  call    ?Deref@CTabsArray@@QEBAPEBJJ@Z; CTabsArray::Deref(long)
0x18002038e  mov     edx, [r10+34h]
0x180020392  mov     r15, rax
0x180020395  and     edx, 1Fh
0x180020398  lea     ecx, [rdx-1]
0x18002039b  cmp     ecx, 0Fh
0x18002039e  ja      short loc_1800203AE
0x1800203a0  lea     r8, ?g_Colors@@3QBKB; ulong const near * const g_Colors
0x1800203a7  mov     r8d, [r8+rdx*4-4]
0x1800203ac  jmp     short loc_1800203B5
0x1800203ae  mov     r8d, [rdi+0ECh]; color
0x1800203b5  xor     edx, edx; cWidth
0x1800203b7  xor     ecx, ecx; iStyle
0x1800203b9  call    cs:__imp_CreatePen
0x1800203bf  mov     rdx, [rdi+90h]
0x1800203c6  mov     rcx, rdi; this
0x1800203c9  mov     rsi, rax
0x1800203cc  mov     [rsp+88h+ho], rax
0x1800203d1  mov     edx, [rdx+0Ch]; int
0x1800203d4  call    ?LXtoDX@CMeasurer@@QEAAJJ@Z; CMeasurer::LXtoDX(long)
0x1800203d9  mov     rdx, [rdi+90h]
0x1800203e0  mov     rcx, rdi; this
0x1800203e3  mov     ebx, eax
0x1800203e5  mov     edx, [rdx+4]; int
0x1800203e8  call    ?LXtoDX@CMeasurer@@QEAAJJ@Z; CMeasurer::LXtoDX(long)
0x1800203ed  mov     rcx, [rdi+90h]
0x1800203f4  mov     ebp, eax
0x1800203f6  mov     [rsp+88h+var_64], eax
0x1800203fa  movzx   edx, byte ptr [rcx+11h]
0x1800203fe  mov     rcx, rdi; this
0x180020401  mov     edx, [r15+rdx*4-4]
0x180020406  and     edx, 0FFFFFFh; int
0x18002040c  call    ?LXtoDX@CMeasurer@@QEAAJJ@Z; CMeasurer::LXtoDX(long)
0x180020411  test    rsi, rsi
0x180020414  jz      loc_180020549
0x18002041a  mov     r13d, [rsp+88h+arg_20]
0x180020422  sub     eax, ebp
0x180020424  mov     rcx, [rdi+118h]; hdc
0x18002042b  sub     r13d, ebx
0x18002042e  movsx   ebx, word ptr [rdi+5Ch]
0x180020432  mov     rdx, rsi; h
0x180020435  lea     ebp, [rax+r13]
0x180020439  mov     eax, [rdi+134h]
0x18002043f  mov     [rsp+88h+y], eax
0x180020446  add     ebx, eax
0x180020448  call    cs:__imp_SelectObject
0x18002044e  mov     r8d, [rsp+88h+y]; y
0x180020456  xor     r9d, r9d; lppt
0x180020459  mov     rcx, [rdi+118h]; hdc
0x180020460  mov     edx, r13d; x
0x180020463  mov     [rsp+88h+h], rax
0x180020468  call    cs:__imp_MoveToEx
0x18002046e  mov     r8d, [rsp+88h+y]; y
0x180020476  mov     edx, ebp; x
0x180020478  mov     rcx, [rdi+118h]; hdc
0x18002047f  call    cs:__imp_LineTo
0x180020485  test    byte ptr [rdi+67h], 20h
0x180020489  jnz     short loc_1800204B5
0x18002048b  mov     rcx, [rdi+118h]; hdc
0x180020492  lea     r8d, [rbx-1]; y
0x180020496  xor     r9d, r9d; lppt
0x180020499  mov     edx, r13d; x
0x18002049c  call    cs:__imp_MoveToEx
0x1800204a2  mov     rcx, [rdi+118h]; hdc
0x1800204a9  lea     r8d, [rbx-1]; y
0x1800204ad  mov     edx, ebp; x
0x1800204af  call    cs:__imp_LineTo
0x1800204b5  mov     rax, [rdi+90h]
0x1800204bc  xor     esi, esi
0x1800204be  mov     r12d, [rsp+88h+y]
0x1800204c6  mov     r14d, ebx
0x1800204c9  movzx   ebp, byte ptr [rax+11h]
0x1800204cd  mov     rcx, [rdi+118h]; hdc
0x1800204d4  lea     ebx, [rsi+r13]
0x1800204d8  mov     edx, ebx; x
0x1800204da  xor     r9d, r9d; lppt
0x1800204dd  mov     r8d, r12d; y
0x1800204e0  call    cs:__imp_MoveToEx
0x1800204e6  mov     rcx, [rdi+118h]; hdc
0x1800204ed  mov     r8d, r14d; y
0x1800204f0  mov     edx, ebx; x
0x1800204f2  call    cs:__imp_LineTo
0x1800204f8  test    ebp, ebp
0x1800204fa  jz      short loc_180020517
0x1800204fc  mov     edx, [r15]
0x1800204ff  mov     rcx, rdi; this
0x180020502  and     edx, 0FFFFFFh; int
0x180020508  add     r15, 4
0x18002050c  call    ?LXtoDX@CMeasurer@@QEAAJJ@Z; CMeasurer::LXtoDX(long)
0x180020511  mov     esi, eax
0x180020513  sub     esi, [rsp+88h+var_64]
0x180020517  sub     ebp, 1
0x18002051a  jns     short loc_1800204CD
0x18002051c  mov     r12, [rsp+88h+h]
0x180020521  mov     r14, [rsp+88h+arg_8]
0x180020529  test    r12, r12
0x18002052c  jz      short loc_18002053E
0x18002052e  mov     rcx, [rdi+118h]; hdc
0x180020535  mov     rdx, r12; h
0x180020538  call    cs:__imp_SelectObject
0x18002053e  mov     rcx, [rsp+88h+ho]; ho
0x180020543  call    cs:__imp_DeleteObject
0x180020549  mov     r8d, [rsp+88h+x]; x
0x180020551  mov     eax, [rsp+88h+arg_18]
0x180020558  test    r14, r14
0x18002055b  jz      short loc_18002056B
0x18002055d  mov     r9d, eax; y
0x180020560  mov     rdx, r14; hdc
0x180020563  mov     rcx, rdi; this
0x180020566  call    ?RenderOffScreenBitmap@CRenderer@@QEAAXPEAUHDC__@@JJ@Z; CRenderer::RenderOffScreenBitmap(HDC__ *,long,long)
0x18002056b  mov     edx, [rdi+0E0h]; color
0x180020571  cmp     edx, [rdi+0F0h]
0x180020577  jz      short loc_180020592
0x180020579  mov     rcx, [rdi+118h]; hdc
0x180020580  call    cs:__imp_SetBkColor
0x180020586  mov     eax, [rdi+0E0h]
0x18002058c  mov     [rdi+0F0h], eax
0x180020592  add     rsp, 48h
0x180020596  pop     r15
0x180020598  pop     r14
0x18002059a  pop     r13
0x18002059c  pop     r12
0x18002059e  pop     rdi
0x18002059f  pop     rsi
0x1800205a0  pop     rbp
0x1800205a1  pop     rbx
0x1800205a2  retn
```
