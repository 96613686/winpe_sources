# D3DCommon::CreateTextureFromResource10(HINSTANCE__ *,uint,ID3D10Device *,ID3D10Texture2D * *)

- ea: `0x1400824ec`
- end: `0x140082677`
- name: `?CreateTextureFromResource10@D3DCommon@@YAJPEAUHINSTANCE__@@IPEAUID3D10Device@@PEAPEAUID3D10Texture2D@@@Z`
- size: `395`
- prototype: `__int64 __fastcall(D3DCommon *__hidden this, HINSTANCE, unsigned int, struct ID3D10Device *, struct ID3D10Texture2D **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140087420`

## callees

- `0x14000398c`
- `0x14007fa4c`
- `0x140082250`
- `0x140082280`
- `0x1400824ec`
- `0x140082724`
- `0x14011a010`

## import_xrefs

- `gdiplus!GdipDisposeImage` at `0x140082635`
- `gdiplus!GdipDisposeImage` at `0x140082635`
- `gdiplus!GdipCreateBitmapFromStream` at `0x1400825cd`
- `gdiplus!GdipCreateBitmapFromStream` at `0x1400825cd`
- `gdiplus!GdiplusShutdown` at `0x14008265b`
- `gdiplus!GdiplusShutdown` at `0x14008265b`
- `gdiplus!GdiplusStartup` at `0x14008254c`
- `gdiplus!GdiplusStartup` at `0x14008254c`

## string_xrefs

- `0x140082605`: ``anonymous-namespace'::StreamWrapper::CreateStreamWrapper`

## pseudocode

```c
__int64 __fastcall D3DCommon::CreateTextureFromResource10(
        D3DCommon *this,
        HINSTANCE a2,
        __int64 a3,
        struct ID3D10Device *a4)
{
  __int64 v8; // rbx
  void *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rsi
  int TextureFromGDIPBitmap10; // edi
  unsigned __int16 v13; // dx
  _QWORD v14[2]; // [rsp+20h] [rbp-38h] BYREF
  int v15; // [rsp+30h] [rbp-28h] BYREF
  __int64 v16; // [rsp+38h] [rbp-20h]
  int v17; // [rsp+40h] [rbp-18h]
  int v18; // [rsp+44h] [rbp-14h]
  __int64 v19; // [rsp+A0h] [rbp+48h] BYREF

  if ( !a3 || !a4 )
    return 2147500035LL;
  v19 = 0;
  v15 = 1;
  v18 = 1;
  v14[0] = 0;
  v16 = 0;
  v17 = 0;
  if ( (unsigned int)GdiplusStartup(v14, &v15, 0, a4) )
    return 2147500037LL;
  v8 = 0;
  v9 = operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
  v14[1] = v9;
  if ( v9 && (v10 = anonymous_namespace_::StreamWrapper::StreamWrapper(v9, this), (v11 = v10) != 0) )
  {
    TextureFromGDIPBitmap10 = anonymous_namespace_::StreamWrapper::Load(v10);
    if ( TextureFromGDIPBitmap10 >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
      TextureFromGDIPBitmap10 = 0;
      v8 = v11;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    if ( TextureFromGDIPBitmap10 >= 0 )
    {
      if ( (unsigned int)GdipCreateBitmapFromStream(v8, &v19) || !v19 )
      {
        TextureFromGDIPBitmap10 = -2147467259;
        D3DCommon::ERR((D3DCommon *)0x8E, v13);
      }
      else
      {
        TextureFromGDIPBitmap10 = anonymous_namespace_::CreateTextureFromGDIPBitmap10(v19, a3, a4);
      }
      goto LABEL_16;
    }
  }
  else
  {
    D3DCommon::ERR(
      (D3DCommon *)0x6D,
      (unsigned __int16)L"pStream",
      L"`anonymous-namespace'::StreamWrapper::CreateStreamWrapper");
    TextureFromGDIPBitmap10 = -2147024882;
  }
  D3DCommon::ERR((D3DCommon *)0x9F, 0x2BDu);
LABEL_16:
  if ( v19 )
  {
    GdipDisposeImage(v19);
    v19 = 0;
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  GdiplusShutdown(v14[0]);
  return (unsigned int)TextureFromGDIPBitmap10;
}

