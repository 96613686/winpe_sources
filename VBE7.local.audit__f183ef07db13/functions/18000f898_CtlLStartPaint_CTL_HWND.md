# CtlLStartPaint(CTL *,HWND__ *)

- ea: `0x18000f898`
- end: `0x18000faf5`
- name: `?CtlLStartPaint@@YAJPEAUCTL@@PEAUHWND__@@@Z`
- size: `605`
- prototype: `__int64 __fastcall(struct CTL *, HWND)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800238cc`

## callees

- `0x18000f5b0`
- `0x18000f784`
- `0x18000f898`
- `0x1800171a4`
- `0x180021a90`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `USER32!BeginPaint` at `0x18000fa5b`
- `USER32!BeginPaint` at `0x18000fa5b`
- `USER32!EndPaint` at `0x18000faba`
- `USER32!EndPaint` at `0x18000faba`
- `USER32!GetUpdateRgn` at `0x18000f946`
- `USER32!GetUpdateRgn` at `0x18000f946`
- `GDI32!SetRectRgn` at `0x18000f993`
- `GDI32!SetRectRgn` at `0x18000f993`
- `GDI32!CreateRectRgn` at `0x18000f92a`
- `GDI32!CreateRectRgn` at `0x18000f962`
- `GDI32!CreateRectRgn` at `0x18000f92a`
- `GDI32!CreateRectRgn` at `0x18000f962`
- `GDI32!CombineRgn` at `0x18000f9a8`
- `GDI32!CombineRgn` at `0x18000f9a8`
- `GDI32!DeleteObject` at `0x18000f9cd`
- `GDI32!DeleteObject` at `0x18000fa4a`
- `GDI32!DeleteObject` at `0x18000f9cd`
- `GDI32!DeleteObject` at `0x18000fa4a`

## pseudocode

```c
__int64 __fastcall CtlLStartPaint(struct CTL *a1, HWND a2)
{
  __int64 v2; // rax
  __int64 v3; // r14
  HRGN v4; // rsi
  __int64 v5; // r13
  HRGN v6; // rdi
  int v7; // r15d
  int v9; // r15d
  int UpdateRgn; // r12d
  __int64 v11; // rax
  HRGN RectRgn; // rax
  __int64 i; // rdi
  HWND v14; // rdi
  HWND v15; // rdx
  __int64 result; // rax
  HWND hWnd[2]; // [rsp+30h] [rbp-69h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+40h] [rbp-59h] BYREF
  struct CTL *v19; // [rsp+88h] [rbp-11h]
  int v20; // [rsp+90h] [rbp-9h]
  __int64 v21; // [rsp+98h] [rbp-1h]
  struct tagRECT left; // [rsp+A0h] [rbp+7h] BYREF

  v2 = *((_QWORD *)a1 + 8);
  v3 = *((_QWORD *)a1 + 14);
  v4 = 0;
  v5 = *(_QWORD *)(v2 + 80);
  v6 = 0;
  v7 = *(_DWORD *)(v2 + 48) >> 4;
  hWnd[0] = a2;
  v9 = v7 & 1;
  UpdateRgn = 2;
  v11 = v9;
  if ( !v3 )
    goto LABEL_15;
  do
  {
    if ( (*(_DWORD *)(v3 + 40) & 0x100000) == 0 || (*(_BYTE *)(v3 + 40) & 4) == 0 && !v11 )
      goto LABEL_12;
    if ( !v4 )
    {
      RectRgn = CreateRectRgn(0, 0, 0, 0);
      v4 = RectRgn;
      if ( !RectRgn )
        break;
      UpdateRgn = GetUpdateRgn(hWnd[0], RectRgn, 0);
      if ( !UpdateRgn )
        break;
    }
    if ( !v6 )
    {
      v6 = CreateRectRgn(0, 0, 0, 0);
      if ( !v6 )
        goto LABEL_15;
    }
    CtlGetRectInParent((struct CTL *)v3, &left);
    SetRectRgn(v6, left.left, left.top, left.right, left.bottom);
    UpdateRgn = CombineRgn(v4, v4, v6, 4);
    if ( !UpdateRgn )
      break;
    v11 = v9;
LABEL_12:
    v3 = *(_QWORD *)(v3 + 96);
  }
  while ( v3 );
  if ( v6 )
    DeleteObject(v6);
LABEL_15:
  if ( *((char *)a1 + 40) < 0
    && UpdateRgn != 1
    && !v9
    && !Mode_break
    && ***((int ***)a1 + 6) < 0
    && (*((_BYTE *)a1 + 368) & 0x20) == 0
    && (unsigned int)EvtFWillFire(a1, 0x16u) )
  {
    for ( i = *((_QWORD *)a1 + 14); i; i = *(_QWORD *)(i + 96) )
    {
      if ( (*(_DWORD *)(i + 40) & 0x200000) != 0 )
        CtlInvRectCheck((struct CTL *)i, 0, 1, 1);
    }
  }
  if ( v4 )
    DeleteObject(v4);
  v14 = hWnd[0];
  BeginPaint(hWnd[0], &Paint);
  v19 = a1;
  v20 = 1;
  v21 = *(_QWORD *)(v5 + 1320);
  *(_QWORD *)(v5 + 1320) = &Paint;
  if ( UpdateRgn != 1 )
  {
    v15 = (HWND)*((_QWORD *)a1 + 11);
    LODWORD(hWnd[0]) = 0;
    CommonGizWndProc(a1, v15, 0xFu, (unsigned __int64)Paint.hdc, 0, (unsigned int *)hWnd);
  }
  if ( v20 )
    EndPaint(v14, &Paint);
  result = 1;
  *(_QWORD *)(v5 + 1320) = v21;
  return result;
}

```

