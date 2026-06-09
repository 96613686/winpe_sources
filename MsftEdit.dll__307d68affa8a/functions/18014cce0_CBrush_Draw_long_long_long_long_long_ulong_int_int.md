# CBrush::Draw(long,long,long,long,long,ulong,int,int)

- ea: `0x18014cce0`
- end: `0x18014ce5f`
- name: `?Draw@CBrush@@QEAAXJJJJJKHH@Z`
- size: `383`
- prototype: `void __fastcall(CBrush *__hidden this, int, int, int, int, int, COLORREF color, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180120a90`

## callees

- `0x18006e4d4`
- `0x1800eee70`
- `0x18013bad0`
- `0x18014cce0`
- `0x18027a010`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18014cd85`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18014cd85`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x18014cd5f`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x18014cd5f`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18014cd9b`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18014cd9b`

## pseudocode

```c
void __fastcall CBrush::Draw(CBrush *this, LONG a2, LONG a3, LONG a4, LONG a5, int a6, COLORREF color, int a8, int a9)
{
  int v9; // esi
  HBRUSH SolidBrush; // r13
  HDC v16; // rax
  HGDIOBJ v17; // rax
  LONG v18; // eax
  __int64 v20; // rcx
  struct tagRECT v21; // [rsp+30h] [rbp-38h] BYREF
  struct tagRECT v22; // [rsp+40h] [rbp-28h] BYREF

  v9 = a6;
  if ( !a6 )
  {
    if ( a8 )
      return;
    v9 = 1;
    color = 12632256;
  }
  *(_QWORD *)&v21.left = *((_QWORD *)this + 3);
  if ( (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)&v21.left + 336LL) + 48LL))(*(_QWORD *)(*(_QWORD *)&v21.left + 336LL))
    && (!*((_QWORD *)this + 2) || *(_DWORD *)this != color) )
  {
    SolidBrush = CreateSolidBrush(color);
    v16 = (HDC)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)&v21.left + 336LL) + 48LL))(*(_QWORD *)(*(_QWORD *)&v21.left + 336LL));
    v17 = SelectObject(v16, SolidBrush);
    if ( *((_QWORD *)this + 2) )
      DeleteObject(v17);
    else
      *((_QWORD *)this + 1) = v17;
    *((_QWORD *)this + 2) = SolidBrush;
    *(_DWORD *)this = color;
  }
  v21.top = a3;
  v18 = a2;
  if ( a2 <= a4 )
  {
    v18 = a4;
    a4 = a2;
  }
  v21.left = a4;
  if ( a4 == v18 )
  {
    v21.right = a4 + v9;
  }
  else
  {
    v21.right = v18;
    a5 = a3 + v9;
  }
  v21.bottom = a5;
  if ( !a9
    || (unsigned int)CW32System::IntersectRect(&v21, &v21, (const struct tagRECT *)(*((_QWORD *)this + 3) + 376LL)) )
  {
    v20 = *((_QWORD *)this + 3);
    v22 = 0;
    CDisplay::RectFromRectuv(*(CDisplay **)(v20 + 152), &v22, (const struct RECTUV *)&v21, 1, 0);
    (*(void (__fastcall **)(_QWORD, struct tagRECT *, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 3) + 336LL) + 248LL))(
      *(_QWORD *)(*((_QWORD *)this + 3) + 336LL),
      &v22,
      color);
  }
}

```

## disassembly

