# CImage::CreateDIBSectionFromBitmapSource(HDC__ *,IWICBitmapSource *)

- ea: `0x1801e65c0`
- end: `0x1801e67ad`
- name: `?CreateDIBSectionFromBitmapSource@CImage@@AEAAJPEAUHDC__@@PEAUIWICBitmapSource@@@Z`
- size: `493`
- prototype: `int(CImage *__hidden this, HDC, struct IWICBitmapSource *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1801e6130`

## callees

- `0x18013bad0`
- `0x18013c8f2`
- `0x1801e65c0`
- `0x18027a010`

## import_xrefs

- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x1801e678f`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x1801e678f`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801e66d8`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801e66d8`

## pseudocode

```c
__int64 __fastcall CImage::CreateDIBSectionFromBitmapSource(CImage *this, HDC a2, struct IWICBitmapSource *a3)
{
  struct IWICBitmapSourceVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetPixelFormat)(IWICBitmapSource *, WICPixelFormatGUID *); // rax
  signed int v8; // ebx
  unsigned __int64 v9; // rax
  __int64 v10; // r8
  unsigned __int64 v11; // rcx
  __int64 v12; // r9
  void *v13; // rcx
  HBITMAP v15; // rax
  unsigned int v16; // [rsp+30h] [rbp-29h] BYREF
  unsigned int v17; // [rsp+34h] [rbp-25h] BYREF
  void *ppvBits; // [rsp+38h] [rbp-21h] BYREF
  __int128 Buf1; // [rsp+40h] [rbp-19h] BYREF
  BITMAPINFO pbmi; // [rsp+50h] [rbp-9h] BYREF

  lpVtbl = a3->lpVtbl;
  v16 = 0;
  v17 = 0;
  ppvBits = 0;
  GetPixelFormat = lpVtbl->GetPixelFormat;
  Buf1 = 0;
  v8 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, __int128 *))GetPixelFormat)(a3, &Buf1);
  if ( v8 < 0 )
    goto LABEL_14;
  if ( *((_BYTE *)this + 211) )
  {
    if ( memcmp_0(&Buf1, &GUID_WICPixelFormat32bppPBGRA, 0x10u) )
      v8 = -2147467259;
    if ( v8 < 0 )
      goto LABEL_14;
  }
  else if ( memcmp_0(&Buf1, &GUID_WICPixelFormat32bppBGR, 0x10u) )
  {
LABEL_20:
    v8 = -2147467259;
    goto LABEL_14;
  }
  v8 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, unsigned int *, unsigned int *))a3->lpVtbl->GetSize)(
         a3,
         &v16,
         &v17);
  if ( v8 < 0 )
  {
LABEL_14:
    v13 = (void *)*((_QWORD *)this + 16);
    if ( v13 )
    {
      DeleteObject(v13);
      *((_QWORD *)this + 16) = 0;
    }
    return (unsigned int)v8;
  }
  pbmi.bmiHeader.biWidth = v16;
  pbmi.bmiHeader.biHeight = -v17;
  memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
  pbmi.bmiHeader.biSize = 40;
  *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  v15 = CreateDIBSection(a2, &pbmi, 0, &ppvBits, 0, 0);
  *((_QWORD *)this + 16) = v15;
  if ( !v15 )
    goto LABEL_20;
  v9 = 4LL * v16;
  v10 = 4 * v16;
  if ( v9 > 0xFFFFFFFF )
    v10 = 0xFFFFFFFFLL;
  v8 = v9 > 0xFFFFFFFF ? 0x80070216 : 0;
  if ( v9 > 0xFFFFFFFF )
    goto LABEL_14;
  v11 = v17 * (unsigned __int64)(unsigned int)v10;
  v12 = v17 * (unsigned int)v10;
  if ( v11 > 0xFFFFFFFF )
    v12 = 0xFFFFFFFFLL;
  v8 = v11 > 0xFFFFFFFF ? 0x80070216 : 0;
  if ( v11 > 0xFFFFFFFF )
    goto LABEL_14;
  v8 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, _QWORD, __int64, __int64, void *))a3->lpVtbl->CopyPixels)(
         a3,
         0,
         v10,
         v12,
         ppvBits);
  if ( v8 < 0 )
    goto LABEL_14;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1801e65c0  mov     [rsp-8+arg_18], rbx
0x1801e65c5  push    rbp
0x1801e65c6  push    rsi
0x1801e65c7  push    rdi
0x1801e65c8  push    r12
0x1801e65ca  push    r14
0x1801e65cc  lea     rbp, [rsp-37h]
0x1801e65d1  sub     rsp, 90h
0x1801e65d8  mov     rax, cs:__security_cookie
0x1801e65df  xor     rax, rsp
0x1801e65e2  mov     [rbp+57h+var_30], rax
0x1801e65e6  mov     rax, [r8]
0x1801e65e9  mov     r14, rdx
0x1801e65ec  mov     rdi, rcx
0x1801e65ef  mov     [rbp+57h+var_80], 0
0x1801e65f6  xorps   xmm0, xmm0
0x1801e65f9  mov     [rbp+57h+var_7C], 0
0x1801e6600  lea     rdx, [rbp+57h+Buf1]
0x1801e6604  mov     [rbp+57h+ppvBits], 0
0x1801e660c  mov     rax, [rax+20h]
0x1801e6610  mov     rcx, r8
0x1801e6613  mov     rsi, r8
0x1801e6616  movups  [rbp+57h+Buf1], xmm0
0x1801e661a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e661f  mov     ebx, eax
0x1801e6621  test    eax, eax
0x1801e6623  js      short loc_1801E665C
0x1801e6625  cmp     byte ptr [rdi+0D3h], 0
0x1801e662c  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1801e6630  mov     r12d, 80004005h
0x1801e6636  mov     r8d, 10h; Size
0x1801e663c  jz      loc_1801E670E
0x1801e6642  lea     rdx, GUID_WICPixelFormat32bppPBGRA; Buf2
0x1801e6649  call    memcmp_0
0x1801e664e  test    eax, eax
0x1801e6650  cmovnz  ebx, r12d
0x1801e6654  test    ebx, ebx
0x1801e6656  jns     loc_1801E6722
0x1801e665c  test    ebx, ebx
0x1801e665e  js      short loc_1801E66CC
0x1801e6660  mov     eax, [rbp+57h+var_80]
0x1801e6663  mov     edx, 0FFFFFFFFh
0x1801e6668  shl     rax, 2
0x1801e666c  mov     r8d, eax
0x1801e666f  cmp     rax, rdx
0x1801e6672  jbe     short loc_1801E6677
0x1801e6674  mov     r8d, edx
0x1801e6677  cmp     rdx, rax
0x1801e667a  mov     r10d, 80070216h
0x1801e6680  sbb     ebx, ebx
0x1801e6682  and     ebx, r10d
0x1801e6685  cmp     rax, rdx
0x1801e6688  ja      short loc_1801E66CC
0x1801e668a  mov     eax, [rbp+57h+var_7C]
0x1801e668d  mov     ecx, r8d
0x1801e6690  imul    rcx, rax
0x1801e6694  mov     r9d, ecx
0x1801e6697  cmp     rcx, rdx
0x1801e669a  jbe     short loc_1801E669F
0x1801e669c  mov     r9d, edx
0x1801e669f  cmp     rdx, rcx
0x1801e66a2  sbb     ebx, ebx
0x1801e66a4  and     ebx, r10d
0x1801e66a7  cmp     rcx, rdx
0x1801e66aa  ja      short loc_1801E66CC
0x1801e66ac  mov     rdx, [rbp+57h+ppvBits]
0x1801e66b0  mov     rcx, rsi
0x1801e66b3  mov     rax, [rsi]
0x1801e66b6  mov     [rsp+0B0h+hSection], rdx
0x1801e66bb  xor     edx, edx
0x1801e66bd  mov     rax, [rax+38h]
0x1801e66c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e66c6  mov     ebx, eax
0x1801e66c8  test    eax, eax
0x1801e66ca  jns     short loc_1801E66E9
0x1801e66cc  mov     rcx, [rdi+80h]; ho
0x1801e66d3  test    rcx, rcx
0x1801e66d6  jz      short loc_1801E66E9
0x1801e66d8  call    cs:__imp_DeleteObject
0x1801e66de  mov     qword ptr [rdi+80h], 0
0x1801e66e9  mov     eax, ebx
0x1801e66eb  mov     rcx, [rbp+57h+var_30]
0x1801e66ef  xor     rcx, rsp; StackCookie
0x1801e66f2  call    __security_check_cookie
0x1801e66f7  mov     rbx, [rsp+0B0h+arg_18]
0x1801e66ff  add     rsp, 90h
0x1801e6706  pop     r14
0x1801e6708  pop     r12
0x1801e670a  pop     rdi
0x1801e670b  pop     rsi
0x1801e670c  pop     rbp
0x1801e670d  retn
0x1801e670e  lea     rdx, GUID_WICPixelFormat32bppBGR; Buf2
0x1801e6715  call    memcmp_0
0x1801e671a  test    eax, eax
0x1801e671c  jnz     loc_1801E67A5
0x1801e6722  mov     rax, [rsi]
0x1801e6725  lea     r8, [rbp+57h+var_7C]
0x1801e6729  lea     rdx, [rbp+57h+var_80]
0x1801e672d  mov     rcx, rsi
0x1801e6730  mov     rax, [rax+18h]
0x1801e6734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e6739  mov     ebx, eax
0x1801e673b  test    eax, eax
0x1801e673d  js      loc_1801E665C
0x1801e6743  mov     eax, [rbp+57h+var_80]
0x1801e6746  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x1801e674a  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x1801e674d  lea     rdx, [rbp+57h+pbmi]; pbmi
0x1801e6751  mov     eax, [rbp+57h+var_7C]
0x1801e6754  xorps   xmm0, xmm0
0x1801e6757  neg     eax
0x1801e6759  mov     [rsp+0B0h+offset], 0; offset
0x1801e6761  xor     r8d, r8d; usage
0x1801e6764  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x1801e6767  mov     rcx, r14; hdc
0x1801e676a  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], 0
0x1801e6772  movdqu  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x1801e6777  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x1801e677e  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x1801e6786  mov     [rsp+0B0h+hSection], 0; hSection
0x1801e678f  call    cs:__imp_CreateDIBSection
0x1801e6795  mov     [rdi+80h], rax
0x1801e679c  test    rax, rax
0x1801e679f  jnz     loc_1801E6660
0x1801e67a5  mov     ebx, r12d
0x1801e67a8  jmp     loc_1801E66CC
```
