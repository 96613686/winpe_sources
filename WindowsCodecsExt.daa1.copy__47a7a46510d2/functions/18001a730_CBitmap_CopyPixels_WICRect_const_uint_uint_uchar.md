# CBitmap::CopyPixels(WICRect const *,uint,uint,uchar *)

- ea: `0x18001a730`
- end: `0x18001a945`
- name: `?CopyPixels@CBitmap@@UEAAJPEBUWICRect@@IIPEAE@Z`
- size: `533`
- prototype: `int(CBitmap *__hidden this, const struct WICRect *, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002c5d0`

## callees

- `0x1800058c0`
- `0x180005c90`
- `0x18000f1d0`
- `0x1800171c4`
- `0x1800199d8`
- `0x18001a40c`
- `0x18001a730`
- `0x180021a30`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CBitmap::CopyPixels(
        CBitmap *this,
        const struct WICRect *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 *a5)
{
  int v10; // ebx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 v16; // rcx
  unsigned int v17; // [rsp+50h] [rbp-31h] BYREF
  __int64 v18; // [rsp+58h] [rbp-29h] BYREF
  int v19; // [rsp+60h] [rbp-21h] BYREF
  unsigned int v20; // [rsp+64h] [rbp-1Dh] BYREF
  int v21; // [rsp+68h] [rbp-19h] BYREF
  void *v22; // [rsp+70h] [rbp-11h] BYREF
  char *v23; // [rsp+78h] [rbp-9h] BYREF
  WICRect v24; // [rsp+80h] [rbp-1h] BYREF

  if ( !a5 )
    return 2147942487LL;
  v18 = 0;
  v24 = 0;
  v23 = (char *)this + 160;
  CMTALock::Enter((CBitmap *)((char *)this + 160));
  v10 = HrValidatePixelRects(a2, *((_DWORD *)this + 24), *((_DWORD *)this + 25), &v24, 0);
  if ( v10 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(CBitmap *, WICRect *, __int64, __int64 *))(*(_QWORD *)this + 72LL))(
            this,
            &v24,
            1,
            &v18);
    v10 = v11;
    if ( v11 < 0 )
    {
      if ( g_doStackCaptures )
        DoStackCapture(v11);
    }
  }
  v21 = 0;
  v20 = 0;
  if ( v10 >= 0 )
  {
    v12 = HrCheckBufferSize(*((unsigned int *)this + 28), a3, &v24, a4);
    v10 = v12;
    if ( v12 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, int *, unsigned int *))(*(_QWORD *)v18 + 24LL))(v18, &v21, &v20);
      v10 = v13;
      if ( v13 < 0 && g_doStackCaptures )
        DoStackCapture(v13);
    }
    else if ( g_doStackCaptures )
    {
      DoStackCapture(v12);
      v17 = 0;
      goto LABEL_19;
    }
  }
  v17 = 0;
  if ( v10 >= 0 )
  {
    v14 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v18 + 32LL))(v18, &v17);
    v10 = v14;
    if ( v14 < 0 )
    {
      if ( g_doStackCaptures )
        DoStackCapture(v14);
    }
  }
LABEL_19:
  v22 = 0;
  v19 = 0;
  if ( v10 >= 0 )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, int *, void **))(*(_QWORD *)v18 + 40LL))(v18, &v19, &v22);
    v10 = v15;
    if ( v15 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_26;
      goto LABEL_25;
    }
    v15 = CBitmap::CopyPixelsHelper(
            v16,
            *((unsigned int *)this + 28),
            (unsigned int)v24.Width,
            v20,
            v17,
            v19,
            v22,
            a3,
            a4,
            (__int64)a5);
    v10 = v15;
    if ( v15 < 0 && g_doStackCaptures )
LABEL_25:
      DoStackCapture(v15);
  }