```asm
0x18014cce0  push    rbp
0x18014cce2  push    rbx
0x18014cce3  push    rsi
0x18014cce4  push    rdi
0x18014cce5  push    r12
0x18014cce7  push    r13
0x18014cce9  push    r14
0x18014cceb  push    r15
0x18014cced  mov     rbp, rsp
0x18014ccf0  sub     rsp, 68h
0x18014ccf4  mov     rax, cs:__security_cookie
0x18014ccfb  xor     rax, rsp
0x18014ccfe  mov     [rbp+var_18], rax
0x18014cd02  mov     esi, [rbp+arg_28]
0x18014cd05  mov     edi, r9d
0x18014cd08  mov     r14d, [rbp+color]
0x18014cd0c  mov     r12d, r8d
0x18014cd0f  mov     r15d, edx
0x18014cd12  mov     rbx, rcx
0x18014cd15  test    esi, esi
0x18014cd17  jnz     short loc_18014CD30
0x18014cd19  cmp     [rbp+arg_38], esi
0x18014cd1f  jnz     loc_18014CE42
0x18014cd25  mov     esi, 1
0x18014cd2a  mov     r14d, 0C0C0C0h
0x18014cd30  mov     rax, [rcx+18h]
0x18014cd34  mov     qword ptr [rbp+var_38.left], rax
0x18014cd38  mov     rcx, [rax+150h]
0x18014cd3f  mov     rax, [rcx]
0x18014cd42  mov     rax, [rax+30h]
0x18014cd46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014cd4b  test    rax, rax
0x18014cd4e  jz      short loc_18014CDA8
0x18014cd50  cmp     qword ptr [rbx+10h], 0
0x18014cd55  jz      short loc_18014CD5C
0x18014cd57  cmp     [rbx], r14d
0x18014cd5a  jz      short loc_18014CDA8
0x18014cd5c  mov     ecx, r14d; color
0x18014cd5f  call    cs:__imp_CreateSolidBrush
0x18014cd65  mov     rcx, qword ptr [rbp+var_38.left]
0x18014cd69  mov     r13, rax
0x18014cd6c  mov     rcx, [rcx+150h]
0x18014cd73  mov     rdx, [rcx]
0x18014cd76  mov     rax, [rdx+30h]
0x18014cd7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014cd7f  mov     rdx, r13; h
0x18014cd82  mov     rcx, rax; hdc
0x18014cd85  call    cs:__imp_SelectObject
0x18014cd8b  cmp     qword ptr [rbx+10h], 0
0x18014cd90  jnz     short loc_18014CD98
0x18014cd92  mov     [rbx+8], rax
0x18014cd96  jmp     short loc_18014CDA1
0x18014cd98  mov     rcx, rax; ho
0x18014cd9b  call    cs:__imp_DeleteObject
0x18014cda1  mov     [rbx+10h], r13
0x18014cda5  mov     [rbx], r14d
0x18014cda8  cmp     r15d, edi
0x18014cdab  mov     [rbp+var_38.top], r12d
0x18014cdaf  mov     eax, r15d
0x18014cdb2  cmovle  eax, edi
0x18014cdb5  cmovle  edi, r15d
0x18014cdb9  mov     [rbp+var_38.left], edi
0x18014cdbc  cmp     edi, eax
0x18014cdbe  jnz     short loc_18014CDCB
0x18014cdc0  lea     eax, [rdi+rsi]
0x18014cdc3  mov     [rbp+var_38.right], eax
0x18014cdc6  mov     eax, [rbp+arg_20]
0x18014cdc9  jmp     short loc_18014CDD2
0x18014cdcb  mov     [rbp+var_38.right], eax
0x18014cdce  lea     eax, [r12+rsi]
0x18014cdd2  cmp     [rbp+arg_40], 0
0x18014cdd9  mov     [rbp+var_38.bottom], eax
0x18014cddc  jz      short loc_18014CDFA
0x18014cdde  mov     r8, [rbx+18h]
0x18014cde2  lea     rdx, [rbp+var_38]; struct tagRECT *
0x18014cde6  add     r8, 178h; struct tagRECT *
0x18014cded  lea     rcx, [rbp+var_38]; struct tagRECT *
0x18014cdf1  call    ?IntersectRect@CW32System@@SAHPEAUtagRECT@@PEBU2@1@Z; CW32System::IntersectRect(tagRECT *,tagRECT const *,tagRECT const *)
0x18014cdf6  test    eax, eax
0x18014cdf8  jz      short loc_18014CE42
0x18014cdfa  mov     rcx, [rbx+18h]
0x18014cdfe  lea     r8, [rbp+var_38]; struct RECTUV *
0x18014ce02  xorps   xmm0, xmm0
0x18014ce05  mov     [rsp+68h+var_48], 0; bool
0x18014ce0a  movups  xmmword ptr [rbp+var_28.left], xmm0
0x18014ce0e  mov     r9b, 1; bool
0x18014ce11  lea     rdx, [rbp+var_28]; struct tagRECT *
0x18014ce15  mov     rcx, [rcx+98h]; this
0x18014ce1c  call    ?RectFromRectuv@CDisplay@@QEBAXAEAUtagRECT@@AEBURECTUV@@_N2@Z; CDisplay::RectFromRectuv(tagRECT &,RECTUV const &,bool,bool)
0x18014ce21  mov     rax, [rbx+18h]
0x18014ce25  lea     rdx, [rbp+var_28]
0x18014ce29  mov     r8d, r14d
0x18014ce2c  mov     rcx, [rax+150h]
0x18014ce33  mov     rax, [rcx]
0x18014ce36  mov     rax, [rax+0F8h]
0x18014ce3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ce42  mov     rcx, [rbp+var_18]
0x18014ce46  xor     rcx, rsp; StackCookie
0x18014ce49  call    __security_check_cookie
0x18014ce4e  add     rsp, 68h
0x18014ce52  pop     r15
0x18014ce54  pop     r14
0x18014ce56  pop     r13
0x18014ce58  pop     r12
0x18014ce5a  pop     rdi
0x18014ce5b  pop     rsi
0x18014ce5c  pop     rbx
0x18014ce5d  pop     rbp
0x18014ce5e  retn
```
