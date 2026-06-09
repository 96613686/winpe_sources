# WICCreateOrientedBitmapSource(IWICImagingFactory *,IWICBitmapSource *,IWICMetadataQueryReader *,IWICBitmapSource * *)

- ea: `0x18000d17c`
- end: `0x18000d2f3`
- name: `?WICCreateOrientedBitmapSource@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@PEAUIWICMetadataQueryReader@@PEAPEAU2@@Z`
- size: `375`
- prototype: `__int64 __fastcall(struct IWICImagingFactory *, struct IWICBitmapSource *, struct IWICMetadataQueryReader *, struct IWICBitmapSource **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010830`
- `0x18001d38c`
- `0x18001d678`

## callees

- `0x18000d17c`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d1e0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d1e0`

## pseudocode

```c
__int64 __fastcall WICCreateOrientedBitmapSource(
        struct IWICImagingFactory *a1,
        struct IWICBitmapSource *a2,
        struct IWICMetadataQueryReader *a3,
        struct IWICBitmapSource **a4)
{
  int v7; // eax
  int v8; // edi
  unsigned int v9; // ebx
  struct IWICImagingFactoryVtbl *lpVtbl; // rax
  struct IWICBitmapSource *v11; // rcx
  PROPVARIANT pvar; // [rsp+20h] [rbp-38h] BYREF
  struct IWICBitmapSource *v14; // [rsp+70h] [rbp+18h] BYREF

  *a4 = 0;
  memset(&pvar, 0, sizeof(pvar));
  v7 = ((__int64 (__fastcall *)(struct IWICMetadataQueryReader *, const wchar_t *, PROPVARIANT *))a3->lpVtbl->GetMetadataByName)(
         a3,
         L"System.Photo.Orientation",
         &pvar);
  v8 = v7;
  if ( v7 == -2003292352 || pvar.vt != 18 )
  {
    v9 = 0;
    v8 = 0;
  }
  else
  {
    v9 = 0;
    if ( v7 >= 0 && pvar.uiVal != 1 )
    {
      switch ( pvar.uiVal )
      {
        case 2u:
          v9 = 8;
          break;
        case 3u:
          v9 = 2;
          break;
        case 4u:
          v9 = 16;
          break;
        case 5u:
          v9 = 17;
          break;
        case 6u:
          v9 = 1;
          break;
        case 7u:
          v9 = 19;
          break;
        case 8u:
          v9 = 3;
          break;
      }
    }
  }
  PropVariantClear(&pvar);
  if ( v8 >= 0 )
  {
    lpVtbl = a1->lpVtbl;
    v14 = 0;
    v8 = ((__int64 (__fastcall *)(struct IWICImagingFactory *, struct IWICBitmapSource **))lpVtbl->CreateBitmapFlipRotator)(
           a1,
           &v14);
    if ( v8 >= 0 )
    {
      v8 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, struct IWICBitmapSource *, _QWORD))v14->lpVtbl[1].QueryInterface)(
             v14,
             a2,
             v9);
      if ( v8 >= 0 )
      {
        v11 = v14;
        *a4 = v14;
        ((void (__fastcall *)(struct IWICBitmapSource *))v11->lpVtbl->AddRef)(v11);
      }
      ((void (__fastcall *)(struct IWICBitmapSource *))v14->lpVtbl->Release)(v14);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000d17c  mov     r11, rsp
