# HrCreateBitmapFromSource(IMILBitmapSource *,MilBitmapCreateCacheOption::Enum,CBitmap * *)

- ea: `0x18001e670`
- end: `0x18001e771`
- name: `?HrCreateBitmapFromSource@@YAJPEAUIMILBitmapSource@@W4Enum@MilBitmapCreateCacheOption@@PEAPEAVCBitmap@@@Z`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001e5b0`

## callees

- `0x1800171c4`
- `0x18001e670`
- `0x1800215e8`
- `0x18002e964`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall HrCreateBitmapFromSource(__int64 *a1, __int64 a2, CSourceBitmap **a3)
{
  __int64 v3; // rax
  int v6; // ebx
  CSourceBitmap *v7; // rax
  CSourceBitmap *v8; // rax
  CSourceBitmap *v9; // rcx
  int v10; // eax
  int v11; // ecx
  CSourceBitmap *v13; // [rsp+48h] [rbp+20h] BYREF

  v3 = *a1;
  v13 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, CSourceBitmap **))(v3 + 64))(a1, &v13);
  if ( v6 >= 0 )
  {
    (*(void (__fastcall **)(CSourceBitmap *))(*(_QWORD *)v13 + 8LL))(v13);
LABEL_9:
    (*(void (__fastcall **)(CSourceBitmap *))(*(_QWORD *)v13 + 8LL))(v13);
    v9 = v13;
    *a3 = v13;
    goto LABEL_15;
  }
  v7 = (CSourceBitmap *)operator new(0x110u);
  if ( !v7 )
  {
    v9 = 0;
    v13 = 0;
    goto LABEL_11;
  }
  v8 = CSourceBitmap::CSourceBitmap(v7);
  v13 = v8;
  v9 = v8;
  if ( !v8 )
  {
LABEL_11:
    v6 = -2147024882;
    if ( !g_doStackCaptures )
      goto LABEL_15;
    v11 = -2147024882;
    goto LABEL_13;
  }
  (*(void (__fastcall **)(CSourceBitmap *))(*(_QWORD *)v8 + 8LL))(v8);
  v10 = (*(__int64 (__fastcall **)(CSourceBitmap *, __int64 *))(*(_QWORD *)v13 + 40LL))(v13, a1);
  v6 = v10;
  if ( v10 >= 0 )
    goto LABEL_9;
  if ( !g_doStackCaptures )
    goto LABEL_14;
  v11 = v10;
LABEL_13:
  DoStackCapture(v11);
LABEL_14:
  v9 = v13;
LABEL_15:
  if ( v9 )
    (*(void (__fastcall **)(CSourceBitmap *))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001e670  mov     r11, rsp
0x18001e673  mov     [r11+8], rbx
0x18001e677  mov     [r11+10h], rsi
0x18001e67b  push    rdi
0x18001e67c  sub     rsp, 20h
0x18001e680  mov     rax, [rcx]
0x18001e683  lea     rdx, [r11+20h]
0x18001e687  mov     rsi, r8
0x18001e68a  mov     qword ptr [r11+20h], 0
0x18001e692  mov     rdi, rcx
0x18001e695  mov     rax, [rax+40h]
0x18001e699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e69e  mov     ebx, eax
0x18001e6a0  test    eax, eax
0x18001e6a2  js      short loc_18001E6B7
0x18001e6a4  mov     rcx, [rsp+28h+arg_18]
0x18001e6a9  mov     rdx, [rcx]
0x18001e6ac  mov     rax, [rdx+8]
0x18001e6b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6b5  jmp     short loc_18001E712
0x18001e6b7  mov     ecx, 110h; Size
0x18001e6bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e6c1  test    rax, rax
0x18001e6c4  jz      short loc_18001E72D
0x18001e6c6  mov     rcx, rax; this
0x18001e6c9  call    ??0CSourceBitmap@@QEAA@XZ; CSourceBitmap::CSourceBitmap(void)
0x18001e6ce  mov     [rsp+28h+arg_18], rax
0x18001e6d3  mov     rcx, rax
0x18001e6d6  test    rax, rax
0x18001e6d9  jz      short loc_18001E734
0x18001e6db  mov     rax, [rax]
0x18001e6de  mov     rax, [rax+8]
0x18001e6e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6e7  mov     rcx, [rsp+28h+arg_18]
0x18001e6ec  mov     rdx, rdi
0x18001e6ef  mov     rax, [rcx]
0x18001e6f2  mov     rax, [rax+28h]
0x18001e6f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6fb  mov     ebx, eax
0x18001e6fd  test    eax, eax
0x18001e6ff  jns     short loc_18001E712
0x18001e701  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001e708  jz      short loc_18001E70E
0x18001e70a  mov     ecx, eax
0x18001e70c  jmp     short loc_18001E744
0x18001e70e  test    eax, eax
0x18001e710  js      short loc_18001E749
0x18001e712  mov     rcx, [rsp+28h+arg_18]
0x18001e717  mov     rax, [rcx]
0x18001e71a  mov     rax, [rax+8]
0x18001e71e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e723  mov     rcx, [rsp+28h+arg_18]
0x18001e728  mov     [rsi], rcx
0x18001e72b  jmp     short loc_18001E74E
0x18001e72d  xor     ecx, ecx
0x18001e72f  mov     [rsp+28h+arg_18], rcx
0x18001e734  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001e73b  mov     ebx, 8007000Eh
0x18001e740  jz      short loc_18001E74E
0x18001e742  mov     ecx, ebx; int
0x18001e744  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001e749  mov     rcx, [rsp+28h+arg_18]
0x18001e74e  test    rcx, rcx
0x18001e751  jz      short loc_18001E75F
0x18001e753  mov     rax, [rcx]
0x18001e756  mov     rax, [rax+10h]
0x18001e75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e75f  mov     rsi, [rsp+28h+arg_8]
0x18001e764  mov     eax, ebx
0x18001e766  mov     rbx, [rsp+28h+arg_0]
0x18001e76b  add     rsp, 20h
0x18001e76f  pop     rdi
0x18001e770  retn
```
