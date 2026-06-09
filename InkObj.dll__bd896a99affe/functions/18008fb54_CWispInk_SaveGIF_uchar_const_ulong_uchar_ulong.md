# CWispInk::SaveGIF(uchar const *,ulong,uchar * *,ulong &)

- ea: `0x18008fb54`
- end: `0x18008fdb4`
- name: `?SaveGIF@CWispInk@@QEAAJPEBEKPEAPEAEAEAK@Z`
- size: `608`
- prototype: `__int64 __usercall@<rax>(CWispInk *__hidden this@<rcx>, const unsigned __int8 *@<rdx>, unsigned int@<r8d>, unsigned __int8 **@<r9>, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18008d3f8`
- `0x18008f934`

## callees

- `0x18000c788`
- `0x1800890b0`
- `0x18008c540`
- `0x18008fb54`
- `0x1800994a0`
- `0x180104f30`

## import_xrefs

- `USER32!IsRectEmpty` at `0x18008fbb5`
- `USER32!IsRectEmpty` at `0x18008fbda`
- `USER32!IsRectEmpty` at `0x18008fbb5`
- `USER32!IsRectEmpty` at `0x18008fbda`
- `USER32!GetDC` at `0x18008fbf0`
- `USER32!GetDC` at `0x18008fbf0`
- `USER32!ReleaseDC` at `0x18008fc0f`
- `USER32!ReleaseDC` at `0x18008fc5f`
- `USER32!ReleaseDC` at `0x18008fc0f`
- `USER32!ReleaseDC` at `0x18008fc5f`
- `GDI32!Rectangle` at `0x18008fcf9`
- `GDI32!Rectangle` at `0x18008fcf9`
- `GDI32!CreateCompatibleBitmap` at `0x18008fc50`
- `GDI32!CreateCompatibleBitmap` at `0x18008fc50`
- `GDI32!GetStockObject` at `0x18008fcbb`
- `GDI32!GetStockObject` at `0x18008fcd2`
- `GDI32!GetStockObject` at `0x18008fcbb`
- `GDI32!GetStockObject` at `0x18008fcd2`
- `GDI32!RestoreDC` at `0x18008fd3e`
- `GDI32!RestoreDC` at `0x18008fd3e`
- `GDI32!DeleteDC` at `0x18008fc71`
- `GDI32!DeleteDC` at `0x18008fd56`
- `GDI32!DeleteDC` at `0x18008fc71`
- `GDI32!DeleteDC` at `0x18008fd56`
- `GDI32!SetWindowOrgEx` at `0x18008fca1`
- `GDI32!SetWindowOrgEx` at `0x18008fca1`
- `GDI32!SaveDC` at `0x18008fc90`
- `GDI32!SaveDC` at `0x18008fc90`
- `GDI32!SetWindowExtEx` at `0x18008fcb3`
- `GDI32!SetWindowExtEx` at `0x18008fcb3`
- `GDI32!CreateCompatibleDC` at `0x18008fbfc`
- `GDI32!CreateCompatibleDC` at `0x18008fbfc`
- `GDI32!SelectObject` at `0x18008fc84`
- `GDI32!SelectObject` at `0x18008fcc7`
- `GDI32!SelectObject` at `0x18008fcde`
- `GDI32!SelectObject` at `0x18008fd4a`
- `GDI32!SelectObject` at `0x18008fc84`
- `GDI32!SelectObject` at `0x18008fcc7`
- `GDI32!SelectObject` at `0x18008fcde`
- `GDI32!SelectObject` at `0x18008fd4a`
- `GDI32!DeleteObject` at `0x18008fd85`
- `GDI32!DeleteObject` at `0x18008fd85`

## pseudocode

