# WICCreateCachedOrientedBitmapSource(IWICImagingFactory *,IWICBitmapSource *,IWICMetadataQueryReader *,IWICBitmapSource * *)

- ea: `0x18000bd3c`
- end: `0x18000be77`
- name: `?WICCreateCachedOrientedBitmapSource@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@PEAUIWICMetadataQueryReader@@PEAPEAU2@@Z`
- size: `315`
- prototype: `__int64 __fastcall(struct IWICImagingFactory *, struct IWICBitmapSource *, struct IWICMetadataQueryReader *, struct IWICBitmapSource **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ae9c`

## callees

- `0x18000bd3c`
- `0x18000be80`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall WICCreateCachedOrientedBitmapSource(
        struct IWICImagingFactory *a1,
        struct IWICBitmapSource *a2,
        struct IWICMetadataQueryReader *a3,
        struct IWICBitmapSource **a4)
{
  int v7; // ebx
  struct IWICImagingFactoryVtbl *lpVtbl; // rax
  struct IWICImagingFactoryVtbl *v9; // rax
  struct IWICBitmapSource *v10; // rcx
  struct IWICBitmapSource *v12; // [rsp+30h] [rbp-10h] BYREF
  __int64 v13; // [rsp+38h] [rbp-8h] BYREF
  WICBitmapTransformOptions v14; // [rsp+78h] [rbp+38h] BYREF

  *a4 = 0;
  v14 = WICBitmapTransformRotate0;
  v7 = WICGetTransformOptionFromMetadata(a3, &v14);
  if ( v7 >= 0 )
  {
    if ( v14 == WICBitmapTransformRotate0 )
    {
      *a4 = a2;
      ((void (__fastcall *)(struct IWICBitmapSource *))a2->lpVtbl->AddRef)(a2);
      return (unsigned int)v7;
    }
    lpVtbl = a1->lpVtbl;
    v12 = 0;
    v7 = ((__int64 (__fastcall *)(struct IWICImagingFactory *, struct IWICBitmapSource **))lpVtbl->CreateBitmapFlipRotator)(
           a1,
           &v12);
    if ( v7 < 0 )
      return (unsigned int)v7;
    if ( (v14 & 0x11) != 0 || v14 == WICBitmapTransformRotate180 )
    {
      v9 = a1->lpVtbl;
      v13 = 0;
      v7 = ((__int64 (__fastcall *)(struct IWICImagingFactory *, struct IWICBitmapSource *, __int64, __int64 *))v9->CreateBitmapFromSource)(
             a1,
             a2,
             2,
             &v13);
      if ( v7 < 0 )
      {
LABEL_12:
        ((void (__fastcall *)(struct IWICBitmapSource *))v12->lpVtbl->Release)(v12);
        return (unsigned int)v7;
      }
      v7 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, __int64, _QWORD))v12->lpVtbl[1].QueryInterface)(
             v12,
             v13,
             (unsigned int)v14);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    else
    {
      v7 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, struct IWICBitmapSource *, _QWORD))v12->lpVtbl[1].QueryInterface)(
             v12,
             a2,
             (unsigned int)v14);
    }
    if ( v7 >= 0 )
    {
      v10 = v12;
      *a4 = v12;
      ((void (__fastcall *)(struct IWICBitmapSource *))v10->lpVtbl->AddRef)(v10);
    }
    goto LABEL_12;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000bd3c  mov     [rsp-18h+arg_0], rbx
