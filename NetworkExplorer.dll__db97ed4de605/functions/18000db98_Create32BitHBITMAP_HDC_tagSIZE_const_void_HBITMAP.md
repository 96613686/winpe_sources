# Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)

- ea: `0x18000db98`
- end: `0x18000dc58`
- name: `?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(HDC, const struct tagSIZE *, void **, HBITMAP *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dc60`

## callees

- `0x18000db98`
- `0x18000f0a0`

## import_xrefs

- `GDI32!CreateDIBSection` at `0x18000dc1c`
- `GDI32!CreateDIBSection` at `0x18000dc1c`
- `USER32!ReleaseDC` at `0x18000dc2a`
- `USER32!ReleaseDC` at `0x18000dc2a`
- `USER32!GetDC` at `0x18000dbef`
- `USER32!GetDC` at `0x18000dbef`

## pseudocode

```c
__int64 __fastcall Create32BitHBITMAP(HDC a1, const struct tagSIZE *a2, void **a3, HBITMAP *a4)
{
  LONG cx; // eax
  HDC DC; // rax
  HDC v7; // rdi
  __int64 result; // rax
  BITMAPINFO pbmi; // [rsp+30h] [rbp-48h] BYREF

  *a4 = 0;
  cx = a2->cx;
  memset(&pbmi.bmiHeader.biWidth, 0, 40);
  pbmi.bmiHeader.biWidth = cx;
  pbmi.bmiHeader.biHeight = a2->cy;
  pbmi.bmiHeader.biSize = 40;
  *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  DC = GetDC(0);
  v7 = DC;
  if ( DC )
  {
    *a4 = CreateDIBSection(DC, &pbmi, 0, 0, 0, 0);
    ReleaseDC(0, v7);
  }
  result = 2147942414LL;
  if ( *a4 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18000db98  mov     [rsp+arg_0], rbx
0x18000db9d  push    rdi
0x18000db9e  sub     rsp, 70h
0x18000dba2  mov     rax, cs:__security_cookie
0x18000dba9  xor     rax, rsp
0x18000dbac  mov     [rsp+78h+var_18], rax
0x18000dbb1  xor     eax, eax
0x18000dbb3  mov     qword ptr [r9], 0
0x18000dbba  xorps   xmm0, xmm0
0x18000dbbd  mov     qword ptr [rsp+78h+pbmi.bmiHeader.biClrImportant], rax
0x18000dbc2  mov     eax, [rdx]
0x18000dbc4  xor     ecx, ecx; hWnd
0x18000dbc6  movups  xmmword ptr [rsp+78h+pbmi.bmiHeader.biWidth], xmm0
0x18000dbcb  mov     [rsp+78h+pbmi.bmiHeader.biWidth], eax
0x18000dbcf  mov     rbx, r9
0x18000dbd2  mov     eax, [rdx+4]
0x18000dbd5  mov     [rsp+78h+pbmi.bmiHeader.biHeight], eax
0x18000dbd9  movups  xmmword ptr [rsp+78h+pbmi.bmiHeader.biSizeImage], xmm0
0x18000dbde  mov     [rsp+78h+pbmi.bmiHeader.biSize], 28h ; '('
0x18000dbe6  mov     qword ptr [rsp+78h+pbmi.bmiHeader.biPlanes], 200001h
0x18000dbef  call    cs:__imp_GetDC
0x18000dbf5  mov     rdi, rax
0x18000dbf8  test    rax, rax
0x18000dbfb  jz      short loc_18000DC30
0x18000dbfd  mov     [rsp+78h+offset], 0; offset
0x18000dc05  lea     rdx, [rsp+78h+pbmi]; pbmi
0x18000dc0a  xor     r9d, r9d; ppvBits
0x18000dc0d  mov     [rsp+78h+hSection], 0; hSection
0x18000dc16  xor     r8d, r8d; usage
0x18000dc19  mov     rcx, rax; hdc
0x18000dc1c  call    cs:__imp_CreateDIBSection
0x18000dc22  mov     rdx, rdi; hDC
0x18000dc25  xor     ecx, ecx; hWnd
0x18000dc27  mov     [rbx], rax
0x18000dc2a  call    cs:__imp_ReleaseDC
0x18000dc30  xor     ecx, ecx
0x18000dc32  mov     eax, 8007000Eh
0x18000dc37  cmp     [rbx], rcx
0x18000dc3a  cmovnz  eax, ecx
0x18000dc3d  mov     rcx, [rsp+78h+var_18]
0x18000dc42  xor     rcx, rsp; StackCookie
0x18000dc45  call    __security_check_cookie
0x18000dc4a  mov     rbx, [rsp+78h+arg_0]
0x18000dc52  add     rsp, 70h
0x18000dc56  pop     rdi
0x18000dc57  retn
```