## disassembly

```asm
0x18000f898  mov     [rsp-8+arg_10], rbx
0x18000f89d  push    rbp
0x18000f89e  push    rsi
0x18000f89f  push    rdi
0x18000f8a0  push    r12
0x18000f8a2  push    r13
0x18000f8a4  push    r14
0x18000f8a6  push    r15
0x18000f8a8  lea     rbp, [rsp-27h]
0x18000f8ad  mov     eax, 0C0h
0x18000f8b2  call    _alloca_probe
0x18000f8b7  sub     rsp, rax
0x18000f8ba  mov     rax, cs:__security_cookie
0x18000f8c1  xor     rax, rsp
0x18000f8c4  mov     [rbp+57h+var_40], rax
0x18000f8c8  mov     rax, [rcx+40h]
0x18000f8cc  mov     r14, [rcx+70h]
0x18000f8d0  xor     esi, esi
0x18000f8d2  mov     r15d, [rax+30h]
0x18000f8d6  mov     r13, [rax+50h]
0x18000f8da  xor     edi, edi
0x18000f8dc  shr     r15d, 4
0x18000f8e0  mov     [rbp+57h+hWnd], rdx
0x18000f8e4  mov     rbx, rcx
0x18000f8e7  and     r15d, 1
0x18000f8eb  mov     r12d, 2
0x18000f8f1  movsxd  rax, r15d
0x18000f8f4  test    r14, r14
0x18000f8f7  jz      loc_18000F9D3
0x18000f8fd  test    dword ptr [r14+28h], 100000h
0x18000f905  jz      loc_18000F9B8
0x18000f90b  test    byte ptr [r14+28h], 4
0x18000f910  jnz     short loc_18000F91B
0x18000f912  test    rax, rax
0x18000f915  jz      loc_18000F9B8
0x18000f91b  test    rsi, rsi
0x18000f91e  jnz     short loc_18000F953
0x18000f920  xor     r9d, r9d; y2
0x18000f923  xor     r8d, r8d; x2
0x18000f926  xor     edx, edx; y1
0x18000f928  xor     ecx, ecx; x1
0x18000f92a  call    cs:__imp_CreateRectRgn
0x18000f930  mov     rsi, rax
0x18000f933  test    rax, rax
0x18000f936  jz      loc_18000F9C5
0x18000f93c  mov     rcx, [rbp+57h+hWnd]; hWnd
0x18000f940  xor     r8d, r8d; bErase
0x18000f943  mov     rdx, rax; hRgn
0x18000f946  call    cs:__imp_GetUpdateRgn
0x18000f94c  mov     r12d, eax
0x18000f94f  test    eax, eax
0x18000f951  jz      short loc_18000F9C5
0x18000f953  test    rdi, rdi
0x18000f956  jnz     short loc_18000F970
0x18000f958  xor     r9d, r9d; y2
0x18000f95b  xor     r8d, r8d; x2
0x18000f95e  xor     edx, edx; y1
0x18000f960  xor     ecx, ecx; x1
0x18000f962  call    cs:__imp_CreateRectRgn
0x18000f968  mov     rdi, rax
0x18000f96b  test    rax, rax
0x18000f96e  jz      short loc_18000F9D3
0x18000f970  lea     rdx, [rbp+57h+left]; struct tagRECT *
0x18000f974  mov     rcx, r14; struct CTL *
0x18000f977  call    ?CtlGetRectInParent@@YAXPEAUCTL@@PEAUtagRECT@@@Z; CtlGetRectInParent(CTL *,tagRECT *)
0x18000f97c  mov     r11d, [rbp+57h+var_44]
0x18000f980  mov     r9d, [rbp+57h+right]; right
0x18000f984  mov     r8d, [rbp+57h+top]; top
0x18000f988  mov     edx, [rbp+57h+left]; left
0x18000f98b  mov     rcx, rdi; hrgn
0x18000f98e  mov     [rsp+0F0h+bottom], r11d; bottom
0x18000f993  call    cs:__imp_SetRectRgn
0x18000f999  mov     r9d, 4; iMode
0x18000f99f  mov     r8, rdi; hrgnSrc2
0x18000f9a2  mov     rdx, rsi; hrgnSrc1
0x18000f9a5  mov     rcx, rsi; hrgnDst
0x18000f9a8  call    cs:__imp_CombineRgn
0x18000f9ae  mov     r12d, eax
0x18000f9b1  test    eax, eax
0x18000f9b3  jz      short loc_18000F9C5
0x18000f9b5  movsxd  rax, r15d
0x18000f9b8  mov     r14, [r14+60h]
0x18000f9bc  test    r14, r14
0x18000f9bf  jnz     loc_18000F8FD
0x18000f9c5  test    rdi, rdi
0x18000f9c8  jz      short loc_18000F9D3
0x18000f9ca  mov     rcx, rdi; ho
0x18000f9cd  call    cs:__imp_DeleteObject
0x18000f9d3  test    byte ptr [rbx+28h], 80h
0x18000f9d7  mov     r14d, 1
0x18000f9dd  jz      short loc_18000FA42
0x18000f9df  cmp     r12d, r14d
0x18000f9e2  jz      short loc_18000FA42
0x18000f9e4  test    r15d, r15d
0x18000f9e7  jnz     short loc_18000FA42
0x18000f9e9  cmp     cs:?Mode_break@@3W4BREAKMODE@@A, r15d; BREAKMODE Mode_break
0x18000f9f0  jnz     short loc_18000FA42
0x18000f9f2  mov     rax, [rbx+30h]
0x18000f9f6  mov     rcx, [rax]
0x18000f9f9  test    dword ptr [rcx], 80000000h
0x18000f9ff  jz      short loc_18000FA42
0x18000fa01  test    byte ptr [rbx+170h], 20h
0x18000fa08  jnz     short loc_18000FA42
0x18000fa0a  lea     edx, [r14+15h]; unsigned int
0x18000fa0e  mov     rcx, rbx; struct CTL *
0x18000fa11  call    ?EvtFWillFire@@YAHPEAUCTL@@I@Z; EvtFWillFire(CTL *,uint)
0x18000fa16  test    eax, eax
0x18000fa18  jz      short loc_18000FA42
0x18000fa1a  mov     rdi, [rbx+70h]
0x18000fa1e  jmp     short loc_18000FA3D
0x18000fa20  test    dword ptr [rdi+28h], 200000h
0x18000fa27  jz      short loc_18000FA39
0x18000fa29  mov     r9d, r14d; int
0x18000fa2c  mov     r8d, r14d; int
0x18000fa2f  xor     edx, edx; struct tagRECT *
0x18000fa31  mov     rcx, rdi; struct CTL *
0x18000fa34  call    ?CtlInvRectCheck@@YAXPEAUCTL@@PEAUtagRECT@@HH@Z; CtlInvRectCheck(CTL *,tagRECT *,int,int)
0x18000fa39  mov     rdi, [rdi+60h]
0x18000fa3d  test    rdi, rdi
0x18000fa40  jnz     short loc_18000FA20
0x18000fa42  test    rsi, rsi
0x18000fa45  jz      short loc_18000FA50
0x18000fa47  mov     rcx, rsi; ho
0x18000fa4a  call    cs:__imp_DeleteObject
0x18000fa50  mov     rdi, [rbp+57h+hWnd]
0x18000fa54  lea     rdx, [rbp+57h+Paint]; lpPaint
0x18000fa58  mov     rcx, rdi; hWnd
0x18000fa5b  call    cs:__imp_BeginPaint
0x18000fa61  mov     [rbp+57h+var_68], rbx
0x18000fa65  mov     [rbp+57h+var_60], r14d
0x18000fa69  mov     rax, [r13+528h]
0x18000fa70  mov     [rbp+57h+var_58], rax
0x18000fa74  lea     rax, [rbp+57h+Paint]
0x18000fa78  mov     [r13+528h], rax
0x18000fa7f  cmp     r12d, r14d
0x18000fa82  jz      short loc_18000FAAD
0x18000fa84  mov     r9, [rbp+57h+Paint.hdc]; unsigned __int64
0x18000fa88  mov     rdx, [rbx+58h]; HWND
0x18000fa8c  and     dword ptr [rbp+57h+hWnd], 0
0x18000fa90  lea     rax, [rbp+57h+hWnd]
0x18000fa94  mov     r8d, 0Fh; unsigned int
0x18000fa9a  mov     rcx, rbx; struct CTL *
0x18000fa9d  mov     [rsp+0F0h+var_C8], rax; unsigned int *
0x18000faa2  and     qword ptr [rsp+0F0h+bottom], 0
0x18000faa8  call    ?CommonGizWndProc@@YA_JPEAUCTL@@PEAUHWND__@@I_K_JPEAK@Z; CommonGizWndProc(CTL *,HWND__ *,uint,unsigned __int64,__int64,ulong *)
0x18000faad  cmp     [rbp+57h+var_60], 0
0x18000fab1  jz      short loc_18000FAC0
0x18000fab3  lea     rdx, [rbp+57h+Paint]; lpPaint
0x18000fab7  mov     rcx, rdi; hWnd
0x18000faba  call    cs:__imp_EndPaint
0x18000fac0  mov     rcx, [rbp+57h+var_58]
0x18000fac4  mov     eax, r14d
0x18000fac7  mov     [r13+528h], rcx
0x18000face  mov     rcx, [rbp+57h+var_40]
0x18000fad2  xor     rcx, rsp; StackCookie
0x18000fad5  call    __security_check_cookie
0x18000fada  mov     rbx, [rsp+0F0h+arg_10]
0x18000fae2  add     rsp, 0C0h
0x18000fae9  pop     r15
0x18000faeb  pop     r14
0x18000faed  pop     r13
0x18000faef  pop     r12
0x18000faf1  pop     rdi
0x18000faf2  pop     rsi
0x18000faf3  pop     rbp
0x18000faf4  retn
```
