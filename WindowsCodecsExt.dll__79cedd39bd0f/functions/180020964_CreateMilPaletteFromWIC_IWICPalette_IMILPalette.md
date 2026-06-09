# CreateMilPaletteFromWIC(IWICPalette *,IMILPalette * *)

- ea: `0x180020964`
- end: `0x180020ad5`
- name: `?CreateMilPaletteFromWIC@@YAJPEAUIWICPalette@@PEAPEAUIMILPalette@@@Z`
- size: `369`
- prototype: `__int64 __fastcall(struct IWICPalette *, struct IMILPalette **)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180020570`
- `0x1800206d0`
- `0x1800207a0`

## callees

- `0x1800058c0`
- `0x1800096bc`
- `0x18000f1d0`
- `0x1800171c4`
- `0x180020964`
- `0x1800215e8`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CreateMilPaletteFromWIC(struct IWICPalette *a1, struct IMILPalette **a2)
{
  struct IWICPaletteVtbl *lpVtbl; // rax
  int v5; // ebx
  _DWORD *v6; // rdi
  struct IMILPalette *v7; // rcx
  struct IMILPalette *v8; // rbx
  __int64 v9; // rcx
  struct IMILPalette *v10; // rcx
  struct IMILPalette *v12; // [rsp+40h] [rbp+8h] BYREF
  char *v13; // [rsp+48h] [rbp+10h] BYREF

  lpVtbl = a1->lpVtbl;
  *a2 = 0;
  v12 = 0;
  v5 = ((__int64 (__fastcall *)(struct IWICPalette *, GUID *, struct IMILPalette **))lpVtbl->QueryInterface)(
         a1,
         &IID_IMILPalette,
         &v12);
  if ( v5 >= 0 )
  {
LABEL_13:
    v10 = v12;
    *a2 = v12;
    if ( !v10 )
      return (unsigned int)v5;
    (*(void (__fastcall **)(struct IMILPalette *))(*(_QWORD *)v10 + 8LL))(v10);
    goto LABEL_15;
  }
  v6 = operator new(0x60u);
  if ( v6 )
  {
    v6[2] = 0;
    *(_QWORD *)v6 = &CMILCOMBase::`vftable';
    _InterlockedIncrement(&g_cActiveObjects);
    CMTALock::CMTALock((CMTALock *)(v6 + 4));
    *((_QWORD *)v6 + 11) = 0;
    *(_QWORD *)v6 = &CMilPaletteFromWIC::`vftable'{for `CMILCOMBase'};
    v7 = (struct IMILPalette *)(v6 + 18);
    *((_QWORD *)v6 + 2) = &CMilPaletteFromWIC::`vftable'{for `CMTALock'};
    *((_QWORD *)v6 + 9) = &CMilPaletteFromWIC::`vftable'{for `IMILPalette'};
    *((_QWORD *)v6 + 10) = &CMilPaletteFromWIC::`vftable'{for `IWICPalette'};
  }
  else
  {
    v7 = 0;
  }
  v12 = v7;
  if ( v7 )
  {
    (*(void (__fastcall **)(struct IMILPalette *))(*(_QWORD *)v7 + 8LL))(v7);
    v8 = v12;
    if ( v12 )
      v8 = (struct IMILPalette *)((char *)v12 - 72);
    v13 = (char *)v8 + 16;
    CMTALock::Enter((struct IMILPalette *)((char *)v8 + 16));
    v9 = *((_QWORD *)v8 + 11);
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)v8 + 11) = a1;
    ((void (__fastcall *)(struct IWICPalette *))a1->lpVtbl->AddRef)(a1);
    CGuard<CMTALock>::~CGuard<CMTALock>(&v13);
    v5 = 0;
    goto LABEL_13;
  }
  v5 = -2147024882;
  if ( !g_doStackCaptures )
    goto LABEL_16;
  DoStackCapture(-2147024882);
LABEL_15:
  v7 = v12;
