# CMILBitmapSourceFromWic::CopyPalette(IMILPalette *)

- ea: `0x18002c520`
- end: `0x18002c570`
- name: `?CopyPalette@CMILBitmapSourceFromWic@@UEAAJPEAUIMILPalette@@@Z`
- size: `80`
- prototype: `int(CMILBitmapSourceFromWic *__hidden this, struct IMILPalette *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800058c0`
- `0x18000f1d0`
- `0x18002cac0`

## pseudocode

```c
__int64 __fastcall CMILBitmapSourceFromWic::CopyPalette(CMILBitmapSourceFromWic *this, struct IMILPalette *a2)
{
  CMILBitmapSourceFromWic *v2; // rbx
  char *v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = this;
  v5 = (char *)this - 56;
  CMTALock::Enter((CMILBitmapSourceFromWic *)((char *)this - 56));
  LODWORD(v2) = CopyToMilPaletteFromWicBitmapSource(
                  a2,
                  (struct IWICBitmapSource *)(((unsigned __int64)v2 + 8)
                                            & ((unsigned __int128)-(__int128)((unsigned __int64)v2 - 72) >> 64)));
  CGuard<CMTALock>::~CGuard<CMTALock>(&v5);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002c520  mov     [rsp+arg_8], rbx
0x18002c525  push    rdi
0x18002c526  sub     rsp, 20h
0x18002c52a  mov     rbx, rcx
0x18002c52d  mov     rdi, rdx
0x18002c530  add     rcx, 0FFFFFFFFFFFFFFC8h; this
0x18002c534  mov     [rsp+28h+arg_0], rcx
0x18002c539  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18002c53e  lea     rcx, [rbx+8]
0x18002c542  lea     rax, [rbx-48h]
0x18002c546  neg     rax
0x18002c549  sbb     rdx, rdx
0x18002c54c  and     rdx, rcx; struct IWICBitmapSource *
0x18002c54f  mov     rcx, rdi; struct IMILPalette *
0x18002c552  call    ?CopyToMilPaletteFromWicBitmapSource@@YAJPEAUIMILPalette@@PEAUIWICBitmapSource@@@Z; CopyToMilPaletteFromWicBitmapSource(IMILPalette *,IWICBitmapSource *)
0x18002c557  lea     rcx, [rsp+28h+arg_0]
0x18002c55c  mov     ebx, eax
0x18002c55e  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18002c563  mov     eax, ebx
0x18002c565  mov     rbx, [rsp+28h+arg_8]
0x18002c56a  add     rsp, 20h
0x18002c56e  pop     rdi
0x18002c56f  retn
```
