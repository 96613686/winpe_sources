# CMetadataContainer::_AddPaddingForContainer(IWICMetadataQueryWriter *)

- ea: `0x18001b878`
- end: `0x18001ba16`
- name: `?_AddPaddingForContainer@CMetadataContainer@@AEAAJPEAUIWICMetadataQueryWriter@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(CMetadataContainer *__hidden this, struct IWICMetadataQueryWriter *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c8f4`

## callees

- `0x18001b878`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001b9fc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001b9fc`

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
0x18001b878  mov     [rsp+arg_0], rbx
0x18001b87d  push    rdi
0x18001b87e  sub     rsp, 40h
0x18001b882  xor     eax, eax
0x18001b884  xorps   xmm0, xmm0
0x18001b887  mov     qword ptr [rsp+48h+pvar+10h], rax
0x18001b88c  mov     rdi, rdx
0x18001b88f  mov     eax, 13h
0x18001b894  movups  xmmword ptr [rsp+48h+pvar], xmm0
0x18001b899  mov     word ptr [rsp+48h+pvar], ax
0x18001b89e  mov     eax, 100h
0x18001b8a3  mov     word ptr [rsp+48h+pvar+8], ax
0x18001b8a8  mov     rax, [rcx+50h]
0x18001b8ac  sub     rax, qword ptr cs:GUID_ContainerFormatJpeg.Data1
0x18001b8b3  jnz     short loc_18001B8C0
0x18001b8b5  mov     rax, [rcx+58h]
0x18001b8b9  sub     rax, qword ptr cs:GUID_ContainerFormatJpeg.Data4
0x18001b8c0  test    rax, rax
0x18001b8c3  jnz     short loc_18001B91B
0x18001b8c5  mov     rax, [rdx]
0x18001b8c8  lea     r8, [rsp+48h+pvar]
0x18001b8cd  lea     rdx, aApp1IfdPadding; "/app1/ifd/PaddingSchema:Padding"
0x18001b8d4  mov     rcx, rdi
0x18001b8d7  mov     rax, [rax+38h]
0x18001b8db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8e0  mov     ebx, eax
0x18001b8e2  test    eax, eax
0x18001b8e4  js      loc_18001B9F7
0x18001b8ea  mov     rax, [rdi]
0x18001b8ed  lea     r8, [rsp+48h+pvar]
0x18001b8f2  lea     rdx, aApp1IfdExifPad; "/app1/ifd/exif/PaddingSchema:Padding"
0x18001b8f9  mov     rcx, rdi
0x18001b8fc  mov     rax, [rax+38h]
0x18001b900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b905  mov     ebx, eax
0x18001b907  test    eax, eax
0x18001b909  js      loc_18001B9F7
0x18001b90f  lea     rdx, aXmpPaddingsche; "/xmp/PaddingSchema:Padding"
0x18001b916  jmp     loc_18001B9E1
0x18001b91b  mov     rax, [rcx+50h]
0x18001b91f  sub     rax, qword ptr cs:GUID_ContainerFormatTiff.Data1
0x18001b926  jnz     short loc_18001B933
0x18001b928  mov     rax, [rcx+58h]
0x18001b92c  sub     rax, qword ptr cs:GUID_ContainerFormatTiff.Data4
0x18001b933  test    rax, rax
0x18001b936  jz      short loc_18001B998
0x18001b938  mov     rax, [rcx+50h]
0x18001b93c  sub     rax, qword ptr cs:GUID_ContainerFormatAdng.Data1
0x18001b943  jnz     short loc_18001B950
0x18001b945  mov     rax, [rcx+58h]
0x18001b949  sub     rax, qword ptr cs:GUID_ContainerFormatAdng.Data4
0x18001b950  test    rax, rax
0x18001b953  jz      short loc_18001B998
0x18001b955  mov     rax, [rcx+50h]
0x18001b959  sub     rax, qword ptr cs:GUID_ContainerFormatWmp.Data1
0x18001b960  jnz     short loc_18001B96D
0x18001b962  mov     rax, [rcx+58h]
0x18001b966  sub     rax, qword ptr cs:GUID_ContainerFormatWmp.Data4
0x18001b96d  test    rax, rax
0x18001b970  jz      short loc_18001B998
0x18001b972  mov     rax, [rcx+50h]
0x18001b976  mov     ebx, 88982F81h
0x18001b97b  sub     rax, qword ptr cs:GUID_ContainerFormatPng.Data1
0x18001b982  jnz     short loc_18001B98F
0x18001b984  mov     rax, [rcx+58h]
0x18001b988  sub     rax, qword ptr cs:GUID_ContainerFormatPng.Data4
0x18001b98f  test    rax, rax
0x18001b992  jnz     short loc_18001B9F7
0x18001b994  xor     ebx, ebx
0x18001b996  jmp     short loc_18001B9F7
0x18001b998  mov     rax, [rdx]
0x18001b99b  lea     r8, [rsp+48h+pvar]
0x18001b9a0  lea     rdx, aIfdPaddingsche; "/ifd/PaddingSchema:Padding"
0x18001b9a7  mov     rcx, rdi
0x18001b9aa  mov     rax, [rax+38h]
0x18001b9ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9b3  mov     ebx, eax
0x18001b9b5  test    eax, eax
0x18001b9b7  js      short loc_18001B9F7
0x18001b9b9  mov     rax, [rdi]
0x18001b9bc  lea     r8, [rsp+48h+pvar]
0x18001b9c1  lea     rdx, aIfdExifPadding; "/ifd/exif/PaddingSchema:Padding"
0x18001b9c8  mov     rcx, rdi
0x18001b9cb  mov     rax, [rax+38h]
0x18001b9cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9d4  mov     ebx, eax
0x18001b9d6  test    eax, eax
0x18001b9d8  js      short loc_18001B9F7
0x18001b9da  lea     rdx, aIfdXmpPaddings; "/ifd/xmp/PaddingSchema:Padding"
0x18001b9e1  mov     rax, [rdi]
0x18001b9e4  lea     r8, [rsp+48h+pvar]
0x18001b9e9  mov     rcx, rdi
0x18001b9ec  mov     rax, [rax+38h]
0x18001b9f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9f5  mov     ebx, eax
0x18001b9f7  lea     rcx, [rsp+48h+pvar]; pvar
0x18001b9fc  call    cs:__imp_PropVariantClear
0x18001ba03  nop     dword ptr [rax+rax+00h]
0x18001ba08  mov     eax, ebx
0x18001ba0a  mov     rbx, [rsp+48h+arg_0]
0x18001ba0f  add     rsp, 40h
0x18001ba13  pop     rdi
0x18001ba14  retn
```