LABEL_16:
  if ( v7 )
    (*(void (__fastcall **)(struct IMILPalette *))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180020964  mov     [rsp+arg_10], rbx
0x180020969  push    rsi
0x18002096a  push    rdi
0x18002096b  push    r14
0x18002096d  sub     rsp, 20h
0x180020971  mov     rax, [rcx]
0x180020974  lea     r8, [rsp+38h+arg_0]
0x180020979  mov     r14, rdx
0x18002097c  mov     qword ptr [rdx], 0
0x180020983  lea     rdx, IID_IMILPalette
0x18002098a  mov     [rsp+38h+arg_0], 0
0x180020993  mov     rsi, rcx
0x180020996  mov     rax, [rax]
0x180020999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002099e  mov     ebx, eax
0x1800209a0  test    eax, eax
0x1800209a2  jns     loc_180020A96
0x1800209a8  mov     ecx, 60h ; '`'; Size
0x1800209ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800209b2  mov     rdi, rax
0x1800209b5  test    rax, rax
0x1800209b8  jz      short loc_180020A14
0x1800209ba  lea     rax, ??_7CMILCOMBase@@6B@; const CMILCOMBase::`vftable'
0x1800209c1  mov     dword ptr [rdi+8], 0
0x1800209c8  mov     [rdi], rax
0x1800209cb  lock inc cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x1800209d2  lea     rcx, [rdi+10h]; this
0x1800209d6  call    ??0CMTALock@@QEAA@XZ; CMTALock::CMTALock(void)
0x1800209db  lea     rax, ??_7CMilPaletteFromWIC@@6BCMILCOMBase@@@; const CMilPaletteFromWIC::`vftable'{for `CMILCOMBase'}
0x1800209e2  mov     qword ptr [rdi+58h], 0
0x1800209ea  mov     [rdi], rax
0x1800209ed  lea     rcx, [rdi+48h]
0x1800209f1  lea     rax, ??_7CMilPaletteFromWIC@@6BCMTALock@@@; const CMilPaletteFromWIC::`vftable'{for `CMTALock'}
0x1800209f8  mov     [rdi+10h], rax
0x1800209fc  lea     rax, ??_7CMilPaletteFromWIC@@6BIMILPalette@@@; const CMilPaletteFromWIC::`vftable'{for `IMILPalette'}
0x180020a03  mov     [rdi+48h], rax
0x180020a07  lea     rax, ??_7CMilPaletteFromWIC@@6BIWICPalette@@@; const CMilPaletteFromWIC::`vftable'{for `IWICPalette'}
0x180020a0e  mov     [rdi+50h], rax
0x180020a12  jmp     short loc_180020A16
0x180020a14  xor     ecx, ecx
0x180020a16  mov     [rsp+38h+arg_0], rcx
0x180020a1b  test    rcx, rcx
0x180020a1e  jnz     short loc_180020A3A
0x180020a20  cmp     cs:?g_doStackCaptures@@3HA, ecx; int g_doStackCaptures
0x180020a26  mov     ebx, 8007000Eh
0x180020a2b  jz      loc_180020AB4
0x180020a31  mov     ecx, ebx; int
0x180020a33  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180020a38  jmp     short loc_180020AAF
0x180020a3a  mov     rax, [rcx]
0x180020a3d  mov     rax, [rax+8]
0x180020a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a46  mov     rbx, [rsp+38h+arg_0]
0x180020a4b  test    rbx, rbx
0x180020a4e  jz      short loc_180020A54
0x180020a50  add     rbx, 0FFFFFFFFFFFFFFB8h
0x180020a54  lea     rcx, [rbx+10h]; this
0x180020a58  mov     [rsp+38h+arg_8], rcx
0x180020a5d  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x180020a62  mov     rcx, [rbx+58h]
0x180020a66  test    rcx, rcx
0x180020a69  jz      short loc_180020A77
0x180020a6b  mov     rax, [rcx]
0x180020a6e  mov     rax, [rax+10h]
0x180020a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a77  mov     [rbx+58h], rsi
0x180020a7b  mov     rcx, rsi
0x180020a7e  mov     rax, [rsi]
0x180020a81  mov     rax, [rax+8]
0x180020a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a8a  lea     rcx, [rsp+38h+arg_8]
0x180020a8f  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x180020a94  xor     ebx, ebx
0x180020a96  mov     rcx, [rsp+38h+arg_0]
0x180020a9b  mov     [r14], rcx
0x180020a9e  test    rcx, rcx
0x180020aa1  jz      short loc_180020AC5
0x180020aa3  mov     rax, [rcx]
0x180020aa6  mov     rax, [rax+8]
0x180020aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020aaf  mov     rcx, [rsp+38h+arg_0]
0x180020ab4  test    rcx, rcx
0x180020ab7  jz      short loc_180020AC5
0x180020ab9  mov     rax, [rcx]
0x180020abc  mov     rax, [rax+10h]
0x180020ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ac5  mov     eax, ebx
0x180020ac7  mov     rbx, [rsp+38h+arg_10]
0x180020acc  add     rsp, 20h
0x180020ad0  pop     r14
0x180020ad2  pop     rdi
0x180020ad3  pop     rsi
0x180020ad4  retn
```
