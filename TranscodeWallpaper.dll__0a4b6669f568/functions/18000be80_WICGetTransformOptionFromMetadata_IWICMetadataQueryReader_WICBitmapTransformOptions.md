# WICGetTransformOptionFromMetadata(IWICMetadataQueryReader *,WICBitmapTransformOptions *)

- ea: `0x18000be80`
- end: `0x18000bf54`
- name: `?WICGetTransformOptionFromMetadata@@YAJPEAUIWICMetadataQueryReader@@PEAW4WICBitmapTransformOptions@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(struct IWICMetadataQueryReader *, enum WICBitmapTransformOptions *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000bd3c`

## callees

- `0x18000be80`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bf41`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bf41`

## pseudocode

```c
__int64 __fastcall WICGetTransformOptionFromMetadata(
        struct IWICMetadataQueryReader *a1,
        enum WICBitmapTransformOptions *a2)
{
  struct IWICMetadataQueryReaderVtbl *lpVtbl; // rax
  int v4; // eax
  unsigned int v5; // edi
  PROPVARIANT pvar; // [rsp+20h] [rbp-28h] BYREF

  *a2 = WICBitmapTransformRotate0;
  lpVtbl = a1->lpVtbl;
  memset(&pvar, 0, sizeof(pvar));
  v4 = ((__int64 (__fastcall *)(struct IWICMetadataQueryReader *, const wchar_t *, PROPVARIANT *))lpVtbl->GetMetadataByName)(
         a1,
         L"System.Photo.Orientation",
         &pvar);
  v5 = v4;
  if ( v4 == -2003292352 || pvar.vt != 18 )
  {
    v5 = 0;
    goto LABEL_20;
  }
  if ( v4 >= 0 )
  {
    if ( pvar.uiVal != 1 )
    {
      switch ( pvar.uiVal )
      {
        case 2u:
          *a2 = WICBitmapTransformFlipHorizontal;
          goto LABEL_21;
        case 3u:
          *a2 = WICBitmapTransformRotate180;
          goto LABEL_21;
        case 4u:
          *a2 = WICBitmapTransformFlipVertical;
          goto LABEL_21;
        case 5u:
          *a2 = WICBitmapTransformFlipVertical|WICBitmapTransformRotate90;
          goto LABEL_21;
        case 6u:
          *a2 = WICBitmapTransformRotate90;
          goto LABEL_21;
        case 7u:
          *a2 = WICBitmapTransformFlipVertical|WICBitmapTransformRotate270;
          goto LABEL_21;
        case 8u:
          *a2 = WICBitmapTransformRotate270;
          goto LABEL_21;
      }
    }
LABEL_20:
    *a2 = WICBitmapTransformRotate0;
  }
LABEL_21:
  PropVariantClear(&pvar);
  return v5;
}

```

## disassembly

```asm
0x18000be80  mov     [rsp+arg_0], rbx
0x18000be85  push    rdi
0x18000be86  sub     rsp, 40h
0x18000be8a  xor     eax, eax
0x18000be8c  mov     dword ptr [rdx], 0
0x18000be92  mov     qword ptr [rsp+48h+pvar+10h], rax
0x18000be97  lea     r8, [rsp+48h+pvar]
0x18000be9c  mov     rax, [rcx]
0x18000be9f  mov     rbx, rdx
0x18000bea2  xorps   xmm0, xmm0
0x18000bea5  lea     rdx, aSystemPhotoOri; "System.Photo.Orientation"
0x18000beac  movups  xmmword ptr [rsp+48h+pvar], xmm0
0x18000beb1  mov     rax, [rax+28h]
0x18000beb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000beba  mov     edi, eax
0x18000bebc  cmp     eax, 88982F40h
0x18000bec1  jz      short loc_18000BF34
0x18000bec3  cmp     word ptr [rsp+48h+pvar], 12h
0x18000bec9  jnz     short loc_18000BF34
0x18000becb  test    eax, eax
0x18000becd  js      short loc_18000BF3C
0x18000becf  movzx   edx, word ptr [rsp+48h+pvar+8]
0x18000bed4  sub     edx, 1
0x18000bed7  jz      short loc_18000BF36
0x18000bed9  sub     edx, 1
0x18000bedc  jz      short loc_18000BF2C
0x18000bede  sub     edx, 1
0x18000bee1  jz      short loc_18000BF24
0x18000bee3  sub     edx, 1
0x18000bee6  jz      short loc_18000BF1C
0x18000bee8  sub     edx, 1
0x18000beeb  jz      short loc_18000BF14
0x18000beed  sub     edx, 1
0x18000bef0  jz      short loc_18000BF0C
0x18000bef2  sub     edx, 1
0x18000bef5  jz      short loc_18000BF04
0x18000bef7  cmp     edx, 1
0x18000befa  jnz     short loc_18000BF36
0x18000befc  mov     dword ptr [rbx], 3
0x18000bf02  jmp     short loc_18000BF3C
0x18000bf04  mov     dword ptr [rbx], 13h
0x18000bf0a  jmp     short loc_18000BF3C
0x18000bf0c  mov     dword ptr [rbx], 1
0x18000bf12  jmp     short loc_18000BF3C
0x18000bf14  mov     dword ptr [rbx], 11h
0x18000bf1a  jmp     short loc_18000BF3C
0x18000bf1c  mov     dword ptr [rbx], 10h
0x18000bf22  jmp     short loc_18000BF3C
0x18000bf24  mov     dword ptr [rbx], 2
0x18000bf2a  jmp     short loc_18000BF3C
0x18000bf2c  mov     dword ptr [rbx], 8
0x18000bf32  jmp     short loc_18000BF3C
0x18000bf34  xor     edi, edi
0x18000bf36  mov     dword ptr [rbx], 0
0x18000bf3c  lea     rcx, [rsp+48h+pvar]; pvar
0x18000bf41  call    cs:__imp_PropVariantClear
0x18000bf47  mov     rbx, [rsp+48h+arg_0]
0x18000bf4c  mov     eax, edi
0x18000bf4e  add     rsp, 40h
0x18000bf52  pop     rdi
0x18000bf53  retn
```
