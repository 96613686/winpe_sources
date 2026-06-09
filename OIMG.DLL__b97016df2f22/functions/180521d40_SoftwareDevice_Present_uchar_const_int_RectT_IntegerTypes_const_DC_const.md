# SoftwareDevice::Present(uchar const *,int,RectT<IntegerTypes> const &,DC const &)

- ea: `0x180521d40`
- end: `0x180521fd6`
- name: `?Present@SoftwareDevice@@AEAAXPEBEHAEBU?$RectT@UIntegerTypes@@@@AEBVDC@@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180521acc`

## callees

- `0x18001397c`
- `0x18001db0c`
- `0x1804c6950`
- `0x180521d40`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180521e62`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180521e62`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180521ee4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180521ee4`
- `GDI32!CreateCompatibleDC` at `0x180521f1d`
- `GDI32!CreateCompatibleDC` at `0x180521f1d`
- `GDI32!DeleteDC` at `0x180521fa1`
- `GDI32!DeleteDC` at `0x180521fa1`
- `GDI32!CreateDIBitmap` at `0x180521e99`
- `GDI32!CreateDIBitmap` at `0x180521e99`
- `GDI32!BitBlt` at `0x180521f94`
- `GDI32!BitBlt` at `0x180521f94`
- `GDI32!SelectObject` at `0x180521f40`
- `GDI32!SelectObject` at `0x180521f40`
- `GDI32!DeleteObject` at `0x180521f32`
- `GDI32!DeleteObject` at `0x180521faa`
- `GDI32!DeleteObject` at `0x180521f32`
- `GDI32!DeleteObject` at `0x180521faa`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall SoftwareDevice::Present(__int64 a1, const void *a2, int a3, int *a4, __int64 a5)
{
  int v8; // r8d
  WORD v9; // ax
  DWORD v10; // ecx
  LONG v11; // edx
  __int64 v12; // r9
  void *v13; // rbx
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  void *v16; // rax
  HBITMAP v17; // rdi
  __int64 v18; // rcx
  HDC CompatibleDC; // rax
  HDC v21; // rbx
  __int64 v22; // r8
  __int64 v23; // rcx
  __int64 v24; // r9
  Base *v25; // rcx
  BITMAPINFOHEADER pbmih; // [rsp+68h] [rbp-29h] BYREF
  __int64 v27; // [rsp+90h] [rbp-1h]
  int v28; // [rsp+98h] [rbp+7h]

  v27 = 0;
  v28 = 0;
  v8 = *(_DWORD *)(a1 + 272);
  pbmih.biSize = 40;
  pbmih.biPlanes = 1;
  v9 = 32;
  if ( v8 == 1 )
    v9 = 16;
  pbmih.biBitCount = v9;
  v10 = 0;
  if ( v8 == 1 )
    v10 = 3;
  pbmih.biCompression = v10;
  if ( v8 == 1 )
  {
    v27 = 0x7E00000F800LL;
    v28 = 31;
  }
  memset(&pbmih.biSizeImage, 0, 20);
  v11 = a3 / 4;
  v12 = a4[3] - (__int64)a4[1];
  if ( (unsigned __int64)(v12 + 0x80000000LL) > 0xFFFFFFFF )
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  pbmih.biWidth = v11;
  pbmih.biHeight = -(int)v12;
  v13 = 0;
  if ( v8 == 1 )
  {
    v14 = 2LL * (unsigned int)(v11 % 2 + v11);
    if ( v14 > 0xFFFFFFFF
      || (v15 = (unsigned int)v14 * (unsigned __int64)(unsigned int)v12, v15 > 0xFFFFFFFF)
      || (unsigned int)v15 > 0x7FFFFFFF )
    {
      v17 = 0;
      goto LABEL_24;
    }
    v16 = malloc((int)v15);
    v13 = v16;
    if ( !v16 )
      ThrowOOM();
    a2 = v16;
  }
  v17 = CreateDIBitmap(*(HDC *)(a5 + 8), &pbmih, 4u, a2, (const BITMAPINFO *)&pbmih, 0);
  if ( v13 )
  {
    v18 = ImagingEngine::s_singleton ? *((_QWORD *)ImagingEngine::s_singleton + 10) : 0LL;
    if ( !v18 || (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v18 + 88LL))(v18, v13) != 0 )
      free(v13);
  }
LABEL_24:
  if ( v17 )
  {
    CompatibleDC = CreateCompatibleDC(*(HDC *)(a5 + 8));
    v21 = CompatibleDC;
    if ( CompatibleDC )
    {
      SelectObject(CompatibleDC, v17);
      v22 = a4[1];
      v23 = a4[3] - v22;
      if ( (unsigned __int64)(v23 + 0x80000000LL) > 0xFFFFFFFF
        || (v24 = a4[2] - (__int64)*a4, (unsigned __int64)(v24 + 0x80000000LL) > 0xFFFFFFFF) )
      {
        safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
      }
      if ( !BitBlt(*(HDC *)(a5 + 8), *a4, v22, v24, v23, v21, 0, 0, 0xCC0020u) )
        Base::ThrowLastError(v25);
      DeleteDC(v21);
      DeleteObject(v17);
    }
    else
    {
      DeleteObject(v17);
    }
  }
}

```

