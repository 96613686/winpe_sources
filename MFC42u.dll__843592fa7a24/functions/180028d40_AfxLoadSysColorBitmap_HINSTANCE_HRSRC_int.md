# AfxLoadSysColorBitmap(HINSTANCE__ *,HRSRC__ *,int)

- ea: `0x180028d40`
- end: `0x180028f57`
- name: `?AfxLoadSysColorBitmap@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@PEAUHRSRC__@@H@Z`
- size: `535`
- prototype: `HBITMAP __fastcall(HINSTANCE, HRSRC, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002d60`
- `0x180048cb0`

## callees

- `0x180028d40`
- `0x1800d1f7a`

## import_xrefs

- `msvcrt!free` at `0x180028f29`
- `msvcrt!free` at `0x180028f29`
- `msvcrt!malloc` at `0x180028d94`
- `msvcrt!malloc` at `0x180028d94`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180028d5c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180028d5c`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180028d71`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180028d71`
- `api-ms-win-core-libraryloader-l1-2-0!FreeResource` at `0x180028f32`
- `api-ms-win-core-libraryloader-l1-2-0!FreeResource` at `0x180028f32`
- `USER32!GetSysColor` at `0x180028dfa`
- `USER32!GetSysColor` at `0x180028e12`
- `USER32!GetSysColor` at `0x180028e2f`
- `USER32!GetSysColor` at `0x180028dfa`
- `USER32!GetSysColor` at `0x180028e12`
- `USER32!GetSysColor` at `0x180028e2f`
- `USER32!ReleaseDC` at `0x180028f20`
- `USER32!ReleaseDC` at `0x180028f20`
- `USER32!GetDC` at `0x180028e71`
- `USER32!GetDC` at `0x180028e71`
- `GDI32!DeleteDC` at `0x180028f15`
- `GDI32!DeleteDC` at `0x180028f15`
- `GDI32!StretchDIBits` at `0x180028f00`
- `GDI32!StretchDIBits` at `0x180028f00`
- `GDI32!CreateCompatibleBitmap` at `0x180028e83`
- `GDI32!CreateCompatibleBitmap` at `0x180028e83`
- `GDI32!CreateCompatibleDC` at `0x180028e98`
- `GDI32!CreateCompatibleDC` at `0x180028e98`
- `GDI32!SelectObject` at `0x180028ea7`
- `GDI32!SelectObject` at `0x180028f0c`
- `GDI32!SelectObject` at `0x180028ea7`
- `GDI32!SelectObject` at `0x180028f0c`

## pseudocode

```c
HBITMAP __fastcall AfxLoadSysColorBitmap(HINSTANCE a1, HRSRC a2, int a3)
{
  int v3; // edi
  HGLOBAL Resource; // rax
  void *v5; // r12
  unsigned int *v6; // rax
  unsigned int *v7; // r15
  unsigned int v8; // edx
  unsigned int v9; // ebx
  unsigned int *v10; // rax
  unsigned int *lpbmi; // rsi
  char *v12; // r14
  __int64 i; // rbp
  unsigned int j; // ecx
  __int64 v15; // r13
  int v16; // ecx
  int v17; // ebx
  DWORD v18; // edi
  int v19; // ecx
  int v20; // ebx
  int SrcWidth; // r13d
  HDC DC; // rbp
  HBITMAP CompatibleBitmap; // r14
  HDC CompatibleDC; // rdi
  HGDIOBJ v25; // rbx
  int DestHeight; // [rsp+C8h] [rbp+20h]

  v3 = a3;
  Resource = LoadResource(a1, a2);
  v5 = Resource;
  if ( !Resource )
    return 0;
  v6 = (unsigned int *)LockResource(Resource);
  v7 = v6;
  if ( !v6 )
    return 0;
  v8 = *v6 + 64;
  if ( v8 < *v6 )
    return 0;
  v9 = *v6 + 64;
  v10 = (unsigned int *)malloc(v8);
  lpbmi = v10;
  if ( !v10 )
    return 0;
  memcpy_0(v10, v7, v9);
  v12 = (char *)lpbmi + *lpbmi;
  for ( i = 0; i != 16; ++i )
  {
    for ( j = 0; j < 4; ++j )
    {
      v15 = (int)j;
      if ( *(_DWORD *)&v12[4 * i] == *((_DWORD *)&_afxSysColorMap + 2 * (int)j) )
      {
        v16 = *((_DWORD *)&_afxSysColorMap + 2 * (int)j + 1);
        if ( v3 )
        {
          if ( v16 != 18 )
            *(_DWORD *)&v12[4 * i] = 0xFFFFFF;
        }
        else
        {
          v17 = (unsigned __int8)(GetSysColor(v16) >> 16);
          v18 = v17 | GetSysColor(*((_DWORD *)&_afxSysColorMap + 2 * v15 + 1)) & 0xFF00;
          v19 = v18 | ((unsigned __int8)GetSysColor(*((_DWORD *)&_afxSysColorMap + 2 * v15 + 1)) << 16);
          v3 = a3;
          *(_DWORD *)&v12[4 * i] = v19;
        }
        break;
      }
    }
  }
  v20 = lpbmi[2];
  SrcWidth = lpbmi[1];
  DestHeight = v20;
  DC = GetDC(0);
  CompatibleBitmap = CreateCompatibleBitmap(DC, SrcWidth, v20);
  if ( CompatibleBitmap )
  {
    CompatibleDC = CreateCompatibleDC(DC);
    v25 = SelectObject(CompatibleDC, CompatibleBitmap);
    StretchDIBits(
      CompatibleDC,
      0,
      0,
      SrcWidth,
      DestHeight,
      0,
      0,
      SrcWidth,
      DestHeight,
      &v7[(1LL << *((_BYTE *)lpbmi + 14)) + 10],
      (const BITMAPINFO *)lpbmi,
      0,
      0xCC0020u);
    SelectObject(CompatibleDC, v25);
    DeleteDC(CompatibleDC);
  }
  ReleaseDC(0, DC);
  free(lpbmi);
  FreeResource(v5);
  return CompatibleBitmap;
}

