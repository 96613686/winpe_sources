# WICCreateOrientedBitmapSource(IWICImagingFactory *,IWICBitmapSource *,IWICMetadataQueryReader *,IWICBitmapSource * *)

- ea: `0x18000db74`
- end: `0x18000dcf2`
- name: `?WICCreateOrientedBitmapSource@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@PEAUIWICMetadataQueryReader@@PEAPEAU2@@Z`
- size: `382`
- prototype: `__int64 __fastcall(struct IWICImagingFactory *, struct IWICBitmapSource *, struct IWICMetadataQueryReader *, struct IWICBitmapSource **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011050`
- `0x18001e150`
- `0x18001e448`

## callees

- `0x18000db74`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000dbd8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000dbd8`

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
0x18000db74  mov     r11, rsp
0x18000db77  mov     [r11+8], rbx
0x18000db7b  mov     [r11+10h], rbp
0x18000db7f  push    rsi
0x18000db80  push    rdi
0x18000db81  push    r14
0x18000db83  sub     rsp, 40h
0x18000db87  xor     eax, eax
0x18000db89  mov     qword ptr [r9], 0
0x18000db90  mov     r10, r8
0x18000db93  xorps   xmm0, xmm0
0x18000db96  movups  xmmword ptr [rsp+58h+pvar], xmm0
0x18000db9b  mov     [r11-28h], rax
0x18000db9f  mov     rbp, rdx
0x18000dba2  mov     rax, [r8]
0x18000dba5  lea     rdx, aSystemPhotoOri; "System.Photo.Orientation"
0x18000dbac  mov     rsi, rcx
0x18000dbaf  lea     r8, [r11-38h]
0x18000dbb3  mov     rcx, r10
0x18000dbb6  mov     r14, r9
0x18000dbb9  mov     rax, [rax+28h]
0x18000dbbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbc2  mov     edi, eax
0x18000dbc4  cmp     eax, 88982F40h
0x18000dbc9  jnz     loc_18000DC63
0x18000dbcf  xor     ebx, ebx
0x18000dbd1  xor     edi, edi
0x18000dbd3  lea     rcx, [rsp+58h+pvar]; pvar
0x18000dbd8  call    cs:__imp_PropVariantClear
0x18000dbdf  nop     dword ptr [rax+rax+00h]
0x18000dbe4  test    edi, edi
0x18000dbe6  js      short loc_18000DC4D
0x18000dbe8  mov     rax, [rsi]
0x18000dbeb  lea     rdx, [rsp+58h+arg_10]
0x18000dbf0  mov     rcx, rsi
0x18000dbf3  mov     [rsp+58h+arg_10], 0
0x18000dbfc  mov     rax, [rax+68h]
0x18000dc00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc05  mov     edi, eax
0x18000dc07  test    eax, eax
0x18000dc09  js      short loc_18000DC4D
0x18000dc0b  mov     rcx, [rsp+58h+arg_10]
0x18000dc10  mov     r8d, ebx
0x18000dc13  mov     rdx, rbp
0x18000dc16  mov     rax, [rcx]
0x18000dc19  mov     rax, [rax+40h]
0x18000dc1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc22  mov     edi, eax
0x18000dc24  test    eax, eax
0x18000dc26  js      short loc_18000DC3C
0x18000dc28  mov     rcx, [rsp+58h+arg_10]
0x18000dc2d  mov     [r14], rcx
0x18000dc30  mov     rax, [rcx]
0x18000dc33  mov     rax, [rax+8]
0x18000dc37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc3c  mov     rcx, [rsp+58h+arg_10]
0x18000dc41  mov     rax, [rcx]
0x18000dc44  mov     rax, [rax+10h]
0x18000dc48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc4d  mov     rbx, [rsp+58h+arg_0]
0x18000dc52  mov     eax, edi
0x18000dc54  mov     rbp, [rsp+58h+arg_8]
0x18000dc59  add     rsp, 40h
0x18000dc5d  pop     r14
0x18000dc5f  pop     rdi
0x18000dc60  pop     rsi
0x18000dc61  retn
0x18000dc63  cmp     word ptr [rsp+58h+pvar], 12h
0x18000dc69  jnz     loc_18000DBCF
0x18000dc6f  xor     ebx, ebx
0x18000dc71  test    eax, eax
0x18000dc73  js      loc_18000DBD3
0x18000dc79  movzx   ecx, word ptr [rsp+58h+pvar+8]
0x18000dc7e  sub     ecx, 1
0x18000dc81  jz      loc_18000DBD3
0x18000dc87  sub     ecx, 1
0x18000dc8a  jz      short loc_18000DCE8
0x18000dc8c  sub     ecx, 1
0x18000dc8f  jz      short loc_18000DCDE
0x18000dc91  sub     ecx, 1
0x18000dc94  jz      short loc_18000DCD4
0x18000dc96  sub     ecx, 1
0x18000dc99  jz      short loc_18000DCCA
0x18000dc9b  sub     ecx, 1
0x18000dc9e  jz      short loc_18000DCB6
0x18000dca0  sub     ecx, 1
0x18000dca3  jz      short loc_18000DCC0
0x18000dca5  cmp     ecx, 1
0x18000dca8  jnz     loc_18000DBD3
0x18000dcae  lea     ebx, [rcx+2]
0x18000dcb1  jmp     loc_18000DBD3
0x18000dcb6  mov     ebx, 1
0x18000dcbb  jmp     loc_18000DBD3
0x18000dcc0  mov     ebx, 13h
0x18000dcc5  jmp     loc_18000DBD3
0x18000dcca  mov     ebx, 11h
0x18000dccf  jmp     loc_18000DBD3
0x18000dcd4  mov     ebx, 10h
0x18000dcd9  jmp     loc_18000DBD3
0x18000dcde  mov     ebx, 2
0x18000dce3  jmp     loc_18000DBD3
0x18000dce8  mov     ebx, 8
0x18000dced  jmp     loc_18000DBD3
```
