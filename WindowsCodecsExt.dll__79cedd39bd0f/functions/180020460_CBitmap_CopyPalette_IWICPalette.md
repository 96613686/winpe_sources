# CBitmap::CopyPalette(IWICPalette *)

- ea: `0x180020460`
- end: `0x1800204dd`
- name: `?CopyPalette@CBitmap@@UEAAJPEAUIWICPalette@@@Z`
- size: `125`
- prototype: `int(CBitmap *__hidden this, struct IWICPalette *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800058c0`
- `0x18000f1d0`
- `0x1800171c4`
- `0x180020460`
- `0x180020570`

## pseudocode

```c
__int64 __fastcall CBitmap::CopyPalette(CBitmap *this, struct IWICPalette *a2)
{
  unsigned int v4; // ebx
  int v5; // ecx
  int v6; // eax
  char *v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = (char *)this + 152;
  CMTALock::Enter((CBitmap *)((char *)this + 152));
  if ( a2 )
  {
    v6 = CopyToWICPaletteFromMilBitmapSource(
           a2,
           (struct IMILBitmapSource *)(((unsigned __int64)this - 8)
                                     & ((unsigned __int128)-(__int128)((unsigned __int64)this - 24) >> 64)));
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
0x180020460  mov     [rsp+arg_8], rbx
0x180020465  push    rdi
0x180020466  sub     rsp, 20h
0x18002046a  mov     rbx, rcx
0x18002046d  mov     rdi, rdx
0x180020470  add     rcx, 98h; this
0x180020477  mov     [rsp+28h+arg_0], rcx
0x18002047c  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x180020481  test    rdi, rdi
0x180020484  jnz     short loc_180020497
0x180020486  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18002048c  mov     ebx, 80070057h
0x180020491  jz      short loc_1800204C6
0x180020493  mov     ecx, ebx
0x180020495  jmp     short loc_1800204C1
0x180020497  lea     rcx, [rbx-8]
0x18002049b  lea     rax, [rbx-18h]
0x18002049f  neg     rax
0x1800204a2  sbb     rdx, rdx
0x1800204a5  and     rdx, rcx; struct IMILBitmapSource *
0x1800204a8  mov     rcx, rdi; struct IWICPalette *
0x1800204ab  call    ?CopyToWICPaletteFromMilBitmapSource@@YAJPEAUIWICPalette@@PEAUIMILBitmapSource@@@Z; CopyToWICPaletteFromMilBitmapSource(IWICPalette *,IMILBitmapSource *)
0x1800204b0  mov     ebx, eax
0x1800204b2  test    eax, eax
0x1800204b4  jns     short loc_1800204C6
0x1800204b6  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800204bd  jz      short loc_1800204C6
0x1800204bf  mov     ecx, eax; int
0x1800204c1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800204c6  lea     rcx, [rsp+28h+arg_0]
0x1800204cb  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x1800204d0  mov     eax, ebx
0x1800204d2  mov     rbx, [rsp+28h+arg_8]
0x1800204d7  add     rsp, 20h
0x1800204db  pop     rdi
0x1800204dc  retn
```