## disassembly

```asm
0x180521d40  push    rbp
0x180521d42  push    rbx
0x180521d43  push    rsi
0x180521d44  push    rdi
0x180521d45  push    r12
0x180521d47  push    r13
0x180521d49  push    r14
0x180521d4b  lea     rbp, [rsp-1Fh]
0x180521d50  sub     rsp, 0B0h
0x180521d57  mov     rax, cs:__security_cookie
0x180521d5e  xor     rax, rsp
0x180521d61  mov     [rbp+4Fh+var_40], rax
0x180521d65  mov     rsi, r9
0x180521d68  mov     r9d, r8d
0x180521d6b  mov     r10, rdx
0x180521d6e  mov     r14, [rbp+4Fh+arg_20]
0x180521d72  mov     [rbp+4Fh+var_50], 0
0x180521d7a  mov     [rbp+4Fh+var_48], 0
0x180521d81  mov     r8d, [rcx+110h]
0x180521d88  mov     [rbp+4Fh+pbmih.biSize], 28h ; '('
0x180521d8f  mov     r11d, 1
0x180521d95  mov     [rbp+4Fh+pbmih.biPlanes], r11w
0x180521d9a  lea     eax, [r11+1Fh]
0x180521d9e  lea     ecx, [rax-10h]
0x180521da1  cmp     r8d, r11d
0x180521da4  cmovz   ax, cx
0x180521da8  mov     [rbp+4Fh+pbmih.biBitCount], ax
0x180521dac  xor     ecx, ecx
0x180521dae  lea     ebx, [rcx+3]
0x180521db1  cmp     r8d, r11d
0x180521db4  cmovz   ecx, ebx
0x180521db7  mov     [rbp+4Fh+pbmih.biCompression], ecx
0x180521dba  jnz     short loc_180521DD1
0x180521dbc  mov     dword ptr [rbp+4Fh+var_50], 0F800h
0x180521dc3  mov     dword ptr [rbp+4Fh+var_50+4], 7E0h
0x180521dca  mov     [rbp+4Fh+var_48], 1Fh
0x180521dd1  mov     qword ptr [rbp+4Fh+pbmih.biSizeImage], 0
0x180521dd9  mov     qword ptr [rbp+4Fh+pbmih.biYPelsPerMeter], 0
0x180521de1  mov     [rbp+4Fh+pbmih.biClrImportant], 0
0x180521de8  mov     eax, r9d
0x180521deb  cdq
0x180521dec  and     edx, ebx
0x180521dee  add     edx, eax
0x180521df0  sar     edx, 2
0x180521df3  movsxd  r9, dword ptr [rsi+0Ch]
0x180521df7  movsxd  rcx, dword ptr [rsi+4]
0x180521dfb  sub     r9, rcx
0x180521dfe  mov     r13d, 80000000h
0x180521e04  lea     rcx, [r9+r13]
0x180521e08  mov     r12d, 0FFFFFFFFh
0x180521e0e  cmp     rcx, r12
0x180521e11  ja      loc_180521FBE
0x180521e17  mov     [rbp+4Fh+pbmih.biWidth], edx
0x180521e1a  mov     eax, r9d
0x180521e1d  neg     eax
0x180521e1f  mov     [rbp+4Fh+pbmih.biHeight], eax
0x180521e22  xor     ebx, ebx
0x180521e24  mov     [rbp+4Fh+var_90], rbx
0x180521e28  cmp     r8d, r11d
0x180521e2b  jnz     short loc_180521E77
0x180521e2d  mov     eax, edx
0x180521e2f  and     eax, 80000001h
0x180521e34  jge     short loc_180521E3F
0x180521e36  sub     eax, r11d
0x180521e39  or      eax, 0FFFFFFFEh
0x180521e3c  add     eax, r11d
0x180521e3f  add     edx, eax
0x180521e41  add     rdx, rdx
0x180521e44  cmp     rdx, r12
0x180521e47  ja      short loc_180521EB9
0x180521e49  mov     ecx, r9d
0x180521e4c  mov     eax, edx
0x180521e4e  imul    rcx, rax
0x180521e52  cmp     rcx, r12
0x180521e55  ja      short loc_180521EB9
0x180521e57  cmp     ecx, 7FFFFFFFh
0x180521e5d  ja      short loc_180521EB9
0x180521e5f  movsxd  rcx, ecx; Size
0x180521e62  call    cs:__imp_malloc
0x180521e68  mov     rbx, rax
0x180521e6b  test    rax, rax
0x180521e6e  jz      loc_180521FC7
0x180521e74  mov     r10, rax
0x180521e77  mov     [rsp+0E0h+iUsage], 0; iUsage
0x180521e7f  lea     rax, [rbp+4Fh+pbmih]
0x180521e83  mov     [rsp+0E0h+pbmi], rax; pbmi
0x180521e88  mov     r9, r10; pjBits
0x180521e8b  mov     r8d, 4; flInit
0x180521e91  lea     rdx, [rbp+4Fh+pbmih]; pbmih
0x180521e95  mov     rcx, [r14+8]; hdc
0x180521e99  call    cs:__imp_CreateDIBitmap
0x180521e9f  mov     rdi, rax
0x180521ea2  test    rbx, rbx
0x180521ea5  jz      short loc_180521EEA
0x180521ea7  mov     rax, cs:?s_singleton@ImagingEngine@@2USingleton@1@A; ImagingEngine::Singleton ImagingEngine::s_singleton
0x180521eae  test    rax, rax
0x180521eb1  jz      short loc_180521EBD
0x180521eb3  mov     rcx, [rax+50h]
0x180521eb7  jmp     short loc_180521EBF
0x180521eb9  xor     edi, edi
0x180521ebb  jmp     short loc_180521EEA
0x180521ebd  xor     ecx, ecx
0x180521ebf  test    rcx, rcx
0x180521ec2  jz      short loc_180521EDB
0x180521ec4  mov     rax, [rcx]
0x180521ec7  mov     rdx, rbx
0x180521eca  mov     rax, [rax+58h]
0x180521ece  call    cs:__guard_dispatch_icall_fptr
0x180521ed4  test    eax, eax
0x180521ed6  setz    al
0x180521ed9  jmp     short loc_180521EDD
0x180521edb  xor     al, al
0x180521edd  test    al, al
0x180521edf  jnz     short loc_180521EEA
0x180521ee1  mov     rcx, rbx; Block
0x180521ee4  call    cs:__imp_free
0x180521eea  mov     [rbp+4Fh+var_90], rdi
0x180521eee  test    rdi, rdi
0x180521ef1  jnz     short loc_180521F11
0x180521ef3  mov     rcx, [rbp+4Fh+var_40]
0x180521ef7  xor     rcx, rsp; StackCookie
0x180521efa  call    __security_check_cookie
0x180521eff  add     rsp, 0B0h
0x180521f06  pop     r14
0x180521f08  pop     r13
0x180521f0a  pop     r12
0x180521f0c  pop     rdi
0x180521f0d  pop     rsi
0x180521f0e  pop     rbx
0x180521f0f  pop     rbp
0x180521f10  retn
0x180521f11  mov     [rbp+4Fh+var_88], 0
0x180521f19  mov     rcx, [r14+8]; hdc
0x180521f1d  call    cs:__imp_CreateCompatibleDC
0x180521f23  mov     rbx, rax
0x180521f26  mov     [rbp+4Fh+var_80], rax
0x180521f2a  test    rax, rax
0x180521f2d  jnz     short loc_180521F3A
0x180521f2f  mov     rcx, rdi; ho
0x180521f32  call    cs:__imp_DeleteObject
0x180521f38  jmp     short loc_180521EF3
0x180521f3a  mov     rdx, rdi; h
0x180521f3d  mov     rcx, rbx; hdc
0x180521f40  call    cs:__imp_SelectObject
0x180521f46  movsxd  r8, dword ptr [rsi+4]; y
0x180521f4a  movsxd  rcx, dword ptr [rsi+0Ch]
0x180521f4e  sub     rcx, r8
0x180521f51  lea     rax, [rcx+r13]
0x180521f55  cmp     rax, r12
0x180521f58  ja      short loc_180521FB5
0x180521f5a  movsxd  r9, dword ptr [rsi+8]
0x180521f5e  movsxd  rax, dword ptr [rsi]
0x180521f61  sub     r9, rax; cx
0x180521f64  lea     rax, [r9+r13]
0x180521f68  cmp     rax, r12
0x180521f6b  ja      short loc_180521FB5
0x180521f6d  mov     [rsp+0E0h+rop], 0CC0020h; rop
0x180521f75  mov     [rsp+0E0h+y1], 0; y1
0x180521f7d  mov     [rsp+0E0h+x1], 0; x1
0x180521f85  mov     qword ptr [rsp+0E0h+iUsage], rbx; hdcSrc
0x180521f8a  mov     dword ptr [rsp+0E0h+pbmi], ecx; cy
0x180521f8e  mov     edx, [rsi]; x
0x180521f90  mov     rcx, [r14+8]; hdc
0x180521f94  call    cs:__imp_BitBlt
0x180521f9a  test    eax, eax
0x180521f9c  jz      short loc_180521FD0
0x180521f9e  mov     rcx, rbx; hdc
0x180521fa1  call    cs:__imp_DeleteDC
0x180521fa7  mov     rcx, rdi; ho
0x180521faa  call    cs:__imp_DeleteObject
0x180521fb0  jmp     loc_180521EF3
0x180521fb5  call    ?SafeIntOnOverflow@SafeInt_InvalidParameter@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow(void)
0x180521fbb  jmp     short $+2
0x180521fbd  nop
0x180521fbe  call    ?SafeIntOnOverflow@SafeInt_InvalidParameter@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow(void)
0x180521fc4  jmp     short $+2
0x180521fc6  nop
0x180521fc7  call    ?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x180521fcd  jmp     short $+2
0x180521fcf  nop
0x180521fd0  call    ?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
```