LABEL_26:
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  CGuard<CMTALock>::~CGuard<CMTALock>(&v23);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001a730  push    rbp
0x18001a732  push    rbx
0x18001a733  push    rsi
0x18001a734  push    rdi
0x18001a735  push    r12
0x18001a737  push    r14
0x18001a739  push    r15
0x18001a73b  lea     rbp, [rsp-1Fh]
0x18001a740  sub     rsp, 0A0h
0x18001a747  mov     rax, cs:__security_cookie
0x18001a74e  xor     rax, rsp
0x18001a751  mov     [rbp+4Fh+var_40], rax
0x18001a755  mov     r15, [rbp+4Fh+arg_20]
0x18001a759  xor     r12d, r12d
0x18001a75c  mov     esi, r9d
0x18001a75f  mov     r14d, r8d
0x18001a762  mov     rbx, rdx
0x18001a765  mov     rdi, rcx
0x18001a768  test    r15, r15
0x18001a76b  jnz     short loc_18001A777
0x18001a76d  mov     eax, 80070057h
0x18001a772  jmp     loc_18001A927
0x18001a777  xorps   xmm0, xmm0
0x18001a77a  mov     [rbp+4Fh+var_78], r12
0x18001a77e  add     rcx, 0A0h; this
0x18001a785  movups  xmmword ptr [rbp+4Fh+var_50.X], xmm0
0x18001a789  mov     [rbp+4Fh+var_58], rcx
0x18001a78d  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18001a792  mov     r8d, [rdi+64h]; unsigned int
0x18001a796  lea     r9, [rbp+4Fh+var_50]; struct WICRect *
0x18001a79a  mov     edx, [rdi+60h]; unsigned int
0x18001a79d  mov     rcx, rbx; struct WICRect *
0x18001a7a0  mov     [rsp+0D0h+var_B0], r12; struct tagRECT *
0x18001a7a5  call    ?HrValidatePixelRects@@YAJPEBUWICRect@@IIPEAU1@PEAUtagRECT@@@Z; HrValidatePixelRects(WICRect const *,uint,uint,WICRect *,tagRECT *)
0x18001a7aa  mov     ebx, eax
0x18001a7ac  test    eax, eax
0x18001a7ae  js      short loc_18001A7E3
0x18001a7b0  mov     rax, [rdi]
0x18001a7b3  lea     r9, [rbp+4Fh+var_78]
0x18001a7b7  mov     r8d, 1
0x18001a7bd  lea     rdx, [rbp+4Fh+var_50]
0x18001a7c1  mov     rcx, rdi
0x18001a7c4  mov     rax, [rax+48h]
0x18001a7c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7cd  mov     ebx, eax
0x18001a7cf  test    eax, eax
0x18001a7d1  jns     short loc_18001A7E3
0x18001a7d3  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18001a7da  jz      short loc_18001A7E3
0x18001a7dc  mov     ecx, eax; int
0x18001a7de  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001a7e3  mov     [rbp+4Fh+var_68], r12d
0x18001a7e7  mov     [rbp+4Fh+var_6C], r12d
0x18001a7eb  test    ebx, ebx
0x18001a7ed  js      short loc_18001A84F
0x18001a7ef  mov     ecx, [rdi+70h]
0x18001a7f2  lea     r8, [rbp+4Fh+var_50]
0x18001a7f6  mov     r9d, esi
0x18001a7f9  mov     edx, r14d
0x18001a7fc  call    ?HrCheckBufferSize@@YAJW4Enum@MilPixelFormat@@IPEBUWICRect@@I@Z; HrCheckBufferSize(MilPixelFormat::Enum,uint,WICRect const *,uint)
0x18001a801  mov     ebx, eax
0x18001a803  test    eax, eax
0x18001a805  jns     short loc_18001A821
0x18001a807  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18001a80e  jz      short loc_18001A81D
0x18001a810  mov     ecx, eax; int
0x18001a812  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001a817  mov     [rbp+4Fh+var_80], r12d
0x18001a81b  jmp     short loc_18001A881
0x18001a81d  test    eax, eax
0x18001a81f  js      short loc_18001A84F
0x18001a821  mov     rcx, [rbp+4Fh+var_78]
0x18001a825  lea     r8, [rbp+4Fh+var_6C]
0x18001a829  lea     rdx, [rbp+4Fh+var_68]
0x18001a82d  mov     rax, [rcx]
0x18001a830  mov     rax, [rax+18h]
0x18001a834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a839  mov     ebx, eax
0x18001a83b  test    eax, eax
0x18001a83d  jns     short loc_18001A84F
0x18001a83f  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18001a846  jz      short loc_18001A84F
0x18001a848  mov     ecx, eax; int
0x18001a84a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001a84f  mov     [rbp+4Fh+var_80], r12d
0x18001a853  test    ebx, ebx
0x18001a855  js      short loc_18001A881
0x18001a857  mov     rcx, [rbp+4Fh+var_78]
0x18001a85b  lea     rdx, [rbp+4Fh+var_80]
0x18001a85f  mov     rax, [rcx]
0x18001a862  mov     rax, [rax+20h]
0x18001a866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a86b  mov     ebx, eax
0x18001a86d  test    eax, eax
0x18001a86f  jns     short loc_18001A881
0x18001a871  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18001a878  jz      short loc_18001A881
0x18001a87a  mov     ecx, eax; int
0x18001a87c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001a881  mov     [rbp+4Fh+var_60], r12
0x18001a885  mov     [rbp+4Fh+var_70], r12d
0x18001a889  test    ebx, ebx
0x18001a88b  js      short loc_18001A903
0x18001a88d  mov     rcx, [rbp+4Fh+var_78]
0x18001a891  lea     r8, [rbp+4Fh+var_60]
0x18001a895  lea     rdx, [rbp+4Fh+var_70]
0x18001a899  mov     rax, [rcx]
0x18001a89c  mov     rax, [rax+28h]
0x18001a8a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8a5  mov     ebx, eax
0x18001a8a7  test    eax, eax
0x18001a8a9  jns     short loc_18001A8B8
0x18001a8ab  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18001a8b2  jnz     short loc_18001A8FC
0x18001a8b4  test    eax, eax
0x18001a8b6  js      short loc_18001A903
0x18001a8b8  mov     rax, [rbp+4Fh+var_60]
0x18001a8bc  mov     r9d, [rbp+4Fh+var_6C]
0x18001a8c0  mov     r8d, [rbp+4Fh+var_50.Width]
0x18001a8c4  mov     edx, [rdi+70h]
0x18001a8c7  mov     [rsp+0D0h+var_88], r15
0x18001a8cc  mov     [rsp+0D0h+var_90], esi
0x18001a8d0  mov     [rsp+0D0h+var_98], r14d
0x18001a8d5  mov     [rsp+0D0h+var_A0], rax
0x18001a8da  mov     eax, [rbp+4Fh+var_70]
0x18001a8dd  mov     [rsp+0D0h+var_A8], eax
0x18001a8e1  mov     eax, [rbp+4Fh+var_80]
0x18001a8e4  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18001a8e8  call    ?CopyPixelsHelper@CBitmap@@AEAAJW4Enum@MilPixelFormat@@IIIIPEAEII1@Z; CBitmap::CopyPixelsHelper(MilPixelFormat::Enum,uint,uint,uint,uint,uchar *,uint,uint,uchar *)
0x18001a8ed  mov     ebx, eax
0x18001a8ef  test    eax, eax
0x18001a8f1  jns     short loc_18001A903
0x18001a8f3  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18001a8fa  jz      short loc_18001A903
0x18001a8fc  mov     ecx, eax; int
0x18001a8fe  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001a903  mov     rcx, [rbp+4Fh+var_78]
0x18001a907  test    rcx, rcx
0x18001a90a  jz      short loc_18001A91C
0x18001a90c  mov     rax, [rcx]
0x18001a90f  mov     rax, [rax+10h]
0x18001a913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a918  mov     [rbp+4Fh+var_78], r12
0x18001a91c  lea     rcx, [rbp+4Fh+var_58]
0x18001a920  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18001a925  mov     eax, ebx
0x18001a927  mov     rcx, [rbp+4Fh+var_40]
0x18001a92b  xor     rcx, rsp; StackCookie
0x18001a92e  call    __security_check_cookie
0x18001a933  add     rsp, 0A0h
0x18001a93a  pop     r15
0x18001a93c  pop     r14
0x18001a93e  pop     r12
0x18001a940  pop     rdi
0x18001a941  pop     rsi
0x18001a942  pop     rbx
0x18001a943  pop     rbp
0x18001a944  retn
```
