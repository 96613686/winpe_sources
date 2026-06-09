# COleClientItem::OnDeactivateUI(int)

- ea: `0x180084750`
- end: `0x1800849a1`
- name: `?OnDeactivateUI@COleClientItem@@UEAAXH@Z`
- size: `593`
- prototype: `void __fastcall(COleClientItem *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18009f330`

## callees

- `0x180013a90`
- `0x180014a00`
- `0x180026a40`
- `0x18002da20`
- `0x18005f920`
- `0x180084750`
- `0x1800d7010`

## import_xrefs

- `USER32!GetActiveWindow` at `0x180084983`
- `USER32!GetActiveWindow` at `0x180084983`
- `OLE32!OleSetMenuDescriptor` at `0x1800848bc`
- `OLE32!OleSetMenuDescriptor` at `0x1800848e3`
- `OLE32!OleSetMenuDescriptor` at `0x1800848bc`
- `OLE32!OleSetMenuDescriptor` at `0x1800848e3`

## pseudocode

```c
void __fastcall COleClientItem::OnDeactivateUI(COleClientItem *this)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rcx
  CWnd *MainWnd; // rax
  struct CWnd *TopLevelParent; // rdi
  HWND v12; // rbx
  _DWORD *v13; // [rsp+40h] [rbp+8h] BYREF
  _DWORD *v14; // [rsp+50h] [rbp+18h] BYREF

  if ( *((_DWORD *)this + 36) != 3 )
  {
    (*(void (__fastcall **)(COleClientItem *, __int64, __int64))(*(_QWORD *)this + 232LL))(this, 4, 3);
    *((_DWORD *)this + 36) = 3;
  }
  if ( *((_QWORD *)this + 19)
    && (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 208LL))(*((_QWORD *)this + 8)) )
  {
    CWnd::ModifyStyle(*((CWnd **)this + 19), 0x2000000u, *((_DWORD *)this + 40) & 0x2000000, 0);
  }
  v2 = *(_QWORD *)this;
  v13 = 0;
  v14 = 0;
  if ( (*(unsigned int (__fastcall **)(COleClientItem *, _DWORD **, _DWORD **, _QWORD))(v2 + 328))(this, &v13, &v14, 0) )
  {
    if ( !v13 )
      AfxThrowInvalidArgException();
    v13[82] |= 2u;
    if ( (*(unsigned int (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v13 + 448LL))(v13, 3) )
      v13[82] |= 0xCu;
    if ( v14 )
    {
      v14[82] |= 2u;
      if ( (*(unsigned int (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v14 + 448LL))(v14, 3) )
        v14[82] |= 0xCu;
    }
  }
  v3 = *((_QWORD *)this + 21);
  if ( v3 )
  {
    (*(void (__fastcall **)(COleClientItem *, _QWORD, __int64))(*(_QWORD *)this + 376LL))(this, *(_QWORD *)(v3 + 64), 1);
    OleSetMenuDescriptor(0, *(HWND *)(*(_QWORD *)(*((_QWORD *)this + 21) + 64LL) + 64LL), 0, 0, 0);
    v4 = *((_QWORD *)this + 22);
    if ( v4 )
      OleSetMenuDescriptor(0, *(HWND *)(*(_QWORD *)(v4 + 64) + 64LL), 0, 0, 0);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 21) + 64LL) + 488LL))(
      *(_QWORD *)(*((_QWORD *)this + 21) + 64LL),
      0);
    v5 = *((_QWORD *)this + 21);
    v6 = *(_QWORD *)(v5 + 64);
    if ( *(_QWORD *)(v6 + 184) == v5 )
      *(_QWORD *)(v6 + 184) = 0;
    v7 = *((_QWORD *)this + 22);
    if ( v7 )
    {
      (*(void (__fastcall **)(COleClientItem *, _QWORD, __int64))(*(_QWORD *)this + 376LL))(
        this,
        *(_QWORD *)(v7 + 64),
        1);
      v8 = *((_QWORD *)this + 22);
      v9 = *(_QWORD *)(v8 + 64);
      if ( *(_QWORD *)(v9 + 184) == v8 )
        *(_QWORD *)(v9 + 184) = 0;
    }
  }
  *((_QWORD *)this + 23) = 0;
  MainWnd = AfxGetMainWnd();
  if ( MainWnd )
  {
    TopLevelParent = CWnd::GetTopLevelParent(MainWnd);
    v12 = (HWND)*((_QWORD *)TopLevelParent + 8);
    if ( GetActiveWindow() == v12 )
      CWnd::SetFocus(TopLevelParent);
  }
}

```