```

## disassembly

```asm
0x180028d40  mov     [rsp+arg_0], rbx
0x180028d45  mov     [rsp+arg_10], r8d
0x180028d4a  push    rbp
0x180028d4b  push    rsi
0x180028d4c  push    rdi
0x180028d4d  push    r12
0x180028d4f  push    r13
0x180028d51  push    r14
0x180028d53  push    r15
0x180028d55  sub     rsp, 70h
0x180028d59  mov     edi, r8d
0x180028d5c  call    cs:__imp_LoadResource
0x180028d62  mov     r12, rax
0x180028d65  test    rax, rax
0x180028d68  jz      loc_180028F3D
0x180028d6e  mov     rcx, rax; hResData
0x180028d71  call    cs:__imp_LockResource
0x180028d77  mov     r15, rax
0x180028d7a  test    rax, rax
0x180028d7d  jz      loc_180028F3D
0x180028d83  mov     ecx, [rax]
0x180028d85  lea     edx, [rcx+40h]
0x180028d88  cmp     edx, ecx
0x180028d8a  jb      loc_180028F3D
0x180028d90  mov     ecx, edx; Size
0x180028d92  mov     ebx, edx
0x180028d94  call    cs:__imp_malloc
0x180028d9a  mov     rsi, rax
0x180028d9d  test    rax, rax
0x180028da0  jz      loc_180028F3D
0x180028da6  mov     r8d, ebx; Size
0x180028da9  mov     rdx, r15; Src
0x180028dac  mov     rcx, rax; void *
0x180028daf  call    memcpy_0
0x180028db4  mov     r14d, [rsi]
0x180028db7  lea     r8, ?_afxSysColorMap@@3QBUAFX_COLORMAP@@B; AFX_COLORMAP const near * const _afxSysColorMap
0x180028dbe  add     r14, rsi
0x180028dc1  xor     ebp, ebp
0x180028dc3  lea     edx, [rbp+1]
0x180028dc6  xor     ecx, ecx
0x180028dc8  cmp     ecx, 4
0x180028dcb  jnb     loc_180028E54
0x180028dd1  movsxd  r13, ecx
0x180028dd4  mov     eax, [r8+r13*8]
0x180028dd8  cmp     [r14+rbp*4], eax
0x180028ddc  jz      short loc_180028DE2
0x180028dde  add     ecx, edx
0x180028de0  jmp     short loc_180028DC8
0x180028de2  mov     ecx, [r8+r13*8+4]; nIndex
0x180028de7  test    edi, edi
0x180028de9  jz      short loc_180028DFA
0x180028deb  cmp     ecx, 12h
0x180028dee  jz      short loc_180028E54
0x180028df0  mov     dword ptr [r14+rbp*4], 0FFFFFFh
0x180028df8  jmp     short loc_180028E54
0x180028dfa  call    cs:__imp_GetSysColor
0x180028e00  lea     rcx, ?_afxSysColorMap@@3QBUAFX_COLORMAP@@B; AFX_COLORMAP const near * const _afxSysColorMap
0x180028e07  shr     eax, 10h
0x180028e0a  mov     ecx, [rcx+r13*8+4]; nIndex
0x180028e0f  movzx   ebx, al
0x180028e12  call    cs:__imp_GetSysColor
0x180028e18  movzx   edi, ax
0x180028e1b  lea     rax, ?_afxSysColorMap@@3QBUAFX_COLORMAP@@B; AFX_COLORMAP const near * const _afxSysColorMap
0x180028e22  mov     ecx, [rax+r13*8+4]; nIndex
0x180028e27  and     edi, 0FFFFFF00h
0x180028e2d  or      edi, ebx
0x180028e2f  call    cs:__imp_GetSysColor
0x180028e35  movzx   ecx, al
0x180028e38  mov     edx, 1
0x180028e3d  shl     ecx, 10h
0x180028e40  lea     r8, ?_afxSysColorMap@@3QBUAFX_COLORMAP@@B; AFX_COLORMAP const near * const _afxSysColorMap
0x180028e47  or      ecx, edi
0x180028e49  mov     edi, [rsp+0A8h+arg_10]
0x180028e50  mov     [r14+rbp*4], ecx
0x180028e54  inc     rbp
0x180028e57  cmp     rbp, 10h
0x180028e5b  jnz     loc_180028DC6
0x180028e61  mov     ebx, [rsi+8]
0x180028e64  xor     ecx, ecx; hWnd
0x180028e66  mov     r13d, [rsi+4]
0x180028e6a  mov     [rsp+0A8h+arg_18], ebx
0x180028e71  call    cs:__imp_GetDC
0x180028e77  mov     r8d, ebx; cy
0x180028e7a  mov     edx, r13d; cx
0x180028e7d  mov     rcx, rax; hdc
0x180028e80  mov     rbp, rax
0x180028e83  call    cs:__imp_CreateCompatibleBitmap
0x180028e89  mov     r14, rax
0x180028e8c  test    rax, rax
0x180028e8f  jz      loc_180028F1B
0x180028e95  mov     rcx, rbp; hdc
0x180028e98  call    cs:__imp_CreateCompatibleDC
0x180028e9e  mov     rcx, rax; hdc
0x180028ea1  mov     rdx, r14; h
0x180028ea4  mov     rdi, rax
0x180028ea7  call    cs:__imp_SelectObject
0x180028ead  mov     cl, [rsi+0Eh]
0x180028eb0  xor     edx, edx; xDest
0x180028eb2  mov     [rsp+0A8h+rop], 0CC0020h; rop
0x180028eba  mov     rbx, rax
0x180028ebd  mov     [rsp+0A8h+iUsage], edx; iUsage
0x180028ec1  mov     eax, 1
0x180028ec6  mov     [rsp+0A8h+lpbmi], rsi; lpbmi
0x180028ecb  mov     r9d, r13d; DestWidth
0x180028ece  shl     rax, cl
0x180028ed1  xor     r8d, r8d; yDest
0x180028ed4  lea     rcx, [rax+0Ah]
0x180028ed8  mov     eax, [rsp+0A8h+arg_18]
0x180028edf  lea     rcx, [r15+rcx*4]
0x180028ee3  mov     [rsp+0A8h+lpBits], rcx; lpBits
0x180028ee8  mov     rcx, rdi; hdc
0x180028eeb  mov     [rsp+0A8h+SrcHeight], eax; SrcHeight
0x180028eef  mov     [rsp+0A8h+SrcWidth], r13d; SrcWidth
0x180028ef4  mov     [rsp+0A8h+ySrc], edx; ySrc
0x180028ef8  mov     [rsp+0A8h+xSrc], edx; xSrc
0x180028efc  mov     [rsp+0A8h+DestHeight], eax; DestHeight
0x180028f00  call    cs:__imp_StretchDIBits
0x180028f06  mov     rdx, rbx; h
0x180028f09  mov     rcx, rdi; hdc
0x180028f0c  call    cs:__imp_SelectObject
0x180028f12  mov     rcx, rdi; hdc
0x180028f15  call    cs:__imp_DeleteDC
0x180028f1b  mov     rdx, rbp; hDC
0x180028f1e  xor     ecx, ecx; hWnd
0x180028f20  call    cs:__imp_ReleaseDC
0x180028f26  mov     rcx, rsi; Block
0x180028f29  call    cs:__imp_free
0x180028f2f  mov     rcx, r12; hResData
0x180028f32  call    cs:__imp_FreeResource
0x180028f38  mov     rax, r14
0x180028f3b  jmp     short loc_180028F3F
0x180028f3d  xor     eax, eax
0x180028f3f  mov     rbx, [rsp+0A8h+arg_0]
0x180028f47  add     rsp, 70h
0x180028f4b  pop     r15
0x180028f4d  pop     r14
0x180028f4f  pop     r13
0x180028f51  pop     r12
0x180028f53  pop     rdi
0x180028f54  pop     rsi
0x180028f55  pop     rbp
0x180028f56  retn
```
