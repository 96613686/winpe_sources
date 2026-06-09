# CopyToMilPaletteFromWicBitmapSource(IMILPalette *,IWICBitmapSource *)

- ea: `0x18002cac0`
- end: `0x18002cbf6`
- name: `?CopyToMilPaletteFromWicBitmapSource@@YAJPEAUIMILPalette@@PEAUIWICBitmapSource@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(struct IMILPalette *, struct IWICBitmapSource *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002c520`

## callees

- `0x180008c00`
- `0x180008d60`
- `0x1800171c4`
- `0x1800215e8`
- `0x18002c820`
- `0x18002cac0`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CopyToMilPaletteFromWicBitmapSource(struct IMILPalette *a1, struct IWICBitmapSource *a2)
{
  CMILCOMBase *v2; // rdi
  bool v5; // zf
  unsigned int v6; // ebx
  int v7; // eax
  bool v8; // zf
  int v9; // ecx
  CPalette *v10; // rax
  CMILCOMBase *v11; // rax
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *v14; // r9
  __int64 v16; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  v16 = 0;
  if ( !a1 || !a2 )
  {
    v5 = g_doStackCaptures == 0;
    v6 = -2147024809;
LABEL_16:
    if ( v5 )
      goto LABEL_19;
    v9 = v6;
    goto LABEL_18;
  }
  if ( (**(int (__fastcall ***)(struct IMILPalette *, GUID *, __int64 *))a1)(a1, &IID_IWICPalette, &v16) >= 0 )
  {
    v7 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, __int64))a2->lpVtbl->CopyPalette)(a2, v16);
    v6 = v7;
    if ( v7 >= 0 )
      goto LABEL_19;
    v8 = g_doStackCaptures == 0;
    goto LABEL_7;
  }
  v10 = (CPalette *)operator new(0x460u);
  if ( !v10 || (v11 = CPalette::CPalette(v10), (v2 = v11) == 0) )
  {
    v5 = g_doStackCaptures == 0;
    v6 = -2147024882;
    goto LABEL_16;
  }
  CMILCOMBase::InternalAddRef(v11, v12, v13, v14);
  v7 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, char *))a2->lpVtbl->CopyPalette)(a2, (char *)v2 + 80);
  v6 = v7;
  if ( v7 < 0
    || (v7 = (*(__int64 (__fastcall **)(struct IMILPalette *, __int64))(*(_QWORD *)a1 + 48LL))(a1, (__int64)v2 + 72),
        v6 = v7,
        v7 < 0) )
  {
    v8 = g_doStackCaptures == 0;
LABEL_7:
    if ( v8 )
      goto LABEL_19;
    v9 = v7;
LABEL_18:
    DoStackCapture(v9);
  }
LABEL_19:
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v2 )
    CMILCOMBase::InternalRelease(v2);
  return v6;
}

```

## disassembly

```asm
0x18002cac0  mov     [rsp+arg_8], rbx
0x18002cac5  mov     [rsp+arg_10], rsi
0x18002caca  push    rdi
0x18002cacb  sub     rsp, 20h
0x18002cacf  xor     edi, edi
0x18002cad1  mov     [rsp+28h+arg_0], 0
0x18002cada  mov     rbx, rdx
0x18002cadd  mov     rsi, rcx
0x18002cae0  test    rcx, rcx
0x18002cae3  jnz     short loc_18002CAF5
0x18002cae5  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18002caeb  mov     ebx, 80070057h
0x18002caf0  jmp     loc_18002CBAF
0x18002caf5  test    rbx, rbx
0x18002caf8  jz      short loc_18002CAE5
0x18002cafa  mov     rax, [rcx]
0x18002cafd  lea     r8, [rsp+28h+arg_0]
0x18002cb02  lea     rdx, IID_IWICPalette
0x18002cb09  mov     rax, [rax]
0x18002cb0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb11  test    eax, eax
0x18002cb13  js      short loc_18002CB3F
0x18002cb15  mov     rax, [rbx]
0x18002cb18  mov     rcx, rbx
0x18002cb1b  mov     rdx, [rsp+28h+arg_0]
0x18002cb20  mov     rax, [rax+30h]
0x18002cb24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb29  mov     ebx, eax
0x18002cb2b  test    eax, eax
0x18002cb2d  jns     loc_18002CBB8
0x18002cb33  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18002cb39  jz      short loc_18002CBB8
0x18002cb3b  mov     ecx, eax
0x18002cb3d  jmp     short loc_18002CBB3
0x18002cb3f  mov     ecx, 460h; Size
0x18002cb44  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002cb49  test    rax, rax
0x18002cb4c  jz      short loc_18002CBA3
0x18002cb4e  mov     rcx, rax; this
0x18002cb51  call    ??0CPalette@@QEAA@XZ; CPalette::CPalette(void)
0x18002cb56  mov     rdi, rax
0x18002cb59  test    rax, rax
0x18002cb5c  jz      short loc_18002CBA3
0x18002cb5e  mov     rcx, rax; this
0x18002cb61  call    ?InternalAddRef@CMILCOMBase@@QEAAKXZ; CMILCOMBase::InternalAddRef(void)
0x18002cb66  mov     rax, [rbx]
0x18002cb69  lea     rdx, [rdi+50h]
0x18002cb6d  mov     rcx, rbx
0x18002cb70  mov     rax, [rax+30h]
0x18002cb74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb79  mov     ebx, eax
0x18002cb7b  test    eax, eax
0x18002cb7d  jns     short loc_18002CB88
0x18002cb7f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002cb86  jmp     short loc_18002CB39
0x18002cb88  mov     rax, [rsi]
0x18002cb8b  lea     rdx, [rdi+48h]
0x18002cb8f  mov     rcx, rsi
0x18002cb92  mov     rax, [rax+30h]
0x18002cb96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb9b  mov     ebx, eax
0x18002cb9d  test    eax, eax
0x18002cb9f  jns     short loc_18002CBB8
0x18002cba1  jmp     short loc_18002CB7F
0x18002cba3  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002cbaa  mov     ebx, 8007000Eh
0x18002cbaf  jz      short loc_18002CBB8
0x18002cbb1  mov     ecx, ebx; int
0x18002cbb3  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002cbb8  mov     rcx, [rsp+28h+arg_0]
0x18002cbbd  test    rcx, rcx
0x18002cbc0  jz      short loc_18002CBD7
0x18002cbc2  mov     rax, [rcx]
0x18002cbc5  mov     rax, [rax+10h]
0x18002cbc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbce  mov     [rsp+28h+arg_0], 0
0x18002cbd7  test    rdi, rdi
0x18002cbda  jz      short loc_18002CBE4
0x18002cbdc  mov     rcx, rdi; this
0x18002cbdf  call    ?InternalRelease@CMILCOMBase@@QEAAKXZ; CMILCOMBase::InternalRelease(void)
0x18002cbe4  mov     rsi, [rsp+28h+arg_10]
0x18002cbe9  mov     eax, ebx
0x18002cbeb  mov     rbx, [rsp+28h+arg_8]
0x18002cbf0  add     rsp, 20h
0x18002cbf4  pop     rdi
0x18002cbf5  retn
```