## disassembly

```asm
0x180084750  mov     [rsp+arg_8], rbx
0x180084755  push    rdi
0x180084756  sub     rsp, 30h
0x18008475a  cmp     dword ptr [rcx+90h], 3
0x180084761  mov     rbx, rcx
0x180084764  jz      short loc_180084788
0x180084766  mov     rax, [rcx]
0x180084769  mov     edx, 4
0x18008476e  mov     rax, [rax+0E8h]
0x180084775  lea     r8d, [rdx-1]
0x180084779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008477e  mov     dword ptr [rbx+90h], 3
0x180084788  xor     edi, edi
0x18008478a  cmp     [rbx+98h], rdi
0x180084791  jz      short loc_1800847C9
0x180084793  mov     rcx, [rbx+40h]
0x180084797  mov     rax, [rcx]
0x18008479a  mov     rax, [rax+0D0h]
0x1800847a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800847a6  test    rax, rax
0x1800847a9  jz      short loc_1800847C9
0x1800847ab  mov     r8d, [rbx+0A0h]
0x1800847b2  mov     edx, 2000000h; unsigned int
0x1800847b7  mov     rcx, [rbx+98h]; this
0x1800847be  and     r8d, edx; unsigned int
0x1800847c1  xor     r9d, r9d; unsigned int
0x1800847c4  call    ?ModifyStyle@CWnd@@QEAAHKKI@Z; CWnd::ModifyStyle(ulong,ulong,uint)
0x1800847c9  mov     rax, [rbx]
0x1800847cc  lea     r8, [rsp+38h+arg_10]
0x1800847d1  xor     r9d, r9d
0x1800847d4  mov     [rsp+38h+arg_0], rdi
0x1800847d9  lea     rdx, [rsp+38h+arg_0]
0x1800847de  mov     [rsp+38h+arg_10], rdi
0x1800847e3  mov     rcx, rbx
0x1800847e6  mov     rax, [rax+148h]
0x1800847ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800847f2  test    eax, eax
0x1800847f4  jz      short loc_180084874
0x1800847f6  mov     rax, [rsp+38h+arg_0]
0x1800847fb  test    rax, rax
0x1800847fe  jnz     short loc_180084806
0x180084800  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
0x180084806  or      dword ptr [rax+148h], 2
0x18008480d  xor     r8d, r8d
0x180084810  mov     rcx, [rsp+38h+arg_0]
0x180084815  lea     edx, [r8+3]
0x180084819  mov     rax, [rcx]
0x18008481c  mov     rax, [rax+1C0h]
0x180084823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084828  test    eax, eax
0x18008482a  jz      short loc_180084838
0x18008482c  mov     rax, [rsp+38h+arg_0]
0x180084831  or      dword ptr [rax+148h], 0Ch
0x180084838  mov     rax, [rsp+38h+arg_10]
0x18008483d  test    rax, rax
0x180084840  jz      short loc_180084874
0x180084842  or      dword ptr [rax+148h], 2
0x180084849  xor     r8d, r8d
0x18008484c  mov     rcx, [rsp+38h+arg_10]
0x180084851  lea     edx, [r8+3]
0x180084855  mov     rax, [rcx]
0x180084858  mov     rax, [rax+1C0h]
0x18008485f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084864  test    eax, eax
0x180084866  jz      short loc_180084874
0x180084868  mov     rax, [rsp+38h+arg_10]
0x18008486d  or      dword ptr [rax+148h], 0Ch
0x180084874  mov     rdx, [rbx+0A8h]
0x18008487b  test    rdx, rdx
0x18008487e  jz      loc_180084963
0x180084884  mov     rax, [rbx]
0x180084887  mov     r8d, 1
0x18008488d  mov     rdx, [rdx+40h]
0x180084891  mov     rcx, rbx
0x180084894  mov     rax, [rax+178h]
0x18008489b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800848a0  mov     rax, [rbx+0A8h]
0x1800848a7  xor     r9d, r9d; lpFrame
0x1800848aa  xor     r8d, r8d; hwndActiveObject
0x1800848ad  mov     [rsp+38h+lpActiveObj], rdi; lpActiveObj
0x1800848b2  xor     ecx, ecx; holemenu
0x1800848b4  mov     rdx, [rax+40h]
0x1800848b8  mov     rdx, [rdx+40h]; hwndFrame
0x1800848bc  call    cs:__imp_OleSetMenuDescriptor
0x1800848c2  mov     rdx, [rbx+0B0h]
0x1800848c9  test    rdx, rdx
0x1800848cc  jz      short loc_1800848E9
0x1800848ce  mov     rdx, [rdx+40h]
0x1800848d2  xor     r9d, r9d; lpFrame
0x1800848d5  xor     r8d, r8d; hwndActiveObject
0x1800848d8  mov     [rsp+38h+lpActiveObj], rdi; lpActiveObj
0x1800848dd  xor     ecx, ecx; holemenu
0x1800848df  mov     rdx, [rdx+40h]; hwndFrame
0x1800848e3  call    cs:__imp_OleSetMenuDescriptor
0x1800848e9  mov     rax, [rbx+0A8h]
0x1800848f0  xor     edx, edx
0x1800848f2  mov     rcx, [rax+40h]
0x1800848f6  mov     rax, [rcx]
0x1800848f9  mov     rax, [rax+1E8h]
0x180084900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084905  mov     rax, [rbx+0A8h]
0x18008490c  mov     rcx, [rax+40h]
0x180084910  cmp     [rcx+0B8h], rax
0x180084917  jnz     short loc_180084920
0x180084919  mov     [rcx+0B8h], rdi
0x180084920  mov     rdx, [rbx+0B0h]
0x180084927  test    rdx, rdx
0x18008492a  jz      short loc_180084963
0x18008492c  mov     rax, [rbx]
0x18008492f  mov     r8d, 1
0x180084935  mov     rdx, [rdx+40h]
0x180084939  mov     rcx, rbx
0x18008493c  mov     rax, [rax+178h]
0x180084943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084948  mov     rax, [rbx+0B0h]
0x18008494f  mov     rcx, [rax+40h]
0x180084953  cmp     [rcx+0B8h], rax
0x18008495a  jnz     short loc_180084963
0x18008495c  mov     [rcx+0B8h], rdi
0x180084963  mov     [rbx+0B8h], rdi
0x18008496a  call    ?AfxGetMainWnd@@YAPEAVCWnd@@XZ; AfxGetMainWnd(void)
0x18008496f  test    rax, rax
0x180084972  jz      short loc_180084996
0x180084974  mov     rcx, rax; this
0x180084977  call    ?GetTopLevelParent@CWnd@@QEBAPEAV1@XZ; CWnd::GetTopLevelParent(void)
0x18008497c  mov     rdi, rax
0x18008497f  mov     rbx, [rax+40h]
0x180084983  call    cs:__imp_GetActiveWindow
0x180084989  cmp     rax, rbx
0x18008498c  jnz     short loc_180084996
0x18008498e  mov     rcx, rdi; this
0x180084991  call    ?SetFocus@CWnd@@QEAAPEAV1@XZ; CWnd::SetFocus(void)
0x180084996  mov     rbx, [rsp+38h+arg_8]
0x18008499b  add     rsp, 30h
0x18008499f  pop     rdi
0x1800849a0  retn
```
