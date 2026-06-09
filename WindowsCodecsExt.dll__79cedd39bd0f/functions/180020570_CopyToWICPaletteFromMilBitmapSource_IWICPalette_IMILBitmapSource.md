# CopyToWICPaletteFromMilBitmapSource(IWICPalette *,IMILBitmapSource *)

- ea: `0x180020570`
- end: `0x18002060f`
- name: `?CopyToWICPaletteFromMilBitmapSource@@YAJPEAUIWICPalette@@PEAUIMILBitmapSource@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(struct IWICPalette *, struct IMILBitmapSource *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180020460`
- `0x1800204f0`

## callees

- `0x1800171c4`
- `0x180020570`
- `0x180020964`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CopyToWICPaletteFromMilBitmapSource(struct IWICPalette *a1, struct IMILBitmapSource *a2)
{
  unsigned int v3; // ebx
  int v4; // eax
  struct IMILPalette *v5; // rdi
  struct IMILPalette *v7; // [rsp+30h] [rbp+8h] BYREF

  v7 = 0;
  if ( a1 && a2 )
  {
    v4 = CreateMilPaletteFromWIC(a1, &v7);
    v5 = v7;
    v3 = v4;
    if ( v4 < 0
      || (v4 = (*(__int64 (__fastcall **)(struct IMILBitmapSource *, struct IMILPalette *))(*(_QWORD *)a2 + 48LL))(
                 a2,
                 v7),
          v3 = v4,
          v4 < 0) )
    {
      if ( g_doStackCaptures )
        DoStackCapture(v4);
    }
    if ( v5 )
      (*(void (__fastcall **)(struct IMILPalette *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  else
  {
    v3 = -2147024809;
    if ( g_doStackCaptures )
      DoStackCapture(-2147024809);
  }
  return v3;
}

```

## disassembly

```asm
0x180020570  mov     [rsp+arg_8], rbx
0x180020575  mov     [rsp+arg_10], rsi
0x18002057a  push    rdi
0x18002057b  sub     rsp, 20h
0x18002057f  mov     [rsp+28h+arg_0], 0
0x180020588  mov     rsi, rdx
0x18002058b  test    rcx, rcx
0x18002058e  jnz     short loc_1800205A7
0x180020590  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180020597  mov     ebx, 80070057h
0x18002059c  jz      short loc_1800205FD
0x18002059e  mov     ecx, ebx; int
0x1800205a0  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800205a5  jmp     short loc_1800205FD
0x1800205a7  test    rsi, rsi
0x1800205aa  jz      short loc_180020590
0x1800205ac  lea     rdx, [rsp+28h+arg_0]; struct IMILPalette **
0x1800205b1  call    ?CreateMilPaletteFromWIC@@YAJPEAUIWICPalette@@PEAPEAUIMILPalette@@@Z; CreateMilPaletteFromWIC(IWICPalette *,IMILPalette * *)
0x1800205b6  mov     rdi, [rsp+28h+arg_0]
0x1800205bb  mov     ebx, eax
0x1800205bd  test    eax, eax
0x1800205bf  js      short loc_1800205D9
0x1800205c1  mov     rax, [rsi]
0x1800205c4  mov     rdx, rdi
0x1800205c7  mov     rcx, rsi
0x1800205ca  mov     rax, [rax+30h]
0x1800205ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205d3  mov     ebx, eax
0x1800205d5  test    eax, eax
0x1800205d7  jns     short loc_1800205E9
0x1800205d9  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800205e0  jz      short loc_1800205E9
0x1800205e2  mov     ecx, eax; int
0x1800205e4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800205e9  test    rdi, rdi
0x1800205ec  jz      short loc_1800205FD
0x1800205ee  mov     rdx, [rdi]
0x1800205f1  mov     rcx, rdi
0x1800205f4  mov     rax, [rdx+10h]
0x1800205f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205fd  mov     rsi, [rsp+28h+arg_10]
0x180020602  mov     eax, ebx
0x180020604  mov     rbx, [rsp+28h+arg_8]
0x180020609  add     rsp, 20h
0x18002060d  pop     rdi
0x18002060e  retn
```