0x18000bd41  mov     [rsp-18h+arg_8], rsi
0x18000bd46  push    rbp
0x18000bd47  push    r14
0x18000bd49  push    r15
0x18000bd4b  mov     rbp, rsp
0x18000bd4e  sub     rsp, 40h
0x18000bd52  mov     rsi, rdx
0x18000bd55  mov     qword ptr [r9], 0
0x18000bd5c  mov     r14, rcx
0x18000bd5f  mov     [rbp+arg_18], 0
0x18000bd66  lea     rdx, [rbp+arg_18]; enum WICBitmapTransformOptions *
0x18000bd6a  mov     rcx, r8; struct IWICMetadataQueryReader *
0x18000bd6d  mov     r15, r9
0x18000bd70  call    ?WICGetTransformOptionFromMetadata@@YAJPEAUIWICMetadataQueryReader@@PEAW4WICBitmapTransformOptions@@@Z; WICGetTransformOptionFromMetadata(IWICMetadataQueryReader *,WICBitmapTransformOptions *)
0x18000bd75  mov     ebx, eax
0x18000bd77  test    eax, eax
0x18000bd79  js      loc_18000BE61
0x18000bd7f  cmp     [rbp+arg_18], 0
0x18000bd83  jnz     short loc_18000BD97
0x18000bd85  mov     [r15], rsi
0x18000bd88  mov     rcx, [rsi]
0x18000bd8b  mov     rax, [rcx+8]
0x18000bd8f  mov     rcx, rsi
0x18000bd92  jmp     loc_18000BE5C
0x18000bd97  mov     rax, [r14]
0x18000bd9a  lea     rdx, [rbp+var_10]
0x18000bd9e  mov     rcx, r14
0x18000bda1  mov     [rbp+var_10], 0
0x18000bda9  mov     rax, [rax+68h]
0x18000bdad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdb2  mov     ebx, eax
0x18000bdb4  test    eax, eax
0x18000bdb6  js      loc_18000BE61
0x18000bdbc  test    byte ptr [rbp+arg_18], 11h
0x18000bdc0  mov     r8d, 2
0x18000bdc6  jnz     short loc_18000BDE9
0x18000bdc8  cmp     [rbp+arg_18], r8d
0x18000bdcc  jz      short loc_18000BDE9
0x18000bdce  mov     rcx, [rbp+var_10]
0x18000bdd2  mov     rdx, rsi
0x18000bdd5  mov     r8d, [rbp+arg_18]
0x18000bdd9  mov     rax, [rcx]
0x18000bddc  mov     rax, [rax+40h]
0x18000bde0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bde5  mov     ebx, eax
0x18000bde7  jmp     short loc_18000BE3A
0x18000bde9  mov     rax, [r14]
0x18000bdec  lea     r9, [rbp+var_8]
0x18000bdf0  mov     rdx, rsi
0x18000bdf3  mov     [rbp+var_8], 0
0x18000bdfb  mov     rcx, r14
0x18000bdfe  mov     rax, [rax+90h]
0x18000be05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be0a  mov     ebx, eax
0x18000be0c  test    eax, eax
0x18000be0e  js      short loc_18000BE51
0x18000be10  mov     rcx, [rbp+var_10]
0x18000be14  mov     r8d, [rbp+arg_18]
0x18000be18  mov     rdx, [rbp+var_8]
0x18000be1c  mov     rax, [rcx]
0x18000be1f  mov     rax, [rax+40h]
0x18000be23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be28  mov     rcx, [rbp+var_8]
0x18000be2c  mov     ebx, eax
0x18000be2e  mov     rax, [rcx]
0x18000be31  mov     rax, [rax+10h]
0x18000be35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be3a  test    ebx, ebx
0x18000be3c  js      short loc_18000BE51
0x18000be3e  mov     rcx, [rbp+var_10]
0x18000be42  mov     [r15], rcx
0x18000be45  mov     rax, [rcx]
0x18000be48  mov     rax, [rax+8]
0x18000be4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be51  mov     rcx, [rbp+var_10]
0x18000be55  mov     rax, [rcx]
0x18000be58  mov     rax, [rax+10h]
0x18000be5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be61  mov     rsi, [rsp+40h+arg_8]
0x18000be66  mov     eax, ebx
0x18000be68  mov     rbx, [rsp+40h+arg_0]
0x18000be6d  add     rsp, 40h
0x18000be71  pop     r15
0x18000be73  pop     r14
0x18000be75  pop     rbp
0x18000be76  retn
```