```c
__int64 __fastcall CWispInk::SaveGIF(
        CWispInk *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  HDC DC; // rbx
  HDC CompatibleDC; // rax
  HDC v11; // rdi
  LONG v12; // r13d
  HDC v13; // rcx
  LONG v14; // r12d
  HGDIOBJ v15; // rbx
  HGDIOBJ StockObject; // rax
  HGDIOBJ v17; // rax
  HBITMAP v18; // rsi
  unsigned int v19; // ebx
  HBITMAP h; // [rsp+30h] [rbp-51h]
  struct tagRECT v22; // [rsp+48h] [rbp-39h] BYREF
  RECT rc; // [rsp+58h] [rbp-29h] BYREF
  struct tagXFORM v24; // [rsp+68h] [rbp-19h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  rc = (RECT)*((_OWORD *)this + 8);
  if ( IsRectEmpty(&rc) )
  {
    rc = *CWispInk::GetBoundingBox(this, &v22, 0);
    if ( IsRectEmpty(&rc) )
      return 2147549183LL;
  }
  DC = GetDC(0);
  CompatibleDC = CreateCompatibleDC(DC);
  v11 = CompatibleDC;
  if ( !CompatibleDC )
  {
    ReleaseDC(0, DC);
    return 2147500037LL;
  }
  v12 = *((_DWORD *)this + 103);
  *(_QWORD *)&v22.right = 0;
  v13 = CompatibleDC;
  *(_QWORD *)&v22.left = 0;
  if ( DC )
    v13 = DC;
  v14 = *((_DWORD *)this + 104);
  v22.right = v12;
  v22.bottom = v14;
  h = CreateCompatibleBitmap(v13, v12 + 1, v14 + 1);
  ReleaseDC(0, DC);
  if ( h )
  {
    v15 = SelectObject(v11, h);
    SaveDC(v11);
    SetWindowOrgEx(v11, 0, 0, 0);
    SetWindowExtEx(v11, v12, v14, 0);
    StockObject = GetStockObject(0);
    SelectObject(v11, StockObject);
    v17 = GetStockObject(6);
    SelectObject(v11, v17);
    Rectangle(v11, 0, 0, v12 + 1, v14 + 1);
    memset(&v24, 0, sizeof(v24));
    MapRectToRect(&rc, &v22, &v24);
    CWispInk::Draw(this, v11, 0, &v24, 0);
    RestoreDC(v11, -1);
    v18 = (HBITMAP)SelectObject(v11, v15);
    DeleteDC(v11);
    if ( !v18 )
      return 2147500037LL;
    v19 = SaveBitmapAsGIF(v18, a2, a3, a4, a5);
    DeleteObject(v18);
    return v19;
  }
  else
  {
    DeleteDC(v11);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18008fb54  push    rbp
0x18008fb56  push    rbx
0x18008fb57  push    rsi
0x18008fb58  push    rdi
0x18008fb59  push    r12
0x18008fb5b  push    r13
0x18008fb5d  push    r14
0x18008fb5f  push    r15
0x18008fb61  lea     rbp, [rsp-17h]
0x18008fb66  sub     rsp, 98h
0x18008fb6d  mov     rax, cs:__security_cookie
0x18008fb74  xor     rax, rsp
0x18008fb77  mov     [rbp+4Fh+var_50], rax
0x18008fb7b  mov     rax, [rbp+4Fh+arg_20]
0x18008fb7f  xor     r12d, r12d
0x18008fb82  mov     [rbp+4Fh+var_90], r9
0x18008fb86  mov     r14d, r8d
0x18008fb89  mov     [rbp+4Fh+var_98], rax
0x18008fb8d  mov     r15, rdx
0x18008fb90  mov     rsi, rcx
0x18008fb93  test    rdx, rdx
0x18008fb96  jz      loc_18008FD8F
0x18008fb9c  test    r8d, r8d
0x18008fb9f  jz      loc_18008FD8F
0x18008fba5  movups  xmm0, xmmword ptr [rcx+80h]
0x18008fbac  lea     rcx, [rbp+4Fh+rc]; lprc
0x18008fbb0  movdqu  xmmword ptr [rbp+4Fh+rc.left], xmm0
0x18008fbb5  call    cs:__imp_IsRectEmpty
0x18008fbbb  test    eax, eax
0x18008fbbd  jz      short loc_18008FBEE
0x18008fbbf  xor     r8d, r8d; unsigned int
0x18008fbc2  lea     rdx, [rbp+4Fh+var_88]; retstr
0x18008fbc6  mov     rcx, rsi; this
0x18008fbc9  call    ?GetBoundingBox@CWispInk@@QEBA?AUtagRECT@@K@Z; CWispInk::GetBoundingBox(ulong)
0x18008fbce  lea     rcx, [rbp+4Fh+rc]; lprc
0x18008fbd2  movups  xmm0, xmmword ptr [rax]
0x18008fbd5  movdqu  xmmword ptr [rbp+4Fh+rc.left], xmm0
0x18008fbda  call    cs:__imp_IsRectEmpty
0x18008fbe0  test    eax, eax
0x18008fbe2  jz      short loc_18008FBEE
0x18008fbe4  mov     eax, 8000FFFFh
0x18008fbe9  jmp     loc_18008FD94
0x18008fbee  xor     ecx, ecx; hWnd
0x18008fbf0  call    cs:__imp_GetDC
0x18008fbf6  mov     rcx, rax; hdc
0x18008fbf9  mov     rbx, rax
0x18008fbfc  call    cs:__imp_CreateCompatibleDC
0x18008fc02  mov     rdi, rax
0x18008fc05  test    rax, rax
0x18008fc08  jnz     short loc_18008FC1F
0x18008fc0a  mov     rdx, rbx; hDC
0x18008fc0d  xor     ecx, ecx; hWnd
0x18008fc0f  call    cs:__imp_ReleaseDC
0x18008fc15  mov     eax, 80004005h
0x18008fc1a  jmp     loc_18008FD94
0x18008fc1f  mov     r13d, [rsi+19Ch]
0x18008fc26  test    rbx, rbx
0x18008fc29  mov     qword ptr [rbp+4Fh+var_88.right], r12
0x18008fc2d  mov     rcx, rdi
0x18008fc30  mov     qword ptr [rbp+4Fh+var_88.left], r12
0x18008fc34  cmovnz  rcx, rbx; hdc
0x18008fc38  mov     r12d, [rsi+1A0h]
0x18008fc3f  lea     edx, [r13+1]; cx
0x18008fc43  mov     [rbp+4Fh+var_88.right], r13d
0x18008fc47  mov     [rbp+4Fh+var_88.bottom], r12d
0x18008fc4b  lea     r8d, [r12+1]; cy
0x18008fc50  call    cs:__imp_CreateCompatibleBitmap
0x18008fc56  mov     rdx, rbx; hDC
0x18008fc59  xor     ecx, ecx; hWnd
0x18008fc5b  mov     [rbp+4Fh+h], rax
0x18008fc5f  call    cs:__imp_ReleaseDC
0x18008fc65  mov     rax, [rbp+4Fh+h]
0x18008fc69  mov     rcx, rdi; hdc
0x18008fc6c  test    rax, rax
0x18008fc6f  jnz     short loc_18008FC81
0x18008fc71  call    cs:__imp_DeleteDC
0x18008fc77  mov     eax, 8007000Eh
0x18008fc7c  jmp     loc_18008FD94
0x18008fc81  mov     rdx, rax; h
0x18008fc84  call    cs:__imp_SelectObject
0x18008fc8a  mov     rcx, rdi; hdc
0x18008fc8d  mov     rbx, rax
0x18008fc90  call    cs:__imp_SaveDC
0x18008fc96  xor     r9d, r9d; lppt
0x18008fc99  xor     r8d, r8d; y
0x18008fc9c  xor     edx, edx; x
0x18008fc9e  mov     rcx, rdi; hdc
0x18008fca1  call    cs:__imp_SetWindowOrgEx
0x18008fca7  xor     r9d, r9d; lpsz
0x18008fcaa  mov     r8d, r12d; y
0x18008fcad  mov     edx, r13d; x
0x18008fcb0  mov     rcx, rdi; hdc
0x18008fcb3  call    cs:__imp_SetWindowExtEx
0x18008fcb9  xor     ecx, ecx; i
0x18008fcbb  call    cs:__imp_GetStockObject
0x18008fcc1  mov     rdx, rax; h
0x18008fcc4  mov     rcx, rdi; hdc
0x18008fcc7  call    cs:__imp_SelectObject
0x18008fccd  mov     ecx, 6; i
0x18008fcd2  call    cs:__imp_GetStockObject
0x18008fcd8  mov     rdx, rax; h
0x18008fcdb  mov     rcx, rdi; hdc
0x18008fcde  call    cs:__imp_SelectObject
0x18008fce4  lea     eax, [r12+1]
0x18008fce9  xor     r8d, r8d; top
0x18008fcec  lea     r9d, [r13+1]; right
0x18008fcf0  mov     [rsp+0D0h+bottom], eax; bottom
0x18008fcf4  xor     edx, edx; left
0x18008fcf6  mov     rcx, rdi; hdc
0x18008fcf9  call    cs:__imp_Rectangle
0x18008fcff  xorps   xmm0, xmm0
0x18008fd02  lea     r8, [rbp+4Fh+var_68]; struct tagXFORM *
0x18008fd06  xor     eax, eax
0x18008fd08  lea     rdx, [rbp+4Fh+var_88]; struct tagRECT *
0x18008fd0c  lea     rcx, [rbp+4Fh+rc]; struct tagRECT *
0x18008fd10  mov     qword ptr [rbp+4Fh+var_68.eDx], rax
0x18008fd14  movups  xmmword ptr [rbp+4Fh+var_68.eM11], xmm0
0x18008fd18  call    ?MapRectToRect@@YAXAEBUtagRECT@@0AEAUtagXFORM@@@Z; MapRectToRect(tagRECT const &,tagRECT const &,tagXFORM &)
0x18008fd1d  lea     r9, [rbp+4Fh+var_68]; struct tagXFORM *
0x18008fd21  mov     qword ptr [rsp+0D0h+bottom], 0; struct CStrokeSetImpl *
0x18008fd2a  xor     r8d, r8d; struct tagXFORM *
0x18008fd2d  mov     rdx, rdi; HDC
0x18008fd30  mov     rcx, rsi; this
0x18008fd33  call    ?Draw@CWispInk@@QEAAJPEAUHDC__@@PEBUtagXFORM@@1PEBVCStrokeSetImpl@@@Z; CWispInk::Draw(HDC__ *,tagXFORM const *,tagXFORM const *,CStrokeSetImpl const *)
0x18008fd38  or      edx, 0FFFFFFFFh; nSavedDC
0x18008fd3b  mov     rcx, rdi; hdc
0x18008fd3e  call    cs:__imp_RestoreDC
0x18008fd44  mov     rdx, rbx; h
0x18008fd47  mov     rcx, rdi; hdc
0x18008fd4a  call    cs:__imp_SelectObject
0x18008fd50  mov     rcx, rdi; hdc
0x18008fd53  mov     rsi, rax
0x18008fd56  call    cs:__imp_DeleteDC
0x18008fd5c  test    rsi, rsi
0x18008fd5f  jz      loc_18008FC15
0x18008fd65  mov     rax, [rbp+4Fh+var_98]
0x18008fd69  mov     r8d, r14d; unsigned int
0x18008fd6c  mov     r9, [rbp+4Fh+var_90]; unsigned __int8 **
0x18008fd70  mov     rdx, r15; unsigned __int8 *
0x18008fd73  mov     rcx, rsi; HBITMAP
0x18008fd76  mov     qword ptr [rsp+0D0h+bottom], rax; unsigned int *
0x18008fd7b  call    ?SaveBitmapAsGIF@@YAJPEAUHBITMAP__@@PEBEKPEAPEAEAEAK@Z; SaveBitmapAsGIF(HBITMAP__ *,uchar const *,ulong,uchar * *,ulong &)
0x18008fd80  mov     rcx, rsi; ho
0x18008fd83  mov     ebx, eax
0x18008fd85  call    cs:__imp_DeleteObject
0x18008fd8b  mov     eax, ebx
0x18008fd8d  jmp     short loc_18008FD94
0x18008fd8f  mov     eax, 80070057h
0x18008fd94  mov     rcx, [rbp+4Fh+var_50]
0x18008fd98  xor     rcx, rsp; StackCookie
0x18008fd9b  call    __security_check_cookie
0x18008fda0  add     rsp, 98h
0x18008fda7  pop     r15
0x18008fda9  pop     r14
0x18008fdab  pop     r13
0x18008fdad  pop     r12
0x18008fdaf  pop     rdi
0x18008fdb0  pop     rsi
0x18008fdb1  pop     rbx
0x18008fdb2  pop     rbp
0x18008fdb3  retn
```
