# CIcmColorTransform::CopyPalette(IWICPalette *)

- ea: `0x1800204f0`
- end: `0x18002056a`
- name: `?CopyPalette@CIcmColorTransform@@UEAAJPEAUIWICPalette@@@Z`
- size: `122`
- prototype: `int(CIcmColorTransform *__hidden this, struct IWICPalette *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002a7a0`

## callees

- `0x1800058c0`
- `0x18000f1d0`
- `0x1800171c4`
- `0x1800204f0`
- `0x180020570`

## pseudocode

```c
__int64 __fastcall CIcmColorTransform::CopyPalette(CIcmColorTransform *this, struct IWICPalette *a2)
{
  unsigned int v4; // ebx
  int v5; // ecx
  int v6; // eax
  char *v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = (char *)this - 56;
  CMTALock::Enter((CIcmColorTransform *)((char *)this - 56));
  if ( a2 )
  {
    v6 = CopyToWICPaletteFromMilBitmapSource(
           a2,
           (struct IMILBitmapSource *)(((unsigned __int64)this + 16)
                                     & ((unsigned __int128)-(__int128)((unsigned __int64)this - 72) >> 64)));
    v4 = v6;
    if ( v6 < 0 && g_doStackCaptures )
    {
      v5 = v6;
      goto LABEL_7;
    }
  }
  else
  {
    v4 = -2147024809;
    if ( g_doStackCaptures )
    {
      v5 = -2147024809;
LABEL_7:
      DoStackCapture(v5);
    }
  }
  CGuard<CMTALock>::~CGuard<CMTALock>(&v8);
  return v4;
}

```

## disassembly

```asm
0x1800204f0  mov     [rsp+arg_8], rbx
0x1800204f5  push    rdi
0x1800204f6  sub     rsp, 20h
0x1800204fa  mov     rbx, rcx
0x1800204fd  mov     rdi, rdx
0x180020500  add     rcx, 0FFFFFFFFFFFFFFC8h; this
0x180020504  mov     [rsp+28h+arg_0], rcx
0x180020509  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18002050e  test    rdi, rdi
0x180020511  jnz     short loc_180020524
0x180020513  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180020519  mov     ebx, 80070057h
0x18002051e  jz      short loc_180020553
0x180020520  mov     ecx, ebx
0x180020522  jmp     short loc_18002054E
0x180020524  lea     rcx, [rbx+10h]
0x180020528  lea     rax, [rbx-48h]
0x18002052c  neg     rax
0x18002052f  sbb     rdx, rdx
0x180020532  and     rdx, rcx; struct IMILBitmapSource *
0x180020535  mov     rcx, rdi; struct IWICPalette *
0x180020538  call    ?CopyToWICPaletteFromMilBitmapSource@@YAJPEAUIWICPalette@@PEAUIMILBitmapSource@@@Z; CopyToWICPaletteFromMilBitmapSource(IWICPalette *,IMILBitmapSource *)
0x18002053d  mov     ebx, eax
0x18002053f  test    eax, eax
0x180020541  jns     short loc_180020553
0x180020543  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002054a  jz      short loc_180020553
0x18002054c  mov     ecx, eax; int
0x18002054e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180020553  lea     rcx, [rsp+28h+arg_0]
0x180020558  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18002055d  mov     eax, ebx
0x18002055f  mov     rbx, [rsp+28h+arg_8]
0x180020564  add     rsp, 20h
0x180020568  pop     rdi
0x180020569  retn
```
