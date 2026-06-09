# CreateFormatConverterResolver(IWICFormatConverter * *)

- ea: `0x18001ff04`
- end: `0x18001ff81`
- name: `?CreateFormatConverterResolver@@YAJPEAPEAUIWICFormatConverter@@@Z`
- size: `125`
- prototype: `__int64 __fastcall(struct IWICFormatConverter **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001fd80`

## callees

- `0x180004004`
- `0x1800171c4`
- `0x18001ff04`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CreateFormatConverterResolver(struct IWICFormatConverter **a1, __int64 a2, __int64 a3)
{
  int CodecFactory; // eax
  struct IWICComponentFactory *v5; // rdi
  unsigned int v6; // ebx
  struct IWICComponentFactory *v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = 0;
  CodecFactory = GetCodecFactory(&v8, a2, a3);
  v5 = v8;
  v6 = CodecFactory;
  if ( CodecFactory < 0
    || (CodecFactory = ((__int64 (__fastcall *)(struct IWICComponentFactory *, struct IWICFormatConverter **))v8->lpVtbl->CreateFormatConverter)(
                         v8,
                         a1),
        v6 = CodecFactory,
        CodecFactory < 0) )
  {
    if ( g_doStackCaptures )
      DoStackCapture(CodecFactory);
  }
  if ( v5 )
    ((void (__fastcall *)(struct IWICComponentFactory *))v5->lpVtbl->Release)(v5);
  return v6;
}

```

## disassembly

```asm
0x18001ff04  mov     rax, rsp
0x18001ff07  mov     [rax+8], rbx
0x18001ff0b  mov     [rax+18h], rsi
0x18001ff0f  push    rdi
0x18001ff10  sub     rsp, 20h
0x18001ff14  mov     rsi, rcx
0x18001ff17  mov     qword ptr [rax+10h], 0
0x18001ff1f  lea     rcx, [rax+10h]; struct IWICComponentFactory **
0x18001ff23  call    ?GetCodecFactory@@YAJPEAPEAUIWICComponentFactory@@@Z; GetCodecFactory(IWICComponentFactory * *)
0x18001ff28  mov     rdi, [rsp+28h+arg_8]
0x18001ff2d  mov     ebx, eax
0x18001ff2f  test    eax, eax
0x18001ff31  js      short loc_18001FF4B
0x18001ff33  mov     rax, [rdi]
0x18001ff36  mov     rdx, rsi
0x18001ff39  mov     rcx, rdi
0x18001ff3c  mov     rax, [rax+50h]
0x18001ff40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff45  mov     ebx, eax
0x18001ff47  test    eax, eax
0x18001ff49  jns     short loc_18001FF5B
0x18001ff4b  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001ff52  jz      short loc_18001FF5B
0x18001ff54  mov     ecx, eax; int
0x18001ff56  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001ff5b  test    rdi, rdi
0x18001ff5e  jz      short loc_18001FF6F
0x18001ff60  mov     rdx, [rdi]
0x18001ff63  mov     rcx, rdi
0x18001ff66  mov     rax, [rdx+10h]
0x18001ff6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff6f  mov     rsi, [rsp+28h+arg_10]
0x18001ff74  mov     eax, ebx
0x18001ff76  mov     rbx, [rsp+28h+arg_0]
0x18001ff7b  add     rsp, 20h
0x18001ff7f  pop     rdi
0x18001ff80  retn
```
