# CIcmColorTransform::CopyPixels(WICRect const *,uint,uint,WICBitmapTransformOptions,WICPlanarOptions,WICBitmapPlane const *,uint)

- ea: `0x180005370`
- end: `0x1800054c3`
- name: `?CopyPixels@CIcmColorTransform@@UEAAJPEBUWICRect@@IIW4WICBitmapTransformOptions@@W4WICPlanarOptions@@PEBUWICBitmapPlane@@I@Z`
- size: `339`
- prototype: `__int64 __fastcall(CIcmColorTransform *this, const struct WICRect *, unsigned int, unsigned int, enum WICBitmapTransformOptions, enum WICPlanarOptions, const struct WICBitmapPlane *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004abc`
- `0x180005370`
- `0x1800058c0`
- `0x1800058e0`
- `0x1800171c4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CIcmColorTransform::CopyPixels(
        CIcmColorTransform *this,
        const struct WICRect *a2,
        unsigned int a3,
        unsigned int a4,
        enum WICBitmapTransformOptions a5,
        enum WICPlanarOptions a6,
        const struct WICBitmapPlane *a7,
        unsigned int a8)
{
  CMTALock *v8; // rsi
  __int64 v13; // rcx
  unsigned int v14; // ebx
  int v16; // eax
  int v17; // ecx

  v8 = (CIcmColorTransform *)((char *)this - 96);
  CMTALock::Enter((CIcmColorTransform *)((char *)this - 96));
  if ( !a7 )
    goto LABEL_7;
  v13 = *((_QWORD *)this + 17);
  if ( v13 && *((_DWORD *)this + 30) )
  {
    v16 = (*(__int64 (__fastcall **)(__int64, const struct WICRect *, _QWORD, _QWORD, enum WICBitmapTransformOptions, enum WICPlanarOptions, const struct WICBitmapPlane *, unsigned int))(*(_QWORD *)v13 + 32LL))(
            v13,
            a2,
            a3,
            a4,
            a5,
            a6,
            a7,
            a8);
  }
  else
  {
    if ( a8 - 2 > 1 || (a5 & 0xFFFFFFE4) != 0 || (a6 & 0xFFFFFFFE) != 0 )
    {
LABEL_7:
      v14 = -2147024809;
LABEL_8:
      if ( !g_doStackCaptures )
        goto LABEL_9;
      v17 = v14;
LABEL_16:
      DoStackCapture(v17);
      goto LABEL_9;
    }
    if ( !v13 )
    {
      v14 = -2003292287;
      goto LABEL_8;
    }
    v16 = CIcmColorTransform::EnsurePlanarTransform((CIcmColorTransform *)((char *)this - 112), a3, a4, a5, a6, a7, a8);
    v14 = v16;
    if ( v16 < 0 )
    {
LABEL_14:
      if ( !g_doStackCaptures )
        goto LABEL_9;
      v17 = v16;
      goto LABEL_16;
    }
    v16 = (*(__int64 (__fastcall **)(_QWORD, const struct WICRect *, const struct WICBitmapPlane *, _QWORD))(**((_QWORD **)this + 18) + 32LL))(
            *((_QWORD *)this + 18),
            a2,
            a7,
            a8);
  }
  v14 = v16;
  if ( v16 < 0 )
    goto LABEL_14;
LABEL_9:
  if ( v8 )
    CMTALock::Leave(v8);
  return v14;
}

```

## disassembly