```

## disassembly

```asm
0x1400824ec  push    rbp
0x1400824ee  push    rbx
0x1400824ef  push    rsi
0x1400824f0  push    rdi
0x1400824f1  push    r14
0x1400824f3  push    r15
0x1400824f5  mov     rbp, rsp
0x1400824f8  sub     rsp, 58h
0x1400824fc  mov     r14, r9
0x1400824ff  mov     r15, r8
0x140082502  mov     rdi, rcx
0x140082505  test    r8, r8
0x140082508  jz      loc_140082665
0x14008250e  test    r9, r9
0x140082511  jz      loc_140082665
0x140082517  mov     eax, 1
0x14008251c  mov     [rbp+arg_10], 0
0x140082524  xor     r8d, r8d
0x140082527  mov     [rbp+var_28], eax
0x14008252a  lea     rdx, [rbp+var_28]
0x14008252e  mov     [rbp+var_14], eax
0x140082531  lea     rcx, [rbp+var_38]
0x140082535  mov     [rbp+var_38], 0
0x14008253d  mov     [rbp+var_20], 0
0x140082545  mov     [rbp+var_18], 0
0x14008254c  call    cs:__imp_GdiplusStartup
0x140082552  test    eax, eax
0x140082554  jz      short loc_140082560
0x140082556  mov     eax, 80004005h
0x14008255b  jmp     loc_14008266A
0x140082560  xor     ebx, ebx
0x140082562  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140082569  lea     ecx, [rbx+30h]; unsigned __int64
0x14008256c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140082571  mov     [rbp+var_30], rax
0x140082575  test    rax, rax
0x140082578  jz      loc_140082600
0x14008257e  mov     rdx, rdi
0x140082581  mov     rcx, rax
0x140082584  call    _anonymous_namespace___StreamWrapper__StreamWrapper
0x140082589  mov     rsi, rax
0x14008258c  test    rax, rax
0x14008258f  jz      short loc_140082600
0x140082591  mov     rcx, rax
0x140082594  call    _anonymous_namespace___StreamWrapper__Load
0x140082599  mov     edi, eax
0x14008259b  test    eax, eax
0x14008259d  js      short loc_1400825B3
0x14008259f  mov     rcx, [rsi]
0x1400825a2  mov     rax, [rcx+8]
0x1400825a6  mov     rcx, rsi
0x1400825a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400825ae  xor     edi, edi
0x1400825b0  mov     rbx, rsi
0x1400825b3  mov     rax, [rsi]
0x1400825b6  mov     rcx, rsi
0x1400825b9  mov     rax, [rax+10h]
0x1400825bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400825c2  test    edi, edi
0x1400825c4  js      short loc_14008261D
0x1400825c6  lea     rdx, [rbp+arg_10]
0x1400825ca  mov     rcx, rbx
0x1400825cd  call    cs:__imp_GdipCreateBitmapFromStream
0x1400825d3  test    eax, eax
0x1400825d5  jnz     short loc_1400825EF
0x1400825d7  mov     rcx, [rbp+arg_10]
0x1400825db  test    rcx, rcx
0x1400825de  jz      short loc_1400825EF
0x1400825e0  mov     r8, r14
0x1400825e3  mov     rdx, r15
0x1400825e6  call    _anonymous_namespace___CreateTextureFromGDIPBitmap10
0x1400825eb  mov     edi, eax
0x1400825ed  jmp     short loc_14008262C
0x1400825ef  mov     ecx, 8Eh; this
0x1400825f4  mov     edi, 80004005h
0x1400825f9  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x1400825fe  jmp     short loc_14008262C
0x140082600  mov     ecx, 6Dh ; 'm'; this
0x140082605  lea     r8, aAnonymousNames_8; "`anonymous-namespace'::StreamWrapper::C"...
0x14008260c  lea     rdx, aPstream; "pStream"
0x140082613  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x140082618  mov     edi, 8007000Eh
0x14008261d  mov     ecx, 9Fh; this
0x140082622  mov     edx, 2BDh; unsigned __int16
0x140082627  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x14008262c  mov     rcx, [rbp+arg_10]
0x140082630  test    rcx, rcx
0x140082633  jz      short loc_140082643
0x140082635  call    cs:__imp_GdipDisposeImage
0x14008263b  mov     [rbp+arg_10], 0
0x140082643  test    rbx, rbx
0x140082646  jz      short loc_140082657
0x140082648  mov     rax, [rbx]
0x14008264b  mov     rcx, rbx
0x14008264e  mov     rax, [rax+10h]
0x140082652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140082657  mov     rcx, [rbp+var_38]
0x14008265b  call    cs:__imp_GdiplusShutdown
0x140082661  mov     eax, edi
0x140082663  jmp     short loc_14008266A
0x140082665  mov     eax, 80004003h
0x14008266a  add     rsp, 58h
0x14008266e  pop     r15
0x140082670  pop     r14
0x140082672  pop     rdi
0x140082673  pop     rsi
0x140082674  pop     rbx
0x140082675  pop     rbp
0x140082676  retn
```
