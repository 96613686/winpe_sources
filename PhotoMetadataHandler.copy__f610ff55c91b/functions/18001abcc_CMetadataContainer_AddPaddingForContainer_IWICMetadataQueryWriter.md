# CMetadataContainer::_AddPaddingForContainer(IWICMetadataQueryWriter *)

- ea: `0x18001abcc`
- end: `0x18001ad63`
- name: `?_AddPaddingForContainer@CMetadataContainer@@AEAAJPEAUIWICMetadataQueryWriter@@@Z`
- size: `407`
- prototype: `__int64 __fastcall(CMetadataContainer *__hidden this, struct IWICMetadataQueryWriter *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001bc00`

## callees

- `0x18001abcc`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ad50`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ad50`

## pseudocode

```c
__int64 __fastcall CMetadataContainer::_AddPaddingForContainer(
        CMetadataContainer *this,
        struct IWICMetadataQueryWriter *a2)
{
  __int64 v3; // rax
  int v4; // ebx
  const wchar_t *v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  PROPVARIANT pvar; // [rsp+20h] [rbp-28h] BYREF

  memset(&pvar, 0, sizeof(pvar));
  pvar.vt = 19;
  pvar.iVal = 256;
  v3 = *((_QWORD *)this + 10) - *(_QWORD *)&GUID_ContainerFormatJpeg.Data1;
  if ( !v3 )
    v3 = *((_QWORD *)this + 11) - *(_QWORD *)GUID_ContainerFormatJpeg.Data4;
  if ( v3 )
  {
    v6 = *((_QWORD *)this + 10) - *(_QWORD *)&GUID_ContainerFormatTiff.Data1;
    if ( !v6 )
      v6 = *((_QWORD *)this + 11) - *(_QWORD *)GUID_ContainerFormatTiff.Data4;
    if ( !v6 )
      goto LABEL_20;
    v7 = *((_QWORD *)this + 10) - *(_QWORD *)&GUID_ContainerFormatAdng.Data1;
    if ( !v7 )
      v7 = *((_QWORD *)this + 11) - *(_QWORD *)GUID_ContainerFormatAdng.Data4;
    if ( !v7 )
      goto LABEL_20;
    v8 = *((_QWORD *)this + 10) - *(_QWORD *)&GUID_ContainerFormatWmp.Data1;
    if ( !v8 )
      v8 = *((_QWORD *)this + 11) - *(_QWORD *)GUID_ContainerFormatWmp.Data4;
    if ( v8 )
    {
      v4 = -2003292287;
      v9 = *((_QWORD *)this + 10) - *(_QWORD *)&GUID_ContainerFormatPng.Data1;
      if ( !v9 )
        v9 = *((_QWORD *)this + 11) - *(_QWORD *)GUID_ContainerFormatPng.Data4;
      if ( !v9 )
        v4 = 0;
    }
    else
    {
LABEL_20:
      v4 = ((__int64 (__fastcall *)(struct IWICMetadataQueryWriter *, const wchar_t *, PROPVARIANT *))a2->lpVtbl->SetMetadataByName)(
             a2,
             L"/ifd/PaddingSchema:Padding",
             &pvar);
      if ( v4 >= 0 )
      {
        v4 = ((__int64 (__fastcall *)(struct IWICMetadataQueryWriter *, const wchar_t *, PROPVARIANT *))a2->lpVtbl->SetMetadataByName)(
               a2,
               L"/ifd/exif/PaddingSchema:Padding",
               &pvar);
        if ( v4 >= 0 )
        {
          v5 = L"/ifd/xmp/PaddingSchema:Padding";
          goto LABEL_23;
        }
      }
    }
  }
  else
  {
    v4 = ((__int64 (__fastcall *)(struct IWICMetadataQueryWriter *, const wchar_t *, PROPVARIANT *))a2->lpVtbl->SetMetadataByName)(
           a2,
           L"/app1/ifd/PaddingSchema:Padding",
           &pvar);
    if ( v4 >= 0 )
    {
      v4 = ((__int64 (__fastcall *)(struct IWICMetadataQueryWriter *, const wchar_t *, PROPVARIANT *))a2->lpVtbl->SetMetadataByName)(
             a2,
             L"/app1/ifd/exif/PaddingSchema:Padding",
             &pvar);
      if ( v4 >= 0 )
      {
        v5 = L"/xmp/PaddingSchema:Padding";
LABEL_23:
        v4 = ((__int64 (__fastcall *)(struct IWICMetadataQueryWriter *, const wchar_t *, PROPVARIANT *))a2->lpVtbl->SetMetadataByName)(
               a2,
               v5,
               &pvar);
      }
    }
  }
  PropVariantClear(&pvar);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001abcc  mov     [rsp+arg_0], rbx
0x18001abd1  push    rdi
0x18001abd2  sub     rsp, 40h
0x18001abd6  xor     eax, eax
0x18001abd8  xorps   xmm0, xmm0
0x18001abdb  mov     qword ptr [rsp+48h+pvar+10h], rax
0x18001abe0  mov     rdi, rdx
0x18001abe3  mov     eax, 13h
0x18001abe8  movups  xmmword ptr [rsp+48h+pvar], xmm0
0x18001abed  mov     word ptr [rsp+48h+pvar], ax
0x18001abf2  mov     eax, 100h
0x18001abf7  mov     word ptr [rsp+48h+pvar+8], ax
0x18001abfc  mov     rax, [rcx+50h]
0x18001ac00  sub     rax, qword ptr cs:GUID_ContainerFormatJpeg.Data1
0x18001ac07  jnz     short loc_18001AC14
0x18001ac09  mov     rax, [rcx+58h]
0x18001ac0d  sub     rax, qword ptr cs:GUID_ContainerFormatJpeg.Data4
0x18001ac14  test    rax, rax
0x18001ac17  jnz     short loc_18001AC6F
0x18001ac19  mov     rax, [rdx]
0x18001ac1c  lea     r8, [rsp+48h+pvar]
0x18001ac21  lea     rdx, aApp1IfdPadding; "/app1/ifd/PaddingSchema:Padding"
0x18001ac28  mov     rcx, rdi
0x18001ac2b  mov     rax, [rax+38h]
0x18001ac2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac34  mov     ebx, eax
0x18001ac36  test    eax, eax
0x18001ac38  js      loc_18001AD4B
0x18001ac3e  mov     rax, [rdi]
0x18001ac41  lea     r8, [rsp+48h+pvar]
0x18001ac46  lea     rdx, aApp1IfdExifPad; "/app1/ifd/exif/PaddingSchema:Padding"
0x18001ac4d  mov     rcx, rdi
0x18001ac50  mov     rax, [rax+38h]
0x18001ac54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac59  mov     ebx, eax
0x18001ac5b  test    eax, eax
0x18001ac5d  js      loc_18001AD4B
0x18001ac63  lea     rdx, aXmpPaddingsche; "/xmp/PaddingSchema:Padding"
0x18001ac6a  jmp     loc_18001AD35
0x18001ac6f  mov     rax, [rcx+50h]
0x18001ac73  sub     rax, qword ptr cs:GUID_ContainerFormatTiff.Data1
0x18001ac7a  jnz     short loc_18001AC87
0x18001ac7c  mov     rax, [rcx+58h]
0x18001ac80  sub     rax, qword ptr cs:GUID_ContainerFormatTiff.Data4
0x18001ac87  test    rax, rax
0x18001ac8a  jz      short loc_18001ACEC
0x18001ac8c  mov     rax, [rcx+50h]
0x18001ac90  sub     rax, qword ptr cs:GUID_ContainerFormatAdng.Data1
0x18001ac97  jnz     short loc_18001ACA4
0x18001ac99  mov     rax, [rcx+58h]
0x18001ac9d  sub     rax, qword ptr cs:GUID_ContainerFormatAdng.Data4
0x18001aca4  test    rax, rax
0x18001aca7  jz      short loc_18001ACEC
0x18001aca9  mov     rax, [rcx+50h]
0x18001acad  sub     rax, qword ptr cs:GUID_ContainerFormatWmp.Data1
0x18001acb4  jnz     short loc_18001ACC1
0x18001acb6  mov     rax, [rcx+58h]
0x18001acba  sub     rax, qword ptr cs:GUID_ContainerFormatWmp.Data4
0x18001acc1  test    rax, rax
0x18001acc4  jz      short loc_18001ACEC
0x18001acc6  mov     rax, [rcx+50h]
0x18001acca  mov     ebx, 88982F81h
0x18001accf  sub     rax, qword ptr cs:GUID_ContainerFormatPng.Data1
0x18001acd6  jnz     short loc_18001ACE3
0x18001acd8  mov     rax, [rcx+58h]
0x18001acdc  sub     rax, qword ptr cs:GUID_ContainerFormatPng.Data4
0x18001ace3  test    rax, rax
0x18001ace6  jnz     short loc_18001AD4B
0x18001ace8  xor     ebx, ebx
0x18001acea  jmp     short loc_18001AD4B
0x18001acec  mov     rax, [rdx]
0x18001acef  lea     r8, [rsp+48h+pvar]
0x18001acf4  lea     rdx, aIfdPaddingsche; "/ifd/PaddingSchema:Padding"
0x18001acfb  mov     rcx, rdi
0x18001acfe  mov     rax, [rax+38h]
0x18001ad02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad07  mov     ebx, eax
0x18001ad09  test    eax, eax
0x18001ad0b  js      short loc_18001AD4B
0x18001ad0d  mov     rax, [rdi]
0x18001ad10  lea     r8, [rsp+48h+pvar]
0x18001ad15  lea     rdx, aIfdExifPadding; "/ifd/exif/PaddingSchema:Padding"
0x18001ad1c  mov     rcx, rdi
0x18001ad1f  mov     rax, [rax+38h]
0x18001ad23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad28  mov     ebx, eax
0x18001ad2a  test    eax, eax
0x18001ad2c  js      short loc_18001AD4B
0x18001ad2e  lea     rdx, aIfdXmpPaddings; "/ifd/xmp/PaddingSchema:Padding"
0x18001ad35  mov     rax, [rdi]
0x18001ad38  lea     r8, [rsp+48h+pvar]
0x18001ad3d  mov     rcx, rdi
0x18001ad40  mov     rax, [rax+38h]
0x18001ad44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad49  mov     ebx, eax
0x18001ad4b  lea     rcx, [rsp+48h+pvar]; pvar
0x18001ad50  call    cs:__imp_PropVariantClear
0x18001ad56  mov     eax, ebx
0x18001ad58  mov     rbx, [rsp+48h+arg_0]
0x18001ad5d  add     rsp, 40h
0x18001ad61  pop     rdi
0x18001ad62  retn
```
