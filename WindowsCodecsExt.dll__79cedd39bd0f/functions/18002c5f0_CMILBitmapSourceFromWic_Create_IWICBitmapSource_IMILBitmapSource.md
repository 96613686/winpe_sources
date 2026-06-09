# CMILBitmapSourceFromWic::Create(IWICBitmapSource *,IMILBitmapSource * *)

- ea: `0x18002c5f0`
- end: `0x18002c654`
- name: `?Create@CMILBitmapSourceFromWic@@SAJPEAUIWICBitmapSource@@PEAPEAUIMILBitmapSource@@@Z`
- size: `100`
- prototype: `__int64 __fastcall(struct IWICBitmapSource *, struct IMILBitmapSource **)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005900`
- `0x180012b20`

## callees

- `0x180008d60`
- `0x1800171c4`
- `0x1800215e8`
- `0x18002c414`
- `0x18002c5f0`

## pseudocode

```c
__int64 __fastcall CMILBitmapSourceFromWic::Create(struct IWICBitmapSource *a1, struct IMILBitmapSource **a2)
{
  CMILBitmapSourceFromWic *v4; // rax
  CMILBitmapSourceFromWic *v5; // rax
  const unsigned __int16 *v6; // rdx
  const unsigned __int16 *v7; // r8
  const unsigned __int16 *v8; // r9
  unsigned int v9; // ebx

  v4 = (CMILBitmapSourceFromWic *)operator new(0x60u);
  if ( v4 && (v5 = CMILBitmapSourceFromWic::CMILBitmapSourceFromWic(v4, a1)) != 0 )
  {
    v9 = 0;
    *a2 = (CMILBitmapSourceFromWic *)((char *)v5 + 72);
    CMILCOMBase::InternalAddRef(v5, v6, v7, v8);
  }
  else
  {
    v9 = -2147024882;
    if ( g_doStackCaptures )
      DoStackCapture(-2147024882);
  }
  return v9;
}

```

## disassembly

```asm
0x18002c5f0  mov     [rsp+arg_0], rbx
0x18002c5f5  push    rdi
0x18002c5f6  sub     rsp, 20h
0x18002c5fa  mov     rbx, rcx
0x18002c5fd  mov     rdi, rdx
0x18002c600  mov     ecx, 60h ; '`'; Size
0x18002c605  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c60a  test    rax, rax
0x18002c60d  jz      short loc_18002C632
0x18002c60f  mov     rdx, rbx; struct IWICBitmapSource *
0x18002c612  mov     rcx, rax; this
0x18002c615  call    ??0CMILBitmapSourceFromWic@@IEAA@PEAUIWICBitmapSource@@@Z; CMILBitmapSourceFromWic::CMILBitmapSourceFromWic(IWICBitmapSource *)
0x18002c61a  test    rax, rax
0x18002c61d  jz      short loc_18002C632
0x18002c61f  lea     rcx, [rax+48h]
0x18002c623  xor     ebx, ebx
0x18002c625  mov     [rdi], rcx
0x18002c628  mov     rcx, rax; this
0x18002c62b  call    ?InternalAddRef@CMILCOMBase@@QEAAKXZ; CMILCOMBase::InternalAddRef(void)
0x18002c630  jmp     short loc_18002C647
0x18002c632  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002c639  mov     ebx, 8007000Eh
0x18002c63e  jz      short loc_18002C647
0x18002c640  mov     ecx, ebx; int
0x18002c642  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002c647  mov     eax, ebx
0x18002c649  mov     rbx, [rsp+28h+arg_0]
0x18002c64e  add     rsp, 20h
0x18002c652  pop     rdi
0x18002c653  retn
```