```asm
0x180005370  push    rbx
0x180005372  push    rbp
0x180005373  push    rsi
0x180005374  push    rdi
0x180005375  push    r12
0x180005377  push    r14
0x180005379  push    r15
0x18000537b  sub     rsp, 50h
0x18000537f  lea     rsi, [rcx-60h]
0x180005383  mov     rdi, rcx
0x180005386  mov     rcx, rsi; this
0x180005389  mov     ebx, r9d
0x18000538c  mov     r15d, r8d
0x18000538f  mov     r12, rdx
0x180005392  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x180005397  mov     r14, [rsp+88h+arg_30]
0x18000539f  test    r14, r14
0x1800053a2  jz      short loc_1800053E8
0x1800053a4  mov     rcx, [rdi+88h]
0x1800053ab  test    rcx, rcx
0x1800053ae  jz      short loc_1800053BA
0x1800053b0  cmp     dword ptr [rdi+78h], 0
0x1800053b4  jnz     loc_180005479
0x1800053ba  mov     ebp, [rsp+88h+arg_38]
0x1800053c1  lea     eax, [rbp-2]
0x1800053c4  cmp     eax, 1
0x1800053c7  ja      short loc_1800053E8
0x1800053c9  mov     r9d, [rsp+88h+arg_20]; enum WICBitmapTransformOptions
0x1800053d1  test    r9d, 0FFFFFFE4h
0x1800053d8  jnz     short loc_1800053E8
0x1800053da  mov     eax, [rsp+88h+arg_28]
0x1800053e1  test    eax, 0FFFFFFFEh
0x1800053e6  jz      short loc_180005414
0x1800053e8  mov     ebx, 80070057h
0x1800053ed  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800053f4  jnz     short loc_180005475
0x1800053f6  test    rsi, rsi
0x1800053f9  jz      short loc_180005403
0x1800053fb  mov     rcx, rsi; this
0x1800053fe  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x180005403  mov     eax, ebx
0x180005405  add     rsp, 50h
0x180005409  pop     r15
0x18000540b  pop     r14
0x18000540d  pop     r12
0x18000540f  pop     rdi
0x180005410  pop     rsi
0x180005411  pop     rbp
0x180005412  pop     rbx
0x180005413  retn
0x180005414  test    rcx, rcx
0x180005417  jz      loc_1800054B9
0x18000541d  mov     [rsp+88h+var_58], ebp; unsigned int
0x180005421  lea     rcx, [rdi-70h]; this
0x180005425  mov     [rsp+88h+var_60], r14; struct WICBitmapPlane *
0x18000542a  mov     r8d, ebx; unsigned int
0x18000542d  mov     edx, r15d; unsigned int
0x180005430  mov     [rsp+88h+var_68], eax; enum WICPlanarOptions
0x180005434  call    ?EnsurePlanarTransform@CIcmColorTransform@@AEAAJIIW4WICBitmapTransformOptions@@W4WICPlanarOptions@@PEBUWICBitmapPlane@@I@Z; CIcmColorTransform::EnsurePlanarTransform(uint,uint,WICBitmapTransformOptions,WICPlanarOptions,WICBitmapPlane const *,uint)
0x180005439  mov     ebx, eax
0x18000543b  test    eax, eax
0x18000543d  jns     short loc_180005451
0x18000543f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180005446  jz      short loc_1800053F6
0x180005448  mov     ecx, eax; int
0x18000544a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000544f  jmp     short loc_1800053F6
0x180005451  mov     rcx, [rdi+90h]
0x180005458  mov     r9d, ebp
0x18000545b  mov     r8, r14
0x18000545e  mov     rdx, r12
0x180005461  mov     rax, [rcx]
0x180005464  mov     rax, [rax+20h]
0x180005468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000546d  mov     ebx, eax
0x18000546f  test    eax, eax
0x180005471  js      short loc_18000543F
0x180005473  jmp     short loc_1800053F6
0x180005475  mov     ecx, ebx
0x180005477  jmp     short loc_18000544A
0x180005479  mov     rax, [rcx]
0x18000547c  mov     r9d, ebx
0x18000547f  mov     r8d, r15d
0x180005482  mov     rdx, r12
0x180005485  mov     r10, [rax+20h]
0x180005489  mov     eax, [rsp+88h+arg_38]
0x180005490  mov     [rsp+88h+var_50], eax
0x180005494  mov     eax, [rsp+88h+arg_28]
0x18000549b  mov     qword ptr [rsp+88h+var_58], r14
0x1800054a0  mov     dword ptr [rsp+88h+var_60], eax
0x1800054a4  mov     eax, [rsp+88h+arg_20]
0x1800054ab  mov     [rsp+88h+var_68], eax
0x1800054af  mov     rax, r10
0x1800054b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054b7  jmp     short loc_18000546D
0x1800054b9  mov     ebx, 88982F81h
0x1800054be  jmp     loc_1800053ED
```