0x18000d17f  mov     [r11+8], rbx
0x18000d183  mov     [r11+10h], rbp
0x18000d187  push    rsi
0x18000d188  push    rdi
0x18000d189  push    r14
0x18000d18b  sub     rsp, 40h
0x18000d18f  xor     eax, eax
0x18000d191  mov     qword ptr [r9], 0
0x18000d198  mov     r10, r8
0x18000d19b  xorps   xmm0, xmm0
0x18000d19e  movups  xmmword ptr [rsp+58h+pvar], xmm0
0x18000d1a3  mov     [r11-28h], rax
0x18000d1a7  mov     rbp, rdx
0x18000d1aa  mov     rax, [r8]
0x18000d1ad  lea     rdx, aSystemPhotoOri; "System.Photo.Orientation"
0x18000d1b4  mov     rsi, rcx
0x18000d1b7  lea     r8, [r11-38h]
0x18000d1bb  mov     rcx, r10
0x18000d1be  mov     r14, r9
0x18000d1c1  mov     rax, [rax+28h]
0x18000d1c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1ca  mov     edi, eax
0x18000d1cc  cmp     eax, 88982F40h
0x18000d1d1  jnz     loc_18000D264
0x18000d1d7  xor     ebx, ebx
0x18000d1d9  xor     edi, edi
0x18000d1db  lea     rcx, [rsp+58h+pvar]; pvar
0x18000d1e0  call    cs:__imp_PropVariantClear
0x18000d1e6  test    edi, edi
0x18000d1e8  js      short loc_18000D24F
0x18000d1ea  mov     rax, [rsi]
0x18000d1ed  lea     rdx, [rsp+58h+arg_10]
0x18000d1f2  mov     rcx, rsi
0x18000d1f5  mov     [rsp+58h+arg_10], 0
0x18000d1fe  mov     rax, [rax+68h]
0x18000d202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d207  mov     edi, eax
0x18000d209  test    eax, eax
0x18000d20b  js      short loc_18000D24F
0x18000d20d  mov     rcx, [rsp+58h+arg_10]
0x18000d212  mov     r8d, ebx
0x18000d215  mov     rdx, rbp
0x18000d218  mov     rax, [rcx]
0x18000d21b  mov     rax, [rax+40h]
0x18000d21f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d224  mov     edi, eax
0x18000d226  test    eax, eax
0x18000d228  js      short loc_18000D23E
0x18000d22a  mov     rcx, [rsp+58h+arg_10]
0x18000d22f  mov     [r14], rcx
0x18000d232  mov     rax, [rcx]
0x18000d235  mov     rax, [rax+8]
0x18000d239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d23e  mov     rcx, [rsp+58h+arg_10]
0x18000d243  mov     rax, [rcx]
0x18000d246  mov     rax, [rax+10h]
0x18000d24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d24f  mov     rbx, [rsp+58h+arg_0]
0x18000d254  mov     eax, edi
0x18000d256  mov     rbp, [rsp+58h+arg_8]
0x18000d25b  add     rsp, 40h
0x18000d25f  pop     r14
0x18000d261  pop     rdi
0x18000d262  pop     rsi
0x18000d263  retn
0x18000d264  cmp     word ptr [rsp+58h+pvar], 12h
0x18000d26a  jnz     loc_18000D1D7
0x18000d270  xor     ebx, ebx
0x18000d272  test    eax, eax
0x18000d274  js      loc_18000D1DB
0x18000d27a  movzx   ecx, word ptr [rsp+58h+pvar+8]
0x18000d27f  sub     ecx, 1
0x18000d282  jz      loc_18000D1DB
0x18000d288  sub     ecx, 1
0x18000d28b  jz      short loc_18000D2E9
0x18000d28d  sub     ecx, 1
0x18000d290  jz      short loc_18000D2DF
0x18000d292  sub     ecx, 1
0x18000d295  jz      short loc_18000D2D5
0x18000d297  sub     ecx, 1
0x18000d29a  jz      short loc_18000D2CB
0x18000d29c  sub     ecx, 1
0x18000d29f  jz      short loc_18000D2B7
0x18000d2a1  sub     ecx, 1
0x18000d2a4  jz      short loc_18000D2C1
0x18000d2a6  cmp     ecx, 1
0x18000d2a9  jnz     loc_18000D1DB
0x18000d2af  lea     ebx, [rcx+2]
0x18000d2b2  jmp     loc_18000D1DB
0x18000d2b7  mov     ebx, 1
0x18000d2bc  jmp     loc_18000D1DB
0x18000d2c1  mov     ebx, 13h
0x18000d2c6  jmp     loc_18000D1DB
0x18000d2cb  mov     ebx, 11h
0x18000d2d0  jmp     loc_18000D1DB
0x18000d2d5  mov     ebx, 10h
0x18000d2da  jmp     loc_18000D1DB
0x18000d2df  mov     ebx, 2
0x18000d2e4  jmp     loc_18000D1DB
0x18000d2e9  mov     ebx, 8
0x18000d2ee  jmp     loc_18000D1DB
```
